---
title: Power Apps 커넥터
description: Power Apps 및 Power Automate와 연결합니다.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3fa91553fd50a22ab62b5a2b1e3f13b9483776a8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598163"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="0b790-103">Microsoft Power Apps 커넥터(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="0b790-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="0b790-104">통합된 고객 프로필을 Power Apps를 사용하여 개인화된 앱으로 가져오기.</span><span class="sxs-lookup"><span data-stu-id="0b790-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="0b790-105">Power Apps 및 Dynamics 365 Customer Insights 연결</span><span class="sxs-lookup"><span data-stu-id="0b790-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="0b790-106">Customer Insights는 [Power Apps에서 사용 가능한 많은 데이터 소스](/powerapps/maker/canvas-apps/working-with-data-sources) 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="0b790-106">Customer Insights is one of the many [available sources for data in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="0b790-107">[앱에 데이터 연결을 추가](/powerapps/maker/canvas-apps/add-data-connection)하는 방법을 알아보려면 Power Apps 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0b790-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="0b790-108">또한 [Power Apps가 위임을 사용하여 캔버스 앱에서 대규모 데이터 집합을 처리하는 방법](/powerapps/maker/canvas-apps/delegation-overview)을 검토하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0b790-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="0b790-109">사용 가능한 엔터티</span><span class="sxs-lookup"><span data-stu-id="0b790-109">Available entities</span></span>

<span data-ttu-id="0b790-110">Customer Insights를 데이터 연결로 추가한 후 Power Apps에서 다음 엔터티를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b790-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="0b790-111">고객: [통합 고객 프로필](customer-profiles.md)의 데이터를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0b790-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="0b790-112">UnifiedActivity: 앱에 [활동 타임라인](activities.md)을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0b790-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="0b790-113">제한 사항</span><span class="sxs-lookup"><span data-stu-id="0b790-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="0b790-114">검색 가능한 엔터티</span><span class="sxs-lookup"><span data-stu-id="0b790-114">Retrievable entities</span></span>

<span data-ttu-id="0b790-115">Power Apps 커넥터에서 **고객**, **통합 활동**, **세그먼트** 엔터티만 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b790-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="0b790-116">다른 엔터티는 기본 커넥터가 Power Automate 내의 트리거를 통해 지원하기 때문에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b790-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="0b790-117">위임</span><span class="sxs-lookup"><span data-stu-id="0b790-117">Delegation</span></span>

<span data-ttu-id="0b790-118">고객 엔터티 및 통합 활동 엔터티에 대한 위임 작업.</span><span class="sxs-lookup"><span data-stu-id="0b790-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="0b790-119">**고객** 엔터티에 대한 위임: 이 엔터티에 대한 위임을 사용하려면 필드가 [검색 및 필터 색인](search-filter-index.md)에 인덱싱되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b790-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="0b790-120">**통합 활동** 위임:이 엔티티에 대한 위임은 **ActivityId** 와 **고객 ID** 필드에서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="0b790-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="0b790-121">위임에 대한 자세한 내용은 [Power Apps 위임 가능한 기능 및 작업](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b790-121">For more information about delegation, see [Power Apps delegable functions and operations](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="0b790-122">갤러리 컨트롤 예</span><span class="sxs-lookup"><span data-stu-id="0b790-122">Example gallery control</span></span>

<span data-ttu-id="0b790-123">예를 들어, 고객 프로필을 [갤러리 컨트롤](/powerapps/maker/canvas-apps/add-gallery)에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0b790-123">For example, you add customer profiles to a [gallery control](/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="0b790-124">빌드 중인 앱에 **갤러리** 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0b790-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0b790-125">![갤러리 요소 추가](media/connector-powerapps9.png "갤러리 요소 추가")</span><span class="sxs-lookup"><span data-stu-id="0b790-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="0b790-126">**고객** 을 항목의 데이터 원본을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0b790-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0b790-127">![데이터 원본 선택](media/choose-datasource-powerapps.png "데이터 원본 선택")</span><span class="sxs-lookup"><span data-stu-id="0b790-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="0b790-128">오른쪽의 데이터 패널을 변경하여 갤러리에 표시할 고객 엔터티 필드를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b790-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="0b790-129">갤러리에서 선택한 고객의 필드를 표시하려면 레이블: **{Name_of_the_gallery}.Selected.{property_name}** 의 텍스트 속성을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0b790-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="0b790-130">예: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="0b790-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="0b790-131">고객의 통합 타임라인을 표시하려면 갤러리 요소를 추가하고 항목 속성: **Filter('UnifiedActivity', CustomerId = {Customer_Id})** 을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0b790-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="0b790-132">예: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="0b790-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]