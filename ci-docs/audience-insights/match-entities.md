---
title: 데이터 통합 시 엔터티 일치
description: 엔터티를 일치시켜 통합 고객 프로필을 만듭니다.
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 78549037f9c9e59329f5423c36eeb058128802c0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406304"
---
# <a name="match-entities"></a><span data-ttu-id="64c29-103">엔터티 매칭</span><span class="sxs-lookup"><span data-stu-id="64c29-103">Match entities</span></span>

<span data-ttu-id="64c29-104">맵 단계를 완료하면 엔터티와 일치할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-104">After completing the map phase, you're ready to match your entities.</span></span> <span data-ttu-id="64c29-105">일치 단계에서는 데이터 집합을 통합된 고객 프로필 데이터 집합으로 결합하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-105">The match phase specifies how to combine your datasets into a unified customer profile dataset.</span></span> <span data-ttu-id="64c29-106">일치 단계에는 [매핑된 엔터티가 두 개](map-entities.md) 이상 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-106">The match phase requires at least [two mapped entities](map-entities.md).</span></span>

## <a name="specify-the-match-order"></a><span data-ttu-id="64c29-107">일치 순서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-107">Specify the match order</span></span>

<span data-ttu-id="64c29-108">**통합** > **일치** 로 이동하고 **순서 설정** 을 선택하여 일치 단계를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-108">Go to **Unify** > **Match** and select **Set order** to start the match phase.</span></span>

<span data-ttu-id="64c29-109">각 일치는 두 개 이상의 엔터티를 단일 엔터티로 통합하는 동시에 각 고유 고객 레코드를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-109">Each match unifies two or more entities into a single entity, while persisting each unique customer record.</span></span> <span data-ttu-id="64c29-110">다음 예제에서는 **기본** 엔터티로 **ContactCSV: TestData**, **엔터티 2** 로 **WebAccountCSV: TestData** 및 **엔터티 3** 으로 **CallRecordSmall: TestData** 등 3개의 엔터티를 선택했습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-110">In the following example, we selected three entities: **ContactCSV: TestData** as the **Primary** entity, **WebAccountCSV: TestData** as **Entity 2**, and **CallRecordSmall: TestData** as **Entity 3**.</span></span> <span data-ttu-id="64c29-111">선택 항목 위의 다이어그램은 일치 순서가 실행되는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-111">The diagram above the selections illustrates how the match order will be executed.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="64c29-112">![데이터 일치 순서 편집](media/configure-data-match-order-edit-page.png "데이터 일치 순서 편집")</span><span class="sxs-lookup"><span data-stu-id="64c29-112">![Edit the data match order](media/configure-data-match-order-edit-page.png "Edit the data match order")</span></span>
  
<span data-ttu-id="64c29-113">**기본** 엔터티는 **엔터티 2** 와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-113">The **Primary** entity is matched with **Entity 2**.</span></span> <span data-ttu-id="64c29-114">첫 번째 일치에서 발생하는 데이터 집합은 **엔터티 3** 과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-114">The dataset that results from the first match is matched with **Entity 3**.</span></span>
<span data-ttu-id="64c29-115">이 예제에서는 두 개의 일치 항목만 선택했지만 시스템은 더 많은 항목을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-115">In this example, we only selected two matches, but the system can support more.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="64c29-116">**기본** 엔터티로 선택하는 엔터티는 통합 마스터 데이터 집합의 기초가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-116">The entity that you choose as your **Primary** entity will serve as the basis for your unified master dataset.</span></span> <span data-ttu-id="64c29-117">일치 단계 중에 선택된 추가 엔터티가 이 엔터티에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-117">Additional entities that are selected during the match phase will be added to this entity.</span></span> <span data-ttu-id="64c29-118">동시에 이것이 통합된 엔터티가 이 엔터티에 포함된 데이터를 *모두* 포함한다는 것을 의미하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-118">At the same time, this doesn't mean that the unified entity will include *all* of the data included in this entity.</span></span>
>
> <span data-ttu-id="64c29-119">엔터티의 계층 구조를 선택하는 데 도움이 되는 두 가지 고려 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-119">There are two considerations that can help you choose the hierarchy of your entities:</span></span>
>
> - <span data-ttu-id="64c29-120">고객에 대한 가장 완벽하고 신뢰할 수 있는 데이터를 보유하는 것을 고려하는 엔터티는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="64c29-120">What entity do you consider having the most complete and reliable data about your customers?</span></span>
> - <span data-ttu-id="64c29-121">방금 확인한 엔터티에 다른 엔터티(예: 이름, 전화 번호 또는 이메일 주소)가 공유하는 특성이 있습니까?</span><span class="sxs-lookup"><span data-stu-id="64c29-121">Does the entity that you just identified have attributes that are also shared by other entities (for example, name, phone number, or email address)?</span></span> <span data-ttu-id="64c29-122">그렇지 않은 경우 두 번째로 가장 신뢰할 수 있는 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-122">If not, choose your second most reliable entity.</span></span>

