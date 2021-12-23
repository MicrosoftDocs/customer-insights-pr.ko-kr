---
title: Azure Machine Learning 실험
description: Dynamics 365 Customer Insights의 Azure Machine Learning 기반 모델을 사용합니다.
ms.date: 12/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e37eec503c9df83ef72497e22afa1266296e642c
ms.sourcegitcommit: 58651d33e0a7d438a2587c9ceeaf7ff58ae3b648
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2021
ms.locfileid: "7881746"
---
# <a name="use-azure-machine-learning-based-models"></a>Azure Machine Learning 기반 모델 사용

Dynamics 365 Customer Insights의 통합 데이터는 추가 비즈니스 인사이트를 생성할 수 있는 기계 학습 모델을 구축하기 위한 소스입니다. Customer Insights는 Azure Machine Learning과 통합되어 고유한 사용자 지정 모델을 사용합니다.

## <a name="prerequisites"></a>필수 구성 요소

- Customer Insights에 액세스
- 활성 Azure Enterprise 구독
- [통합 고객 프로필](data-unification.md)
- 구성된 [Azure Blob Storage로 엔터티 내보내기](export-azure-blob-storage.md)

## <a name="set-up-azure-machine-learning-workspace"></a>Azure Machine Learning 작업 영역 설정

1. 작업 영역을 만드는 다양한 옵션은 [Azure Machine Learning 작업 영역 만들기](/azure/machine-learning/concept-workspace#-create-a-workspace)를 참조하세요. 최상의 성능을 위해 지리적으로 Customer Insights 환경에 가장 가까운 Azure 지역에 작업 영역을 만듭니다.

1. [Azure Machine Learning Studio](https://ml.azure.com/)를 통해 작업 영역에 액세스합니다. 작업 영역과 [상호 작용하는 방법](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction)에는 여러 가지가 있습니다.

## <a name="work-with-azure-machine-learning-designer"></a>Azure Machine Learning 디자이너로 작업

Azure Machine Learning 디자이너는 데이터 세트 및 모듈을 끌어다 놓을 수 있는 시각적 캔버스를 제공합니다. 디자이너에서 생성된 배치 파이프라인은 적절히 구성된 경우 Customer Insights에 통합될 수 있습니다. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>Azure Machine Learning SDK로 작업

데이터 과학자 및 AI 개발자는 [Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py)를 사용하여 기계 학습 워크플로를 빌드합니다. 현재 SDK를 사용하여 훈련된 모델은 Customer Insights와 직접 통합할 수 없습니다. Customer Insights와 통합하려면 해당 모델을 사용하는 배치 추론 파이프라인이 필요합니다.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Customer Insights와 통합하기 위한 배치 파이프라인 요구 사항

### <a name="dataset-configuration"></a>데이터 집합 구성

Customer Insights에서 배치 추론 파이프라인으로 엔터티 데이터를 사용하려면 데이터 집합을 만들어야 합니다. 이러한 데이터 집합은 작업 영역에 등록해야 합니다. 현재는 .csv 형식의 [테이블 형식 데이터 집합](/azure/machine-learning/how-to-create-register-datasets#tabulardataset)만 지원합니다. 항목 데이터에 해당하는 데이터 집합은 파이프라인 매개 변수로 매개 변수화되어야 합니다.
   
* 디자이너의 데이터 집합 매개 변수
   
     디자이너에서 **데이터 집합의 열 선택** 을 열고 매개 변수 이름을 제공하는 **파이프라인 매개 변수로 설정** 을 선택합니다.

     > [!div class="mx-imgBorder"]
     > ![디자이너의 데이터 집합 매개 변수화.](media/intelligence-designer-dataset-parameters.png "디자이너의 데이터 집합 매개 변수화")
   
* SDK(Python)의 데이터 집합 매개 변수
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>배치 추론 파이프라인
  
* 디자이너에서 교육 파이프라인을 사용하여 추론 파이프라인을 생성하거나 업데이트할 수 있습니다. 현재는 일괄 추론 파이프라인만 지원됩니다.

* SDK를 사용하여 파이프라인을 엔드포인트에 게시할 수 있습니다. 현재 Customer Insights는 기계 학습 작업 영역의 배치 파이프라인 엔드포인트에서 기본 파이프라인과 통합됩니다.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Customer Insights로 파이프라인 데이터 가져오기

* 디자이너는 파이프라인의 출력을 Azure Storage로 내보낼 수 있는 [데이터 내보내기 모듈](/azure/machine-learning/algorithm-module-reference/export-data)을 제공합니다. 현재 모듈은 데이터 저장소 유형 **Azure Blob Storage** 를 사용하고 **데이터 저장소** 및 상대 **경로** 를 매개 변수화해야 합니다. Customer Insights는 파이프라인 실행 중에 제품에 액세스할 수 있는 데이터 저장소 및 경로를 사용하여 이러한 매개 변수를 모두 재정의합니다.
   > [!div class="mx-imgBorder"]
   > ![데이터 내보내기 모듈 구성.](media/intelligence-designer-importdata.png "데이터 내보내기 모듈 구성")
   
* 코드를 사용하여 추론 출력을 작성할 때 출력을 작업 영역의 *등록된 데이터 스토어* 내의 경로에 업로드할 수 있습니다. 경로 및 데이터 스토어가 파이프라인에서 매개 변수화되면 Customer Insights에서 추론 출력을 읽고 가져올 수 있습니다. 현재 csv 형식의 단일 테이블 형식 출력이 지원됩니다. 경로에는 디렉터리와 파일 이름이 포함되어야 합니다.

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```


[!INCLUDE[footer-include](../includes/footer-banner.md)]