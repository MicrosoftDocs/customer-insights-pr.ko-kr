---
title: 내보내기 대상
description: 데이터를 내보내고 내보내기 대상을 관리합니다.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643871"
---
# <a name="export-destinations-preview"></a><span data-ttu-id="57f43-103">내보내기 대상(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="57f43-103">Export destinations (preview)</span></span>

<span data-ttu-id="57f43-104">**내보내기 대상** 페이지에는 데이터를 내보내도록 설정한 모든 위치가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="57f43-104">The **Export destinations** page shows you all locations you've set up to export data to.</span></span> <span data-ttu-id="57f43-105">내보낼 새 대상을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f43-105">You can also add new destinations for export.</span></span> <span data-ttu-id="57f43-106">또한 현재 사용 가능한 내보내기 옵션을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="57f43-106">Additionally, it shows export currently available options.</span></span> <span data-ttu-id="57f43-107">빠른 개요, 설명 및 각 확장성 옵션으로 수행 할 수 있는 작업을 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="57f43-107">Get a quick overview, description, and find out what you can do with each extensibility option.</span></span> <span data-ttu-id="57f43-108">비즈니스와 관련된 지원되는 앱으로 통합 프로필, 측정 값 및 세그먼트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="57f43-108">Export unified profiles, measures, and segments to supported apps relevant for your business.</span></span>

<span data-ttu-id="57f43-109">**관리자** > **내보내기 대상** 으로 이동하여 다음과 같은 확장성 옵션을 찾으십시오.</span><span class="sxs-lookup"><span data-stu-id="57f43-109">Go to **Admin** > **Export destinations** to find the following extensibility options:</span></span>

- [<span data-ttu-id="57f43-110">Dynamics 365 고객 카드 추가 기능</span><span class="sxs-lookup"><span data-stu-id="57f43-110">Dynamics 365 Customer Card Add-in</span></span>](customer-card-add-in.md)
- [<span data-ttu-id="57f43-111">Facebook 광고 관리자 커넥터</span><span class="sxs-lookup"><span data-stu-id="57f43-111">Facebook Ads Manager connector</span></span>](export-facebook.md)
- [<span data-ttu-id="57f43-112">Power Automate 커넥터</span><span class="sxs-lookup"><span data-stu-id="57f43-112">Power Automate connector</span></span>](export-power-automate.md)
- [<span data-ttu-id="57f43-113">Power Apps 커넥터</span><span class="sxs-lookup"><span data-stu-id="57f43-113">Power Apps connector</span></span>](export-power-apps.md)
- [<span data-ttu-id="57f43-114">Power BI 커넥터</span><span class="sxs-lookup"><span data-stu-id="57f43-114">Power BI connector</span></span>](export-power-bi.md)
- [<span data-ttu-id="57f43-115">DotDigital</span><span class="sxs-lookup"><span data-stu-id="57f43-115">DotDigital</span></span>](export-dotdigital.md)
- [<span data-ttu-id="57f43-116">Dynamics 365 for Sales</span><span class="sxs-lookup"><span data-stu-id="57f43-116">Dynamics 365 Sales</span></span>](export-dynamics365-sales.md)
- [<span data-ttu-id="57f43-117">Dynamics 365 Marketing</span><span class="sxs-lookup"><span data-stu-id="57f43-117">Dynamics 365 Marketing</span></span>](export-dynamics365-marketing.md)
- [<span data-ttu-id="57f43-118">Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="57f43-118">Azure Blob Storage</span></span>](export-azure-blob-storage.md)
- [<span data-ttu-id="57f43-119">LiveRamp&reg; 커넥터</span><span class="sxs-lookup"><span data-stu-id="57f43-119">LiveRamp&reg; connector</span></span>](export-liveramp.md)
- [<span data-ttu-id="57f43-120">Microsoft Teams용 봇</span><span class="sxs-lookup"><span data-stu-id="57f43-120">Bot for Microsoft Teams</span></span>](export-teams-bot.md)
- [<span data-ttu-id="57f43-121">Mailchimp</span><span class="sxs-lookup"><span data-stu-id="57f43-121">Mailchimp</span></span>](export-mailchimp.md)
- [<span data-ttu-id="57f43-122">Customer Insights API</span><span class="sxs-lookup"><span data-stu-id="57f43-122">Customer Insights API</span></span>](apis.md)

## <a name="add-a-new-export-destination"></a><span data-ttu-id="57f43-123">새 내보내기 대상 추가</span><span class="sxs-lookup"><span data-stu-id="57f43-123">Add a new export destination</span></span>

<span data-ttu-id="57f43-124">내보내기 대상을 추가하려면 [관리자 권한](permissions.md)이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57f43-124">To add export destinations, you have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="57f43-125">Microsoft 서비스로 내보내는 경우 두 서비스가 모두 같은 조직에 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="57f43-125">If you export to Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="57f43-126">**관리자** > **내보내기 대상** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="57f43-126">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="57f43-127">**내 내보내기 대상** 탭으로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="57f43-127">Switch to the **My export destinations** tab.</span></span>

1. <span data-ttu-id="57f43-128">**내보내기 추가** 로 이동하여 새 내보내기 대상을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="57f43-128">Select **Add destination** to create a new export destination.</span></span>