<span data-ttu-id="64c29-123">**완료** 를 선택하여 일치 순서를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-123">Select **Done** to save your match order.</span></span>

## <a name="define-rules-for-your-first-match-pair"></a><span data-ttu-id="64c29-124">첫 번째 일치 쌍에 대한 규칙 정의</span><span class="sxs-lookup"><span data-stu-id="64c29-124">Define rules for your first match pair</span></span>

<span data-ttu-id="64c29-125">일치 순서를 지정하면 **일치** 페이지에 정의된 일치 항목이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-125">After specifying the match order, you'll see the defined matches on the **Match** page.</span></span> <span data-ttu-id="64c29-126">일치 순서를 실행할 때까지 화면 상단의 타일은 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-126">The tiles at the top of the screen will be empty until you run your match order.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="64c29-127">![규칙 정의](media/configure-data-match-need-rules.png "규칙 정의")</span><span class="sxs-lookup"><span data-stu-id="64c29-127">![Define rules](media/configure-data-match-need-rules.png "Define rules")</span></span>

<span data-ttu-id="64c29-128">**규칙 필요** 경고는 일치 쌍에 대해 일치하는 규칙이 정의되지 않았음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-128">The **Needs Rules** warning suggests that no match rule is defined for a match pair.</span></span> <span data-ttu-id="64c29-129">일치 규칙은 특정 엔터티 쌍이 일치할 논리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-129">Match rules specify the logic by which a specific pair of entities will be matched.</span></span>

1. <span data-ttu-id="64c29-130">첫 번째 규칙을 정의하려면 일치 테이블(1)에서 해당 일치 행을 선택한 다음 **새 규칙 만들기**(2)를 선택하여 **규칙 정의** 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-130">To define your first rule, open the **Rule Definition** pane by selecting the corresponding match row in the matches table (1) and then selecting **Create new rule** (2).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="64c29-131">![새 규칙 만들기](media/configure-data-match-new-rule2.png "새 규칙 만들기")</span><span class="sxs-lookup"><span data-stu-id="64c29-131">![Create new rule](media/configure-data-match-new-rule2.png "Create new rule")</span></span>

2. <span data-ttu-id="64c29-132">**규칙 편집** 창에서 해당 규칙에 대한 조건을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-132">In the **Edit Rule** pane, configure the conditions for that rule.</span></span> <span data-ttu-id="64c29-133">각 조건은 필수 선택을 포함하는 두 행으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-133">Each condition is represented by two rows that include mandatory selections.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="64c29-134">![새 규칙 창](media/configure-data-match-new-rule-condition.png "새 규칙 창")</span><span class="sxs-lookup"><span data-stu-id="64c29-134">![New rule pane](media/configure-data-match-new-rule-condition.png "New rule pane")</span></span>

   <span data-ttu-id="64c29-135">엔터티/필드(첫 번째) - 첫 번째 일치 쌍 엔터티에서 일치하는 데 사용되는 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-135">Entity/Field (first) - An attribute that will be used for matching from the first match pair entity.</span></span> <span data-ttu-id="64c29-136">예를 들어 전화 번호 또는 전자 메일 주소를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-136">Examples could include a phone number or email address.</span></span> <span data-ttu-id="64c29-137">고객에게 고유할 수 있는 특성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-137">Choose an attribute that is likely to be unique to the customer.</span></span>

   > [!TIP]
   > <span data-ttu-id="64c29-138">활동 유형 특성을 기준으로 일치하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-138">Avoid matching on the basis of activity-type attributes.</span></span> <span data-ttu-id="64c29-139">즉, 특성이 활동인 것처럼 보이는 경우 일치하는 기준이 잘못될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-139">In other words, if an attribute seems to be an activity, then it might be a poor criteria to match by.</span></span>  

   <span data-ttu-id="64c29-140">엔터티/필드(두 번째) - 두 번째 일치 쌍 엔터티에서 일치하는 데 사용되는 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-140">Entity/Field (Second) - An attribute that will be used for matching from the second match pair entity.</span></span>

   <span data-ttu-id="64c29-141">정규화 - **정규화 방법**: 선택한 특성에 대해 다양한 정규화 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-141">Normalize - **Normalization method**: Various normalization options are available for the selected attributes.</span></span> <span data-ttu-id="64c29-142">예를 들어, 문장 부호를 제거하거나 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-142">For example, removing punctuation or removing spaces</span></span>

   <span data-ttu-id="64c29-143">조직 이름 정규화(미리 보기)의 경우 **유형(전화, 이름, 조직)** 을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-143">For Organization name normalization (Preview), you can also select **Type (Phone, Name, Organization)**</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="64c29-144">![정규화-B2B](media/match-normalization-b2b.png "정규화-B2B")</span><span class="sxs-lookup"><span data-stu-id="64c29-144">![Normalization-B2B](media/match-normalization-b2b.png "Normalization-B2B")</span></span>

   <span data-ttu-id="64c29-145">정밀도 수준 - 이 조건에 사용할 정밀도 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-145">Precision level - The level of precision that will be used for this condition.</span></span> <span data-ttu-id="64c29-146">일치 조건에 대한 정밀도 수준을 설정하면 **기본** 및 **사용자 지정** 의 두 가지 유형이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-146">Setting a precision level for a match condition can have two types: **Basic** and **Custom**.</span></span>  
   - <span data-ttu-id="64c29-147">기본: 낮음, 중간, 높음 및 정확의 네 가지 옵션 중에서 선택할 수 있는 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-147">Basic: Provides you with four options to select from: Low, Medium, High, and Exact.</span></span> <span data-ttu-id="64c29-148">100%와 일치하는 레코드만 일치하도록 **정확** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-148">Select **Exact** to only match records that that match 100 percent.</span></span> <span data-ttu-id="64c29-149">100% 동일하지 않은 레코드와 일치하도록 다른 수준 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-149">Select one of the other levels to match records that aren't 100 percent identical.</span></span>
   - <span data-ttu-id="64c29-150">사용자 지정: 슬라이더를 사용하여 레코드가 **사용자 지정** 필드에 값을 일치하거나 입력하는 데 필요한 사용자 지정 백분율을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-150">Custom: Use the slider to define the custom percentage that records need to match or enter a value in the **Custom** field.</span></span> <span data-ttu-id="64c29-151">시스템은 이 임계값을 통과한 레코드만 합성된 일치 쌍으로 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-151">The system will only match records passing this threshold as conflated match pairs.</span></span> <span data-ttu-id="64c29-152">슬라이더의 값은 0에서 1 사이입니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-152">Values on the slider are between 0 and 1.</span></span> <span data-ttu-id="64c29-153">따라서 0.64는 64%를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-153">So 0.64 represents 64 percent.</span></span>

