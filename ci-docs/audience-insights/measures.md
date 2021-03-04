---
title: 측정값 만들기 및 관리
description: 비즈니스 성과를 분석하고 반영하기 위한 측정값을 정의합니다.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269936"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="da8e7-103">측정 정의 및 관리</span><span class="sxs-lookup"><span data-stu-id="da8e7-103">Define and manage measures</span></span>

<span data-ttu-id="da8e7-104">측정값은 [통합 프로필](data-unification.md)에서 관련 값을 검색하여 고객 행동 및 비즈니스 성과를 더 잘 이해하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="da8e7-105">예를 들어, 비즈니스에서 *고객당 총 지출* 을 확인하여 개별 고객의 구매 기록을 파악하고자 합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="da8e7-106">또는 *회사의 총 매출* 을 측정하여 전체 비즈니스의 총 수익을 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="da8e7-107">측정값은 다양한 연산자와 간단한 매핑 옵션이 있는 데이터 쿼리 플랫폼인 측정값 빌더를 사용하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="da8e7-108">이를 통해 데이터를 필터링하고 결과를 그룹화하고 [엔터티 관계 경로](relationships.md)를 감지하고 출력을 미리 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="da8e7-109">측정값 빌더를 사용하여 고객 데이터를 쿼리하고 인사이트를 추출하여 비즈니스 활동을 계획합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="da8e7-110">예를 들어 *고객당 총 지출* 및 *고객당 총 수익* 의 측정값을 생성하면 지출이 많고 수익이 높은 고객 그룹을 식별하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="da8e7-111">[세그먼트 생성](segments.md)을 통해 차선책을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="da8e7-112">측정값 만들기</span><span class="sxs-lookup"><span data-stu-id="da8e7-112">Create a measure</span></span>

<span data-ttu-id="da8e7-113">이 섹션에서는 새 측정값을 만드는 과정을 처음부터 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="da8e7-114">고객 엔터티와 연결하도록 설정된 관계가 있는 데이터 엔터티의 데이터 특성을 사용하여 측정값을 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="da8e7-115">대상 그룹 인사이트에서 **측정값** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="da8e7-116">**새로 만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-116">Select **New**.</span></span>

1. <span data-ttu-id="da8e7-117">**이름 편집** 을 선택하고 측정값에 대한 **이름** 을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="da8e7-118">새 측정값 구성에 두 개의 필드(예: CustomerID 및 계산)만 있는 경우 출력은 Customer_Measure라는 시스템 생성 엔터티에 새 열로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="da8e7-119">그리고 통합 고객 프로필에서 측정값의 값을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="da8e7-120">다른 측정값은 자체 엔터티를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="da8e7-121">구성 영역의 **함수 선택** 드롭 다운 메뉴에서 집계 함수를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="da8e7-122">집계 함수에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="da8e7-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="da8e7-123">**Sum**</span></span>
   - <span data-ttu-id="da8e7-124">**평균**</span><span class="sxs-lookup"><span data-stu-id="da8e7-124">**Average**</span></span>
   - <span data-ttu-id="da8e7-125">**수**</span><span class="sxs-lookup"><span data-stu-id="da8e7-125">**Count**</span></span>
   - <span data-ttu-id="da8e7-126">**고유 개수**</span><span class="sxs-lookup"><span data-stu-id="da8e7-126">**Count Unique**</span></span>
   - <span data-ttu-id="da8e7-127">**최대**</span><span class="sxs-lookup"><span data-stu-id="da8e7-127">**Max**</span></span>
   - <span data-ttu-id="da8e7-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="da8e7-128">**Min**</span></span>
   - <span data-ttu-id="da8e7-129">**첫 번째**: 데이터 레코드의 첫 번째 값 사용</span><span class="sxs-lookup"><span data-stu-id="da8e7-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="da8e7-130">**마지막**: 데이터 레코드에 추가된 마지막 값 사용</span><span class="sxs-lookup"><span data-stu-id="da8e7-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="측정값 계산을 위한 연산자입니다.":::

1. <span data-ttu-id="da8e7-132">**특성 추가** 를 선택하여 이 측정값을 만드는 데 필요한 데이터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="da8e7-133">**특성** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="da8e7-134">데이터 엔터티: 측정하려는 특성이 포함된 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="da8e7-135">데이터 특성: 측정값을 계산하기 위해 집계 함수에서 사용할 특성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="da8e7-136">한번에 하나의 특성만 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="da8e7-137">**측정** 탭을 선택하여 기존 측정에서 데이터 속성을 선택할 수도 있습니다. 또는 엔터티 또는 측정값 이름을 검색 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="da8e7-138">**추가** 를 선택하여 측정값에 선택한 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="계산에 사용할 특성을 선택합니다.":::

1. <span data-ttu-id="da8e7-140">더 복잡한 측정값을 빌드하기 위해 측정값 함수에 더 많은 특성을 추가하거나 수학 연산자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="수학 연산자를 사용하여 복잡한 측정값을 만듭니다.":::

