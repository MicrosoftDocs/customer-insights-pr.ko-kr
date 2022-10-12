---
title: 고객 평생 가치(CLV) 예측 샘플 가이드
description: 이 샘플 가이드를 사용하여 고객 평생 가치 예측 모델을 사용해보세요.
ms.date: 09/15/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: fec43b279326daa17fb179181f5e310c99d48bb7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609646"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>고객 평생 가치(CLV) 예측 샘플 가이드

이 가이드를 통해 샘플 데이터를 사용하는 Customer Insights에서 고객 평생 가치(CLV) 예측의 엔드투엔드 예를 설명합니다. [새로운 환경에서](manage-environments.md) 이 예측을 시도하는 것이 좋습니다.

## <a name="scenario"></a>시나리오

Contoso는 고품질 커피 및 커피 머신을 생산하는 회사입니다. Contoso Coffee 웹 사이트를 통해 제품을 판매합니다. 회사는 고객이 향후 12개월 동안 창출할 수 있는 가치(수익)를 파악하려고 합니다. 향후 12개월 동안 고객의 기대 가치를 파악하면 고 가치 고객을 대상으로 마케팅 활동을 진행하는 데 도움이 될 것입니다.

## <a name="prerequisites"></a>전제 조건

- 최소한 [기여자 권한](permissions.md)이 있어야 합니다.

## <a name="task-1---ingest-data"></a>작업 1 - 데이터 수집

[데이터 수집 정보](data-sources.md) 및 [Power Query 데이터 원본에 연결](connect-power-query.md) 문서를 검토하세요. 다음 정보는 사용자가 일반적인 데이터 수집에 익숙하다고 가정합니다.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>전자상거래 플랫폼에서 고객 데이터 수집

1. **전자상거래** 라는 Power Query 데이터 원본을 만들고 **Text/CSV** 커넥터를 선택합니다.

1. 전자상거래 연락처 URL인 https://aka.ms/ciadclasscontacts를 입력합니다.

1. 데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.

1. 아래 나열된 열의 데이터 유형을 업데이트하세요.
   - **DateOfBirth**: 날짜
   - **CreatedOn**: 날짜/시간/영역

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="생년월일을 현재로 변환합니다.":::

1. 오른쪽 창의 **이름** 필드에서 데이터 원본의 이름을 **eCommerceContacts** 로 바꿉니다

1. 데이터 원본을 **저장** 합니다.

### <a name="ingest-online-purchase-data"></a>온라인 구매 데이터 수집

1. 동일한 **전자상거래** 데이터 원본에 다른 데이터 원본을 추가합니다. **텍스트/CSV** 커넥터를 다시 선택합니다.

1. **온라인 구매** 데이터 URL인 https://aka.ms/ciadclassonline을 입력합니다.

1. 데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.

1. 아래 나열된 열의 데이터 유형을 업데이트하세요.
   - **PurchasedOn**: 날짜/시간
   - **TotalPrice**: 통화

1. 측면 창의 **이름** 필드에서 데이터 원본의 이름을 **eCommercePurchases** 로 바꿉니다.

1. 데이터 원본을 **저장** 합니다.

### <a name="ingest-customer-data-from-loyalty-schema"></a>충성도 스키마에서 고객 데이터 수집

1. **LoyaltyScheme** 이라는 데이터 원본을 만들고 **Text/CSV** 커넥터를 선택합니다.

1. 충성도가 높은 고객의 URL https://aka.ms/ciadclasscustomerloyalty를 입력합니다.

1. 데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.

1. 아래 나열된 열의 데이터 유형을 업데이트하세요.
   - **DateOfBirth**: 날짜
   - **RewardsPoints**: 정수
   - **CreatedOn**: 날짜/시간

1. 오른쪽 창의 **이름** 필드에서 데이터 원본의 이름을 **loyCustomers** 로 바꿉니다.

1. 데이터 원본을 **저장** 합니다.

### <a name="ingest-customer-data-from-website-reviews"></a>웹 사이트 리뷰에서 고객 데이터 수집

1. **웹 사이트** 라는 데이터 원본을 만들고 **Text/CSV** 커넥터를 선택합니다.

1. 웹사이트 리뷰의 URL https://aka.ms/CI-ILT/WebReviews를 입력합니다.

1. 데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.

1. 아래 나열된 열의 데이터 유형을 업데이트하세요.
   - **ReviewRating**: 10진수
   - **ReviewDate**: 날짜

1. 오른쪽 창의 **이름** 필드에서 데이터 원본의 이름을 **Reviews** 로 바꿉니다.

1. 데이터 원본을 **저장** 합니다.

## <a name="task-2---data-unification"></a>작업 2 - 데이터 통합

[데이터 통합 정보](data-unification.md) 문서를 검토하세요. 다음 정보는 일반적으로 데이터 통합에 익숙하다고 가정합니다.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>작업 3 - 트랜잭션 기록 활동 만들기

[고객 활동 정보](activities.md) 문서를 검토하세요. 다음 정보는 일반적으로 활동 만들기에 익숙하다고 가정합니다.

1. *eCommercePurchases:eCommerce* 엔터티와 기본 키 **PurchaseId** 를 사용하여 **eCommercePurchases** 라는 활동을 만듭니다.

