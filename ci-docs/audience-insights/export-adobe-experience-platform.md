---
title: Adobe 환경 플랫폼으로 Customer Insights 데이터 내보내기
description: Adobe 환경 플랫폼에서 대상 그룹 인사이트 세그먼트를 사용하는 방법을 알아보십시오.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 884f4d30f354bed29909d57be84dce4c8e46965a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760109"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="974b8-103">Adobe 환경 플랫폼(프리뷰)에서 Customer Insights 세그먼트 사용하기</span><span class="sxs-lookup"><span data-stu-id="974b8-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="974b8-104">Dynamics 365 Customer Insights에 대한 대상 그룹 인사이트의 사용자로서 관련 대상 그룹을 타기팅하여 마케팅 캠페인의 효율성을 높이기 위해 세그먼트를 생성했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="974b8-105">Adobe 환경 플랫폼 및 Adobe Campaign Standard와 같은 애플리케이션에서 대상 그룹 인사이트의 세그먼트를 사용하려면 이 문서에 설명된 몇 가지 단계를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="이 문서에 설명된 단계의 프로세스 다이어그램입니다.":::

## <a name="prerequisites"></a><span data-ttu-id="974b8-107">필요한 항목</span><span class="sxs-lookup"><span data-stu-id="974b8-107">Prerequisites</span></span>

-   <span data-ttu-id="974b8-108">Dynamics 365 Customer Insights 라이선스</span><span class="sxs-lookup"><span data-stu-id="974b8-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="974b8-109">Adobe 환경 플랫폼 라이선스</span><span class="sxs-lookup"><span data-stu-id="974b8-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="974b8-110">Adobe Campaign Standard 라이선스</span><span class="sxs-lookup"><span data-stu-id="974b8-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="974b8-111">Azure Blob Storage 계정</span><span class="sxs-lookup"><span data-stu-id="974b8-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="974b8-112">캠페인 개요</span><span class="sxs-lookup"><span data-stu-id="974b8-112">Campaign Overview</span></span>

<span data-ttu-id="974b8-113">Adobe 환경 플랫폼에서 대상 그룹 인사이트의 세그먼트를 사용하는 방법을 더 잘 이해하기 위해 가상의 샘플 캠페인을 살펴 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="974b8-114">귀사가 미국 고객에게 월간 구독 기반 서비스를 제공한다고 가정합시다.</span><span class="sxs-lookup"><span data-stu-id="974b8-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="974b8-115">다음 8일 이내에 구독을 갱신해야 하지만 아직 갱신하지 않은 고객을 식별하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="974b8-116">이러한 고객을 유지하려면 Adobe 환경 플랫폼을 사용하여 이메일을 통해 프로모션 제안을 보내는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="974b8-117">이 예에서는 프로모션 이메일 캠페인을 한 번 실행하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="974b8-118">이 문서에서는 캠페인을 두 번 이상 실행하는 사용 사례를 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="974b8-119">목표 대상 그룹 식별</span><span class="sxs-lookup"><span data-stu-id="974b8-119">Identify your target audience</span></span>

<span data-ttu-id="974b8-120">이 시나리오에서는 고객의 이메일 주소가 대상 그룹 인사이트에서 사용 가능하며 고객의 프로모션 선호도를 분석하여 세그먼트 구성원을 식별한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="974b8-121">[대상 그룹 인사이트에서 정의한 세그먼트](segments.md)는 **ChurnProneCustomers** 로 불리며 이러한 고객에게 이메일 프로모션을 보낼 것을 계획합니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ChurnProneCustomers 세그먼트가 만들어진 세그먼트 페이지의 스크린샷입니다.":::

<span data-ttu-id="974b8-123">보내려는 제안 이메일에는 이름, 성, 및 고객의 구독 종료 날짜가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="974b8-124">구독이 끝나기 전에 갱신하면 받을 수 있는 할인을 고객에게 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="974b8-125">목표 대상 그룹 내보내기</span><span class="sxs-lookup"><span data-stu-id="974b8-125">Export your target audience</span></span>

<span data-ttu-id="974b8-126">목표 대상 그룹이 식별되면 대상 그룹 인사이트에서 Azure Blob Storage 계정으로 내보내기를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="974b8-127">연결 구성</span><span class="sxs-lookup"><span data-stu-id="974b8-127">Configure a connection</span></span>

1. <span data-ttu-id="974b8-128">**관리자** > **연결** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="974b8-129">**연결 추가** 를 선택하고 **Azure Blob Storage** 또는 **Azure Blob Storage** 타일에서 **설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile:</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Azure Blob Storage에 대한 구성 타일입니다."::: <span data-ttu-id="974b8-131">이렇게 연결을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-131">to configure the connection.</span></span>

