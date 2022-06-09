---
title: 지원되는 예측 시나리오에 대한 개요
description: Dynamics 365 Customer Insights 애플리케이션에서 사용하는 예측 시나리오 및 옵션입니다.
ms.date: 03/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 11b0efeecf8bea893272e67d29b1c6622771110c
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647456"
---
# <a name="predictions-overview"></a>예측 개요

Dynamics 365 Customer Insights에는 AI 및 기계 학습을 활용하여 데이터를 예측하는 다양한 옵션이 제공됩니다. 

## <a name="out-of-box-models"></a>기본 제공 모델

데이터 예측을 시작하는 가장 쉬운 방법은 흔히 기본 제공 모델이라고 부르는 사전 정의된 모델입니다. 인사이트를 빠르게 생성하도록 특정 데이터와 구조만 필요합니다. 현재 다음 모델을 사용할 수 있습니다. 

# <a name="individual-consumers-b-to-c"></a>[개별 소비자(B2C)](#tab/b2c)

- [고객 평생 가치](predict-customer-lifetime-value.md): 비즈니스와의 전체 상호 작용에서 고객의 잠재적 수익을 예측합니다.
- [제품 추천](predict-product-recommendation.md): 구매 행동 및 구매 패턴이 유사한 고객을 기반으로 한 예측 제품 추천 세트를 제안합니다.
- [구독 이탈](predict-subscription-churn.md): 고객이 회사의 구독 제품 또는 서비스를 더 이상 사용하지 않을 위험에 처해 있는지 여부를 예측합니다.
- [트랜잭션 이탈](predict-transactional-churn.md): 고객이 특정 시간 프레임에서 귀하의 제품이나 서비스를 더 이상 구매하지 않을 것인지 예측합니다.
- [감정 분석](sentiment-analysis.md): 고객 피드백의 감정을 분석하고 자주 언급되는 비즈니스 측면을 식별합니다.

# <a name="business-accounts-b-to-b"></a>[비즈니스 어카운트(B2B)](#tab/b2b)

- [트랜잭션 이탈](predict-transactional-churn.md): 고객이 특정 시간 프레임에서 귀하의 제품이나 서비스를 더 이상 구매하지 않을 것인지 예측합니다.

---

> [!TIP]
> 업데이트된 데이터로 즉시 사용 가능한 모델을 정기적으로 새로 고쳐 비즈니스 사용 사례를 정확하게 알릴 수 있도록 하는 것이 좋습니다. 시스템이 새 데이터 원본 또는 업데이트된 데이터 원본을 수집할 때 데이터가 임시로 새로 고쳐집니다. 그러나 모델은 이 경우에만 다시 점수를 매기고 기존 훈련 데이터를 계속 사용합니다.
> 
> 구성 환경에서 모델 재훈련 일정을 설정하여 **업데이트 일정** 을 구성할 수 있습니다. 모델은 언제든지 변경할 수 있는 이 일정에 따라 재훈련하고 다시 채점합니다.


## <a name="azure-machine-learning-integration"></a>Azure 기계 학습 통합

조직에서 이미 Azure 기계 학습 실험을 기반으로 기계 학습 시나리오를 사용하는 경우 Customer Insights의 사용자 지정 모델 기능은 종합적인 결론을 도출하는 데 도움이 됩니다. 인사이트를 생성할 데이터를 선택하고 결과를 통합 고객 프로필에 매핑할 수 있도록 지원하는 워크플로를 만듭니다. 자세한 내용은 [사용자 지정 기계 학습 모델](custom-models.md)을 참조하세요.

## <a name="ai-builder-prediction"></a>AI Builder 예측

때로는 데이터 집합이 불완전하고 일부 값이 누락됩니다. Customer Insights는 고객 엔터티 및 세그먼트에 대한 누락된 값을 예측하는 데 도움이 될 수 있습니다. 자세한 내용은 [예측으로 부분 데이터 완성](predictions.md)을 참조하십시오.