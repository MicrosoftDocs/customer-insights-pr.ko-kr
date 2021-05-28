---
title: 데이터 통합 시 엔터티 일치
description: 엔터티를 일치시켜 통합 고객 프로필을 만듭니다.
ms.date: 02/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2155042d86cda0cffee1588760a06d6c7eb7077e
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085630"
---
# <a name="match-entities"></a><span data-ttu-id="d66d2-103">엔터티 매칭</span><span class="sxs-lookup"><span data-stu-id="d66d2-103">Match entities</span></span>

<span data-ttu-id="d66d2-104">일치 단계에서는 데이터 집합을 통합된 고객 프로필 데이터 집합으로 결합하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-104">The match phase specifies how to combine your datasets into a unified customer profile dataset.</span></span> <span data-ttu-id="d66d2-105">데이터 통합 프로세스에서 [지도 단계](map-entities.md)를 완료한 후 엔티티를 일치시킬 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-105">After completing the [map step](map-entities.md) in the data unification process, you're ready to match your entities.</span></span> <span data-ttu-id="d66d2-106">일치 단계에는 매핑된 엔터티가 두 개 이상 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-106">The match phase requires at least two mapped entities.</span></span>

<span data-ttu-id="d66d2-107">일치 페이지는 다음 세 섹션으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-107">The match page consists of three sections:</span></span> 
- <span data-ttu-id="d66d2-108">일치하는 레코드 수를 요약하는 키 메트릭</span><span class="sxs-lookup"><span data-stu-id="d66d2-108">Key metrics that summarize the number of matched records</span></span>
- <span data-ttu-id="d66d2-109">엔티티 간 일치를 위한 일치 순서 및 규칙</span><span class="sxs-lookup"><span data-stu-id="d66d2-109">Match order and rules for cross-entity matching</span></span>
- <span data-ttu-id="d66d2-110">일치 엔터티의 중복 제거 규칙</span><span class="sxs-lookup"><span data-stu-id="d66d2-110">Rules for deduplication of match entities</span></span>

## <a name="specify-the-match-order"></a><span data-ttu-id="d66d2-111">일치 순서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-111">Specify the match order</span></span>

<span data-ttu-id="d66d2-112">**데이터** > **통합** > **일치** 로 이동하고 **순서 설정** 을 선택하여 일치 단계를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-112">Go to **Data** > **Unify** > **Match** and select **Set order** to start the match phase.</span></span>

<span data-ttu-id="d66d2-113">각 일치 항목은 둘 이상의 엔터티를 하나의 통합 엔터티로 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-113">Each match unifies two or more entities into a single, consolidated entity.</span></span> <span data-ttu-id="d66d2-114">동시에 고유한 고객 레코드를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-114">At the same time, it keeps the unique customer records.</span></span> <span data-ttu-id="d66d2-115">예를 들어, 기본 엔터티로 **eCommerce:eCommerceContacts** 를, 두 번째 엔터티로 **LoyaltyScheme:loyCustomers** 를 이렇게 두 개의 엔티티를 선택했습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-115">For example, we selected two entities: **eCommerce:eCommerceContacts** as the primary entity and **LoyaltyScheme:loyCustomers** as second entity.</span></span> <span data-ttu-id="d66d2-116">엔티티의 순서는 시스템이 레코드를 일치시키려고 시도하는 순서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-116">The order of the entities specifies in which order the system will try to match the records.</span></span>

:::image type="content" source="media/match-page.png" alt-text="데이터 통합 프로세스의 Unify 영역에 있는 일치 페이지의 스크린샷입니다.":::
  
<span data-ttu-id="d66d2-118">기본 엔터티 *eCommerce:eCommerceContacts* 는 다음 엔터티인 *LoyaltyScheme:loyCustomers* 와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-118">The primary entity *eCommerce:eCommerceContacts* is matched with the next entity *LoyaltyScheme:loyCustomers*.</span></span> <span data-ttu-id="d66d2-119">항목이 두 개 이상인 경우 첫 번째 일치 단계의 결과 데이터 집합은 다음 항목과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-119">The dataset that results from the first match step is matched with the following entity if you have more than two entities.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d66d2-120">기본 엔터티로 선택하는 엔터티는 통합 마스터 데이터 집합의 기초가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-120">The entity that you choose as your primary entity will serve as the basis for your unified profiles dataset.</span></span> <span data-ttu-id="d66d2-121">일치 단계 중에 선택된 추가 엔터티가 이 엔터티에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-121">Additional entities that are selected during the match phase will be added to this entity.</span></span> <span data-ttu-id="d66d2-122">이것은 통합 엔터티가 이 엔터티에 포함된 *모든* 데이터를 포함한다는 것을 의미하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-122">This doesn't mean that the unified entity will include *all* of the data included in this entity.</span></span>
>
> <span data-ttu-id="d66d2-123">엔터티의 계층 구조를 선택하는 데 도움이 되는 두 가지 고려 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-123">There are two considerations that can help you choose the hierarchy of your entities:</span></span>
>
> - <span data-ttu-id="d66d2-124">고객에 대한 가장 완전하고 신뢰할 수 있는 프로필 데이터를 기본 엔터티로 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="d66d2-124">Choose the entity with the most complete and reliable profile data about your customers as primary entity.</span></span>
> - <span data-ttu-id="d66d2-125">다른 엔티티(예: 이름, 전화번호 또는 이메일 주소)와 공통된 여러 속성이 있는 엔티티를 기본 엔티티로 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="d66d2-125">Choose the entity that hast several attributes in common with other entities (for example, name, phone number, or email address) as primary entity.</span></span>