1. <span data-ttu-id="da8e7-142">필터를 추가하려면 구성 영역에서 **필터** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="da8e7-143">**필터** 창의 **속성 추가** 섹션에서 필터를 만드는 데 사용할 특성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="da8e7-144">선택한 모든 특성에 대한 필터를 정의하도록 필터 연산자를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="da8e7-145">**적용** 을 선택하여 측정값에 필터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="da8e7-146">차원을 추가하려면 구성 영역에서 **차원** 을 ​​선택합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="da8e7-147">차원은 측정값 출력 엔터티에서 열로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="da8e7-148">**차원 편집** 을 선택하여 측정값을 그룹화하려는 데이터 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="da8e7-149">예: 도시 또는 성별.</span><span class="sxs-lookup"><span data-stu-id="da8e7-149">For example, city or gender.</span></span> <span data-ttu-id="da8e7-150">기본적으로 *고객 수준 측정값* 을 만들기 위해 *CustomerID* 차원이 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="da8e7-151">*비즈니스 수준 측정값* 을 만들려는 경우 기본 차원을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="da8e7-152">**완료** 를 선택하여 측정값에 차원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="da8e7-153">매핑한 데이터 엔터티와 고객 엔터티 사이에 여러 경로가 있는 경우 식별된 [엔티티 관계 경로](relationships.md) 중 하나를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-153">If there are multiple paths between the data entity you mapped and the Customer entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="da8e7-154">측정 결과는 선택한 경로에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-154">Measure results can vary depending on the selected path.</span></span>
   1. <span data-ttu-id="da8e7-155">**데이터 선호 설정** 을 선택하여 측정값을 식별하는 데 사용해야 하는 엔터티 경로를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span>
   1. <span data-ttu-id="da8e7-156">**완료** 를 선택하여 선택 사항을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-156">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="측정값에 대한 엔터티 경로를 선택합니다.":::

1. <span data-ttu-id="da8e7-158">측정값에 대한 계산을 더 추가하려면 **새로운 계산** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-158">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="da8e7-159">새로운 계산에는 동일한 엔터티 경로에 있는 엔터티만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-159">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="da8e7-160">더 많은 계산이 측정값 출력 엔터티에 새 열로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-160">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="da8e7-161">계산에서 **...** 을 선택하여 측정값에서 계산을 **복제**, **이름 바꾸기** 또는 **제거** 합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-161">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="da8e7-162">**미리 보기** 영역에는 필터 및 차원을 포함하여 측정값 출력 엔터티의 데이터 스키마가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-162">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="da8e7-163">미리 보기는 구성 변경에 동적으로 반응합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-163">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="da8e7-164">**실행** 을 선택하여 구성된 측정값에 대한 결과를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-164">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="da8e7-165">현재 구성을 유지하고 나중에 측정을 실행하려면 **저장 및 닫기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-165">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="da8e7-166">**측정값** 으로 이동하여 목록에서 새로 만들어진 측정값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-166">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="da8e7-167">측정 관리</span><span class="sxs-lookup"><span data-stu-id="da8e7-167">Manage your measures</span></span>

<span data-ttu-id="da8e7-168">[측정값 만들기](#create-a-measure)를 실행한 이후에 **측정값** 페이지에서 측정값 목록을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-168">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="da8e7-169">측정값 유형, 작성자, 생성 날짜, 현황 및 상태에 대한 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-169">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="da8e7-170">목록에서 측정값을 선택하면 출력을 미리보고 .CSV 파일을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-170">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="da8e7-171">모든 측정을 동시에 새로 고치려면 특정 측정을 선택하지 않고 **모두 새로 고침** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-171">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="da8e7-172">![단일 측정을 관리하기 위한 작업](media/measure-actions.png "단일 측정을 관리하기 위한 작업")</span><span class="sxs-lookup"><span data-stu-id="da8e7-172">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="da8e7-173">다음 옵션에 대한 목록에서 측정값을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="da8e7-173">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="da8e7-174">세부 사항을 보려면 측정 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-174">Select the measure name to see its details.</span></span>
- <span data-ttu-id="da8e7-175">측정의 구성을 **편집** 합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-175">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="da8e7-176">최신 데이터를 기반으로 측정값을 **새로 고침** 합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-176">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="da8e7-177">측정 **이름 바꾸기** 를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-177">**Rename** the measure.</span></span>
- <span data-ttu-id="da8e7-178">측정을 **삭제** 합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-178">**Delete** the measure.</span></span>
- <span data-ttu-id="da8e7-179">**활성화** 또는 **비활성화** 합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-179">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="da8e7-180">[예약된 새로 고침](system.md#schedule-tab) 중에는 비활성 측정값이 새로 고쳐지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-180">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="da8e7-181">작업/프로세스 [상태에는 6가지 유형](system.md#status-types)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-181">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="da8e7-182">또한 대부분의 프로세스는 [다른 다운스트림 프로세스에 의존](system.md#refresh-policies)합니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-182">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="da8e7-183">프로세스 상태를 선택하여 전체 작업의 진행률에 대한 세부 사항을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-183">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="da8e7-184">작업 중 하나를 선택한 다음 **자세히 보기** 참조를 선택하면, 처리 시간, 마지막 처리 날짜, 작업과 관련된 모든 오류 및 경고와 같은 추가 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-184">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="da8e7-185">다음 단계</span><span class="sxs-lookup"><span data-stu-id="da8e7-185">Next step</span></span>

<span data-ttu-id="da8e7-186">기존 측정값을 사용하여 [고객 세그먼트](segments.md)를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da8e7-186">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]