---
title: 데이터 통합 시 엔터티 병합
description: 엔터티를 병합하여 통합 고객 프로필을 만듭니다.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 737c593353878a5e322488d00de5dc5db5befda9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597841"
---
# <a name="merge-entities"></a><span data-ttu-id="e8cf7-103">엔터티 병합</span><span class="sxs-lookup"><span data-stu-id="e8cf7-103">Merge entities</span></span>

<span data-ttu-id="e8cf7-104">병합 단계는 데이터 통합 프로세스의 마지막 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="e8cf7-105">그 목적은 충돌하는 데이터를 조정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="e8cf7-106">충돌하는 데이터의 예로는 두 데이터 집합에 있지만 각 데이터 집합에 있는 고객 이름("Grant Marshall"과 "Grant Marshal") 또는 형식(617-803-091X와 617803091X)에 차이가 있는 휴대폰 번호 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="e8cf7-107">충돌하는 데이터 요소를 병합하는 작업은 특성별로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="e8cf7-108">[일치 단계](match-entities.md)를 완료한 후 **통합** 페이지에서 **병합** 타일을 선택하여 병합 단계를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="e8cf7-109">시스템 권장 사항 검토</span><span class="sxs-lookup"><span data-stu-id="e8cf7-109">Review system recommendations</span></span>

<span data-ttu-id="e8cf7-110">**병합** 페이지에서 통합 고객 프로필 엔터티(구성 프로세스의 결과) 내에서 병합할 특성을 선택하고 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="e8cf7-111">일부 특성은 시스템에서 자동으로 병합됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="e8cf7-112">병합된 특성 보기</span><span class="sxs-lookup"><span data-stu-id="e8cf7-112">View merged attributes</span></span>

<span data-ttu-id="e8cf7-113">자동으로 병합된 특성 중 하나에 포함된 특성을 보려면 병합된 특성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="e8cf7-114">병합된 특성을 구성하는 두 특성이 병합된 특성 아래 두 개의 새 행에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e8cf7-115">![병합된 특성 선택](media/configure-data-merge-profile-attributes.png "병합된 특성 선택")</span><span class="sxs-lookup"><span data-stu-id="e8cf7-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="e8cf7-116">병합된 특성 분리</span><span class="sxs-lookup"><span data-stu-id="e8cf7-116">Separate merged attributes</span></span>

<span data-ttu-id="e8cf7-117">자동으로 병합된 특성을 분리하거나 병합 해제하려면 **프로필 특성** 표에서 특성을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="e8cf7-118">줄임표(...) 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="e8cf7-119">드롭다운 목록에서 **분리 필드** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="e8cf7-120">병합된 특성 제거</span><span class="sxs-lookup"><span data-stu-id="e8cf7-120">Remove merged attributes</span></span>

<span data-ttu-id="e8cf7-121">최종 고객 프로필 엔터티에서 특성을 제외하려면 **프로필 특성** 표에서 특성을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="e8cf7-122">줄임표(...) 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="e8cf7-123">드롭다운 목록에서 **병합하지 않음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="e8cf7-124">특성이 **고객 레코드에서 제거됨** 섹션으로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="e8cf7-125">병합된 특성을 수동으로 추가</span><span class="sxs-lookup"><span data-stu-id="e8cf7-125">Manually add a merged attribute</span></span>

<span data-ttu-id="e8cf7-126">병합된 특성을 추가하려면 **병합** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="e8cf7-127">**병합된 특성 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="e8cf7-128">나중에 **병합** 페이지에서 이름을 식별할 **이름** 을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="e8cf7-129">선택적으로 통합 고객 프로필 엔터티에 표시할 **표시 이름** 을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="e8cf7-130">일치하는 엔터티에서 병합할 특성을 선택하려면 **중복 특성 선택** 을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="e8cf7-131">특성을 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="e8cf7-132">**중요도 순위** 를 설정하여 한 특성의 우선 순위를 다른 특성보다 우선으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="e8cf7-133">예를 들어 *WebAccountCSV* 엔터티에 *전체 이름* 특성에 대한 가장 정확한 데이터가 포함된 경우 *WebAccountCSV* 를 선택하여 *ContactCSV* 보다 이 엔터티의 우선 순위를 높게 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="e8cf7-134">결과적으로 *WebAccountCSV* 는 첫 번째 우선 순위로 이동하고 *ContactCSV* 는 *전체 이름* 특성에 대한 값을 끌어낼 때 두 번째 우선 순위로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="e8cf7-135">병합 실행</span><span class="sxs-lookup"><span data-stu-id="e8cf7-135">Run your merge</span></span>

<span data-ttu-id="e8cf7-136">특성을 수동으로 병합하든 시스템에서 특성을 병합하도록 허용하든 언제든지 병합을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="e8cf7-137">**병합** 페이지에서 **실행** 을 선택하여 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e8cf7-138">![데이터 병합 저장 및 실행](media/configure-data-merge-save-run.png "데이터 병합 저장 및 실행")</span><span class="sxs-lookup"><span data-stu-id="e8cf7-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="e8cf7-139">추가 변경을 수행하고 단계를 다시 실행하기 위해 진행 중인 병합을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="e8cf7-140">**새로 고침 중...** 을 선택하고 나타나는 측면 창에서 **작업 취소** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="e8cf7-141">**새로 고침 중 ...** 텍스트가 **성공** 으로 변경된 후, 병합은 정의한 정책에 따라 데이터의 모순을 완료하고 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="e8cf7-142">병합 및 병합되지 않은 특성은 통합 프로필 엔터티에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="e8cf7-143">제외된 특성은 통합 프로필 엔터티에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="e8cf7-144">처음으로 병합을 성공적으로 실행하지 않은 경우 보강, 세분화 및 측정을 포함한 모든 다운스트림 프로세스가 자동으로 다시 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="e8cf7-145">모든 다운스트림 프로세스가 재실행된 후 고객 프로필은 변경 사항을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="e8cf7-146">작업/프로세스 [상태에는 6가지 유형](system.md#status-types)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="e8cf7-147">또한 대부분의 프로세스는 [다른 다운스트림 프로세스에 의존](system.md#refresh-policies)합니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="e8cf7-148">프로세스 상태를 선택하여 전체 작업의 진행률에 대한 세부 사항을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="e8cf7-149">작업 중 하나를 선택한 다음 **자세히 보기** 참조를 선택하면, 처리 시간, 마지막 처리 날짜, 작업과 관련된 모든 오류 및 경고와 같은 추가 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="e8cf7-150">다음 단계</span><span class="sxs-lookup"><span data-stu-id="e8cf7-150">Next Step</span></span>

<span data-ttu-id="e8cf7-151">고객에 대한 더 많은 통찰력을 얻기 위해 [활동](activities.md), [보강](enrichment-microsoft-graph.md) 또는 [관계](relationships.md)를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="e8cf7-152">활동, 보강 또는 관계를 이미 구성했거나 세그먼트를 정의한 경우 최신 고객 데이터를 사용하도록 세그먼트가 자동으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8cf7-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]