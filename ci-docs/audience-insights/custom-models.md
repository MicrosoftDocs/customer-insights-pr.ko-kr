---
title: 사용자 지정 기계 학습 모델 | Microsoft Docs
description: Dynamics 365 Customer Insights Azure Machine Learning의 사용자 지정 모델로 작업합니다.
ms.date: 12/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 8ca30193ae4f4ef3ed9c60f2d694cd11fad46c76
ms.sourcegitcommit: 15b1521041149716f8031cfa6d0dc61a56a5e2ff
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2022
ms.locfileid: "7967663"
---
# <a name="custom-machine-learning-models"></a>사용자 지정 기계 학습 모델

> [!NOTE]
> Machine Learning Studio(클래식)에 대한 지원이 2024년 8월 31일에 종료됩니다. 그 날짜까지 [Azure Machine Learning](/azure/machine-learning/overview-what-is-azure-machine-learning)으로 전환하는 것이 좋습니다.
>
> 2021년 12월 1일부터 새로운 Machine Learning Studio(클래식) 리소스를 생성할 수 없습니다. 2024년 8월 31일까지 기존 Machine Learning Studio(클래식) 리소스를 계속 사용할 수 있습니다. 자세한 내용은 [Azure Machine Learning로 마이그레이션](/azure/machine-learning/migrate-overview)을 참고하세요.


**인텔리전스** > **사용자 지정 모델** 을 사용하면 Azure Machine Learning 모델을 기반으로 워크플로를 관리할 수 있습니다. 워크플로는 인사이트를 생성할 데이터를 선택하고 결과를 통합 고객 데이터에 매핑하는 데 도움이 됩니다. 사용자 지정 ML 모델 빌드에 대한 자세한 내용은 [Azure Machine Learning 기반 모델 사용](azure-machine-learning-experiments.md)을 참조하세요.

## <a name="responsible-ai"></a>책임감 있는 AI

예측은 더 나은 고객 경험을 창출하고 비즈니스 기능을 개선하며 수익원을 창출하는 기능을 제공합니다. 윤리적 방식으로 도입할 수 있는 편견 및 영향과 예측의 가치 간의 균형을 맞추는 것이 좋습니다. Microsoft가 [책임감 있는 AI를 해결](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6)하는 방법에 대해 자세히 알아보세요. Azure Machine Learning과 관련된 [책임 있는 기계 학습을 위한 기술 및 프로세스](/azure/machine-learning/concept-responsible-ml)에 대해서도 알아볼 수 있습니다.

## <a name="prerequisites"></a>필수 항목

- 이 기능은 [Azure Machine Learning 일괄 파이프라인](/azure/machine-learning/concept-ml-pipelines)을 통해 게시된 웹 서비스를 지원합니다.

- 이 기능을 사용하려면 Azure Studio 인스턴스와 연결된 Azure Data Lake Gen2 스토리지 계정이 필요합니다. 자세한 내용은 [Azure Data Lake Storage Gen2 스토리지 계정 만들기](/azure/storage/blobs/data-lake-storage-quickstart-create-account)를 참조하십시오.

- 파이프라인이 있는 Azure Machine Learning 작업 영역의 경우 Azure Machine Learning 작업 영역에 대한 담당자 또는 사용자 액세스 관리자 권한이 필요합니다.

   > [!NOTE]
   > Customer Insights 인스턴스와 워크플로에서 선택한 Azure 웹 서비스 또는 파이프라인 간에 데이터가 전송됩니다. Azure 서비스로 데이터를 전송하는 경우 조직의 해당 데이터에 대한 법적 요구 사항 또는 규제 사항을 준수하는 데 필요한 방식과 위치에서 데이터를 처리하도록 서비스가 구성되어 있는지 확인하시기 바랍니다.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

## <a name="add-a-new-workflow"></a>새 워크플로 추가

1. **인텔리전스** > **사용자 지정 모델** 로 이동하고 **새로운 워크플로** 를 선택합니다.

