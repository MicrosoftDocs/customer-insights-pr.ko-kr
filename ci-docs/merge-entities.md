---
title: 고객 또는 계정 필드 통합
description: 엔터티를 병합하여 통합 고객 프로필을 만듭니다.
recommendations: false
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-merge
- ci-match
- ci-relationships
- customerInsights
ms.openlocfilehash: 78e2528d4a3058f879d83952f72ed88a1da065b6
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740865"
---
# <a name="unify-customer-fields"></a>고객 필드 통합

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

통합 프로세스의 이 단계에서 통합 프로필 엔터티 내에서 병합할 속성을 선택하고 제외합니다. 예를 들어 3개의 엔터티에 이메일 데이터가 있는 경우 3개의 개별 이메일 필드를 모두 유지하거나 통합 프로필에 대한 단일 이메일 필드로 병합할 수 있습니다. 일부 특성은 시스템에 의해 자동으로 결합됩니다. 안정적이고 고유한 고객 ID를 생성하고 관련 프로필을 클러스터로 그룹화할 수 있습니다.

:::image type="content" source="media/m3_unify.png" alt-text="통합 고객 프로필을 정의하는 병합된 필드가 있는 테이블을 보여주는 데이터 통합 프로세스의 병합 페이지입니다.":::

## <a name="review-and-update-the-customer-fields"></a>고객 필드 검토 및 업데이트

