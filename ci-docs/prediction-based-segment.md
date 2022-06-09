---
title: 예측 출력을 기반으로 한 세그먼트
description: 예측 모델의 출력 엔터티를 기반으로 세그먼트를 만듭니다.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b0b3357cdf3c049bd92f6c3f690f27433df9117b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647276"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>예측 모델을 기반으로 세그먼트 만들기(프리뷰)

예측 결과는 때때로 고객의 하위 집합에만 적용됩니다. 예측 모델의 결과에서 세그먼트를 만들어 추천 맞춤 설정을 높입니다. 예를 들어 특정 유형의 서비스를 선호하는 고객에게 특정 권장 사항을 제공할 수 있습니다. 

## <a name="prerequisites"></a>필요한 항목

- Customer Insights에 최소한 [기여자 권한](permissions.md).

- Customer Insights에 구성된 제품 추천, 트랜잭션 이탈, 구독 이탈 또는 고객 평생 가치 모델. 다양한 모델을 설정하기 위한 요구 사항을 검토하십시오.

  - [제품 추천 모델](predict-product-recommendation.md)
  - [구독 이탈 모델(프리뷰)](predict-subscription-churn.md)
  - [트랜잭션 이탈 모델](predict-transactional-churn.md)
  - [고객 평생 가치 모델](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>예측을 기반으로 고객 세그먼트 생성

1. **인텔리전스** > **예측** 으로 이동하고 **내 예측** 탭을 선택합니다.

1. 검토할 모델 옆에 있는 수직 줄임표를 선택하고 **보기** 를 선택합니다.

1. 결과 페이지에서 **세그먼트 생성** 을 선택합니다. 결과 페이지에 대한 자세한 내용은 모델에 대한 문서를 검토하세요.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="세그먼트 만들기 작업이 강조 표시된 예측 결과 페이지의 스크린 샷":::

1. 선택한 모델의 출력 엔터티를 기반으로 새 세그먼트를 만듭니다. 자세한 내용은 [세그먼트 만들기 및 관리](segments.md)를 참조하세요.