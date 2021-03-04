---
title: 구독 이탈 예측 샘플 가이드
description: 이 샘플 가이드를 사용하여 즉시 사용 가능한 구독 이탈 예측 모델을 사용해보세요.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3f1019ace424f89320c5a0d5058e928f4cbc7e62
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269844"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a>구독 이탈 예측(미리 보기) 샘플 가이드

아래 제공된 샘플 데이터를 사용하여 구독 이탈 예측의 엔드 투 엔드 예를 안내합니다. 

## <a name="scenario"></a>시나리오

Contoso는 고품질 커피 및 커피 머신을 생산하는 회사로 Contoso Coffee 웹 사이트를 통해 판매합니다. 최근에는 고객이 정기적으로 커피를 마실 수 있도록 구독 사업을 시작했습니다. 목표는 어떤 구독 고객이 앞으로 몇 달 안에 구독을 취소할 수 있는지 파악하는 것입니다. 고객이 **이탈할 가능성이** 있는 고객을 파악하면 고객 유지에 집중하여 마케팅 노력을 절약 할 수 있습니다.

## <a name="prerequisites"></a>필수 구성 요소

- Customer Insights에 최소한 [기여자 권한](permissions.md).
- [새로운 환경에서](manage-environments.md) 다음 단계를 구현하는 것이 좋습니다.

## <a name="task-1---ingest-data"></a>작업 1 - 데이터 수집

파워 쿼리 커넥터를 사용하여 [데이터 수집](data-sources.md) 및 [데이터 원본 가져오기](connect-power-query.md)에 대한 문서를 검토하세요. 다음 정보는 사용자가 일반적인 데이터 수집에 익숙하다고 가정합니다. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>전자상거래 플랫폼에서 고객 데이터 수집

1. **전자상거래** 라는 데이터 원본을 만들고 가져오기 옵션을 선택한 다음 **텍스트/CSV** 커넥터를 선택합니다.

1. 전자상거래 연락처 URL인 https://aka.ms/ciadclasscontacts를 입력합니다.

1. 데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.

1. 아래 나열된 열의 데이터 유형을 업데이트하세요.

   - **DateOfBirth**: 날짜
   - **CreatedOn**: 날짜/시간/영역

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="생년월일을 현재로 변환합니다.":::

1. 오른쪽 창의 **이름** 필드에서 데이터 원본의 이름을 **쿼리** 에서 **eCommerceContacts** 로 바꿉니다.

1. 데이터 원본을 저장합니다.

### <a name="ingest-customer-data-from-loyalty-schema"></a>충성도 스키마에서 고객 데이터 수집

1. **LoyaltyScheme** 이라는 데이터 원본을 만들고 가져오기 옵션을 선택한 다음 **텍스트/CSV** 커넥터를 선택합니다.

1. 전자상거래 연락처 URL인 https://aka.ms/ciadclasscustomerloyalty를 입력합니다.

1. 데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.

1. 아래 나열된 열의 데이터 유형을 업데이트하세요.

   - **DateOfBirth**: 날짜
   - **RewardsPoints**: 정수
   - **CreatedOn**: 날짜/시간

1. 오른쪽 창의 **이름** 필드에서 데이터 원본의 이름을 **쿼리** 에서 **loyCustomers** 로 바꿉니다.

1. 데이터 원본을 저장합니다.

### <a name="ingest-subscription-information"></a>구독 정보 수집

1. **SubscriptionHistory** 이라는 데이터 원본을 만들고 가져오기 옵션을 선택한 다음 **텍스트/CSV** 커넥터를 선택합니다.

1. 전자상거래 연락처 URL인 https://aka.ms/ciadchurnsubscriptionhistory를 입력합니다.

1. 데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.

1. 아래 나열된 열의 데이터 유형을 업데이트하세요.

   - **SubscriptioID**: 정수
   - **SubscriptionAmount**: 통화
   - **SubscriptionEndDate**: 날짜/시간
   - **SubscriptionStartDate**: 날짜/시간
   - **TransactionDate**: 날짜/시간
   - **IsRecurring**: 참/거짓
   - **Is_auto_renew**: 참/거짓
   - **RecurringFrequencyInMonths**: 정수

