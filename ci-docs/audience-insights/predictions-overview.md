---
title: 지원되는 예측 시나리오에 대한 개요
description: Dynamics 365 Customer Insights 애플리케이션에서 사용하는 예측 시나리오 및 옵션입니다.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095727"
---
# <a name="predictions-overview"></a>예측 개요

Dynamics 365 Customer Insights에는 AI 및 기계 학습을 활용하여 데이터를 예측하는 다양한 옵션이 제공됩니다. 

## <a name="out-of-box-models"></a>기본 제공 모델

데이터 예측을 시작하는 가장 쉬운 방법은 흔히 기본 제공 모델이라고 부르는 사전 정의된 모델입니다. 인사이트를 빠르게 생성하도록 특정 데이터와 구조만 필요합니다. 현재 다음 모델을 사용할 수 있습니다. 
- [고객 평생 가치](predict-customer-lifetime-value.md): 비즈니스와의 전체 상호 작용에서 고객의 잠재적 수익을 예측합니다. 
- [제품 추천](predict-product-recommendation.md): 구매 행동 및 구매 패턴이 유사한 고객을 기반으로 한 예측 제품 추천 세트를 제안합니다.
- [구독 이탈](predict-subscription-churn.md): 고객이 회사의 구독 제품 또는 서비스를 더 이상 사용하지 않을 위험에 처해 있는지 여부를 예측합니다.
- [트랜잭션 이탈](predict-transactional-churn.md): 고객이 특정 시간 프레임에서 귀하의 제품이나 서비스를 더 이상 구매하지 않을 것인지 예측합니다.

## <a name="azure-machine-learning-integration"></a>Azure 기계 학습 통합

조직에서 이미 Azure 기계 학습 실험을 기반으로 기계 학습 시나리오를 사용하는 경우 Customer Insights의 사용자 지정 모델 기능은 종합적인 결론을 도출하는 데 도움이 됩니다. 인사이트를 생성할 데이터를 선택하고 결과를 통합 고객 프로필에 매핑할 수 있도록 지원하는 워크플로를 만듭니다. 자세한 내용은 [사용자 지정 기계 학습 모델](custom-models.md)을 참조하세요.

## <a name="ai-builder-prediction"></a>AI Builder 예측

때로는 데이터 집합이 불완전하고 일부 값이 누락됩니다. Customer Insights는 고객 엔터티 및 세그먼트에 대한 누락된 값을 예측하는 데 도움이 될 수 있습니다. 자세한 내용은 [예측으로 부분 데이터 완성](predictions.md)을 참조하십시오.
