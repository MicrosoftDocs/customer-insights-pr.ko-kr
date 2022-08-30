---
title: 데이터 통합 검토
description: 데이터 통합 단계 검토, 통합 고객 프로필 생성 및 결과 검토
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303975"
---
# <a name="review-data-unification"></a>데이터 통합 검토

변경 사항 요약을 검토하고 통합 프로필을 만들고 결과를 검토합니다.

## <a name="review-and-create-customer-profiles"></a>고객 프로필 검토 및 만들기

통합 프로세스의 이 마지막 단계는 프로세스 단계의 요약을 보여주고 통합 프로필을 생성하기 전에 변경할 수 있는 기회를 제공합니다.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="고객 프로필 검토 및 생성 스크린샷.":::

1. 데이터 통합 단계에서 **편집** 을 선택하여 검토하고 변경합니다.

1. 선택에 만족하면 **고객 프로필 만들기**(또는 B-to-B의 경우 **거래처 프로필 만들기**)를 선택합니다. 통합 고객 프로필이 생성되는 동안 **통합** 페이지가 표시됩니다.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="대기 중 또는 새로 고침 중을 표시하는 타일이 있는 Unify 페이지의 스크린샷.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

통합 알고리즘은 완료하는 데 시간이 걸리며 완료될 때까지 구성을 변경할 수 없습니다.

## <a name="view-the-results-of-data-unification"></a>데이터 통합 ​​결과 보기

통합 후 **데이터** > **통합** 페이지에 통합된 고객 프로필(또는 B-to-B의 경우 거래처 프로필)의 수가 표시됩니다. 통합 프로세스의 각 단계 결과가 각 타일에 표시됩니다. 예를 들어 **원본 필드** 는 매핑된 특성(필드)의 수를 표시하고 **중복 레코드** 는 발견된 중복 레코드 수를 표시합니다.

:::image type="content" source="media/m3_unified.png" alt-text="데이터 통합 후 데이터 통합 페이지의 스크린샷.":::

> [!TIP]
> **일치 조건** 타일은 여러 엔터티를 선택한 경우에만 표시됩니다.

결과, 특히 [일치 규칙](data-unification-update.md#manage-match-rules)의 품질을 검토하고 필요한 경우 수정하는 것이 좋습니다.

필요한 경우 [통합 설정 변경](data-unification-update.md) 및 통합 프로필을 다시 실행합니다.

### <a name="verify-output-entities-from-data-unification"></a>데이터 통합에서 출력 엔터티 확인

**데이터** > **엔터티** 로 이동하여 출력 엔터티를 확인합니다.

*고객* 이라는 통합 고객 프로필 엔터티가 **프로필** 섹션에 표시됩니다. 첫 번째 성공적인 통합 실행은 통합된 *고객* 엔터티를 생성합니다. 모든 후속 실행은 해당 엔터티를 확장합니다.

중복 제거 및 병합 항목이 생성되어 **시스템** 섹션에 표시됩니다. 각 원본 엔터티에 대해 중복 제거된 엔터티는 **Deduplication_DataSource_Entity** 라는 이름으로 생성됩니다. **ConflationMatchPairs** 엔터티에는 엔터티 간 일치에 대한 정보가 포함됩니다.

중복 제거 출력 엔터티에는 다음 정보가 포함됩니다.
- ID / 키
  - 기본 키 및 대체 ID 필드. 대체 ID 필드는 레코드에 대해 식별된 모든 대체 ID로 구성됩니다.
  - Deduplication_GroupId 필드는 지정된 중복 제거 필드를 기반으로 모든 유사한 레코드를 그룹화하는 엔터티 내에서 식별된 그룹 또는 클러스터를 보여줍니다. 이것은 시스템 처리 목적으로 사용됩니다. 지정된 수동 중복 제거 규칙이 없고 시스템 정의 중복 제거 규칙이 적용되는 경우 중복 제거 출력 엔터티에서 이 필드를 찾을 수 없습니다.
  - Deduplication_WinnerId: 이 필드에는 식별된 그룹 또는 클러스터의 승자 ID가 포함됩니다. Deduplication_WinnerId가 레코드의 기본 키 값과 같으면 레코드가 승자 레코드라는 의미입니다.
- 중복 제거 규칙을 정의하는 데 사용되는 필드입니다.
- 적용된 중복 제거 규칙과 일치 알고리즘에서 반환된 점수를 나타내는 규칙 및 점수 필드입니다.

## <a name="next-step"></a>다음 단계

- B-to-B의 경우 선택적으로 수행 [연락처 통합](data-unification-contacts.md)을 수행합니다.

- B-to-C의 경우 [활동](activities.md), [보강](enrichment-hub.md), [관계](relationships.md) 또는 [측정값](measures.md)을 구성하여 고객에 대한 더 많은 인사이트를 얻으십시오.

[!INCLUDE[footer-include](includes/footer-banner.md)]