1. 오른쪽 창의 **이름** 필드에서 데이터 원본의 이름을 **쿼리** 에서 **SubscriptionHistory** 로 바꿉니다.

1. 데이터 원본을 저장합니다.

### <a name="ingest-customer-data-from-website-reviews"></a>웹 사이트 리뷰에서 고객 데이터 수집

1. **웹 사이트** 라는 데이터 원본을 만들고 가져오기 옵션을 선택한 다음 **텍스트/CSV** 커넥터를 선택합니다.

1. 전자상거래 연락처 URL인 https://aka.ms/ciadclasswebsite를 입력합니다.

1. 데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.

1. 아래 나열된 열의 데이터 유형을 업데이트하세요.

   - **ReviewRating**: 정수
   - **ReviewDate**: 날짜

1. 오른쪽 창의 '이름' 필드에서 데이터 원본의 이름을 **쿼리** 에서 **webReviews** 로 바꿉니다.

## <a name="task-2---data-unification"></a>작업 2 - 데이터 통합

데이터를 수집 한 후 이제 **매핑, 일치, 병합** 프로세스를 시작하여 통합 고객 프로필을 만듭니다. 자세한 내용은 [데이터 통합](data-unification.md)을 참조하십시오.

### <a name="map"></a>매핑

1. 데이터를 수집한 후 전자상거래 및 충성도 데이터의 연락처를 공통 데이터 유형에 매핑합니다. **데이터** > **통합** > **매핑** 으로 이동합니다.

1. 고객 프로필을 나타내는 엔터티(**eCommerceContacts** 및 **loyCustomers**)를 선택합니다. 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="전자상거래와 충성도 데이터 원본을 통합합니다.":::

1. **eCommerceContacts** 의 기본 키로 **ContactId** 를 선택하고 **loyCustomers** 의 기본 키로 **LoyaltyID** 를 선택합니다.

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="LoyaltyId를 기본 키로 통합합니다.":::

### <a name="match"></a>일치

1. **일치 탭** 으로 이동한 다음 **순서 설정** 을 선택합니다.

1. **기본** 드롭다운 목록에서 **eCommerceContacts : eCommerce** 를 기본 소스로 선택하고 모든 레코드를 포함합니다.

1. **엔터티 2** 드롭다운 목록에서 **loyCustomers : LoyaltyScheme** 을 선택하고 모든 레코드를 포함합니다.

   :::image type="content" source="media/unify-match-order.PNG" alt-text="전자상거래와 충성도 데이터 원본을 통합합니다.":::

1. **새 규칙 만들기** 선택

1. FullName을 사용하여 첫 번째 조건을 추가합니다.

   * eCommerceContacts의 경우 **FullName** 드롭다운에서 선택합니다.
   * loyCustomers의 경우 **FullName** 드롭다운에서 선택합니다.
   * **정규화** 드롭다운을 선택하고 **유형(전화, 이름, 주소, ...)** 을 선택합니다.
   * **정밀도 수준**: **기본** 및 **값**: **높음** 을 설정합니다.

1. 새 규칙의 이름에 **FullName, Email** 을 입력합니다.

   * **조건 추가** 를 선택하여 이메일 주소에 대한 두 번째 조건을 추가합니다.
   * 엔터티 eCommerceContacts의 경우 드롭다운에서 **이메일** 을 선택합니다.
   * 엔터티 loyCustomers의 경우 드롭다운에서 **이메일** 을 선택합니다. 
   * 정규화를 비워 둡니다. 
   * **정밀도 수준**: **기본** 및 **값**: **높음** 을 설정합니다.

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="이름 및 이메일에 대한 일치 규칙을 통합합니다.":::

7. **저장** 및 **실행** 을 선택합니다.

### <a name="merge"></a>병합

1. **병합** 탭으로 이동합니다.

1. **loyCustomers** 엔터티의 **ContactId** 에서 표시 이름을 **ContactIdLOYALTY** 로 변경하여 수집된 다른 ID와 구별합니다.

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="포인트 ID에서 contactid의 이름을 바꿉니다.":::

1. **저장** 및 **실행** 을 선택하여 병합 프로세스를 시작합니다.


