---
title: Common Data Model의 Customer Insights 엔터티 스키마
description: Common Data Model에서 엔터티로 작업합니다.
ms.date: 04/17/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 6667e411a1b56e13105a6b59b7b5d249bc8141ea
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596369"
---
# <a name="entity-schemas-in-common-data-model"></a><span data-ttu-id="e3e3e-103">Common Data Model의 엔터티 스키마</span><span class="sxs-lookup"><span data-stu-id="e3e3e-103">Entity schemas in Common Data Model</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="e3e3e-104">[Common Data Model](/common-data-model/)은 선언적 사양이며, 여러 비즈니스 및 생산성 애플리케이션에서 일반적으로 사용되는 개념과 활동을 나타내는 표준 엔터티의 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="e3e3e-104">[Common Data Model](/common-data-model/) is a declarative specification, and a definition of standard entities that represent commonly used concepts and activities across business and productivity applications.</span></span> <span data-ttu-id="e3e3e-105">이 모델은 관측 및 분석 데이터로 확장되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3e3e-105">This model is being extended to observational and analytical data as well.</span></span> <span data-ttu-id="e3e3e-106">Common Data Model은 거래처, 사업부, 서비스 케이스, 연락처, 잠재 고객, 영업 기회, 제품 등과 같은 잘 정의되고 확장 가능한 모듈식 비즈니스 엔터티뿐 아니라 활동이나 서비스 수준 약정 같은 공급업체, 작업자, 고객과의 상호 작용을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e3e3e-106">Common Data Model provides well-defined, modular, and extensible business entities—such as Account, Business Unit, Case, Contact, Lead, Opportunity, and Product—as well as interactions with vendors, workers, and customers—such as activities and service level agreements.</span></span> <span data-ttu-id="e3e3e-107">누구나 Common Data Model 정의를 구축하고 확장하여 추가 비즈니스별 아이디어를 포착할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3e3e-107">Anyone can build on and extend Common Data Model definitions to capture additional business-specific ideas.</span></span>

<span data-ttu-id="e3e3e-108">이 공유 데이터 모델을 통해 응용 프로그램과 데이터 통합자가 통합된 데이터 정의를 제공하여 보다 쉽게 공동 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3e3e-108">This shared data model allows applications and data integrators to collaborate more easily by providing a unified definition of data.</span></span> <span data-ttu-id="e3e3e-109">Common Data Model에는 표준 엔터티, 관계, 계층 구조, 특성 등이 포함된 풍부한 메타데이터 시스템이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3e3e-109">Common Data Model includes a rich metadata system with standard entities, relationships, hierarchies, traits, and more.</span></span> <span data-ttu-id="e3e3e-110">Dynamics 365 앱에서 시작되었으며 260개가 넘는 표준 엔터티가 있는 GitHub에서 오픈 소스로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3e3e-110">It originated from Dynamics 365 apps and is open-sourced on GitHub with over 260 standard entities.</span></span> <span data-ttu-id="e3e3e-111">내부 및 외부 파트너의 대규모 시스템은 Common Data Model에 산업별 개념을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e3e3e-111">A large system of internal and external partners contributes industry-specific concepts to Common Data Model.</span></span>