1. 테이블의 **고객 필드** 탭에서 통합될 필드 목록을 검토하세요. 해당되는 경우 변경합니다.

   1. 결합된 필드에 대해 다음을 수행할 수 있습니다.
      - [편집](#edit-a-merged-field)
      - [이름 바꾸기](#rename-fields)
      - [분리](#separate-merged-fields)
      - [제외](#exclude-fields)
      - [위 또는 아래로 이동](#change-the-order-of-fields)

   1. 단일 필드에 대해 다음을 수행할 수 있습니다.
      - [필드 결합](#combine-fields-manually)
      - [필드 그룹 결합](#combine-a-group-of-fields)
      - [이름 바꾸기](#rename-fields)
      - [제외](#exclude-fields)
      - [위 또는 아래로 이동](#change-the-order-of-fields)

1. 선택적으로, [고객 ID 구성을 생성](#configure-customer-id-generation)합니다.

1. 선택적으로, [프로필을 가족 또는 클러스터로 그룹화](#group-profiles-into-households-or-clusters)합니다.

> [!div class="nextstepaction"]
> [다음 단계: 통합 검토](review-unification.md)

### <a name="edit-a-merged-field"></a>병합된 필드 편집

1. 병합된 필드를 선택하고 **편집** 을 선택합니다. 필드 결합 창이 표시됩니다.

1. 다음 세 가지 옵션 중 하나에서 필드를 결합하거나 병합하는 방법을 지정합니다.
    - **중요도**: 참여 필드에 대해 지정된 중요도 순위를 기반으로 승자 값을 식별합니다. 기본 병합 옵션입니다. **위/아래로 이동** 을 선택하여 중요도 순위를 설정합니다.

      :::image type="content" source="media/importance-merge-option.png" alt-text="병합 필드의 중요도 옵션 대화 상자.":::

    - **가장 최근**: 가장 최근성을 기준으로 승자 값을 식별합니다. 최근성을 정의하려면 병합 필드 범위의 모든 참여 엔터티에 대한 날짜 또는 숫자 필드가 필요합니다.

      :::image type="content" source="media/recency-merge-option.png" alt-text="병합 필드의 최근성 옵션 대화 상자.":::

    - **최소 최근**: 최소 최근성을 기준으로 승자 값을 식별합니다. 최근성을 정의하려면 병합 필드 범위의 모든 참여 엔터티에 대한 날짜 또는 숫자 필드가 필요합니다.

1. 병합 프로세스에 참여할 필드를 더 추가할 수 있습니다.

1. 병합된 필드의 이름을 바꿀 수 있습니다.

1. **완료** 를 선택하여 변경 내용을 적용합니다.

### <a name="rename-fields"></a>필드 이름 바꾸기

병합되거나 분리된 필드의 표시 이름를 변경합니다. 출력 엔터티의 이름은 변경할 수 없습니다.

1. 필드를 선택하고 **이름 변경** 을 선택합니다.

1. 새 표시 이름을 입력합니다.

1. **완료** 를 선택합니다.

### <a name="separate-merged-fields"></a>병합된 필드 분리

병합된 필드를 분리하려면 테이블에서 특성을 찾으십시오. 분리된 필드는 통합 고객 프로필에서 개별 데이터 요소로 표시됩니다.

1. 병합된 필드를 선택하고 **별도의 필드** 를 선택합니다.

1. 분리를 확인합니다.

### <a name="exclude-fields"></a>필드 제외

통합 고객 프로필에서 병합되거나 별도의 필드를 제외합니다. 필드가 다른 프로세스(예: 세그먼트)에서 사용되는 경우 고객 프로필에서 제외하기 전에 이러한 프로세스에서 제거하십시오.

1. 필드를 선택하고 **제외** 를 선택합니다.

1. 제외를 확인하십시오.

모든 제외 필드 목록을 보려면 **제외된 필드** 를 선택하세요. 필요한 경우 제외된 필드를 다시 추가할 수 있습니다.

### <a name="change-the-order-of-fields"></a>필드의 순서 변경

일부 엔터티에는 다른 엔터티보다 자세한 내용이 포함되어 있습니다. 엔터티에 필드에 대한 최신 데이터가 포함된 경우 값을 병합할 때 다른 엔터티보다 우선 순위로 지정할 수 있습니다.

1. 필드를 선택합니다.
  
1. **위/아래로 이동** 을 선택하여 순서를 설정하거나 원하는 위치에 끌어다 놓습니다.

### <a name="combine-fields-manually"></a>수동으로 필드 결합

분리된 필드를 결합하여 병합된 특성을 만듭니다.

1. **결합** > **필드** 를 선택합니다. 필드 결합 창이 표시됩니다.

1. **필드 결합 기준** 드롭다운에서 병합 승자 정책을 지정합니다.

1. 더 많은 필드를 결합하려면 **필드 추가** 를 선택하세요.

1. **이름** 및 **출력 필드 이름** 을 제공합니다.

1. **완료** 를 선택하여 변경 내용을 적용합니다.

### <a name="combine-a-group-of-fields"></a>필드 그룹 결합

필드 그룹을 단일 단위로 취급합니다. 예를 들어 레코드에 주소1, 주소2, 도시, 지역 및 우편번호 필드가 포함되어 있는 경우 다른 레코드의 주소2에 병합하지 않고 데이터를 더 완전하게 만들 수 있습니다.

1. **결합** > **필드 그룹** 를 선택합니다.

1. **그룹 순위 지정 기준** 드롭다운에서 병합 승자 정책을 지정합니다.

1. **추가** 를 선택하고 선택하고 필드에 더 많은 필드 또는 그룹을 추가할 것인지 선택합니다.

1. 결합된 모든 필드에 대해 **이름** 과 **출력 이름** 을 제공합니다.

1. 필드 그룹에 대해 **이름** 을 제공합니다.

1. **완료** 를 선택하여 변경 내용을 적용합니다.

## <a name="configure-customer-id-generation"></a>고객 ID 생성 구성

고유한 고객 프로필 식별자인 고객 ID 값을 생성하는 방법을 정의합니다. 데이터 통합 프로세스의 필드 통합 단계에서는 고유한 고객 프로필 식별자를 생성합니다. 식별자는 데이터 통합 ​​프로세스의 결과인 *고객* 엔터티의 *CustomerId* 입니다.

*CustomerId* 는 null이 아닌 승자 기본 키의 첫 번째 값 해시를 기반으로 합니다. 이러한 키는 데이터 통합에 사용되는 엔터티에서 제공되며 일치 순서의 영향을 받습니다. 따라서 일치 순서의 기본 엔터티에서 기본 키 값이 변경되면 생성된 고객 ID가 변경될 수 있습니다. 기본 키 값이 항상 동일한 고객을 나타내는 것은 아닙니다.

안정적인 고객 ID를 구성하면 이러한 동작을 피할 수 있습니다.

1. **키** 탭을 선택합니다.

1. **CustomerId** 행에 마우스를 놓고 **구성** 를 선택합니다.
   :::image type="content" source="media/customize-stable-id.png" alt-text="ID 생성을 사용자 지정하는 컨트롤.":::

1. 고유한 고객 ID를 구성하고 보다 안정적인 필드를 최대 5개까지 선택하십시오. 구성과 일치하지 않는 레코드는 시스템 구성 ID를 대신 사용합니다.  

1. **완료** 를 선택합니다.

## <a name="group-profiles-into-households-or-clusters"></a>프로필을 가족 또는 클러스터로 그룹화

관련 프로필을 클러스터로 그룹화하는 규칙을 정의할 수 있습니다. 현재 사용 가능한 클러스터 유형은 가정 및 사용자 지정 클러스터의 두 가지입니다. *Customer* 엔터티에 의미 필드 *Person.LastName* 및 *Location.Address* 가 포함된 경우 시스템은 미리 정의된 규칙을 사용하여 가구를 자동으로 선택합니다. [일치 규칙](match-entities.md#define-rules-for-match-pairs)과 유사한 고유한 규칙 및 조건으로 클러스터를 생성할 수도 있습니다.

1. **고급** > **클러스터 생성** 을 선택합니다.

   :::image type="content" source="media/create-cluster.png" alt-text="새 클러스터를 생성하도록 제어.":::

1. **가구** 또는 **사용자 지정** 클러스터 중에서 선택합니다. 의미 필드 *Person.LastName* 및 *Location.Address* 가 *Customer* 엔터티에 있는 경우 가구가 자동으로 선택됩니다.

1. 클러스터의 이름을 제공하고 **완료** 를 선택합니다.

1. **클러스터** 탭을 선택하여 생성한 클러스터를 찾습니다.

1. 클러스터를 정의하기 위한 규칙 및 조건을 지정합니다.

1. **완료** 를 선택합니다. 클러스터는 통합 프로세스가 완료되면 생성됩니다. 클러스터 식별자가 *Customer* 엔터티에 새 필드로 추가됩니다.

> [!div class="nextstepaction"]
> [다음 단계: 통합 검토](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
