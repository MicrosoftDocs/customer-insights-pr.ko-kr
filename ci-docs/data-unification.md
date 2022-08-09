---
title: 데이터 통합 개요
description: 통합 고객 프로필의 단일 데이터 세트를 만들기 위해 데이터와 데이터 통합 프로세스를 진행합니다.
ms.date: 05/10/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: v-wendysmith
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: 766e688cb80c50a0d620943f87b76eb84a2fb89a
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139506"
---
# <a name="data-unification-overview"></a>데이터 통합 개요

[데이터 원본 설정](data-sources.md) 후 데이터를 통합할 수 있습니다. 데이터 통합을 사용하면 한 때 서로 다른 데이터 원본을 해당 데이터에 대한 통합 보기를 제공하는 단일 마스터 데이터 세트로 통합할 수 있습니다. 데이터가 개인 중심인 개인 소비자(B-to-C)의 경우 통합은 고객에 대한 통합 보기를 제공합니다. 데이터가 거래처 중심인 비즈니스 거래처(B-to-B)의 경우 통합은 거래처에 대한 통합 보기를 제공합니다.

데이터는 단일 엔터티 또는 여러 엔터티에서 통합될 수 있습니다. 통합은 다음 순서로 수행됩니다.

1. [원본 필드](map-entities.md)(이전에는 Map이라고 함): 원본 필드 단계에서 통합 프로세스에 포함할 엔터티와 필드를 선택합니다. 필드의 목적을 설명하는 공통 의미 유형에 필드를 매핑합니다.

1. [중복 레코드](remove-duplicates.md)(이전에는 일치의 일부): 중복 레코드 단계에서 선택적으로 각 엔터티 내에서 중복 고객 레코드를 제거하는 규칙을 정의합니다.

1. [매칭 조건](match-entities.md)(이전에는 일치라고 함): 일치 조건 단계에서 엔터티 간에 고객 레코드를 일치시키는 규칙을 정의합니다. 고객이 둘 이상의 엔터티에서 발견되면 각 엔터티의 모든 열과 데이터가 포함된 단일 통합 레코드가 생성됩니다.

1. [통합 고객 필드](merge-entities.md)(이전에는 병합이라고 함): 통합 고객 필드 단계에서 통합 고객 프로필에 포함, 제외 또는 병합해야 하는 소스 필드를 결정합니다.  

1. 통합 프로필을 [검토](review-unification.md)하고 생성합니다.

데이터 통합을 완료한 후 선택적으로:

- [엔터티 간 관계 설정](relationships.md)을 통해 정교한 세그먼트를 만듭니다.
- [데이터 보강](enrichment-hub.md)을 통해 고객에 대한 광범위한 통찰력을 얻습니다.
- 일부 수집된 특성에서 [활동을 정의](activities.md)합니다.
- [측정값 구축](measures.md)을 통해 고객 행동과 비즈니스 성과를 더 잘 이해합니다.

[!INCLUDE [footer-include](includes/footer-banner.md)]
