---
title: 활동을 기반으로 제안된 세그먼트.
description: 기계 학습을 통해 고객 활동을 기반으로 새롭고 흥미로운 세그먼트를 찾을 수 있습니다.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034091"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="1ca2b-103">활동 데이터를 기반으로 제안된 세그먼트(프리뷰)</span><span class="sxs-lookup"><span data-stu-id="1ca2b-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="1ca2b-104">Customer Insights에 수집된 고객 활동 데이터를 기반으로 고객의 흥미로운 세그먼트를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="1ca2b-105">활동 데이터의 예로는 트랜잭션, 지원 통화 기간, 구매 또는 반품이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="1ca2b-106">세그먼트를 제안하기 위해 활동 데이터에서 최신성, 빈도 및 금전적 가치(또는 기간)를 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="1ca2b-107">또는 [측정값을 개선하거나 속성에 영향을 미치는 요소를 더 잘 이해하기 위해 제안된 세그먼트](suggested-segments.md)를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="활동 기반 및 특성 기반 세그먼트에 대한 세그먼트 제안을 표시하는 제안된 세그먼트 탭.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="1ca2b-109">활동별로 고객 분류</span><span class="sxs-lookup"><span data-stu-id="1ca2b-109">Categorize customers by activity</span></span>

<span data-ttu-id="1ca2b-110">Customer Insights에서 제공하는 [활동 데이터](activities.md)를 사용하여 고객 그룹을 나타내는 제안을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="1ca2b-111">가장 활동적인 고객</span><span class="sxs-lookup"><span data-stu-id="1ca2b-111">most active customers</span></span> 
- <span data-ttu-id="1ca2b-112">가장 많이 구매한 고객</span><span class="sxs-lookup"><span data-stu-id="1ca2b-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="1ca2b-113">가장 많은 수익을 발생시킨 고객</span><span class="sxs-lookup"><span data-stu-id="1ca2b-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="1ca2b-114">최근 활동하지 않은 고객</span><span class="sxs-lookup"><span data-stu-id="1ca2b-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="1ca2b-115">귀사와 자주 상호 작용하는 고객</span><span class="sxs-lookup"><span data-stu-id="1ca2b-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="1ca2b-116">소매업의 경우 어떤 고객이 가장 많은 수익을 발생시키는지 확인하고 쿠폰으로 보상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="1ca2b-117">또는 비정기적인 고객을 식별하고 보상 프로그램에 참여하도록 제안하여 고객이 귀하의 비즈니스를 더 자주 방문하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="1ca2b-118">공공 의료 서비스를 제공하는 의료 사업에 종사하고 있다면 귀하의 목표는 개별 환자의 비용을 최소화하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="1ca2b-119">그렇게 하는 방법은 가능한 적은 방문으로 최상의 치료를 제공함으로써 반복 방문을 줄이는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="1ca2b-120">이 경우 목표는 방문 빈도를 낮게 유지하고 환자의 정기 비용을 최소화하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="1ca2b-121">또는 진료 예약을 자주하고 정기 비용이 높은 환자 세그먼트를 식별하고 이러한 사례를 분석하여 개인의 치료를 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="1ca2b-122">필수 데이터</span><span class="sxs-lookup"><span data-stu-id="1ca2b-122">Required data</span></span>

<span data-ttu-id="1ca2b-123">선택한 입력 데이터를 기반으로 제안이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="1ca2b-124">고객 프로필: 특정 세그먼트의 모든 고객 또는 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="1ca2b-125">기간: 지난 달, 작년 또는 사용자 지정 시간 프레임.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="1ca2b-126">활동 유형: 구매, 소매 거래, 온라인 거래, 고객 지원 사례, 구독 등.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="1ca2b-127">활동 데이터가 포함된 Customer Insights의 엔터티: UnifiedActivity 엔터티 또는 특정 활동에 대한 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="1ca2b-128">포함할 차원: 비즈니스 요구 사항에 따라 최신성, 빈도 또는 금전적 차원.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="1ca2b-129">제안된 세그먼트 생성</span><span class="sxs-lookup"><span data-stu-id="1ca2b-129">Generate suggested segments</span></span>

1. <span data-ttu-id="1ca2b-130">**세그먼트** 로 이동</span><span class="sxs-lookup"><span data-stu-id="1ca2b-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="1ca2b-131">**제안(미리 보기)** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="1ca2b-132">**새로운 제안 찾기** 를 선택하고 **고객 행동 확인 또는 예상** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="1ca2b-133">**시작** 을 선택하여 가이드 경험을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="활동을 기반으로 제안된 세그먼트에 대한 구성 마법사의 첫 번째 단계입니다.":::

1. <span data-ttu-id="1ca2b-135">필요한 입력 데이터를 제공하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="1ca2b-136">고객 선택: 모든 고객 또는 특정 세그먼트를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="1ca2b-137">활동 선택: 활동 유형과 활동을 설명하는 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="1ca2b-138">기본 설정: 고려할 기간, 제안 요인을 설정하고 속성을 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="1ca2b-139">입력 내용을 검토하고 **실행** 을 ​​선택하여 모델을 실행하고 제안을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="1ca2b-140">고객 프로필 수와 선택한 활동에 따라 완료하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="1ca2b-141">제안을 생성한 후 가장 관심이 있는 차원 또는 값으로 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="1ca2b-142">제안된 세그먼트의 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="1ca2b-142">View details of a suggested segment</span></span>

<span data-ttu-id="1ca2b-143">제안이 생성되면 **활동 기반 제안** 섹션의 **세그먼트** > **제안(미리 보기)** 에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="제안된 세그먼트의 세부 데이터를 표시하는 확장된 측면 창입니다.":::

<span data-ttu-id="1ca2b-145">해당 세그먼트의 세부 정보를 보려면 제안된 세그먼트에서 **제안 보기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="1ca2b-146">측면 창은 대상 그룹과 비교하여 각 차원의 범위와 같은 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="1ca2b-147">또한 세그먼트의 잠재적 회원 수와 총 고객의 해당 비율을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="1ca2b-148">제안을 세그먼트로 유지하려면 **세그먼트 만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="1ca2b-149">제안을 세그먼트로 저장</span><span class="sxs-lookup"><span data-stu-id="1ca2b-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="1ca2b-150">**세그먼트** > **제안(미리 보기)** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="1ca2b-151">저장할 세그먼트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="1ca2b-152">측면 창에서 **세그먼트 만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="1ca2b-153">세그먼트를 저장하면 **모든 세그먼트** 탭의 세그먼트 목록에 표시됩니다. 이제 [다른 세그먼트처럼 새로 고침하거나 삭제](segments.md) 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="1ca2b-154">세그먼트 세부 정보는 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-154">You can't edit the segment details.</span></span> <span data-ttu-id="1ca2b-155">그러나 제안에 대한 입력 기준을 변경하고 다른 제안을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="1ca2b-156">제안 모음 새로 고침 또는 편집</span><span class="sxs-lookup"><span data-stu-id="1ca2b-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="1ca2b-157">**세그먼트** > **제안(미리 보기)** 로 이동하여 **활동 기반 제안** 섹션에서 세그먼트를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="1ca2b-158">**제안 새로 고침** 을 선택하여 구성된 특성을 유지하면서 제안을 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="1ca2b-159">또는 **제안 편집** 을 선택하여 구성된 특성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="1ca2b-160">시스템은 프로세스를 다시 실행하고 최신 데이터를 기반으로 세그먼트 제안을 생성하여 현재 제안을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca2b-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
