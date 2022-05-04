---
title: 제품 추천 예측 샘플 가이드
description: 이 샘플 가이드를 사용하여 즉시 사용 가능한 제품 추천 예측 모델을 사용해보세요.
ms.date: 02/10/2021
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
ms.openlocfilehash: 1115bab13bdca4a308a8d9eb5a1dc270801d16be
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647107"
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

1. 전자상거래 연락처 URL인 https://aka.ms/ciadclasscontacts를 입력합니다.

1. 데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.

1. 아래 나열된 열의 데이터 유형을 업데이트하세요.
   - **DateOfBirth**: 날짜
   - **CreatedOn**: 날짜/시간/영역

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="생년월일을 현재로 변환합니다.":::

5. 오른쪽 창의 '이름' 필드에서 데이터 원본의 이름을 **쿼리** 에서 **eCommerceContacts** 로 바꿉니다.

6. 데이터 원본을 **저장** 합니다.

### <a name="ingest-online-purchase-data"></a>온라인 구매 데이터 수집

1. 동일한 **전자상거래** 데이터 원본에 다른 데이터 원본을 추가합니다. **텍스트/CSV** 커넥터를 다시 선택합니다.

1. **온라인 구매** 데이터 URL인 https://aka.ms/ciadclassonline을 입력합니다.

1. 데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.

1. 아래 나열된 열의 데이터 유형을 업데이트하세요.
   - **PurchasedOn**: 날짜/시간
   - **TotalPrice**: 통화

1. 측면 창의 **이름** 필드에서 데이터 원본의 이름을 **쿼리** 에서 **eCommercePurchases** 로 바꿉니다.

1. 데이터 원본을 **저장** 합니다.


### <a name="ingest-customer-data-from-loyalty-schema"></a>충성도 스키마에서 고객 데이터 수집

1. **LoyaltyScheme** 이라는 데이터 원본을 만들고 가져오기 옵션을 선택한 다음 **텍스트/CSV** 커넥터를 선택합니다.

1. 전자상거래 연락처 URL인 https://aka.ms/ciadclasscustomerloyalty를 입력합니다.

1. 데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.

1. 아래 나열된 열의 데이터 유형을 업데이트하세요.
   - **DateOfBirth**: 날짜
   - **RewardsPoints**: 정수
   - **CreatedOn**: 날짜/시간

1. 오른쪽 창의 **이름** 필드에서 데이터 원본의 이름을 **쿼리** 에서 **loyCustomers** 로 바꿉니다.

1. 데이터 원본을 **저장** 합니다.

## <a name="task-2---data-unification"></a>작업 2 - 데이터 통합

데이터를 수집한 후 이제 데이터 통합 프로세스를 시작하여 통합 고객 프로필을 만듭니다. 자세한 내용은 [데이터 통합](data-unification.md)을 참조하십시오.

### <a name="map"></a>매핑

1. 데이터를 수집한 후 전자상거래 및 충성도 데이터의 연락처를 공통 데이터 유형에 매핑합니다. **데이터** > **통합** > **매핑** 으로 이동합니다.

2. 고객 프로필을 나타내는 엔터티(**eCommerceContacts** 및 **loyCustomers**)를 선택합니다.

   ![전자상거래와 충성도 데이터 원본을 통합합니다.](media/unify-ecommerce-loyalty.png)

3. **eCommerceContacts** 의 기본 키로 **ContactId** 를 선택하고 **loyCustomers** 의 기본 키로 **LoyaltyID** 를 선택합니다.

   ![LoyaltyId를 기본 키로 통합합니다.](media/unify-loyaltyid.png)

### <a name="match"></a>일치

1. **일치 탭** 으로 이동한 다음 **순서 설정** 을 선택합니다.

2. **기본** 드롭다운 목록에서 **eCommerceContacts : eCommerce** 를 기본 소스로 선택하고 모든 레코드를 포함합니다.

3. **엔터티 2** 드롭다운 목록에서 **loyCustomers : LoyaltyScheme** 을 선택하고 모든 레코드를 포함합니다.

   ![전자상거래와 충성도 데이터 원본을 통합합니다.](media/unify-match-order.png)

4. **새 규칙 만들기** 선택

5. FullName을 사용하여 첫 번째 조건을 추가합니다.

   - eCommerceContacts의 경우 드롭다운에서 **FullName** 을 선택합니다.
   - loyCustomers의 경우 드롭다운에서 **FullName** 을 선택합니다.
   - **정규화** 드롭다운을 선택하고 **유형(전화, 이름, 주소, ...)** 을 선택합니다.
   - **정밀도 수준**: **기본** 및 **값**: **높음** 을 설정합니다.

