---
title: 사용자 권한 관리
description: 사용 권한 및 사용자 역할에 대해 알아봅니다.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8638489dba908d4504278916d2c28454e3ea9e18
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760381"
---
# <a name="user-permissions"></a><span data-ttu-id="725e5-103">사용자 권한</span><span class="sxs-lookup"><span data-stu-id="725e5-103">User permissions</span></span>

<span data-ttu-id="725e5-104">**권한** 페이지에서 대상 그룹 인사이트를 사용하기 위한 역할 및 권한을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-104">The **Permissions** page is where you'll set up roles and permissions for using audience insights.</span></span>

<span data-ttu-id="725e5-105">페이지를 보려면 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-105">You need to have administrator permissions to see the page.</span></span> <span data-ttu-id="725e5-106">대상 그룹 인사이트의 권한 페이지에 액세스하려면 **관리자** > **권한** 으로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="725e5-106">To access the permissions page in audience insights, go to **Admin** > **Permissions**.</span></span>

<span data-ttu-id="725e5-107">역할에는 다음 세 가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-107">There are three types of roles:</span></span>

## <a name="viewer"></a><span data-ttu-id="725e5-108">뷰어</span><span class="sxs-lookup"><span data-stu-id="725e5-108">Viewer</span></span>

- <span data-ttu-id="725e5-109">**홈** 및 **세그먼트** 페이지 내에서 인사이트와 세그먼트를 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-109">Explore insights and segments within the **Home** and **Segments** pages.</span></span>
- <span data-ttu-id="725e5-110">**고객** 페이지를 사용하여 고객 프로필을 검색하고 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-110">Search and filter customer profiles using the **Customers** page.</span></span> <span data-ttu-id="725e5-111">필드는 검색이 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-111">Fields must be searchable.</span></span>
- <span data-ttu-id="725e5-112">**보강** 페이지를 보고 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-112">View and explore the **Enrichment** page.</span></span>
- <span data-ttu-id="725e5-113">**엔터티** 페이지를 사용하여 엔터티를 탐색하고 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-113">Explore and export entities using the **Entities** page.</span></span>
- <span data-ttu-id="725e5-114">**시스템** 페이지를 사용하여 시스템 프로세스의 상태를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-114">View the status of system processes  using the **System** page.</span></span>
- <span data-ttu-id="725e5-115">**내보내기** 페이지에서 내보내기를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-115">View exports in **Exports** page.</span></span>
- <span data-ttu-id="725e5-116">**Power BI Customer Insights** 대시보드를 설치하고 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-116">Install and use the **Power BI Customer Insights** dashboard.</span></span>

## <a name="contributor"></a><span data-ttu-id="725e5-117">참가자</span><span class="sxs-lookup"><span data-stu-id="725e5-117">Contributor</span></span>

- <span data-ttu-id="725e5-118">뷰어에서 사용할 수 있는 모든 권한입니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-118">All permissions available to the Viewer.</span></span>
- <span data-ttu-id="725e5-119">**데이터 원본** 페이지를 사용하여 데이터를 로드하고 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-119">Load and transform data using the **Data sources** page.</span></span>
- <span data-ttu-id="725e5-120">통합 고객 프로필 엔터티를 만드는 *데이터 통합* 섹션(**매핑**, **일치** 및 **병합**)을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-120">Complete the *Data Unification* sections (**Map**, **Match**, and **Merge**) which result in the unified customer profile entity.</span></span>
- <span data-ttu-id="725e5-121">**관계** 및 **활동** 을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-121">Define **Relationships** and **Activities**.</span></span>
- <span data-ttu-id="725e5-122">**세그먼트** 페이지를 사용하여 세그먼트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-122">Create segments using the **Segments** page.</span></span>
- <span data-ttu-id="725e5-123">**측정값** 페이지를 사용하여 측정값을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-123">Create measures using the **Measures** page.</span></span>
- <span data-ttu-id="725e5-124">**보강** 페이지에서 구성을 관리하고 고객 프로필을 보강합니다(자사 보강만 해당).</span><span class="sxs-lookup"><span data-stu-id="725e5-124">Manage configuration and enrich customer profiles from the **Enrichment** page (for first party enrichments only).</span></span>
- <span data-ttu-id="725e5-125">기여자와 공유된 연결을 기반으로 내보내기를 관리하고 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-125">Manage and create exports based on connections shared with contributors.</span></span> <span data-ttu-id="725e5-126">[관리자가 기여자가 내보내기에 연결을 사용하도록 허용하는 방법에 대해 자세히 알아보세요.](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="725e5-126">[Learn more about how administrators allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

## <a name="administrator"></a><span data-ttu-id="725e5-127">관리자</span><span class="sxs-lookup"><span data-stu-id="725e5-127">Administrator</span></span>

