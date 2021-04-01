---
title: 제품 추천 예측
description: 고객이 구매하거나 상호 작용할 가능성이 있는 제품을 예측합니다.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 5ae78b6bbc51fd8a25bc408050a23479698a1414
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598071"
---
# <a name="product-recommendation-prediction-preview"></a><span data-ttu-id="1065f-103">제품 추천 예측(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="1065f-103">Product recommendation prediction (preview)</span></span>

<span data-ttu-id="1065f-104">제품 추천 모델은 예측 제품 추천 세트를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-104">The product recommendation model creates sets of predictive product recommendations.</span></span> <span data-ttu-id="1065f-105">추천은 이전 구매 행동과 유사한 구매 패턴을 가진 고객을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-105">Recommendations are based on previous purchase behavior and customers with similar purchase patterns.</span></span> <span data-ttu-id="1065f-106">**인텔리전스** > **예측** 페이지에서 새 제품 추천 예측을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-106">You can create new product recommendation predictions on the **Intelligence** > **Predictions** page.</span></span> <span data-ttu-id="1065f-107">**내 예측** 을 선택하여 내가 만든 다른 예측을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-107">Select **My predictions** to see other predictions that you've created.</span></span>

<span data-ttu-id="1065f-108">제품 추천은 모델이 특별히 고려하도록 구축되지 않은 고객 기대치뿐만 아니라 현지 법률 및 규정의 적용을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-108">Product recommendations may be subject to local laws and regulations as well as customer expectations, which the model is not built to specifically take into account.</span></span>  <span data-ttu-id="1065f-109">이 예측 기능의 사용자로서 **고객에게 제공하기 전에 추천을 검토** 하여 관련 법률이나 규정뿐 아니라 추천에 대한 고객 기대치를 준수하고 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-109">As a user of this predictive capability, **you must review the recommendations prior to delivering them to your customers** to ensure you are complying with any applicable laws or regulations, as well as customer expectations for what you may recommend.</span></span> 

<span data-ttu-id="1065f-110">또한 이 모델의 출력은 제품 ID를 기반으로한 추천을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-110">Additionally, the output of this model will give you recommendations based on the product ID.</span></span> <span data-ttu-id="1065f-111">전달 메커니즘은 예측된 제품 ID를 가져와 지역화, 이미지 콘텐츠 및 기타 비즈니스 특정 콘텐츠 또는 행동을 고객이 고려할 수 있도록 적절한 콘텐츠에 매핑해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-111">Your delivery mechanism will need to take predicted product IDs and map them to appropriate content for your customers to account for localization, image content, and other business specific content or behavior.</span></span>

## <a name="sample-guide"></a><span data-ttu-id="1065f-112">샘플 가이드</span><span class="sxs-lookup"><span data-stu-id="1065f-112">Sample Guide</span></span>

<span data-ttu-id="1065f-113">이 기능에 관심이 있지만 아래 요구 사항을 완료할 데이터가 없는 경우 [샘플 실행 만들기](sample-guide-predict-product-recommendation.md)를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-113">If you're interested in trying this feature but don't have data to complete the requirements below, you can [create a sample implementation](sample-guide-predict-product-recommendation.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1065f-114">필요한 항목</span><span class="sxs-lookup"><span data-stu-id="1065f-114">Prerequisites</span></span>

