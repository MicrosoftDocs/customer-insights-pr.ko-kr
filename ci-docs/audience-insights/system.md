---
title: 대상 그룹 인사이트의 시스템 구성
description: Dynamics 365 Customer Insights 대상 그룹 인사이트 기능의 시스템 설정에 대해 알아봅니다.
ms.date: 06/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: 7dd72e6512cd87ac70235d21667399298408db21
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406307"
---
# <a name="system-configuration"></a><span data-ttu-id="a90f1-103">시스템 구성</span><span class="sxs-lookup"><span data-stu-id="a90f1-103">System configuration</span></span>

<span data-ttu-id="a90f1-104">**시스템** 페이지에는 **상태**, **일정**, **정보** 및 **일반** 이라는 4개 탭이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-104">The **System** page includes four tabs: **Status**, **Schedule**, **About**, and **General**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a90f1-105">![시스템 페이지](media/system-tabs.png "시스템 페이지")</span><span class="sxs-lookup"><span data-stu-id="a90f1-105">![System page](media/system-tabs.png "System page")</span></span>

## <a name="status-tab"></a><span data-ttu-id="a90f1-106">상태 탭</span><span class="sxs-lookup"><span data-stu-id="a90f1-106">Status tab</span></span>

<span data-ttu-id="a90f1-107">**상태 탭** 을 사용하면 데이터 수집 진행률, 데이터 내보내기 및 몇 가지 중요한 제품 프로세스를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-107">The **Status tab** lets you track the progress of data ingestion, data exports, and several important product processes.</span></span> <span data-ttu-id="a90f1-108">이 탭의 정보를 검토하여 활성 프로세스의 완전성을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="a90f1-108">Review the information on this tab to ensure the completeness of active processes.</span></span>

<span data-ttu-id="a90f1-109">이 탭에는 **데이터 원본**, **시스템 프로세스** 및 **데이터 준비** 에 대한 상태 테이블이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-109">This tab includes status tables for **Data sources**, **System processes**, and **Data preparation**.</span></span> <span data-ttu-id="a90f1-110">각 테이블은 작업의 **이름** 과 해당 엔터티, 가장 최근에 실행된 **상태** 및 **마지막 업데이트** 날짜를 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-110">Each table tracks the **Name** of the task and its corresponding entity, the **Status** of its most recent run, and when it was **Last updated**.</span></span>

<span data-ttu-id="a90f1-111">이름을 선택하여 작업의 마지막 여러 실행에 대한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-111">View the details of the tasks' last several runs by selecting its name.</span></span>

### <a name="status-types"></a><span data-ttu-id="a90f1-112">상태 유형</span><span class="sxs-lookup"><span data-stu-id="a90f1-112">Status types</span></span>

<span data-ttu-id="a90f1-113">작업 상태에는 6가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-113">There are six types of status for tasks.</span></span> <span data-ttu-id="a90f1-114">다음 상태 유형도 *일치*, *병합*, *데이터 소스*, *세그먼트*, *측정*, *보강*, *활동*, *예측* 페이지에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-114">The following status types also show on the *Match*, *Merge*, *Data sources*, *Segments*, *Measures*, *Enrichment*, *Activities*, and *Predictions* pages:</span></span>

