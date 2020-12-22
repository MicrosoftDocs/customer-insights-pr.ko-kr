---
title: Machine Learning Studio(클래식) 실험
description: Dynamics 365 Customer Insights의 Machine Learning Studio(클래식) 모델을 사용합니다.
ms.date: 12/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: ameetj
manager: shellyha
ms.openlocfilehash: 556b6810db0ed2733a3f086291757bd85b77e371
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4669026"
---
# <a name="use-models-based-on-azure-machine-learning-studio-classic"></a>Azure Machine Learning Studio(클래식) 기반 모델을 사용합니다.

Dynamics 365 Customer Insights의 통합 데이터는 추가 비즈니스 인사이트를 생성할 수 있는 기계 학습 모델을 구축하기 위한 소스입니다. Customer Insights는 Machine Learning Studio(클래식)와 통합되어 고유한 사용자 지정 모델을 사용합니다. Azure Machine Learning에서 개발된 모델이 Customer Insights와 통합되는 방법을 보려면 [Azure Machine Learning 실험](azure-machine-learning-experiments.md)을 참조하세요.

## <a name="prerequisites"></a>필수 구성 요소

- Customer Insights에 액세스
- 활성 Azure Enterprise 구독
- [통합 고객 프로필](data-unification.md)
- [Azure Blob Storage로 엔터티 내보내기](export-azure-blob-storage.md) 설정

## <a name="set-up-machine-learning-studio-classic"></a>Machine Learning Studio 클래식 설정

첫 번째 단계에서 작업 영역을 만들고 Machine Learning Studio(클래식)를 열어야 합니다.

