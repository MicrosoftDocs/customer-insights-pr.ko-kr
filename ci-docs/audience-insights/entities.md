---
title: 엔터티 및 데이터 집합
description: 엔터티 페이지에서 데이터를 봅니다.
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e71c69a6207147d8cd65363d51a5fa6bbf896151
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269384"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="bf7aa-103">대상 그룹 인사이트의 엔터티</span><span class="sxs-lookup"><span data-stu-id="bf7aa-103">Entities in audience insights</span></span>

<span data-ttu-id="bf7aa-104">[데이터 원본을 구성](data-sources.md)한 후 **엔터티** 로 이동하여 수집된 데이터의 품질을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7aa-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="bf7aa-105">엔터티는 데이터 집합으로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7aa-105">Entities are considered datasets.</span></span> <span data-ttu-id="bf7aa-106">Dynamics 365 Customer Insights의 다양한 기능은 이러한 엔터티를 중심으로 구축됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf7aa-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="bf7aa-107">이를 면밀히 검토하면 해당 기능의 출력을 검증하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf7aa-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="bf7aa-108">**엔터티** 페이지는 엔터티를 나열하고 여러 열을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7aa-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="bf7aa-109">**이름**: 데이터 엔터티의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bf7aa-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="bf7aa-110">엔터티 이름 옆에 경고 기호가 표시되면 해당 엔터티의 데이터가 성공적으로 로드되지 않았음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7aa-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="bf7aa-111">**원본**: 엔터티를 수집한 데이터 소스 유형</span><span class="sxs-lookup"><span data-stu-id="bf7aa-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="bf7aa-112">**만든 사람**: 엔터티를 만든 사람의 이름</span><span class="sxs-lookup"><span data-stu-id="bf7aa-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="bf7aa-113">**만든 날짜**: 엔터티 작성 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="bf7aa-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="bf7aa-114">**업데이트한 사람**: 엔터티를 업데이트한 사람의 이름</span><span class="sxs-lookup"><span data-stu-id="bf7aa-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="bf7aa-115">**마지막 업데이트 날짜**: 엔터티의 마지막 업데이트 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="bf7aa-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="bf7aa-116">**마지막 새로 고침**: 마지막으로 데이터를 새로 고친 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="bf7aa-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="bf7aa-117">특정 엔터티의 데이터 탐색</span><span class="sxs-lookup"><span data-stu-id="bf7aa-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="bf7aa-118">엔터티를 선택하여 해당 엔터티에 포함된 다른 필드와 레코드를 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7aa-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bf7aa-119">![엔터티 선택](media/data-manager-entities-data.png "엔터티 선택")</span><span class="sxs-lookup"><span data-stu-id="bf7aa-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="bf7aa-120">**데이터** 탭은 기본적으로 선택되며 엔터티의 개별 레코드에 대한 세부 사항을 나열하는 테이블을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7aa-120">The **Data** tab is selected by default and shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bf7aa-121">![필드 테이블](media/data-manager-entities-fields.PNG "필드 테이블")</span><span class="sxs-lookup"><span data-stu-id="bf7aa-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="bf7aa-122">**필드** 탭에는 필드 이름, 데이터 유형 및 유형과 같은 선택된 엔터티에 대한 세부 정보를 검토하는 테이블이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf7aa-122">The **Fields** tab shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="bf7aa-123">**유형** 열에는 Common Data Model 관련 유형이 표시되며 시스템에 의해 자동 식별되거나 사용자에 의해 [수동으로 매핑](map-entities.md)됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf7aa-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="bf7aa-124">필드와 같이 특성의 데이터 형식과 다를 수 있는 의미 유형입니다. 예를 들어 아래의 *전자 메일* 에는 *텍스트* 라는 데이터 형식이 있지만 (의미론적) Common Data Model 유형은 *전자 메일* 또는 *EmailAddress* 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf7aa-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="bf7aa-125">두 테이블 모두 엔터티 데이터의 샘플만 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7aa-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="bf7aa-126">전체 데이터 집합을 보려면 **데이터 원본** 페이지에서 엔터티를 선택하고 **편집** 을 선택한 다음 [데이터 원본](data-sources.md)에 설명된 대로 파워 쿼리 편집기를 사용하여 이 엔터티의 데이터를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="bf7aa-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="bf7aa-127">엔터티에서 수집된 데이터에 대해 자세히 알아보려면 **요약** 열은 데이터에 적용할 수 있는 null, 누락된 값, 고유 값, 개수 및 분포와 같은 데이터의 중요한 특성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7aa-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="bf7aa-128">데이터 요약을 보려면 차트 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7aa-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bf7aa-129">![요약 기호](media/data-manager-entities-summary.png "데이터 요약 테이블")</span><span class="sxs-lookup"><span data-stu-id="bf7aa-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="bf7aa-130">다음 단계</span><span class="sxs-lookup"><span data-stu-id="bf7aa-130">Next step</span></span>

<span data-ttu-id="bf7aa-131">수집된 데이터를 *매핑*, *일치* 및 *병합* 하는 방법은 [통합](data-unification.md) 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bf7aa-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]