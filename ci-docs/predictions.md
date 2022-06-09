---
title: 예측을 사용하여 부분 데이터 완료
description: 예측을 사용하여 불완전한 고객 데이터를 채웁니다.
ms.date: 11/01/2021
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-predictions
- ci-custom-models
- customerInsights
ms.openlocfilehash: 57ef46416db0a11cde9f9d7650a0b502a01bf0ab
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800658"
---
# <a name="complete-your-partial-data-with-predictions-deprecated"></a>예측으로 부분 데이터 완성(더 이상 사용되지 않음)

> [!IMPORTANT]
> 이 기능은 **2021년 11월 5일** 부터 **더 이상 사용되지 않습니다**. 현재 구현은 기능이 제거될 때까지 계속 작동하지만 아래 지침을 사용하여 새 통합을 만들 수 없습니다.

예측을 통해 고객에 대한 이해를 높일 수 있는 예측 값을 쉽게 만들 수 있습니다. **인텔리전스** > **예측** 페이지에서 **내 예측** 을 선택해 Customer Insights의 다른 부분에서 구성한 예측을 보고 추가로 사용자 지정할 수 있습니다.

> [!NOTE]
> 환경에서 Azure Data Lake Gen 2 저장소를 사용하는 경우 이 기능을 사용할 수 없습니다.
>
> 예측 기능은 자동화된 수단을 사용하여 데이터를 평가하고 해당 데이터를 기반으로 예측을 수행하므로 일반 데이터 보호 규정("GDPR")에 의해 정의된 대로 프로파일링 방법으로 사용될 수 있습니다. 고객이 데이터를 처리하기 위해 이 기능을 사용하는 경우 GDPR 또는 기타 법률 또는 규정이 적용될 수 있습니다. 귀하는 예측을 포함한 Dynamics 365 Customer Insights 사용이 개인 정보 보호, 개인 데이터, 생체 인식 데이터, 데이터 보호 및 통신 기밀과 관련된 법률을 포함하여 모든 관련 법률 및 규정을 준수하는지 확인할 책임이 있습니다.

## <a name="prerequisites"></a>필수 구성 요소

조직에서 예측 기능을 사용하기 전에 다음 전제 조건이 충족되어야 합니다.

