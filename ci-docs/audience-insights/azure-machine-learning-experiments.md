---
title: Azure Machine Learning 실험
description: Dynamics 365 Customer Insights의 Azure Machine Learning 기반 모델을 사용합니다.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: edd2cf488b52cef87b09b90336e48fdc7f470a68
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597427"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="85877-103">Azure Machine Learning 기반 모델 사용</span><span class="sxs-lookup"><span data-stu-id="85877-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="85877-104">Dynamics 365 Customer Insights의 통합 데이터는 추가 비즈니스 인사이트를 생성할 수 있는 기계 학습 모델을 구축하기 위한 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="85877-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="85877-105">Customer Insights는 Machine Learning Studio(클래식) 및 Azure Machine Learning과 통합되어 고유한 사용자 지정 모델을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="85877-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="85877-106">Machine Learning Studio(클래식)에서 빌드된 실험의 예는 [Machine Learning Studio(클래식) 실험](machine-learning-studio-experiments.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="85877-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="85877-107">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="85877-107">Prerequisites</span></span>

- <span data-ttu-id="85877-108">Customer Insights에 액세스</span><span class="sxs-lookup"><span data-stu-id="85877-108">Access to Customer Insights</span></span>
- <span data-ttu-id="85877-109">활성 Azure Enterprise 구독</span><span class="sxs-lookup"><span data-stu-id="85877-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="85877-110">통합 고객 프로필</span><span class="sxs-lookup"><span data-stu-id="85877-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="85877-111">구성된 [Azure Blob Storage로 엔터티 내보내기](export-azure-blob-storage.md)</span><span class="sxs-lookup"><span data-stu-id="85877-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="85877-112">Azure Machine Learning 작업 영역 설정</span><span class="sxs-lookup"><span data-stu-id="85877-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="85877-113">작업 영역을 만드는 다양한 옵션은 [Azure Machine Learning 작업 영역 만들기](/azure/machine-learning/concept-workspace#-create-a-workspace)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="85877-113">See [create a Azure Machine Learning workspace](/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="85877-114">최상의 성능을 위해 지리적으로 Customer Insights 환경에 가장 가까운 Azure 지역에 작업 영역을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85877-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="85877-115">[Azure Machine Learning Studio](https://ml.azure.com/)를 통해 작업 영역에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="85877-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="85877-116">작업 영역과 [상호 작용하는 방법](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction)에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85877-116">There are several [ways to interact](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="85877-117">Azure Machine Learning 디자이너로 작업</span><span class="sxs-lookup"><span data-stu-id="85877-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="85877-118">Azure Machine Learning 디자이너는 Machine Learning Studio(클래식)와 유사한 데이터 집합 및 모듈을 끌어서 놓을 수 있는 시각적 캔버스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="85877-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="85877-119">디자이너에서 생성된 배치 파이프라인은 적절히 구성된 경우 Customer Insights에 통합될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85877-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="85877-120">Azure Machine Learning SDK로 작업</span><span class="sxs-lookup"><span data-stu-id="85877-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="85877-121">데이터 과학자 및 AI 개발자는 [Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py)를 사용하여 기계 학습 워크플로를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="85877-121">Data scientists and AI developers use the [Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) to build machine learning workflows.</span></span> <span data-ttu-id="85877-122">현재 SDK를 사용하여 훈련된 모델은 Customer Insights와 직접 통합할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="85877-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="85877-123">Customer Insights와 통합하려면 해당 모델을 사용하는 배치 추론 파이프라인이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="85877-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="85877-124">Customer Insights와 통합하기 위한 배치 파이프라인 요구 사항</span><span class="sxs-lookup"><span data-stu-id="85877-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="85877-125">데이터 집합 구성</span><span class="sxs-lookup"><span data-stu-id="85877-125">Dataset Configuration</span></span>

<span data-ttu-id="85877-126">Customer Insights에서 배치 추론 파이프라인으로 엔터티 데이터를 사용하려면 데이터 집합을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85877-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="85877-127">이러한 데이터 집합은 작업 영역에 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85877-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="85877-128">현재는 .csv 형식의 [테이블 형식 데이터 집합](/azure/machine-learning/how-to-create-register-datasets#tabulardataset)만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="85877-128">Currently, we only support [tabular datasets](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="85877-129">항목 데이터에 해당하는 데이터 집합은 파이프라인 매개 변수로 매개 변수화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85877-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="85877-130">디자이너의 데이터 집합 매개 변수</span><span class="sxs-lookup"><span data-stu-id="85877-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="85877-131">디자이너에서 **데이터 집합의 열 선택** 을 열고 매개 변수 이름을 제공하는 **파이프라인 매개 변수로 설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="85877-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="85877-132">![디자이너의 데이터 집합 매개 변수화](media/intelligence-designer-dataset-parameters.png "디자이너의 데이터 집합 매개 변수화")</span><span class="sxs-lookup"><span data-stu-id="85877-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="85877-133">SDK(Python)의 데이터 집합 매개 변수</span><span class="sxs-lookup"><span data-stu-id="85877-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="85877-134">배치 추론 파이프라인</span><span class="sxs-lookup"><span data-stu-id="85877-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="85877-135">디자이너에서 교육 파이프라인을 사용하여 추론 파이프라인을 생성하거나 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85877-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="85877-136">현재는 일괄 추론 파이프라인만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="85877-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="85877-137">SDK를 사용하여 파이프라인을 엔드포인트에 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85877-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="85877-138">현재 Customer Insights는 기계 학습 작업 영역의 배치 파이프라인 엔드포인트에서 기본 파이프라인과 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="85877-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="85877-139">Customer Insights로 파이프라인 데이터 가져오기</span><span class="sxs-lookup"><span data-stu-id="85877-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="85877-140">디자이너는 파이프라인의 출력을 Azure Storage로 내보낼 수 있는 [데이터 내보내기 모듈](/azure/machine-learning/algorithm-module-reference/export-data)을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="85877-140">The designer provides the [Export Data module](/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="85877-141">현재 모듈은 데이터 저장소 유형 **Azure Blob Storage** 를 사용하고 **데이터 저장소** 및 상대 **경로** 를 매개 변수화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85877-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="85877-142">Customer Insights는 파이프라인 실행 중에 제품에 액세스할 수 있는 데이터 저장소 및 경로를 사용하여 이러한 매개 변수를 모두 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="85877-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="85877-143">![데이터 내보내기 모듈 구성](media/intelligence-designer-importdata.png "데이터 내보내기 모듈 구성")</span><span class="sxs-lookup"><span data-stu-id="85877-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="85877-144">코드를 사용하여 추론 출력을 작성할 때 출력을 작업 영역의 *등록된 데이터 스토어* 내의 경로에 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85877-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="85877-145">경로 및 데이터 스토어가 파이프라인에서 매개 변수화되면 Customer Insights에서 추론 출력을 읽고 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85877-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="85877-146">현재 csv 형식의 단일 테이블 형식 출력이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="85877-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="85877-147">경로에는 디렉터리와 파일 이름이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85877-147">The path must include the directory and filename.</span></span>

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