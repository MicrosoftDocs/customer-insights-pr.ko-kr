---
title: Adobe Campaign Standard로 Customer Insights 데이터 내보내기
description: Adobe Campaign Standard에서 대상 그룹 인사이트 세그먼트를 사용하는 방법을 알아보십시오.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 917ab9559416f3ee0ffd66e471e590e8da3faffc
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305394"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="4ac80-103">Adobe Campaign Standard(프리뷰)에서 Customer Insights 세그먼트 사용하기</span><span class="sxs-lookup"><span data-stu-id="4ac80-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="4ac80-104">Dynamics 365 Customer Insights의 대상 그룹 인사이트 사용자로서 관련 잠재 고객을 타겟팅하여 마케팅 캠페인의 효율성을 높이기 위해 세그먼트를 만들었을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="4ac80-105">Adobe 환경 플랫폼 및 Adobe Campaign Standard와 같은 애플리케이션에서 대상 그룹 인사이트의 세그먼트를 사용하려면 이 문서에 설명된 몇 가지 단계를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="이 문서에 설명된 단계의 프로세스 다이어그램입니다.":::

## <a name="prerequisites"></a><span data-ttu-id="4ac80-107">필요한 항목</span><span class="sxs-lookup"><span data-stu-id="4ac80-107">Prerequisites</span></span>

-   <span data-ttu-id="4ac80-108">Dynamics 365 Customer Insights 라이선스</span><span class="sxs-lookup"><span data-stu-id="4ac80-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="4ac80-109">Adobe Campaign Standard 라이선스</span><span class="sxs-lookup"><span data-stu-id="4ac80-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="4ac80-110">Azure Blob Storage 계정</span><span class="sxs-lookup"><span data-stu-id="4ac80-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="4ac80-111">캠페인 개요</span><span class="sxs-lookup"><span data-stu-id="4ac80-111">Campaign overview</span></span>

<span data-ttu-id="4ac80-112">Adobe 환경 플랫폼에서 대상 그룹 인사이트의 세그먼트를 사용하는 방법을 더 잘 이해하기 위해 가상의 샘플 캠페인을 살펴 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="4ac80-113">귀사가 미국 고객에게 월간 구독 기반 서비스를 제공한다고 가정합시다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="4ac80-114">다음 8일 이내에 구독을 갱신해야 하지만 아직 갱신하지 않은 고객을 식별하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="4ac80-115">이러한 고객을 유지하려면 Adobe Campaign Standard를 사용하여 이메일을 통해 프로모션 제안을 보내는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="4ac80-116">이 예에서는 프로모션 이메일 캠페인을 한 번 실행하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="4ac80-117">이 문서에서는 캠페인을 두 번 이상 실행하는 사용 사례를 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="4ac80-118">그러나 대상 그룹 인사이트 및 Adobe Campaign Standard는 반복 캠페인 시나리오에서도 작동하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="4ac80-119">목표 대상 그룹 식별</span><span class="sxs-lookup"><span data-stu-id="4ac80-119">Identify your target audience</span></span>

<span data-ttu-id="4ac80-120">이 시나리오에서는 고객의 이메일 주소가 대상 그룹 인사이트에서 사용 가능하며 고객의 프로모션 선호도를 분석하여 세그먼트 구성원을 식별한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="4ac80-121">[대상 그룹 인사이트에서 정의한 세그먼트](segments.md)는 **ChurnProneCustomers** 로 불리며 이러한 고객에게 이메일 프로모션을 보낼 것을 계획합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ChurnProneCustomers 세그먼트가 만들어진 세그먼트 페이지의 스크린샷입니다.":::

<span data-ttu-id="4ac80-123">보내려는 제안 이메일에는 이름, 성, 및 고객의 구독 종료 날짜가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="4ac80-124">구독이 끝나기 전에 갱신하면 받을 수 있는 할인을 고객에게 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="4ac80-125">목표 대상 그룹 내보내기</span><span class="sxs-lookup"><span data-stu-id="4ac80-125">Export your target audience</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="4ac80-126">연결 구성</span><span class="sxs-lookup"><span data-stu-id="4ac80-126">Configure a connection</span></span>

