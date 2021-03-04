---
title: 세그먼트 만들기 및 관리
description: 다양한 특성에 따라 그룹화할 고객 세그먼트를 만듭니다.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: a1308f07ac3ba7d4b09931bab3d19b6dfaf479ee
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270364"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="c66f2-103">세그먼트 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="c66f2-103">Create and manage segments</span></span>

<span data-ttu-id="c66f2-104">세그먼트를 사용하면 인구 통계, 트랜잭션 또는 행동 특성을 기반으로 고객을 그룹화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="c66f2-105">세그먼트를 사용하여 판촉 캠페인, 판매 활동 및 고객 지원 조치를 대상으로 비즈니스 목표를 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="c66f2-106">고객 프로필 엔터티 및 관련 엔터티에 대한 복잡한 필터를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="c66f2-107">처리 후 각 세그먼트는 내보내고 조치를 취할 수 있는 고객 레코드 집합을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="c66f2-108">약간의 [서비스 제한](service-limits.md)이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="c66f2-109">달리 명시하지 않는 한 모든 세그먼트는 **동적 세그먼트** 이며 반복 일정에 따라 새로 고쳐집니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="c66f2-110">다음 예는 분할 기능을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="c66f2-111">지난 90일 동안 최소 $500의 상품을 주문 *하고* 에스컬레이션된 고객 서비스 요청에 참여한 고객을 위한 세그먼트를 정의했습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c66f2-112">![여러 그룹](media/segmentation-group1-2.png "여러 그룹")</span><span class="sxs-lookup"><span data-stu-id="c66f2-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="c66f2-113">새 세그먼트 만들기</span><span class="sxs-lookup"><span data-stu-id="c66f2-113">Create a new segment</span></span>

<span data-ttu-id="c66f2-114">세그먼트는 **세그먼트** 페이지에서 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="c66f2-115">대상 그룹 인사이트에서 **세그먼트** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="c66f2-116">**새로 만들기** > **빈 세그먼트** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="c66f2-117">**새 세그먼트** 창에서 세그먼트 유형을 선택하고 **이름** 을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="c66f2-118">선택적으로 세그먼트를 식별하는 데 도움이 되는 표시 이름 및 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="c66f2-119">**다음** 을 선택하여 그룹을 정의하는 **세그먼트 빌더** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="c66f2-120">그룹은 고객 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="c66f2-121">분류하려는 속성이 포함된 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="c66f2-122">분류 기준을 지정할 속성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="c66f2-123">이 특성은 숫자, 문자열, 날짜 또는 부울의 네 가지 값 유형 중 하나를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="c66f2-124">선택한 특성에 대한 연산자 및 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c66f2-125">![사용자 지정 그룹 필터](media/customer-group-numbers.png "고객 그룹 필터")</span><span class="sxs-lookup"><span data-stu-id="c66f2-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="c66f2-126">번호</span><span class="sxs-lookup"><span data-stu-id="c66f2-126">Number</span></span> |<span data-ttu-id="c66f2-127">정의</span><span class="sxs-lookup"><span data-stu-id="c66f2-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="c66f2-128">1</span><span class="sxs-lookup"><span data-stu-id="c66f2-128">1</span></span>     |<span data-ttu-id="c66f2-129">Entity</span><span class="sxs-lookup"><span data-stu-id="c66f2-129">Entity</span></span>          |
   |<span data-ttu-id="c66f2-130">2</span><span class="sxs-lookup"><span data-stu-id="c66f2-130">2</span></span>     |<span data-ttu-id="c66f2-131">특성</span><span class="sxs-lookup"><span data-stu-id="c66f2-131">Attribute</span></span>          |
   |<span data-ttu-id="c66f2-132">3</span><span class="sxs-lookup"><span data-stu-id="c66f2-132">3</span></span>    |<span data-ttu-id="c66f2-133">연산자</span><span class="sxs-lookup"><span data-stu-id="c66f2-133">Operator</span></span>         |
   |<span data-ttu-id="c66f2-134">4</span><span class="sxs-lookup"><span data-stu-id="c66f2-134">4</span></span>    |<span data-ttu-id="c66f2-135">값</span><span class="sxs-lookup"><span data-stu-id="c66f2-135">Value</span></span>         |

