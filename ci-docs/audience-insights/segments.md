---
title: 대상 그룹 인사이트의 세그먼트
description: 세그먼트 및 세그먼트 생성 및 관리 방법에 대한 개요입니다.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a7fa6515bd6e79dedfb21aa0f0b8e24b873a6771
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034020"
---
# <a name="segments-overview"></a><span data-ttu-id="240e4-103">세그먼트 개요</span><span class="sxs-lookup"><span data-stu-id="240e4-103">Segments overview</span></span>

<span data-ttu-id="240e4-104">세그먼트를 사용하면 인구 통계, 트랜잭션 또는 행동 특성을 기반으로 고객을 그룹화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="240e4-105">세그먼트를 사용하여 판촉 캠페인, 판매 활동 및 고객 지원 조치를 대상으로 비즈니스 목표를 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="240e4-106">세그먼트 정의의 필터와 일치하는 고객 프로필을 세그먼트의 *구성원* 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-106">Customer profiles that match the filters of a segment definition are referred as *members* of a segment.</span></span> <span data-ttu-id="240e4-107">약간의 [서비스 제한](service-limits.md)이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-107">Some [service limits](service-limits.md) apply.</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="240e4-108">새 세그먼트 만들기</span><span class="sxs-lookup"><span data-stu-id="240e4-108">Create a new segment</span></span>

<span data-ttu-id="240e4-109">새 세그먼트를 만드는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-109">There are multiple ways to create a new segment:</span></span> 