1. **이름** 필드에서 사용자 지정 모델에 인식할 수 있는 이름을 지정합니다.

   > [!div class="mx-imgBorder"]
   > ![새 워크플로 창의 스크린샷.](media/new-workflowv2.png "새 워크플로우 창의 스크린샷")

1. **웹 서비스가 포함된 테넌트** 에서 웹 서비스가 포함된 조직을 선택합니다.

1. Azure 기계 학습 구독이 Customer Insights와 다른 테넌트에 있는 경우 선택한 조직의 자격 증명과 함께 **로그인** 을 선택합니다.

1. 웹 서비스와 연결된 **작업 영역** 을 선택합니다. 

1. **모델이 포함된 웹 서비스** 드롭다운에서 Azure Machine Learning 파이프라인을 선택합니다. 그런 후에 **다음** 을 선택합니다.    
   [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) 또는 [디자이너를 사용하여 Azure Machine Learning에서 파이프라인을 게시](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer)하는 방법에 대해 자세히 알아보세요. 파이프라인은 [파이프라인 엔드포인트](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run) 아래에 게시되어야 합니다.

1. 각 **웹 서비스 입력** 에 대상 그룹 인사이트의 일치하는 **엔터티** 를 선택하고 **다음** 을 선택합니다.
   > [!NOTE]
   > 사용자 지정 모델 워크플로는 휴리스틱을 적용하여 필드의 이름 및 데이터 형식을 기반으로 웹 서비스 입력 필드를 엔터티 속성에 매핑합니다. 웹 서비스 필드를 엔터티에 매핑할 수 없는 경우 오류가 표시됩니다.

   > [!div class="mx-imgBorder"]
   > ![워크플로 구성.](media/intelligence-screen2-updated.png "워크플로 구성")

1. **모델 출력 매개 변수** 단계에서 다음 속성을 설정합니다.
      1. 파이프라인 출력 결과가 유입될 출력 **엔터티 이름** 을 입력합니다.
      1. 드롭다운에서 배치 파이프라인의 **출력 데이터 저장소 매개 변수 이름** 을 선택합니다.
      1. 드롭다운에서 배치 파이프라인의 **출력 경로 매개 변수 이름** 을 선택합니다.

      > [!div class="mx-imgBorder"]
      > ![모델 출력 매개 변수 창.](media/intelligence-screen3-outputparameters.png "모델 출력 매개 변수 창")

1. 고객을 식별하는 **결과의 고객 ID** 드롭다운 목록에서 일치하는 특성을 선택하고 **저장** 을 선택합니다.

   > [!div class="mx-imgBorder"]
   > ![결과를 고객 데이터 창에 연결.](media/intelligence-screen4-relatetocustomer.png "결과를 고객 데이터 창에 연결")

1. 워크플로에 대한 세부 정보가 있는 **워크플로 저장** 화면이 표시됩니다.    
   Azure Machine Learning 파이프라인에 대한 워크플로를 구성한 경우 대상 그룹 인사이트가 파이프라인이 포함된 작업 영역에 연결됩니다. 대상 그룹 인사이트는 Azure 작업 영역에서 **기여자** 역할을 받습니다.

1. **완료** 를 선택합니다.

1. 이제 **사용자 지정 모델** 페이지에서 워크플로를 실행할 수 있습니다.

## <a name="edit-a-workflow"></a>워크플로 편집

1. **사용자 지정 모델** 페이지에서 이전에 만든 워크플로 옆의 **작업** 열에서 세로 줄임표를 선택하고 **편집** 을 선택합니다.

1. **표시 이름** 필드에서 워크플로의 인식 가능한 이름을 업데이트할 수 있지만 구성된 웹 서비스 또는 파이프라인은 변경할 수 없습니다. **다음** 을 선택합니다.