<span data-ttu-id="d66d2-126">일치 순서를 지정하면 정의된 일치 쌍을 **데이터** > **Unify** > **일치** 의 **일치하는 레코드 세부 정보** 섹션에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-126">After specifying the match order, you'll see the defined match pairs in the **Matched records details** section on **Data** > **Unify** > **Match**.</span></span> <span data-ttu-id="d66d2-127">키 메트릭은 일치 프로세스가 완료될 때까지 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-127">The key metrics will be empty until the match process completes.</span></span>

## <a name="define-rules-for-match-pairs"></a><span data-ttu-id="d66d2-128">일치 쌍에 대한 규칙 정의</span><span class="sxs-lookup"><span data-stu-id="d66d2-128">Define rules for match pairs</span></span>

<span data-ttu-id="d66d2-129">일치 규칙은 특정 엔터티 쌍이 일치할 논리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-129">Match rules specify the logic by which a specific pair of entities will be matched.</span></span>

<span data-ttu-id="d66d2-130">엔터티 이름 옆에 있는 **규칙 필요** 경고는 일치 쌍에 대해 일치 규칙이 정의되지 않았음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-130">The **Needs rules** warning next to an entity name suggests that no match rule is defined for a match pair.</span></span> 

:::image type="content" source="media/match-rule-add.png" alt-text="강조 표시된 규칙을 추가할 수 있는 컨트롤이 있는 일치 레코드 세부 정보 섹션의 스크린샷입니다.":::

1. <span data-ttu-id="d66d2-132">**일치하는 레코드 세부 정보** 섹션의 엔터티 아래에서 **규칙 추가** 를 선택하여 일치 규칙을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-132">Select **Add rules** under an entity in the **Matched records details** section to define match rules.</span></span>

1. <span data-ttu-id="d66d2-133">**규칙 만들기** 창에서 규칙에 대한 조건을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-133">In the **Create rule** pane, configure the conditions for the rule.</span></span>

   :::image type="content" source="media/match-rule-conditions.png" alt-text="조건이 추가된 열린 일치 규칙의 스크린샷입니다.":::

   - <span data-ttu-id="d66d2-135">**엔티티/필드(첫 번째 행)**: 관련 엔터티 및 특성을 선택하여 고객에게 고유한 레코드 속성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-135">**Entity/Field (first row)**: Choose a related entity and an attribute to specify a record property that is likely unique to a customer.</span></span> <span data-ttu-id="d66d2-136">예를 들어 전화번호 또는 이메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-136">For example, a phone number or email address.</span></span> <span data-ttu-id="d66d2-137">활동 유형 특성으로 일치하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="d66d2-137">Avoid matching by activity-type attributes.</span></span> <span data-ttu-id="d66d2-138">예를 들어 구매 ID는 다른 레코드 종류에서 일치하는 항목을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-138">For example, a purchase ID will likely find no match in other record types.</span></span>

   - <span data-ttu-id="d66d2-139">**엔터티/필드(두 번째 행)**: 첫 번째 행에 지정된 엔티티의 특성과 관련된 특성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-139">**Entity/Field (second row)**: Choose an attribute that relates to the attribute of the entity specified in the first row.</span></span>

   - <span data-ttu-id="d66d2-140">**정규화**: 선택한 특성에 대해 다음 정규화 옵션에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-140">**Normalize**: Select from following normalization options for the selected attributes.</span></span> 
     - <span data-ttu-id="d66d2-141">공백: 모든 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-141">Whitespace: Removes all spaces.</span></span> <span data-ttu-id="d66d2-142">*Hello   World* 는 *HelloWorld* 가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-142">*Hello   World* becomes *HelloWorld*.</span></span>
     - <span data-ttu-id="d66d2-143">기호: 모든 기호와 특수 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-143">Symbols: Removes all symbols and special characters.</span></span> <span data-ttu-id="d66d2-144">*머리&어깨* 는 *머리어깨* 가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-144">*Head&Shoulder* becomes *HeadShoulder*.</span></span>
     - <span data-ttu-id="d66d2-145">텍스트를 소문자로: 모든 문자를 소문자로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-145">Text to lower case: Converts all character to lower case.</span></span> <span data-ttu-id="d66d2-146">*ALL CAPS and Title Case* 는 *all caps and title case* 가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-146">*ALL CAPS and Title Case* becomes *all caps and title case*.</span></span>
     - <span data-ttu-id="d66d2-147">유니코드를 ASCII로: 유니코드 표기법을 ASCII 문자로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-147">Unicode to ASCII: Converts unicode notation to ASCII characters.</span></span> <span data-ttu-id="d66d2-148">*/u00B2* 는 *2* 가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-148">*/u00B2* becomes *2*.</span></span>
     - <span data-ttu-id="d66d2-149">숫자: 로마 숫자와 같은 다른 숫자 체계를 아라비아 숫자로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-149">Numerals: Converts other numeral systems, such as Roman numerals, to Arabic numerals.</span></span> <span data-ttu-id="d66d2-150">*VIII* 는 *8* 이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-150">*VIII* becomes *8*.</span></span>
     - <span data-ttu-id="d66d2-151">의미 체계 형식: 이름, 제목, 전화번호, 주소 등을 표준화합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-151">Semantic types: Standardizes names, titles, phone numbers, addresses, etc.</span></span> 

   - <span data-ttu-id="d66d2-152">**정밀도**: 이 조건에 적용할 정밀도 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-152">**Precision**: Set the level of precision to apply for this condition.</span></span> 
     - <span data-ttu-id="d66d2-153">**기본**: *최저*, *보통*, *최고*, 및 *정확* 에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-153">**Basic**: Choose from *Low*, *Medium*, *High*, and *Exact*.</span></span> <span data-ttu-id="d66d2-154">100%와 일치하는 레코드만 일치하도록 **정확** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-154">Select **Exact** to only match records that that match 100 percent.</span></span> <span data-ttu-id="d66d2-155">100% 동일하지 않은 레코드와 일치하도록 다른 수준 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-155">Select one of the other levels to match records that aren't 100 percent identical.</span></span>
     - <span data-ttu-id="d66d2-156">**사용자 지정**: 레코드가 일치해야 하는 비율을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-156">**Custom**: Set a percentage that records need to match.</span></span> <span data-ttu-id="d66d2-157">시스템은이 임계값을 통과하는 일치 레코드만 일치시킵니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-157">The system will only match records passing this threshold.</span></span>

