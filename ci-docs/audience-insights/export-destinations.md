---
title: Customer Insights에서 데이터 내보내기
description: 데이터 공유를 위한 내보내기를 관리합니다.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016622"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="ec6b1-103">내보내기(프리뷰) 개요</span><span class="sxs-lookup"><span data-stu-id="ec6b1-103">Exports (preview) overview</span></span>

<span data-ttu-id="ec6b1-104">**내보내기** 페이지에는 구성된 모든 내보내기가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="ec6b1-105">내보내기는 다양한 애플리케이션과 특정 데이터를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="ec6b1-106">여기에는 고객 프로필 또는 엔터티, 스키마 및 매핑 세부 정보가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="ec6b1-107">각 내보내기에는 [인증 및 액세스 관리를 위해 관리자가 설정한 연결](connections.md)이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="ec6b1-108">**데이터** > **내보내기** 로 이동하여 내보내기 페이지를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="ec6b1-109">모든 사용자 역할은 구성된 내보내기를 볼 수 있는 액세스 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="ec6b1-110">명령 모음의 검색 필드를 사용하여 이름, 연결 이름 또는 연결 유형별로 내보내기를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="ec6b1-111">새로운 내보내기 설정</span><span class="sxs-lookup"><span data-stu-id="ec6b1-111">Set up a new export</span></span>

<span data-ttu-id="ec6b1-112">내보내기를 설정하거나 편집하려면 연결을 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="ec6b1-113">연결은 귀하의 [사용자 역할](permissions.md)에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="ec6b1-114">관리자는 모든 연결에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-114">Administrators have access to all connections.</span></span> <span data-ttu-id="ec6b1-115">내보내기를 설정할 때 새 연결을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="ec6b1-116">기여자는 특정 연결에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="ec6b1-117">관리자가 연결을 구성하고 공유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="ec6b1-118">자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="ec6b1-119">보기 권한자는 기존 내보내기를 볼 수만 있고 만들 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="ec6b1-120">**데이터** > **내보내기** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ec6b1-121">**내보내기 추가** 를 선택하여 새 내보내기 대상을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="ec6b1-122">**내보내기 설정** 창에서 사용할 연결을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="ec6b1-123">[연결](connections.md)은 관리자가 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="ec6b1-124">필요한 세부 정보를 제공하고 **저장** 을 선택하여 내보내기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="ec6b1-125">내보내기 편집</span><span class="sxs-lookup"><span data-stu-id="ec6b1-125">Edit an export</span></span>

1. <span data-ttu-id="ec6b1-126">편집할 내보내기 대상의 세로 줄임표를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="ec6b1-127">드롭다운 메뉴에서 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="ec6b1-128">업데이트할 값을 변경하고 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="ec6b1-129">내보내기 및 내보내기 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="ec6b1-129">View Exports and export details</span></span>

<span data-ttu-id="ec6b1-130">내보내기 대상을 만들면 **데이터** > **내보내기** 에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="ec6b1-131">모든 사용자는 공유된 데이터와 최신 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="ec6b1-132">**데이터** > **내보내기** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ec6b1-133">편집 권한이 없는 사용자는 **편집** 대신 **보기** 를 선택하여 내보내기 세부 사항을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="ec6b1-134">이 측면 창에는 이 내보내기 설정이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="ec6b1-135">편집 권한이 없으면 값을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="ec6b1-136">**닫기** 를 선택하여 내보내기 페이지로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="ec6b1-137">주문형으로 내보내기 실행</span><span class="sxs-lookup"><span data-stu-id="ec6b1-137">Run exports on demand</span></span>

<span data-ttu-id="ec6b1-138">내보내기를 구성하면 내보내기는 작동하는 연결이 있는 한 모든 [예약된 새로 고침](system.md#schedule-tab)을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="ec6b1-139">예약된 새로 고침을 기다리지 않고 데이터를 내보내려면 **데이터** > **내보내기** 로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="ec6b1-140">이때 다음 두 가지 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-140">You have two options:</span></span>

- <span data-ttu-id="ec6b1-141">모든 내보내기를 실행하려면 명령 모음에서 **모두 실행** 을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="ec6b1-142">단일 내보내기를 실행하려면 목록 항목에서 줄임표(...)를 선택한 다음 **실행** 을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="ec6b1-143">내보내기 제거</span><span class="sxs-lookup"><span data-stu-id="ec6b1-143">Remove an Export</span></span>

1. <span data-ttu-id="ec6b1-144">**데이터** > **내보내기** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ec6b1-145">제거할 내보내기 대상의 세로 줄임표를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="ec6b1-146">드롭다운 메뉴에서 **제거** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="ec6b1-147">확인 화면에서 **제거** 를 선택하여 제거를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6b1-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
