---
title: 측정값 만들기 및 관리
description: 비즈니스 성과를 분석하고 반영하기 위한 측정값을 정의합니다.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9a94a32a04f2a8beb661c27271fe96f23d998722
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887948"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="5890e-103">측정 정의 및 관리</span><span class="sxs-lookup"><span data-stu-id="5890e-103">Define and manage measures</span></span>

<span data-ttu-id="5890e-104">측정값은 고객 행동과 비즈니스 성과를 더 잘 이해하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="5890e-105">측정값은 [통합 프로필](data-unification.md)에서 관련 가치를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="5890e-106">예를 들어, 비즈니스가 개별 고객의 구매 내역을 이해하기 위해 *고객당 총 지출* 을 보거나 전체 비즈니스의 총 수익을 이해하기 위해 *회사의 총 매출* 을 측정하고자 합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-106">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="5890e-107">측정값은 다양한 연산자와 간단한 매핑 옵션이 있는 데이터 쿼리 플랫폼인 측정값 빌더를 사용하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="5890e-108">이를 통해 데이터를 필터링하고 결과를 그룹화하고 [엔터티 관계 경로](relationships.md)를 감지하고 출력을 미리 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="5890e-109">측정값 빌더를 사용하여 고객 데이터를 쿼리하고 인사이트를 추출하여 비즈니스 활동을 계획합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="5890e-110">예를 들어 *고객당 총 지출* 및 *고객당 총 수익* 의 측정값을 생성하면 지출이 많고 수익이 높은 고객 그룹을 식별하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="5890e-111">[세그먼트 생성](segments.md)을 통해 차선책을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="5890e-112">처음부터 측정값 직접 빌드</span><span class="sxs-lookup"><span data-stu-id="5890e-112">Build your own measure from scratch</span></span>

<span data-ttu-id="5890e-113">이 섹션에서는 새 측정값을 만드는 과정을 처음부터 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="5890e-114">고객 엔터티와 연결하도록 설정된 관계가 있는 데이터 엔터티의 데이터 특성을 사용하여 측정값을 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="5890e-115">대상 그룹 인사이트에서 **측정값** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="5890e-116">**신규** 를 선택하고 **직접 빌드** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="5890e-117">**이름 편집** 을 선택하고 측정값에 대한 **이름** 을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="5890e-118">새 측정값 구성에 두 개의 필드(예: CustomerID 및 계산)만 있는 경우 출력은 Customer_Measure라는 시스템 생성 엔터티에 새 열로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="5890e-119">그리고 통합 고객 프로필에서 측정값의 값을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="5890e-120">다른 측정값은 자체 엔터티를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="5890e-121">구성 영역의 **함수 선택** 드롭 다운 메뉴에서 집계 함수를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="5890e-122">집계 함수에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="5890e-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="5890e-123">**Sum**</span></span>
   - <span data-ttu-id="5890e-124">**평균**</span><span class="sxs-lookup"><span data-stu-id="5890e-124">**Average**</span></span>
   - <span data-ttu-id="5890e-125">**수**</span><span class="sxs-lookup"><span data-stu-id="5890e-125">**Count**</span></span>
   - <span data-ttu-id="5890e-126">**고유 개수**</span><span class="sxs-lookup"><span data-stu-id="5890e-126">**Count Unique**</span></span>
   - <span data-ttu-id="5890e-127">**최대**</span><span class="sxs-lookup"><span data-stu-id="5890e-127">**Max**</span></span>
   - <span data-ttu-id="5890e-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="5890e-128">**Min**</span></span>
   - <span data-ttu-id="5890e-129">**첫 번째**: 데이터 레코드의 첫 번째 값 사용</span><span class="sxs-lookup"><span data-stu-id="5890e-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="5890e-130">**마지막**: 데이터 레코드에 추가된 마지막 값 사용</span><span class="sxs-lookup"><span data-stu-id="5890e-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="측정값 계산을 위한 연산자입니다.":::