- <span data-ttu-id="725e5-128">참가자가 사용할 수 있는 모든 권한입니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-128">All permissions available to the Contributor.</span></span>
- <span data-ttu-id="725e5-129">시스템 프로세스의 작업 언어 및 새로 고침 일정을 포함하여 **시스템** 페이지에서 설정을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-129">Change settings on the **System** page, including the working language and refresh schedules for your system processes.</span></span>
- <span data-ttu-id="725e5-130">**권한** 페이지를 사용하여 권한을 보고 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-130">View and add permissions using the **Permissions** page.</span></span>
- <span data-ttu-id="725e5-131">**검색 및 필터 인덱스** 페이지(**고객** 페이지를 통해 액세스할 수 있음)를 사용하여 고객 페이지에 대한 검색 및 필터 정의를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-131">Set search and filter definitions for the Customers page using the **Search & filter index** page (accessible via the **Customers** page).</span></span>
- <span data-ttu-id="725e5-132">연결을 관리하고 **연결** 페이지에서 다른 사용자 역할에 허용하세요.</span><span class="sxs-lookup"><span data-stu-id="725e5-132">Manage connections and allow them for other user roles on **Connections** page.</span></span>
- <span data-ttu-id="725e5-133">**보강** 페이지에서 구성을 관리하고 고객 프로필을 보강합니다(모든 보강용).</span><span class="sxs-lookup"><span data-stu-id="725e5-133">Manage configuration and enrich customer profiles from the **Enrichment** page (for all enrichments).</span></span>
- <span data-ttu-id="725e5-134">**내보내기** 페이지에서 내보내기를 관리하고 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-134">Manage and create exports on **Exports** page.</span></span>
- <span data-ttu-id="725e5-135">**고객 카드 추가 기능** 을 설치하고 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-135">Install and use the **Customer Card Add-in**.</span></span>
- <span data-ttu-id="725e5-136">**Power Apps 커넥터** 를 추가하고 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-136">Add and use the **Power Apps connector**.</span></span>
- <span data-ttu-id="725e5-137">[Customer Insights API](apis.md)의 사용을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-137">Enable usage of [Customer Insights APIs](apis.md).</span></span>

## <a name="assign-roles-and-permissions"></a><span data-ttu-id="725e5-138">역할 및 사용 권한 할당</span><span class="sxs-lookup"><span data-stu-id="725e5-138">Assign roles and permissions</span></span>

1. <span data-ttu-id="725e5-139">대상 그룹 인사이트에서 **관리** > **권한** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-139">In audience insights, go to **Admin** > **Permissions**.</span></span>

1. <span data-ttu-id="725e5-140">**사용자 추가** 를 선택하여 **권한 추가/편집** 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-140">Select **Add users** to open the **Add/Edit permissions** pane.</span></span>

1. <span data-ttu-id="725e5-141">**검색** 필드를 사용하여 권한을 조정하려는 Azure Active Directory 사용자 또는 그룹을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-141">Use the **Search** field to find the Azure Active Directory user or group whose permissions you want to adjust.</span></span> <span data-ttu-id="725e5-142">**역할** 을 선택하여 해당 사용자 또는 그룹에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-142">Select a **Role** to assign to that user or group.</span></span>

1. <span data-ttu-id="725e5-143">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-143">Select **Save**.</span></span> <span data-ttu-id="725e5-144">현재 환경은 권한을 변경한 그룹의 사용자 또는 구성원과 자동으로 공유됩니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-144">The current environment will automatically be shared with the user or members of the group whose permissions you've changed.</span></span> <span data-ttu-id="725e5-145">사용자는 Customer Insights 앱에 액세스하고 지정된 역할에 따라 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-145">Users can access the Customer Insights app and work according to their specified role.</span></span>

## <a name="view-current-permissions"></a><span data-ttu-id="725e5-146">현재 사용 권한 보기</span><span class="sxs-lookup"><span data-stu-id="725e5-146">View current permissions</span></span>

<span data-ttu-id="725e5-147">대상 그룹 인사이트에서 **관리자** > **권한** 으로 이동하여 현재 활성화된 역할 할당을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-147">In audience insights, go to **Admin** > **Permissions** to see what role assignments are currently active.</span></span>

- <span data-ttu-id="725e5-148">**유형** 열은 단일 사용자, 그룹 또는 응용 프로그램을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-148">The **Type** column specifies a single user, group, or application.</span></span> <span data-ttu-id="725e5-149">시스템은 개별 사용자 및 그룹을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-149">The system supports individual users and groups.</span></span>
- <span data-ttu-id="725e5-150">역할은 **역할** 열 아래에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-150">Roles are specified under the **Role** column.</span></span>
- <span data-ttu-id="725e5-151">열 제목을 선택하여 해당 열 값으로 결과를 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-151">Select any column title to sort the results by that column's value.</span></span>
- <span data-ttu-id="725e5-152">페이지 상단의 **검색** 필드를 사용하여 특정 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="725e5-152">Use the **Search** field at the top of the page to locate specific users.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
