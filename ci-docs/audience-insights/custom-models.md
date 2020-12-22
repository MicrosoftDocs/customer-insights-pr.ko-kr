---
title: 사용자 지정 기계 학습 모델 | Microsoft Docs
description: Dynamics 365 Customer Insights Azure Machine Learning의 사용자 지정 모델로 작업합니다.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668911"
---
# <a name="custom-machine-learning-models"></a>사용자 지정 기계 학습 모델

**인텔리전스** > **사용자 지정 모델** 을 사용하면 Azure Machine Learning 모델을 기반으로 워크플로를 관리할 수 있습니다. 워크플로는 인사이트를 생성할 데이터를 선택하고 결과를 통합 고객 데이터에 매핑하는 데 도움이 됩니다. 사용자 지정 ML 모델 빌드에 대한 자세한 내용은 [Azure Machine Learning 기반 모델 사용](azure-machine-learning-experiments.md)을 참조하세요.

## <a name="responsible-ai"></a>책임감 있는 AI

예측은 더 나은 고객 경험을 창출하고 비즈니스 기능을 개선하며 수익원을 창출하는 기능을 제공합니다. 윤리적 방식으로 도입할 수 있는 편견 및 영향과 예측의 가치 간의 균형을 맞추는 것이 좋습니다. Microsoft가 [책임감 있는 AI를 해결](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6)하는 방법에 대해 자세히 알아보세요. Azure Machine Learning과 관련된 [책임 있는 기계 학습을 위한 기술 및 프로세스](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml)에 대해서도 알아볼 수 있습니다.

## <a name="prerequisites"></a>필수 구성 요소

