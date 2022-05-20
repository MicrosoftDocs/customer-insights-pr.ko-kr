---
title: 제품 추천 예측 샘플 가이드
description: 이 샘플 가이드를 사용하여 즉시 사용 가능한 제품 추천 예측 모델을 사용해보세요.
ms.date: 05/16/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762694"
---
# <a name="product-recommendation-prediction-sample-guide"></a>제품 추천 예측 샘플 가이드

아래 제공된 샘플 데이터를 사용하여 제품 추천 예측의 엔드 투 엔드 예를 안내합니다.

## <a name="scenario"></a>시나리오

Contoso는 고품질 커피 및 커피 머신을 생산하는 회사로 Contoso Coffee 웹 사이트를 통해 판매합니다. 회사의 목표는 정기 고객에게 어떤 제품을 추천해야 하는지 이해하는 것입니다. 어떤 고객이 **구매 가능성** 이 더 높은지 알면 특정 항목에 집중함으로써 마케팅 노력을 절감할 수 있습니다.

## <a name="prerequisites"></a>필요한 항목

- Customer Insights에 최소한 [기여자 권한](permissions.md).
- [새로운 환경에서](manage-environments.md) 다음 단계를 구현하는 것이 좋습니다.

## <a name="task-1---ingest-data"></a>작업 1 - 데이터 수집

구체적으로 Power Query 커넥터를 사용한 [데이터 수집](data-sources.md) 및 [데이터 원본 가져오기에 대한 문서](connect-power-query.md)를 검토하세요. 다음 정보는 사용자가 일반적인 데이터 수집에 익숙하다고 가정합니다.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>전자상거래 플랫폼에서 고객 데이터 수집

1. **전자상거래** 라는 데이터 원본을 만들고 가져오기 옵션을 선택한 다음 **텍스트/CSV** 커넥터를 선택합니다.

1. 전자상거래 연락처 URL인 [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts)를 입력합니다.

1. 데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.

1. 아래 나열된 열의 데이터 유형을 업데이트하세요.
   - **DateOfBirth**: 날짜
   - **CreatedOn**: 날짜/시간/영역

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="생년월일을 현재로 변환합니다.":::

1. 오른쪽 창의 '이름' 필드에서 데이터 원본의 이름을 **쿼리** 에서 **eCommerceContacts** 로 바꿉니다.

1. 데이터 원본을 **저장** 합니다.

### <a name="ingest-online-purchase-data"></a>온라인 구매 데이터 수집

1. 동일한 **전자상거래** 데이터 원본에 다른 데이터 원본을 추가합니다. **텍스트/CSV** 커넥터를 다시 선택합니다.

1. **온라인 구매** 데이터 URL인 [https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline)을 입력합니다.

1. 데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.

1. 아래 나열된 열의 데이터 유형을 업데이트하세요.
   - **PurchasedOn**: 날짜/시간
   - **TotalPrice**: 통화

1. 측면 창의 **이름** 필드에서 데이터 원본의 이름을 **쿼리** 에서 **eCommercePurchases** 로 바꿉니다.

1. 데이터 원본을 **저장** 합니다.

### <a name="ingest-customer-data-from-loyalty-schema"></a>충성도 스키마에서 고객 데이터 수집

1. **LoyaltyScheme** 이라는 데이터 원본을 만들고 가져오기 옵션을 선택한 다음 **텍스트/CSV** 커넥터를 선택합니다.

1. 전자상거래 연락처 URL인 [https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty)를 입력합니다.

1. 데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.

1. 아래 나열된 열의 데이터 유형을 업데이트하세요.
   - **DateOfBirth**: 날짜
   - **RewardsPoints**: 정수
   - **CreatedOn**: 날짜/시간

1. 오른쪽 창의 **이름** 필드에서 데이터 원본의 이름을 **쿼리** 에서 **loyCustomers** 로 바꿉니다.

1. 데이터 원본을 **저장** 합니다.

## <a name="task-2---data-unification"></a>작업 2 - 데이터 통합

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>작업 3 - 제품 추천 예측 구성

통합 고객 프로필이 있으면 이제 제품 추천 예측을 실행할 수 있습니다.

1. **인텔리전스** > **예측** 으로 이동하여 **제품 추천** 을 선택합니다.

1. **시작** 을 선택합니다.

1. 모델 이름을 **OOB 제품 추천 모델 예측** 으로 지정하고 출력 엔티티를 **OOBProductRecommendationModelPrediction** 으로 지정합니다.