1. <span data-ttu-id="5890e-132">**특성 추가** 를 선택하여 이 측정값을 만드는 데 필요한 데이터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="5890e-133">**특성** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="5890e-134">데이터 엔터티: 측정하려는 특성이 포함된 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="5890e-135">데이터 특성: 측정값을 계산하기 위해 집계 함수에서 사용할 특성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="5890e-136">한번에 하나의 특성만 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="5890e-137">**측정** 탭을 선택하여 기존 측정에서 데이터 속성을 선택할 수도 있습니다. 또는 엔터티 또는 측정값 이름을 검색 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="5890e-138">**추가** 를 선택하여 측정값에 선택한 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="계산에 사용할 특성을 선택합니다.":::

1. <span data-ttu-id="5890e-140">더 복잡한 측정값을 빌드하기 위해 측정값 함수에 더 많은 특성을 추가하거나 수학 연산자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="수학 연산자를 사용하여 복잡한 측정값을 만듭니다.":::

1. <span data-ttu-id="5890e-142">필터를 추가하려면 구성 영역에서 **필터** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="5890e-143">**필터** 창의 **속성 추가** 섹션에서 필터를 만드는 데 사용할 특성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="5890e-144">선택한 모든 특성에 대한 필터를 정의하도록 필터 연산자를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="5890e-145">**적용** 을 선택하여 측정값에 필터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="5890e-146">차원을 추가하려면 구성 영역에서 **차원** 을 ​​선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="5890e-147">차원은 측정값 출력 엔터티에서 열로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="5890e-148">**차원 편집** 을 선택하여 측정값을 그룹화하려는 데이터 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="5890e-149">예: 도시 또는 성별.</span><span class="sxs-lookup"><span data-stu-id="5890e-149">For example, city or gender.</span></span> <span data-ttu-id="5890e-150">기본적으로 *고객 수준 측정값* 을 만들기 위해 *CustomerID* 차원이 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="5890e-151">*비즈니스 수준 측정값* 을 만들려는 경우 기본 차원을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="5890e-152">**완료** 를 선택하여 측정값에 차원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="5890e-153">데이터에 정수로 바꿔야 하는 값이 있는 경우(예: *Null* 을 *0* 으로 대체) **규칙** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-153">If there are values in your data that you need to replace with an integer, for example, replace *null* with *0*, select **Rules**.</span></span> <span data-ttu-id="5890e-154">규칙을 구성하고 정수만 선택했는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="5890e-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="5890e-155">매핑한 데이터 엔터티와 *고객* 엔터티 사이에 여러 경로가 있는 경우 식별된 [엔티티 관계 경로](relationships.md) 중 하나를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="5890e-156">측정 결과는 선택한 경로에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-156">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="5890e-157">**데이터 선호 설정** 을 선택하여 측정값을 식별하는 데 사용해야 하는 엔터티 경로를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="5890e-158">*고객* 엔터티로의 경로가 하나뿐인 경우 이 컨트롤은 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="5890e-159">**완료** 를 선택하여 선택 사항을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="측정값에 대한 엔터티 경로를 선택합니다.":::

1. <span data-ttu-id="5890e-161">측정값에 대한 계산을 더 추가하려면 **새로운 계산** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="5890e-162">새로운 계산에는 동일한 엔터티 경로에 있는 엔터티만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="5890e-163">더 많은 계산이 측정값 출력 엔터티에 새 열로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="5890e-164">계산에서 **...** 을 선택하여 측정값에서 계산을 **복제**, **이름 바꾸기** 또는 **제거** 합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="5890e-165">**미리 보기** 영역에는 필터 및 차원을 포함하여 측정값 출력 엔터티의 데이터 스키마가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="5890e-166">미리 보기는 구성 변경에 동적으로 반응합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="5890e-167">**실행** 을 선택하여 구성된 측정값에 대한 결과를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="5890e-168">현재 구성을 유지하고 나중에 측정을 실행하려면 **저장 및 닫기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="5890e-169">**측정값** 으로 이동하여 목록에서 새로 만들어진 측정값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="5890e-170">템플릿을 사용하여 측정값 빌드</span><span class="sxs-lookup"><span data-stu-id="5890e-170">Use a template to build a measure</span></span>