1. 조직에 [Microsoft Dataverse에서 설정](/ai-builder/build-model#prerequisites) 인스턴스가 있고 이는 Customer Insights와 동일한 조직에 있습니다.

2. Customer Insights 환경이 Dataverse 인스턴스에 첨부됩니다.

자세한 내용은 [새 환경 만들기](create-environment.md)를 참조하세요.

## <a name="create-a-prediction-in-the-customer-entity"></a>고객 엔터티에서 예측 만들기

1. **데이터** > **엔터티** 로 이동합니다.

2. **고객** 엔터티를 선택합니다.

3. **고객: CustomerInsights** 엔터티에서 **필드** 탭을 선택합니다.

4. 값을 예측하려는 특성 이름을 찾은 다음 **요약** 열에서 **개요** 아이콘을 선택합니다.
   > [!div class="mx-imgBorder"]
   > ![개요 아이콘.](media/intelligence-overviewicon.png "개요 아이콘")

5. 특성에 대해 누락된 값의 비율이 높은 경우 **누락된 값 예측** 을 선택하여 예측을 계속합니다.
   > [!div class="mx-imgBorder"]
   > ![누락된 값 예측 단추가 표시된 개요 상태.](media/intelligence-overviewpredictmissingvalues.png "누락된 값 예측 단추가 표시된 개요 상태")

6. 예측 결과를 위해 **표시 이름** 과 **출력 엔터티 이름** 을 제공합니다.

7. 미리 채워진 옵션 목록에 값을 예측된 범주에 매핑할 수 있는 위치가 표시됩니다. 이 경우 예측의 참/거짓 또는 이진 특성에 매핑되므로 범주 옵션만 0 또는 1이 됩니다. 범주 열에서 최종 예측에서 "0"으로 분류할 필드 값을 "0"으로 매핑하고 최종 예측에서 "1"로 분류할 항목을 "1"로 매핑합니다.
   > [!div class="mx-imgBorder"]
   > ![범주에 매핑된 필드 값을 보여주는 예.](media/intelligence-categorymapping.png "범주에 매핑된 필드 값을 보여주는 예")

8. **완료** 를 선택하면 예측이 처리됩니다. 데이터의 크기와 복잡성에 따라 처리에 시간이 걸립니다. 생성한 예측의 **출력 엔터티 이름** 을 기반으로 새 엔터티에서 결과를 사용할 수 있습니다.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="create-a-prediction-while-creating-a-segment"></a>세그먼트를 만들면서 예측 만들기

세그먼트를 만들 때 선택한 특정 특성에 대한 누락된 값을 예측할 수도 있습니다. 특히, 통합 고객 엔터티 또는 Customer_Measure 엔터티를 기반으로 세그먼트를 빠르게 만들 때가 그렇습니다.

이 흐름의 일부로 고객 만족도 또는 구매 금액 등 세그먼트를 기반으로 특정 특성을 선택합니다. 세그먼트 생성 시 시스템은 이 특성에 대한 놓친 값을 예측하는 방법을 제안합니다.

1. **세그먼트** 로 이동하여 **프로필** 타일을 선택합니다.

2. **필드** 를 선택하여 세그먼트를 만들고 **운영자** 를 선택한 다음 **검토** 를 선택합니다.

3. 세그먼트에 대한 **이름** 및 **표시 이름** 을 제공합니다.

4. **저장** 을 선택합니다.

5. 만든 세그먼트에 소스 필드에 불완전한 데이터가 있는 경우 누락된 값을 예측하도록 선택할 수 있습니다.
   > [!div class="mx-imgBorder"]
   > ![예측 단추.](media/segments-predictoption.png "예측 단추")

6. 예측 결과를 위해 **표시 이름** 과 **출력 엔터티 이름** 을 제공합니다.

7. **완료** 를 선택합니다. 곧 **출력 엔터티 이름** 에 제공한 새로운 엔터티에서 예측이 생성됩니다.

## <a name="view-a-prediction"></a>예측 보기

1. **인텔리전스** > **예측** > **내 예측** 으로 이동합니다.

2. 검토하려는 예측을 선택합니다.

3. **작업** 열에서 세로 줄임표(&vellip;)를 선택하고 **보기** 를 선택합니다.

4. 예측 보기에 여러 데이터 요소가 표시됩니다.
   > [!div class="mx-imgBorder"]
   > ![예측 페이지.](media/intelligence-predictionsviewpage.png "예측 페이지")

   - **예측 가치** 는 필드 값 대 범주 매핑 단계에서 작성한 매핑을 보여줍니다. 이들은 특정 범주에 매핑된 데이터 집합의 값입니다.
   -**상위 인플루언서** 는 데이터 집합 내에서 특정 범주에 매핑되는 필드 값에 대한 예측의 신뢰도에 영향을 줄 수 있는 요인입니다.
   - **성능** 은 예측이 수행되는 방식을 나타냅니다. 자세한 내용을 보려면 링크를 선택하십시오.
   - **미리 보기** 는 0은 불확실하고 1은 확실한 예측 가치의 가능성 또는 신뢰도에서 나온 출력 데이터 집합의 샘플을 보여줍니다.

## <a name="update-a-prediction"></a>예측 업데이트

1. **인텔리전스** > **예측** > **내 예측** 으로 이동합니다.

2. 업데이트할 예측을 선택하고 **업데이트** 아이콘을 선택합니다.

3. 예측이 처리 예정입니다. **예측**  페이지의 **업데이트됨** 열에서 마지막으로 업데이트된 시간을 확인할 수 있습니다.

## <a name="edit-a-prediction"></a>예측 편집

예측을 생성한 후 AI Builder에서 모델을 사용자 지정하여 모델의 효율성을 높일 수 있습니다.  

1. **인텔리전스** > **예측** > **내 예측** 으로 이동합니다.

2. 편집할 예측을 선택합니다.

3. **작업** 열에서 세로 줄임표(&vellip;)를 선택하고 **보기** 를 선택합니다.

4. **AI Builder에서 사용자화** 를 선택합니다.

5. AI Builder에서 모델을 업데이트합니다. [AI Builder에서 모델 관리에 대해 자세히 알아보십시오](/ai-builder/manage-model#retrain-and-republish-existing-models).

다음 예측에서는 생성한 업데이트된 모델을 사용합니다.

> [!NOTE]
> AI Builder에서 생성된 새 모델은 위에 나열된 경험에서 생성된 모델이 아니면 Customer Insights에 표시되지 않습니다.

## <a name="remove-a-prediction"></a>예측 제거

1. **인텔리전스** > **예측** > **내 예측** 으로 이동합니다.

2. 삭제하려는 예측을 선택합니다.

3. **작업** 열에서 세로 줄임표(&vellip;)를 선택하고 **삭제** 를 선택합니다.

4. 삭제를 확인합니다.

## <a name="troubleshooting"></a>문제 해결

오류로 인해 Dataverse 첨부 프로세스를 완료할 수 없는 경우 프로세스를 수동으로 완료할 수 있습니다. 연결 프로세스에서 발생할 수 있는 두 가지 알려진 문제가 있습니다.

- 고객 카드 추가 기능 솔루션이 설치되지 않았습니다.
    1. [솔루션 설치 및 구성](customer-card-add-in.md)에 대한 지침을 완료하십시오.

- 앱 권한이 부여되지 않습니다.
    1. [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com)으로 이동합니다.
    1. **환경** 을 선택합니다.
    1. 권한을 추가하려는 환경 옆의 세로 줄임표(&vellip;)를 선택하고 **설정** 을 선택합니다.
    1. **사용자 + 권한** 을 확장하고 **사용자** 를 선택합니다.
    1. **+ 새로 만들기** 를 선택하고 **사용자** 를 선택합니다.
    1. 아직 선택하지 않은 경우 **응용 프로그램 사용자** 를 선택하고 다음 정보를 입력합니다.
        - **사용자 이름:** cihelp@microsoft.com
        - **응용 프로그램 ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c
        - **고객 이름:** 고객
        - **성:** 인사이트
        - **기본 이메일:** cihelp@microsoft.com
    1. **저장 후 닫기** 를 선택합니다.
    1. 방금 만든 사용자를 선택합니다.
    1. 상단 메뉴 모음에서 **역할 관리** 를 선택합니다.
    1. **시스템 관리자** 를 선택한 다음 **확인** 을 선택합니다.


[!INCLUDE [footer-include](includes/footer-banner.md)]