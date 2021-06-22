---
title: Customer Insights에서 데이터 내보내기
description: 데이터 공유를 위한 내보내기를 관리합니다.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253048"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="10875-103">내보내기(프리뷰) 개요</span><span class="sxs-lookup"><span data-stu-id="10875-103">Exports (preview) overview</span></span>

<span data-ttu-id="10875-104">**내보내기** 페이지에는 구성된 모든 내보내기가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="10875-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="10875-105">내보내기는 다양한 애플리케이션과 특정 데이터를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="10875-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="10875-106">여기에는 고객 프로필 또는 엔터티, 스키마 및 매핑 세부 정보가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10875-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="10875-107">각 내보내기에는 [인증 및 액세스 관리를 위해 관리자가 설정한 연결](connections.md)이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="10875-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="10875-108">**데이터** > **내보내기** 로 이동하여 내보내기 페이지를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="10875-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="10875-109">모든 사용자 역할은 구성된 내보내기를 볼 수 있는 액세스 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10875-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="10875-110">명령 모음의 검색 필드를 사용하여 이름, 연결 이름 또는 연결 유형별로 내보내기를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="10875-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="10875-111">새로운 내보내기 설정</span><span class="sxs-lookup"><span data-stu-id="10875-111">Set up a new export</span></span>

<span data-ttu-id="10875-112">내보내기를 설정하거나 편집하려면 연결을 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10875-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="10875-113">연결은 귀하의 [사용자 역할](permissions.md)에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="10875-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="10875-114">관리자는 모든 연결에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10875-114">Administrators have access to all connections.</span></span> <span data-ttu-id="10875-115">내보내기를 설정할 때 새 연결을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10875-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="10875-116">기여자는 특정 연결에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10875-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="10875-117">관리자가 연결을 구성하고 공유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10875-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="10875-118">내보내기 목록에는 참여자가 **내 권한** 열에서 내보내기를 편집할 수 있는지 아니면 보기만 가능한지 여부가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="10875-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="10875-119">자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="10875-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="10875-120">보기 권한자는 기존 내보내기를 볼 수만 있고 만들 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="10875-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="10875-121">새로운 내보내기 정의</span><span class="sxs-lookup"><span data-stu-id="10875-121">Define a new export</span></span>

1. <span data-ttu-id="10875-122">**데이터** > **내보내기** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="10875-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="10875-123">**내보내기 추가** 를 선택하여 새 내보내기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="10875-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="10875-124">**내보내기 설정** 창에서 사용할 연결을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="10875-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="10875-125">[연결](connections.md)은 관리자가 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="10875-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="10875-126">필요한 세부 정보를 제공하고 **저장** 을 선택하여 내보내기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="10875-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="10875-127">기존 내보내기를 기반으로 새 내보내기 정의</span><span class="sxs-lookup"><span data-stu-id="10875-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="10875-128">**데이터** > **내보내기** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="10875-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="10875-129">내보내기 목록에서 복제할 내보내기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="10875-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="10875-130">명령 모음에서 **복제본 만들기** 를 선택하여 선택한 내보내기의 세부 정보가 있는 **내보내기 설정** 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="10875-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="10875-131">내보내기를 검토 및 조정하고 **저장** 을 선택하여 새 내보내기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="10875-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="10875-132">내보내기 편집</span><span class="sxs-lookup"><span data-stu-id="10875-132">Edit an export</span></span>

1. <span data-ttu-id="10875-133">**데이터** > **내보내기** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="10875-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="10875-134">내보내기 목록에서 편집할 내보내기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="10875-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="10875-135">명령 모음에서 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="10875-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="10875-136">업데이트할 값을 변경하고 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="10875-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="10875-137">내보내기 및 내보내기 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="10875-137">View exports and export details</span></span>

<span data-ttu-id="10875-138">내보내기 대상을 만들면 **데이터** > **내보내기** 에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="10875-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="10875-139">모든 사용자는 공유된 데이터와 최신 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10875-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="10875-140">**데이터** > **내보내기** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="10875-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="10875-141">편집 권한이 없는 사용자는 **편집** 대신 **보기** 를 선택하여 내보내기 세부 사항을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="10875-141">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="10875-142">측면 창에는 내보내기 구성이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="10875-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="10875-143">편집 권한이 없으면 값을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="10875-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="10875-144">**닫기** 를 선택하여 내보내기 페이지로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="10875-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="10875-145">내보내기 예약 및 실행</span><span class="sxs-lookup"><span data-stu-id="10875-145">Schedule and run exports</span></span>

