---
title: 사용자 지정 기계 학습 모델 | Microsoft Docs
description: Dynamics 365 Customer Insights Azure Machine Learning의 사용자 지정 모델로 작업합니다.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34489faaecc5da1ce3dd68d799b3e0e0d9672ab7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267242"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="9bbcb-103">사용자 지정 기계 학습 모델</span><span class="sxs-lookup"><span data-stu-id="9bbcb-103">Custom machine learning models</span></span>

<span data-ttu-id="9bbcb-104">**인텔리전스** > **사용자 지정 모델** 을 사용하면 Azure Machine Learning 모델을 기반으로 워크플로를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="9bbcb-105">워크플로는 인사이트를 생성할 데이터를 선택하고 결과를 통합 고객 데이터에 매핑하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="9bbcb-106">사용자 지정 ML 모델 빌드에 대한 자세한 내용은 [Azure Machine Learning 기반 모델 사용](azure-machine-learning-experiments.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="9bbcb-107">책임감 있는 AI</span><span class="sxs-lookup"><span data-stu-id="9bbcb-107">Responsible AI</span></span>

<span data-ttu-id="9bbcb-108">예측은 더 나은 고객 경험을 창출하고 비즈니스 기능을 개선하며 수익원을 창출하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="9bbcb-109">윤리적 방식으로 도입할 수 있는 편견 및 영향과 예측의 가치 간의 균형을 맞추는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="9bbcb-110">Microsoft가 [책임감 있는 AI를 해결](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6)하는 방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="9bbcb-111">Azure Machine Learning과 관련된 [책임 있는 기계 학습을 위한 기술 및 프로세스](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml)에 대해서도 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9bbcb-112">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="9bbcb-112">Prerequisites</span></span>

- <span data-ttu-id="9bbcb-113">현재이 기능은 [Machine Learning Studio(클래식)](https://studio.azureml.net) 및 [Azure Machine Learning 일괄 파이프라인](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines)을 통해 게시 된 웹 서비스를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="9bbcb-114">이 기능을 사용하려면 Azure Studio 인스턴스와 연결된 Azure Data Lake Gen2 스토리지 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="9bbcb-115">자세한 내용은 [Azure Data Lake Storage Gen2 저장소 계정 만들기](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="9bbcb-116">새 워크플로 추가</span><span class="sxs-lookup"><span data-stu-id="9bbcb-116">Add a new workflow</span></span>

1. <span data-ttu-id="9bbcb-117">**인텔리전스** > **사용자 지정 모델** 로 이동하고 **새로운 워크플로** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="9bbcb-118">**이름** 필드에서 사용자 지정 모델에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9bbcb-119">![새 워크플로우 창의 스크린샷](media/new-workflowv2.png "새 워크플로우 창의 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="9bbcb-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="9bbcb-120">**웹 서비스가 포함된 테넌트** 에서 웹 서비스가 포함된 조직을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="9bbcb-121">Azure 기계 학습 구독이 Customer Insights와 다른 테넌트에 있는 경우 선택한 조직의 자격 증명과 함께 **로그인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="9bbcb-122">웹 서비스와 연결된 **작업 영역** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="9bbcb-123">Azure Machine Learning v1(Machine Learning Studio(클래식)) 및 Azure Machine Learning v2(Azure Machine Learning)의 두 섹션이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="9bbcb-124">Machine Learning Studio(클래식) 웹 서비스에 적합한 작업 영역이 무엇인지 확실하지 않은 경우 **임의** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="9bbcb-125">**모델이 포함된 웹 서비스** 드롭다운에서 Machine Learning Studio(클래식) 웹 서비스 또는 Azure Machine Learning 파이프라인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="9bbcb-126">그런 후에 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="9bbcb-127">[Machine Learning Studio(클래식)에서 웹 서비스 게시](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="9bbcb-128">[SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) 또는 [디자이너를 사용하여 Azure Machine Learning에서 파이프라인을 게시](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer)하는 방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="9bbcb-129">파이프라인은 [파이프라인 엔드포인트](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run) 아래에 게시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="9bbcb-130">각 **웹 서비스 입력** 에 대상 그룹 인사이트의 일치하는 **엔터티** 를 선택하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="9bbcb-131">사용자 지정 모델 워크플로는 휴리스틱을 적용하여 필드의 이름 및 데이터 형식을 기반으로 웹 서비스 입력 필드를 엔터티 속성에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-131">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="9bbcb-132">웹 서비스 필드를 엔터티에 매핑할 수 없는 경우 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-132">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9bbcb-133">![워크플로 구성](media/intelligence-screen2-updated.png "워크플로 구성")</span><span class="sxs-lookup"><span data-stu-id="9bbcb-133">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>
   
1. <span data-ttu-id="9bbcb-134">**모델 출력 매개 변수** 단계에서 다음 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-134">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="9bbcb-135">Machine Learning Studio(클래식)</span><span class="sxs-lookup"><span data-stu-id="9bbcb-135">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="9bbcb-136">웹 서비스 출력 결과가 전달될 출력 **엔터티 이름** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-136">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="9bbcb-137">Azure 기계 학습</span><span class="sxs-lookup"><span data-stu-id="9bbcb-137">Azure Machine Learning</span></span>
      1. <span data-ttu-id="9bbcb-138">파이프라인 출력 결과가 유입될 출력 **엔터티 이름** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-138">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="9bbcb-139">드롭다운에서 배치 파이프라인의 **출력 데이터 저장소 매개 변수 이름** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-139">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="9bbcb-140">드롭다운에서 배치 파이프라인의 **출력 경로 매개 변수 이름** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-140">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="9bbcb-141">![모델 출력 매개 변수 창](media/intelligence-screen3-outputparameters.png "모델 출력 매개 변수 창")</span><span class="sxs-lookup"><span data-stu-id="9bbcb-141">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="9bbcb-142">고객을 식별하는 **결과의 고객 ID** 드롭다운 목록에서 일치하는 특성을 선택하고 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-142">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9bbcb-143">![결과를 고객 데이터 창에 연결](media/intelligence-screen4-relatetocustomer.png "결과를 고객 데이터 창에 연결")</span><span class="sxs-lookup"><span data-stu-id="9bbcb-143">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="9bbcb-144">워크플로에 대한 세부 정보가 있는 **워크플로 저장** 화면이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-144">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="9bbcb-145">Azure Machine Learning 파이프라인에 대한 워크플로를 구성한 경우 대상 그룹 인사이트가 파이프라인이 포함된 작업 영역에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-145">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="9bbcb-146">대상 그룹 인사이트는 Azure 작업 영역에서 **기여자** 역할을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-146">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="9bbcb-147">**완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-147">Select **Done**.</span></span>

1. <span data-ttu-id="9bbcb-148">이제 **사용자 지정 모델** 페이지에서 워크플로를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-148">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="9bbcb-149">워크플로 편집</span><span class="sxs-lookup"><span data-stu-id="9bbcb-149">Edit a workflow</span></span>

1. <span data-ttu-id="9bbcb-150">**사용자 지정 모델** 페이지에서 이전에 만든 워크플로 옆의 **작업** 열에서 세로 줄임표를 선택하고 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-150">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="9bbcb-151">**표시 이름** 필드에서 워크플로의 인식 가능한 이름을 업데이트할 수 있지만 구성된 웹 서비스 또는 파이프라인은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-151">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="9bbcb-152">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-152">Select **Next**.</span></span>

1. <span data-ttu-id="9bbcb-153">각 **웹 서비스 입력** 에 대해 대상 그룹 인사이트에서 일치하는 **엔터티** 를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-153">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="9bbcb-154">그런 후에 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-154">Then, select **Next**.</span></span>

1. <span data-ttu-id="9bbcb-155">**모델 출력 매개 변수** 단계에서 다음 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-155">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="9bbcb-156">Machine Learning Studio(클래식)</span><span class="sxs-lookup"><span data-stu-id="9bbcb-156">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="9bbcb-157">웹 서비스 출력 결과가 전달될 출력 **엔터티 이름** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-157">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="9bbcb-158">Azure 기계 학습</span><span class="sxs-lookup"><span data-stu-id="9bbcb-158">Azure Machine Learning</span></span>
      1. <span data-ttu-id="9bbcb-159">파이프라인 출력 결과가 유입될 출력 **엔터티 이름** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-159">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="9bbcb-160">테스트 파이프라인의 **출력 데이터 저장소 매개 변수 이름** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-160">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="9bbcb-161">테스트 파이프라인의 **출력 경로 매개 변수 이름** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-161">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="9bbcb-162">고객을 식별하는 **결과의 고객 ID** 드롭다운 목록에서 일치하는 특성을 선택하고 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-162">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="9bbcb-163">고객 엔터티의 고객 ID 열과 유사한 값이 있는 추론 출력에서 특성을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-163">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="9bbcb-164">데이터 집합에 이러한 열이 없으면 행을 고유하게 식별하는 특성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-164">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="9bbcb-165">워크플로 실행</span><span class="sxs-lookup"><span data-stu-id="9bbcb-165">Run a workflow</span></span>

1. <span data-ttu-id="9bbcb-166">**사용자 지정 모델** 페이지에서 이전에 만든 워크플로 옆의 **작업** 열에서 세로 줄임표를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-166">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="9bbcb-167">**실행** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-167">Select **Run**.</span></span>

<span data-ttu-id="9bbcb-168">워크플로는 예약된 새로 고침마다 자동으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-168">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="9bbcb-169">[예약된 새로 고침 설정](system.md#schedule-tab)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-169">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="9bbcb-170">워크플로 삭제</span><span class="sxs-lookup"><span data-stu-id="9bbcb-170">Delete a workflow</span></span>

1. <span data-ttu-id="9bbcb-171">**사용자 지정 모델** 페이지에서 이전에 만든 워크플로 옆의 **작업** 열에서 세로 줄임표를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-171">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="9bbcb-172">**삭제** 를 선택하고 삭제를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-172">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="9bbcb-173">워크플로가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-173">Your workflow will be deleted.</span></span> <span data-ttu-id="9bbcb-174">워크플로를 만들 때 생성된 [엔터티](entities.md)이며 **엔터티** 페이지에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bbcb-174">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]