1. <span data-ttu-id="57f43-129">**대상 추가** 창에서 드롭다운에서 내보내기 대상의 **유형** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="57f43-129">In the **Add destination** pane, select the **Type** of export destination in the drop-down.</span></span>

1. <span data-ttu-id="57f43-130">필요한 세부 사항을 제공하고 **다음** 을 선택해 내보내기 대상을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="57f43-130">Provide the required details and select **Next** to create the export destination.</span></span>

<span data-ttu-id="57f43-131">**검색** 탭의 타일에서 **설정** 을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f43-131">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

## <a name="view-export-destinations"></a><span data-ttu-id="57f43-132">내보내기 대상 보기</span><span class="sxs-lookup"><span data-stu-id="57f43-132">View Export destinations</span></span>

<span data-ttu-id="57f43-133">내보내기 대상을 만든 후에는 **내 내보내기 대상** 탭의 테이블에서 찾을 수 있습니다. 이 테이블에는 세 개의 열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f43-133">After creating export destinations, you'll find them in a table on the **My export destinations** tab. This table has three columns:</span></span>

- <span data-ttu-id="57f43-134">**표시 이름**: 대상을 만들 때 입력한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="57f43-134">**Display name**: The name you entered when creating the destination.</span></span>
- <span data-ttu-id="57f43-135">**유형**: 대상을 만들 때 설정한 내보내기 대상 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="57f43-135">**Type**: The export destination type you set when creating the destination.</span></span>
- <span data-ttu-id="57f43-136">**만든 날짜**: 대상을 만든 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="57f43-136">**Created**: The date you created the destination.</span></span>

## <a name="edit-an-export-destination"></a><span data-ttu-id="57f43-137">내보내기 대상 편집</span><span class="sxs-lookup"><span data-stu-id="57f43-137">Edit an export destination</span></span>

1. <span data-ttu-id="57f43-138">편집할 내보내기 대상의 세로 줄임표를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="57f43-138">Select the vertical ellipsis for the Export destination you want to edit.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="57f43-139">![세로 줄임표](media/export-destinations-page-ellipsis.png "세로 줄임표")</span><span class="sxs-lookup"><span data-stu-id="57f43-139">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

1. <span data-ttu-id="57f43-140">드롭다운 메뉴에서 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="57f43-140">Select **Edit** from the dropdown menu.</span></span>

1. <span data-ttu-id="57f43-141">업데이트가 필요한 값을 변경하고 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="57f43-141">Change the values that require update and select **Save**.</span></span>

## <a name="export-data-on-demand"></a><span data-ttu-id="57f43-142">주문 시 데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="57f43-142">Export data on demand</span></span>

<span data-ttu-id="57f43-143">내보내기 대상에 대한 커넥터를 구성한 후에는 내보내기가 [예정된 새로 고침](system.md#schedule-tab)으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="57f43-143">After configuring a connector for an export destination, exports will run with every [scheduled refresh](system.md#schedule-tab).</span></span>

<span data-ttu-id="57f43-144">예약된 새로 고침을 기다리지 않고 데이터를 내보내려면 **관리자** > **내보내기 대상** 에서 **내 내보내기 목적** 탭으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="57f43-144">To export data without waiting for a scheduled refresh, go the **My export destinations** tab on **Admin** > **Export destinations**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="57f43-145">![세로 줄임표](media/export-destinations-page-ellipsis.png "세로 줄임표")</span><span class="sxs-lookup"><span data-stu-id="57f43-145">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

- <span data-ttu-id="57f43-146">목록 위의 **내보내기** 를 선택해 모든 내보내기 대상으로 동시에 내보내기를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="57f43-146">Select **Export** above the list to run the export to all export destinations simultaneously.</span></span>
- <span data-ttu-id="57f43-147">목록 항목 뒤의 줄임표(...)를 선택한 다음 **내보내기** 옵션을 선택해 단일 내보내기 대상에 대해 내보내기를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="57f43-147">Select the ellipsis (...) after a list item and then choose the **Export** option to run the export for a single export destination.</span></span>

## <a name="remove-an-export-destination"></a><span data-ttu-id="57f43-148">내보내기 대상 제거</span><span class="sxs-lookup"><span data-stu-id="57f43-148">Remove an Export destination</span></span>

<span data-ttu-id="57f43-149">내보내기 대상을 제거하려면 기본 **내보내기 대상** 페이지에서 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="57f43-149">To remove an Export destination, start from the main **Export destinations** page.</span></span>

1. <span data-ttu-id="57f43-150">제거할 내보내기 대상의 세로 줄임표를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="57f43-150">Select the vertical ellipsis for the Export destination you want to remove.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="57f43-151">![세로 줄임표](media/export-destinations-page-ellipsis.png "세로 줄임표")</span><span class="sxs-lookup"><span data-stu-id="57f43-151">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

2. <span data-ttu-id="57f43-152">드롭다운 메뉴에서 **제거** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="57f43-152">Select **Remove** from the dropdown menu.</span></span>

3. <span data-ttu-id="57f43-153">확인 화면에서 **제거** 를 선택하여 제거를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="57f43-153">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>