- <span data-ttu-id="1065f-115">Customer Insights에 최소한 [기여자 권한](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="1065f-115">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="1065f-116">비즈니스를 위한 다양한 유형의 제품과 고객이 해당 제품과 상호 작용하는 방식을 이해하는 비즈니스 지식입니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-116">Business knowledge to understand different types of products for your business and how your customers interact with them.</span></span> <span data-ttu-id="1065f-117">고객이 이전에 구매한 제품 또는 신제품에 대한 추천을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-117">We support recommending products that have been previously purchased by your customers or recommendations for new products.</span></span>
- <span data-ttu-id="1065f-118">트랜잭션, 구매 및 그 기록에 대한 데이터:</span><span class="sxs-lookup"><span data-stu-id="1065f-118">Data about transactions, purchases, and their history:</span></span>
    - <span data-ttu-id="1065f-119">구매 또는 트랜잭션을 구별하기 위한 트랜잭션 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-119">Transaction identifiers to distinguish purchases or transactions.</span></span>
    - <span data-ttu-id="1065f-120">트랜잭션을 고객에게 매핑하는 고객 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-120">Customer identifiers to map transactions to your customers.</span></span>
    - <span data-ttu-id="1065f-121">트랜잭션이 발생한 날짜를 지정하는 트랜잭션 이벤트 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-121">Transaction event dates that specify dates the transaction occurred on.</span></span>
    - <span data-ttu-id="1065f-122">(선택 사항) 트랜잭션에 대한 제품 ID 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-122">(Optional) Product ID information for the transaction.</span></span>
    - <span data-ttu-id="1065f-123">(선택 사항) 트랜잭션이 반품인지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-123">(Optional) If a transaction is a return or not.</span></span>
    - <span data-ttu-id="1065f-124">의미론적 데이터 스키마에는 다음 정보가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-124">The semantic data schema requires the following information:</span></span>
        - <span data-ttu-id="1065f-125">**거래 ID:** 구매 또는 거래의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-125">**Transaction ID:** A unique identifier of a purchase or transaction.</span></span>
        - <span data-ttu-id="1065f-126">**트랜잭션 날짜:** 구매 또는 트랜잭션 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-126">**Transaction date:** The date the of the purchase or transaction.</span></span>
        - <span data-ttu-id="1065f-127">**트랜잭션 가치:** 구매 또는 트랜잭션의 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-127">**Value of the transaction:** The numerical value of the purchase or transaction.</span></span>
        - <span data-ttu-id="1065f-128">**고유 제품 ID:** 데이터가 항목 수준에 있는 경우 구매한 제품 또는 서비스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-128">**Unique product ID:** The ID of the product or service purchased if your data is at a line item level.</span></span>
        - <span data-ttu-id="1065f-129">(선택 항목) **구매 또는 반품:** 트랜잭션이 반품인지 여부를 식별하는 참/거짓 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-129">(Optional) **Purchase or return:** A true/false field that identifies if the transaction was a return or not.</span></span> <span data-ttu-id="1065f-130">**거래 가치** 가 음수이면 이 정보를 사용하여 수익을 추론합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-130">If the **Value of the transaction** is negative, we will also use this information to infer a return.</span></span>


## <a name="create-a-product-recommendation-prediction"></a><span data-ttu-id="1065f-131">제품 추천 예측 만들기</span><span class="sxs-lookup"><span data-stu-id="1065f-131">Create a product recommendation prediction</span></span>

1. <span data-ttu-id="1065f-132">Customer Insights에서 **인텔리전스** > **예측** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-132">In Customer Insights, go to **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="1065f-133">**제품 추천 모델(미리 보기)** 타일을 선택하고 **이 모델 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-133">Select the **Product recommendations model (preview)** tile and select **Use this model**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1065f-134">![이 모델 사용 버튼이 있는 제품 추천 모델 타일](media/product-recommendation-usethismodel.PNG "이 모델 사용 버튼이 있는 제품 추천 모델 타일")</span><span class="sxs-lookup"><span data-stu-id="1065f-134">![Product Recommendation model tile with Use this model button](media/product-recommendation-usethismodel.PNG "Product Recommendation model tile with Use this model button")</span></span>

1. <span data-ttu-id="1065f-135">모델 요구 사항에 대한 정보를 검토하십시오.</span><span class="sxs-lookup"><span data-stu-id="1065f-135">Review the information about the model requirements.</span></span> <span data-ttu-id="1065f-136">필요한 데이터가 있는 경우, **시작하기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-136">If you have the required data, select **Get started**.</span></span>

### <a name="name-model"></a><span data-ttu-id="1065f-137">모델에 이름 붙이기</span><span class="sxs-lookup"><span data-stu-id="1065f-137">Name model</span></span>

1. <span data-ttu-id="1065f-138">다른 모델과 구별할 수 있도록 모델 이름을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-138">Provide a name for the model to distinguish it from other models.</span></span>

1. <span data-ttu-id="1065f-139">공백 없이 문자와 숫자만 사용하여 출력 엔터티의 이름을 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="1065f-139">Enter a name for the output entity using letters and numbers only, without any spaces.</span></span> <span data-ttu-id="1065f-140">이것이 모델 엔터티가 사용할 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-140">That's the name that the model entity will use.</span></span> <span data-ttu-id="1065f-141">그런 후에 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-141">Then, select **Next**.</span></span>

### <a name="define-product-recommendation-configuration"></a><span data-ttu-id="1065f-142">제품 추천 구성 정의</span><span class="sxs-lookup"><span data-stu-id="1065f-142">Define product recommendation configuration</span></span>

1. <span data-ttu-id="1065f-143">고객에게 추천하고자 하는 **제품 수** 를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-143">Set the **Number of products** you want to recommend to a customer.</span></span> <span data-ttu-id="1065f-144">이 값은 전달 방법이 데이터를 채우는 방식에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-144">This value depends on how your delivery method fills data.</span></span> <span data-ttu-id="1065f-145">세 가지 제품을 추천할 수 있다면 그에 따라 이 값을 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="1065f-145">If you can recommend three products, set this value accordingly.</span></span>
   
   >[!TIP]
   > <span data-ttu-id="1065f-146">언제든지 **저장 후 닫기** 를 선택하여 예측을 초안으로 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-146">You can select **Save and close** at any time to save the prediction as a draft.</span></span> <span data-ttu-id="1065f-147">**내 예측** 탭에서 예측 초안을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-147">You'll find the draft prediction in the **My predictions** tab.</span></span>

1. <span data-ttu-id="1065f-148">**고객이 최근에 구매한 제품을 제안** 하려면 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-148">Choose if you want to **Suggest products customers have recently purchased**.</span></span>

1. <span data-ttu-id="1065f-149">최근 구매한 제품을 추천하지 *않음* 을 선택한 경우 **과거 내역 보기 창** 을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-149">If you've selected to *not* recommend recently purchased products, set the **Look back window**.</span></span> <span data-ttu-id="1065f-150">이 설정은 사용자에게 제품을 다시 추천하기 전에 모델이 고려하는 시간 프레임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-150">This setting specifies the time frame the model considers before recommending the product to the user again.</span></span> <span data-ttu-id="1065f-151">예를 들어, 고객이 2년마다 노트북을 구입한다고 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-151">For example, indicate a customer purchases a laptop every 2 years.</span></span> <span data-ttu-id="1065f-152">이 창에서는 지난 2년 동안의 구매 기록을 확인하고 항목을 찾으면 해당 항목이 추천에서 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-152">This window will look at the purchase history for the last 2 years, and if they find an item, the item will be filtered from the recommendations.</span></span>

1. <span data-ttu-id="1065f-153">**다음** 선택</span><span class="sxs-lookup"><span data-stu-id="1065f-153">Select **Next**</span></span>

### <a name="add-required-data"></a><span data-ttu-id="1065f-154">필수 데이터 추가</span><span class="sxs-lookup"><span data-stu-id="1065f-154">Add required data</span></span>

1. <span data-ttu-id="1065f-155">**고객 트랜잭션 기록** 에 대한 **데이터 추가** 를 선택하고 [필수 구성 요소](#prerequisites)에 설명된 대로 트랜잭션/구매 기록 정보를 제공하는 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-155">Select **Add data** for **Customer transaction history** and choose the entity that provides the transaction/purchase history information as described in the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="1065f-156">의미론적 필드를 구매 기록 엔터티 내의 특성에 매핑하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-156">Map the semantic fields to attributes within your purchase history entity and select **Next**.</span></span> <span data-ttu-id="1065f-157">필드에 대한 설명은 [필수 구성 요소](#prerequisites)를 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="1065f-157">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1065f-158">![엔터티 관계 정의](media/product-recommendation-purchasehistorymapping.PNG "선택한 구매 기록 엔터티의 필드에 매핑되는 의미론적 특성을 보여주는 구매 기록 페이지")</span><span class="sxs-lookup"><span data-stu-id="1065f-158">![Define the entity relationship](media/product-recommendation-purchasehistorymapping.PNG "Purchase history page showing semantic attributes that are mapped to fields in the selected purchase history entity")</span></span>

1. <span data-ttu-id="1065f-159">필드가 채워지지 않은 경우 구매 기록 엔터티에서 *고객* 엔터티로의 관계를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-159">If the fields aren't filled in, configure the relationship from your purchase history entity to the *Customer* entity.</span></span>
    1. <span data-ttu-id="1065f-160">**구매 기록 엔터티** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-160">Select the **Purchase history entity**.</span></span>
    1. <span data-ttu-id="1065f-161">구매 기록 엔터티에서 고객을 식별하는 **필드** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-161">Select the **Field** that identifies the customer in the purchase history entity.</span></span> <span data-ttu-id="1065f-162">*고객* 엔터티의 기본 고객 ID와 관련되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-162">It needs to relate to the primary customer ID of your *Customer* entity.</span></span>
    1. <span data-ttu-id="1065f-163">기본 고객 엔터티와 일치하는 **고객 엔터티** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-163">Select the **Customer entity** that matches your primary customer entity.</span></span>
    1. <span data-ttu-id="1065f-164">관계를 설명하는 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-164">Enter a name that describes the relationship.</span></span>
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="1065f-165">![고객과의 관계 생성을 보여주는 구매 기록 페이지](media/model-purchase-join.png "고객과의 관계 생성을 보여주는 구매 기록 페이지")</span><span class="sxs-lookup"><span data-stu-id="1065f-165">![Purchase history page showing the creation of a relationship to customer](media/model-purchase-join.png "Purchase history page showing the creation of a relationship to customer")</span></span>

1. <span data-ttu-id="1065f-166">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-166">Select **Save**.</span></span>

1. <span data-ttu-id="1065f-167">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-167">Select **Next**.</span></span>

### <a name="set-schedule-and-review-configuration"></a><span data-ttu-id="1065f-168">일정 설정 및 구성 검토</span><span class="sxs-lookup"><span data-stu-id="1065f-168">Set schedule and review configuration</span></span>

1. <span data-ttu-id="1065f-169">모델을 재교육할 빈도를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-169">Set a frequency to retrain your model.</span></span> <span data-ttu-id="1065f-170">이 설정은 새 데이터를 Customer Insights로 가져올 때 예측 정확도를 업데이트하는 데 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-170">This setting is important to update the accuracy of predictions as new data is imported into Customer Insights.</span></span> <span data-ttu-id="1065f-171">대부분의 비즈니스는 한 달에 한 번 재교육을 받고 예측의 정확도를 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-171">Most businesses can retrain once per month and get a good accuracy for their prediction.</span></span>

1. <span data-ttu-id="1065f-172">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-172">Select **Next**.</span></span>

1. <span data-ttu-id="1065f-173">구성을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-173">Review the configuration.</span></span> <span data-ttu-id="1065f-174">표시된 값 아래에서 **편집** 을 선택하여 예측 구성의 일부로 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-174">You can go back to any part of the prediction configuration by selecting **Edit** under the shown value.</span></span> <span data-ttu-id="1065f-175">또는 진행률 표시기에서 구성 단계를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-175">Or you can select a configuration step from the progress indicator.</span></span>

1. <span data-ttu-id="1065f-176">모든 값이 올바르게 구성된 경우 **저장 후 실행** 을 선택하여 예측 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-176">If all values are configured correctly, select **Save and run** to begin the prediction process.</span></span> <span data-ttu-id="1065f-177">**내 예측** 탭에서 예측 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-177">On the **My predictions** tab, you can see the status of your predictions.</span></span> <span data-ttu-id="1065f-178">예측에 사용된 데이터 양에 따라 프로세스를 완료하는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-178">The process may take several hours to complete depending on the amount of data used in the prediction.</span></span>

## <a name="review-a-prediction-status-and-results"></a><span data-ttu-id="1065f-179">예측 상태 및 결과 검토</span><span class="sxs-lookup"><span data-stu-id="1065f-179">Review a prediction status and results</span></span>

1. <span data-ttu-id="1065f-180">**인텔리전스** > **예측** 에서 **내 예측** 탭으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-180">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1065f-181">![내 예측 페이지 보기](media/product-recommendation-mypredictions.PNG "내 예측 페이지 보기")</span><span class="sxs-lookup"><span data-stu-id="1065f-181">![View of the My Predictions page](media/product-recommendation-mypredictions.PNG "View of the My Predictions page")</span></span>

1. <span data-ttu-id="1065f-182">검토하려는 예측을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-182">Select the prediction you want to review.</span></span>
   - <span data-ttu-id="1065f-183">**예측 이름:** 생성할 때 제공한 예측의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-183">**Prediction name:** The name of the prediction provided when creating it.</span></span>
   - <span data-ttu-id="1065f-184">**예측 유형:** 예측에 사용된 모델 유형</span><span class="sxs-lookup"><span data-stu-id="1065f-184">**Prediction type:** The type of model used for the prediction</span></span>
   - <span data-ttu-id="1065f-185">**출력 엔터티:** 예측의 출력을 저장할 엔터티 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-185">**Output entity:** Name of the entity to store the output of the prediction.</span></span> <span data-ttu-id="1065f-186">**데이터** > **엔터티** 에서 이 이름을 가진 엔터티를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-186">You can find an entity with this name on **Data** > **Entities**.</span></span>
   - <span data-ttu-id="1065f-187">**예측 필드:** 이 필드는 일부 예측 유형에 대해서만 채워지며 이탈 예측에서는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-187">**Predicted field:** This field is populated only for some types of predictions, and isn't used in churn prediction.</span></span>
   - <span data-ttu-id="1065f-188">**상태:** 예측 실행의 현재 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-188">**Status:** The current status of the prediction's run.</span></span>
        - <span data-ttu-id="1065f-189">**큐에 대기 중:** 예측이 현재 다른 프로세스가 실행되기를 기다리고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-189">**Queued:** The prediction is currently waiting for other processes to run.</span></span>
        - <span data-ttu-id="1065f-190">**새로 고침:** 예측이 현재 출력 엔터티로 흐르는 결과를 생성하기 위해 처리의 "점수" 단계를 실행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-190">**Refreshing:** The prediction is currently running the "score" stage of processing to produce results that will flow into the output entity.</span></span>
        - <span data-ttu-id="1065f-191">**실패:** 예측이 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-191">**Failed:** the prediction has failed.</span></span> <span data-ttu-id="1065f-192">자세한 내용은 **로그** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-192">Select **Logs** for more details.</span></span>
        - <span data-ttu-id="1065f-193">**성공:** 예측이 성공했습니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-193">**Succeeded:** the prediction has succeeded.</span></span> <span data-ttu-id="1065f-194">세로 줄임표 아래에서 **보기** 를 선택하여 예측을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-194">Select **View** under the vertical ellipses to review the prediction</span></span>
   - <span data-ttu-id="1065f-195">**편집됨:** 예측의 구성이 변경된 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-195">**Edited:** The date the configuration for the prediction was changed.</span></span>
   - <span data-ttu-id="1065f-196">**마지막 새로 고침:** 출력 엔터티에서 예측을 새로 고친 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-196">**Last refreshed:** The date the prediction refreshed results in the output entity.</span></span>

1. <span data-ttu-id="1065f-197">결과를 검토하려는 예측 옆에 있는 세로 줄임표를 선택하고 **보기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-197">Select the vertical ellipses next to the prediction you want to review results for and select **View**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1065f-198">![편집, 새로 고침, 보기, 로그 및 삭제를 포함하여 예측에 대한 세로 줄임표 메뉴의 옵션 보기](media/product-recommendation-verticalellipses.PNG "편집, 새로 고침, 보기, 로그 및 삭제를 포함하여 예측에 대한 세로 줄임표 메뉴의 옵션 보기")</span><span class="sxs-lookup"><span data-stu-id="1065f-198">![View of options in the vertical ellipses menu for a prediction including edit, refresh, view, logs, and delete](media/product-recommendation-verticalellipses.PNG "View of options in the vertical ellipses menu for a prediction including edit, refresh, view, logs, and delete")</span></span>

1. <span data-ttu-id="1065f-199">결과 페이지에는 세 가지 기본 데이터 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-199">There are three primary sections of data within the results page:</span></span>
    1. <span data-ttu-id="1065f-200">**교육 모델 성능:** A, B 또는 C가 가능한 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-200">**Training model performance:** A, B, or C are possible scores.</span></span> <span data-ttu-id="1065f-201">이 점수는 예측의 성능을 나타내며 출력 엔터티에 저장된 결과를 사용하도록 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-201">This score indicates the performance of the prediction, and can help you make the decision to use the results stored in the output entity.</span></span>
        - <span data-ttu-id="1065f-202">점수는 다음 규칙에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-202">Scores are determined based on the following rules:</span></span>
            - <span data-ttu-id="1065f-203">**A** "Success @ K" 메트릭이 기준보다 10%를 초과할 경우 모델은 **A** 품질로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-203">**A** The model will be considered **A** quality if the "Success @ K" metric is at least 10% more the baseline.</span></span> 
            - <span data-ttu-id="1065f-204">**B** "Success @ K" 메트릭이 기준보다 0~10% 많은 경우 모델은 **B** 품질로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-204">**B** The model will be considered **B** quality if the "Success @ K" metric is 0 to 10% more than the baseline.</span></span>
            - <span data-ttu-id="1065f-205">**C** "Success @ K" 메트릭이 기준보다 적은 경우 모델은 **C** 품질로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-205">**C** The model will be considered **C** quality if the "Success @ K" metric is less than than the baseline.</span></span>
               
               > [!div class="mx-imgBorder"]
               > <span data-ttu-id="1065f-206">![모델 성능 결과 보기](media/product-recommendation-modelperformance.PNG "모델 성능 결과 보기")</span><span class="sxs-lookup"><span data-stu-id="1065f-206">![View of the model performance result](media/product-recommendation-modelperformance.PNG "View of the model performance result")</span></span>
            - <span data-ttu-id="1065f-207">**기준**: 모델은 모든 고객의 구매 횟수별로 가장 많이 권장되는 제품을 선택하고 모델에서 식별한 학습된 규칙을 사용하여 고객을 위한 추천 세트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-207">**Baseline**: The model takes the top most recommended products by purchase count across all customers, and uses learned rules identified by the model to create a set of recommendations for the customers.</span></span> <span data-ttu-id="1065f-208">그런 다음 제품을 구매한 고객의 수로 계산하여 상위 제품과 예측을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-208">The predictions are then compared to the top products, as calculated by the number of customers that had purchased the product.</span></span> <span data-ttu-id="1065f-209">가장 많이 구매한 제품에도 표시되는 추천 제품의 제품을 고객이 하나 이상 보유한 경우 기준의 일부로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-209">If a customer has at least one product in their recommended products that was also seen in the top purchased products, they're considered a part of the baseline.</span></span> <span data-ttu-id="1065f-210">총 고객 100명 중 추천 제품을 구매한 고객이 10명이라면 기준은 10%가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-210">If there were 10 of these customers that had a recommended product purchased out of 100 total customers, the baseline would be 10%.</span></span>
            - <span data-ttu-id="1065f-211">**Success @ K**: 트랜잭션 기간의 유효성 검사 세트를 사용하여 모든 고객에 대한 추천을 생성하고 트랜잭션 유효성 검사 세트와 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-211">**Success @ K**: Using a validation set of time period of transactions, recommendations are created for all customers and compared against the validation set of transactions.</span></span> <span data-ttu-id="1065f-212">예를 들어 12개월 기간에서, 12개월은 데이터 유효성 검사 세트로 따로 설정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-212">For example, in a 12 month period, month 12 might be set aside as a validation set of data.</span></span> <span data-ttu-id="1065f-213">모델이 지난 11개월 동안 학습한 내용을 기반으로 12개월에 구매할 제품을 하나 이상 예측하는 경우 고객은 "Success @ K" 메트릭을 늘릴 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-213">If the model predicts at least one thing you would purchase in month 12 based on what it learned from the previous 11 months, the customer would increase the "Success @ K" metric.</span></span>
    
    1. <span data-ttu-id="1065f-214">**가장 많이 제안된 제품(누적 기록 포함):** 고객에 대해 예측된 상위 5개 제품입니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-214">**Most suggested products (with tally):** The top 5 products that were predicted for your customers.</span></span>
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="1065f-215">![가장 추천하는 상위 5개 제품을 보여주는 그래프](media/product-recommendation-topproducts.PNG "가장 추천하는 상위 5개 제품을 보여주는 그래프")</span><span class="sxs-lookup"><span data-stu-id="1065f-215">![Graph showing the top 5 most recommended products](media/product-recommendation-topproducts.PNG "Graph showing the top 5 most recommended products")</span></span>
    
    1. <span data-ttu-id="1065f-216">**신뢰도가 높은 제품 추천 항목:** 모델이 고객이 구매할 가능성이 있다고 판단하여 고객에게 제공된 추천 항목 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-216">**High-confidence product recommendations:** A sample of recommendations provided to your customers that the model believes are likely to be purchased by the customer.</span></span>
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="1065f-217">![선별된 개별 고객에 대한 높은 신뢰도 제안을 보여주는 목록](media/product-recommendation-highconfidence.PNG "선별된 개별 고객에 대한 높은 신뢰도 제안을 보여주는 목록")</span><span class="sxs-lookup"><span data-stu-id="1065f-217">![List showing high confidence suggestions for a select set of individual customers](media/product-recommendation-highconfidence.PNG "List showing high confidence suggestions for a select set of individual customers")</span></span>

## <a name="fix-a-failed-prediction"></a><span data-ttu-id="1065f-218">실패한 예측 수정</span><span class="sxs-lookup"><span data-stu-id="1065f-218">Fix a failed prediction</span></span>

1. <span data-ttu-id="1065f-219">**인텔리전스** > **예측** 에서 **내 예측** 탭으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-219">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="1065f-220">오류 로그를 보려는 예측을 선택하고 **로그** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-220">Select the prediction you would like to view error logs for and select **Logs**.</span></span>

1. <span data-ttu-id="1065f-221">모든 오류를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-221">Review all the errors.</span></span> <span data-ttu-id="1065f-222">발생할 수 있는 여러 유형의 오류가 있으며 오류를 일으킨 조건을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-222">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="1065f-223">예를 들어 정확하게 예측하기에 데이터가 충분하지 않은 오류는 일반적으로 추가 데이터를 Customer Insights에 로드하여 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-223">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="1065f-224">예측 새로 고침</span><span class="sxs-lookup"><span data-stu-id="1065f-224">Refresh a prediction</span></span>

<span data-ttu-id="1065f-225">예측은 설정에 구성된 것과 동일한 [데이터 새로 고침 예약](system.md#schedule-tab)에서 자동으로 새로 고쳐집니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-225">Predictions automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span>

1. <span data-ttu-id="1065f-226">**인텔리전스** > **예측** 에서 **내 예측** 탭으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-226">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="1065f-227">새로 고치려는 예측 옆의 세로 줄임표를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-227">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="1065f-228">**새로 고침** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-228">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="1065f-229">예측 삭제</span><span class="sxs-lookup"><span data-stu-id="1065f-229">Delete a prediction</span></span>

<span data-ttu-id="1065f-230">예측을 삭제하면 출력 엔터티도 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-230">Deleting a prediction will also remove its output entity.</span></span>

1. <span data-ttu-id="1065f-231">**인텔리전스** > **예측** 에서 **내 예측** 탭으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-231">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="1065f-232">삭제하려는 예측 옆의 세로 줄임표를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-232">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="1065f-233">**삭제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1065f-233">Select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]