---
title: 트랜잭션 이탈 예측 샘플 가이드
description: 이 샘플 가이드를 사용하여 즉시 사용 가능한 트랜잭션 이탈 예측 모델을 사용해보세요.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ccc32b6e5e96adf6f2fa8c6d52960a07d1513f3
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609692"
---
# <a name="transactional-churn-prediction-sample-guide"></a>트랜잭션 이탈 예측 샘플 가이드

이 가이드는 샘플 데이터를 사용한 트랜잭션 이탈 예측의 엔드투엔드 예를 안내합니다. [새로운 환경에서](manage-environments.md) 이 예측을 시도하는 것이 좋습니다.

## <a name="scenario"></a>시나리오

Contoso는 고품질 커피 및 커피 머신을 생산하는 회사입니다. Contoso Coffee 웹 사이트를 통해 제품을 판매합니다. 목표는 일반적으로 정기적으로 제품을 구매하는 고객이 향후 60일 동안 활성 고객이 되는 것을 중단할 것인지를 아는 것입니다. 고객이 **이탈할 가능성이** 있는 고객을 파악하면 고객 유지에 집중하여 마케팅 노력을 절약 할 수 있습니다.

## <a name="prerequisites"></a>전제 조건

- 최소한 [기여자 권한](permissions.md)이 있어야 합니다.

## <a name="task-1---ingest-data"></a>작업 1 - 데이터 수집

[데이터 수집 정보](data-sources.md) 및 [Power Query 데이터 원본에 연결](connect-power-query.md) 문서를 검토하세요. 다음 정보는 사용자가 일반적인 데이터 수집에 익숙하다고 가정합니다.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>전자상거래 플랫폼에서 고객 데이터 수집

1. **전자상거래** 라는 데이터 원본을 만들고 **Text/CSV** 커넥터를 선택합니다.

1. 전자상거래 연락처 URL인 https://aka.ms/ciadclasscontacts를 입력합니다.

1. 데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.

1. 아래 나열된 열의 데이터 유형을 업데이트하세요.

   - **DateOfBirth**: 날짜
   - **CreatedOn**: 날짜/시간/영역

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="날짜로 DoB 전환.":::

1. 오른쪽 창의 **이름** 필드에서 데이터 원본의 이름을 **eCommerceContacts** 로 바꿉니다

1. 데이터 원본을 저장합니다.

### <a name="ingest-online-purchase-data"></a>온라인 구매 데이터 수집

1. 동일한 **전자상거래** 데이터 원본에 다른 데이터 원본을 추가합니다. **텍스트/CSV** 커넥터를 다시 선택합니다.

1. 온라인 구매 데이터 URL https://aka.ms/ciadclassonline을 입력합니다.

1. 데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.

1. 아래 나열된 열의 데이터 유형을 업데이트하세요.

   - **PurchasedOn**: 날짜/시간
   - **TotalPrice**: 통화

1. 오른쪽 창의 **이름** 필드에서 데이터 원본의 이름을 **eCommercePurchases** 로 바꿉니다.

1. 데이터 원본을 저장합니다.

### <a name="ingest-customer-data-from-loyalty-schema"></a>충성도 스키마에서 고객 데이터 수집

1. **LoyaltyScheme** 이라는 데이터 원본을 만들고 **Text/CSV** 커넥터를 선택합니다.

1. 전자상거래 연락처 URL인 https://aka.ms/ciadclasscustomerloyalty를 입력합니다.

1. 데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.

1. 아래 나열된 열의 데이터 유형을 업데이트하세요.

   - **DateOfBirth**: 날짜
   - **RewardsPoints**: 정수
   - **CreatedOn**: 날짜/시간

1. 오른쪽 창의 **이름** 필드에서 데이터 원본의 이름을 **loyCustomers** 로 바꿉니다.

1. 데이터 원본을 저장합니다.

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

## <a name="task-4---configure-transaction-churn-prediction"></a>작업 4 - 트랜잭션 이탈 구성 예측

통합 고객 프로필과 활동이 있는 상태에서 트랜잭션 이탈 예측을 실행합니다.

1. **인텔리전스** > **예측** 으로 이동합니다.

1. **만들기** 탭의 **고객 이탈 모델** 에서 **모델 사용** 을 선택합니다.

1. 이탈 유형으로 **구독** 을 선택한 다음 **트랜잭션** 을 선택합니다.

1. 모델 이름을 **OOB 전자상거래 트랜잭션 이탈 예측** 과 출력 엔터티 **OOBeCommerceChurnPrediction** 으로 지정합니다.

1. **다음** 을 선택합니다.

1. 모델 기본 설정 정의:

   - **예측 기간**: 고객 이탈 예측 기간을 **60** 일로 정의합니다.

   - **이탈 정의**: 구매하지 않고 고객이 이탈한 것으로 간주되는 기간 **60** 일입니다.

     :::image type="content" source="media/model-levers.PNG" alt-text="모델 기본 설정 예측 기간 및 변동 정의를 선택합니다.":::

1. **다음** 을 선택합니다.

1. **구매 기록(필수)** 을 선택하고 구매 기록에 대한 **데이터 추가** 를 선택합니다.

1. **SalesOrderLine** 및 eCommercePurchases 엔터티를 선택하고 **다음** 을 선택합니다. 필수 데이터는 활동에서 자동으로 채워집니다. **저장** 을 선택하고 **다음** 을 선택합니다.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="전자상거래 엔터티에 가입하세요.":::

1. **추가 데이터(선택 사항)** 단계를 건너뜁니다.

1. **데이터 업데이트** 단계에서 모델 일정으로 **매월** 을 선택합니다.

1. 모든 세부 정보를 검토한 후 **저장 및 실행** 을 선택합니다.

## <a name="task-5---review-model-results-and-explanations"></a>작업 5 - 모델 결과 및 설명 검토

모델이 데이터의 학습 및 채점을 완료하도록 합니다. 이탈 모델 설명을 검토하십시오. 자세한 내용은 [예측 결과 보기](predict-transactional-churn.md#view-prediction-results)를 참조하세요.

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>작업 6 - 이탈 위험이 높은 고객 세그먼트 생성

프로덕션 모델을 실행하면 **데이터** > **엔터티** 에 나열된 새 항목이 생성됩니다. 모델에서 생성한 엔터티를 기반으로 새 세그먼트를 생성할 수 있습니다.

1. 결과 페이지에서 **세그먼트 생성** 을 선택합니다.

1. **OOBeCommerceChurnPrediction** 엔터티를 사용하여 규칙을 만들고 세그먼트를 정의합니다.
   - **필드**: ChurnScore
   - **연산자**: 보다 큼
   - **값**: 0.6

1. **저장** 을 선택하고 세그먼트를 **실행** 합니다.

이제 이탈 위험이 높은 고객을 식별하는 동적으로 업데이트되는 세그먼트가 있습니다. 자세한 내용은 [세그먼트 만들기 및 관리](segments.md)를 참조하세요.

> [!TIP]
> **새로 만들기** 를 선택하고 **다음에서 생성** > **인텔리전스** 를 선택하여 **세그먼트** 페이지에서 예측 모델에 대한 세그먼트를 생성할 수도 있습니다. 자세한 내용은 [빠른 세그먼트로 새 세그먼트 만들기](segment-quick.md)을 참조하세요.

[!INCLUDE [footer-include](includes/footer-banner.md)]