1. [https://www.portal.azure.com](https://www.portal.azure.com/)로 이동하고 로그인합니다.

1. **리소스 만들기** 를 선택합니다.

1. **Machine Learning Studio 작업 영역** 을 검색해 **만들기** 를 선택합니다.

1. 필요한 세부 정보를 입력하여 [작업 공간을 만듭니다](https://docs.microsoft.com/azure/machine-learning/studio/create-workspace). 가져올 데이터 양에 따라 **웹 서비스 계획 가격 책정 계층** 을 선택합니다. 최상의 성능을 위해 지리적으로 가장 가까운 **위치** 를 선택합니다.

1. 리소스를 생성하면 Machine Learning Studio 작업 영역 대시보드가 나타납니다. **Machine Learning Studio 실행** 을 선택합니다.

   ![Azure Machine Learning Studio 사용자 인터페이스](media/azure-machine-learning-studio.png)

## <a name="work-with-azure-machine-learning-studio"></a>Azure Machine Learning Studio 작업

이제 새 실험을 만들거나 샘플 갤러리에서 기존 실험 템플릿을 가져올 수 있습니다. 세 가지 표준 시나리오에 대한 샘플 실험이 있습니다.

- [이탈 예측](#churn-analysis)

- [고객 수명 값](#customer-lifetime-value-prediction)

- [제품 추천 또는 차선책](#productrecommendation-or-next-best-action)

1. 새 실험을 만들거나 갤러리의 실험 템플릿을 사용하는 경우 **데이터 가져오기** 속성을 구성해야 합니다. 안내식 환경을 사용하거나 데이터가 포함된 Azure Blob Storage에 액세스하기 위한 세부 정보를 직접 제공하세요.  

   ![Azure Machine Learning Studio 실험](media/azure-machine-learning-studio-experiment.png)

1. 이제 사용자 지정 처리 파이프라인을 구축하여 데이터를 정리 및 전처리하고, 기능을 추출하고, 적합한 모델을 학습시킬 수 있습니다.

1. 모델 성능을 테스트하고 최적화합니다.

1. 모델의 품질이 만족스러우면 **웹 서비스 설정** > **예측 웹 서비스** 를 선택합니다. 이 옵션은 학습 실험에서 예측 서비스로 학습된 모델과 기능화 파이프라인을 가져옵니다. 예측 서비스는 학습 실험에 사용된 스키마를 사용하여 다른 입력 데이터 집합을 가져와 예측을 수행할 수 있습니다.

   ![예측 웹 서비스 설정](media/predictive-webservice-control.png)

1. 예측 웹 서비스 실험이 성공하면 자동 예약을 위해 배포할 수 있습니다. 웹 서비스가 Customer Insights와 함께 작동하게 하려면 **웹 서비스 배포** > **웹 서비스 배포 [신규] 미리 보기** 를 선택합니다. [웹 서비스 배포에 대해 자세히 알아보세요](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service).

   ![예측 웹 서비스 배포](media/predictive-webservice-deploy.png)

## <a name="sample-models-from-the-gallery"></a>갤러리의 샘플 모델

이 문서에서는 모델에 Contoso Hotel의 가상 시나리오를 사용합니다. Contoso Hotel은 다음 데이터를 수집합니다.

- 호텔 숙박 활동으로 구성된 CRM 데이터. 데이터 집합에는 등록된 각 고객의 숙박 날짜에 대한 정보가 포함되어 있습니다. 또한 예약, 객실 유형, 지출 세부 정보 등에 대한 정보도 포함됩니다. 데이터는 2014년 1월부터 2018년 1월까지 4년에 걸쳐 있습니다.
- 호텔 투숙객의 고객 프로필. 이러한 프로필에는 이름, 생년월일, 우편 주소, 성별, 전화 번호 등 각 고객에 대한 정보가 포함됩니다.
- 스파, 세탁, Wi-Fi, 택배 등 호텔에서 제공하는 서비스 이용. 이 정보는 등록된 각 고객에 대해 기록됩니다. 일반적으로 서비스 사용은 숙박과 관련이 있습니다. 경우에 따라 호텔에 숙박하지 않고 고객이 서비스를 이용할 수 있습니다.

## <a name="churn-analysis"></a>이탈 분석

이탈 분석은 다양한 비즈니스 영역에 적용됩니다. 이 예에서는 위에서 설명한 바와 같이 특히 호텔 서비스의 맥락에서 서비스 이탈을 살펴보겠습니다. 다른 유형의 이탈 모델에 대한 시작점으로 사용할 수 있는 종합적인 모델 파이프라인의 작동 예제를 제공합니다.

### <a name="definition-of-churn"></a>이탈의 정의

이탈의 정의는 시나리오에 따라 다를 수 있습니다. 이 예에서 작년에 호텔을 방문하지 않은 게스트는 이탈로 표시되어야 합니다.  

갤러리에서 실험 템플릿을 가져올 수 있습니다. 먼저 Azure Blob Storage에서 **호텔 숙박 활동**, **고객 데이터**, **서비스 사용 데이터** 에 대한 데이터를 가져와야 합니다.

   ![이탈 모델에 대한 데이터 가져오기](media/import-data-azure-blob-storage.png)

### <a name="featurization"></a>기능화

이탈의 정의에 따라 먼저 레이블에 영향을 미칠 원시 기능을 식별합니다. 그런 다음 이러한 원시 기능을 기계 학습 모델과 함께 사용할 수 있는 수치 기능으로 처리합니다. Customer Insights에서 데이터 통합이 이루어 지므로 *고객 ID* 를 사용하여 이러한 테이블을 포함될 수 있습니다.

   ![가져온 데이터 결합](media/join-imported-data.png)

이탈 분석을 위한 모델 구축을 위한 기능화는 약간 까다로울 수 있습니다. 데이터는 매일 새로운 호텔 활동이 기록되는 시간의 함수입니다. 기능화 중에 동적 데이터에서 정적 기능을 생성하려고 합니다. 이 경우 슬라이딩 윈도우가 1년인 호텔 활동에서 여러 기능을 생성합니다. 또한 원-핫 인코딩을 사용하여 객실 유형 또는 예약 유형과 같은 범주별 기능을 별도의 기능으로 확장합니다.  

최종 기능 목록:

| **숫자**  | **Original_Column**          | **파생 기능**                                                                                                                      |
|-------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 1           | 객실 종류                    | RoomTypeLargeCount, RoomTypeSmallCount                                                                                                    |
| 2           | 예약 유형                 | BookingTypeOnlineCount, BookingTypePhoneCallCount                                                                                         |
| 3           | 이동 범주              | TravelCategoryBusinessCount, TravelCategoryLeisureCount                                                                                   |
| 4           | 지출된 달러 비용                | TotalDollarSpent                                                                                                                          |
| 5           | 체크인 및 체크아웃 날짜  | StayDayCount, StayDayCount2016, StayDayCount2015, StayDayCount2014, StayCount, StayCount2016. StayCount2015, StayCount2014                |
| 6           | 서비스 사용                | UsageTenure, ConciergeUsage, CourierUsage, DryCleaningUsage, GymUsage, PhoneUsage, RestaurantUsage, SpaUsage, TelevisionUsage, WifiUsage  |

### <a name="model-selection"></a>모델 선택

이제 사용할 최적의 알고리즘을 선택해야 합니다. 이 경우 대부분의 기능은 범주 기능을 기반으로 합니다. 일반적으로 의사 결정 트리 기반 모델이 잘 작동합니다. 숫자 기능만 있는 경우 신경망이 더 나은 선택이 될 수 있습니다. SVM(Support Vector Machine)도 이러한 상황에서 좋은 후보입니다. 그러나 최상의 성능을 얻기 위해서는 약간의 조정이 필요합니다. 첫 번째 모델로 **2클래스 향상된 의사 결정 트리** 를 선택하고 두 번째 모델로 **2클래스 SVM** 을 선택합니다. Azure Machine Learning Studio를 사용하면 A/B 테스트를 수행할 수 있으므로 하나가 아닌 두 가지 모델로 시작하는 것이 좋습니다.

다음 이미지는 Azure Machine Learning Studio의 모델 학습 및 평가 파이프라인을 보여줍니다.

![Azure Machine Learning Studio의 이탈 모델](media/azure-machine-learning-model.png)

또한 모델 최적화의 중요한 측면인 **순열 기능 중요성** 이라는 기술도 적용합니다. 내장 모델은 특정 기능이 최종 예측에 미치는 영향에 대한 통찰력이 거의 또는 전혀 없습니다. 기능 중요도 계산기는 사용자 지정 알고리즘을 사용하여 특정 모델의 결과에 대한 개별 기능의 영향을 계산합니다. 기능 중요도는 +1에서 -1 사이로 정규화됩니다. 부정적인 영향은 해당 기능이 결과에 반 직관적인 영향을 미치므로 모델에서 제거해야 함을 의미합니다. 긍정적인 영향은 기능이 예측에 크게 기여하고 있음을 나타냅니다. 이러한 값은 서로 다른 메트릭이므로 상관 계수가 아닙니다. 자세한 내용은 [순열 기능 중요성](https://docs.microsoft.com/azure/machine-learning/studio-module-reference/permutation-feature-importance)을 참조하세요.

전체 [이탈 실험은 Azure AI Gallery에서 사용할 수 있습니다](https://gallery.azure.ai/Experiment/Hotel-Churn-Predictive-Exp).

## <a name="customer-lifetime-value-prediction"></a>고객 평생 가치 예측

CLTV(고객 평생 가치) 계산은 기업이 고객을 평가하고 분류하는 데 사용할 수 있는 주요 지표 중 하나입니다. 호텔 비즈니스의 경우 고객을 아는 것이 중요합니다. 예를 들어 좋은 고객을 구성하는 요소를 이해하는 것은 중요한 정보입니다. 이는 호텔 경영진이 고액 고객을 만족시키기 위해 집중하고 개선해야 하는 기능을 평가하는 데 도움이 됩니다. 이러한 결정은 판매 및 수입에 직접적인 영향을 미칠 수 있습니다.  

### <a name="definition-of-cltv"></a>CLTV의 정의

이 예에서는 고객의 CLTV를 고객이 향후 365일 동안 지출할 것으로 예상되는 총 금액으로 정의합니다. 우리는 이 가치를 예측하기 위해 모든 고객의 지난 3년간의 데이터를 사용할 것입니다.

### <a name="featurization"></a>기능화

이 경우 기능화는 이탈 시나리오와 매우 유사합니다. 그러나 레이블과 예측 값은 위에 정의된 것과 다릅니다.

### <a name="model-selection"></a>모델 선택

CLTV를 예측하는 것은 예측 값이 양의 값을 갖는 연속 변수이기 때문에 회귀 문제입니다. 기능 속성에 따라 **향상된 의사 결정 트리 회귀** 를 하나의 알고리즘으로 **신경망** 회귀를 모델 훈련을 위한 또 다른 알고리즘으로 선택합니다.

## <a name="product-recommendation-or-next-best-action"></a>제품 추천 또는 차선책

호텔 시나리오에서 제품 추천은 호텔이 고객에게 제공하는 서비스를 추천하는 것으로 해석됩니다. 목표는 고객의 사용이 극대화되도록 고객에게 적합한 서비스를 선택하는 것입니다. 비디오 스트리밍 서비스 사용자를 위한 영화 추천과 유사합니다.

### <a name="definition-of-product-recommendation-or-next-best-action"></a>제품 추천 또는 차선책의 정의

호텔 고객의 관심사에 따라 최상의 매칭 서비스를 제공하여 서비스 이용 금액을 극대화하는 것을 목표로 정의합니다.

### <a name="featurization"></a>기능화

이탈 모델과 마찬가지로, 우리는 CustomerID별로 일관되게 추천을 구축하기 위해 호텔 ServiceCustomerID와 CustomerID를 결합하고 있습니다.

![추천 모델의 기능화](media/azure-machine-learning-model-featurization.png)

데이터는 세 가지 다른 엔터티에서 제공되며 기능은 이들에서 파생됩니다. 추천의 기능화는 이탈 또는 CLTV 시나리오와 다릅니다. 추천 모델에는 세 가지 기능 집합 형식의 입력 데이터가 필요합니다.

### <a name="model-selection"></a>모델 선택

우리는 **매치박스 추천 학습** 이라는 알고리즘을 사용하여 추천 모델을 교육하여 제품 또는 서비스를 예측합니다.

![제품 추천 알고리즘](media/azure-machine-learning-model-recommendation-algorithm.png)

세 개의 **매치박스 추천 학습** 모델에 대한 입력 포트는 교육 서비스 사용 데이터, 고객 설명(선택 사항) 및 서비스 설명을 취합니다. 모델을 평가하는 방법에는 세 가지가 있습니다. 하나는 NDCG(Normalized Discounted Cumulative Gain) 점수를 계산하여 등급 항목의 순위를 매기는 모델 평가용입니다. 이 실험에서 NDCG 점수는 0.97입니다. 다른 두 가지 옵션은 전체 권장 서비스 카탈로그에서 모델을 평가하거나 사용자가 이전에 사용하지 않은 항목에 대해서만 평가하는 것입니다.

전체 서비스 카탈로그의 권장 사항 배포를 자세히 살펴보면 전화, Wi-Fi 및 택배가 가장 권장되는 서비스임을 알 수 있습니다. 이것은 서비스 소비 데이터의 분포에서 찾은 것과 일치합니다.

![추천 모델 출력](media/azure-machine-learning-model-output.png)

전체 [제품 추천 실험은 Azure AI Gallery에서 액세스할 수 있습니다.](https://gallery.azure.ai/Experiment/Recommendation-4)

## <a name="integrate-custom-models"></a>사용자 지정 모델 통합

Customer Insights에서 이러한 예측을 사용하려면 고객 ID와 함께 예측을 **내보내야** 합니다. 원본 데이터를 내보내는 [동일한 Azure Blob 저장소 위치로 내보냅니다](https://docs.microsoft.com/azure/storage/common/storage-import-export-data-from-blobs). 예측 웹 서비스를 정기적으로 실행하고 점수가 업데이트되도록 예약할 수 있습니다.

사용자 지정 모델에서 생성된 데이터를 사용하여 고객 데이터를 더욱 보강할 수 있습니다. 자세한 내용은 [사용자 지정 기계 학습 모델](custom-models.md)을 참조하세요.
