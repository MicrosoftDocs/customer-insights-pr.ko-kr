---
title: 예측 개요
description: Dynamics 365 Customer Insights 애플리케이션에서 사용하는 예측 시나리오 및 옵션입니다.
ms.date: 09/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f8c61d7530126890d26ce482a27a0f97a39e836c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610198"
---
# <a name="predictions-overview"></a>예측 개요

Dynamics 365 Customer Insights에는 AI 및 기계 학습을 활용하여 데이터를 예측하는 다양한 옵션이 제공됩니다.

## <a name="out-of-box-models"></a>기본 제공 모델

데이터 예측을 시작하는 가장 쉬운 방법은 흔히 기본 제공 모델이라고 부르는 사전 정의된 모델입니다. 인사이트를 빠르게 생성하도록 특정 데이터와 구조만 필요합니다. 다음 모델을 사용할 수 있습니다.

# <a name="individual-consumers-b-to-c"></a>[개별 소비자(B2C)](#tab/b2c)

- [고객 평생 가치](predict-customer-lifetime-value.md): 비즈니스와의 전체 상호 작용에서 고객의 잠재적 수익을 예측합니다.
- [제품 추천](predict-product-recommendation.md): 구매 행동 및 구매 패턴이 유사한 고객을 기반으로 한 예측 제품 추천 세트를 제안합니다.
- [구독 이탈](predict-subscription-churn.md): 고객이 회사의 구독 제품 또는 서비스를 더 이상 사용하지 않을 위험에 처해 있는지 여부를 예측합니다.
- [트랜잭션 이탈](predict-transactional-churn.md): 개별 고객이 특정 기간에 더 이상 제품이나 서비스를 구매하지 않을지 여부를 예측합니다.
- [감정 분석](sentiment-analysis.md): 고객 피드백의 감정을 분석하고 자주 언급되는 비즈니스 측면을 식별합니다.

# <a name="business-accounts-b-to-b"></a>[비즈니스 어카운트(B2B)](#tab/b2b)

- [트랜잭션 이탈](predict-transactional-churn.md): 고객 계정이 특정 시간 프레임에서 귀하의 제품이나 서비스를 더 이상 구매하지 않을 것인지 예측합니다.

---

> [!TIP]
> 업데이트된 데이터로 즉시 사용 가능한 모델을 정기적으로 새로 고쳐 비즈니스 사용 사례를 정확하게 알릴 수 있도록 하는 것이 좋습니다. 시스템이 새 데이터 원본 또는 업데이트된 데이터 원본을 수집할 때 데이터가 임시로 새로 고쳐집니다. 그러나 모델은 이 경우에만 다시 점수를 매기고 기존 훈련 데이터를 계속 사용합니다.
>
> 구성 중 모델 재학습 일정을 설정하여 **업데이트 일정** 을 구성합니다. 모델은 언제든지 변경할 수 있는 이 일정에 따라 재훈련하고 다시 채점합니다.

## <a name="azure-machine-learning-integration"></a>Azure 기계 학습 통합

조직에서 이미 Azure 기계 학습 실험을 기반으로 기계 학습 시나리오를 사용하는 경우 Customer Insights의 사용자 지정 모델 기능은 종합적인 결론을 도출하는 데 도움이 됩니다. 인사이트를 생성할 데이터를 선택하고 결과를 통합 고객 프로필에 매핑할 수 있도록 지원하는 워크플로를 만듭니다. 자세한 내용은 [사용자 지정 기계 학습 모델](custom-models.md)을 참조하세요.

## <a name="manage-existing-predictions"></a>기존 예측 관리

**인텔리전스** > **예측** 페이지로 이동합니다. **내 예측** 탭에서 생성한 예측, 예측 유형, 출력 엔터티 이름, 상태, 예측이 마지막으로 편집된 시간 및 데이터가 마지막으로 새로 고쳐진 시간을 확인합니다. 모든 열을 기준으로 예측 목록을 정렬할 수 있습니다.

사용 가능한 작업을 보려면 예측을 선택합니다.

:::image type="content" source="media/predictions.png" alt-text="내 예측 페이지.":::

- **편집**: 속성을 변경할 예측을 편집합니다.
- 최신 데이터를 포함하도록 예측을 [**새로 고침**](#refresh-a-prediction)합니다.
- 예측 세부 정보를 **봅니다**.
- [**입력 데이터 사용성 보고서**](#view-the-input-data-usability-report): 오류, 경고 및 권장 사항을 확인합니다.
- 예측을 **삭제** 합니다.

### <a name="refresh-a-prediction"></a>예측 새로 고침

예측은 자동 일정에 따라 새로 고쳐 지거나 필요에 따라 수동으로 새로 고칠 수 있습니다. 모든 예측을 수동으로 새로 고치려면 **모두 새로 고침** 을 선택합니다. 예측을 수동으로 새로 고치려면 예측을 선택하고 **새로 고침** 을 선택합니다. [자동 새로 고침을 예약](schedule-refresh.md)하려면 **관리** > **시스템** > **예약** 으로 이동합니다.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

### <a name="view-the-input-data-usability-report"></a>입력 데이터 사용성 보고서 보기

입력 데이터 사용성 보고서는 기본 제공 예측이 생성할 수 있는 오류 및 경고에 대한 통합 보기를 제공합니다. 또한 모델 성능을 개선하는 방법에 대한 권장 사항을 제공합니다.

이 보고서는 모델이 학습 프로세스를 완료한 후에 사용할 수 있습니다. 학습이 성공적으로 완료되었는지 여부와 관계없이 각 모델에 대해 별도로 생성됩니다.

**내 예측** 탭에서 예측을 선택하고 **입력 데이터 사용성 보고서** 를 선택합니다. 또는 예측 세부정보 보기에서 **입력 데이터 사용성 보고서** 을 선택합니다.

:::image type="content" source="media/input-data-usability-report.png" alt-text="오류, 경고 및 권장 사항이 있는 테이블을 보여주는 입력 데이터 사용성 보고서의 예입니다.":::

보고서에는 다음이 포함됩니다.

- **이름:** 오류, 경고 또는 권장 사항을 설명하는 이름입니다.
- **단계:** 모델 단계, 훈련 또는 점수, 참조 정보입니다.
- **상태:** 정보의 심각도(오류, 경고, 권장 사항)입니다.
- **열 이름:** 모델 성능을 개선하기 위해 수정해야 하는 엔터티의 열입니다.
- **엔터티 이름:** 모델 성능을 개선하기 위해 수정해야 하는 엔터티의 이름입니다.
- **세부 정보:** 오류, 경고 또는 권장 사항에 대한 세부 정보입니다.

[!INCLUDE [footer-include](includes/footer-banner.md)]