3. <span data-ttu-id="64c29-154">**완료** 를 선택하여 규칙을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-154">Select **Done** to save the rule.</span></span>

### <a name="add-multiple-conditions"></a><span data-ttu-id="64c29-155">여러 조건 추가</span><span class="sxs-lookup"><span data-stu-id="64c29-155">Add multiple conditions</span></span>

<span data-ttu-id="64c29-156">여러 조건이 충족되는 경우에만 엔터티를 일치시키기 위해 AND 연산자를 통해 연결된 조건을 더 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-156">To match your entities only if multiple conditions are met, add more conditions that are linked through an AND operator.</span></span>

1. <span data-ttu-id="64c29-157">**편집 규칙** 창에서 **조건 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-157">In the **Edit rule** pane, select **Add condition**.</span></span> <span data-ttu-id="64c29-158">기존 조건 옆의 제거 단추를 선택하여 조건을 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-158">You can also delete conditions by selecting the remove button next to an existing condition.</span></span>

2. <span data-ttu-id="64c29-159">**완료** 를 선택하여 규칙을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-159">Select **Done** so save the rule.</span></span>

## <a name="add-multiple-rules"></a><span data-ttu-id="64c29-160">여러 규칙 추가</span><span class="sxs-lookup"><span data-stu-id="64c29-160">Add multiple rules</span></span>

<span data-ttu-id="64c29-161">각 조건은 단일 특성 쌍에 적용되며 규칙은 조건 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-161">Each condition applies to a single pair of attributes, while rules represent sets of conditions.</span></span> <span data-ttu-id="64c29-162">엔터티를 다른 특성 집합과 일치하도록 하려면 규칙을 더 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-162">To have your entities matched by different sets of attributes, you can add more rules.</span></span>

1. <span data-ttu-id="64c29-163">대상 그룹 인사이트에서 **데이터** > **통합** > **일치** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-163">In audience insights, go to **Data** > **Unify** > **Match**.</span></span>

2. <span data-ttu-id="64c29-164">업데이트하려는 엔터티를 선택하고 **규칙 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-164">Select the entity you want to update and select **Add rules**.</span></span>