1. 각 **웹 서비스 입력** 에 대해 대상 그룹 인사이트에서 일치하는 **엔터티** 를 업데이트할 수 있습니다. 그런 후에 **다음** 을 선택합니다.

1. **모델 출력 매개 변수** 단계에서 다음 속성을 설정합니다.
      1. 파이프라인 출력 결과가 유입될 출력 **엔터티 이름** 을 입력합니다.
      1. 테스트 파이프라인의 **출력 데이터 저장소 매개 변수 이름** 을 선택합니다.
      1. 테스트 파이프라인의 **출력 경로 매개 변수 이름** 을 선택합니다.

1. 고객을 식별하는 **결과의 고객 ID** 드롭다운 목록에서 일치하는 특성을 선택하고 **저장** 을 선택합니다.
   고객 엔터티의 고객 ID 열과 유사한 값이 있는 추론 출력에서 특성을 선택합니다. 데이터 집합에 이러한 열이 없으면 행을 고유하게 식별하는 특성을 선택합니다.

## <a name="run-a-workflow"></a>워크플로 실행

1. **사용자 지정 모델** 페이지에서 이전에 만든 워크플로 옆의 **작업** 열에서 세로 줄임표를 선택합니다.

1. **실행** 을 선택합니다.

워크플로는 예약된 새로 고침마다 자동으로 실행됩니다. [예약된 새로 고침 설정](system.md#schedule-tab)에 대해 자세히 알아보세요.

## <a name="delete-a-workflow"></a>워크플로 삭제

1. **사용자 지정 모델** 페이지에서 이전에 만든 워크플로 옆의 **작업** 열에서 세로 줄임표를 선택합니다.

1. **삭제** 를 선택하고 삭제를 확인합니다.

워크플로가 삭제됩니다. 워크플로를 만들 때 생성된 [엔터티](entities.md)이며 **엔터티** 페이지에서 확인할 수 있습니다.

## <a name="results"></a>결과

워크플로의 결과는 모델 출력 매개 변수 단계에서 구성된 엔티티에 저장됩니다. 이 데이터는 [엔티티 페이지](entities.md) 또는 [API 액세스](apis.md)에서 액세스할 수 있습니다.

### <a name="api-access"></a>API 액세스

사용자 지정 모델 엔터티에서 데이터를 가져 오는 특정 OData 쿼리의 경우 다음 형식을 사용합니다.

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. `<your instance id>`(을)를 Customer Insights에 액세스할 때 브라우저의 주소 표시줄에서 찾을 수 있는 Customer Insights 환경의 ID로 교체합니다.

1. `<custom model output entity>`(을)를 사용자 지정 모델 구성의 모델 출력 매개 변수 단계에서 제공한 엔터티 이름으로 교체합니다.

1. `<guid value>`(을)를 레코드에 액세스하려는 고객의 고객 ID로 교체합니다. 일반적으로 이 ID는 CustomerID 필드의 [고객 프로필 페이지](customer-profiles.md)에서 찾을 수 있습니다.

## <a name="frequently-asked-questions"></a>질문과 대답

- 사용자 지정 모델 워크플로를 설정할 때 파이프라인을 볼 수 없는 이유는 무엇입니까?    
  이 문제는 파이프라인의 구성 문제로 인해 자주 발생합니다. [입력 매개 변수가 구성](azure-machine-learning-experiments.md#dataset-configuration)되고 [출력 데이터 저장소 및 경로 매개 변수](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) 또한 구성되도록 확인하십시오.

- "인텔리전스 워크플로를 저장할 수 없음"라는 오류는 무엇을 의미합니까?    
  작업 영역에 대한 담당자 또는 사용자 액세스 관리자 권한이 없는 경우 일반적으로 이 오류 메시지가 표시됩니다. 사용자는 후속 워크플로 실행에 사용자 자격 증명을 사용하는 대신 Customer Insights에서 워크 플로를 서비스로 처리할 수 있도록 더 높은 수준의 권한이 필요합니다.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
