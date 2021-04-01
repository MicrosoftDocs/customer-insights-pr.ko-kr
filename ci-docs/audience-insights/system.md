---
title: 대상 그룹 인사이트의 시스템 구성
description: Dynamics 365 Customer Insights 대상 그룹 인사이트 기능의 시스템 설정에 대해 알아봅니다.
ms.date: 02/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 87bf8d7b9c23633ebdc929e15ac645c55cc21e4a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595388"
---
# <a name="system-configuration"></a><span data-ttu-id="8d6a0-103">시스템 구성</span><span class="sxs-lookup"><span data-stu-id="8d6a0-103">System configuration</span></span>

<span data-ttu-id="8d6a0-104">**시스템** 페이지에는 다음 탭이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-104">The **System** page includes the following tabs:</span></span>
- [<span data-ttu-id="8d6a0-105">상태</span><span class="sxs-lookup"><span data-stu-id="8d6a0-105">Status</span></span>](#status-tab)
- [<span data-ttu-id="8d6a0-106">일정</span><span class="sxs-lookup"><span data-stu-id="8d6a0-106">Schedule</span></span>](#schedule-tab)
- [<span data-ttu-id="8d6a0-107">API 사용량</span><span class="sxs-lookup"><span data-stu-id="8d6a0-107">API usage</span></span>](#api-usage-tab)
- [<span data-ttu-id="8d6a0-108">정보</span><span class="sxs-lookup"><span data-stu-id="8d6a0-108">About</span></span>](#about-tab)
- [<span data-ttu-id="8d6a0-109">일반</span><span class="sxs-lookup"><span data-stu-id="8d6a0-109">General</span></span>](#general-tab)

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8d6a0-110">![시스템 페이지](media/system-tabs.png "시스템 페이지")</span><span class="sxs-lookup"><span data-stu-id="8d6a0-110">![System page](media/system-tabs.png "System page")</span></span>

## <a name="status-tab"></a><span data-ttu-id="8d6a0-111">상태 탭</span><span class="sxs-lookup"><span data-stu-id="8d6a0-111">Status tab</span></span>

<span data-ttu-id="8d6a0-112">**상태 탭** 을 사용하면 데이터 수집, 데이터 내보내기 및 기타 여러 중요한 제품 프로세스의 진행 상황을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-112">The **Status tab** lets you track the progress of data ingestion, data exports, and several other important product processes.</span></span> <span data-ttu-id="8d6a0-113">이 탭의 정보를 검토하여 활성 프로세스의 완전성을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-113">Review the information on this tab to ensure the completeness of active processes.</span></span>

<span data-ttu-id="8d6a0-114">이 탭에는 다양한 프로세스에 대한 상태 및 처리 정보가 있는 테이블이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-114">This tab includes tables with status and processing information for various processes.</span></span> <span data-ttu-id="8d6a0-115">각 테이블은 작업의 **이름** 과 해당 엔터티, 가장 최근에 실행된 **상태** 및 **마지막 업데이트** 날짜를 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-115">Each table tracks the **Name** of the task and its corresponding entity, the **Status** of its most recent run, and when it was **Last updated**.</span></span>

<span data-ttu-id="8d6a0-116">이름을 선택하여 작업의 마지막 여러 실행에 대한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-116">View the details of the tasks' last several runs by selecting its name.</span></span>

### <a name="status-types"></a><span data-ttu-id="8d6a0-117">상태 유형</span><span class="sxs-lookup"><span data-stu-id="8d6a0-117">Status types</span></span>

<span data-ttu-id="8d6a0-118">작업 상태에는 6가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-118">There are six types of status for tasks.</span></span> <span data-ttu-id="8d6a0-119">다음 상태 유형도 *일치*, *병합*, *데이터 소스*, *세그먼트*, *측정*, *보강*, *활동*, *예측* 페이지에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-119">The following status types also show on the *Match*, *Merge*, *Data sources*, *Segments*, *Measures*, *Enrichment*, *Activities*, and *Predictions* pages:</span></span>

- <span data-ttu-id="8d6a0-120">**처리 중:** 작업이 진행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-120">**Processing:** Task is in progress.</span></span> <span data-ttu-id="8d6a0-121">상태는 성공 또는 실패로 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-121">The status can change to Successful or Failure.</span></span>
- <span data-ttu-id="8d6a0-122">**성공:** 작업이 성공적으로 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-122">**Successful:** Task completed successfully.</span></span>
- <span data-ttu-id="8d6a0-123">**건너뜀:** 작업을 건너 뛰었습니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-123">**Skipped:** Task got skipped.</span></span> <span data-ttu-id="8d6a0-124">이 작업이 의존하는 하나 이상의 다운스트림 프로세스가 실패하거나 건너 뜁니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-124">One or more of the downstream processes this task depends on are failing or got skipped.</span></span>
- <span data-ttu-id="8d6a0-125">**실패:** 작업 처리에 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-125">**Failure:** Processing  of the task has failed.</span></span>
- <span data-ttu-id="8d6a0-126">**취소됨:** 사용자가 처리를 마치기 전에 취소했습니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-126">**Canceled:** Processing was canceled by the user before it finished.</span></span>
- <span data-ttu-id="8d6a0-127">**대기중:** 처리가 대기열에 있으며 모든 업스트림 작업이 완료되면 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-127">**Queued:** Processing is queued and will start once all the upstream tasks are completed.</span></span> <span data-ttu-id="8d6a0-128">자세한 내용은 [새로 고침 정책](#refresh-policies)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-128">For more information, see [Refresh policies](#refresh-policies).</span></span>

### <a name="refresh-policies"></a><span data-ttu-id="8d6a0-129">새로 고침 정책</span><span class="sxs-lookup"><span data-stu-id="8d6a0-129">Refresh policies</span></span>

<span data-ttu-id="8d6a0-130">이 목록은 각 주요 프로세스에 대한 새로 고침 정책을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-130">This list shows the refresh policies for each of the main processes:</span></span>

- <span data-ttu-id="8d6a0-131">**데이터 소스:** [구성된 일정](#schedule-tab)에 따라 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-131">**Data sources:** Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="8d6a0-132">다른 프로세스에 의존하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-132">Doesn't depend on any other process.</span></span> <span data-ttu-id="8d6a0-133">일치는 이 프로세스의 성공적인 완료에 달려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-133">Match depends on the successful completion of this process.</span></span>
- <span data-ttu-id="8d6a0-134">**일치:** [구성된 일정](#schedule-tab)에 따라 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-134">**Match:** Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="8d6a0-135">일치 정의에 사용된 데이터 소스의 처리에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-135">Depends on the processing of the data sources used in the match definition.</span></span> <span data-ttu-id="8d6a0-136">병합은 이 프로세스의 성공적인 완료에 달려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-136">Merge depends on the successful completion of this process.</span></span>
- <span data-ttu-id="8d6a0-137">**병합:** [구성된 일정](#schedule-tab)에 따라 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-137">**Merge**: Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="8d6a0-138">일치 프로세스의 완료에 달려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-138">Depends on the completion of the match process.</span></span> <span data-ttu-id="8d6a0-139">세그먼트, 측정, 보강, 검색, 활동, 예측 및 데이터 준비는 이 프로세스의 성공적인 완료에 달려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-139">Segments, measures, enrichment, search, activities, predictions, and data preparation depend on the successful completion of this process.</span></span>
- <span data-ttu-id="8d6a0-140">**세그먼트**: 수동으로 실행하고(단일 새로 고침) [구성된 일정](#schedule-tab)에 따라 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-140">**Segments**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="8d6a0-141">병합에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-141">Depends on Merge.</span></span> <span data-ttu-id="8d6a0-142">인사이트는 처리 과정에 달려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-142">Insights depend on its processing.</span></span>
- <span data-ttu-id="8d6a0-143">**측정**: 수동으로 실행하고(단일 새로 고침) [구성된 일정](#schedule-tab)에 따라 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-143">**Measures**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="8d6a0-144">병합에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-144">Depends on Merge.</span></span>
- <span data-ttu-id="8d6a0-145">**활동**: 수동으로 실행하고(단일 새로 고침) [구성된 일정](#schedule-tab)에 따라 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-145">**Activities**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="8d6a0-146">병합에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-146">Depends on Merge.</span></span>
- <span data-ttu-id="8d6a0-147">**보강**: 수동으로 실행하고(단일 새로 고침) [구성된 일정](#schedule-tab)에 따라 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-147">**Enrichment**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="8d6a0-148">병합에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-148">Depends on Merge.</span></span>
- <span data-ttu-id="8d6a0-149">**검색**: 수동으로 실행하고(단일 새로 고침) [구성된 일정](#schedule-tab)에 따라 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-149">**Search**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="8d6a0-150">병합에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-150">Depends on Merge.</span></span>
- <span data-ttu-id="8d6a0-151">**데이터 준비**: [구성된 일정](#schedule-tab)에 따라 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-151">**Data preparation**: Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="8d6a0-152">병합에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-152">Depends on Merge.</span></span>
- <span data-ttu-id="8d6a0-153">**인사이트**: 수동으로 실행하고(단일 새로 고침) [구성된 일정](#schedule-tab)에 따라 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-153">**Insights**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="8d6a0-154">세그먼트에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-154">Depends on Segments.</span></span>

<span data-ttu-id="8d6a0-155">작업 상태를 선택하면 작업이 진행 중인 전체 작업의 진행률 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-155">Select the status of a task to see the progress details of the entire job it was in.</span></span> <span data-ttu-id="8d6a0-156">위의 새로 고침 정책은 **건너뜀** 또는 **큐에 대기 중** 작업을 해결하기 위해 수행할 수 있는 작업을 이해하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-156">The refresh policies above can help to understand what you can do to address a **Skipped** or **Queued** task.</span></span>

## <a name="schedule-tab"></a><span data-ttu-id="8d6a0-157">예약 탭</span><span class="sxs-lookup"><span data-stu-id="8d6a0-157">Schedule tab</span></span>

<span data-ttu-id="8d6a0-158">**일정** 탭을 사용하여 [수집된 데이터 원본](data-sources.md) 전체에 대한 자동 새로 고침을 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-158">Use the **Schedule** tab to schedule automatic refreshes of all your [ingested data sources](data-sources.md).</span></span> <span data-ttu-id="8d6a0-159">자동 새로 고침은 데이터 소스의 업데이트가 통합 고객 프로필에 반영되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-159">Automatic refreshes help ensure that updates from your data sources are reflected in your unified customer profiles.</span></span>

1. <span data-ttu-id="8d6a0-160">대상 그룹 인사이트에서 **관리** > **시스템** 으로 이동한 후 **일정** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-160">In audience insights, go to **Admin** > **System** and select the **Schedule** tab.</span></span>

2. <span data-ttu-id="8d6a0-161">예약된 새로 고침의 기본 상태는 **꺼짐** 입니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-161">The default state for the scheduled refresh is **Off**.</span></span> <span data-ttu-id="8d6a0-162">예약된 새로 고침을 사용하려면 화면 상단의 토글을 **켜짐** 으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-162">To enable scheduled refreshes, change the toggle at the top of the screen to **On**.</span></span>

3. <span data-ttu-id="8d6a0-163">**매주**(기본값) 및 **매일** 새로 고침 중에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-163">Choose between **Weekly** (default) and **Daily** refreshes.</span></span> <span data-ttu-id="8d6a0-164">매주 새로 고침을 예약하려면 새로 고침을 실행할 날짜를 하나 이상 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-164">If you intend to schedule weekly refreshes, select one or more days on which you want to run the refresh.</span></span>

4. <span data-ttu-id="8d6a0-165">**표준 시간대** 를 설정한 다음 **시간** 드롭 다운 메뉴에서 새로 고침 타이밍을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-165">Set your **Time zone**, then use the **Time** dropdown to set your refresh timing.</span></span> <span data-ttu-id="8d6a0-166">완료되면 **설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-166">When you're finished, select **Set**.</span></span> <span data-ttu-id="8d6a0-167">하루에 여러 번 새로 고침을 예약하려면 **다른 시간 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-167">If you'd like to schedule multiple refreshes in a single day, select **Add another time**.</span></span>

5. <span data-ttu-id="8d6a0-168">**저장** 을 선택하여 변경 내용을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-168">Select **Save** to apply your changes.</span></span>

## <a name="about-tab"></a><span data-ttu-id="8d6a0-169">정보 탭</span><span class="sxs-lookup"><span data-stu-id="8d6a0-169">About tab</span></span>

<span data-ttu-id="8d6a0-170">**정보** 탭은 조직의 **표시 이름**, 활성 **환경 ID**, **지역** 및 사용자의 **세션 ID** 를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-170">The **About** tab contains your organization's **Display name**, the active **Environment ID**, the **Region**, and your **Session ID**.</span></span> <span data-ttu-id="8d6a0-171">둘 이상의 작업 환경이 있는 경우 쉽게 식별할 수 있는 표시 이름을 각각 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-171">If you have more than one work environment, you should give each an easily identifiable display name.</span></span>

## <a name="general-tab"></a><span data-ttu-id="8d6a0-172">일반 탭</span><span class="sxs-lookup"><span data-stu-id="8d6a0-172">General tab</span></span>

<span data-ttu-id="8d6a0-173">**일반** 탭에는 **언어** 및 **국가/지역 형식** 의 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-173">There are two options on the **General** tab, **Language** and **Country/Region format**.</span></span>

<span data-ttu-id="8d6a0-174">앱은 [다양한 언어를 지원](supported-languages.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-174">The app [supports a number of languages](supported-languages.md).</span></span> <span data-ttu-id="8d6a0-175">선호하는 언어를 변경하려면 드롭 다운에서 **언어** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-175">To change your preferred language, choose a **Language** from the dropdown.</span></span>

<span data-ttu-id="8d6a0-176">날짜, 시간 및 숫자에 대한 원하는 형식을 변경하려면 **국가/지역 형식** 드롭다운을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-176">To change your preferred formatting for dates, time, and numbers, use the **Country/Region format** dropdown.</span></span> <span data-ttu-id="8d6a0-177">이 필드 아래에 서식 미리 보기가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-177">A formatting preview is displayed under this field.</span></span> <span data-ttu-id="8d6a0-178">새 언어를 선택하면 시스템이 자동으로 선택 항목을 제안합니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-178">The system will automatically suggest a selection when you choose a new language.</span></span>

<span data-ttu-id="8d6a0-179">**저장** 을 선택하여 새 선택 항목을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-179">Select **Save** to confirm your selections.</span></span>

## <a name="api-usage-tab"></a><span data-ttu-id="8d6a0-180">API 사용 탭</span><span class="sxs-lookup"><span data-stu-id="8d6a0-180">API usage tab</span></span>

<span data-ttu-id="8d6a0-181">실시간 API 사용에 대한 세부 정보를 찾고 주어진 시간 프레임에서 발생한 이벤트를 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-181">Find details about the real-time API usage and see which events happened in a given time frame.</span></span> <span data-ttu-id="8d6a0-182">**시간 프레임 선택** 드롭 다운 메뉴에서 시간 프레임을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-182">You choose the time frame in the **Select a time frame** drop-down menu.</span></span> 

<span data-ttu-id="8d6a0-183">**API 사용량** 에는 세 개의 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-183">The **API usage** contains three sections:</span></span> 
- <span data-ttu-id="8d6a0-184">**API 호출** - 선택한 시간 프레임에서 API에 대한 총 호출 수를 시각화하는 차트입니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-184">**API calls** - a chart that visualizes the aggregated number of calls to the API in the selected time frame.</span></span>

- <span data-ttu-id="8d6a0-185">**데이터 전송** - 선택한 시간 프레임에서 API를 통해 전송된 데이터의 양을 보여주는 차트입니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-185">**Data transfer** - a chart that shows the amount of data that was transferred through the API in the selected time frame.</span></span>

-  <span data-ttu-id="8d6a0-186">**작업** - 각각의 사용 가능한 API 작업에 대한 행과 작업의 사용량에 대한 세부 정보가 포함된 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-186">**Operations** - a table with rows for each available API operation and details about the usage of the operations.</span></span> <span data-ttu-id="8d6a0-187">작업 이름을 선택하여 [API 참조](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances)로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-187">You can select an operation name to go to [the API reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

   <span data-ttu-id="8d6a0-188">[실시간 데이터 수집](real-time-data-ingestion.md)을 사용하는 작업에는 실시간 API 사용량을 볼 수 있도록 쌍안경 기호가 있는 버튼이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-188">Operations which use [real-time data ingestion](real-time-data-ingestion.md) contain a button with a binocular symbol to view real-time API usage.</span></span> <span data-ttu-id="8d6a0-189">버튼을 선택하여 현재 환경에서 실시간 API 사용에 대한 사용 세부 정보가 포함된 사이드 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-189">Select the button to open a side pane containing usage details for the real-time API usage in the current environment.</span></span>   
   <span data-ttu-id="8d6a0-190">**실시간 API 사용량** 창에서 **그룹화** 상자를 사용하여 실시간 상호 작용을 가장 잘 표시하는 방법을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-190">Use the **Group by** box in the **Real-time API usage** pane to choose how to best present your real-time interactions.</span></span> <span data-ttu-id="8d6a0-191">API 메서드, 엔터티 규정이름(대상 엔터티), (이벤트 소스), 결과(성공 또는 실패) 또는 오류 코드별로 데이터를 그룹화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-191">You can group the data by API method, entity qualified name (ingested entity), created by (source of the event), result (success or failure) or error codes.</span></span> <span data-ttu-id="8d6a0-192">데이터는 이력 차트 및 테이블로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d6a0-192">The data is available as a history chart and as a table.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]