3. <span data-ttu-id="64c29-165">[첫 번째 일치 쌍에 대한 규칙 정의](#define-rules-for-your-first-match-pair)에 설명된 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-165">Follow the procedure as outlined in [Define rules for your first match pair](#define-rules-for-your-first-match-pair).</span></span>

> [!NOTE]
> <span data-ttu-id="64c29-166">규칙 순서가 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-166">The rule order matters.</span></span> <span data-ttu-id="64c29-167">일치 알고리즘은 첫 번째 규칙에 따라 일치하려고 시도하며 첫 번째 규칙에 따라 일치하는 항목이 식별되지 않은 경우에만 두 번째 규칙을 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-167">The matching algorithm tries to match on the basis of your first rule and continues to the second rule only if no matches were identified under the first rule.</span></span>

## <a name="define-deduplication-on-a-match-entity"></a><span data-ttu-id="64c29-168">일치 항목에서 중복 제거 정의</span><span class="sxs-lookup"><span data-stu-id="64c29-168">Define deduplication on a match entity</span></span>

<span data-ttu-id="64c29-169">위 섹션에 설명된 대로 상호 엔터티 일치 규칙을 지정하는 것과 함께 중복 제거 규칙을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-169">Along with specifying cross entity matching rules as outlined in the above sections, you can also specify deduplications rules.</span></span> <span data-ttu-id="64c29-170">*중복 제거* 는 과정입니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-170">*Deduplication* is a process.</span></span> <span data-ttu-id="64c29-171">중복 레코드를 식별하고 이를 하나의 레코드로 병합하고 대체 ID를 사용하여 병합된 레코드에 모든 원본 레코드를 병합된 레코드에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-171">It identifies duplicate records, merges them into one record, and links all the source records to this merged record with alternate IDs to the merged record.</span></span>

<span data-ttu-id="64c29-172">중복 제거된 레코드가 식별되면 해당 레코드가 상호 엔터티 일치 프로세스에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-172">After a deduplicated record is identified, that record will be used in the cross-entity matching process.</span></span> <span data-ttu-id="64c29-173">중복 제거는 엔터티 수준에서 구현되며 일치 프로세스에 사용되는 모든 엔터티에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-173">Deduplication is implemented at the entity level and can be applied to every entity used in the Match process.</span></span>

### <a name="add-deduplication-rules"></a><span data-ttu-id="64c29-174">중복 제거 규칙 추가</span><span class="sxs-lookup"><span data-stu-id="64c29-174">Add deduplication rules</span></span>

1. <span data-ttu-id="64c29-175">대상 그룹 인사이트에서 **데이터** > **통합** > **일치** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-175">In audience insights, go to **Data** > **Unify** > **Match**.</span></span>

1. <span data-ttu-id="64c29-176">**병합된 중복 항목** 섹션에서 **엔터티 설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-176">In the **Merged duplicates** section, select **Set entities**.</span></span>

1. <span data-ttu-id="64c29-177">**기본 설정 병합** 섹션에서 중복 제거를 적용할 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-177">In the **Merge preferences** section, select the entities you want to apply deduplication to.</span></span>

1. <span data-ttu-id="64c29-178">중복 레코드를 병합하는 방법을 지정하고 다음 세 가지 병합 옵션 중 하나를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="64c29-178">Specify how to merge the duplicate records and choose one of three merge options:</span></span>
   - <span data-ttu-id="64c29-179">*가장 많이 채워진*: 가장 많이 채워진 특성이 있는 레코드를 승자 레코드로 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-179">*Most filled*: Identifies the record with most filled attributes as the winner record.</span></span> <span data-ttu-id="64c29-180">기본 병합 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-180">This is the default merge option.</span></span>
   - <span data-ttu-id="64c29-181">*가장 최근*: 최신순으로 승자 기록을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-181">*Most recent*: Identifies the winner record based on the most recency.</span></span> <span data-ttu-id="64c29-182">최신 성을 정의하려면 날짜 또는 숫자 필드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-182">Requires a date or a numeric field to define the recency.</span></span>
   - <span data-ttu-id="64c29-183">*가장 최근*: 최신순으로 승자 기록을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-183">*Least recent*: Identifies the winner record based on the least recency.</span></span> <span data-ttu-id="64c29-184">최신 성을 정의하려면 날짜 또는 숫자 필드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-184">Requires a date or a numeric field to define the recency.</span></span>
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="64c29-185">![중복 제거 규칙 1단계](media/match-selfconflation.png "중복 제거 규칙 1단계")</span><span class="sxs-lookup"><span data-stu-id="64c29-185">![Deduplication rules step 1](media/match-selfconflation.png "Deduplication rules step 1")</span></span>
 
1. <span data-ttu-id="64c29-186">엔터티가 선택되고 기본 설정 병합이 설정되면 **새 규칙 만들기** 를 선택하여 엔터티 수준에서 중복 제거 규칙을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-186">Once the entities are selected and their merge preference is set, select **Create new rule** to define the deduplication rules at an entity level.</span></span>
   - <span data-ttu-id="64c29-187">**필드 선택** 은 원본 데이터를 중복 제거하려는 해당 엔터티에서 사용 가능한 모든 필드를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-187">**Select field** lists all the available fields from that entity you want to deduplicate source data on.</span></span>
   - <span data-ttu-id="64c29-188">상호 엔터티 일치에 지정된 것과 유사한 방식으로 정규화 및 정밀도 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-188">Specify the normalization and precision settings in similar way as specified in the cross entity matching.</span></span>
   - <span data-ttu-id="64c29-189">**조건 추가** 를 선택하여 추가 조건을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-189">You can define additional conditions by selecting **Add condition**.</span></span>
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="64c29-190">![중복 제거 규칙 2단계](media/match-selfconflation-rules.png "중복 제거 규칙 2단계")</span><span class="sxs-lookup"><span data-stu-id="64c29-190">![Deduplication rules step 2](media/match-selfconflation-rules.png "Deduplication rules step 2")</span></span>

  <span data-ttu-id="64c29-191">엔터티에 대해 여러 중복 제거 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-191">You can create multiple deduplication rules for an entity.</span></span> 

1. <span data-ttu-id="64c29-192">이제 일치 프로세스를 실행하면 중복 제거 규칙에 정의된 조건에 따라 레코드가 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-192">Running the match process now groups the records based on the conditions defined in the deduplication rules.</span></span> <span data-ttu-id="64c29-193">레코드를 그룹화한 후 병합 정책이 적용되어 승자 레코드를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-193">After grouping the records, the merge policy is applied to identify the winner record.</span></span>

1. <span data-ttu-id="64c29-194">그런 다음 이 우승자 레코드는 엔터티 간 일치에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-194">This winner record is then passed on to the cross-entity matching.</span></span>

1. <span data-ttu-id="64c29-195">항상 일치에 대해 정의 된 사용자 지정 일치 규칙은 중복 제거 규칙을 무시하고 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-195">Any custom match rules defined for always match and never match overrule deduplication rules.</span></span> <span data-ttu-id="64c29-196">중복 제거 규칙이 일치하는 레코드를 식별하고 사용자 지정 일치 규칙이 해당 레코드와 일치하지 않도록 설정된 경우 이 두 레코드는 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-196">If a deduplication rule identifies matching records, and a custom match rule is set to never match those records, then these two records won't be matched.</span></span>

1. <span data-ttu-id="64c29-197">일치 프로세스를 실행하면 중복 제거 통계가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-197">After running the match process, you will see the deduplication stats.</span></span>
   
> [!NOTE]
> <span data-ttu-id="64c29-198">중복 제거 규칙을 지정하는 것은 필수가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-198">Specifying deduplication rules isn't mandatory.</span></span> <span data-ttu-id="64c29-199">이러한 규칙이 구성되지 않은 경우 시스템 정의 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-199">If no such rules are configured, the system-defined rules are applied.</span></span> <span data-ttu-id="64c29-200">성능 및 시스템 온전성을 향상시키기 위해 엔터티 데이터를 엔터티 간 일치에 전달하기 전에 기본 키와 일치 규칙의 필드에서 동일한 값 조합(정확히 일치)을 공유하는 모든 레코드를 단일 레코드로 축소합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-200">They collapse all records that share the same value combination (exact match) from primary key and the fields in the matching rules into a single record before passing the entity data to cross-entity matching for enhanced performance and system sanity.</span></span>

## <a name="run-your-match-order"></a><span data-ttu-id="64c29-201">일치 순서 실행</span><span class="sxs-lookup"><span data-stu-id="64c29-201">Run your match order</span></span>

<span data-ttu-id="64c29-202">엔터티 간 일치 및 중복 제거 규칙을 포함하여 일치 규칙을 정의한 후 일치 순서를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-202">After defining the match rules, including cross-entity matching and deduplication rules, you can run the match order.</span></span> <span data-ttu-id="64c29-203">**일치** 페이지에서 **실행** 을 선택하여 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-203">On the **Match** page, select **Run** to start the process.</span></span> <span data-ttu-id="64c29-204">일치 알고리즘을 완료하는 데 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-204">The matching algorithm might take some time to complete.</span></span> <span data-ttu-id="64c29-205">일치 프로세스가 완료될 때까지 **일치** 페이지에서 속성을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-205">You can't change properties on the **Match** page until the match process completes.</span></span> <span data-ttu-id="64c29-206">**엔터티** 페이지에서 만든 통합된 고객 프로필 엔터티를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-206">You'll find the unified customer profile entity that was created on the **Entities** page.</span></span> <span data-ttu-id="64c29-207">통합 고객 엔터티를 **ConflationMatchPairs: CustomerInsights** 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-207">Your unified customer entity is called **ConflationMatchPairs:CustomerInsights**.</span></span>

<span data-ttu-id="64c29-208">추가 변경을 수행하고 단계를 다시 실행하기 위해 진행 중인 일치를 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-208">To make additional changes and rerun the step, you can cancel a match in progress.</span></span> <span data-ttu-id="64c29-209">**새로 고침 중...** 텍스트를 선택하고 나타나는 측면 창의 맨 아래에서 **작업 취소** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-209">Select the **Refreshing ...** text and select **Cancel job** at the bottom of the side pane that appears.</span></span>

<span data-ttu-id="64c29-210">일치 프로세스가 완료되면 **새로 고침 중...** 텍스트가 **성공** 으로 바뀌고 페이지의 모든 기능을 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-210">When the match process is complete, the **Refreshing ...** text will change to **Successful** and you can use all functionality of the page again.</span></span>

<span data-ttu-id="64c29-211">첫 번째 일치 프로세스는 통합된 마스터 엔터티를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-211">The first match process results in the creation of a unified master entity.</span></span> <span data-ttu-id="64c29-212">이후의 모든 일치 실행은 해당 엔터티의 확장을 초래합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-212">All subsequent match runs result in the expansion of that entity.</span></span>

> [!TIP]
> <span data-ttu-id="64c29-213">작업/프로세스 [상태에는 6가지 유형](system.md#status-types)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-213">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="64c29-214">또한 대부분의 프로세스는 [다른 다운스트림 프로세스에 의존](system.md#refresh-policies)합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-214">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="64c29-215">프로세스 상태를 선택하여 전체 작업의 진행률에 대한 세부 사항을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-215">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="64c29-216">작업 중 하나를 선택한 다음 **자세히 보기** 참조를 선택하면, 처리 시간, 마지막 처리 날짜, 작업과 관련된 모든 오류 및 경고와 같은 추가 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-216">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="review-and-validate-your-matches"></a><span data-ttu-id="64c29-217">일치 검토 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="64c29-217">Review and validate your matches</span></span>

<span data-ttu-id="64c29-218">일치 쌍의 품질을 평가하고 세분화합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-218">Evaluate the quality of your match pairs and refine it:</span></span>

- <span data-ttu-id="64c29-219">**일치** 페이지에서 데이터에 대한 초기 인사이트를 보여주는 두 개의 타일을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-219">On the **Match** page, you'll find two tiles showing initial insights about your data.</span></span>

  - <span data-ttu-id="64c29-220">**고유 고객**: 시스템이 식별한 고유 프로필 수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-220">**Unique customers**: shows the number of unique profiles that the system identified.</span></span>
  - <span data-ttu-id="64c29-221">**일치하는 레코드**: 모든 일치 쌍에 대한 일치 횟수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-221">**Matched records**: shows the number of matches across all of your match pairs.</span></span>

- <span data-ttu-id="64c29-222">**일치 순서** 테이블에서 이 일치 쌍 엔터티에서 온 레코드 수와 성공적으로 일치하는 레코드의 백분율을 비교하여 각 일치 쌍의 결과를 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-222">In the **Match order** table, you can assess the results of each match pair by comparing the number of records that came from this match-pair entity against the percentage of successfully matched records.</span></span>

- <span data-ttu-id="64c29-223">**일치 순서** 테이블에서 엔터티의 **규칙** 섹션에서 규칙 수준에서 성공적으로 일치하는 레코드의 백분율을 찾을 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="64c29-223">In the **Rules** section of an entity in the **Match order** table, you'll find the percentage of successfully matched records at the rule level.</span></span> <span data-ttu-id="64c29-224">규칙 옆의 테이블 기호를 선택하면 규칙 수준에서 이러한 모든 레코드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-224">By selecting the table symbol next to a rule, you can view all these records on the rule level.</span></span> <span data-ttu-id="64c29-225">레코드의 하위 집합을 검토하여 레코드가 올바르게 일치하는지 확인하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-225">We recommend that you review a subset of the records to validate that they were matched correctly.</span></span>

- <span data-ttu-id="64c29-226">조건 주위의 다양한 정밀도 임계값을 실험하여 최적의 값을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-226">Experiment with different precision thresholds around your conditions to identify the optimal value.</span></span>

  1. <span data-ttu-id="64c29-227">실험할 일치 쌍 규칙에 대해 타원(...)을 선택하고 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-227">Select the ellipsis (...) for the match pair rule that you want to experiment with and select **Edit**.</span></span>

  2. <span data-ttu-id="64c29-228">실험할 조건을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-228">Select the condition that you want to experiment with.</span></span> <span data-ttu-id="64c29-229">각 기준은 **일치 규칙** 창에서 한 행으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-229">Each criterion is represented by one row in the **Match rule** pane.</span></span>

  3. <span data-ttu-id="64c29-230">**기준 미리 보기** 페이지에 표시되는 내용은 조건에 대해 선택한 정밀도 수준에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-230">What you'll see on the **Criteria preview** page depends on the precision level you've selected for a condition.</span></span> <span data-ttu-id="64c29-231">선택한 조건에 대해 일치하고 일치하지 않는 레코드 수를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-231">Find the number of matched and unmatched records for the selected condition.</span></span>

     <span data-ttu-id="64c29-232">다른 임계값 수준의 효과에 대한 풍부한 이해를 얻으십시오.</span><span class="sxs-lookup"><span data-stu-id="64c29-232">Get a rich understanding of the effects of different threshold levels.</span></span> <span data-ttu-id="64c29-233">각 임계값 수준에서 일치하는 레코드 수를 비교하고 각 옵션에서 레코드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-233">You can compare how many records will be matched under each of the threshold levels, and view the records under each option.</span></span> <span data-ttu-id="64c29-234">각 타일을 선택하고 테이블 섹션의 데이터를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-234">Select each of the tiles and review the data in the table section.</span></span>

## <a name="optimize-your-matches"></a><span data-ttu-id="64c29-235">일치 최적화</span><span class="sxs-lookup"><span data-stu-id="64c29-235">Optimize your matches</span></span>

<span data-ttu-id="64c29-236">일부 일치 매개 변수를 다시 구성하여 품질을 향상시킵니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-236">Increase the quality by reconfiguring some of your match parameters:</span></span>

- <span data-ttu-id="64c29-237">**편집** 을 선택하여 **일치 순서를 변경** 하고 일치 순서 필드를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-237">**Change the match order** by selecting **Edit** and change the match order fields.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="64c29-238">![데이터 일치 순서 편집](media/configure-data-match-order-edit.png "데이터 일치 순서 편집")</span><span class="sxs-lookup"><span data-stu-id="64c29-238">![Edit data match order](media/configure-data-match-order-edit.png "Edit data match order")</span></span>

- <span data-ttu-id="64c29-239">여러 규칙을 정의한 경우 **규칙의 순서를 변경** 합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-239">**Change the order of your rules** if you defined multiple rules.</span></span> <span data-ttu-id="64c29-240">일치 규칙 그리드에서 **위로 이동** 및 **아래로 이동** 옵션을 선택하여 일치 규칙의 순서를 다시 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-240">You can reorder the match rules by selecting the **Move Up** and **Move Down** options in the match rules grid.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="64c29-241">![규칙 순서 변경](media/configure-data-change-rule-order.png "규칙 순서 변경")</span><span class="sxs-lookup"><span data-stu-id="64c29-241">![Change rule order](media/configure-data-change-rule-order.png "Change rule order")</span></span>

- <span data-ttu-id="64c29-242">일치 규칙을 정의하고 수정하여 유사한 규칙을 만들려면 **규칙을 복제** 합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-242">**Duplicate your rules** if you've defined a match rule and would like to create a similar rule with modifications.</span></span> <span data-ttu-id="64c29-243">이렇게 하려면 **중복** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-243">Do so by selecting **Duplicate**.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="64c29-244">![규칙 복제](media/configure-data-duplicate-rule.png "규칙 복제")</span><span class="sxs-lookup"><span data-stu-id="64c29-244">![Duplicate a rule](media/configure-data-duplicate-rule.png "Duplicate a rule")</span></span>

- <span data-ttu-id="64c29-245">**편집** 기호를 선택하여 **규칙을 편집** 합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-245">**Edit your rules** by selecting the **Edit** symbol.</span></span> <span data-ttu-id="64c29-246">또한 다음과 같이 변경을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-246">You can apply the following changes:</span></span>

  - <span data-ttu-id="64c29-247">조건에 대한 특성 변경: 특정 조건 행 내에서 새 특성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-247">Change attributes for a condition: Select new attributes within the specific condition row.</span></span>
  - <span data-ttu-id="64c29-248">조건의 임계값을 변경합니다. 정밀도 슬라이더를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-248">Change the threshold for a condition: Adjust the precision slider.</span></span>
  - <span data-ttu-id="64c29-249">조건에 대한 정규화 방법을 변경합니다. 정규화 메서드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-249">Change the normalization method for a condition: Update the normalization method.</span></span>

## <a name="specify-your-custom-match-records"></a><span data-ttu-id="64c29-250">사용자 지정 일치 레코드 지정</span><span class="sxs-lookup"><span data-stu-id="64c29-250">Specify your custom match records</span></span>

<span data-ttu-id="64c29-251">특정 레코드가 항상 일치하거나 일치하지 않아야 하는 조건을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-251">You can specify conditions that certain records should always match or never match.</span></span> <span data-ttu-id="64c29-252">이러한 규칙은 일치 프로세스에 일괄 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-252">These rules can be uploaded in bulk to the match process.</span></span>

1. <span data-ttu-id="64c29-253">**일치 주문** 화면에서 **맞춤 검색** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-253">Select the **Custom match** option on the **Match order** screen.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="64c29-254">![사용자 지정 일치 만들기](media/custom-match-create.png "사용자 지정 일치 만들기")</span><span class="sxs-lookup"><span data-stu-id="64c29-254">![Create a custom match](media/custom-match-create.png "Create a custom match")</span></span>

2. <span data-ttu-id="64c29-255">업로드된 엔터티가 없는 경우 몇 가지 세부 정보를 입력해야 하는 새로운 **사용자 지정 일치** 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-255">If you have no uploaded entities, you'll see a new **Custom match** dialog box that requires you to fill in some details.</span></span> <span data-ttu-id="64c29-256">이러한 세부 정보를 이전에 제공한 경우 8단계로 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-256">If you've provided these details earlier, skip to step 8.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="64c29-257">![새 사용자 지정 일치 대화 상자](media/custom-match-new-dialog-box.png "새 사용자 지정 일치 대화 상자")</span><span class="sxs-lookup"><span data-stu-id="64c29-257">![New custom match dialog box](media/custom-match-new-dialog-box.png "New custom match dialog box")</span></span>

3. <span data-ttu-id="64c29-258">**템플릿에서 채우기** 를 선택하여 엔터티가 항상 일치해야 하는 레코드를 지정할 수 있는 템플릿 파일을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-258">Select **Fill in the template** to get a template file that can specify which records from which entities should always match or never match.</span></span> <span data-ttu-id="64c29-259">"항상 일치" 레코드와 "절대 일치" 레코드를 두 개의 다른 파일로 따로 기입해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-259">You'll need to separately fill in the "always match" records and "never match" records in two different files.</span></span>

4. <span data-ttu-id="64c29-260">템플릿에는 사용자 지정 일치에 사용할 엔터티 및 엔터티 기본 키 값을 지정하는 필드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-260">The template contains fields to specify the entity and the entity primary key values to be used in the custom match.</span></span> <span data-ttu-id="64c29-261">예를 들어 영업 엔터티의 기본 키 12345가 연락처 엔터티의 기본 키 34567과 항상 일치하도록 하려면 다음과 같이 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-261">For example, if you want primary key 12345 from Sales entity to always match with primary key 34567 from Contact entity, you'll need to specify as follows:</span></span>
    - <span data-ttu-id="64c29-262">Entity1: 영업</span><span class="sxs-lookup"><span data-stu-id="64c29-262">Entity1: Sales</span></span>
    - <span data-ttu-id="64c29-263">Entity1Key: 12345</span><span class="sxs-lookup"><span data-stu-id="64c29-263">Entity1Key: 12345</span></span>
    - <span data-ttu-id="64c29-264">Entity2: 연락처</span><span class="sxs-lookup"><span data-stu-id="64c29-264">Entity2: Contact</span></span>
    - <span data-ttu-id="64c29-265">Entity2Key: 34567</span><span class="sxs-lookup"><span data-stu-id="64c29-265">Entity2Key: 34567</span></span>

   <span data-ttu-id="64c29-266">동일한 템플릿 파일은 여러 엔터티의 사용자 지정 일치 레코드를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-266">The same template file can specify custom match records from multiple entities.</span></span>

5. <span data-ttu-id="64c29-267">적용할 모든 재정의를 추가한 후 템플릿 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-267">After adding all the overrides you want to apply, save the template file.</span></span>

<span data-ttu-id="64c29-268">6.**데이터** > **데이터 원본** 으로 이동하여 새 엔터티로 템플릿 파일을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-268">6.Go to **Data** > **Data sources** and ingest the template files as new entities.</span></span> <span data-ttu-id="64c29-269">일단 수집되면 이를 사용하여 일치 구성을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-269">Once ingested, you can use them to specify the Match configuration.</span></span>

7. <span data-ttu-id="64c29-270">파일 및 엔터티를 업로드한 후 **사용자 지정 일치** 옵션을 다시 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-270">After uploading the files and entities are available, select the **Custom match** option again.</span></span> <span data-ttu-id="64c29-271">포함할 엔터티를 지정하는 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-271">You'll see options to specify the entities you want to include.</span></span> <span data-ttu-id="64c29-272">드롭다운 메뉴에서 필요한 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-272">Select the required entities from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="64c29-273">![사용자 지정 일치 재정의](media/custom-match-overrides.png "사용자 지정 일치 재정의")</span><span class="sxs-lookup"><span data-stu-id="64c29-273">![Custom match overrides](media/custom-match-overrides.png "Custom match overrides")</span></span>

8. <span data-ttu-id="64c29-274">**항상 일치** 및 **일치 없음** 에 사용할 엔터티를 선택하고 **완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-274">Select the entities you want to use for **Always match** and **Never match**, select **Done**.</span></span>

9. <span data-ttu-id="64c29-275">방금 설정한 사용자 지정 검색 구성을 위해 **일치** 페이지에서 **일치** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-275">Select **Save** on the **Match** page for the custom match configuration you just set up.</span></span>

10. <span data-ttu-id="64c29-276">**일치** 페이지에서 **실행** 을 선택하여 일치 프로세스를 시작하면 사용자 정의 일치 구성이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-276">Select **Run** on the **Match** page to start the matching process, and the custom match configuration will be taken into effect.</span></span> <span data-ttu-id="64c29-277">일치하는 모든 시스템은 구성 집합에 의해 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-277">Any system matched rules are overridden by the configuration set.</span></span>

11. <span data-ttu-id="64c29-278">일치가 완료되면 **ConflationMatchPair** 엔터티를 확인하여 재재정이 컴플레이션 일치에 적용되는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-278">Once the matching is complete, you can verify the **ConflationMatchPair** entity to confirm that the overrides are applied in the conflation matches.</span></span>

## <a name="next-step"></a><span data-ttu-id="64c29-279">다음 단계</span><span class="sxs-lookup"><span data-stu-id="64c29-279">Next step</span></span>

<span data-ttu-id="64c29-280">하나 이상의 일치 쌍에 대한 매치 프로세스를 완료한 후 [**병합**](merge-entities.md) 항목을 통해 데이터에서 발생할 수 있는 모순을 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64c29-280">After completing the match process for at least one match pair, you may resolve possible contradictions in your data by going through the [**Merge**](merge-entities.md) topic.</span></span>