1. <span data-ttu-id="d66d2-158">규칙의 **명칭** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-158">Provide a **Name** for the rule.</span></span>

1. <span data-ttu-id="d66d2-159">[더 많은 조건을 추가](#add-conditions-to-a-rule)하거나 **완료** 를 선택하여 규칙을 마무리합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-159">[Add more conditions](#add-conditions-to-a-rule) or select **Done** to finalize the rule.</span></span>

1. <span data-ttu-id="d66d2-160">선택적으로 [더 많은 규칙을 추가](#add-rules-to-a-match-pair)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-160">Optionally, [add more rules](#add-rules-to-a-match-pair).</span></span>

1. <span data-ttu-id="d66d2-161">**저장** 을 선택하여 변경 내용을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-161">Select **Save** to apply your changes.</span></span>

### <a name="add-conditions-to-a-rule"></a><span data-ttu-id="d66d2-162">규칙에 조건 추가</span><span class="sxs-lookup"><span data-stu-id="d66d2-162">Add conditions to a rule</span></span>

<span data-ttu-id="d66d2-163">특성이 여러 조건을 충족하는 경우에만 엔터티를 일치시키려면 일치 규칙에 조건을 더 추가하십시오.</span><span class="sxs-lookup"><span data-stu-id="d66d2-163">To match entities only if attributes meet multiple conditions, add more conditions to a match rule.</span></span> <span data-ttu-id="d66d2-164">조건은 논리 AND 연산자로 연결되므로 모든 조건이 충족되는 경우에만 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-164">Conditions are connected with a logical AND operator and thus only executed if all conditions are met.</span></span>

1. <span data-ttu-id="d66d2-165">**데이터** > **Unify** > **일치** 로 이동하고 조건을 추가하려는 규칙에서 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-165">Go to **Data** > **Unify** > **Match** and select **Edit** on the rule you want to add conditions to.</span></span>

1. <span data-ttu-id="d66d2-166">**편집 규칙** 창에서 **조건 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-166">In the **Edit rule** pane, select **Add condition**.</span></span>

1. <span data-ttu-id="d66d2-167">**완료** 를 선택하여 규칙을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-167">Select **Done** so save the rule.</span></span>

### <a name="add-rules-to-a-match-pair"></a><span data-ttu-id="d66d2-168">일치 쌍에 규칙 추가</span><span class="sxs-lookup"><span data-stu-id="d66d2-168">Add rules to a match pair</span></span>

<span data-ttu-id="d66d2-169">일치 규칙은 조건 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-169">Match rules represent sets of conditions.</span></span> <span data-ttu-id="d66d2-170">여러 특성을 기반으로 하여 조건별로 엔터티를 일치시키려면 더 많은 규칙을 추가함</span><span class="sxs-lookup"><span data-stu-id="d66d2-170">To match entities by conditions based on multiple attributes, add more rules</span></span>

1.  <span data-ttu-id="d66d2-171">**데이터** > **Unify** > **일치** 로 이동하고 규칙을 추가하려는 엔터티에서 **규칙 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-171">Go to **Data** > **Unify** > **Match** and select **Add rule** on the entity you want to add rules to.</span></span>

2. <span data-ttu-id="d66d2-172">[일치 쌍에 대한 규칙 정의](#define-rules-for-match-pairs)의 단계를 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="d66d2-172">Follow the steps in [Define rules for match pairs](#define-rules-for-match-pairs).</span></span>

> [!NOTE]
> <span data-ttu-id="d66d2-173">규칙의 순서가 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-173">The order of rules matters.</span></span> <span data-ttu-id="d66d2-174">일치 알고리즘은 첫 번째 규칙을 기준으로 일치를 시도하고 첫 번째 규칙과 일치하는 항목이 없는 경우에만 두 번째 규칙으로 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-174">The matching algorithm tries to match on the basis of your first rule and continues to the second rule only if no matches were identified with the first rule.</span></span>

### <a name="change-the-entity-order-in-match-rules"></a><span data-ttu-id="d66d2-175">일치 규칙에서 엔터티 순서 변경</span><span class="sxs-lookup"><span data-stu-id="d66d2-175">Change the entity order in match rules</span></span>

<span data-ttu-id="d66d2-176">일치 규칙의 엔터티를 다시 정렬하여 처리 순서를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-176">You can reorder entities for match rules to change the order in which they are processed.</span></span> <span data-ttu-id="d66d2-177">변경된 순서로 인해 충돌하는 규칙은 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-177">Rules that are conflicting because of a changed order will be removed.</span></span> <span data-ttu-id="d66d2-178">업데이트된 구성으로 제거된 규칙은 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-178">You have to recreate removed rules with an updated configuration.</span></span>

1. <span data-ttu-id="d66d2-179">**데이터** > **통합** > **일치** 로 이동하여 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-179">Go to **Data** > **Unify** > **Match** and select **Edit**.</span></span>

1. <span data-ttu-id="d66d2-180">**규칙 편집** 창에서 **위/아래로 이동** 컨트롤을 선택하거나 엔터티를 끌어서 놓아 순서를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-180">In the **Edit rule** pane, select the **Move up/down** control or drag and drop entities to change the order.</span></span>

   :::image type="content" source="media/reorder-match-rules.png" alt-text="일치 단계에서 엔터티가 처리되는 순서를 변경하는 옵션입니다.":::

1. <span data-ttu-id="d66d2-182">**완료** 를 선택하여 규칙을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-182">Select **Done** so save the rule.</span></span>

## <a name="define-deduplication-on-a-match-entity"></a><span data-ttu-id="d66d2-183">일치 항목에서 중복 제거 정의</span><span class="sxs-lookup"><span data-stu-id="d66d2-183">Define deduplication on a match entity</span></span>

<span data-ttu-id="d66d2-184">[엔터티 간 일치 규칙](#define-rules-for-match-pairs) 이외에 중복 제거 규칙을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-184">In addition to [cross-entity match rules](#define-rules-for-match-pairs), you can also specify deduplications rules.</span></span> <span data-ttu-id="d66d2-185">*중복 제거* 은 레코드를 일치시킬 때 또 다른 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-185">*Deduplication* is another process when matching records.</span></span> <span data-ttu-id="d66d2-186">중복 레코드를 식별하고 이를 하나의 레코드로 병합합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-186">It identifies duplicate records and merges them into one record.</span></span> <span data-ttu-id="d66d2-187">원본 레코드는 대체 ID를 사용하여 병합된 레코드에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-187">Source records get linked to the merged record with alternate IDs.</span></span>

<span data-ttu-id="d66d2-188">중복 제거된 레코드는 엔터티 간 일치 프로세스에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-188">Deduplicated records will be used in the cross-entity matching process.</span></span> <span data-ttu-id="d66d2-189">중복 제거는 개별 엔터티에서 발생하며 일치 쌍에 사용되는 모든 엔터티를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-189">Deduplication happens on individual entities and can be configured every entity used in match pairs.</span></span>

<span data-ttu-id="d66d2-190">중복 제거 규칙을 지정하는 것은 필수가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-190">Specifying deduplication rules isn't mandatory.</span></span> <span data-ttu-id="d66d2-191">이러한 규칙이 구성되지 않은 경우 시스템 정의 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-191">If no such rules are configured, the system-defined rules are applied.</span></span> <span data-ttu-id="d66d2-192">성능 향상을 위해 엔터티 데이터를 엔터티 간 일치에 전달하기 전에 모든 레코드를 단일 레코드로 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-192">They combine all records into a single record before passing the entity data to cross-entity matching for enhanced performance.</span></span>

### <a name="add-deduplication-rules"></a><span data-ttu-id="d66d2-193">중복 제거 규칙 추가</span><span class="sxs-lookup"><span data-stu-id="d66d2-193">Add deduplication rules</span></span>

1. <span data-ttu-id="d66d2-194">**데이터** > **Unify** > **일치** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-194">Go to **Data** > **Unify** > **Match**.</span></span>

1. <span data-ttu-id="d66d2-195">**병합된 중복 항목** 섹션에서 **엔터티 설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-195">In the **Merged duplicates** section, select **Set entities**.</span></span> <span data-ttu-id="d66d2-196">중복 제거 규칙이 이미 만들어진 경우 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-196">In case deduplication rules are already created, select **Edit**.</span></span>

1. <span data-ttu-id="d66d2-197">**기본 설정 병합** 창에서 중복 제거를 적용할 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-197">In the **Merge preferences** pane, choose the entities you want to run deduplication on.</span></span>

1. <span data-ttu-id="d66d2-198">중복 레코드를 결합하는 방법을 지정하고 다음 세 가지 병합 옵션 중 하나를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="d66d2-198">Specify how to combine the duplicate records and choose one of three options:</span></span>
   - <span data-ttu-id="d66d2-199">**가장 많이 채워진**: 가장 많이 채워진 특성 필드가 있는 레코드를 승자 레코드로 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-199">**Most filled**: Identifies the record with most populated attribute fields as the winner record.</span></span> <span data-ttu-id="d66d2-200">기본 병합 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-200">It's the default merge option.</span></span>
   - <span data-ttu-id="d66d2-201">**가장 최근**: 최신순으로 승자 기록을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-201">**Most recent**: Identifies the winner record based on the most recency.</span></span> <span data-ttu-id="d66d2-202">최신 성을 정의하려면 날짜 또는 숫자 필드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-202">Requires a date or a numeric field to define the recency.</span></span>
   - <span data-ttu-id="d66d2-203">**가장 최근**: 최신순으로 승자 기록을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-203">**Least recent**: Identifies the winner record based on the least recency.</span></span> <span data-ttu-id="d66d2-204">최신 성을 정의하려면 날짜 또는 숫자 필드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-204">Requires a date or a numeric field to define the recency.</span></span>
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d66d2-205">![중복 제거 규칙 1단계](media/match-selfconflation.png "중복 제거 규칙 1단계")</span><span class="sxs-lookup"><span data-stu-id="d66d2-205">![Deduplication rules step 1](media/match-selfconflation.png "Deduplication rules step 1")</span></span>
 
1. <span data-ttu-id="d66d2-206">엔터티가 선택되고 기본 설정 병합이 설정되면 **규칙 추가** 를 선택하여 엔터티 수준에서 중복 제거 규칙을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-206">Once the entities are selected and their merge preference is set, select **Add rule** to define the deduplication rules at an entity level.</span></span>
   - <span data-ttu-id="d66d2-207">**필드 선택** 은 해당 엔터티에서 사용 가능한 모든 필드를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-207">**Select field** lists all the available fields from that entity.</span></span> <span data-ttu-id="d66d2-208">중복을 확인하려는 필드를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="d66d2-208">Choose the field you want to check for duplicates.</span></span> <span data-ttu-id="d66d2-209">모든 단일 고객에게 고유한 필드를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="d66d2-209">Choose fields that are likely unique for every single customer.</span></span> <span data-ttu-id="d66d2-210">예를 들어 이메일 주소 또는 이름, 도시 및 전화번호의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-210">For example, an email address, or the combination of name, city, and phone number.</span></span>
   - <span data-ttu-id="d66d2-211">정규화 및 정밀도 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-211">Specify the normalization and precision settings.</span></span>
   - <span data-ttu-id="d66d2-212">**조건 추가** 를 선택하여 조건을 더 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-212">Define more conditions by selecting **Add condition**.</span></span>
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d66d2-213">![중복 제거 규칙 2단계](media/match-selfconflation-rules.png "중복 제거 규칙 2단계")</span><span class="sxs-lookup"><span data-stu-id="d66d2-213">![Deduplication rules step 2](media/match-selfconflation-rules.png "Deduplication rules step 2")</span></span>

  <span data-ttu-id="d66d2-214">엔터티에 대해 여러 중복 제거 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-214">You can create multiple deduplication rules for an entity.</span></span> 

1. <span data-ttu-id="d66d2-215">이제 일치 프로세스를 실행하면 중복 제거 규칙에 정의된 조건에 따라 레코드가 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-215">Running the match process now groups the records based on the conditions defined in the deduplication rules.</span></span> <span data-ttu-id="d66d2-216">레코드를 그룹화한 후 병합 정책이 적용되어 승자 레코드를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-216">After grouping the records, the merge policy is applied to identify the winner record.</span></span>

1. <span data-ttu-id="d66d2-217">그런 다음 이 승자 레코드는 일치 품질을 개선하기 위해 비 승자 레코드(예: 대체 ID)와 함께 엔티티 간 일치에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-217">This winner record is then passed on to the cross-entity matching, along with the non-winner records (for example, alternate IDs) to improve the matching quality.</span></span>

1. <span data-ttu-id="d66d2-218">정의된 모든 사용자 지정 일치 규칙은 중복 제거 규칙을 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-218">Any custom match rules defined overwrite deduplication rules.</span></span> <span data-ttu-id="d66d2-219">중복 제거 규칙이 일치하는 레코드를 식별하고 사용자 지정 일치 규칙이 해당 레코드와 일치하지 않도록 설정된 경우 이 두 레코드는 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-219">If a deduplication rule identifies matching records, and a custom match rule is set to never match those records, then these two records won't be matched.</span></span>

1. <span data-ttu-id="d66d2-220">[일치 프로세스를 실행](#run-the-match-process)한 다음, 키 메트릭 타일에서 중복 제거 통계가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-220">After [running the match process](#run-the-match-process), you will see the deduplication stats in the key metrics tiles.</span></span>

### <a name="deduplication-output-as-an-entity"></a><span data-ttu-id="d66d2-221">엔터티로서 중복 제거 출력</span><span class="sxs-lookup"><span data-stu-id="d66d2-221">Deduplication output as an entity</span></span>

<span data-ttu-id="d66d2-222">중복 제거 프로세스는 일치 쌍의 모든 엔터티에 대해 새 엔터티를 만들어 중복 제거된 레코드를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-222">The deduplication process creates a new entity for every entity from the match pairs to identify the deduplicated records.</span></span> <span data-ttu-id="d66d2-223">이러한 엔터티는 **엔티티** 페이지의 **시스템** 섹션에서 **Deduplication_DataSource_Entity** 라는 이름으로 **ConflationMatchPairs:CustomerInsights** 와 함께 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-223">These entities can be found along with the **ConflationMatchPairs:CustomerInsights** in the **System** section in the **Entities** page, with the name **Deduplication_DataSource_Entity**.</span></span>

<span data-ttu-id="d66d2-224">중복 제거 출력 엔터티에는 다음 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-224">A deduplication output entity contains the following information:</span></span>
- <span data-ttu-id="d66d2-225">ID / 키</span><span class="sxs-lookup"><span data-stu-id="d66d2-225">IDs / Keys</span></span>
  - <span data-ttu-id="d66d2-226">기본 키 필드 및 대체 ID 필드.</span><span class="sxs-lookup"><span data-stu-id="d66d2-226">Primary key field and its alternate IDs field.</span></span> <span data-ttu-id="d66d2-227">대체 ID 필드는 레코드에 대해 식별된 모든 대체 ID로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-227">Alternate IDs field consists of all the alternate IDs identified for a record.</span></span>
  - <span data-ttu-id="d66d2-228">Deduplication_GroupId 필드는 지정된 중복 제거 필드를 기반으로 모든 유사한 레코드를 그룹화하는 엔터티 내에서 식별된 그룹 또는 클러스터를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-228">Deduplication_GroupId field shows the group or cluster identified within an entity that groups all the similar records based on the specified deduplication fields.</span></span> <span data-ttu-id="d66d2-229">이것은 시스템 처리 목적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-229">It's used for system processing purposes.</span></span> <span data-ttu-id="d66d2-230">지정된 수동 중복 제거 규칙이 없고 시스템 정의 중복 제거 규칙이 적용되는 경우 중복 제거 출력 엔터티에서 이 필드를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-230">If there are no manual deduplication rules specified and system defined deduplication rules apply, you may not find this field in the deduplication output entity.</span></span>
  - <span data-ttu-id="d66d2-231">Deduplication_WinnerId: 이 필드에는 식별된 그룹 또는 클러스터의 승자 ID가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-231">Deduplication_WinnerId: This field contains the winner ID from the identified groups or clusters.</span></span> <span data-ttu-id="d66d2-232">Deduplication_WinnerId가 레코드의 기본 키 값과 같으면 레코드가 승자 레코드라는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-232">If the Deduplication_WinnerId is same as the Primary key value for a record, it means that the record is the winner record.</span></span>
- <span data-ttu-id="d66d2-233">중복 제거 규칙을 정의하는 데 사용되는 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-233">Fields used to define the deduplication rules.</span></span>
- <span data-ttu-id="d66d2-234">적용된 중복 제거 규칙과 일치 알고리즘에서 반환된 점수를 나타내는 규칙 및 점수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-234">Rule and Score fields to denote which of the deduplication rules got applied and the score returned by the matching algorithm.</span></span>
   
## <a name="run-the-match-process"></a><span data-ttu-id="d66d2-235">일치 프로세스 실행</span><span class="sxs-lookup"><span data-stu-id="d66d2-235">Run the match process</span></span>

<span data-ttu-id="d66d2-236">엔터티 간 일치 및 중복 제거 규칙을 포함하여 구성된 일치 규칙으로 일치 프로세스를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-236">With configured match rules, including cross-entity matching and deduplication rules, you can run the match process.</span></span> 

<span data-ttu-id="d66d2-237">**데이터** > **Unify** > **일치** 로 이동하고 그리고 **실행** 을 선택하여 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-237">Go to **Data** > **Unify** > **Match** and select **Run** to start the process.</span></span> <span data-ttu-id="d66d2-238">일치 알고리즘은 완료하는 데 약간의 시간이 걸리며 완료될 때까지 구성을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-238">The matching algorithm takes some time to complete and you can't change the configuration until it completes.</span></span> <span data-ttu-id="d66d2-239">변경하기 위해 실행을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-239">To make changes, you can cancel the run.</span></span> <span data-ttu-id="d66d2-240">작업 상태를 선택하고 **프로그레스 세부 정보** 창에서 **작업 취소** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-240">Select the status of the job and select **Cancel job** on the **Progress details** pane.</span></span>

<span data-ttu-id="d66d2-241">성공적인 실행 결과와 통합 고객 프로필 엔터티를 **엔티티** 페이지에서 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-241">You'll find the result of a successful run, the unified customer profile entity, on the **Entities** page.</span></span> <span data-ttu-id="d66d2-242">통합 고객 엔티티는 **프로필** 섹션에서 **고객** 으로 불립니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-242">Your unified customer entity is called **Customers** in the **Profiles** section.</span></span> <span data-ttu-id="d66d2-243">첫 번째 성공적인 일치 실행은 통합 *고객* 엔터티를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-243">The first successful match run creates the unified *Customer* entity.</span></span> <span data-ttu-id="d66d2-244">모든 후속 일치 실행은 해당 엔티티를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-244">All subsequent match runs expand that entity.</span></span>

> [!TIP]
> <span data-ttu-id="d66d2-245">작업/프로세스 [상태에는 6가지 유형](system.md#status-types)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-245">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="d66d2-246">또한 대부분의 프로세스는 [다른 다운스트림 프로세스에 의존](system.md#refresh-policies)합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-246">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="d66d2-247">프로세스 상태를 선택하여 전체 작업의 진행률에 대한 세부 사항을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-247">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="d66d2-248">작업 중 하나를 선택한 다음 **자세히 보기** 참조를 선택하면, 처리 시간, 마지막 처리 날짜, 작업과 관련된 모든 오류 및 경고와 같은 추가 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-248">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="review-and-validate-your-matches"></a><span data-ttu-id="d66d2-249">일치 검토 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="d66d2-249">Review and validate your matches</span></span>

<span data-ttu-id="d66d2-250">**데이터** > **Unify** > **일치** 로 이동하여 일치 쌍의 품질을 평가하고 필요한 경우 구체화합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-250">Go to **Data** > **Unify** > **Match** to evaluate the quality of your match pairs and refine them if necessary.</span></span>

<span data-ttu-id="d66d2-251">페이지 상단의 타일에는 일치하는 레코드 및 중복 항목의 수를 요약하는 주요 메트릭이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-251">The tiles on top of the page show key metrics, summarizing the number of matched records and duplicates.</span></span>

:::image type="content" source="media/match-KPIs.png" alt-text="숫자와 세부 정보가 포함된 일치 페이지의 키 메트릭에 대한 잘린 스크린샷입니다.":::

- <span data-ttu-id="d66d2-253">**고유한 원본 레코드** 는 마지막 일치 실행에서 처리된 개별 원본 레코드의 수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-253">**Unique source records** shows the number of individual source records that were processed in last match run.</span></span>
- <span data-ttu-id="d66d2-254">**일치 및 일치하지 않는 레코드** 는 일치 규칙을 처리한 후 남아있는 고유 레코드 수를 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-254">**Matched and non-matched records** highlights how many unique records remain after processing the match rules.</span></span>
- <span data-ttu-id="d66d2-255">**일치하는 레코드만** 은 모든 매치 쌍에서 일치 수를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-255">**Matched records only** shows the number of matches across all of your match pairs.</span></span>

<span data-ttu-id="d66d2-256">**일치하는 레코드 세부 정보** 테이블에서 각 일치 쌍의 결과와 규칙을 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-256">You can assess the results of each match pair and its rules in the **Matched records details** table.</span></span> <span data-ttu-id="d66d2-257">일치 쌍에서 가져온 레코드 수를 성공적으로 일치된 레코드의 백분율과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-257">Compare the number of records that came from a match pair against the percentage of successfully matched records.</span></span>

<span data-ttu-id="d66d2-258">일치 쌍의 규칙을 검토하여 규칙 수준에서 성공적으로 일치된 레코드의 백분율을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-258">Review the rules of a match pair to see the percentage of successfully matched records at the rule level.</span></span> <span data-ttu-id="d66d2-259">줄임표(...)를 선택한 다음 **일치 미리보기** 를 선택하여 규칙 수준에서 이러한 모든 레코드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-259">Select the ellipsis (...) and then select **Match preview** to view all these records on the rule level.</span></span> <span data-ttu-id="d66d2-260">일부 레코드를 살펴보고 올바르게 일치되었는지 확인하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-260">We recommend that you take a look at some records to validate that they were matched correctly.</span></span>

<span data-ttu-id="d66d2-261">최적의 값을 찾으려면 조건에 대해 다른 정밀도 임계값을 시도하십시오.</span><span class="sxs-lookup"><span data-stu-id="d66d2-261">Try different precision thresholds on conditions to find the optimal value.</span></span>

  1. <span data-ttu-id="d66d2-262">실험할 규칙의 줄임표(...)를 선택하고 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-262">Select the ellipsis (...) for the rule that you want to experiment with and select **Edit**.</span></span>

  2. <span data-ttu-id="d66d2-263">수정하려는 조건에서 정밀도 값을 변경하십시오.</span><span class="sxs-lookup"><span data-stu-id="d66d2-263">Change the precisions values in the conditions you want to revise.</span></span>

  3. <span data-ttu-id="d66d2-264">**프리뷰** 를 선택하여 선택한 조건에 대해 일치 및 일치하지 않는 레코드 수를 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="d66d2-264">Select **Preview** so see the number of matched and unmatched records for the selected condition.</span></span>

## <a name="manage-match-rules"></a><span data-ttu-id="d66d2-265">일치 규칙 관리</span><span class="sxs-lookup"><span data-stu-id="d66d2-265">Manage match rules</span></span>

<span data-ttu-id="d66d2-266">대부분의 일치 매개 변수를 재구성하고 미세 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-266">You can reconfigure and fine-tune most of the match parameters.</span></span>

:::image type="content" source="media/match-rules-management.png" alt-text="일치 규칙 옵션이 있는 드롭 다운 메뉴의 스크린샷입니다.":::

- <span data-ttu-id="d66d2-268">여러 규칙을 정의한 경우 **규칙의 순서를 변경** 합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-268">**Change the order of your rules** if you defined multiple rules.</span></span> <span data-ttu-id="d66d2-269">**위로 이동** 과 **아래로 이동** 옵션을 선택하거나 끌어서 놓기로 일치 규칙을 재정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-269">You can reorder the match rules by selecting the **Move Up** and **Move Down** options or by drag and drop.</span></span>

- <span data-ttu-id="d66d2-270">**편집** 을 선택하여 **규칙 조건을 변경** 하고 다른 분야를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="d66d2-270">**Change rule conditions** by selecting **Edit** and choose different fields.</span></span>

- <span data-ttu-id="d66d2-271">**규칙을 비활성화** 하여 일치 프로세스에서 제외하는 동안 일치 규칙을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-271">**Deactivate a rule** to retain a match rule while excluding it from the matching process.</span></span>

- <span data-ttu-id="d66d2-272">**규칙 복제**: 일치 규칙을 정의했으며 수정 사항이 포함된 유사한 규칙을 만들려면 **복제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-272">**Duplicate your rules** if you've defined a match rule and would like to create a similar rule with modifications, select **Duplicate**.</span></span>

- <span data-ttu-id="d66d2-273">**삭제** 기호를 선택하여 **규칙을 삭제** 합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-273">**Delete a rule** by selecting the **Delete** symbol.</span></span>

## <a name="specify-custom-match-conditions"></a><span data-ttu-id="d66d2-274">사용자 지정 맞춤 일치 조건 지정</span><span class="sxs-lookup"><span data-stu-id="d66d2-274">Specify custom match conditions</span></span>

<span data-ttu-id="d66d2-275">특정 레코드가 항상 일치하거나 일치하지 않아야 하는 조건을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-275">You can specify conditions that certain records should always match or never match.</span></span> <span data-ttu-id="d66d2-276">이러한 규칙을 업로드하여 표준 일치 프로세스를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-276">These rules can be uploaded to override the standard match process.</span></span> <span data-ttu-id="d66d2-277">예를 들어, 레코드에 John Doe I와 John Doe II가 있는 경우 시스템은 이들을 한 사람으로 일치시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-277">For example, if there are John Doe I and John Doe II in our records, the system might match them as one person.</span></span> <span data-ttu-id="d66d2-278">사용자 지정 일치 규칙을 사용하면 프로필이 다른 사람을 참조하도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-278">Custom match rules let you specify that their profiles refer to different people.</span></span> 

1. <span data-ttu-id="d66d2-279">**데이터** > **Unify** > **일치** 로 이동하고 **일치하는 레코드 세부 정보** 에서 **사용자 지정 일치** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-279">Go to **Data** > **Unify** > **Match** and select **Custom match** in the **Matched records details** section.</span></span>

  :::image type="content" source="media/custom-match-create.png" alt-text="강조 표시된 사용자 지정 컨트롤이 있는 일치 규칙 섹션의 스크린샷입니다.":::

1. <span data-ttu-id="d66d2-281">사용자 지정 일치 규칙이 설정되지 않은 경우 더 많은 세부 정보가 있는 새로운 **사용자 지정 일치** 창을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-281">If you have no custom match rules set, you'll see a new **Custom match** pane with more details.</span></span>

1. <span data-ttu-id="d66d2-282">**템플릿에서 채우기** 를 선택하여 엔터티가 항상 일치해야 하는 레코드를 지정할 수 있는 템플릿 파일을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-282">Select **Fill in the template** to get a template file that can specify which records from which entities should always match or never match.</span></span> <span data-ttu-id="d66d2-283">"항상 일치" 레코드와 "절대 일치" 레코드를 두 개의 다른 파일로 따로 기입해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-283">You'll need to separately fill in the "always match" records and "never match" records in two different files.</span></span>

1. <span data-ttu-id="d66d2-284">템플릿에는 사용자 지정 일치에 사용할 엔터티 및 엔터티 기본 키 값을 지정하는 필드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-284">The template contains fields to specify the entity and the entity primary key values to be used in the custom match.</span></span> <span data-ttu-id="d66d2-285">예를 들어, *영업* 엔터티에서 기본 키 *12345* 가 *Contact* 엔터티에서 기본 키 *34567* 과 항상 일치하는 것을 원하는 경우 템플릿을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-285">For example, if you want primary key *12345* from *Sales* entity to always match with primary key *34567* from *Contact* entity, fill in the template:</span></span>
    - <span data-ttu-id="d66d2-286">Entity1: 영업</span><span class="sxs-lookup"><span data-stu-id="d66d2-286">Entity1: Sales</span></span>
    - <span data-ttu-id="d66d2-287">Entity1Key: 12345</span><span class="sxs-lookup"><span data-stu-id="d66d2-287">Entity1Key: 12345</span></span>
    - <span data-ttu-id="d66d2-288">Entity2: 연락처</span><span class="sxs-lookup"><span data-stu-id="d66d2-288">Entity2: Contact</span></span>
    - <span data-ttu-id="d66d2-289">Entity2Key: 34567</span><span class="sxs-lookup"><span data-stu-id="d66d2-289">Entity2Key: 34567</span></span>

   <span data-ttu-id="d66d2-290">동일한 템플릿 파일은 여러 엔터티의 사용자 지정 일치 레코드를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-290">The same template file can specify custom match records from multiple entities.</span></span>
   
   <span data-ttu-id="d66d2-291">엔터티에서 중복 제거에 대한 사용자 지정 일치를 지정하려면 엔터티1 및 엔터티2와 동일한 엔터티를 제공하고 다른 기본 키 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-291">If you want to specify custom matching for deduplication on an entity, provide the same entity as both Entity1 and Entity2 and set the different primary key values.</span></span>

1. <span data-ttu-id="d66d2-292">적용할 모든 재정의를 추가한 후 템플릿 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-292">After adding all the overrides you want to apply, save the template file.</span></span>

1. <span data-ttu-id="d66d2-293">**데이터** > **데이터 원본** 으로 이동하여 새 엔터티로서 템플릿 파일을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-293">Go to **Data** > **Data sources** and ingest the template files as new entities.</span></span> <span data-ttu-id="d66d2-294">일단 수집되면 이를 사용하여 일치 구성을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-294">Once ingested, you can use them to specify the Match configuration.</span></span>

1. <span data-ttu-id="d66d2-295">파일 및 엔터티를 업로드한 후 **사용자 지정 일치** 옵션을 다시 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-295">After uploading the files and entities are available, select the **Custom match** option again.</span></span> <span data-ttu-id="d66d2-296">포함할 엔터티를 지정하는 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-296">You'll see options to specify the entities you want to include.</span></span> <span data-ttu-id="d66d2-297">드롭다운 메뉴에서 필요한 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-297">Select the required entities from the drop-down menu.</span></span>

   :::image type="content" source="media/custom-match-overrides.png" alt-text="사용자 지정 일치 시나리오에 대한 재정의를 선택하는 대화 상자의 스크린샷입니다.":::

1. <span data-ttu-id="d66d2-299">**항상 일치** 및 **일치 없음** 에 사용할 엔터티를 선택하고 **완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-299">Select the entities you want to use for **Always match** and **Never match**, select **Done**.</span></span>

1. <span data-ttu-id="d66d2-300">**일치** 페이지에서 **저장** 을 선택하여 사용자 지정 일치 구성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-300">Select **Save** on the **Match** page to apply the custom match configuration.</span></span>

1. <span data-ttu-id="d66d2-301">**일치** 페이지에서 **실행** 을 선택하여 일치 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-301">Select **Run** on the **Match** page to start the matching process.</span></span> <span data-ttu-id="d66d2-302">다른 지정된 일치 규칙은 사용자 지정 일치 구성에 의해 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-302">Other specified match rules are overridden by the custom match configuration.</span></span>

> [!TIP]
> <span data-ttu-id="d66d2-303">**데이터** > **엔티티** 로 이동하고 **ConflationMatchPair** 엔터티를 리뷰하여 재정의가 적용되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-303">Go to **Data** > **Entities** and review the **ConflationMatchPair** entity to confirm that the overrides are applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="d66d2-304">다음 단계</span><span class="sxs-lookup"><span data-stu-id="d66d2-304">Next step</span></span>

<span data-ttu-id="d66d2-305">하나 이상의 일치 쌍에 대한 매치 프로세스를 완료한 후 [**병합**](merge-entities.md) 항목을 통해 데이터에서 발생할 수 있는 모순을 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d66d2-305">After completing the match process for at least one match pair, you may resolve possible contradictions in your data by going through the [**Merge**](merge-entities.md) topic.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
