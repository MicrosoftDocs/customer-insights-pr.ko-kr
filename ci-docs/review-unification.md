---
title: 데이터 통합 검토
description: 데이터 통합 단계 검토, 통합 고객 프로필 생성 및 결과 검토
ms.date: 05/04/2022
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
ms.openlocfilehash: 4c709dfb55bf079dd2fe99e41adb4c77c2bece4b
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741720"
---
# <a name="review-data-unification"></a>데이터 통합 검토

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

통합 프로세스의 이 마지막 단계는 프로세스 단계의 요약을 보여주고 통합 프로필을 생성하기 전에 변경할 수 있는 기회를 제공합니다.

:::image type="content" source="media/m3_review.png" alt-text="고객 프로필 검토 및 생성 스크린샷.":::

## <a name="review-the-data-unification-steps"></a>데이터 통합 단계 검토

1. 데이터 통합 단계에서 **편집** 을 선택하여 검토하고 변경합니다.

1. 선택에 만족하면 **고객 프로필 만들기** 를 선택합니다. 통합 고객 프로필이 생성되는 동안 **통합** 페이지가 표시됩니다. 통합 알고리즘은 완료하는 데 시간이 걸리며 완료될 때까지 구성을 변경할 수 없습니다.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

통합 프로세스가 완료되면 *고객* 이라는 통합 고객 프로필 엔터티가 **프로필** 섹션의 **엔터티** 페이지에 나열됩니다. 첫 번째 성공적인 통합 실행은 통합된 *고객* 엔터티를 생성합니다. 모든 후속 실행은 해당 엔터티를 확장합니다.

## <a name="review-the-results-of-data-unification"></a>데이터 통합 ​​결과 검토

통합 후 **데이터** > **통합** 페이지에 통합된 고객 프로필의 수가 표시됩니다. 통합 프로세스의 각 단계 결과가 각 타일에 표시됩니다. 예를 들어 **원본 필드** 는 매핑된 특성(필드)의 수를 표시하고 **중복 레코드** 는 발견된 중복 레코드 수를 표시합니다.

:::image type="content" source="media/m3_unified.png" alt-text="데이터 통합 후 데이터 통합 페이지의 스크린샷.":::

> [!TIP]
> **일치 조건** 타일은 여러 엔터티를 선택한 경우에만 표시됩니다.

결과, 특히 [일치 규칙](data-unification-update.md#manage-match-rules)의 품질을 검토하고 필요한 경우 수정하는 것이 좋습니다.

필요한 경우 [통합 설정 변경](data-unification-update.md) 및 통합 프로필을 다시 실행합니다.

## <a name="next-step"></a>다음 단계

[활동](activities.md), [보강](enrichment-hub.md), [관계](relationships.md) 또는 [측정값](measures.md)을 구성하여 고객에 대한 더 많은 인사이트를 얻으십시오.

[!INCLUDE[footer-include](includes/footer-banner.md)]