<span data-ttu-id="e3e3e-112">오늘날 Power BI 데이터 흐름 및 Azure 데이터 서비스 등 여러 시스템 및 플랫폼이 Common Data Model을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="e3e3e-112">Multiple systems and platforms implement Common Data Model today, including Power BI dataflows and Azure Data Services.</span></span> <span data-ttu-id="e3e3e-113">Common Data Service, Dynamics 365, Power Apps, Power BI, 그리고 출시 예정인 Azure 데이터 서비스에서 이미 지원되며, [Open Data Initiative](https://www.microsoft.com/open-data-initiative)에 직접 가치를 더합니다.</span><span class="sxs-lookup"><span data-stu-id="e3e3e-113">It's already supported in the Common Data Service, Dynamics 365, Power Apps, Power BI, and upcoming Azure data services, directly accruing value towards the [Open Data Initiative](https://www.microsoft.com/open-data-initiative).</span></span>

## <a name="customer-insights-entity-schemas"></a><span data-ttu-id="e3e3e-114">Customer Insights 엔터티 스키마</span><span class="sxs-lookup"><span data-stu-id="e3e3e-114">Customer Insights entity schemas</span></span>

<span data-ttu-id="e3e3e-115">고객에 대한 360도 뷰를 확립하고 확장성을 위해 Common Data Model에서 Customer Insights 모델을 사용할 수 있도록 하기 위해 다음 엔터티 스키마를 공개했습니다.</span><span class="sxs-lookup"><span data-stu-id="e3e3e-115">To establish a 360-degree view of the customer and make Customer Insights models available in Common Data Model for extensibility, we've published the following entity schemas:</span></span>

| <span data-ttu-id="e3e3e-116">엔터티</span><span class="sxs-lookup"><span data-stu-id="e3e3e-116">Entity</span></span> | <span data-ttu-id="e3e3e-117">설명</span><span class="sxs-lookup"><span data-stu-id="e3e3e-117">Description</span></span> |
|---------|---------|
|[<span data-ttu-id="e3e3e-118">CustomerActivity</span><span class="sxs-lookup"><span data-stu-id="e3e3e-118">CustomerActivity</span></span>](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | <span data-ttu-id="e3e3e-119">비즈니스에 대한 관찰 가치가 있는 사용자가 수행한 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="e3e3e-119">An activity performed by a user that has observational value to the business.</span></span> |
|[<span data-ttu-id="e3e3e-120">CustomerProfile</span><span class="sxs-lookup"><span data-stu-id="e3e3e-120">CustomerProfile</span></span>](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | <span data-ttu-id="e3e3e-121">비즈니스 활동을 수행하거나 수행할 가능성이 있는 개인 또는 조직.</span><span class="sxs-lookup"><span data-stu-id="e3e3e-121">A person or organization that either performed, or has the potential to engage in, business activities.</span></span> |
|[<span data-ttu-id="e3e3e-122">MeasureDefinition</span><span class="sxs-lookup"><span data-stu-id="e3e3e-122">MeasureDefinition</span></span>](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | <span data-ttu-id="e3e3e-123">0개 이상의 차원으로 분할된 KPI 정의(예: 월간 활성 사용자, 총 고객 지출, 평균 고객 확보 비용)</span><span class="sxs-lookup"><span data-stu-id="e3e3e-123">Definition of KPIs partitioned by zero or more dimensions (such as Monthly Active Users, Total Spend By Customer, Average Customer Acquisition Cost)</span></span> |
|[<span data-ttu-id="e3e3e-124">세그먼트</span><span class="sxs-lookup"><span data-stu-id="e3e3e-124">Segment</span></span>](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | <span data-ttu-id="e3e3e-125">공통된 특성을 가진 구성원 그룹을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e3e3e-125">Defines a group of members with common traits.</span></span> |
|[<span data-ttu-id="e3e3e-126">SegmentMembership</span><span class="sxs-lookup"><span data-stu-id="e3e3e-126">SegmentMembership</span></span>](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | <span data-ttu-id="e3e3e-127">주어진 세그먼트에 참여하는 구성원.</span><span class="sxs-lookup"><span data-stu-id="e3e3e-127">Members participating in a given segment.</span></span> |

<span data-ttu-id="e3e3e-128">자세한 내용은 [Common Data Model의 Customer Insights 엔터티 스키마](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview)에 대한 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e3e3e-128">For more information, see the documentation about the [Customer Insights entity schemas in Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).</span></span>

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a><span data-ttu-id="e3e3e-129">Common Data Model 엔터티 탐색기를 사용하여 엔터티 보기</span><span class="sxs-lookup"><span data-stu-id="e3e3e-129">View entities using the Common Data Model Entity Navigator</span></span>

<span data-ttu-id="e3e3e-130">[Common Data Model 엔터티 탐색기](https://microsoft.github.io/CDM/)에서 엔터티를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3e3e-130">You can view entities in the [Common Data Model Entity Navigator](https://microsoft.github.io/CDM/).</span></span> <span data-ttu-id="e3e3e-131">**GitHub에서 로드!**</span><span class="sxs-lookup"><span data-stu-id="e3e3e-131">Select the **Load from GitHub!**</span></span> <span data-ttu-id="e3e3e-132">버튼을 클릭하고 **foundationCommon** > **crmCommon** > **solutions** > **customerInsights** 로 이동하여 Customer Insights 엔터티 및 그 정의 목록을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3e3e-132">button and navigate to **foundationCommon** > **crmCommon** > **solutions** > **customerInsights** where you'll find the list of Customer Insights entities and their definitions.</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="e3e3e-133">![CustomerActivity 엔터티를 보여주는 CDM 엔터티 탐색기](media/CDM-entity-navigator.png "CustomerActivity 엔터티를 보여주는 CDM 엔터티 탐색기")</span><span class="sxs-lookup"><span data-stu-id="e3e3e-133">![CDM Entity Navigator showing CustomerActivity entity](media/CDM-entity-navigator.png "CDM Entity Navigator showing CustomerActivity entity")</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]