<span data-ttu-id="5890e-171">일반적으로 사용되는 측정값의 미리 정의된 템플릿을 사용하여 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="5890e-172">템플릿에 대한 자세한 설명과 안내식 경험은 효율적인 측정값 생성에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="5890e-173">템플릿은 *통합 활동* 엔터티의 매핑된 데이터를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="5890e-174">따라서 템플릿에서 측정값을 만들기 전에 [고객 활동](activities.md)을 구성했는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="5890e-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="5890e-175">사용할 수 있는 측정값 템플릿:</span><span class="sxs-lookup"><span data-stu-id="5890e-175">Available measure templates:</span></span> 
- <span data-ttu-id="5890e-176">평균 거래 금액(ATV)</span><span class="sxs-lookup"><span data-stu-id="5890e-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="5890e-177">총 거래 금액</span><span class="sxs-lookup"><span data-stu-id="5890e-177">Total transaction value</span></span>
- <span data-ttu-id="5890e-178">평균 일일 수익</span><span class="sxs-lookup"><span data-stu-id="5890e-178">Average daily revenue</span></span>
- <span data-ttu-id="5890e-179">평균 연간 수익</span><span class="sxs-lookup"><span data-stu-id="5890e-179">Average yearly revenue</span></span>
- <span data-ttu-id="5890e-180">거래 횟수</span><span class="sxs-lookup"><span data-stu-id="5890e-180">Transaction count</span></span>
- <span data-ttu-id="5890e-181">획득한 로열티 포인트</span><span class="sxs-lookup"><span data-stu-id="5890e-181">Loyalty points earned</span></span>
- <span data-ttu-id="5890e-182">사용한 로열티 포인트</span><span class="sxs-lookup"><span data-stu-id="5890e-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="5890e-183">잔여 로열티 포인트</span><span class="sxs-lookup"><span data-stu-id="5890e-183">Loyalty points balance</span></span>
- <span data-ttu-id="5890e-184">활성 고객 수명</span><span class="sxs-lookup"><span data-stu-id="5890e-184">Active customer lifespan</span></span>
- <span data-ttu-id="5890e-185">로열티 멤버십 기간</span><span class="sxs-lookup"><span data-stu-id="5890e-185">Loyalty membership duration</span></span>
- <span data-ttu-id="5890e-186">마지막 구매 후 경과 시간</span><span class="sxs-lookup"><span data-stu-id="5890e-186">Time since last purchase</span></span>

<span data-ttu-id="5890e-187">다음 절차에서는 템플릿을 사용하여 새 측정값을 작성하는 단계를 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="5890e-188">대상 그룹 인사이트에서 **측정값** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="5890e-189">**신규** 를 선택하고 **템플릿 선택** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="템플릿이 강조 표시된 새 측정값을 생성할 때 드롭다운 메뉴의 스크린 샷.":::

1. <span data-ttu-id="5890e-191">필요에 맞는 템플릿을 찾아 **템플릿 선택** 을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="5890e-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="5890e-192">필요한 데이터를 검토하고 모든 데이터가 제자리에 있다면 **시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="5890e-193">**이름 편집** 창에서 측정 및 출력 엔터티의 이름을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="5890e-194">**완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-194">Select **Done**.</span></span>

1. <span data-ttu-id="5890e-195">**기간 설정** 섹션에서 사용할 데이터의 시간 프레임을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="5890e-196">새 측정값이 전체 데이터 집합를 포함하도록 하려면 **항상** 을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="5890e-196">Choose if you want the new measure to cover the entire data set by selecting **All time**.</span></span> <span data-ttu-id="5890e-197">또는 측정값이 **특정 기간** 에 초점을 맞추도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-197">Or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="템플릿에서 측정값을 구성할 때 기간 섹션을 보여주는 스크린 샷입니다.":::

