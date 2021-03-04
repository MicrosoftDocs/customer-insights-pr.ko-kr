---
title: Common Data Model 데이터를 Azure Data Lake 계정에 연결
description: Azure Data Lake Storage를 사용하여 Common Data Model 데이터로 작업합니다.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 247e4d9c47ff2373065ebf3c6d554323e45a120b
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267868"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="107a5-103">Azure Data Lake 계정을 사용하여 Common Data Model 폴더에 연결</span><span class="sxs-lookup"><span data-stu-id="107a5-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="107a5-104">이 문서에서는 Azure Data Lake Storage Gen2 계정을 사용하여 Common Data Model 폴더에서 데이터를 수집하는 방법에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="107a5-105">중요 사항</span><span class="sxs-lookup"><span data-stu-id="107a5-105">Important considerations</span></span>

- <span data-ttu-id="107a5-106">Azure Data Lake의 데이터는 Common Data Model 표준을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="107a5-107">현재 다른 형식은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="107a5-108">데이터 수집은 Azure Data Lake *Gen2* 스토리지 계정을 독점적으로 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="107a5-109">Azure Data Lake Gen1 스토리지 계정을 사용하여 데이터를 수집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="107a5-110">Azure 서비스 주체로 인증하려면 테넌트에 구성되어 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="107a5-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="107a5-111">자세한 내용은 [Azure 서비스 보안 주체를 사용하여 대상 그룹 인사이트를 Azure Data Lake Storage Gen2 계정에 연결](connect-service-principal.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="107a5-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="107a5-112">연결하고 데이터를 수집하려는 Azure Data Lake는 Dynamics 365 Customer Insights 환경과 동일한 Azure 지역에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="107a5-113">다른 Azure 지역의 데이터 레이크에서 Common Data Model 폴더에 대한 연결은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="107a5-114">환경의 Azure 지역을 확인하려면 대상 그룹 인사이트에서 **관리** > **시스템** > **정보** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="107a5-115">온라인 서비스에 저장된 데이터는 Dynamics 365 Customer Insights에서 데이터가 처리되거나 저장되는 위치와 다른 위치에 저장될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="107a5-116">온라인 서비스에서 데이터를 가져오거나 이에 연결하면 해당 데이터가 Dynamics 365 Customer Insights에 전송되거나 저장될 수 있음에 동의하는 것입니다. [Microsoft 보안 센터에서 자세히 알아보십시오.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="107a5-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="107a5-117">Common Data Model 폴더에 연결</span><span class="sxs-lookup"><span data-stu-id="107a5-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="107a5-118">대상 그룹 인사이트에서 **데이터** > **데이터 원본** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="107a5-119">**데이터 원본 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="107a5-120">**Common Data Model 폴더에 연결** 을 선택하고 데이터 원본의 **이름** 을 입력한 후 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span> <span data-ttu-id="107a5-121">이름 지침:</span><span class="sxs-lookup"><span data-stu-id="107a5-121">Name guidelines:</span></span> 
   - <span data-ttu-id="107a5-122">문자로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-122">Start with a letter.</span></span>
   - <span data-ttu-id="107a5-123">문자와 숫자만 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="107a5-123">Use letters and numbers only.</span></span> <span data-ttu-id="107a5-124">특수 문자와 공백은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-124">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="107a5-125">3~64자 사이에서 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="107a5-125">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="107a5-126">인증을 위해 리소스 기반 옵션과 구독 기반 옵션 중에서 사용하여 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-126">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="107a5-127">자세한 내용은 [Azure 서비스 보안 주체를 사용하여 대상 그룹 인사이트를 Azure Data Lake Storage Gen2 계정에 연결](connect-service-principal.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="107a5-127">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="107a5-128">**컨테이너** 정보를 입력하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-128">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="107a5-129">![Azure Data Lake에 대한 새 연결 세부 정보를 입력하는 대화 상자](media/enter-new-storage-details.png)
   > </span><span class="sxs-lookup"><span data-stu-id="107a5-129">![Dialog box to enter new connection details for Azure Data Lake](media/enter-new-storage-details.png)
   > </span></span>[!NOTE]
<span data-ttu-id="107a5-130">위에서 언급한 컨테이너 또는 스토리지 계정에 연결하고 데이터 원본을 만들려면 다음 역할 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-130">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="107a5-131">스토리지 Blob 데이터 Reader</span><span class="sxs-lookup"><span data-stu-id="107a5-131">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="107a5-132">스토리지 Blob 데이터 담당자</span><span class="sxs-lookup"><span data-stu-id="107a5-132">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="107a5-133">Storage Blob 데이터 Contributor</span><span class="sxs-lookup"><span data-stu-id="107a5-133">Storage Blob Data Contributor</span></span>

1. <span data-ttu-id="107a5-134">**Common Data Model 폴더 선택** 대화상자에서 데이터를 가져올 model.json 또는 manifest.json 파일을 선택하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-134">In the **Select a Common Data Model folder** dialog, select the model.json or manifest.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="107a5-135">환경의 다른 데이터 원본과 연결된 model.json 또는 manifest.json 파일은 목록에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-135">Any model.json or manifest.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="107a5-136">선택한 model.json 또는 manifest.json 파일에서 사용 가능한 엔터티 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-136">You'll get a list of available entities in the selected model.json or manifest.json file.</span></span> <span data-ttu-id="107a5-137">사용 가능한 엔터티 목록에서 검토하고 선택한 후 **저장** 을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-137">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="107a5-138">선택한 모든 항목이 새 데이터 원본에서 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-138">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="107a5-139">![model.json 파일의 엔터티 목록을 표시하는 대화 상자](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="107a5-139">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="107a5-140">데이터 프로파일링을 사용할 데이터 엔터티를 지정하고 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-140">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="107a5-141">데이터 프로파일링을 통해 분석 및 기타 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-141">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="107a5-142">엔터티에서 모든 특성을 선택하는 전체 엔터티를 선택하거나 선택한 특정 특성을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-142">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="107a5-143">기본적으로 데이터 프로파일링에 대해 활성화된 엔터티가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-143">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="107a5-144">![데이터 프로파일링을 보여주는 대화 상자](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="107a5-144">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="107a5-145">선택 사항을 저장하면 **데이터 원본** 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-145">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="107a5-146">이제 Common Data Model 폴더 연결이 데이터 원본으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-146">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="107a5-147">model.json 파일 또는 manifest.json은 동일한 환경에서 하나의 데이터 원본에만 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-147">A model.json file or manifest.json can only associate with one data source in the same environment.</span></span> <span data-ttu-id="107a5-148">그러나 여러 환경의 데이터 원본에 동일한 model.json 또는 manifest.json 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-148">However, the same model.json or manifest.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="107a5-149">Common Data Model 폴더 데이터 원본 편집</span><span class="sxs-lookup"><span data-stu-id="107a5-149">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="107a5-150">Common Data Model 폴더가 포함된 스토리지 계정의 액세스 키를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-150">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="107a5-151">model.json 또는 manifest.json 파일을 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-151">You may also change the model.json or manifest.json file.</span></span> <span data-ttu-id="107a5-152">저장소 계정과 다른 컨테이너에 연결하거나 계정 이름을 변경하려면 [새로운 데이터 원본 연결을 만듭니다](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="107a5-152">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="107a5-153">대상 그룹 인사이트에서 **데이터** > **데이터 원본** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="107a5-154">업데이트하려는 데이터 원본 옆에 있는 줄임표를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="107a5-154">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="107a5-155">목록에서 **편집** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-155">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="107a5-156">선택적으로 **액세스 키** 를 업데이트하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-156">Optionally, update the **Access key** and select **Next**.</span></span>

   ![기존 데이터 원본에 대한 액세스 키를 편집하고 업데이트하는 대화 상자](media/edit-access-key.png)

5. <span data-ttu-id="107a5-158">선택적으로 계정 키 기반 연결에서 리소스 기반 또는 구독 기반 연결로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-158">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="107a5-159">자세한 내용은 [Azure 서비스 보안 주체를 사용하여 대상 그룹 인사이트를 Azure Data Lake Storage Gen2 계정에 연결](connect-service-principal.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="107a5-159">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="107a5-160">연결을 업데이트할 때 **컨테이너** 정보를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-160">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]

   > ![Azure Data Lake에 대한 연결 세부 정보를 기존 스토리지 계정에 입력하는 대화 상자](media/enter-existing-storage-details.png)

   > [!NOTE]
   > <span data-ttu-id="107a5-162">위에서 언급한 컨테이너 또는 스토리지 계정에 연결하고 데이터 원본을 만들려면 다음 역할 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-162">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="107a5-163">스토리지 Blob 데이터 Reader</span><span class="sxs-lookup"><span data-stu-id="107a5-163">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="107a5-164">스토리지 Blob 데이터 담당자</span><span class="sxs-lookup"><span data-stu-id="107a5-164">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="107a5-165">Storage Blob 데이터 Contributor</span><span class="sxs-lookup"><span data-stu-id="107a5-165">Storage Blob Data Contributo</span></span>


6. <span data-ttu-id="107a5-166">선택적으로, 컨테이너와 다른 엔터티 집합이 있는 다른 model.json 또는 manifest.json 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-166">Optionally, choose a different model.json or manifest.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="107a5-167">선택적으로 수집할 추가 엔터티를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-167">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="107a5-168">종속성이 없는 경우 이미 선택된 엔터티를 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-168">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="107a5-169">기존 model.json 또는 manifest.json 파일과 엔티티 집합에 대한 종속성이 있는 경우 오류 메시지가 표시되고 다른 model.json 또는 manifest.json 파일을 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-169">If there are dependencies on the existing model.json or manifest.json file and the set of entities, you'll see an error message and can't select a different model.json or manifest.json file.</span></span> <span data-ttu-id="107a5-170">model.json 또는 manifest.json 파일을 변경하기 전에 이러한 종속성을 제거하거나 종속성 제거를 방지하기 위해 사용할 model.json 또는 manifest.json 파일로 새 데이터 원본를 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="107a5-170">Remove those dependencies before changing the model.json or manifest.json file or create a new data source with the model.json or manifest.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="107a5-171">선택적으로 추가 특성 또는 엔터티를 선택하여 데이터 프로파일링을 사용 설정하거나 이미 선택한 항목을 사용 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="107a5-171">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   


[!INCLUDE[footer-include](../includes/footer-banner.md)]