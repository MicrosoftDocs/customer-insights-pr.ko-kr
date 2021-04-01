---
title: 예측을 사용하여 부분 데이터 완료
description: 예측을 사용하여 불완전한 고객 데이터를 채웁니다.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3342328b9eead9bdcb8b41f119a1d0a5823001c8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595909"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="9e35e-103">예측으로 부분 데이터 완성</span><span class="sxs-lookup"><span data-stu-id="9e35e-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="9e35e-104">예측을 통해 고객에 대한 이해를 높일 수 있는 예측 값을 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="9e35e-105">**인텔리전스** > **예측** 페이지에서 **내 예측** 을 선택하여 대상 그룹 인사이트의 다른 부분에서 구성한 예측을 보고 추가로 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="9e35e-106">환경에서 Azure Data Lake Gen 2 저장소를 사용하는 경우 이 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="9e35e-107">예측 기능은 자동화된 수단을 사용하여 데이터를 평가하고 해당 데이터를 기반으로 예측을 수행하므로 일반 데이터 보호 규정("GDPR")에 의해 정의된 대로 프로파일링 방법으로 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="9e35e-108">고객이 데이터를 처리하기 위해 이 기능을 사용하는 경우 GDPR 또는 기타 법률 또는 규정이 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="9e35e-109">귀하는 예측을 포함한 Dynamics 365 Customer Insights 사용이 개인 정보 보호, 개인 데이터, 생체 인식 데이터, 데이터 보호 및 통신 기밀과 관련된 법률을 포함하여 모든 관련 법률 및 규정을 준수하는지 확인할 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9e35e-110">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="9e35e-110">Prerequisites</span></span>

