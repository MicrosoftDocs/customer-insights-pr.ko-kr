---
title: 데이터 통합 시 엔터티 병합
description: 엔터티를 병합하여 통합 고객 프로필을 만듭니다.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305654"
---
# <a name="merge-entities"></a><span data-ttu-id="ca1c6-103">엔터티 병합</span><span class="sxs-lookup"><span data-stu-id="ca1c6-103">Merge entities</span></span>

<span data-ttu-id="ca1c6-104">병합 단계는 데이터 통합 프로세스의 마지막 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="ca1c6-105">그 목적은 충돌하는 데이터를 조정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="ca1c6-106">충돌하는 데이터의 예로는 두 데이터 집합에 있지만 각 데이터 집합에 있는 고객 이름("Grant Marshall"과 "Grant Marshal") 또는 형식(617-803-091X와 617803091X)에 차이가 있는 휴대폰 번호 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="ca1c6-107">충돌하는 데이터 요소를 병합하는 작업은 특성별로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="통합 고객 프로필을 정의하는 병합된 필드가 있는 테이블을 보여주는 데이터 통합 프로세스의 병합 페이지입니다.":::

<span data-ttu-id="ca1c6-109">[일치 단계](match-entities.md)를 완료한 후 **통합** 페이지에서 **병합** 타일을 선택하여 병합 단계를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="ca1c6-110">시스템 권장 사항 검토</span><span class="sxs-lookup"><span data-stu-id="ca1c6-110">Review system recommendations</span></span>

<span data-ttu-id="ca1c6-111">**데이터** > **통합** > **병합** 에서 통합 고객 프로필 엔터티 내에서 병합할 특성을 선택하고 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="ca1c6-112">통합 고객 프로필은 데이터 통합 프로세스의 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="ca1c6-113">일부 특성은 시스템에서 자동으로 병합됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="ca1c6-114">자동으로 병합된 특성 중 하나에 포함된 특성을 보려면 표의 **고객 필드** 탭에서 병합된 특성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="ca1c6-115">병합된 특성을 구성하는 특성은 병합된 특성 아래 두 개의 새 행에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="ca1c6-116">병합된 필드 분리, 이름 변경, 제외 및 편집</span><span class="sxs-lookup"><span data-stu-id="ca1c6-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="ca1c6-117">통합 고객 프로필을 생성하기 위해 시스템이 병합된 특성을 처리하는 방법을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="ca1c6-118">**더 보기** 를 선택하고 변경할 항목을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="병합된 특성을 관리하기 위한 더 보기 드롭다운 메뉴의 옵션입니다.":::

<span data-ttu-id="ca1c6-120">자세한 내용은 다음 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="ca1c6-121">병합된 필드 분리</span><span class="sxs-lookup"><span data-stu-id="ca1c6-121">Separate merged fields</span></span>

<span data-ttu-id="ca1c6-122">병합된 필드를 분리하려면 테이블에서 특성을 찾으십시오.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="ca1c6-123">분리된 필드는 통합 고객 프로필에서 개별 데이터 요소로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="ca1c6-124">병합된 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="ca1c6-125">**더 보기** 를 선택하고 **필드 분리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="ca1c6-126">분리를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-126">Confirm the separation.</span></span>

1. <span data-ttu-id="ca1c6-127">**저장** 및 **실행** 을 선택하여 변경 사항을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="ca1c6-128">병합된 필드 이름 바꾸기</span><span class="sxs-lookup"><span data-stu-id="ca1c6-128">Rename merged fields</span></span>

<span data-ttu-id="ca1c6-129">병합된 특성의 표시 이름을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="ca1c6-130">출력 엔터티의 이름은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="ca1c6-131">병합된 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="ca1c6-132">**더 보기** 를 선택하고 **이름 바꾸기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="ca1c6-133">변경된 표시 이름을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="ca1c6-134">**저장** 및 **실행** 을 선택하여 변경 사항을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="ca1c6-135">병합된 필드 제외</span><span class="sxs-lookup"><span data-stu-id="ca1c6-135">Exclude merged fields</span></span>