1. <span data-ttu-id="5890e-199">다음 섹션에서 **데이터 추가** 를 선택하여 활동을 선택하고 *통합 활동* 엔터티의 해당 데이터를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-199">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="5890e-200">1/2단계: **활동 유형** 에서 사용할 엔터티의 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-200">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="5890e-201">**활동** 에서 매핑할 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-201">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="5890e-202">2/2단계: *통합 활동* 엔터티에서 공식에 필요한 구성 요소에 대한 특성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-202">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="5890e-203">예를 들어 평균 트랜잭션 값의 경우 트랜잭션 값을 나타내는 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-203">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="5890e-204">**활동 타임 스탬프** 의 경우 통합 활동 엔터티에서 활동의 날짜 및 시간을 나타내는 특성을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="5890e-204">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="5890e-205">데이터 매핑이 성공하면 상태가 **완료** 로 표시되며 매핑된 활동 및 특성의 이름을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-205">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="완료된 측정 템플릿 구성의 스크린 샷입니다.":::

1. <span data-ttu-id="5890e-207">이제 **실행** 을 선택하여 측정 결과를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-207">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="5890e-208">나중에 수정하려면 **임시보관함에 저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-208">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="5890e-209">측정 관리</span><span class="sxs-lookup"><span data-stu-id="5890e-209">Manage your measures</span></span>

<span data-ttu-id="5890e-210">측정값 목록은 **측정** 페이지에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-210">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="5890e-211">측정값 유형, 작성자, 생성 날짜, 현황 및 상태에 대한 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-211">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="5890e-212">목록에서 측정값을 선택하면 출력을 미리보고 .CSV 파일을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-212">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="5890e-213">모든 측정을 동시에 새로 고치려면 특정 측정을 선택하지 않고 **모두 새로 고침** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-213">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5890e-214">![단일 측정을 관리하기 위한 작업](media/measure-actions.png "단일 측정을 관리하기 위한 작업")</span><span class="sxs-lookup"><span data-stu-id="5890e-214">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="5890e-215">다음 옵션에 대한 목록에서 측정값을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="5890e-215">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="5890e-216">세부 사항을 보려면 측정 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-216">Select the measure name to see its details.</span></span>
- <span data-ttu-id="5890e-217">측정의 구성을 **편집** 합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-217">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="5890e-218">최신 데이터를 기반으로 측정값을 **새로 고침** 합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-218">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="5890e-219">측정 **이름 바꾸기** 를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-219">**Rename** the measure.</span></span>
- <span data-ttu-id="5890e-220">측정을 **삭제** 합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-220">**Delete** the measure.</span></span>
- <span data-ttu-id="5890e-221">**활성화** 또는 **비활성화** 합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-221">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="5890e-222">[예약된 새로 고침](system.md#schedule-tab) 중에는 비활성 측정값이 새로 고쳐지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-222">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="5890e-223">작업/프로세스 [상태에는 6가지 유형](system.md#status-types)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-223">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="5890e-224">또한 대부분의 프로세스는 [다른 다운스트림 프로세스에 의존](system.md#refresh-policies)합니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-224">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="5890e-225">프로세스 상태를 선택하여 전체 작업의 진행률에 대한 세부 사항을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-225">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="5890e-226">작업 중 하나를 선택한 다음 **자세히 보기** 참조를 선택하면, 처리 시간, 마지막 처리 날짜, 작업과 관련된 모든 오류 및 경고와 같은 추가 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-226">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="5890e-227">다음 단계</span><span class="sxs-lookup"><span data-stu-id="5890e-227">Next step</span></span>

<span data-ttu-id="5890e-228">기존 측정값을 사용하여 [고객 세그먼트](segments.md)를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5890e-228">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]