6. 새 규칙의 이름에 **FullName, Email** 을 입력합니다.

   - **조건 추가** 를 선택하여 이메일 주소에 대한 두 번째 조건을 추가합니다.
   - 엔터티 eCommerceContacts의 경우 드롭다운에서 **이메일** 을 선택합니다.
   - 엔터티 loyCustomers의 경우 드롭다운에서 **이메일** 을 선택합니다.
   - 정규화를 비워 둡니다.
   - **정밀도 수준**: **기본** 및 **값**: **높음** 을 설정합니다.

   ![이름 및 이메일에 대한 일치 규칙을 통합합니다.](media/unify-match-rule.png)

7. **저장** 및 **실행** 을 선택합니다.

### <a name="merge"></a>병합

1. **병합** 탭으로 이동합니다.

1. **loyCustomers** 엔터티의 **ContactId** 에서 표시 이름을 **ContactIdLOYALTY** 로 변경하여 수집된 다른 ID와 구별합니다.

   ![포인트 ID에서 contactid의 이름을 바꿉니다.](media/unify-merge-contactid.png)

1. **저장** 및 **실행** 을 선택하여 병합 프로세스를 시작합니다.

## <a name="task-3---configure-product-recommendation-prediction"></a>작업 3 - 제품 추천 예측 구성

통합된 고객 프로필을 사용하면 이제 구독 이탈 예측을 실행할 수 있습니다.

1. **인텔리전스** > **예측** 으로 이동하여 **제품 추천** 을 선택합니다.

1. **시작** 을 선택합니다.

1. 모델 이름을 **OOB 제품 추천 모델 예측** 으로 지정하고 출력 엔티티를 **OOBProductRecommendationModelPrediction** 으로 지정합니다.

1. 모델에 대한 세 가지 조건을 정의합니다.

   - **제품 수**: 이 값을 **5** 로 설정합니다. 이 설정은 고객에게 추천할 제품 수를 정의합니다.

   - **예상되는 반복 구매**: **예** 를 선택하여 고객이 이전에 구매한 추천에 제품을 포함할 것임을 나타냅니다.

   - **과거 기록 보기 창:** **365 일** 이상을 선택합니다. 이 설정은 모델이 추천에 대한 입력으로 사용하기 위해 고객의 활동을 되돌아 볼 기간을 정의합니다.
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="제품 추천 모델에 대한 모델 선호 설정입니다.":::

1. **필수 데이터** 를 선택하고 구매 기록에 대한 **데이터 추가** 를 선택합니다.

1. **eCommercePurchases : 전자상거래** 추가 엔터티를 추가하고 전자상거래의 필드를 모델에 필요한 해당 필드에 매핑합니다.

1. **eCommercePurchases : 전자상거래** 엔터티와 **eCommerceContacts : 전자상거래** 에 가입하세요.

   ![전자상거래 엔터티에 가입하세요.](media/model-purchase-join.png)

1. **다음** 을 선택하여 모델 일정을 설정합니다.

   모델은 수집된 새 데이터가 있을 때 새로운 패턴을 학습하기 위해 정기적으로 학습해야 합니다. 이 예에서는 **월별** 을 선택합니다.

1. 모든 세부 정보를 검토한 후 **저장 및 실행** 을 선택합니다.


## <a name="task-4---review-model-results-and-explanations"></a>작업 4 - 모델 결과 및 설명 검토

모델이 데이터의 학습 및 채점을 완료하도록 합니다. 이제 제품 추천 모델 설명을 검토할 수 있습니다. 자세한 내용은 [예측 상태 및 결과를 검토](predict-subscription-churn.md#review-a-prediction-status-and-results)를 참조하세요.

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>작업 5 - 자주 구매한 제품 세그먼트 만들기

프로덕션 모델을 실행하면 **데이터** > **엔티티** 에서 볼 수 있는 새 엔티티가 생성됩니다.

모델에서 생성한 엔터티를 기반으로 새 세그먼트를 생성할 수 있습니다.

1. **세그먼트** 로 이동 **새로 만들기** 를 **만들기** > **인텔리전스** 를 선택합니다.

   ![모델 출력으로 세그먼트 생성.](media/segment-intelligence.png)

1. **OOBProductRecommendationModelPrediction** 엔드포인트를 선택하고 세그먼트를 정의합니다.

   - 필드: ProductID
   - 연산자: 값
   - 값: 상위 3개 제품 ID 선택

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="모델 결과에서 세그먼트를 만듭니다.":::

이제 가장 추천하는 세 가지 제품을 구매할 의사가 있는 고객을 식별하며 동적으로 업데이트되는 세그먼트를 보유했습니다. 

자세한 내용은 [세그먼트 만들기 및 관리](segments.md)를 참조하세요.


[!INCLUDE [footer-include](includes/footer-banner.md)]
