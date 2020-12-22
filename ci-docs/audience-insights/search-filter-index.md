---
title: 고객 프로필 검색 및 필터링
description: 통합 고객 프로필에 대한 정보를 신속하게 찾고 지정된 속성을 필터링합니다.
ms.date: 04/16/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1842ad333c23bb155abc89167556163ae79cdd34
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406310"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="17277-103">고객 프로필: 색인 검색 및 필터링</span><span class="sxs-lookup"><span data-stu-id="17277-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="17277-104">고객 데이터를 통합한 결과는 전체 고객 기반에 대한 통일된 보기를 제공하는 고객 프로필 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="17277-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="17277-105">[특정 고객 또는 고객 그룹에 대한 정보를 빠르게 찾을 수 있도록](customer-profiles.md) **고객** 페이지에서 **검색** 및 **필터** 기능을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17277-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="17277-106">관리자가 **검색 및 필터 색인** 페이지에서 특성을 편집하여 사용자가 검색 및 필터링할 수 있는 특성을 편집하는 방법을 계속 읽으십시오.</span><span class="sxs-lookup"><span data-stu-id="17277-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="17277-107">![검색 필터](media/search-filter.png "검색 필터")</span><span class="sxs-lookup"><span data-stu-id="17277-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="17277-108">필드 추가 및 특성 지정</span><span class="sxs-lookup"><span data-stu-id="17277-108">Add fields and specify attributes</span></span>

<span data-ttu-id="17277-109">검색 가능한 특성을 관리자로 처음 정의하는 경우 먼저 색인화된 필드를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17277-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="17277-110">**고객** 페이지에서 사용자가 고객을 검색하고 필터링할 수 있는 모든 특성을 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="17277-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="17277-111">데이터 통합 프로세스 중에 작성한 고객 프로필 엔터티에 존재하는 특성만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17277-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="17277-112">**고객** 페이지를 열고 **검색 및 필터 색인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="17277-112">Open the **Customers** page and select **Search & filter index**.</span></span>

> [!NOTE]
> <span data-ttu-id="17277-113">맵 페이지에 정의된 다음 의미 유형에서 고객 엔터티의 사용 가능한 특성에 대한 기본 검색 색인 구성을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="17277-113">We create a default search index configuration on the available attributes in the Customer entity from the following semantic types as defined on the Map page.</span></span>
> - <span data-ttu-id="17277-114">개인 이름, 성, 중간 이름, 전체 이름</span><span class="sxs-lookup"><span data-stu-id="17277-114">Person First name, Last name, Middle name, Full Name</span></span>
> - <span data-ttu-id="17277-115">조직 이름</span><span class="sxs-lookup"><span data-stu-id="17277-115">Organization Name</span></span>
> - <span data-ttu-id="17277-116">전자 메일 주소</span><span class="sxs-lookup"><span data-stu-id="17277-116">Email address</span></span>
> - <span data-ttu-id="17277-117">전화 번호</span><span class="sxs-lookup"><span data-stu-id="17277-117">Phone number</span></span>
> - <span data-ttu-id="17277-118">위치 정보</span><span class="sxs-lookup"><span data-stu-id="17277-118">Location information</span></span>

2. <span data-ttu-id="17277-119">색인화된 필드를 지정하려면 **+ 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="17277-119">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="17277-120">색인 필드로 추가할 목록에서 특성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="17277-120">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="17277-121">**추가** 를 선택하면 언제든지 더 많은 특성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17277-121">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="17277-122">또한 **제거** 기호를 선택하여 선택한 특성을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17277-122">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="17277-123">색인화된 고객 필드 테이블 탐색</span><span class="sxs-lookup"><span data-stu-id="17277-123">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="17277-124">다음 정보가 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17277-124">The following information is presented in the table.</span></span>

- <span data-ttu-id="17277-125">**이름**: 고객 프로필 엔터티에 나타나는 특성 이름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="17277-125">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="17277-126">**데이터 형식**: 데이터 형식이 문자열, 숫자 또는 날짜인지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="17277-126">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="17277-127">**검색에 포함**: **검색** 을 사용하여 **고객** 페이지에서 이 특성을 고객 검색에 사용할 수 있는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="17277-127">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="17277-128">**필터 추가**: **고객** 페이지에서 이 특성을 필터링에 사용하는 방법을 정의하기 위한 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="17277-128">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="17277-129">주어진 특성에 대한 필터링 옵션 편집</span><span class="sxs-lookup"><span data-stu-id="17277-129">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="17277-130">**고객** 페이지의 **필터** 메뉴에는 다양한 수의 특성 수준이 포함될 수 있습니다(예: 고객별로 필터링하기 위한 다른 연령 그룹).</span><span class="sxs-lookup"><span data-stu-id="17277-130">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="17277-131">**검색 및 필터 색인** 페이지에서 주어진 특성에 대해 **필터 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="17277-131">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="17277-132">결과 수와 결과 순서를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17277-132">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="17277-133">특성의 데이터 형식에 따라 다음 창 중 하나가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="17277-133">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="17277-134">문자열 유형 특성: **문자열 필터 옵션** 창 및 구성할 주문 정책에 원하는 결과 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="17277-134">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="17277-135">숫자 유형 특성: **숫자 필터 옵션** 창 및 구성할 주문 정책에 포함되는 간격을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="17277-135">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="17277-136">날짜 유형 특성: **날짜 필터 옵션** 창 및 구성할 주문 정책에 포함되는 간격을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="17277-136">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="17277-137">**저장** 을 선택하여 변경 내용을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="17277-137">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="17277-138">설정을 적용할 준비가 되면 **실행** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="17277-138">Select **Run** once you're ready to apply your settings.</span></span>