- <span data-ttu-id="a90f1-115">**처리 중:** 작업이 진행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-115">**Processing:** Task is in progress.</span></span> <span data-ttu-id="a90f1-116">상태는 성공 또는 실패로 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-116">The status can change to Successful or Failure.</span></span>
- <span data-ttu-id="a90f1-117">**성공:** 작업이 성공적으로 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-117">**Successful:** Task completed successfully.</span></span>
- <span data-ttu-id="a90f1-118">**건너뜀:** 작업을 건너 뛰었습니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-118">**Skipped:** Task got skipped.</span></span> <span data-ttu-id="a90f1-119">이 작업이 의존하는 하나 이상의 다운스트림 프로세스가 실패하거나 건너 뜁니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-119">One or more of the downstream processes this task depends on are failing or got skipped.</span></span>
- <span data-ttu-id="a90f1-120">**실패:** 작업 처리에 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-120">**Failure:** Processing  of the task has failed.</span></span>
- <span data-ttu-id="a90f1-121">**취소됨:** 사용자가 처리를 마치기 전에 취소했습니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-121">**Canceled:** Processing was canceled by the user before it finished.</span></span>
- <span data-ttu-id="a90f1-122">**큐에 대기 중:** 처리가 대기 중이며 모든 다운스트림 작업이 완료되면 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-122">**Queued:** Processing is queued and will start once all the downstream tasks are completed.</span></span> <span data-ttu-id="a90f1-123">자세한 내용은 [새로 고침 정책](#refresh-policies)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a90f1-123">For more information, see [Refresh policies](#refresh-policies).</span></span>

### <a name="refresh-policies"></a><span data-ttu-id="a90f1-124">새로 고침 정책</span><span class="sxs-lookup"><span data-stu-id="a90f1-124">Refresh policies</span></span>

<span data-ttu-id="a90f1-125">이 목록은 각 주요 프로세스에 대한 새로 고침 정책을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-125">This list shows the refresh policies for each of the main processes:</span></span>

- <span data-ttu-id="a90f1-126">**데이터 소스:** [구성된 일정](#schedule-tab)에 따라 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-126">**Data sources:** Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="a90f1-127">다른 프로세스에 의존하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-127">Doesn't depend on any other process.</span></span> <span data-ttu-id="a90f1-128">일치는 이 프로세스의 성공적인 완료에 달려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-128">Match depends on the successful completion of this process.</span></span>
- <span data-ttu-id="a90f1-129">**일치:** [구성된 일정](#schedule-tab)에 따라 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-129">**Match:** Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="a90f1-130">일치 정의에 사용된 데이터 소스의 처리에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-130">Depends on the processing of the data sources used in the match definition.</span></span> <span data-ttu-id="a90f1-131">병합은 이 프로세스의 성공적인 완료에 달려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-131">Merge depends on the successful completion of this process.</span></span>
- <span data-ttu-id="a90f1-132">**병합:** [구성된 일정](#schedule-tab)에 따라 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-132">**Merge**: Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="a90f1-133">일치 프로세스의 완료에 달려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-133">Depends on the completion of the match process.</span></span> <span data-ttu-id="a90f1-134">세그먼트, 측정, 보강, 검색, 활동, 예측 및 데이터 준비는 이 프로세스의 성공적인 완료에 달려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-134">Segments, measures, enrichment, search, activities, predictions, and data preparation depend on the successful completion of this process.</span></span>
- <span data-ttu-id="a90f1-135">**세그먼트**: 수동으로 실행하고(단일 새로 고침) [구성된 일정](#schedule-tab)에 따라 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-135">**Segments**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="a90f1-136">병합에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-136">Depends on Merge.</span></span> <span data-ttu-id="a90f1-137">인사이트는 처리 과정에 달려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-137">Insights depend on its processing.</span></span>
- <span data-ttu-id="a90f1-138">**측정**: 수동으로 실행하고(단일 새로 고침) [구성된 일정](#schedule-tab)에 따라 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-138">**Measures**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="a90f1-139">병합에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-139">Depends on Merge.</span></span>
- <span data-ttu-id="a90f1-140">**활동**: 수동으로 실행하고(단일 새로 고침) [구성된 일정](#schedule-tab)에 따라 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-140">**Activities**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="a90f1-141">병합에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-141">Depends on Merge.</span></span>
- <span data-ttu-id="a90f1-142">**보강**: 수동으로 실행하고(단일 새로 고침) [구성된 일정](#schedule-tab)에 따라 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-142">**Enrichment**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="a90f1-143">병합에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-143">Depends on Merge.</span></span>
- <span data-ttu-id="a90f1-144">**검색**: 수동으로 실행하고(단일 새로 고침) [구성된 일정](#schedule-tab)에 따라 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-144">**Search**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="a90f1-145">병합에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-145">Depends on Merge.</span></span>
- <span data-ttu-id="a90f1-146">**데이터 준비**: [구성된 일정](#schedule-tab)에 따라 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-146">**Data preparation**: Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="a90f1-147">병합에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-147">Depends on Merge.</span></span>
- <span data-ttu-id="a90f1-148">**인사이트**: 수동으로 실행하고(단일 새로 고침) [구성된 일정](#schedule-tab)에 따라 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-148">**Insights**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="a90f1-149">세그먼트에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-149">Depends on Segments.</span></span>

<span data-ttu-id="a90f1-150">작업 상태를 선택하면 작업이 진행 중인 전체 작업의 진행률 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-150">Select the status of a task to see the progress details of the entire job it was in.</span></span> <span data-ttu-id="a90f1-151">위의 새로 고침 정책은 **건너뜀** 또는 **큐에 대기 중** 작업을 해결하기 위해 수행할 수 있는 작업을 이해하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-151">The refresh policies above can help to understand what you can do to address a **Skipped** or **Queued** task.</span></span>

## <a name="schedule-tab"></a><span data-ttu-id="a90f1-152">예약 탭</span><span class="sxs-lookup"><span data-stu-id="a90f1-152">Schedule tab</span></span>

<span data-ttu-id="a90f1-153">**일정** 탭을 사용하여 [수집된 데이터 원본](data-sources.md) 전체에 대한 자동 새로 고침을 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-153">Use the **Schedule** tab to schedule automatic refreshes of all your [ingested data sources](data-sources.md).</span></span> <span data-ttu-id="a90f1-154">자동 새로 고침은 데이터 소스의 업데이트가 통합 고객 프로필에 반영되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-154">Automatic refreshes help ensure that updates from your data sources are reflected in your unified customer profiles.</span></span>

1. <span data-ttu-id="a90f1-155">대상 그룹 인사이트에서 **관리** > **시스템** 으로 이동한 후 **일정** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-155">In audience insights, go to **Admin** > **System** and select the **Schedule** tab.</span></span>

2. <span data-ttu-id="a90f1-156">예약된 새로 고침의 기본 상태는 **꺼짐** 입니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-156">The default state for the scheduled refresh is **Off**.</span></span> <span data-ttu-id="a90f1-157">예약된 새로 고침을 사용하려면 화면 상단의 토글을 **켜짐** 으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-157">To enable scheduled refreshes, change the toggle at the top of the screen to **On**.</span></span>

3. <span data-ttu-id="a90f1-158">**매주**(기본값) 및 **매일** 새로 고침 중에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-158">Choose between **Weekly** (default) and **Daily** refreshes.</span></span> <span data-ttu-id="a90f1-159">매주 새로 고침을 예약하려면 새로 고침을 실행할 날짜를 하나 이상 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-159">If you intend to schedule weekly refreshes, select one or more days on which you want to run the refresh.</span></span>

4. <span data-ttu-id="a90f1-160">**표준 시간대** 를 설정한 다음 **시간** 드롭 다운 메뉴에서 새로 고침 타이밍을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-160">Set your **Time zone**, then use the **Time** dropdown to set your refresh timing.</span></span> <span data-ttu-id="a90f1-161">완료되면 **설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-161">When you're finished, select **Set**.</span></span> <span data-ttu-id="a90f1-162">하루에 여러 번 새로 고침을 예약하려면 **다른 시간 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-162">If you'd like to schedule multiple refreshes in a single day, select **Add another time**.</span></span>

5. <span data-ttu-id="a90f1-163">**저장** 을 선택하여 변경 내용을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-163">Select **Save** to apply your changes.</span></span>

## <a name="about-tab"></a><span data-ttu-id="a90f1-164">정보 탭</span><span class="sxs-lookup"><span data-stu-id="a90f1-164">About tab</span></span>

<span data-ttu-id="a90f1-165">**정보** 탭은 조직의 **표시 이름**, 활성 **환경 ID**, **지역** 및 사용자의 **세션 ID** 를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-165">The **About** tab contains your organization's **Display name**, the active **Environment ID**, the **Region**, and your **Session ID**.</span></span> <span data-ttu-id="a90f1-166">둘 이상의 작업 환경이 있는 경우 쉽게 식별할 수 있는 표시 이름을 각각 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-166">If you have more than one work environment, you should give each an easily identifiable display name.</span></span>

## <a name="general-tab"></a><span data-ttu-id="a90f1-167">일반 탭</span><span class="sxs-lookup"><span data-stu-id="a90f1-167">General tab</span></span>

<span data-ttu-id="a90f1-168">**일반** 탭에는 **언어** 및 **국가/지역 형식** 의 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-168">There are two options on the **General** tab, **Language** and **Country/Region format**.</span></span>

<span data-ttu-id="a90f1-169">앱은 [다양한 언어를 지원](supported-languages.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-169">The app [supports a number of languages](supported-languages.md).</span></span> <span data-ttu-id="a90f1-170">선호하는 언어를 변경하려면 드롭 다운에서 **언어** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-170">To change your preferred language, choose a **Language** from the dropdown.</span></span>

<span data-ttu-id="a90f1-171">날짜, 시간 및 숫자에 대한 원하는 형식을 변경하려면 **국가/지역 형식** 드롭다운을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-171">To change your preferred formatting for dates, time, and numbers, use the **Country/Region format** dropdown.</span></span> <span data-ttu-id="a90f1-172">이 필드 아래에 서식 미리 보기가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-172">A formatting preview is displayed under this field.</span></span> <span data-ttu-id="a90f1-173">새 언어를 선택하면 시스템이 자동으로 선택 항목을 제안합니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-173">The system will automatically suggest a selection when you choose a new language.</span></span>

<span data-ttu-id="a90f1-174">**저장** 을 선택하여 새 선택 항목을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-174">Select **Save** to confirm your selections.</span></span>

## <a name="api-usage-tab"></a><span data-ttu-id="a90f1-175">API 사용 탭</span><span class="sxs-lookup"><span data-stu-id="a90f1-175">API usage tab</span></span>

<span data-ttu-id="a90f1-176">실시간 API 사용에 대한 세부 사항을 찾고 주어진 시간 범위에서 발생한 이벤트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a90f1-176">Find details about the real-time API usage and see which events happened in a given time range.</span></span> <span data-ttu-id="a90f1-177">자세한 내용은 [실시간 데이터 수집](real-time-data-ingestion.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a90f1-177">For more information, see [Real-time data ingestion](real-time-data-ingestion.md).</span></span>
