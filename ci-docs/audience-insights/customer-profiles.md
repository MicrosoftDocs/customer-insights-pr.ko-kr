---
title: 고객 프로필 보기
description: 통합된 고객 데이터를 조합하여 볼 수 있습니다.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 433e6ceda0ec7827bd672cff40f895d7719561df
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896335"
---
# <a name="customer-profiles"></a><span data-ttu-id="98e7f-103">고객 프로필</span><span class="sxs-lookup"><span data-stu-id="98e7f-103">Customer profiles</span></span>

<span data-ttu-id="98e7f-104">**고객** 페이지에는 [모든 데이터 원본](data-sources.md)에서 수집된 프로필 데이터를 기반으로 고객의 결합된 보기를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="98e7f-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="98e7f-105">[통합된 고객 엔터티를 만든](data-unification.md) 후 고객 프로필을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98e7f-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="98e7f-106">데이터 통합 프로세스를 완료하여 고객에 대한 풍부한 보기를 확보해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e7f-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="98e7f-107">또한 이 페이지에서 고객을 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98e7f-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="98e7f-108">고객은 개인 또는 조직(미리 보기)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98e7f-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="98e7f-109">각 고객 또는 조직 프로필은 타일로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="98e7f-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="98e7f-110">타일을 선택하여 특정 고객 또는 조직에 대한 추가 정보를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="98e7f-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="98e7f-111">추가 레코드를 보려면 페이지 하단의 페이지 매기기 컨트롤을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="98e7f-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="98e7f-112">![B2C 고객 프로필](media/profiles-customers.png "B2C 고객 프로필")</span><span class="sxs-lookup"><span data-stu-id="98e7f-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="98e7f-113">조직(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="98e7f-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="98e7f-114">![B2B 고객 프로필](media/profile-customers-b2b.png "B2B 고객 프로필")</span><span class="sxs-lookup"><span data-stu-id="98e7f-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="98e7f-115">탐색에서 **고객** 을 선택할 때 타일이 표시되지 않으면 관리자는 **검색 및 필터 색인** 에서 [검색 가능한 속성을 하나 이상 정의](search-filter-index.md)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e7f-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="98e7f-116">고객 검색</span><span class="sxs-lookup"><span data-stu-id="98e7f-116">Search for customers</span></span>

<span data-ttu-id="98e7f-117">검색 상자에 이름이나 다른 특성을 입력하여 고객을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="98e7f-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="98e7f-118">검색은 데이터 통합 프로세스 중에 만든 고객 프로필 엔터티 내에서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="98e7f-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="98e7f-119">관리자는 **검색 및 필터 색인** 페이지를 사용하여 검색 가능한 특성을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98e7f-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="98e7f-120">자세한 내용은 [검색 및 필터 색인 관리](search-filter-index.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="98e7f-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="98e7f-121">고객 필터링</span><span class="sxs-lookup"><span data-stu-id="98e7f-121">Filter customers</span></span>

<span data-ttu-id="98e7f-122">고객 프로필 엔터티 필드별로 고객을 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98e7f-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="98e7f-123">검색과 마찬가지로 관리자는 먼저 **검색 및 필터 색인** 페이지를 사용하여 필드를 필터링 가능한 필드로 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e7f-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="98e7f-124">**고객** 페이지에서 **필터** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="98e7f-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="98e7f-125">고객을 필터링할 특성 옆에 있는 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="98e7f-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="98e7f-126">![고객 프로필](media/profiles-customers3.png "고객 프로필")</span><span class="sxs-lookup"><span data-stu-id="98e7f-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="98e7f-127">**고객** 페이지에서 **필터 지우기** 를 선택하여 필터를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="98e7f-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="98e7f-128">고객 정보 페이지</span><span class="sxs-lookup"><span data-stu-id="98e7f-128">Customer details page</span></span>

<span data-ttu-id="98e7f-129">고객 타일 중 하나를 선택하여 **고객 정보 페이지** 를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="98e7f-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="98e7f-130">이 보기에는 선택된 고객의 통합된 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="98e7f-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="98e7f-131">고객 정보에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="98e7f-131">Customer details include:</span></span>

-   <span data-ttu-id="98e7f-132">**고객 프로필 타일**: 이 타일에는 통합된 고객 프로필 엔터티의 다양한 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="98e7f-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="98e7f-133">이러한 세부 정보에는 이메일 주소, 이름, 도시 등이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98e7f-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="98e7f-134">**잠재적 관심사, 잠재적 브랜드:** 자사 보강을 구성했는지 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="98e7f-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="98e7f-135">이 고객과 유사한 프로필을 가진 고객이 가질 수 있는 브랜드에 대한 잠재적인 관심사 및 친밀도를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="98e7f-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="98e7f-136">자세한 내용은 [브랜드 및 관심 선호도로 고객 프로필 강화](enrichment-microsoft.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="98e7f-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft.md).</span></span>

-   <span data-ttu-id="98e7f-137">**측정값:** 특정 유형의 측정값(고객 특성 측정값)을 하나 이상 구성했는지 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="98e7f-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="98e7f-138">여기에는 개별 고객 수준에서 고객에 대한 계산된 KPI가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="98e7f-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="98e7f-139">자세한 내용은 [측정값 정의 및 관리](measures.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="98e7f-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="98e7f-140">**활동 시간 표시줄:** 활동을 구성했는지 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="98e7f-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="98e7f-141">시간 표시줄 보기에는 가장 최근 활동부터 시작하여 이 고객의 시간순으로 정렬된 활동이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="98e7f-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="98e7f-142">자세한 내용은 [고객 활동](activities.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="98e7f-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="98e7f-143">**고객으로 돌아가기** 를 선택하여 고객 검색 페이지로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="98e7f-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="98e7f-144">다음 단계</span><span class="sxs-lookup"><span data-stu-id="98e7f-144">Next steps</span></span>

<span data-ttu-id="98e7f-145">[더 많은 데이터 원본 추가](data-sources.md) 또는 [고객 분류 작성](segments.md).</span><span class="sxs-lookup"><span data-stu-id="98e7f-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]