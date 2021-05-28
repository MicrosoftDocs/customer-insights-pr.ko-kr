---
title: 세그먼트 만들기 및 관리
description: 다양한 특성에 따라 그룹화할 고객 세그먼트를 만듭니다.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064945"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="37a60-103">세그먼트 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="37a60-103">Create and manage segments</span></span>

<span data-ttu-id="37a60-104">통합 고객 엔터티 및 관련 엔터티를 중심으로 복잡한 필터를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="37a60-105">처리 후 각 세그먼트는 내보내고 조치를 취할 수 있는 고객 레코드 집합을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="37a60-106">세그먼트는 **세그먼트** 페이지에서 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="37a60-107">다음 예는 분할 기능을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="37a60-108">지난 90일 동안 최소 $500의 상품을 주문 *하고* 에스컬레이션된 고객 서비스 요청에 참여한 고객을 위한 세그먼트를 정의했습니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="고객 세그먼트를 지정하는 두 그룹이 있는 세그먼트 작성 도구 UI의 스크린샷입니다.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="37a60-110">새 세그먼트 만들기</span><span class="sxs-lookup"><span data-stu-id="37a60-110">Create a new segment</span></span>

<span data-ttu-id="37a60-111">여러 가지 방법으로 새 세그먼트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="37a60-112">이 섹션에서는 *빈 세그먼트* 를 만드는 방법에 대해 처음부터 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="37a60-113">기존 엔터티를 기반으로 *빠른 세그먼트* 를 만들거나 기계 학습 모델을 사용하여 *제안된 세그먼트* 를 얻을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="37a60-114">추가 정보: [세그먼트 개요](segments.md).</span><span class="sxs-lookup"><span data-stu-id="37a60-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="37a60-115">세그먼트를 만드는 동안 초안을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="37a60-116">이는 비활성 세그먼트로 저장되며 유효한 구성으로 완료되면 활성화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="37a60-117">**세그먼트** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="37a60-118">**새로 만들기** > **빈 세그먼트** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="37a60-119">**새로운 세그먼트** 창에서 세그먼트 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="37a60-120">**동적 세그먼트** 는 정기 일정에 따라 [새로 고침](segments.md#refresh-segments)됩니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="37a60-121">**정적 세그먼트** 를 만들 때는 한 번 실행하십시오.</span><span class="sxs-lookup"><span data-stu-id="37a60-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="37a60-122">세그먼트에 **출력 엔터티 이름** 을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="37a60-123">선택적으로 세그먼트를 식별하는 데 도움이 되는 표시 이름 및 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="37a60-124">**다음** 을 선택하여 그룹을 정의하는 **세그먼트 빌더** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="37a60-125">그룹은 고객 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="37a60-126">분류하려는 속성이 포함된 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="37a60-127">분류 기준을 지정할 속성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="37a60-128">이 특성은 숫자, 문자열, 날짜 또는 부울의 네 가지 값 유형 중 하나를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="37a60-129">선택한 특성에 대한 연산자 및 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="37a60-130">![사용자 지정 그룹 필터](media/customer-group-numbers.png "고객 그룹 필터")</span><span class="sxs-lookup"><span data-stu-id="37a60-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="37a60-131">숫자</span><span class="sxs-lookup"><span data-stu-id="37a60-131">Number</span></span> |<span data-ttu-id="37a60-132">정의</span><span class="sxs-lookup"><span data-stu-id="37a60-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="37a60-133">1</span><span class="sxs-lookup"><span data-stu-id="37a60-133">1</span></span>     |<span data-ttu-id="37a60-134">Entity</span><span class="sxs-lookup"><span data-stu-id="37a60-134">Entity</span></span>          |
   |<span data-ttu-id="37a60-135">2</span><span class="sxs-lookup"><span data-stu-id="37a60-135">2</span></span>     |<span data-ttu-id="37a60-136">특성</span><span class="sxs-lookup"><span data-stu-id="37a60-136">Attribute</span></span>          |
   |<span data-ttu-id="37a60-137">3</span><span class="sxs-lookup"><span data-stu-id="37a60-137">3</span></span>    |<span data-ttu-id="37a60-138">연산자</span><span class="sxs-lookup"><span data-stu-id="37a60-138">Operator</span></span>         |
   |<span data-ttu-id="37a60-139">4</span><span class="sxs-lookup"><span data-stu-id="37a60-139">4</span></span>    |<span data-ttu-id="37a60-140">값</span><span class="sxs-lookup"><span data-stu-id="37a60-140">Value</span></span>         |

   1. <span data-ttu-id="37a60-141">그룹에 조건을 더 추가하려면 두 개의 논리 연산자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="37a60-142">**AND** 연산자: 두 조건을 모두 세분화 프로세스의 일부로 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="37a60-143">이 옵션은 여러 엔터티에서 조건을 정의할 때 가장 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="37a60-144">**OR** 연산자: 세그레이션 프로세스의 일부로 조건 중 하나를 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="37a60-145">이 옵션은 동일한 엔터티에 대해 여러 조건을 정의할 때 가장 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="37a60-146">![두 조건 중 하나를 충족해야 하는 OR 연산자](media/segmentation-either-condition.png "두 조건 중 하나를 충족해야 하는 OR 연산자")</span><span class="sxs-lookup"><span data-stu-id="37a60-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="37a60-147">현재 **OR** 연산자를 **AND** 연산자 아래에 중첩시킬 수는 있지만 다른 방법은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="37a60-148">각 그룹은 고객 집합과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-148">Each group matches set of customers.</span></span> <span data-ttu-id="37a60-149">비즈니스 사례에 필요한 고객을 포함하도록 그룹을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="37a60-150">**그룹 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="37a60-151">![고객 그룹 추가 그룹](media/customer-group-add-group.png "고객 그룹 추가 그룹")</span><span class="sxs-lookup"><span data-stu-id="37a60-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="37a60-152">다음 집합 연산자 중 하나를 선택합니다: **결합**, **교차** 또는 **제외**.</span><span class="sxs-lookup"><span data-stu-id="37a60-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="37a60-153">![고객 그룹 추가 결합](media/customer-group-union.png "고객 그룹 추가 결합")</span><span class="sxs-lookup"><span data-stu-id="37a60-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="37a60-154">**결합** 은 두 그룹을 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="37a60-155">**교차** 는 두 그룹을 겹칩니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="37a60-156">두 그룹에 *공통된* 데이터만 통합 그룹에 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="37a60-157">**제외** 는 두 그룹을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-157">**Except** combines the two groups.</span></span> <span data-ttu-id="37a60-158">그룹 B의 데이터와 *공통되지 않은* 그룹 A의 데이터만 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="37a60-159">엔터티가 [관계](relationships.md)를 통해 통합 고객 엔터티에 연결된 경우 유효한 세그먼트를 작성하기 위해 관계 경로를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="37a60-160">드롭다운에서 **고객: CustomerInsights** 엔터티를 선택할 수 있을 때까지 관계 경로에서 엔터티를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="37a60-161">그런 다음 각 단계에 대해 **모든 레코드** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="37a60-162">![세그먼트 작성 중 관계 경로](media/segments-multiple-relationships.png "세그먼트 작성 중 관계 경로")</span><span class="sxs-lookup"><span data-stu-id="37a60-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="37a60-163">기본적으로 세그먼트는 정의된 필터와 일치하는 고객 프로필의 모든 속성을 포함하는 출력 엔터티를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="37a60-164">세그먼트가 *고객* 엔티티가 아닌 다른 엔터티를 기반으로 하는 경우 이러한 엔티티의 더 많은 속성을 출력 엔티티에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="37a60-165">**프로젝트 특성** 을 선택하여 출력 엔티티에 추가될 속성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="37a60-166">예: 세그먼트는 *고객* 엔터티와 관련된 고객 활동 데이터를 포함하는 엔티티를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="37a60-167">이 세그먼트는 지난 60일 동안 지원 센터에 전화한 모든 고객을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="37a60-168">출력 엔터티에서 일치하는 모든 고객 레코드에 통화 기간과 통화 수를 추가하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="37a60-169">이 정보는 자주 전화를 거는 고객에게 온라인 도움말 문서 및 FAQ에 대한 유용한 링크가 포함된 이메일을 보내는 데 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="37a60-170">프로젝트된 특성은 고객 엔터티와 일대다 관계가 있는 엔터티에 대해서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="37a60-171">예를 들어 한 고객이 여러 구독을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="37a60-172">작성중인 모든 세그먼트 쿼리 그룹에 사용되는 엔터티의 특성만 프로젝트 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="37a60-173">프로젝트된 특성은 집합 연산자를 사용할 때 고려됩니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="37a60-174">**저장** 을 선택하여 세그먼트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="37a60-175">모든 요구 사항이 검증되면 세그먼트가 저장되고 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="37a60-176">그렇지 않으면 초안으로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="37a60-177">**세그먼트로 돌아가기** 를 선택하여 **세그먼트** 페이지로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="37a60-178">퀵 세그먼트</span><span class="sxs-lookup"><span data-stu-id="37a60-178">Quick segments</span></span>