- 현재이 기능은 [Machine Learning Studio(클래식)](https://studio.azureml.net) 및 [Azure Machine Learning 일괄 파이프라인](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines)을 통해 게시 된 웹 서비스를 지원합니다.

- 이 기능을 사용하려면 Azure Studio 인스턴스와 연결된 Azure Data Lake Gen2 스토리지 계정이 필요합니다. 자세한 내용은 [Azure Data Lake Storage Gen2 저장소 계정 만들기](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)를 참조하세요.

## <a name="add-a-new-workflow"></a>새 워크플로 추가

1. **인텔리전스** > **사용자 지정 모델** 로 이동하고 **새로운 워크플로** 를 선택합니다.

1. **이름** 필드에서 사용자 지정 모델에 인식할 수 있는 이름을 지정합니다.

   > [!div class="mx-imgBorder"]
   > ![새 워크플로우 창의 스크린샷](media/new-workflowv2.png "새 워크플로우 창의 스크린샷")

1. **웹 서비스가 포함된 테넌트** 에서 웹 서비스가 포함된 조직을 선택합니다.

1. Azure 기계 학습 구독이 Customer Insights와 다른 테넌트에 있는 경우 선택한 조직의 자격 증명과 함께 **로그인** 을 선택합니다.

1. 웹 서비스와 연결된 **작업 영역** 을 선택합니다. Azure Machine Learning v1(Machine Learning Studio(클래식)) 및 Azure Machine Learning v2(Azure Machine Learning)의 두 섹션이 나열됩니다. Machine Learning Studio(클래식) 웹 서비스에 적합한 작업 영역이 무엇인지 확실하지 않은 경우 **임의** 를 선택합니다.

1. **모델이 포함된 웹 서비스** 드롭다운에서 Machine Learning Studio(클래식) 웹 서비스 또는 Azure Machine Learning 파이프라인을 선택합니다. 그런 후에 **다음** 을 선택합니다.
   - [Machine Learning Studio(클래식)에서 웹 서비스 게시](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)에 대해 자세히 알아보세요.
   - [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) 또는 [디자이너를 사용하여 Azure Machine Learning에서 파이프라인을 게시](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer)하는 방법에 대해 자세히 알아보세요. 
     > [!NOTE]
     > 파이프라인은 [파이프라인 엔드포인트](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run) 아래에 게시되어야 합니다.

1. 각 **웹 서비스 입력** 에 대상 그룹 인사이트의 일치하는 **엔터티** 를 선택하고 **다음** 을 선택합니다.

   > [!div class="mx-imgBorder"]
   > ![워크플로 구성](media/intelligence-screen2-updated.png "워크플로 구성")

1. **모델 출력 매개 변수** 단계에서 다음 속성을 설정합니다.
   - Machine Learning Studio(클래식)
      1. 웹 서비스 출력 결과가 전달될 출력 **엔터티 이름** 을 입력합니다.
   - Azure 기계 학습
      1. 파이프라인 출력 결과가 유입될 출력 **엔터티 이름** 을 입력합니다.
      1. 드롭다운에서 배치 파이프라인의 **출력 데이터 저장소 매개 변수 이름** 을 선택합니다.
      1. 드롭다운에서 배치 파이프라인의 **출력 경로 매개 변수 이름** 을 선택합니다.
      
      > [!div class="mx-imgBorder"]
      > ![모델 출력 매개 변수 창](media/intelligence-screen3-outputparameters.png "모델 출력 매개 변수 창")

1. 고객을 식별하는 **결과의 고객 ID** 드롭다운 목록에서 일치하는 특성을 선택하고 **저장** 을 선택합니다.
   
   > [!div class="mx-imgBorder"]
   > ![결과를 고객 데이터 창에 연결](media/intelligence-screen4-relatetocustomer.png "결과를 고객 데이터 창에 연결")

1. 워크플로에 대한 세부 정보가 있는 **워크플로 저장** 화면이 표시됩니다.    
   Azure Machine Learning 파이프라인에 대한 워크플로를 구성한 경우 대상 그룹 인사이트가 파이프라인이 포함된 작업 영역에 연결됩니다. 대상 그룹 인사이트는 Azure 작업 영역에서 **기여자** 역할을 받습니다.

1. **완료** 를 선택합니다.

1. 이제 **사용자 지정 모델** 페이지에서 워크플로를 실행할 수 있습니다.

## <a name="edit-a-workflow"></a>워크플로 편집

1. **사용자 지정 모델** 페이지에서 이전에 만든 워크플로 옆의 **작업** 열에서 세로 줄임표를 선택하고 **편집** 을 선택합니다.

1. **표시 이름** 필드에서 워크플로의 인식 가능한 이름을 업데이트할 수 있지만 구성된 웹 서비스 또는 파이프라인은 변경할 수 없습니다. **다음** 을 선택합니다.

1. 각 **웹 서비스 입력** 에 대해 대상 그룹 인사이트에서 일치하는 **엔터티** 를 업데이트할 수 있습니다. 그런 후에 **다음** 을 선택합니다.

1. **모델 출력 매개 변수** 단계에서 다음 속성을 설정합니다.
   - Machine Learning Studio(클래식)
      1. 웹 서비스 출력 결과가 전달될 출력 **엔터티 이름** 을 입력합니다.
   - Azure 기계 학습
      1. 파이프라인 출력 결과가 유입될 출력 **엔터티 이름** 을 입력합니다.
      1. 테스트 파이프라인의 **출력 데이터 저장소 매개 변수 이름** 을 선택합니다.
      1. 테스트 파이프라인의 **출력 경로 매개 변수 이름** 을 선택합니다.

1. 고객을 식별하는 **결과의 고객 ID** 드롭다운 목록에서 일치하는 특성을 선택하고 **저장** 을 선택합니다.
   고객 엔터티의 고객 ID 열과 유사한 값이 있는 추론 출력에서 특성을 선택해야 합니다. 데이터 집합에 이러한 열이 없으면 행을 고유하게 식별하는 특성을 선택합니다.

## <a name="run-a-workflow"></a>워크플로 실행

1. **사용자 지정 모델** 페이지에서 이전에 만든 워크플로 옆의 **작업** 열에서 세로 줄임표를 선택합니다.

1. **실행** 을 선택합니다.

워크플로는 예약된 새로 고침마다 자동으로 실행됩니다. [예약된 새로 고침 설정](system.md#schedule-tab)에 대해 자세히 알아보세요.

## <a name="delete-a-workflow"></a>워크플로 삭제

1. **사용자 지정 모델** 페이지에서 이전에 만든 워크플로 옆의 **작업** 열에서 세로 줄임표를 선택합니다.

1. **삭제** 를 선택하고 삭제를 확인합니다.

워크플로가 삭제됩니다. 워크플로를 만들 때 생성된 [엔터티](entities.md)이며 **엔터티** 페이지에서 확인할 수 있습니다.
