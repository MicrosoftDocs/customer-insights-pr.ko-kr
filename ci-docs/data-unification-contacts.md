---
title: 통합 연락처 프로필 만들기(프리뷰)
description: 데이터 통합 프로세스를 통해 연락처의 단일 마스터 데이터 세트를 생성합니다.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- ci-match
- ci-merge
- customerInsights
ms.openlocfilehash: 721f47563582a94b5b8244ca5d5d7d1350695512
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9305025"
---
# <a name="create-a-unified-contact-profile-preview"></a>통합 연락처 프로필 만들기(프리뷰)

[비즈니스 거래처 통합](map-entities.md) 후 해당 계정에 대한 연락처를 선택적으로 통합하고 통합된 연락처를 통합 거래처에 연결할 수 있습니다. 연락처 통합 프로세스는 여러 데이터 소스의 연락처 데이터를 매핑하고, 중복을 제거하고, 엔터티 간에 데이터를 일치시키고, 의미 매핑을 설정하고, 연락처와 거래처 간에 관계를 만든 다음 통합 연락처 프로필을 만듭니다.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

처음 몇 단계는 거래처 통합 단계와 동일합니다.

## <a name="prerequisites"></a>전제 조건

거래처 및 연락처 레코드에는 이들을 연결하는 고유 키(외래 키라고 함)가 있어야 합니다. 예를 들어, 거래처와 연락처를 함께 연결하는 거래처 레코드 및 연락처 레코드에 존재하는 거래처 ID입니다.

## <a name="preview-limitations"></a>프리뷰 제한 사항

- 거래처에 대한 링크가 없는 연락처는 삭제됩니다.
- 거래처가 중복 제거되면 병합 기본 설정에 따라 승자 레코드가 식별됩니다. 패자 레코드는 선택되지 않으므로 삭제됩니다. 손실된 레코드와 연결된 연락처는 삭제됩니다.
- 거래처에는 여러 연락처가 있을 수 있지만 연락처는 단일 거래처에 연결되어 있습니다.
- 시맨틱 매핑 단계에서 매핑된 연락처 특성은 고객 카드에 표시할 수 있는 유일한 특성입니다. 그러나 17개의 특성을 사용할 수 있습니다.

## <a name="select-source-fields"></a>원본 필드 선택

1. **연락처 통합(프리뷰)** 에서 **시작** 을 선택합니다.

1. 기본 키 및 특성 유형을 포함한 연락처 데이터 원본용 [엔터티 및 필드를 선택](map-entities.md)합니다.

1. **다음** 을 선택합니다.

## <a name="remove-duplicate-records"></a>중복 레코드 제거

1. 선택적으로 선택한 엔터티에 대해 [중복 제거 규칙을 정의](remove-duplicates.md)합니다.

1. **다음** 을 선택합니다.

## <a name="match-conditions"></a>일치 조건

1. 엔터티 간 일치를 위한 [일치 순서 및 규칙을 정의](match-entities.md)합니다.

1. **다음** 을 선택합니다.

## <a name="unify-contact-fields"></a>연락처 필드 통합

1. [연락처 필드 결합 및 제외](merge-entities.md).

1. **다음** 을 선택합니다.

## <a name="define-the-semantic-fields-for-unified-contacts"></a>통합 연락처의 정의 필드 정의

통합 프로세스의 이 단계에서는 통합 연락처 필드를 의미 유형에 매핑합니다. B-to-B에서는 고객 카드에 거래처가 표시됩니다. 카드를 선택하면 거래처와 연결된 모든 연락처가 표시됩니다. 이 단계에서 매핑하는 필드는 카드에 표시되는 필드입니다.

1. 각 통합 필드에 매핑되는 의미 유형을 선택합니다. 시맨틱 유형을 사용할 수 없는 경우 **없음** 을 선택합니다.

   :::image type="content" source="media/semantic_mapping.png" alt-text="시맨틱 유형을 정의하기 위한 시맨틱 필드 페이지의 스크린샷." lightbox="media/semantic_mapping.png":::

1. 모든 통합 필드를 매핑한 후 **다음** 을 선택합니다.

## <a name="set-the-relationship-between-contacts-and-accounts"></a>연락처와 거래처 간의 관계 설정

통합 프로세스의 이 단계에서는 연락처 데이터를 해당 거래처 데이터에 연결합니다.

1. 각 엔터티에 대해 다음 정보를 입력합니다.

   - **연락처 엔터티의 외래 키**: 연락처 엔터티를 거래처에 연결하는 특성을 선택합니다.
   - **거래처 엔터티에**: 연락처와 연결된 거래처 엔터티를 선택합니다.

   :::image type="content" source="media/contact_relationship.png" alt-text="연락처와 거래처 엔터티를 연결하는 관계 페이지의 스크린샷.":::

1. **다음** 을 선택합니다.

## <a name="review-contact-unification"></a>연락처 통합 검토