1. <span data-ttu-id="974b8-132">**표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-132">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="974b8-133">이름 및 연결 유형은 이 연결을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-133">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="974b8-134">이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-134">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="974b8-135">이 연결을 사용할 수 있는 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-135">Choose who can use this connection.</span></span> <span data-ttu-id="974b8-136">아무 조치도 취하지 않으면 기본값은 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-136">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="974b8-137">자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="974b8-137">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="974b8-138">세그먼트를 내보낼 Blob Storage 계정의 **계정 이름**, **계정 키** 및 **컨테이너** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-138">Enter **Account name**, **Account key**, and **Container** for your Blob storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="스토리지 계정 구성의 스크린샷입니다."::: 
   
    - <span data-ttu-id="974b8-140">Blob Storage 계정 이름 및 계정 키를 찾는 방법에 대한 자세한 내용은 [Azure Portal에서 스토리지 계정 설정 관리](/azure/storage/common/storage-account-manage)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="974b8-140">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="974b8-141">컨테이너를 만드는 방법을 배우려면 [컨테이너 만들기](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="974b8-141">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="974b8-142">연결을 완료하려면 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-142">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="974b8-143">내보내기 구성</span><span class="sxs-lookup"><span data-stu-id="974b8-143">Configure an export</span></span>

<span data-ttu-id="974b8-144">이 유형의 연결에 대한 액세스 권한이 있는 경우 이 내보내기를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-144">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="974b8-145">자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="974b8-145">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="974b8-146">**데이터** > **내보내기** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="974b8-147">**내보내기 추가** 를 선택하여 새 내보내기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-147">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="974b8-148">**내보내기 연결** 필드의 Azure Blob Storage 섹션에서 연결을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-148">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="974b8-149">이 섹션 이름이 표시되지 않으면 사용 가능한 이 유형의 연결이 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-149">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="974b8-150">내보낼 세그먼트를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="974b8-150">Choose the segment that you want to export.</span></span> <span data-ttu-id="974b8-151">이 예에서는 **ChurnProneCustomers** 입니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-151">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="ChurnProneCustomers 세그먼트가 선택된 세그먼트 선택 사용자 인터페이스의 스크린샷입니다.":::

1. <span data-ttu-id="974b8-153">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-153">Select **Save**.</span></span>

<span data-ttu-id="974b8-154">내보내기 대상을 저장한 후 **데이터** > **내보내기** 에서 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-154">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="974b8-155">이제 [필요에 따라 세그먼트 내보내기](export-destinations.md#run-exports-on-demand)를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-155">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="974b8-156">내보내기는 [예약된 새로 고침](system.md)마다 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-156">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="974b8-157">내보낸 세그먼트의 레코드 수가 Adobe Campaign Standard 라이선스의 허용 한도 내에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-157">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="974b8-158">내보낸 데이터는 위에서 구성한 Azure Blob 저장소 컨테이너에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-158">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="974b8-159">컨테이너에 다음 폴더 경로가 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-159">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="974b8-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="974b8-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="974b8-161">예: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="974b8-161">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="974b8-162">내보낸 엔터티의 *model.json* 은 *%ExportDestinationName%* 수준에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-162">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="974b8-163">예: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="974b8-163">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="974b8-164">Adobe 환경 플랫폼에서 환경 데이터 모델(XDM) 정의</span><span class="sxs-lookup"><span data-stu-id="974b8-164">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="974b8-165">대상 그룹 인사이트에서 내보낸 데이터를 Adobe 환경 플랫폼 내에서 사용하려면 먼저 경험 데이터 모델 스키마를 정의하고 [실시간 고객 프로필에 대한 데이터를 구성](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-165">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="974b8-166">[XDM의 정의](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html)를 알아보고 [스키마 구성의 기초](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema)을 파악하십시오.</span><span class="sxs-lookup"><span data-stu-id="974b8-166">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="974b8-167">Adobe 환경 플랫폼으로 데이터 가져오기</span><span class="sxs-lookup"><span data-stu-id="974b8-167">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="974b8-168">이제 모든 것이 준비되었으므로 준비된 대상 그룹 데이터를 대상 그룹 인사이트에서 Adobe 환경 플랫폼으로 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-168">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="974b8-169">먼저, [Azure Blob Storage 원본 연결을 만듭니다](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="974b8-169">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="974b8-170">원본 연결을 정의한 후 클라우드 저장소 일괄 처리 연결에 대한 [데이터 흐름 구성](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials)을 구성하여 대상 그룹 인사이트에서 세그먼트 출력을 Adobe 환경 플랫폼으로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-170">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="974b8-171">Adobe Campaign Standard에서 대상 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="974b8-171">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="974b8-172">이 캠페인에 대한 이메일을 보내기 위해 Adobe Campaign Standard를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-172">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="974b8-173">데이터를 Adobe 환경 플랫폼으로 가져온 후 Adobe 환경 플랫폼의 데이터를 사용하여 Adobe Campaign Standard에서 [대상 그룹을 생성](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-173">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="974b8-174">Adobe Campaign Standard에서 [세그먼트 작성기를 사용하는 방법](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment)을 알아보고 Adobe 환경 플랫폼의 데이터를 기반으로 대상 그룹을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-174">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="974b8-175">Adobe Campaign Standard를 사용하여 이메일 작성 및 보내기</span><span class="sxs-lookup"><span data-stu-id="974b8-175">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="974b8-176">이메일 콘텐츠를 만든 다음 내 이메일을 [테스트 및 전송](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages)합니다.</span><span class="sxs-lookup"><span data-stu-id="974b8-176">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard의 갱신 제안이 포함된 샘플 이메일입니다.":::
