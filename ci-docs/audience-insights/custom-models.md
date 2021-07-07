---
title: 사용자 지정 기계 학습 모델 | Microsoft Docs
description: Dynamics 365 Customer Insights Azure Machine Learning의 사용자 지정 모델로 작업합니다.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 82f6f363497f8f1b45fa84acd49bcaed332e60e8
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305648"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="33dc5-103">사용자 지정 기계 학습 모델</span><span class="sxs-lookup"><span data-stu-id="33dc5-103">Custom machine learning models</span></span>

<span data-ttu-id="33dc5-104">**인텔리전스** > **사용자 지정 모델** 을 사용하면 Azure Machine Learning 모델을 기반으로 워크플로를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="33dc5-105">워크플로는 인사이트를 생성할 데이터를 선택하고 결과를 통합 고객 데이터에 매핑하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="33dc5-106">사용자 지정 ML 모델 빌드에 대한 자세한 내용은 [Azure Machine Learning 기반 모델 사용](azure-machine-learning-experiments.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33dc5-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="33dc5-107">책임감 있는 AI</span><span class="sxs-lookup"><span data-stu-id="33dc5-107">Responsible AI</span></span>

<span data-ttu-id="33dc5-108">예측은 더 나은 고객 경험을 창출하고 비즈니스 기능을 개선하며 수익원을 창출하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="33dc5-109">윤리적 방식으로 도입할 수 있는 편견 및 영향과 예측의 가치 간의 균형을 맞추는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="33dc5-110">Microsoft가 [책임감 있는 AI를 해결](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6)하는 방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="33dc5-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="33dc5-111">Azure Machine Learning과 관련된 [책임 있는 기계 학습을 위한 기술 및 프로세스](/azure/machine-learning/concept-responsible-ml)에 대해서도 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-111">You can also learn about [techniques and processes for responsible machine learning](/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="33dc5-112">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="33dc5-112">Prerequisites</span></span>

- <span data-ttu-id="33dc5-113">현재이 기능은 [Machine Learning Studio(클래식)](https://studio.azureml.net) 및 [Azure Machine Learning 일괄 파이프라인](/azure/machine-learning/concept-ml-pipelines)을 통해 게시 된 웹 서비스를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="33dc5-114">이 기능을 사용하려면 Azure Studio 인스턴스와 연결된 Azure Data Lake Gen2 스토리지 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="33dc5-115">자세한 내용은 [Azure Data Lake Storage Gen2 스토리지 계정 만들기](/azure/storage/blobs/data-lake-storage-quickstart-create-account)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="33dc5-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span></span>

- <span data-ttu-id="33dc5-116">파이프라인이 있는 Azure Machine Learning 작업 영역의 경우 Azure Machine Learning 작업 영역에 대한 담당자 또는 사용자 액세스 관리자 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-116">For Azure Machine Learning workspaces with pipelines, you need Owner or User Access Administrator permissions to the Azure Machine Learning Workspace.</span></span>

   > [!NOTE]
   > <span data-ttu-id="33dc5-117">Customer Insights 인스턴스와 워크플로에서 선택한 Azure 웹 서비스 또는 파이프라인 간에 데이터가 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-117">Data is transferred between your Customer Insights instances and the selected Azure web services or pipelines in the workflow.</span></span> <span data-ttu-id="33dc5-118">Azure 서비스로 데이터를 전송하는 경우 조직의 해당 데이터에 대한 법적 요구 사항 또는 규제 사항을 준수하는 데 필요한 방식과 위치에서 데이터를 처리하도록 서비스가 구성되어 있는지 확인하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-118">When you transfer data to an Azure service, please ensure that service is configured to process data in the manner and location necessary to comply with any legal or regulatory requirements for that data for your organization.</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="33dc5-119">새 워크플로 추가</span><span class="sxs-lookup"><span data-stu-id="33dc5-119">Add a new workflow</span></span>

1. <span data-ttu-id="33dc5-120">**인텔리전스** > **사용자 지정 모델** 로 이동하고 **새로운 워크플로** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-120">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="33dc5-121">**이름** 필드에서 사용자 지정 모델에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-121">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="33dc5-122">![새 워크플로우 창의 스크린샷](media/new-workflowv2.png "새 워크플로우 창의 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="33dc5-122">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="33dc5-123">**웹 서비스가 포함된 테넌트** 에서 웹 서비스가 포함된 조직을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-123">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="33dc5-124">Azure 기계 학습 구독이 Customer Insights와 다른 테넌트에 있는 경우 선택한 조직의 자격 증명과 함께 **로그인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-124">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="33dc5-125">웹 서비스와 연결된 **작업 영역** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-125">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="33dc5-126">Azure Machine Learning v1(Machine Learning Studio(클래식)) 및 Azure Machine Learning v2(Azure Machine Learning)의 두 섹션이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-126">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="33dc5-127">Machine Learning Studio(클래식) 웹 서비스에 적합한 작업 영역이 무엇인지 확실하지 않은 경우 **임의** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-127">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="33dc5-128">**모델이 포함된 웹 서비스** 드롭다운에서 Machine Learning Studio(클래식) 웹 서비스 또는 Azure Machine Learning 파이프라인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-128">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="33dc5-129">그런 후에 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-129">Then, select **Next**.</span></span>
   - <span data-ttu-id="33dc5-130">[Machine Learning Studio(클래식)에서 웹 서비스 게시](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="33dc5-130">Learn more about [publishing a web service in Machine Learning Studio (classic)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="33dc5-131">[SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) 또는 [디자이너를 사용하여 Azure Machine Learning에서 파이프라인을 게시](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer)하는 방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="33dc5-131">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="33dc5-132">파이프라인은 [파이프라인 엔드포인트](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run) 아래에 게시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-132">Your pipeline must be published under a [pipeline endpoint](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="33dc5-133">각 **웹 서비스 입력** 에 대상 그룹 인사이트의 일치하는 **엔터티** 를 선택하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-133">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="33dc5-134">사용자 지정 모델 워크플로는 휴리스틱을 적용하여 필드의 이름 및 데이터 형식을 기반으로 웹 서비스 입력 필드를 엔터티 속성에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-134">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="33dc5-135">웹 서비스 필드를 엔터티에 매핑할 수 없는 경우 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-135">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="33dc5-136">![워크플로 구성](media/intelligence-screen2-updated.png "워크플로 구성")</span><span class="sxs-lookup"><span data-stu-id="33dc5-136">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="33dc5-137">**모델 출력 매개 변수** 단계에서 다음 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-137">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="33dc5-138">Machine Learning Studio(클래식)</span><span class="sxs-lookup"><span data-stu-id="33dc5-138">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="33dc5-139">웹 서비스 출력 결과가 전달될 출력 **엔터티 이름** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-139">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="33dc5-140">Azure 기계 학습</span><span class="sxs-lookup"><span data-stu-id="33dc5-140">Azure Machine Learning</span></span>
      1. <span data-ttu-id="33dc5-141">파이프라인 출력 결과가 유입될 출력 **엔터티 이름** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-141">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="33dc5-142">드롭다운에서 배치 파이프라인의 **출력 데이터 저장소 매개 변수 이름** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-142">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="33dc5-143">드롭다운에서 배치 파이프라인의 **출력 경로 매개 변수 이름** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-143">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="33dc5-144">![모델 출력 매개 변수 창](media/intelligence-screen3-outputparameters.png "모델 출력 매개 변수 창")</span><span class="sxs-lookup"><span data-stu-id="33dc5-144">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="33dc5-145">고객을 식별하는 **결과의 고객 ID** 드롭다운 목록에서 일치하는 특성을 선택하고 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-145">Select the matching attribute from the **Customer ID in results** dropdown list that identifies customers and select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="33dc5-146">![결과를 고객 데이터 창에 연결](media/intelligence-screen4-relatetocustomer.png "결과를 고객 데이터 창에 연결")</span><span class="sxs-lookup"><span data-stu-id="33dc5-146">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="33dc5-147">워크플로에 대한 세부 정보가 있는 **워크플로 저장** 화면이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-147">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="33dc5-148">Azure Machine Learning 파이프라인에 대한 워크플로를 구성한 경우 대상 그룹 인사이트가 파이프라인이 포함된 작업 영역에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-148">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="33dc5-149">대상 그룹 인사이트는 Azure 작업 영역에서 **기여자** 역할을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-149">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="33dc5-150">**완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-150">Select **Done**.</span></span>

1. <span data-ttu-id="33dc5-151">이제 **사용자 지정 모델** 페이지에서 워크플로를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-151">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="33dc5-152">워크플로 편집</span><span class="sxs-lookup"><span data-stu-id="33dc5-152">Edit a workflow</span></span>

1. <span data-ttu-id="33dc5-153">**사용자 지정 모델** 페이지에서 이전에 만든 워크플로 옆의 **작업** 열에서 세로 줄임표를 선택하고 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-153">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="33dc5-154">**표시 이름** 필드에서 워크플로의 인식 가능한 이름을 업데이트할 수 있지만 구성된 웹 서비스 또는 파이프라인은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-154">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="33dc5-155">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-155">Select **Next**.</span></span>

1. <span data-ttu-id="33dc5-156">각 **웹 서비스 입력** 에 대해 대상 그룹 인사이트에서 일치하는 **엔터티** 를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-156">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="33dc5-157">그런 후에 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-157">Then, select **Next**.</span></span>

1. <span data-ttu-id="33dc5-158">**모델 출력 매개 변수** 단계에서 다음 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-158">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="33dc5-159">Machine Learning Studio(클래식)</span><span class="sxs-lookup"><span data-stu-id="33dc5-159">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="33dc5-160">웹 서비스 출력 결과가 전달될 출력 **엔터티 이름** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-160">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="33dc5-161">Azure 기계 학습</span><span class="sxs-lookup"><span data-stu-id="33dc5-161">Azure Machine Learning</span></span>
      1. <span data-ttu-id="33dc5-162">파이프라인 출력 결과가 유입될 출력 **엔터티 이름** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-162">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="33dc5-163">테스트 파이프라인의 **출력 데이터 저장소 매개 변수 이름** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-163">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="33dc5-164">테스트 파이프라인의 **출력 경로 매개 변수 이름** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-164">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="33dc5-165">고객을 식별하는 **결과의 고객 ID** 드롭다운 목록에서 일치하는 특성을 선택하고 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-165">Select the matching attribute from the **Customer ID in results** dropdown list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="33dc5-166">고객 엔터티의 고객 ID 열과 유사한 값이 있는 추론 출력에서 특성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-166">Choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="33dc5-167">데이터 집합에 이러한 열이 없으면 행을 고유하게 식별하는 특성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-167">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="33dc5-168">워크플로 실행</span><span class="sxs-lookup"><span data-stu-id="33dc5-168">Run a workflow</span></span>

1. <span data-ttu-id="33dc5-169">**사용자 지정 모델** 페이지에서 이전에 만든 워크플로 옆의 **작업** 열에서 세로 줄임표를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="33dc5-170">**실행** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-170">Select **Run**.</span></span>

<span data-ttu-id="33dc5-171">워크플로는 예약된 새로 고침마다 자동으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-171">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="33dc5-172">[예약된 새로 고침 설정](system.md#schedule-tab)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="33dc5-172">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="33dc5-173">워크플로 삭제</span><span class="sxs-lookup"><span data-stu-id="33dc5-173">Delete a workflow</span></span>

1. <span data-ttu-id="33dc5-174">**사용자 지정 모델** 페이지에서 이전에 만든 워크플로 옆의 **작업** 열에서 세로 줄임표를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-174">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="33dc5-175">**삭제** 를 선택하고 삭제를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-175">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="33dc5-176">워크플로가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-176">Your workflow will be deleted.</span></span> <span data-ttu-id="33dc5-177">워크플로를 만들 때 생성된 [엔터티](entities.md)이며 **엔터티** 페이지에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-177">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>

## <a name="results"></a><span data-ttu-id="33dc5-178">결과</span><span class="sxs-lookup"><span data-stu-id="33dc5-178">Results</span></span>

<span data-ttu-id="33dc5-179">워크플로의 결과는 모델 출력 매개 변수 단계에서 구성된 엔티티에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-179">Results from a workflow are stored in the entity configured during the Model Output Parameter phase.</span></span> <span data-ttu-id="33dc5-180">이 데이터는 [엔티티 페이지](entities.md) 또는 [API 액세스](apis.md)에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-180">You can access this data from the [entities page](entities.md) or with [API access](apis.md).</span></span>

### <a name="api-access"></a><span data-ttu-id="33dc5-181">API 액세스</span><span class="sxs-lookup"><span data-stu-id="33dc5-181">API Access</span></span>

<span data-ttu-id="33dc5-182">사용자 지정 모델 엔터티에서 데이터를 가져 오는 특정 OData 쿼리의 경우 다음 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-182">For the specific OData query to get data from a custom model entity, use the following format:</span></span>

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. <span data-ttu-id="33dc5-183">`<your instance id>`(을)를 Customer Insights에 액세스할 때 브라우저의 주소 표시줄에서 찾을 수 있는 Customer Insights 환경의 ID로 교체합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-183">Replace `<your instance id>` with the ID of your Customer Insights environment, which you find in the in the address bar of your browser when accessing Customer Insights.</span></span>

1. <span data-ttu-id="33dc5-184">`<custom model output entity>`(을)를 사용자 지정 모델 구성의 모델 출력 매개 변수 단계에서 제공한 엔터티 이름으로 교체합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-184">Replace `<custom model output entity>` with the entity name you provided during the Model Output Parameters step of the custom model configuration.</span></span>

1. <span data-ttu-id="33dc5-185">`<guid value>`(을)를 레코드에 액세스하려는 고객의 고객 ID로 교체합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-185">Replace `<guid value>` with the Customer ID of the customer you'd like to access the record for.</span></span> <span data-ttu-id="33dc5-186">일반적으로 이 ID는 CustomerID 필드의 [고객 프로필 페이지](customer-profiles.md)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-186">You can usually find this ID on the [customer profiles page](customer-profiles.md) in the CustomerID field.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="33dc5-187">질문과 대답</span><span class="sxs-lookup"><span data-stu-id="33dc5-187">Frequently Asked Questions</span></span>

- <span data-ttu-id="33dc5-188">사용자 지정 모델 워크플로를 설정할 때 파이프라인을 볼 수 없는 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="33dc5-188">Why can't I see my pipeline when setting up a custom model workflow?</span></span>    
  <span data-ttu-id="33dc5-189">이 문제는 파이프라인의 구성 문제로 인해 자주 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-189">This issue is frequently caused by a configuration issue in the pipeline.</span></span> <span data-ttu-id="33dc5-190">[입력 매개 변수가 구성](azure-machine-learning-experiments.md#dataset-configuration)되고 [출력 데이터 저장소 및 경로 매개 변수](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) 또한 구성되도록 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="33dc5-190">Ensure the [input parameter is configured](azure-machine-learning-experiments.md#dataset-configuration), and the [output datastore and path parameters](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) are also configured.</span></span>

- <span data-ttu-id="33dc5-191">"인텔리전스 워크플로를 저장할 수 없음"라는 오류는 무엇을 의미합니까?</span><span class="sxs-lookup"><span data-stu-id="33dc5-191">What does the error "Couldn't save intelligence workflow" mean?</span></span>    
  <span data-ttu-id="33dc5-192">작업 영역에 대한 담당자 또는 사용자 액세스 관리자 권한이 없는 경우 일반적으로 이 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-192">Users usually see this error message if they don't have Owner or User Access Administrator privileges on the workspace.</span></span> <span data-ttu-id="33dc5-193">사용자는 후속 워크플로 실행에 사용자 자격 증명을 사용하는 대신 Customer Insights에서 워크 플로를 서비스로 처리할 수 있도록 더 높은 수준의 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="33dc5-193">The user needs a higher level of permissions to enable Customer Insights to process the workflow as a service rather than using the user credentials for subsequent runs of the workflow.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
