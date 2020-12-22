---
title: 측정값 만들기 및 편집
description: 특정 비즈니스 영역의 성과를 분석하고 반영할 고객 관련 조치를 정의합니다.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406306"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="7173f-103">측정 정의 및 관리</span><span class="sxs-lookup"><span data-stu-id="7173f-103">Define and manage measures</span></span>

<span data-ttu-id="7173f-104">**측정값** 은 특정 비즈니스 영역의 성과 및 상태를 반영하는 핵심 성과 지표(KPI)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="7173f-105">대상 그룹 인사이트는 측정값을 수동으로 코딩하거나 유효성을 검사할 필요가 없는 쿼리 빌더를 사용하여 다양한 유형의 측정값을 구축할 수 있는 직관적인 경험을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="7173f-106">**홈** 페이지에서 비즈니스 측정값을 추적하고, **고객 카드** 의 특정 고객에 대한 측정값을 확인하고, 측정값을 사용하여 **세그먼트** 페이지에서 고객 세그먼트를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="7173f-107">측정값 만들기</span><span class="sxs-lookup"><span data-stu-id="7173f-107">Create a measure</span></span>

<span data-ttu-id="7173f-108">이 섹션에서는 처음부터 측정값을 만드는 방법을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="7173f-109">거객 엔터티를 통해 연결된 여러 데이터 원본의 데이터로 측정값을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="7173f-110">약간의 [서비스 제한](service-limits.md)이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="7173f-111">대상 그룹 인사이트에서 **측정값** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="7173f-112">**새 측정값** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-112">Select **New measure**.</span></span>

3. <span data-ttu-id="7173f-113">측정값 **유형** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="7173f-114">**고객 특성**: 고객의 점수, 값 또는 상태를 반영하는 고객당 단일 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="7173f-115">고객 특성은 **Customer_Measure** 라는 새 시스템 생성 엔터티에서 특성으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="7173f-116">**고객 측정값**: 선택한 측정 기준별로 분석된 고객 행동에 대한 인사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="7173f-117">각 측정값에 대해 새 엔터티가 생성되며 잠재적으로 고객당 여러 레코드가 생성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="7173f-118">**비즈니스 측정값**: 비즈니스 성과와 비즈니스 상태를 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="7173f-119">비즈니스 측정값에는 **홈** 페이지에 표시되는 숫자 출력 또는 **엔터티** 페이지에서 찾은 새 엔터티의 두 가지 출력이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="7173f-120">**이름** 과 선택적 **표시 이름** 을 제공한 후 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="7173f-121">**엔터티** 섹션의 드롭다운 목록에서 첫 번째 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="7173f-122">이 시점에서 측정값 정의의 일부로 추가 엔터티가 필요한지 여부를 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7173f-123">![측정 정의](media/measure-definition.png "측정 정의")</span><span class="sxs-lookup"><span data-stu-id="7173f-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="7173f-124">엔터티를 더 추가하려면 **엔터티 추가** 를 선택하고 측정값에 사용할 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7173f-125">시작 엔터티와 관계가 있는 엔터티만 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="7173f-126">관계를 정의하는 자세한 내용은 [관계](relationships.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7173f-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="7173f-127">선택적으로 변수를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="7173f-128">**변수** 섹션에서 **새 변수** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="7173f-129">변수는 선택한 각 레코드에 대한 계산입니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="7173f-130">예를 들어 각 고객 레코드에 대해 POS(Point of Sale) 및 온라인 판매를 합산합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="7173f-131">변수의 **이름** 을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="7173f-132">**식** 영역에서 계산을 시작할 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="7173f-133">계산에 포함할 필드를 더 선택하면서 **식** 영역에 식을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7173f-134">현재는 산술식만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="7173f-135">또한 다른 [엔터티 경로](relationships.md)의 엔터티에 대해서는 변수 계산이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="7173f-136">**완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-136">Select **Done**.</span></span>

