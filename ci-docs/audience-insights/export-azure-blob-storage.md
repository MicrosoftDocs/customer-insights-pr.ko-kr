---
title: Azure Blob Storage로 Customer Insights 데이터 내보내기
description: 연결을 구성하고 Azure Blob Storage로 내보내는 방법을 알아봅니다.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 294feff2f77c3756fbadb36c90aab430454f5967
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760197"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="51841-103">세그먼트 목록 및 기타 데이터를 Azure Blob Storage로 내보내기(프리뷰)</span><span class="sxs-lookup"><span data-stu-id="51841-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="51841-104">Blob Storage에 Customer Insights 데이터를 저장하거나 다른 애플리케이션으로 데이터를 전송하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="51841-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="51841-105">Blob Storage에 대한 연결 수립하기.</span><span class="sxs-lookup"><span data-stu-id="51841-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="51841-106">**관리자** > **연결** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="51841-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="51841-107">**연결 추가** 와 **Azure Blob Storage** 를 선택하여 연결을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="51841-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="51841-108">**표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="51841-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="51841-109">이름 및 연결 유형은 이 연결을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="51841-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="51841-110">이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="51841-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="51841-111">이 연결을 사용할 수 있는 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="51841-111">Choose who can use this connection.</span></span> <span data-ttu-id="51841-112">아무 조치도 취하지 않으면 기본값은 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="51841-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="51841-113">자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="51841-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="51841-114">Azure Blob Storage의 **계정 이름**, **계정 키** 및 **컨테이너** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="51841-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="51841-115">Blob Storage 계정 이름 및 계정 키를 찾는 방법에 대한 자세한 내용은 [Azure Portal에서 스토리지 계정 설정 관리](/azure/storage/common/storage-account-manage)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51841-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="51841-116">컨테이너를 만드는 방법을 배우려면 [컨테이너 만들기](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51841-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="51841-117">연결을 완료하려면 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="51841-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="51841-118">내보내기 구성</span><span class="sxs-lookup"><span data-stu-id="51841-118">Configure an export</span></span>

<span data-ttu-id="51841-119">이 유형의 연결에 대한 액세스 권한이 있는 경우 이 내보내기를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51841-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="51841-120">자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51841-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="51841-121">**데이터** > **내보내기** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="51841-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="51841-122">**대상 추가** 를 선택하여 새 내보내기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="51841-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="51841-123">**내보내기 연결** 필드의 Azure Blob Storage 섹션에서 연결을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="51841-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="51841-124">이 섹션 이름이 표시되지 않으면 사용 가능한 이 유형의 연결이 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="51841-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="51841-125">이 대상으로 내보내려는 각 엔터티 옆의 상자를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="51841-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="51841-126">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="51841-126">Select **Save**.</span></span>

<span data-ttu-id="51841-127">내보내기를 저장해도 내보내기가 즉시 실행되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51841-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="51841-128">내보내기는 모든 [예약된 새로 고침](system.md#schedule-tab)에 따라 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="51841-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="51841-129">[주문형으로 데이터를 내보낼](export-destinations.md#run-exports-on-demand)수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51841-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="51841-130">내보낸 데이터는 구성한 Blob Storage 컨테이너에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="51841-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="51841-131">컨테이너에 다음 폴더 경로가 자동으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="51841-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="51841-132">원본 엔터티 및 시스템에서 생성된 엔터티의 경우:`%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="51841-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="51841-133">예: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="51841-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="51841-134">내보낸 엔터티의 model.json은 %ExportDestinationName% 수준에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51841-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="51841-135">예: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="51841-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