1. *eCommercePurchases:eCommerce* 과 *eCommerceContacts:eCommerce* 간의 관계를 생성하고 **ContactID** 을 외래 키로 사용하여 두 엔터티를 연결합니다.

1. **EventActivity** 에 대해 **TotalPrice** 을 선택하고 **타임스탬프** 에 대해 **PurchasedOn** 을 선택합니다.

1. **활동 유형** 에 대해 **SalesOrderLine** 을 선택하고 활동 데이터를 의미적으로 매핑합니다.

1. 활동을 실행합니다.

1. 다른 활동을 추가하고 해당 필드 이름을 해당 필드에 매핑합니다.
   - **활동 엔터티**: Reviews:Website
   - **기본 키**: ReviewId
   - **타임스탬프**: ReviewDate
   - **이벤트 활동**: ActivityTypeDisplay
   - **추가 세부 정보**: ReviewRating
   - **활동 유형**: Review

1. 활동을 실행합니다.

## <a name="task-4---configure-customer-lifetime-value-prediction"></a>작업 4 - 고객 평생 가치 예측 구성

통합된 고객 프로필이 준비되고 활동이 생성되면 CLV(고객평생가치) 예측을 실행합니다. 자세한 단계는 [고객 평생 가치 예측](predict-customer-lifetime-value.md)을 참조하세요.

1. **인텔리전스** > **예측** 으로 이동합니다.

1. **만들기** 탭의 **고객 평생 가치** 타일에서 **모델 사용** 을 선택합니다.

1. **시작** 을 선택합니다.

1. 모델 이름을 **OOB 전자상거래 CLV 예측** 및 출력 엔터티 **OOBeCommerceCLVPrediction** 로 지정합니다.

1. 모델 기본 설정 정의:
   - **예측 기간**: **12개월 또는 1년** 으로 CLV를 예측할 미래를 정의합니다.
   - **활성 고객**: 고객이 활성으로 간주되기 위해 하나 이상의 트랜잭션을 가지고 있어야 하는 시간 프레임인 **구매 간격을 계산하도록 합니다**.
   - **고 가치 고객**: 수동으로 고 가치 고객을 **활성 고객의 상위 30%** 로 정의합니다.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="CLV 모델에 대한 가이드 환경의 기본 설정 단계입니다.":::

1. **다음** 을 선택합니다.

1. **필수 데이터** 단계에서 **데이터 추가** 를 선택하여 트랜잭션 기록 데이터를 제공합니다.

    :::image type="content" source="media/clv-model-required.png" alt-text="CLV 모델에 대한 안내 환경에서 필수 데이터 단계를 추가합니다.":::

1. **SalesOrderLine** 및 eCommercePurchases 엔터티를 선택하고 **다음** 을 선택합니다. 필수 데이터는 활동에서 자동으로 채워집니다. **저장** 을 선택하고 **다음** 을 선택합니다.

1. **추가 데이터(선택 사항)** 단계를 통해 더 많은 고객 활동 데이터를 추가하여 고객 상호 작용에 대한 더 많은 인사이트를 얻을 수 있습니다. 이 예에서는 **데이터 추가** 를 선택하고 웹 검토 활동을 추가합니다.

1. **다음** 을 선택합니다.

1. **데이터 업데이트** 단계에서 모델 일정으로 **매월** 을 선택합니다.

1. **다음** 을 선택합니다.

1. 모든 세부 정보를 검토한 후 **저장 및 실행** 을 선택합니다.

## <a name="task-5---review-model-results-and-explanations"></a>작업 5 - 모델 결과 및 설명 검토

모델이 데이터의 학습 및 채점을 완료하도록 합니다. [CLV 모델 결과 및 설명](predict-customer-lifetime-value.md#view-prediction-results)을 검토하십시오.

## <a name="task-6---create-a-segment-of-high-value-customers"></a>작업 6 - 고 가치 고객 세그먼트 만들기

모델을 실행하면 **데이터** > **엔터티** 에 나열된 새 항목이 생성됩니다. 모델에서 생성한 엔터티를 기반으로 새 고객 세그먼트를 만들 수 있습니다.

1. 결과 페이지에서 **세그먼트 생성** 을 선택합니다.

1. **OOBeCommerceCLVPrediction** 엔터티를 사용하여 규칙을 만들고 세그먼트를 정의합니다.
   - **필드**: CLVScore
   - **연산자**: 보다 큼
   - **값**: 1500

1. **저장** 을 선택하고 세그먼트를 **실행** 합니다.

이제 향후 12개월 동안 $1500 이상의 수익을 창출할 것으로 예측되는 고객을 식별하는 세그먼트를 보유하게 됩니다. 이 세그먼트는 더 많은 데이터가 수집되면 동적으로 업데이트됩니다. 자세한 내용은 [세그먼트 만들기 및 관리](segments.md)를 참조하세요.

> [!TIP]
> **새로 만들기** 를 선택하고 **다음에서 생성** > **인텔리전스** 를 선택하여 **세그먼트** 페이지에서 예측 모델에 대한 세그먼트를 생성할 수도 있습니다. 자세한 내용은 [빠른 세그먼트로 새 세그먼트 만들기](segment-quick.md)을 참조하세요.

[!INCLUDE [footer-include](includes/footer-banner.md)]