## <a name="task-3---configure-the-subscription-churn-prediction"></a>작업 3 - 구독 이탈 구성 예측

통합된 고객 프로필을 사용하면 이제 구독 이탈 예측을 실행할 수 있습니다. 자세한 단계는 [구독 이탈 예측(미리보기)](predict-subscription-churn.md) 문서를 참조하세요. 

1. **인텔리전스** > **검색** 으로 이동하여 **고객 이탈 모델** 을 사용하도록 선택합니다.

1. **구독** 옵션을 선택하고 **시작** 을 선택합니다.

1. 모델 이름을 **OOB 구독 이탈 예측** 과 출력 엔터티 **OOBSubscriptionChurnPrediction** 으로 지정합니다.

1. 이탈 모델에 대한 두 가지 조건을 정의합니다.

   * **구독 종료 이후 일수**: **최소 60** 일. 고객이 구독이 종료된 이후 이 기간 동안 구독을 갱신하지 않으면 이탈된 것으로 간주됩니다. 

   * **이탈 정의**: **최소 93** 일. 모델이 이탈 할 수 있는 고객을 예측하는 기간입니다. 앞으로 더 멀어질수록 결과의 정확도가 떨어집니다.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="모델 레버 예측 창 및 변동 정의를 선택합니다.":::

1. **필수 데이터 추가** 를 선택하고 구독 기록에 대한 **데이터 추가** 를 선택합니다.

1. **Subscription : SubscriptionHistory** 추가 엔터티를 추가하고 전자상거래의 필드를 모델에 필요한 해당 필드에 매핑합니다.

1. **eCommerceContacts : eCommerce** 와 함께 **Subscription : SubscriptionHistory** 엔터티에 가입하고 관계 이름을 **eCommerceSubscription** 으로 지정합니다.

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="전자상거래 엔터티에 가입하세요.":::

1. 고객 활동 아래 **webReviews : Website** 엔터티를 추가하고 webReviews의 필드를 모델에 필요한 해당 필드에 매핑합니다. 
   - 기본 키: ReviewId
   - 타임스탬프: ReviewDate
   - 이벤트: ReviewRating

1. 웹 사이트 검토를 위한 활동을 구성합니다. 활동 **검토** 를 선택하고 **eCommerceContacts : eCommerce** 와 함께 **webReviews : Website** 엔티티에 참여하세요.

1. **다음** 을 선택하여 모델 일정을 설정합니다.

   모델은 수집된 새 데이터가 있을 때 새로운 패턴을 학습하기 위해 정기적으로 학습해야 합니다. 이 예에서는 **월별** 을 선택합니다.

1. 모든 세부 정보를 검토한 후 **저장 및 실행** 을 선택합니다.

## <a name="task-4---review-model-results-and-explanations"></a>작업 4 - 모델 결과 및 설명 검토

모델이 데이터의 학습 및 채점을 완료하도록 합니다. 이제 구독 이탈 모델 설명을 검토할 수 있습니다. 자세한 내용은 [예측 상태 및 결과를 검토](predict-subscription-churn.md#review-a-prediction-status-and-results)를 참조하세요.

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>작업 5 - 이탈 위험이 높은 고객 세그먼트 생성

프로덕션 모델을 실행하면 **데이터** > **엔티티** 에서 볼 수 있는 새 엔티티가 생성됩니다.   

모델에서 생성한 엔터티를 기반으로 새 세그먼트를 생성할 수 있습니다.

1.  **세그먼트** 로 이동 **새로 만들기** 를 **만들기** > **인텔리전스** 를 선택합니다. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="모델 출력으로 세그먼트 생성.":::

1. **OOBSubscriptionChurnPrediction** 엔드포인트를 선택하고 세그먼트를 정의합니다. 
   - 필드: ChurnScore
   - 연산자: 보다 큼
   - 값: 0.6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="구독 이탈 세그먼트를 설정합니다.":::

이제 이 구독 비즈니스에 대해 이탈 위험이 높은 고객을 식별하는 동적으로 업데이트되는 세그먼트가 있습니다.

자세한 내용은 [세그먼트 만들기 및 관리](segments.md)를 참조하세요.


[!INCLUDE[footer-include](../includes/footer-banner.md)]