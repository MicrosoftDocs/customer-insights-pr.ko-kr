---
title: 통합 설정 업데이트
description: 통합 설정에서 중복 규칙, 일치 규칙 또는 통합 필드를 업데이트합니다.
ms.date: 06/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 590a2996cf8b2b1c6def59b78583169ec1910b59
ms.sourcegitcommit: 760fbac397c738407c7dea59297d54cae19b6f57
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844048"
---
# <a name="update-the-unification-settings"></a>통합 설정 업데이트

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

통합 프로필이 생성된 후 통합 설정을 검토하거나 변경하려면 다음 단계를 수행하십시오.

1. **데이터** > **통합** 으로 이동합니다.

   :::image type="content" source="media/m3_unified.png" alt-text="데이터 통합 후 데이터 통합 페이지의 스크린샷.":::

   > [!TIP]
   > **일치 조건** 타일은 여러 엔터티를 선택한 경우에만 표시됩니다.

1. 업데이트할 항목 선택:
   - [원본 필드](#edit-source-fields): 엔터티 또는 특성을 추가하거나 특성 유형을 변경합니다.
   - [중복 레코드](#manage-deduplication-rules): 중복 제거 규칙을 관리하거나 기본 설정을 병합합니다.
   - [일치 조건](#manage-match-rules): 둘 이상의 엔터티에서 일치 규칙을 업데이트합니다.
   - [통합 고객 필드](#manage-unified-fields): 필드를 결합하거나 제외합니다. 관련 프로필을 클러스터로 그룹화할 수도 있습니다.

1. 변경한 후 다음 옵션을 선택합니다.

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="통합 옵션이 강조 표시된 데이터 통합 페이지의 스크린샷.":::

   - [일치하는 조건을 실행](#run-matching-conditions)하여 통합 프로필을 업데이트하지 않고도 일치 조건(중복 제거 및 일치 규칙)의 품질을 빠르게 평가할 수 있습니다. **일치하는 조건만 실행** 옵션은 단일 엔터티에 대해 표시되지 않습니다.
   - [고객 프로필을 통합](#run-updates-to-the-unified-customer-profile)하여 일치 조건을 실행하고 종속성(예: 보강, 세그먼트 또는 측정값)에 영향을 주지 않고 Unified Customer Profiles 엔터티를 업데이트합니다. 종속 프로세스는 실행되지 않지만 [새로 고침 일정에 정의](system.md#schedule-tab)에 따라 새로 고쳐집니다.
   - [고객 프로필 및 종속성을 통합](#run-updates-to-the-unified-customer-profile)하여 일치 조건을 실행하고 Unified Customer Profiles 엔터티 및 모든 종속성(예: 보강, 세그먼트 또는 측정값)을 업데이트합니다. 모든 프로세스는 자동으로 다시 실행됩니다.

## <a name="edit-source-fields"></a>원본 필드 편집

이미 통합된 특성이나 엔터티는 제거할 수 없습니다.

1. **원본 필드** 타일에서 **편집** 을 선택합니다.

   :::image type="content" source="media/m3_source_edit.png" alt-text="기본 키, 매핑 및 매핑되지 않은 필드의 수를 보여주는 원본 필드 페이지의 스크린샷":::

   매핑된 필드와 매핑되지 않은 필드의 수가 표시됩니다.

1. **엔터티 및 필드 선택** 을 선택하여 다른 특성이나 엔터티를 추가합니다. 검색 또는 스크롤을 사용하여 관심있는 특성 및 엔터티를 찾아 선택하십시오. **적용** 을 선택합니다.

1. 선택적으로 엔터티의 기본 키, 특성 유형을 변경하고 **지능형 매핑** 을 켜거나 끌 수 있습니다. 자세한 내용은 [특성에 대한 기본 키 및 의미 유형 선택](map-entities.md#select-primary-key-and-semantic-type-for-attributes)을 참조하십시오.

1. **다음** 을 ​​선택하여 중복 제거 규칙을 변경하거나 **저장 후 닫기** 를 선택하고 [통합 설정 업데이트](#update-the-unification-settings)로 돌아갑니다.

## <a name="manage-deduplication-rules"></a>중복 제거 규칙 관리

1. **중복 레코드** 타일에서 **편집** 을 선택합니다.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="중복 레코드 수를 보여주는 중복 레코드 페이지 스크린샷" lightbox="media/m3_duplicates_edit.png":::

   발견된 중복 레코드 수가 **중복** 아래에 표시됩니다. **중복 레코드** 열에는 중복 레코드가 있는 엔터티와 중복된 레코드의 비율이 표시됩니다.

1. 보강 엔터티를 추가한 경우 **보강 엔터티 사용** 을 선택합니다 자세한 내용은 [데이터 원본 보강](data-sources-enrichment.md)을 참조하세요.

1. 중복 제거 규칙을 관리하려면 다음 옵션 중 하나를 선택하십시오.
   - **새 규칙 만들기**: 해당 항목에서 **규칙 추가** 를 선택합니다. 자세한 내용은 [중복 제거 규칙 정의](remove-duplicates.md#define-deduplication-rules)를 참조하세요.
   - **규칙 조건 변경**: 규칙을 선택한 **편집** 을 선택합니다. 필드를 변경하거나 조건을 추가 또는 제거하거나 예외를 추가 또는 제거합니다.
   - **미리 보기**: 규칙을 선택한 다음 **미리 보기** 를 선택하여 이 규칙에 대한 마지막 실행 결과를 봅니다.
   - **규칙 비활성화**: 규칙을 선택한 다음 **비활성화** 하여 중복 제거 규칙을 유지하면서 일치 프로세스에서 제외합니다.
   - **규칙 복제** : 규칙을 선택한 다음 **복제** 하여 수정을 통해 유사한 규칙을 생성합니다.
   - **규칙 삭제**: 규칙을 선택한 다음 **삭제** 합니다.

1. 병합 기본 설정을 변경하려면 엔터티를 선택합니다. 규칙이 생성된 경우에만 기본 설정을 변경할 수 있습니다.
   1. **병합 기본 설정 편집** 을 선택하고 **보관할 레코드** 옵션을 변경합니다.
   1. 엔터티의 개별 특성에 대한 병합 기본 설정을 변경하려면 **고급** 을 선택하고 필요에 따라 변경합니다.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="가장 최근의 이메일과 가장 완전한 주소를 보여주는 고급 병합 기본 설정의 스크린샷":::

   1. **완료** 를 선택합니다.

1. **다음** 을 선택하여 일치하는 조건을 변경하거나 **저장 후 닫기** 를 선택하고 [통합 설정 업데이트](#update-the-unification-settings)로 돌아갑니다.

## <a name="manage-match-rules"></a>일치 규칙 관리

대부분의 일치 매개 변수를 재구성하고 미세 조정할 수 있습니다. 엔터티를 추가하거나 삭제할 수 없습니다. 일치 규칙은 단일 엔터티에 적용되지 않습니다.

1. **일치하는 조건** 타일에서 **편집** 을 선택합니다.

   :::image type="content" source="media/m3_match_edit.png" alt-text="통계가 있는 일치 규칙 및 조건 페이지의 스크린샷." lightbox="media/m3_match_edit.png":::

   페이지에는 일치 순서와 정의된 규칙 및 다음 통계가 표시됩니다.
   - **고유한 원본 레코드** 는 마지막 일치 실행에서 처리된 개별 원본 레코드의 수를 표시합니다.
   - **일치 및 일치하지 않는 레코드** 는 일치 규칙을 처리한 후 남아있는 고유 레코드 수를 강조 표시합니다.
   - **일치하는 레코드만** 은 모든 매치 쌍에서 일치 수를 보여줍니다.

1. 모든 규칙 및 해당 점수의 결과를 보려면 **마지막 실행 보기** 를 선택합니다. 대체 연락처 ID를 포함한 결과가 표시됩니다. 결과를 다운로드할 수 있습니다.

1. 특정 규칙의 결과와 점수를 보려면 규칙을 선택한 다음 **미리 보기** 를 선택합니다. 결과가 표시됩니다. 결과를 다운로드할 수 있습니다.

1. 규칙에 대한 특정 조건의 결과를 보려면 규칙을 선택한 다음 **편집** 을 선택합니다. 편집 창의 조건에서 **미리 보기** 를 선택합니다. 결과를 다운로드할 수 있습니다.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="데이터 목록을 포함하여 일치하지 않거나 일치하는 레코드의 그래픽 표현.":::

1. 보강 엔터티를 추가한 경우 **보강 엔터티 사용** 을 선택합니다 자세한 내용은 [데이터 원본 보강](data-sources-enrichment.md)을 참조하세요.

1. 규칙을 관리하려면 다음 옵션 중 하나를 선택합니다.
   - **새 규칙 만들기**: 해당 항목에서 **규칙 추가** 를 선택합니다. 자세한 내용은 [일치 쌍에 대한 규칙 정의](match-entities.md#define-rules-for-match-pairs)를 참조하십시오.
   - **규칙 순서 변경** 여러 규칙을 정의한 경우: 규칙을 원하는 순서로 끌어다 놓습니다. 자세한 내용은 [일치 순서 지정](match-entities.md#specify-the-match-order)을 참조하십시오.
   - **규칙 조건 변경**: 규칙을 선택한 **편집** 을 선택합니다. 필드를 변경하거나 조건을 추가 또는 제거하거나 예외를 추가 또는 제거합니다.
   - **규칙 비활성화**: 규칙을 선택한 다음 **비활성화** 하여 일치 규칙을 유지하면서 일치 프로세스에서 제외합니다.
   - **규칙 복제** : 규칙을 선택한 다음 **복제** 하여 수정을 통해 유사한 규칙을 생성합니다.
   - **규칙 삭제**: 규칙을 선택한 다음 **삭제** 합니다.

1. **다음** 을 선택하여 통합 필드를 변경하거나 **저장 후 닫기** 를 선택하고 [통합 설정 업데이트](#update-the-unification-settings)로 돌아갑니다.

## <a name="manage-unified-fields"></a>통합 필드 관리

1. **통합 고객 필드** 타일에서 **편집** 을 선택합니다.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="통합 고객 필드 스크린샷":::

1. 결합 및 제외 필드를 검토하고 필요에 따라 변경합니다. CustomerID 키 또는 그룹 프로필을 클러스터에 추가하거나 편집합니다. 자세한 내용은 [통합 고객 필드](merge-entities.md)를 참조하십시오.

1. **다음** 을 선택하여 통합 설정을 검토하고 [통합 프로필 및 종속성을 업데이트](#run-updates-to-the-unified-customer-profile)하거나 **저장 및 닫기** 를 선택하고 [통합 설정 업데이트](#update-the-unification-settings)로 돌아가서 추가 변경을 수행합니다.

## <a name="run-matching-conditions"></a>일치하는 조건 실행

일치 조건 실행은 중복 제거 및 일치 규칙만 실행하고 *Deduplication_* 및 *ConflationMatchPair* 엔터티를 업데이트합니다.

1. **데이터** > **통합** 페이지에서 **일치하는 조건만 실행** 을 선택합니다.

   **중복 레코드** 및 **일치하는 조건** 타일에 **대기** 또는 **새로 고침** 상태가 표시됩니다.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. 매칭이 완료되면 **일치하는 조건** 타일에서 **편집** 을 선택합니다.

   :::image type="content" source="media/match-KPIs.png" alt-text="숫자와 세부 정보가 포함된 일치 페이지의 키 메트릭에 대한 잘린 스크린샷입니다.":::

1. 변경하려면 [중복 제거 규칙 관리](#manage-deduplication-rules) 또는 [일치 규칙 관리](#manage-match-rules)를 참조하십시오.

1. 일치 프로세스를 다시 실행하거나 [고객 프로필 업데이트를 실행](#run-updates-to-the-unified-customer-profile)합니다.

## <a name="run-updates-to-the-unified-customer-profile"></a>통합 고객 프로필에 대한 업데이트 실행

1. **데이터** > **통합** 페이지에서 다음을 선택합니다.

   - **고객 프로필 통합**: 일치 조건을 실행하고 종속성(예: 보강, 세그먼트 또는 측정값)에 영향을 주지 않고 Unified Customer Profiles 엔터티를 업데이트합니다. 종속 프로세스는 실행되지 않지만 [새로 고침 일정에 정의](system.md#schedule-tab)에 따라 새로 고쳐집니다.

   - **고객 프로필 및 종속성 통합**: 일치 조건을 실행하고 통합 프로필 및 모든 종속성을 업데이트합니다. 모든 프로세스는 자동으로 다시 실행됩니다. 모든 다운스트림 프로세스가 완료된 후 고객 프로필에 업데이트된 데이터가 반영됩니다.

   **중복 레코드**, **일치하는 조건** 및 **통합 고객 필드** 타일에 **대기** 또는 **새로 고침** 상태가 표시됩니다.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

성공적인 실행 결과는 통합된 고객 프로필의 수를 보여주는 **통합** 페이지에 표시됩니다.