<span data-ttu-id="9e35e-111">조직에서 예측 기능을 사용하기 전에 다음 전제 조건이 충족되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="9e35e-112">조직에 [Common Data Service에 설정된](/ai-builder/build-model#prerequisites) 인스턴스가 있으며 Customer Insights와 동일한 조직에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-112">Your organization has an instance [set up in the Common Data Service](/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="9e35e-113">환경이 Common Data Service 인스턴스에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="9e35e-114">[새 환경을 만드는](manage-environments.md) 경우 **환경 만들기** 대화 상자에서 환경을 구성하고 **고급** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="9e35e-115">이미 환경을 만든 경우 해당 설정으로 이동하여 **고급** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="9e35e-116">어느 쪽이든 **예측 사용** 섹션에서 환경을 연결하려는 Common Data Service 인스턴스 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="9e35e-117">고객 엔터티에서 예측 만들기</span><span class="sxs-lookup"><span data-stu-id="9e35e-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="9e35e-118">대상 그룹 인사이트에서 **데이터** > **엔터티** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="9e35e-119">**고객** 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="9e35e-120">**고객: CustomerInsights** 엔터티에서 **필드** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="9e35e-121">값을 예측하려는 특성 이름을 찾은 다음 **요약** 열에서 **개요** 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9e35e-122">![개요 아이콘](media/intelligence-overviewicon.png "개요 아이콘")</span><span class="sxs-lookup"><span data-stu-id="9e35e-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="9e35e-123">특성에 대해 누락된 값의 비율이 높은 경우 **누락된 값 예측** 을 선택하여 예측을 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9e35e-124">![누락된 값 예측 단추가 표시된 개요 상태](media/intelligence-overviewpredictmissingvalues.png "누락된 값 예측 단추가 표시된 개요 상태")</span><span class="sxs-lookup"><span data-stu-id="9e35e-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="9e35e-125">예측 결과를 위해 **표시 이름** 과 **출력 엔터티 이름** 을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="9e35e-126">미리 채워진 옵션 목록에 값을 예측된 범주에 매핑할 수 있는 위치가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="9e35e-127">이 경우 예측의 참/거짓 또는 이진 특성에 매핑되므로 범주 옵션만 0 또는 1이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="9e35e-128">범주 열에서 최종 예측에서 "0"으로 분류할 필드 값을 "0"으로 매핑하고 최종 예측에서 "1"로 분류할 항목을 "1"로 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9e35e-129">![범주에 매핑된 필드 값을 보여주는 예](media/intelligence-categorymapping.png "범주에 매핑된 필드 값을 보여주는 예")</span><span class="sxs-lookup"><span data-stu-id="9e35e-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="9e35e-130">**완료** 를 선택하면 예측이 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="9e35e-131">데이터의 크기와 복잡성에 따라 처리에 시간이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="9e35e-132">생성한 예측의 **출력 엔터티 이름** 을 기반으로 새 엔터티에서 결과를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="9e35e-133">세그먼트를 만들면서 예측 만들기</span><span class="sxs-lookup"><span data-stu-id="9e35e-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="9e35e-134">세그먼트를 만들 때 선택한 특정 특성에 대한 누락된 값을 예측할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="9e35e-135">특히, 통합 고객 엔터티 또는 Customer_Measure 엔터티를 기반으로 세그먼트를 빠르게 만들 때가 그렇습니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="9e35e-136">이 흐름의 일부로 고객 만족도 또는 구매 금액 등 세그먼트를 기반으로 특정 특성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="9e35e-137">세그먼트 생성 시 시스템은 이 특성에 대한 놓친 값을 예측하는 방법을 제안합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="9e35e-138">대상 그룹 인사이트에서 **세그먼트** 로 이동한 후 **프로필** 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="9e35e-139">**필드** 를 선택하여 세그먼트를 만들고 **운영자** 를 선택한 다음 **검토** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="9e35e-140">세그먼트에 대한 **이름** 및 **표시 이름** 을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="9e35e-141">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-141">Select **Save**.</span></span>

5. <span data-ttu-id="9e35e-142">만든 세그먼트에 소스 필드에 불완전한 데이터가 있는 경우 누락된 값을 예측하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9e35e-143">![예측 단추](media/segments-predictoption.png "예측 단추")</span><span class="sxs-lookup"><span data-stu-id="9e35e-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="9e35e-144">예측 결과를 위해 **표시 이름** 과 **출력 엔터티 이름** 을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="9e35e-145">**완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-145">Select **Done**.</span></span> <span data-ttu-id="9e35e-146">곧 **출력 엔터티 이름** 에 제공한 새로운 엔터티에서 예측이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="9e35e-147">예측 보기</span><span class="sxs-lookup"><span data-stu-id="9e35e-147">View a prediction</span></span>

1. <span data-ttu-id="9e35e-148">대상 그룹 인사이트에서 **인텔리전스** > **예측** > **내 예측** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="9e35e-149">검토하려는 예측을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="9e35e-150">**작업** 열에서 줄임표를 선택하고 **보기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="9e35e-151">예측 보기에 여러 데이터 요소가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9e35e-152">![예측 페이지](media/intelligence-predictionsviewpage.png "예측 페이지")</span><span class="sxs-lookup"><span data-stu-id="9e35e-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="9e35e-153">**예측 가치** 는 필드 값 대 범주 매핑 단계에서 작성한 매핑을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="9e35e-154">이들은 특정 범주에 매핑된 데이터 집합의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="9e35e-155">-**상위 인플루언서** 는 데이터 집합 내에서 특정 범주에 매핑되는 필드 값에 대한 예측의 신뢰도에 영향을 줄 수 있는 요인입니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="9e35e-156">**성능** 은 예측이 수행되는 방식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="9e35e-157">자세한 내용을 보려면 링크를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="9e35e-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="9e35e-158">**미리 보기** 는 0은 불확실하고 1은 확실한 예측 가치의 가능성 또는 신뢰도에서 나온 출력 데이터 집합의 샘플을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="9e35e-159">예측 업데이트</span><span class="sxs-lookup"><span data-stu-id="9e35e-159">Update a prediction</span></span>

1. <span data-ttu-id="9e35e-160">대상 그룹 인사이트에서 **인텔리전스** > **예측** > **내 예측** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="9e35e-161">업데이트할 예측을 선택하고 **업데이트** 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="9e35e-162">예측이 처리 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="9e35e-163">**예측**  페이지의 **업데이트됨** 열에서 마지막으로 업데이트된 시간을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="9e35e-164">예측 편집</span><span class="sxs-lookup"><span data-stu-id="9e35e-164">Edit a prediction</span></span>

<span data-ttu-id="9e35e-165">예측을 만든 후 AI Builder에서 모델을 사용자 지정하여 모델의 효과를 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="9e35e-166">대상 그룹 인사이트에서 **인텔리전스** > **예측** > **내 예측** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="9e35e-167">편집할 예측을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="9e35e-168">**작업** 열에서 줄임표를 선택하고 **보기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="9e35e-169">**AI Builder에서 사용자 지정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="9e35e-170">AI Builder에서 모델을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="9e35e-171">[AI Builder에서 모델 관리에 대해 자세히 알아보십시오](/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="9e35e-171">[Learn more about managing models in the AI builder](/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="9e35e-172">다음 예측에서는 생성한 업데이트된 모델을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="9e35e-173">AI Builder에서 생성된 새 모델은 위에 나열된 경험에서 생성된 모델이 아니면 대상 그룹 인사이트에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="9e35e-174">예측 제거</span><span class="sxs-lookup"><span data-stu-id="9e35e-174">Remove a prediction</span></span>

1. <span data-ttu-id="9e35e-175">대상 그룹 인사이트에서 **인텔리전스** > **예측** > **내 예측** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="9e35e-176">삭제하려는 예측을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="9e35e-177">**작업** 열에서 줄임표를 선택하고 **삭제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="9e35e-178">삭제를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="9e35e-179">문제 해결</span><span class="sxs-lookup"><span data-stu-id="9e35e-179">Troubleshooting</span></span>

<span data-ttu-id="9e35e-180">오류로 인해 Common Data Service 첨부 프로세스를 완료할 수 없는 경우 프로세스를 수동으로 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="9e35e-181">연결 프로세스에서 발생할 수 있는 두 가지 알려진 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="9e35e-182">고객 카드 추가 기능 솔루션이 설치되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="9e35e-183">[솔루션 설치 및 구성](customer-card-add-in.md)에 대한 지침을 완료하십시오.</span><span class="sxs-lookup"><span data-stu-id="9e35e-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="9e35e-184">앱 권한이 부여되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="9e35e-185">[https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="9e35e-186">**환경** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="9e35e-187">권한을 추가하려는 환경 옆의 줄임표를 선택하고 **설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="9e35e-188">**사용자 + 권한** 을 확장하고 **사용자** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="9e35e-189">**+ 새로 만들기** 를 선택하고 **사용자** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="9e35e-190">아직 선택하지 않은 경우 **응용 프로그램 사용자** 를 선택하고 다음 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="9e35e-191">**사용자 이름:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9e35e-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="9e35e-192">**응용 프로그램 ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="9e35e-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="9e35e-193">**고객 이름:** 고객</span><span class="sxs-lookup"><span data-stu-id="9e35e-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="9e35e-194">**성:** 인사이트</span><span class="sxs-lookup"><span data-stu-id="9e35e-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="9e35e-195">**기본 이메일:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9e35e-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="9e35e-196">**저장 후 닫기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="9e35e-197">방금 만든 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="9e35e-198">상단 메뉴 모음에서 **역할 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="9e35e-199">**시스템 관리자** 를 선택한 다음 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e35e-199">Select **System Administrator**, then select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]