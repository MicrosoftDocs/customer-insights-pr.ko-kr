---
title: 활동을 기반으로 제안된 세그먼트(프리뷰)
description: 기계 학습을 통해 고객 활동을 기반으로 새롭고 흥미로운 세그먼트를 찾을 수 있습니다.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: df4f5f4b5c9a3ad66d57a6b349e18a0d714aff62
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170597"
---
# <a name="suggested-segments-based-on-activity-preview"></a>활동을 기반으로 제안된 세그먼트(프리뷰)

Customer Insights에 수집된 고객 활동 데이터를 기반으로 고객의 흥미로운 세그먼트를 검색합니다. 활동 데이터의 예로는 트랜잭션, 지원 통화 기간, 구매 또는 반품이 있습니다. 세그먼트를 제안하기 위해 활동 데이터에서 최신성, 빈도 및 금전적 가치(또는 기간)를 분석합니다. 또는 [측정값을 개선하거나 속성에 영향을 미치는 요소를 더 잘 이해하기 위해 제안된 세그먼트](suggested-segments.md)를 생성할 수 있습니다.

:::image type="content" source="media/suggested-segments-tab.png" alt-text="활동 기반 및 특성 기반 세그먼트에 대한 세그먼트 제안을 표시하는 제안된 세그먼트 탭.":::

## <a name="categorize-customers-by-activity"></a>활동별로 고객 분류

Customer Insights에서 제공하는 [활동 데이터](activities.md)를 사용하여 고객 그룹을 나타내는 제안을 생성할 수 있습니다.

- 가장 활동적인 고객 
- 가장 많이 구매한 고객 
- 가장 많은 수익을 발생시킨 고객 
- 최근 활동하지 않은 고객 
- 귀사와 자주 상호 작용하는 고객  

소매업의 경우 어떤 고객이 가장 많은 수익을 발생시키는지 확인하고 쿠폰으로 보상할 수 있습니다. 또는 비정기적인 고객을 식별하고 보상 프로그램에 참여하도록 제안하여 고객이 귀하의 비즈니스를 더 자주 방문하도록 할 수 있습니다.
공공 의료 서비스를 제공하고 개별 환자의 비용을 최소화하는 것이 목표인 경우 가능한 한 적은 방문으로 최상의 진료를 제공하여 반복 방문을 줄이려고 할 것입니다. 이 경우 목표는 방문 빈도를 낮게 유지하고 환자의 정기 비용을 최소화하는 것입니다. 또는 진료 예약을 자주하고 정기 비용이 높은 환자 세그먼트를 식별하고 이러한 사례를 분석하여 개인의 치료를 개선할 수 있습니다.

## <a name="required-data"></a>필수 데이터

선택한 입력 데이터를 기반으로 제안이 생성됩니다.

- 고객 프로필: 특정 세그먼트의 모든 고객 또는 구성원입니다.

- 기간: 지난 달, 작년 또는 사용자 지정 시간 프레임.

- 활동 유형: 구매, 소매 거래, 온라인 거래, 고객 지원 사례, 구독 등.  

- 활동 데이터가 포함된 Customer Insights의 엔터티: UnifiedActivity 엔터티 또는 특정 활동에 대한 엔터티입니다.

- 포함할 차원: 비즈니스 요구 사항에 따라 최신성, 빈도 또는 금전적 차원.

## <a name="generate-suggested-segments"></a>제안된 세그먼트 생성

1. **세그먼트** 로 이동하여 **제안(프리뷰)** 탭을 선택합니다.

1. **새로운 제안 찾기** 를 선택하고 **고객 행동 확인 또는 예상** 을 선택합니다. **시작** 을 선택합니다.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="활동을 기반으로 제안된 세그먼트에 대한 구성 마법사의 첫 번째 단계입니다.":::

1. 필요한 데이터를 입력하고 **다음** 을 선택합니다.

   - 고객 선택: 모든 고객 또는 특정 세그먼트를 포함합니다.
   - 활동 선택: 활동 유형과 활동을 설명하는 엔터티를 선택합니다.
   - 기본 설정: 고려할 기간, 제안 요인을 설정하고 속성을 매핑합니다.

1. 입력 내용을 검토하고 **실행** 을 ​​선택하여 모델을 실행하고 제안을 생성합니다.

고객 프로필 수와 선택한 활동에 따라 완료하는 데 몇 분 정도 걸릴 수 있습니다.

제안을 생성한 후 가장 관심이 있는 차원 또는 값으로 필터링할 수 있습니다.

## <a name="manage-suggested-segments"></a>제안된 세그먼트 관리

**세그먼트** 로 이동하여 **제안(프리뷰)** 탭을 선택합니다. **활동 기반 제안** 섹션에서 제안된 세그먼트를 선택하여 사용 가능한 작업을 조회합니다.

- **제안을 확인** 하며 대상 그룹과 비교하여 각 차원의 범위 등 해당 세그먼트의 세부 정보를 봅니다. 또한 세그먼트의 잠재적 회원 수와 총 고객의 해당 비율을 강조 표시합니다.
- **세그먼트 만들기** 를 통해 제안을 세그먼트로 저장합니다. **모든 세그먼트** 탭에 표시되며 [새로 고침 또는 삭제](segments.md)됩니다. 세그먼트 세부 정보는 편집할 수 없습니다. 그러나 제안에 대한 입력 기준을 변경하고 다른 제안을 생성할 수 있습니다.
- **제안을 편집** 하고 현재 제안을 대체할 구성된 특성을 수정합니다.
- **제안 새로 고침** 을 통해 구성된 특성을 유지하면서 제안을 새로 고칩니다.

[!INCLUDE [footer-include](includes/footer-banner.md)]