8. <span data-ttu-id="c66f2-136">엔터티가 [관계](relationships.md)를 통해 통합 고객 엔터티에 연결된 경우 유효한 세그먼트를 작성하기 위해 관계 경로를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="c66f2-137">드롭다운에서 **고객: CustomerInsights** 엔터티를 선택할 수 있을 때까지 관계 경로에서 엔터티를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="c66f2-138">그런 다음 각 조건에 대해 **모든 레코드** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c66f2-139">![세그먼트 작성 중 관계 경로](media/segments-multiple-relationships.png "세그먼트 작성 중 관계 경로")</span><span class="sxs-lookup"><span data-stu-id="c66f2-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="c66f2-140">**저장** 을 선택하여 세그먼트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="c66f2-141">모든 요구 사항이 검증되면 세그먼트가 저장되고 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="c66f2-142">그렇지 않으면 초안으로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="c66f2-143">**세그먼트로 돌아가기** 를 선택하여 **세그먼트** 페이지로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="c66f2-144">기존 세그먼트 관리</span><span class="sxs-lookup"><span data-stu-id="c66f2-144">Manage existing segments</span></span>

<span data-ttu-id="c66f2-145">**세그먼트** 페이지에서 저장된 모든 세그먼트를 보고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="c66f2-146">각 세그먼트는 세그먼트에 대한 추가 정보가 포함된 행으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="c66f2-147">열 제목을 선택하여 열의 세그먼트를 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="c66f2-148">오른쪽 상단에 있는 **검색** 상자를 사용하여 세그먼트를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c66f2-149">![기존 세그먼트를 관리하는 옵션](media/segments-selected-segment.png "기존 세그먼트를 관리하는 옵션")</span><span class="sxs-lookup"><span data-stu-id="c66f2-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="c66f2-150">세그먼트를 선택하면 다음 작업을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="c66f2-151">**보기**: 구성원 수 추세를 포함한 세그먼트 세부 사항 및 세그먼트 구성원의 미리보기를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="c66f2-152">**편집**: 속성을 변경할 세그먼트를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="c66f2-153">**새로 고침**: 최신 데이터를 포함하도록 세그먼트를 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="c66f2-154">**활성화** 또는 **비활성화**: 세그먼트를 활성화하거나 비활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="c66f2-155">세그먼트에는 활성 또는 비활성의 두 가지 상태가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="c66f2-156">이러한 상태는 세그먼트를 편집할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="c66f2-157">비활성 세그먼트의 경우 세그먼트 정의가 존재하지만 아직 고객이 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="c66f2-158">세그먼트를 활성화하면 상태가 '비활성'에서 '활성'으로 변경되고 세그먼트 정의와 일치하는 고객을 찾기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="c66f2-159">[예약된 새로 고침](system.md#schedule-tab)이 구성되었고 비활성 세그먼트에 **상태** 가 **건너뜀** 으로 나열되어 있으면 새로 고침이 시도되지 않았음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="c66f2-160">비활성 세그먼트가 활성화되면 새로 고쳐지고 예약된 새로 고침에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="c66f2-161">또는 **활성화/비활성화** 드롭다운의 **나중에 예약** 기능을 사용하여 특정 세그먼트의 활성화 및 비활성화에 대한 미래 날짜 및 시간을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="c66f2-162">**이름 바꾸기**: 세그먼트 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-162">**Rename** the segment.</span></span>
- <span data-ttu-id="c66f2-163">**다운로드**: 구성원 목록을 .CSV 파일로 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="c66f2-164">**추가** 옵션은 다른 애플리케이션에서 처리하기 위해 세그먼트의 고객 ID 목록을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="c66f2-165">**삭제**: 세그먼트를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="c66f2-166">세그먼트 새로 고침</span><span class="sxs-lookup"><span data-stu-id="c66f2-166">Refresh segments</span></span>

<span data-ttu-id="c66f2-167">**세그먼트** 페이지에서 **모두 새로 고침** 을 선택하여 모든 세그먼트를 한 번에 새로 고치거나 세그먼트를 선택할 때 하나 이상의 세그먼트를 새로 고치고 옵션에서 **새로 고침** 을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="c66f2-168">또는 **관리자** > **시스템** > **일정** 에서 반복 새로 고침을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="c66f2-169">작업/프로세스 [상태에는 6가지 유형](system.md#status-types)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="c66f2-170">또한 대부분의 프로세스는 [다른 다운스트림 프로세스에 의존](system.md#refresh-policies)합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="c66f2-171">프로세스 상태를 선택하여 전체 작업의 진행률에 대한 세부 사항을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="c66f2-172">작업 중 하나를 선택한 다음 **자세히 보기** 참조를 선택하면, 처리 시간, 마지막 처리 날짜, 작업과 관련된 모든 오류 및 경고와 같은 추가 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="c66f2-173">세그먼트 다운로드 및 내보내기</span><span class="sxs-lookup"><span data-stu-id="c66f2-173">Download and export segments</span></span>

<span data-ttu-id="c66f2-174">세그먼트를 CSV 파일로 다운로드하거나 Dynamics 365 Sales로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="c66f2-175">세그먼트를 CSV 파일로 다운로드</span><span class="sxs-lookup"><span data-stu-id="c66f2-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="c66f2-176">대상 그룹 인사이트에서 **세그먼트** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="c66f2-177">특정 세그먼트의 타일에서 줄임표를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="c66f2-178">작업 드롭다운 목록에서 **CSV로 다운로드** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="c66f2-179">Dynamics 365 Sales로 세그먼트 내보내기</span><span class="sxs-lookup"><span data-stu-id="c66f2-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="c66f2-180">세그먼트를 Dynamics 365 Sales로 내보내기 전에 관리자는 Dynamics 365 Sales에 대한 [내보내기 대상 만들기](export-destinations.md)를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="c66f2-181">대상 그룹 인사이트에서 **세그먼트** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="c66f2-182">특정 세그먼트의 타일에서 줄임표를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="c66f2-183">작업 드롭다운 목록에서 **추가** 를 선택하여 데이터를 보내려는 내보내기 대상을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="c66f2-184">세그먼트에 대한 초안 모드</span><span class="sxs-lookup"><span data-stu-id="c66f2-184">Draft mode for segments</span></span>

<span data-ttu-id="c66f2-185">세그먼트를 처리하기 위한 모든 요구 사항이 충족되지 않는 경우 세그먼트를 임시로 저장하고 **세그먼트** 페이지에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="c66f2-186">비활성 세그먼트로 저장되며 유효해질 때까지 활성화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="c66f2-187">그룹에 조건 추가</span><span class="sxs-lookup"><span data-stu-id="c66f2-187">Add more conditions to a group</span></span>

<span data-ttu-id="c66f2-188">그룹에 조건을 더 추가하려면 두 개의 논리 연산자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="c66f2-189">**AND** 연산자: 두 조건을 모두 세분화 프로세스의 일부로 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="c66f2-190">이 옵션은 여러 엔터티에서 조건을 정의할 때 가장 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="c66f2-191">**OR** 연산자: 세그레이션 프로세스의 일부로 조건 중 하나를 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="c66f2-192">이 옵션은 동일한 엔터티에 대해 여러 조건을 정의할 때 가장 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c66f2-193">![두 조건 중 하나를 충족해야 하는 OR 연산자](media/segmentation-either-condition.png "두 조건 중 하나를 충족해야 하는 OR 연산자")</span><span class="sxs-lookup"><span data-stu-id="c66f2-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="c66f2-194">현재 **OR** 연산자를 **AND** 연산자 아래에 중첩시킬 수는 있지만 다른 방법은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="c66f2-195">여러 그룹 결합</span><span class="sxs-lookup"><span data-stu-id="c66f2-195">Combine multiple groups</span></span>

<span data-ttu-id="c66f2-196">각 그룹은 특정 고객 세트를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="c66f2-197">이러한 그룹을 결합하여 비즈니스 서비스 케이스에 필요한 고객을 포함시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="c66f2-198">대상 그룹 인사이트에서 **세그먼트** 로 이동한 후 세그먼트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="c66f2-199">**그룹 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c66f2-200">![고객 그룹 추가 그룹](media/customer-group-add-group.png "고객 그룹 추가 그룹")</span><span class="sxs-lookup"><span data-stu-id="c66f2-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="c66f2-201">**통합**, **교차** 또는 **제외** 집합 연산자 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c66f2-202">![고객 그룹 추가 결합](media/customer-group-union.png "고객 그룹 추가 결합")</span><span class="sxs-lookup"><span data-stu-id="c66f2-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="c66f2-203">집합 연산자를 선택하여 새 그룹을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="c66f2-204">다른 그룹을 저장하여 보존되는 데이터를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="c66f2-205">**결합** 은 두 그룹을 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="c66f2-206">**교차** 는 두 그룹을 겹칩니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="c66f2-207">두 그룹에 *공통된* 데이터만 통합 그룹에 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="c66f2-208">**제외** 는 두 그룹을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-208">**Except** combines the two groups.</span></span> <span data-ttu-id="c66f2-209">그룹 B의 데이터와 *공통되지 않은* 그룹 A의 데이터만 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="c66f2-210">처리 기록 및 세그먼트 구성원 보기</span><span class="sxs-lookup"><span data-stu-id="c66f2-210">View processing history and segment members</span></span>

<span data-ttu-id="c66f2-211">세그먼트 세부정보를 검토하여 세그먼트에 대한 통합 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="c66f2-212">**세그먼트** 페이지에서 검토할 세그먼트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="c66f2-213">페이지의 상단 부분에는 구성원 수의 변화를 시각화하는 추세 그래프가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="c66f2-214">데이터 포인트 위로 마우스를 가져가면 특정 날짜의 구성원 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="c66f2-215">시각화의 시간 프레임 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c66f2-216">![세그먼트 시간 범위](media/segment-time-range.png "세그먼트 시간 범위")</span><span class="sxs-lookup"><span data-stu-id="c66f2-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="c66f2-217">아래 부분에는 세그먼트 구성원 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="c66f2-218">이 목록에 나타나는 필드는 세그먼트 엔터티의 특성을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="c66f2-219">이 목록은 일치하는 세그먼트 구성원의 미리 보기이며 세그먼트의 처음 100개 레코드를 표시하므로 신속하게 평가하고 필요한 경우 정의를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="c66f2-220">일치하는 모든 레코드를 보려면 [세그먼트 내보내기](export-destinations.md)를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="c66f2-221">퀵 세그먼트</span><span class="sxs-lookup"><span data-stu-id="c66f2-221">Quick segments</span></span>

<span data-ttu-id="c66f2-222">세그먼트 작성 도구 외에도 세그먼트를 만드는 또 다른 경로가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="c66f2-223">퀵 세그먼트를 사용하면 단일 연산자로 간단한 세그먼트를 신속하고 즉각적인 인사이트로 구축할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="c66f2-224">**세그먼트** 페이지에서 **새로 만들기** > **빠르게 만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="c66f2-225">**프로필** 옵션을 선택하여 통합 고객 엔터티를 기반으로 하는 세그먼트를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="c66f2-226">**측정값** 옵션을 선택하여 **측정**  페이지에서 이전에 만든 각 고객 속성 유형 측정값 주위에 세그먼트를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="c66f2-227">**예측** 또는 **사용자 지정 모델** 기능을 사용하여 생성한 출력 엔터티 중 하나를 중심으로 세그먼트를 작성하려면 **인텔리전스** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="c66f2-228">**새로운 빠른 세그먼트** 대화 상자에서 **필드** 드롭다운에서 특성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="c66f2-229">이 시스템은 고객의 더 나은 세그먼트를 만드는 데 도움이 되는 몇 가지 추가 통찰력을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="c66f2-230">범주별 필드의 경우 10개의 최상위 고객 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="c66f2-231">**값** 을 선택하고 **검토** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="c66f2-232">숫자 특성의 경우 시스템은 각 고객의 백분위수에 속하는 속성 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="c66f2-233">**연산자** 와 **값** 을 선택한 다음 **검토** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="c66f2-234">시스템은 **예상 세그먼트 크기** 를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="c66f2-235">정의한 세그먼트를 생성할지 또는 먼저 다시 방문하여 다른 세그먼트 크기를 얻을지 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c66f2-236">![빠른 세그먼트의 이름 및 평가](media/quick-segment-name.png "빠른 세그먼트의 이름 및 평가")</span><span class="sxs-lookup"><span data-stu-id="c66f2-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="c66f2-237">세그먼트의 **이름** 을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="c66f2-238">또는 **표시 이름** 을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="c66f2-239">**저장** 을 선택하여 세그먼트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="c66f2-240">세그먼트 처리가 완료되면 만든 다른 세그먼트와 마찬가지로 세그먼트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="c66f2-241">다음 시나리오의 경우 권장 세그먼트 기능이 아닌 세그먼트 빌더를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="c66f2-242">연산자가 **Is** 연산자와 다른 범주형 필드에 필터를 사용하여 세그먼트 만들기</span><span class="sxs-lookup"><span data-stu-id="c66f2-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="c66f2-243">연산자가 **사이**, **보다 큼** 및 **보다 작음** 과 다른 숫자 필드에 필터가 있는 세그먼트 만들기</span><span class="sxs-lookup"><span data-stu-id="c66f2-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="c66f2-244">날짜 유형 필드에 필터를 사용하여 세그먼트 작성</span><span class="sxs-lookup"><span data-stu-id="c66f2-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="c66f2-245">다음 단계</span><span class="sxs-lookup"><span data-stu-id="c66f2-245">Next steps</span></span>

<span data-ttu-id="c66f2-246">[세그먼트를 내보내고](export-destinations.md) [고객 카드](customer-card-add-in.md) 및 [커넥터](export-power-bi.md)를 탐색하여 고객 수준에 대한 통찰력을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c66f2-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]