---
title: 고객 평생 가치 예측 샘플 가이드
description: 이 샘플 가이드를 사용하여 고객 평생 가치 예측 모델을 사용해보세요.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 351946c734f5a1054eb3769b2d9cced3bed48e15
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740819"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>고객 평생 가치(CLV) 예측 샘플 가이드

이 가이드를 통해 샘플 데이터를 사용하는 Customer Insights에서 고객 평생 가치(CLV) 예측의 엔드투엔드 예를 설명합니다.

## <a name="scenario"></a>시나리오

Contoso는 고품질 커피 및 커피 머신을 생산하는 회사입니다. Contoso Coffee 웹 사이트를 통해 제품을 판매합니다. 회사는 고객이 향후 12개월 동안 창출할 수 있는 가치(수익)를 파악하려고 합니다. 향후 12개월 동안 고객의 기대 가치를 파악하면 고 가치 고객을 대상으로 마케팅 활동을 진행하는 데 도움이 될 것입니다.

## <a name="prerequisites"></a>전제 조건

- Customer Insights에 최소한 [기여자 권한](permissions.md).
- [새로운 환경에서](manage-environments.md) 다음 단계를 구현하는 것이 좋습니다.

## <a name="task-1---ingest-data"></a>작업 1 - 데이터 수집

Power Query 커넥터를 사용한 [데이터 수집](data-sources.md) 및 [데이터 원본 가져오기에 대한 문서](connect-power-query.md)를 검토하세요. 다음 정보는 사용자가 일반적인 데이터 수집에 익숙하다고 가정합니다.

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

### <a name="ingest-customer-data-from-website-reviews"></a>웹 사이트 리뷰에서 고객 데이터 수집

1. **웹 사이트** 라는 데이터 원본을 만들고 가져오기 옵션을 선택한 다음 **텍스트/CSV** 커넥터를 선택합니다.

1. 전자상거래 연락처 URL인 https://aka.ms/CI-ILT/WebReviews를 입력합니다.

1. 데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.

1. 아래 나열된 열의 데이터 유형을 업데이트하세요.

   - **ReviewRating**: 10진수
   - **ReviewDate**: 날짜

1. 오른쪽 창의 '이름' 필드에서 데이터 원본의 이름을 **쿼리** 에서 **리뷰** 로 바꿉니다.

1. 데이터 원본을 **저장** 합니다.

## <a name="task-2---data-unification"></a>작업 2 - 데이터 통합

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>작업 3 - 고객 평생 가치 예측 구성

통합된 고객 프로필을 통해 이제 고객 평생 가치 예측을 실행할 수 있습니다. 자세한 단계는 [고객 평생 가치 예측](predict-customer-lifetime-value.md)을 참조하세요.

1. **인텔리전스**  > **예측** 으로 이동하고 **고객 평생 가치 모델** 을 선택합니다.

1. 측면 창의 정보를 살펴보고 **시작하기** 를 선택합니다.

1. 모델 이름을 **OOB 전자상거래 CLV 예측** 및 출력 엔터티 **OOBeCommerceCLVPrediction** 로 지정합니다.

1. CLV 모델에 대한 모델 기본 설정을 정의합니다.
   - **예측 기간**: **12개월 또는 1년**. 이 설정은 고객 평생 가치를 예측할 수 있는 미래를 정의합니다.
   - **활성 고객**: 활성 고객이 비즈니스에 어떤 의미를 갖는지 지정합니다. 고객이 활성으로 간주되는 트랜잭션이 하나 이상 있어야 하는 과거 시간 프레임를 설정합니다.으로 이 모델은 활성 고객에 대한 CLV만 예측합니다. 모델이 과거 트랜잭션 데이터를 기반으로 기간을 계산하도록 하거나 특정 시간 프레임을 제공하도록 선택합니다. 이 샘플 가이드에서는 기본 옵션인 **모델이 구매 간격을 계산** 하도록 합니다.
   - **고 가치 고객**: 고 가치 고객을 상위 유료 고객의 백분위수로 정의합니다. 모델은 이 입력을 사용하여 고 가치 고객의 비즈니스 정의에 맞는 결과를 제공합니다. 모델이 고 가치 고객을 정의하도록 선택할 수 있습니다. 백분위수를 도출하는 휴리스틱 규칙을 사용합니다. 또한 고 가치 고객을 미래의 상위 유료 고객의 백분위수로 정의할 수도 있습니다. 이 샘플 가이드에서는 고 가치 고객을 **활성 유료 고객의 상위 30%** 로 수동으로 정의하고 **다음** 을 선택합니다.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="CLV 모델에 대한 가이드 환경의 기본 설정 단계입니다.":::