<span data-ttu-id="ca1c6-136">통합 고객 프로필에서 특성을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="ca1c6-137">필드가 다른 프로세스(예: 세그먼트)에서 사용되는 경우 고객 프로필에서 제외하기 전에 이러한 프로세스에서 제거하십시오.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="ca1c6-138">병합된 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="ca1c6-139">**더 보기** 를 선택하고 **제외하기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="ca1c6-140">제외를 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="ca1c6-141">**저장** 및 **실행** 을 선택하여 변경 사항을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="ca1c6-142">**병합** 페이지에서 **제외된 필드** 를 선택하여 모든 필드 목록을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="ca1c6-143">이 창에서 제외된 필드를 다시 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="ca1c6-144">수동으로 필드 결합</span><span class="sxs-lookup"><span data-stu-id="ca1c6-144">Manually combine fields</span></span>

<span data-ttu-id="ca1c6-145">병합된 특성을 수동으로 지정하십시오.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="ca1c6-146">**병합** 페이지에서 **필드 결합** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="ca1c6-147">**이름** 및 **출력 필드 이름** 을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="ca1c6-148">추가할 필드를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-148">Choose a field to add.</span></span> <span data-ttu-id="ca1c6-149">더 많은 필드를 결합하려면 **필드 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="ca1c6-150">제외를 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="ca1c6-151">**저장** 및 **실행** 을 선택하여 변경 사항을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="ca1c6-152">필드의 순서 변경</span><span class="sxs-lookup"><span data-stu-id="ca1c6-152">Change the order of fields</span></span>

<span data-ttu-id="ca1c6-153">일부 엔터티에는 다른 엔터티보다 자세한 내용이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-153">Some entities contain more details than others.</span></span> <span data-ttu-id="ca1c6-154">엔터티에 필드에 대한 최신 데이터가 포함된 경우 값을 병합할 때 다른 엔터티보다 우선 순위로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="ca1c6-155">병합된 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="ca1c6-156">**더 보기** 를 선택하고 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="ca1c6-157">**필드 결합** 창에서 **위/아래로 이동** 을 선택하여 순서를 설정하거나 원하는 위치로 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="ca1c6-158">변경을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-158">Confirm the change.</span></span>

1. <span data-ttu-id="ca1c6-159">**저장** 및 **실행** 을 선택하여 변경 사항을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="ca1c6-160">병합 실행</span><span class="sxs-lookup"><span data-stu-id="ca1c6-160">Run your merge</span></span>

<span data-ttu-id="ca1c6-161">특성을 수동으로 병합하든 시스템에서 특성을 병합하도록 허용하든 언제든지 병합을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="ca1c6-162">**병합** 페이지에서 **실행** 을 선택하여 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ca1c6-163">![데이터 병합 저장 및 실행](media/configure-data-merge-save-run.png "데이터 병합 저장 및 실행")</span><span class="sxs-lookup"><span data-stu-id="ca1c6-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="ca1c6-164">통합 고객 엔터티에 반영된 출력만 보려면 **병합만 실행** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="ca1c6-165">다운스트림 프로세스는 [지정된 새로 고침 일정](system.md#schedule-tab)에 따라 새로 고쳐집니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="ca1c6-166">**병합 및 다운스트림 프로세스 실행** 을 선택하여 변경 사항으로 시스템을 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="ca1c6-167">보강, 세그먼트 및 측정을 포함한 모든 프로세스가 자동으로 다시 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="ca1c6-168">모든 다운스트림 프로세스가 완료되면 고객 프로필에 변경 사항이 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="ca1c6-169">추가 변경을 수행하고 단계를 다시 실행하기 위해 진행중인 병합을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="ca1c6-170">**새로 고침 중...** 을 선택하고 나타나는 측면 창에서 **작업 취소** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="ca1c6-171">작업/프로세스 [상태에는 6가지 유형](system.md#status-types)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="ca1c6-172">또한 대부분의 프로세스는 [다른 다운스트림 프로세스에 의존](system.md#refresh-policies)합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="ca1c6-173">프로세스 상태를 선택하여 전체 작업의 진행률에 대한 세부 사항을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="ca1c6-174">작업 중 하나를 선택한 다음 **자세히 보기** 참조를 선택하면, 처리 시간, 마지막 처리 날짜, 작업과 관련된 모든 오류 및 경고와 같은 추가 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="ca1c6-175">다음 단계</span><span class="sxs-lookup"><span data-stu-id="ca1c6-175">Next Step</span></span>

<span data-ttu-id="ca1c6-176">고객에 대한 더 많은 통찰력을 얻기 위해 [활동](activities.md), [보강](enrichment-hub.md) 또는 [관계](relationships.md)를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="ca1c6-177">활동, 보강 또는 세그먼트를 이미 구성한 경우 최신 고객 데이터를 사용하도록 자동으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca1c6-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