- <span data-ttu-id="240e4-110">세그먼트 빌더를 통한 복잡한 세그먼트: [빈 세그먼트](segment-builder.md#create-a-new-segment)</span><span class="sxs-lookup"><span data-stu-id="240e4-110">Complex segment with segment builder: [Blank segment](segment-builder.md#create-a-new-segment)</span></span>
- <span data-ttu-id="240e4-111">연산자가 하나인 간단한 세그먼트: [빠른 세그먼트](segment-builder.md#quick-segments)</span><span class="sxs-lookup"><span data-stu-id="240e4-111">Simple segments with one operator: [Quick segment](segment-builder.md#quick-segments)</span></span>
- <span data-ttu-id="240e4-112">유사한 고객을 찾는 AI 기반 방법: [유사 고객](find-similar-customer-segments.md)</span><span class="sxs-lookup"><span data-stu-id="240e4-112">AI-powered way to find similar customers: [Similar Customers](find-similar-customer-segments.md)</span></span>
- <span data-ttu-id="240e4-113">측정값 또는 속성을 기반으로 한 AI 기반 제안: [측정값 향상을 위한 제안 세그먼트](suggested-segments.md)</span><span class="sxs-lookup"><span data-stu-id="240e4-113">AI-powered suggestions based on measures or attributes: [Suggested segments to improve measures](suggested-segments.md)</span></span>
- <span data-ttu-id="240e4-114">활동에 따른 제안: [고객 활동에 기반한 제안 세그먼트](suggested-segments-activity.md)</span><span class="sxs-lookup"><span data-stu-id="240e4-114">Suggestions based on activities: [Suggested segments based on customer activity](suggested-segments-activity.md)</span></span>

## <a name="get-insights-on-existing-segments"></a><span data-ttu-id="240e4-115">기존 세그먼트에 대한 인사이트 얻기</span><span class="sxs-lookup"><span data-stu-id="240e4-115">Get insights on existing segments</span></span>

<span data-ttu-id="240e4-116">[세그먼트 인사이트](segment-insights.md)를 사용하여 기존 세그먼트에 대한 추가 정보를 찾아보십시오.</span><span class="sxs-lookup"><span data-stu-id="240e4-116">Discover additional information around your existing segments with [Segment insights](segment-insights.md).</span></span> <span data-ttu-id="240e4-117">두 세그먼트를 차별화하는 요소 또는 공통점을 찾으십시오.</span><span class="sxs-lookup"><span data-stu-id="240e4-117">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="find-similar-customers"></a><span data-ttu-id="240e4-118">유사 고객 찾기</span><span class="sxs-lookup"><span data-stu-id="240e4-118">Find similar customers</span></span>

<span data-ttu-id="240e4-119">인공 지능의 도움을 받아 선택한 세그먼트의 구성원과 유사한 고객을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-119">Find customers that are similar to the members of a selected segment with the help of artificial intelligence.</span></span> <span data-ttu-id="240e4-120">자세한 내용은 [유사한 고객](find-similar-customer-segments.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="240e4-120">For more information, see [similar customers ](find-similar-customer-segments.md).</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="240e4-121">기존 세그먼트 관리</span><span class="sxs-lookup"><span data-stu-id="240e4-121">Manage existing segments</span></span>

<span data-ttu-id="240e4-122">**세그먼트** 페이지로 이동하여 저장된 모든 세그먼트를 보고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-122">Go to the **Segments** page, to view all your saved segments and manage them.</span></span>

<span data-ttu-id="240e4-123">각 세그먼트는 세그먼트에 대한 추가 정보가 포함된 행으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-123">Each segment is represented by a row that includes additional information about the segment.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="240e4-124">![기존 세그먼트를 관리하는 옵션](media/segments-selected-segment.png "기존 세그먼트를 관리하는 옵션")</span><span class="sxs-lookup"><span data-stu-id="240e4-124">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="240e4-125">세그먼트를 선택하면 다음 작업을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-125">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="240e4-126">**보기**: 구성원 수 추세를 포함한 세그먼트 세부 사항 및 세그먼트 구성원의 미리보기를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-126">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="240e4-127">**편집**: 속성을 변경할 세그먼트를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-127">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="240e4-128">세그먼트의 **중복 항목을 만듭니다**.</span><span class="sxs-lookup"><span data-stu-id="240e4-128">**Create duplicate** of a segment.</span></span> <span data-ttu-id="240e4-129">속성을 즉시 편집하거나 단순히 중복 항목을 저장하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-129">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="240e4-130">**새로 고침**: 최신 데이터를 포함하도록 세그먼트를 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-130">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="240e4-131">**활성화** 또는 **비활성화**: 세그먼트를 활성화하거나 비활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-131">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="240e4-132">세그먼트에는 활성 또는 비활성의 두 가지 상태가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-132">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="240e4-133">이러한 상태는 세그먼트를 편집할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-133">These states come in handy when editing a segment.</span></span> <span data-ttu-id="240e4-134">비활성 세그먼트의 경우 세그먼트 정의가 존재하지만 아직 고객이 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-134">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="240e4-135">세그먼트를 활성화하면 상태가 '비활성'에서 '활성'으로 변경되고 세그먼트 정의와 일치하는 고객을 찾기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-135">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="240e4-136">[예약된 새로 고침](system.md#schedule-tab)이 구성되었고 비활성 세그먼트에 **상태** 가 **건너뜀** 으로 나열되어 있으면 새로 고침이 시도되지 않았음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-136">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="240e4-137">비활성 세그먼트가 활성화되면 새로 고쳐지고 예약된 새로 고침에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-137">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="240e4-138">또는 **활성화/비활성화** 드롭다운의 **나중에 예약** 기능을 사용하여 특정 세그먼트의 활성화 및 비활성화에 대한 미래 날짜 및 시간을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-138">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="240e4-139">**이름 바꾸기**: 세그먼트 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-139">**Rename** the segment.</span></span>
- <span data-ttu-id="240e4-140">**다운로드**: 구성원 목록을 .CSV 파일로 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-140">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="240e4-141">**추가** 옵션은 다른 애플리케이션에서 처리하기 위해 세그먼트의 고객 ID 목록을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-141">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="240e4-142">**삭제**: 세그먼트를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-142">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="240e4-143">세그먼트 새로 고침</span><span class="sxs-lookup"><span data-stu-id="240e4-143">Refresh segments</span></span>

<span data-ttu-id="240e4-144">**세그먼트** 페이지에서 **모두 새로 고침** 을 선택하여 모든 세그먼트를 한 번에 새로 고치거나 세그먼트를 선택할 때 하나 이상의 세그먼트를 새로 고치고 옵션에서 **새로 고침** 을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-144">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="240e4-145">또는 **관리자** > **시스템** > **일정** 에서 반복 새로 고침을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-145">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="240e4-146">작업/프로세스 [상태에는 6가지 유형](system.md#status-types)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="240e4-147">또한 대부분의 프로세스는 [다른 다운스트림 프로세스에 의존](system.md#refresh-policies)합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="240e4-148">프로세스 상태를 선택하여 전체 작업의 진행률에 대한 세부 사항을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="240e4-149">작업 중 하나를 선택한 다음 **자세히 보기** 참조를 선택하면, 처리 시간, 마지막 처리 날짜, 작업과 관련된 모든 오류 및 경고와 같은 추가 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="240e4-150">처리 기록 및 세그먼트 구성원 보기</span><span class="sxs-lookup"><span data-stu-id="240e4-150">View processing history and segment members</span></span>

<span data-ttu-id="240e4-151">세그먼트 세부정보를 검토하여 세그먼트에 대한 통합 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-151">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="240e4-152">**세그먼트** 페이지에서 검토할 세그먼트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-152">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="240e4-153">페이지의 상단 부분에는 구성원 수의 변화를 시각화하는 추세 그래프가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-153">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="240e4-154">데이터 포인트 위로 마우스를 가져가면 특정 날짜의 구성원 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-154">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="240e4-155">시각화의 시간 프레임 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-155">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="240e4-156">![세그먼트 시간 범위](media/segment-time-range.png "세그먼트 시간 범위")</span><span class="sxs-lookup"><span data-stu-id="240e4-156">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="240e4-157">아래 부분에는 세그먼트 구성원 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-157">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="240e4-158">이 목록에 나타나는 필드는 세그먼트 엔터티의 특성을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-158">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="240e4-159">이 목록은 일치하는 세그먼트 구성원의 미리 보기이며 세그먼트의 처음 100개 레코드를 표시하므로 신속하게 평가하고 필요한 경우 정의를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-159">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="240e4-160">일치하는 모든 레코드를 보려면 [세그먼트 내보내기](export-destinations.md)를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-160">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