변경 사항 요약을 검토하고 통합 프로필을 만들고 결과를 검토합니다.

### <a name="review-and-create-contact-profiles"></a>연락처 프로필 리뷰 및 만들기

통합 프로세스의 이 마지막 단계는 프로세스 단계의 요약을 보여주고 통합 연락처 프로필을 생성하기 전에 변경할 수 있는 기회를 제공합니다.

:::image type="content" source="media/b2b_review_contacts.png" alt-text="연락처 프로필 검토 및 생성 스크린샷.":::

1. 연락처 통합 단계에서 **편집** 을 선택하여 검토하고 변경합니다.

1. 선택에 만족하면 **연락처 프로필 만들기** 를 선택합니다. 통합 연락처 프로필이 생성되는 동안 **통합** 페이지가 표시됩니다.
  
   :::image type="content" source="media/b2b_unify_refreshing.png" alt-text="대기 중 또는 새로 고침 중을 표시하는 타일이 있는 연락처 통합 페이지의 스크린샷.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

통합 알고리즘은 완료하는 데 시간이 걸리며 완료될 때까지 구성을 변경할 수 없습니다.

### <a name="view-the-results-of-contact-unification"></a>연락처 통합 결과 보기

통합이 완료되면 **데이터** > **통합** 페이지에 통합 연락처 프로필의 수가 표시됩니다. 통합 프로세스의 각 단계 결과가 각 타일에 표시됩니다. 예를 들어 **원본 필드** 는 매핑된 특성(필드)의 수를 표시하고 **중복 레코드** 는 발견된 중복 레코드 수를 표시합니다.

:::image type="content" source="media/unified_contacts.png" alt-text="연락처가 통합된 후 데이터 통합 페이지의 스크린샷.":::

> [!TIP]
> **일치 조건** 타일은 여러 엔터티를 선택한 경우에만 표시됩니다.

결과, 특히 [일치 규칙](data-unification-update.md#manage-match-rules)의 품질을 검토하고 필요한 경우 수정하는 것이 좋습니다.

필요한 경우 [연락처 통합 설정 변경](data-unification-update.md) 및 통합 프로필을 다시 실행합니다.

### <a name="verify-output-entities-from-data-unification"></a>데이터 통합에서 출력 엔터티 확인

**데이터** > **엔터티** 로 이동하여 출력 엔터티를 확인합니다.

*ContactProfile* 이라는 통합 연락처 프로필 엔터티가 **시맨틱 엔터티** 섹션에 표시됩니다. 첫 번째 성공적인 통합 실행은 통합된 *ContactProfile* 엔터티를 생성합니다. 모든 후속 실행은 해당 엔터티를 확장합니다.

*ContactsCustomer* 엔터티(프리뷰)가 생성되어 **프로필** 섹션에 표시됩니다. 이 엔터티에는 거래처에 대한 링크가 없는 연락처 데이터가 포함되어 있습니다. 이 엔터티는 연락처 통합의 시맨틱 매핑 및 관계 단계에 대한 입력으로 사용됩니다.

중복 제거 및 병합 항목이 생성되어 **시스템** 섹션에 표시됩니다. 각 원본 엔터티에 대해 중복 제거된 엔터티는 **Deduplication_DataSource_Entity** 라는 이름으로 생성됩니다. **ContactsConflationMatchPairs** 엔터티에는 엔터티 간 일치에 대한 정보가 포함됩니다.

중복 제거 출력 엔터티에는 다음 정보가 포함됩니다.
- ID / 키
  - 기본 키 및 대체 ID 필드. 대체 ID 필드는 레코드에 대해 식별된 모든 대체 ID로 구성됩니다.
  - Deduplication_GroupId 필드는 지정된 중복 제거 필드를 기반으로 모든 유사한 레코드를 그룹화하는 엔터티 내에서 식별된 그룹 또는 클러스터를 보여줍니다. 이것은 시스템 처리 목적으로 사용됩니다. 지정된 수동 중복 제거 규칙이 없고 시스템 정의 중복 제거 규칙이 적용되는 경우 중복 제거 출력 엔터티에서 이 필드를 찾을 수 없습니다.
  - Deduplication_WinnerId: 이 필드에는 식별된 그룹 또는 클러스터의 승자 ID가 포함됩니다. Deduplication_WinnerId가 레코드의 기본 키 값과 같으면 레코드가 승자 레코드라는 의미입니다.
- 중복 제거 규칙을 정의하는 데 사용되는 필드입니다.
- 적용된 중복 제거 규칙과 일치 알고리즘에서 반환된 점수를 나타내는 규칙 및 점수 필드입니다.

## <a name="next-step"></a>다음 단계

거래처에 대한 더 많은 인사이트를 얻기 위해 [활동](activities.md), [보강](enrichment-hub.md) 또는 [관계](relationships.md)를 구성합니다.
