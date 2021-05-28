---
title: Customer Insights 데이터를 Azure Synapse 분석으로 내보내기
description: Azure Synapse 분석에 대한 연결을 구성하는 방법을 알아봅니다.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977385"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="657e8-103">Azure Synapse 분석으로 데이터 내보내기(프리뷰)</span><span class="sxs-lookup"><span data-stu-id="657e8-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="657e8-104">Azure Synapse은 데이터 웨어하우스 및 빅 데이터 시스템 전체에서 인사이트를 얻는 시간을 가속화하는 분석 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="657e8-105">[Azure Synapse](/azure/synapse-analytics/overview-what-is)에서 Customer Insights 데이터를 수집하고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="657e8-106">필수 조건</span><span class="sxs-lookup"><span data-stu-id="657e8-106">Prerequisites</span></span>

<span data-ttu-id="657e8-107">Customer Insights에서 Azure Synapse로의 연결을 구성하려면 다음 필수 조건을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="657e8-108">설명된 대로 모든 **역할 할당** 을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="657e8-109">Customer Insights의 필수 조건</span><span class="sxs-lookup"><span data-stu-id="657e8-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="657e8-110">귀하는 대상 그룹 인사이트에서 **관리자** 역할을 갖고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="657e8-111">[대상 그룹 인사이트에서 사용자 권한 설정](permissions.md#assign-roles-and-permissions)에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="657e8-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="657e8-112">Azure에서:</span><span class="sxs-lookup"><span data-stu-id="657e8-112">In Azure:</span></span> 

- <span data-ttu-id="657e8-113">활성 Azure 구독.</span><span class="sxs-lookup"><span data-stu-id="657e8-113">An active Azure subscription.</span></span>

- <span data-ttu-id="657e8-114">Azure Data Lake Storage Gen2 계정을 사용하는 경우 *대상 그룹 인사이트에 대한 서비스 주체는* **스토리지 Blob 데이터 기여자** 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="657e8-115">[대상 그룹 인사이트에 대한 Azure 서비스 주체를 사용하여 Azure Data Lake Storage Gen2 계정에 연결](connect-service-principal.md)에 대해 자세히 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="657e8-116">Data Lake Storage Gen2에는 [계층적 네임스페이스](/azure/storage/blobs/data-lake-storage-namespace)가 활성화되어 **있어야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="657e8-117">리소스 그룹에는 Azure Synapse 작업 영역이 있으며 *서비스 주체* 및 *대상 그룹 인사이트 사용자* 는 **Reader** 이상의 권한을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="657e8-118">자세한 내용은 [Azure Portal을 사용하여 Azure 역할 할당](/azure/role-based-access-control/role-assignments-portal)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="657e8-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="657e8-119">*사용자* 는 데이터가 있고 Azure Synapse 작업 영역에 연결된 Azure Data Lake Storage Gen2 계정에 대한 **스토리지 Blob 데이터 기여자** 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="657e8-120">[Azure Portal을 사용하여 Blob 및 큐 데이터에 대한 액세스를 위한 Azure 역할 할당](/azure/storage/common/storage-auth-aad-rbac-portal) 및 [스토리지 Blob 데이터 기여자 권한](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)에 대해 자세히 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="657e8-121">*[Azure Synapse 작업 영역 관리 ID](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* 는 데이터가 있고 Azure Synapse 작업 영역에 연결된 Azure Data Lake Storage Gen2 계정에 대한 **스토리지 Blob 데이터 기여자** 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="657e8-122">[Azure Portal을 사용하여 Blob 및 큐 데이터에 대한 액세스를 위한 Azure 역할 할당](/azure/storage/common/storage-auth-aad-rbac-portal) 및 [스토리지 Blob 데이터 기여자 권한](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)에 대해 자세히 알아보기.</span><span class="sxs-lookup"><span data-stu-id="657e8-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="657e8-123">Azure Synapse 작업 영역에서 *대상 그룹 인사이트의 서비스 주체* 는 **Synapse 관리자** 역할이 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="657e8-124">자세한 내용은 [Synapse 작업 영역에 대한 액세스 제어를 설정하는 방법](/azure/synapse-analytics/security/how-to-set-up-access-control)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="657e8-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="657e8-125">연결을 설정하고 Azure Synapse로 내보내기</span><span class="sxs-lookup"><span data-stu-id="657e8-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="657e8-126">연결 구성</span><span class="sxs-lookup"><span data-stu-id="657e8-126">Configure a connection</span></span>

1. <span data-ttu-id="657e8-127">**관리자** > **연결** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="657e8-128">**연결 추가** 를 선택하고 **Azure Synapse 분석** 을 선택하거나 **Azure Synapse 분석** 타일에서 **설정** 을 선택하여 연결을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="657e8-129">표시 이름 필드에서 연결에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="657e8-130">이름 및 연결 유형은 이 연결을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="657e8-131">이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="657e8-132">이 연결을 사용할 수 있는 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-132">Choose who can use this connection.</span></span> <span data-ttu-id="657e8-133">아무 조치도 취하지 않으면 기본값은 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="657e8-134">자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="657e8-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="657e8-135">Customer Insights 데이터를 사용할 구독을 선택하거나 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="657e8-136">구독을 선택하자마자 **작업 영역**, **스토리지 계정** 및 **컨테이너** 를 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="657e8-137">**저장** 을 ​​선택하여 연결을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="657e8-138">내보내기 구성</span><span class="sxs-lookup"><span data-stu-id="657e8-138">Configure an export</span></span>

<span data-ttu-id="657e8-139">이 유형의 연결에 대한 액세스 권한이 있는 경우 이 내보내기를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="657e8-140">자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="657e8-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="657e8-141">**데이터** > **내보내기** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="657e8-142">**내보내기 추가** 를 선택하여 새 내보내기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="657e8-143">**내보내기 연결** 필드의 **Azure Synapse 분석** 섹션에서 연결을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="657e8-144">이 섹션 이름이 표시되지 않으면 사용 가능한 이 유형의 [연결](connections.md)이 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="657e8-145">내보내기에 대해 알아볼 수 있는 **표시 이름** 과 **데이터베이스 이름** 을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="657e8-146">Azure Synapse 분석으로 내보낼 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="657e8-147">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-147">Select **Save**.</span></span>

<span data-ttu-id="657e8-148">내보내기를 저장해도 내보내기가 즉시 실행되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="657e8-149">내보내기는 모든 [예약된 새로 고침](system.md#schedule-tab)에 따라 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="657e8-150">[주문형으로 데이터를 내보낼](export-destinations.md#run-exports-on-demand)수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="657e8-151">내보내기 업데이트</span><span class="sxs-lookup"><span data-stu-id="657e8-151">Update an export</span></span>

1. <span data-ttu-id="657e8-152">**데이터** > **내보내기** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="657e8-153">업데이트하려는 내보내기에 대한 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="657e8-154">선택 항목에서 엔터티를 **추가** 또는 **제거** 합니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="657e8-155">선택 항목에서 엔터티가 제거되면 Synapse 분석 데이터베이스에서 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="657e8-156">그러나 향후 데이터 새로 고침은 해당 데이터베이스에서 제거된 항목을 업데이트하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="657e8-157">**데이터베이스 이름 변경** 은 새로운 Synapse 분석 데이터베이스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="657e8-158">이전에 구성된 이름의 데이터베이스는 향후 새로 고침에서 업데이트를 수신하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="657e8-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
