---
title: 데이터 원본 보강(프리뷰)
description: 데이터 통합 프로세스를 진행하기 전에 데이터 원본을 보강합니다.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 98e9e330e7ef9cf085caa94a506fa788cebdd67b
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207191"
---
# <a name="enrichment-for-data-sources-preview"></a>데이터 원본 보강(프리뷰)

Microsoft 및 기타 파트너와 같은 소스의 데이터를 사용하여 데이터 통합 전에 고객 데이터를 강화하십시오. 데이터 원본 보강은 데이터를 통합할 경우 더 나은 결과를 얻을 수 있는 더 높은 데이터 완전성과 품질을 확보하는 데 도움이 됩니다. 예를 들어, 주소에 대해 정규화되고 표준화된 형식을 사용하면 일치 결과의 품질이 향상됩니다. 지원되는 보강 목록은 [지원되는 데이터 원본 보강 옵션](#supported-data-source-enrichments)을 참조하세요.

## <a name="enrich-a-data-source"></a>데이터 원본 보강

보강을 생성하거나 편집하려면 기여자 또는 관리자 [권한](permissions.md)이 있어야 합니다.  

1. **데이터** > **통합** 으로 이동합니다. 보강할 엔터티를 선택하고 엔터티의 [기본 키](map-entities.md#select-primary-key-and-semantic-type-for-attributes)로 특성을 하나 선택합니다.

1. **데이터** > **데이터 원본** 으로 이동.

1. 보강하려는 데이터 원본 옆의 세로 줄임표(&vellip;)를 선택하고 **보강** 을 선택합니다.

   :::image type="content" source="media/data_sources_enrich.png" alt-text="보강이 강조 표시된 데이터 원본 페이지":::

   **검색** 탭에는 [지원되는 데이터 소스 보강 옵션](#supported-data-source-enrichments)이 표시됩니다.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="데이터 원본 보강 페이지입니다.":::

1. **내 데이터 보강** 을 선택하여 데이터 원본 보강을 구성합니다. 출력 엔터티 이름이 자동으로 채워집니다.

## <a name="supported-data-source-enrichments"></a>지원되는 데이터 원본 보강

현재 다음 보강을 데이터 원본에 사용할 수 있습니다. 보강에 대한 자세한 단계를 검토하여 구성 방법을 배우세요.

- [고급 주소](enrichment-enhanced-addresses.md)
- [고급 회사 데이터](enrichment-enhanced-company-data.md)
- [LiveRamp의 ID 데이터](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>기존 데이터 원본 보강 관리

**데이터** > **보강** 으로 이동합니다. **내 보강** 탭에서 구성된 보강, 해당 상태, 보강 고객 수 및 데이터를 마지막으로 새로 고친 시간을 확인합니다. 열을 기준으로 보강 목록을 정렬하거나 검색 상자를 사용하여 관리하려는 보강을 찾을 수 있습니다.

사용 가능한 옵션을 보려면 보강을 선택하십시오. 목록 항목에서 세로 줄임표(&vellip;)를 선택하여 옵션을 볼 수도 있습니다.

데이터 원본 보강을 보고, 편집하고, 실행하거나 삭제할 수 있습니다. 자세한 내용은 [기존 보강 관리](enrichment-hub.md#manage-existing-enrichments)를 확인하세요.