1. **필수 데이터** 단계에서 **데이터 추가** 를 선택하여 트랜잭션 내역 데이터를 제공합니다.

1. **eCommercePurchases : eCommerce** 엔터티를 추가하고 모델에 필요한 특성을 매핑합니다.
   - 트랜잭션 ID: eCommerce.eCommercePurchases.PurchaseId
   - 트랜잭션 날짜: eCommerce.eCommercePurchases.PurchasedOn
   - 트랜잭션 금액: eCommerce.eCommercePurchases.TotalPrice
   - 제품 ID: eCommerce.eCommercePurchases.ProductId

1. **다음** 을 선택합니다.

1. **eCommercePurchases : eCommerce** 엔터티와 **eCommerceContacts : eCommerce** 간의 관계를 설정합니다.

1. **추가 데이터(선택 사항)** 단계에서는 더 많은 고객 활동 데이터를 추가할 수 있습니다. 이 데이터는 CLV에 기여할 수 있는 비즈니스와의 고객 상호 작용에 대한 더 많은 인사이트를 얻는 데 도움이 될 수 있습니다. 웹 로그, 고객 서비스 로그 또는 보상 프로그램 내역과 같은 주요 고객 상호 작용을 추가하면 예측의 정확성을 높일 수 있습니다. 더 많은 고객 활동 데이터를 포함하려면 **데이터 추가** 를 선택합니다.

1. 고객 활동 엔터티를 추가하고 해당 필드 이름을 모델에 필요한 해당 필드에 매핑합니다.
   - 고객 활동 엔터티: Reviews:Website
   - 기본 키: Website.Reviews.ReviewId
   - 타임스탬프: Website.Reviews.ReviewDate
   - 이벤트(활동 이름): Website.Reviews.ActivityTypeDisplay
   - 세부 정보(금액 또는 값): Website.Reviews.ReviewRating

1. **다음** 을 선택하고 트랜잭션 데이터와 고객 데이터 간의 활동과 관계를 구성합니다.  
   - 활동 유형: 기존 선택
   - 활동 레이블: 리뷰
   - 대응 레이블: Website.Reviews.UserId
   - 고객 엔터티: eCommerceContacts:eCommerce
   - 관계: WebsiteReviews

1. **다음** 을 선택하여 모델 일정을 설정합니다.

   모델은 새로운 데이터가 수집될 때 새로운 패턴을 학습하기 위해 정기적으로 학습해야 합니다. 이 예에서는 **월간** 을 선택합니다.

1. 모든 세부 정보를 검토한 후 **저장 및 실행** 을 선택합니다.

## <a name="task-4---review-model-results-and-explanations"></a>작업 4 - 모델 결과 및 설명 검토

모델이 데이터의 학습 및 채점을 완료하도록 합니다. 다음으로 CLV 모델 결과 및 설명을 검토할 수 있습니다. 자세한 내용은 [예측 상태 및 결과를 검토](predict-customer-lifetime-value.md#review-prediction-status-and-results)를 참조하세요.

## <a name="task-5---create-a-segment-of-high-value-customers"></a>작업 5 - 고 가치 고객 세그먼트 만들기

모델을 실행하면 **데이터** > **엔터티** 에 나열된 새 항목이 생성됩니다. 모델에서 생성한 엔터티를 기반으로 새 고객 세그먼트를 만들 수 있습니다.

1. **세그먼트** 로 이동 

1. **새로 만들기** 를 선택하고 **다음에서 만들기** > **인텔리전스** 를 선택합니다.

   ![모델 출력으로 세그먼트 생성.](media/segment-intelligence.png)

1. **OOBeCommerceCLVPrediction** 엔터티를 선택하고 및 다음과 같이 세그먼트를 정의합니다.
  - 필드: CLVScore
  - 연산자: 보다 큼
  - 값: 1500

1. **리뷰** 를 선택하고 세그먼트를 **저장** 합니다.

이제 향후 12개월 동안 $1500 이상의 수익을 창출할 것으로 예측되는 고객을 식별하는 세그먼트를 보유하게 됩니다. 이 세그먼트는 더 많은 데이터가 수집되면 동적으로 업데이트됩니다.

자세한 내용은 [세그먼트 만들기 및 관리](segments.md)를 참조하세요.