<span data-ttu-id="4ac80-127">목표 대상 그룹이 식별되면 대상 그룹 인사이트에서 Azure Blob Storage 계정으로 내보내기를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-127">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="4ac80-128">대상 그룹 Insights에서 **관리자** > **연결** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-128">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="4ac80-129">**연결 추가** 를 선택하고 **Adobe Campaign** 을 선택하여 연결을 구성하거나 **Adobe Campaign** 타일에서 **설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-129">Select **Add connection** and choose **Adobe Campaign** to configure the connection or select **Set up** in the **Adobe Campaign** tile.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Adobe Campaign Standard에 대한 구성 타일입니다.":::

1. <span data-ttu-id="4ac80-131">**표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="4ac80-132">이름 및 연결 유형은 이 연결을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="4ac80-133">이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="4ac80-134">이 연결을 사용할 수 있는 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-134">Choose who can use this connection.</span></span> <span data-ttu-id="4ac80-135">아무 조치도 취하지 않으면 기본값은 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="4ac80-136">자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ac80-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="4ac80-137">세그먼트를 내보낼 Azure Blob Storage 계정의 **계정 이름**, **계정 키** 및 **컨테이너** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-137">Enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="스토리지 계정 구성의 스크린샷입니다."::: 

   - <span data-ttu-id="4ac80-139">Azure Blob Storage 계정 이름 및 계정 키를 찾는 방법에 대한 자세한 내용은 [Azure Portal에서 저장소 계정 설정 관리](/azure/storage/common/storage-account-manage)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4ac80-139">To learn more about how to find the Azure Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="4ac80-140">컨테이너를 만드는 방법을 배우려면 [컨테이너 만들기](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ac80-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="4ac80-141">연결을 완료하려면 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-141">Select **Save** to complete the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="4ac80-142">내보내기 구성</span><span class="sxs-lookup"><span data-stu-id="4ac80-142">Configure an export</span></span>

<span data-ttu-id="4ac80-143">이 유형의 연결에 대한 액세스 권한이 있는 경우 이 내보내기를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="4ac80-144">자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ac80-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="4ac80-145">**데이터** > **내보내기** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="4ac80-146">**내보내기 추가** 를 선택하여 새 내보내기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="4ac80-147">**내보내기 연결** 필드의 Adobe Campaign 섹션에서 연결을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-147">In the **Connection for export** field, choose a connection from the Adobe Campaign section.</span></span> <span data-ttu-id="4ac80-148">이 섹션 이름이 표시되지 않으면 이 유형의 연결을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="4ac80-149">내보낼 세그먼트를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="4ac80-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="4ac80-150">이 예에서는 **ChurnProneCustomers** 입니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="ChurnProneCustomers 세그먼트가 선택된 세그먼트 선택 사용자 인터페이스의 스크린샷입니다.":::

1. <span data-ttu-id="4ac80-152">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-152">Select **Next**.</span></span>

1. <span data-ttu-id="4ac80-153">이제 우리는 대상 그룹 인사이트 세그먼트에서 **원본** 필드를 Adobe Campaign Standard 프로필 스키마의 **대상** 필드 이름으로 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-153">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Adobe Campaign Standard 커넥터에 대한 필드 매핑입니다.":::

   <span data-ttu-id="4ac80-155">더 많은 특성을 추가하려면 **특성 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-155">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="4ac80-156">대상 이름은 원본 필드 이름과 다를 수 있으므로 두 시스템에서 필드 이름이 동일하지 않은 경우 대상 그룹 인사이트의 세그먼트 출력을 Adobe Campaign Standard에 계속 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-156">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4ac80-157">이메일 주소는 ID 필드로 사용되지만 대상 그룹 인사이트 고객 프로필의 다른 식별자를 사용하여 데이터를 Adobe Campaign Standard에 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-157">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="4ac80-158">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-158">Select **Save**.</span></span>