1. 모델에 대한 세 가지 조건을 정의합니다.

   - **제품 수**: 이 값을 **5** 로 설정합니다. 이 설정은 고객에게 추천할 제품 수를 정의합니다.

   - **예상되는 반복 구매**: **예** 를 선택하여 고객이 이전에 구매한 추천에 제품을 포함할 것임을 나타냅니다.

   - **과거 기록 보기 창:** **365 일** 이상을 선택합니다. 이 설정은 모델이 추천에 대한 입력으로 사용하기 위해 고객의 활동을 되돌아 볼 기간을 정의합니다.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="제품 추천 모델에 대한 모델 선호 설정입니다.":::

1. **필수 데이터 추가** 단계에서 **데이터 추가** 를 선택합니다.

1. **데이터 추가** 창에서 구매 내역 엔터티로 **SalesOrderLine** 을 선택합니다. 이 시점에서 아직 구성되지 않았을 수 있습니다. 다음 단계에 따라 활동을 생성하려면 창에서 링크를 엽니다.
   1. **활동 이름** 을 입력하고 **활동 엔터티** 로 *eCommercePurchases:eCommerce* 를 선택합니다. **기본 키** 는 *PurchaseId* 입니다.
   1. *eCommerceContacts:eCommerce entity* 에 대한 관계를 정의하고 이름을 지정하고 **ContactId** 를 외래 키로 선택합니다.
   1. 활동 통합을 위해 **이벤트 활동** 을 *TotalPrice* 로, 타임스탬프를 *PurchasedOn* 으로 설정합니다. [고객 활동](activities.md)에 설명된 대로 더 많은 필드를 지정할 수 있습니다.
   1. **활동 유형** 에 *SalesOrderLine* 을 선택합니다. 다음 활동 필드를 매핑합니다.
      - 주문 라인 ID: PurchaseId
      - 주문 번호: PurchaseId
      - 주문 날짜: PurchasedOn
      - 제품 ID: ProductId
      - 금액: TotalPrice
   1. 모델 구성으로 돌아가기 전에 활동을 검토하고 완료하십시오.

1. **활동 선택** 단계로 돌아가 **활동** 섹션에서 새로 생성된 활동을 선택합니다. **다음** 을 선택하면 특성 매핑이 이미 채워져 있습니다. **저장** 을 선택합니다.

1. 이 샘플 가이드에서는 제품 정보 데이터가 없기 때문에 **제품 정보 추가** 및 **제품 필터** 설정을 건너뜁니다.

1. **데이터 업데이트** 단계에서, 모델 일정을 설정합니다.

   모델은 수집된 새 데이터가 있을 때 새로운 패턴을 학습하기 위해 정기적으로 학습해야 합니다. 이 예에서는 **월별** 을 선택합니다.

1. 모든 세부 정보를 검토한 후 **저장 및 실행** 을 선택합니다. 모델을 처음 실행하는 데 몇 분 정도 걸립니다.

## <a name="task-4---review-model-results-and-explanations"></a>작업 4 - 모델 결과 및 설명 검토

모델이 데이터의 학습 및 채점을 완료하도록 합니다. 이제 제품 추천 모델 설명을 검토할 수 있습니다. 자세한 내용은 [예측 상태 및 결과를 검토](predict-transactional-churn.md#review-a-prediction-status-and-results)를 참조하세요.

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>작업 5 - 자주 구매한 제품 세그먼트 만들기

프로덕션 모델을 실행하면 **데이터** > **엔티티** 에서 볼 수 있는 새 엔티티가 생성됩니다.

모델에서 생성한 엔터티를 기반으로 새 세그먼트를 생성할 수 있습니다.

1. **세그먼트** 로 이동 **새로 만들기** 를 선택하고 **인텔리전스에서 만들기** 를 선택합니다.

   ![모델 출력으로 세그먼트 생성.](media/segment-intelligence.png)

1. **OOBProductRecommendationModelPrediction** 엔드포인트를 선택하고 세그먼트를 정의합니다.

   - 필드: ProductID
   - 값: 상위 3개 제품 ID 선택

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="모델 결과에서 세그먼트를 만듭니다.":::

이제 세 가지 가장 권장되는 제품을 구매하는 데 관심이 있을 수 있는 고객을 식별하는 동적으로 업데이트되는 세그먼트가 있습니다.

자세한 내용은 [세그먼트 만들기 및 관리](segments.md)를 참조하세요.

[!INCLUDE [footer-include](includes/footer-banner.md)]