<span data-ttu-id="37a60-179">빠른 세그먼트를 사용하면 단일 운영자로 간단한 세그먼트를 빠르게 구축하여 더 빠른 인사이트를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="37a60-180">**세그먼트** 페이지에서 **새로 만들기** > **다음에서 만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="37a60-181">**프로필** 옵션을 선택하여 *통합 고객* 엔터티를 기반으로 하는 세그먼트를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="37a60-182">**측정값** 옵션을 선택하여 이전에 만든 측정값을 중심으로 세그먼트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="37a60-183">**예측** 또는 **사용자 지정 모델** 기능을 사용하여 생성한 출력 엔터티 중 하나를 중심으로 세그먼트를 작성하려면 **인텔리전스** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="37a60-184">**새로운 빠른 세그먼트** 대화 상자에서 **필드** 드롭다운에서 특성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="37a60-185">이 시스템은 고객의 더 나은 세그먼트를 만드는 데 도움이 되는 몇 가지 추가 통찰력을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="37a60-186">범주별 필드의 경우 10개의 최상위 고객 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="37a60-187">**값** 을 선택하고 **검토** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="37a60-188">숫자 특성의 경우 시스템은 각 고객의 백분위수에 속하는 속성 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="37a60-189">**연산자** 와 **값** 을 선택한 다음 **검토** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="37a60-190">시스템은 **예상 세그먼트 크기** 를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="37a60-191">정의한 세그먼트를 생성할지 또는 먼저 다시 방문하여 다른 세그먼트 크기를 얻을지 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="37a60-192">![빠른 세그먼트의 이름 및 평가](media/quick-segment-name.png "빠른 세그먼트의 이름 및 평가")</span><span class="sxs-lookup"><span data-stu-id="37a60-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="37a60-193">세그먼트의 **이름** 을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="37a60-194">또는 **표시 이름** 을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="37a60-195">**저장** 을 선택하여 세그먼트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="37a60-196">세그먼트 처리가 완료되면 만든 다른 세그먼트와 마찬가지로 세그먼트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="37a60-197">다음 단계</span><span class="sxs-lookup"><span data-stu-id="37a60-197">Next steps</span></span>

<span data-ttu-id="37a60-198">[세그먼트를 내보내고](export-destinations.md) [고객 카드](customer-card-add-in.md) 및 [커넥터](export-power-bi.md)를 탐색하여 고객 수준에 대한 통찰력을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a60-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