<span data-ttu-id="4ac80-159">내보내기 대상을 저장한 후 **데이터** > **내보내기** 에서 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-159">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="4ac80-160">이제 [필요에 따라 세그먼트 내보내기](export-destinations.md#run-exports-on-demand)를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-160">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="4ac80-161">내보내기는 [예약된 새로 고침](system.md)마다 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-161">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4ac80-162">내보낸 세그먼트의 레코드 수가 Adobe Campaign Standard 라이선스의 허용 한도 내에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-162">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="4ac80-163">내보낸 데이터는 위에서 구성한 Azure Blob Storage 컨테이너에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-163">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="4ac80-164">컨테이너에 다음 폴더 경로가 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-164">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="4ac80-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="4ac80-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="4ac80-166">예: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="4ac80-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="4ac80-167">Adobe Campaign Standard 구성</span><span class="sxs-lookup"><span data-stu-id="4ac80-167">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="4ac80-168">대상 그룹 인사이트의 세그먼트를 내보내면 이전 단계에서 내보내기 대상을 정의할 때 선택한 열이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-168">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="4ac80-169">이 데이터를 사용하여 [Adobe Campaign Standard에서 프로필을 만듭니다](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="4ac80-169">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="4ac80-170">Adobe Campaign Standard에서 세그먼트를 사용하려면 두 개의 추가 필드를 포함하도록 Adobe Campaign Standard의 프로필 스키마를 확장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-170">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="4ac80-171">Adobe Campaign Standard의 새로운 필드로 [프로필 리소스 확장](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) 방법을 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="4ac80-171">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="4ac80-172">이 예에서 이러한 필드는 *세그먼트 이름 및 세그먼트 날짜(선택 사항)* 입니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-172">In our example, these fields are *Segment Name and Segment Date (optional)*.</span></span>

<span data-ttu-id="4ac80-173">이 필드를 사용하여 이 캠페인을 대상으로 하는 Adobe Campaign Standard의 프로필을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-173">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="4ac80-174">Adobe Campaign Standard에 가져올 레코드 외에 다른 레코드가 없는 경우 이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-174">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="4ac80-175">Adobe Campaign Standard로 데이터 가져오기</span><span class="sxs-lookup"><span data-stu-id="4ac80-175">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="4ac80-176">이제 모든 것이 준비되었으므로 준비된 대상 그룹 데이터를 대상 그룹 인사이트에서 Adobe Campaign Standard로 가져와 프로필을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-176">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="4ac80-177">워크플로를 사용해 [Adobe Campaign Standard에서 프로필을 가져오는 방법](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences)을 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="4ac80-177">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="4ac80-178">아래 이미지의 가져오기 워크플로는 8시간마다 실행되고 내보낸 대상 그룹 인사이트 세그먼트(Azure Blob Storage의 .csv 파일)를 찾도록 구성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-178">The import workflow in the image below has been configured to run every eight hours and look for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="4ac80-179">워크플로는 지정된 열 순서로 .csv 파일 콘텐츠를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-179">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="4ac80-180">이 워크플로는 기본 오류 처리를 수행하고 Adobe Campaign Standard에서 데이터를 하이드레이션하기 전에 각 레코드에 이메일 주소가 있는지 확인하기 위해 구축되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-180">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="4ac80-181">또한 워크플로는 Adobe Campaign Standard 프로필 데이터로 업데이트하기 전에 파일 이름에서 세그먼트 이름을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-181">The workflow also extracts the segment name from the filename before upserting into Adobe Campaign Standard profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Adobe Campaign Standard 사용자 인터페이스의 가져오기 워크플로 스크린샷입니다.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="4ac80-183">Adobe Campaign Standard에서 대상 그룹 검색</span><span class="sxs-lookup"><span data-stu-id="4ac80-183">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="4ac80-184">데이터를 Adobe Campaign Standard로 가져 오면 [워크플로 만들기](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data)를 할 수 있으며 *세그먼트 이름* 과 *세그먼트 날짜* 를 기반으로 하여 고객을 [쿼리](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data)하여 샘플 캠페인에 대해 식별된 프로필을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-184">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="4ac80-185">Adobe Campaign Standard를 사용하여 이메일 작성 및 보내기</span><span class="sxs-lookup"><span data-stu-id="4ac80-185">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="4ac80-186">이메일 콘텐츠를 만든 다음 내 이메일을 [테스트 및 전송](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages)합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac80-186">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard의 갱신 제안이 포함된 샘플 이메일입니다.":::
