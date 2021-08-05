---
title: 데이터 통합
description: 수집된 데이터를 통합하는 방법을 알아봅니다.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: cb96763d4b5b67b5110db757eb7d160c294d6fc3
ms.sourcegitcommit: b78c9680b213204e6b0ed47f0147205083f6a98f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "6539077"
---
# <a name="data-unification-overview"></a>데이터 통합 개요

[데이터 원본 설정](data-sources.md) 후 데이터를 통합할 수 있습니다. 데이터 통합에는 **매핑**, **일치** 및 **병합** 의 세 단계가 포함됩니다.

데이터 통합 프로세스를 사용하면 개별 데이터 원본을 단일 마스터 데이터 집합으로 통합하여 고객에 대한 통일된 보기를 제공할 수 있습니다. 통합 단계는 필수이며 다음 순서로 수행됩니다.

1. [매핑](map-entities.md)
2. [일치](match-entities.md)
3. [병합](merge-entities.md)

데이터 통합을 완료한 후 선택적으로

- [엔터티 간 관계 설정](relationships.md)을 통해 정교한 세그먼트를 만들고
- [데이터 보강](enrichment-hub.md)을 통해 고객에 대한 광범위한 인사이트를 얻으며
- 일부 수집된 특성에서 [활동을 정의](activities.md)합니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]