<span data-ttu-id="10875-146">구성하는 각 내보내기에는 새로 고침 일정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10875-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="10875-147">새로 고치는 동안 시스템은 내보내기에 포함할 새 데이터 또는 업데이트된 데이터를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="10875-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="10875-148">기본적으로 내보내기는 모든 [예약된 시스템 새로 고침](system.md#schedule-tab)의 일부로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="10875-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="10875-149">새로 고침 일정을 사용자 지정하거나 해제하여 수동으로 내보내기를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10875-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="10875-150">내보내기 일정은 환경 상태에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="10875-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="10875-151">예약된 내보내기가 시작되어야 할 때 진행중인 [종속성](system.md#refresh-policies)에 대한 업데이트가 있는 경우 시스템은 먼저 종속성을 완료한 다음 내보내기를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="10875-151">If there are updates on [dependencies](system.md#refresh-policies) in progress when a scheduled export should start, the system will first complete the dependencies and then run the export.</span></span> <span data-ttu-id="10875-152">**새로 고침** 열에서 내보내기가 마지막으로 새로 고쳐진 시기를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10875-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="10875-153">내보내기 예약</span><span class="sxs-lookup"><span data-stu-id="10875-153">Schedule exports</span></span>

<span data-ttu-id="10875-154">개별 내보내기 또는 한 번에 여러 내보내기에 대한 사용자 지정 새로 고침 일정을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10875-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="10875-155">현재 정의된 일정은 내보내기 목록의 **일정** 열에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="10875-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="10875-156">일정 변경 권한은 [내보내기 편집 및 정의](export-destinations.md#set-up-a-new-export)의 경우와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="10875-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="10875-157">**데이터** > **내보내기** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="10875-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="10875-158">예약할 내보내기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="10875-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="10875-159">명령 모음에서 **일정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="10875-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="10875-160">**내보내기 예약** 창에서 **일정 실행** 을 **On** 으로 설정하여 내보내기를 자동으로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="10875-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="10875-161">수동으로 새로 고치려면 **Off** 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="10875-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="10875-162">자동으로 새로 고침 되는 내보내기의 경우 **반복** 값을 선택하고 세부 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="10875-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="10875-163">정의된 시간은 모든 반복 인스턴스에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="10875-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="10875-164">이는 내보내기가 새로 고침을 시작해야 할 시기입니다.</span><span class="sxs-lookup"><span data-stu-id="10875-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="10875-165">**저장** 을 선택하여 변경 사항을 적용하고 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="10875-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="10875-166">여러 내보내기에 대한 일정을 편집하는 경우 **일정 유지 또는 다시 정의** 에서 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10875-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="10875-167">**개별 일정 유지**: 선택한 내보내기에 대해 이전에 정의한 일정을 유지하고 비활성화 또는 활성화만합니다.</span><span class="sxs-lookup"><span data-stu-id="10875-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="10875-168">**선택한 모든 내보내기에 대한 새 일정 정의**: 선택한 내보내기의 기존 일정을 다시 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="10875-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="10875-169">주문형으로 내보내기 실행</span><span class="sxs-lookup"><span data-stu-id="10875-169">Run exports on demand</span></span>

<span data-ttu-id="10875-170">예약된 새로 고침을 기다리지 않고 데이터를 내보내려면 **데이터** > **내보내기** 로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="10875-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="10875-171">모든 내보내기를 실행하려면 명령 모음에서 **모두 실행** 을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="10875-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="10875-172">이 작업은 활성 일정이 있는 내보내기만 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="10875-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="10875-173">단일 내보내기를 실행하려면 목록에서 선택하고 명령 모음에서 **실행** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="10875-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="10875-174">이는 활성화된 일정 없이 내보내기를 실행하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="10875-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="10875-175">내보내기 제거</span><span class="sxs-lookup"><span data-stu-id="10875-175">Remove an Export</span></span>

1. <span data-ttu-id="10875-176">**데이터** > **내보내기** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="10875-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="10875-177">제거할 내보내기를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="10875-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="10875-178">명령 모음에서 **제거** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="10875-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="10875-179">확인 화면에서 **제거** 를 선택하여 제거를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="10875-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
