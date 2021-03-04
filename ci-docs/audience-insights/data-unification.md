---
title: 데이터 통합
description: 수집된 데이터를 통합하는 방법을 알아봅니다.
ms.date: 04/16/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 44f97696ec91dc488dd6a7528e186abb99c8288b
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269660"
---
# <a name="data-unification-overview"></a><span data-ttu-id="66a04-103">데이터 통합 개요</span><span class="sxs-lookup"><span data-stu-id="66a04-103">Data unification overview</span></span>

<span data-ttu-id="66a04-104">[데이터 원본 설정](data-sources.md) 후 데이터를 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66a04-104">After [setting up the data sources](data-sources.md), you can unify the data.</span></span> <span data-ttu-id="66a04-105">데이터 통합에는 **매핑**, **일치** 및 **병합** 의 세 단계가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="66a04-105">Data unification includes three steps: **Map**, **Match**, and **Merge**.</span></span>

<span data-ttu-id="66a04-106">데이터 통합 프로세스를 사용하면 개별 데이터 원본을 단일 마스터 데이터 집합으로 통합하여 고객에 대한 통일된 보기를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66a04-106">The data unification process lets you unify once-disparate data sources into a single master dataset that provides a unified view of your customers.</span></span> <span data-ttu-id="66a04-107">통합 단계는 필수이며 다음 순서로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="66a04-107">Unification stages are mandatory, and performed in the following order:</span></span>

1. [<span data-ttu-id="66a04-108">매핑</span><span class="sxs-lookup"><span data-stu-id="66a04-108">Map</span></span>](map-entities.md)
2. [<span data-ttu-id="66a04-109">일치</span><span class="sxs-lookup"><span data-stu-id="66a04-109">Match</span></span>](match-entities.md)
3. [<span data-ttu-id="66a04-110">병합</span><span class="sxs-lookup"><span data-stu-id="66a04-110">Merge</span></span>](merge-entities.md)

<span data-ttu-id="66a04-111">데이터 통합을 완료한 후 선택적으로</span><span class="sxs-lookup"><span data-stu-id="66a04-111">After completing the data unification, you can optionally</span></span>

- <span data-ttu-id="66a04-112">[엔터티 간 관계 설정](relationships.md)을 통해 정교한 세그먼트를 만들고</span><span class="sxs-lookup"><span data-stu-id="66a04-112">[set up relationships between entities](relationships.md) to create sophisticated segments</span></span>
- <span data-ttu-id="66a04-113">[데이터 보강](enrichment-hub.md)을 통해 고객에 대한 광범위한 인사이트를 얻으며</span><span class="sxs-lookup"><span data-stu-id="66a04-113">[enrich your data](enrichment-hub.md) to get a wider range of insights about your customers</span></span>
- <span data-ttu-id="66a04-114">일부 수집된 특성에서 [활동을 정의](activities.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="66a04-114">[define activities](activities.md) from some of the ingested attributes</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]