11. <span data-ttu-id="7173f-137">**측정값 정의** 섹션에서 선택한 엔터티와 계산된 변수가 새 측정값 엔터티 또는 특성에 집계되는 방법을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="7173f-138">**새 차원** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-138">Select **New dimension**.</span></span> <span data-ttu-id="7173f-139">차원을 함수별 *그룹* 으로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="7173f-140">측정값 엔터티 또는 특성의 데이터 출력은 정의된 모든 차원으로 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7173f-141">![집계 주기 선택](media/measures-businessreport-measure-definition2.png "집계 주기 선택")</span><span class="sxs-lookup"><span data-stu-id="7173f-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="7173f-142">차원 정의의 일부로 다음 정보를 선택하거나 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="7173f-143">**엔터티**: 측정값 엔터티를 정의하는 경우 하나 이상의 특성을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="7173f-144">측정값 특성을 정의하는 경우 기본적으로 하나의 특성만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="7173f-145">이 선택은 해당 특성을 포함하는 엔터티를 선택하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="7173f-146">**필드**: 측정값 엔터티 또는 특성에 포함할 특정 특성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="7173f-147">**버킷**: 일별, 월별 또는 연간 기준으로 데이터를 집계할지 여부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="7173f-148">날짜 유형 속성을 선택한 경우에만 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="7173f-149">**(으)로**: 새 필드의 이름을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="7173f-150">**표시 이름**: 필드의 표시 이름을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7173f-151">측정값에 측정 기준을 더 추가하지 않는 한 비즈니스 측정값은 단일 숫자 엔터티로 저장되며 **홈** 페이지에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="7173f-152">차원을 더 추가하면 측정값이 **홈** 페이지에 표시되지 *않습니다*.</span><span class="sxs-lookup"><span data-stu-id="7173f-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="7173f-153">선택적으로 집계 함수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="7173f-154">만드는 모든 집계는 측정값 엔터티 또는 특성 내에 새 값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="7173f-155">지원되는 집계 함수는 **최소**, **최대**, **평균**, **중앙값**, **합계**, **고고유 개수**, **첫 번째**(차원 값의 첫 번째 레코드 를 사용함) 및 **마지막**(마지막 레코드가 차원 값에 추가됨)입니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="7173f-156">**저장** 을 선택하여 측정값에 변경 내용을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="7173f-157">측정 관리</span><span class="sxs-lookup"><span data-stu-id="7173f-157">Manage your measures</span></span>

<span data-ttu-id="7173f-158">측정값을 하나 이상 생성한 후에는 측정값 목록이 **측정값** 페이지에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="7173f-159">측정값 유형, 작성자, 생성 날짜 및 시간, 마지막 편집 날짜 및 시간, 상태(측정값이 활성 상태인지 비활성 상태인지 여부) 및 마지막 새로 고침 날짜 및 시간에 대한 정보를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="7173f-160">목록에서 측정을 선택하면 해당 출력의 미리보기를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="7173f-161">모든 측정을 동시에 새로 고치려면 특정 측정을 선택하지 않고 **모두 새로 고침** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7173f-162">![단일 측정을 관리하기 위한 작업](media/measure-actions.png "단일 측정을 관리하기 위한 작업")</span><span class="sxs-lookup"><span data-stu-id="7173f-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="7173f-163">또는 목록에서 측정을 선택하고 다음 작업 중 하나를 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="7173f-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="7173f-164">세부 사항을 보려면 측정 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="7173f-165">측정의 구성을 **편집** 합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="7173f-166">측정 **이름 바꾸기** 를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-166">**Rename** the measure.</span></span>
- <span data-ttu-id="7173f-167">측정을 **삭제** 합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-167">**Delete** the measure.</span></span>
- <span data-ttu-id="7173f-168">줄임표(...)를 선택한 다음 **새로 고침** 을 선택하여 측정에 대한 새로 고침 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="7173f-169">줄임표(...)를 선택한 다음 **다운로드** 를 선택하여 측정의 .CSV 파일을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="7173f-170">작업/프로세스 [상태에는 6가지 유형](system.md#status-types)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="7173f-171">또한 대부분의 프로세스는 [다른 다운스트림 프로세스에 의존](system.md#refresh-policies)합니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="7173f-172">프로세스 상태를 선택하여 전체 작업의 진행률에 대한 세부 사항을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="7173f-173">작업 중 하나를 선택한 다음 **자세히 보기** 참조를 선택하면, 처리 시간, 마지막 처리 날짜, 작업과 관련된 모든 오류 및 경고와 같은 추가 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="7173f-174">다음 단계</span><span class="sxs-lookup"><span data-stu-id="7173f-174">Next step</span></span>

<span data-ttu-id="7173f-175">기존 측정값을 사용하여 **세그먼트** 페이지에서 첫 번째 고객 세그먼트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7173f-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="7173f-176">자세한 내용은 [세그먼트](segments.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7173f-176">For more information, see [Segments](segments.md).</span></span>
