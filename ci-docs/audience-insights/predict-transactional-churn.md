---
title: 트랜잭션 이탈 예측
description: 고객이 더 이상 제품이나 서비스를 구매하지 않을 위험에 처해 있는지 예측합니다.
ms.date: 11/12/2020
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f3cbbf99a6cecba2aab2cf85428d53e5df8346e4
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644411"
---
# <a name="transactional-churn-prediction-preview"></a><span data-ttu-id="d1d75-103">트랜잭션 이탈 예측(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="d1d75-103">Transactional churn prediction (preview)</span></span>

<span data-ttu-id="d1d75-104">트랜잭션 이탈 예측은 고객이 주어진 기간 내에 더 이상 제품이나 서비스를 구매하지 않을 것인지 예측하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-104">Transactional churn prediction helps predict if a customer will no longer purchase your products or services in a given time window.</span></span> <span data-ttu-id="d1d75-105">**인텔리전스** > **예측** 에서 새로운 이탈 예측을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-105">You can create new churn predictions on **Intelligence** > **Predictions**.</span></span> <span data-ttu-id="d1d75-106">**내 예측** 을 선택하여 내가 만든 다른 예측을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-106">Select **My predictions** to see other predictions that you've created.</span></span>

> [!TIP]
> <span data-ttu-id="d1d75-107">샘플 데이터를 사용한 트랜잭션 이탈 예측 자습서: [트랜잭션 이탈 예측(미리 보기) 샘플 가이드](sample-guide-predict-transactional-churn.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1d75-107">Try the tutorial for a translactional churn prediction using sample data: [Transactional churn prediction (preview) sample guide](sample-guide-predict-transactional-churn.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d1d75-108">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="d1d75-108">Prerequisites</span></span>

- <span data-ttu-id="d1d75-109">Customer Insights에 최소한 [기여자 권한](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="d1d75-109">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="d1d75-110">이탈이 비즈니스에 미치는 영향을 이해하는 비즈니스 지식.</span><span class="sxs-lookup"><span data-stu-id="d1d75-110">Business knowledge to understand what churn means for your business.</span></span> <span data-ttu-id="d1d75-111">시간 기반 이탈 정의를 지원합니다. 즉, 고객이 구매하지 않은 기간이 지나면 이탈한 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-111">We support time-based churn definitions, meaning a customer is considered to have churned after a period of no purchases.</span></span>
- <span data-ttu-id="d1d75-112">트랜잭션/구매 및 내역에 대한 데이터 :</span><span class="sxs-lookup"><span data-stu-id="d1d75-112">Data about your transactions/purchases and their history:</span></span>
    - <span data-ttu-id="d1d75-113">구매/트랜잭션을 구별하기 위한 거래 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-113">Transaction identifiers to distinguish purchases/transactions.</span></span>
    - <span data-ttu-id="d1d75-114">트랜잭션을 고객과 일치시키는 고객 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-114">Customer identifiers to match transactions to your customers.</span></span>
    - <span data-ttu-id="d1d75-115">트랜잭션이 발생한 날짜를 정의하는 트랜잭션 이벤트 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-115">Transaction event dates, which define the dates the transaction occurred on.</span></span>
    - <span data-ttu-id="d1d75-116">구매/거래 위한 의미론적 데이터 스키마에는 다음 정보가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-116">The semantic data schema for purchases/transactions requires the following information:</span></span>
        - <span data-ttu-id="d1d75-117">**거래 ID:** 구매 또는 거래의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-117">**Transaction ID:** A unique identifier of a purchase or transaction.</span></span>
        - <span data-ttu-id="d1d75-118">**거래 날짜:** 구매 또는 거래 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-118">**Transaction Date:** The date of the purchase or transaction.</span></span>
        - <span data-ttu-id="d1d75-119">**거래 가치:** 거래/항목의 통화/숫자적 가치 금액입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-119">**Value of the transaction:** The currency/numerical value amount of the transaction/item.</span></span>
        - <span data-ttu-id="d1d75-120">(선택 항목) **고유 제품 ID:** 데이터가 항목 수준에 있는 경우 구매한 제품 또는 서비스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-120">(Optional) **Unique product ID:** The ID of the product or service purchased if your data is at a line item level.</span></span>
        - <span data-ttu-id="d1d75-121">(선택 항목) **이 거래가 반품인지 여부:** 거래가 반품인지 여부를 식별하는 참/거짓 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-121">(Optional) **Whether this transaction was a return:** A true/false field that identifies if the transaction was a return or not.</span></span> <span data-ttu-id="d1d75-122">**거래 가치** 가 음수이면 이 정보를 사용하여 수익을 추론합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-122">If the **Value of the transaction** is negative, we will also use this information to infer a return.</span></span>
- <span data-ttu-id="d1d75-123">(선택 항목) 고객 활동에 대한 데이터:</span><span class="sxs-lookup"><span data-stu-id="d1d75-123">(Optional) Data about customer activities:</span></span>
    - <span data-ttu-id="d1d75-124">동일한 유형의 활동을 구별하기위한 활동 식별자.</span><span class="sxs-lookup"><span data-stu-id="d1d75-124">Activity identifiers to distinguish activities of the same type.</span></span>
    - <span data-ttu-id="d1d75-125">고객에 활동을 매핑하는 고객 식별자.</span><span class="sxs-lookup"><span data-stu-id="d1d75-125">Customer identifiers to map activities to your customers.</span></span>
    - <span data-ttu-id="d1d75-126">활동의 이름과 날짜를 포함하는 활동 정보.</span><span class="sxs-lookup"><span data-stu-id="d1d75-126">Activity information containing the name and date of the activity.</span></span>
    - <span data-ttu-id="d1d75-127">고객 활동을 위한 의미 데이터 스키마는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-127">The semantic data schema for customer activities includes:</span></span>
        - <span data-ttu-id="d1d75-128">**기본 키:** 활동의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-128">**Primary key:** A unique identifier for an activity.</span></span> <span data-ttu-id="d1d75-129">예를 들어 웹 사이트 방문 또는 고객이 제품 샘플을 시도했음을 보여주는 사용 기록입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-129">For example, a website visit or a usage record showing the customer tried a sample of your product.</span></span>
        - <span data-ttu-id="d1d75-130">**타임스탬프:** 기본 키로 식별된 이벤트 날짜 및 시간.</span><span class="sxs-lookup"><span data-stu-id="d1d75-130">**Timestamp:** The date and time of the event identified by the primary key.</span></span>
        - <span data-ttu-id="d1d75-131">**이벤트:** 사용하려는 이벤트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-131">**Event:** The name of the event you want to use.</span></span> <span data-ttu-id="d1d75-132">예를 들어 식료품점에서 'UserAction'이라는 필드는 고객이 사용하는 쿠폰일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-132">For example, a field called "UserAction" in a grocery store might be a coupon use by the customer.</span></span>
        - <span data-ttu-id="d1d75-133">**세부 정보:** 이벤트에 대한 자세한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-133">**Details:** Detailed information about the event.</span></span> <span data-ttu-id="d1d75-134">예를 들어 식료품점에서 "CouponValue"라는 필드가 쿠폰의 통화 값일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-134">For example, a field called "CouponValue" in a grocery store might be the currency value of the coupon.</span></span>

## <a name="create-a-transactional-churn-prediction"></a><span data-ttu-id="d1d75-135">트랜잭션 이탈 예측 만들기</span><span class="sxs-lookup"><span data-stu-id="d1d75-135">Create a transactional churn prediction</span></span>

1. <span data-ttu-id="d1d75-136">Customer Insights에서 **인텔리전스** > **예측** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-136">In Customer Insights, go to **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="d1d75-137">**고객 이탈 모델(미리 보기)** 타일을 선택하고 **이 모델 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-137">Select the **Customer churn model (preview)** tile and select **Use this model**.</span></span>
   
1. <span data-ttu-id="d1d75-138">**고객 이탈 모델** 창에서 **거래** 를 선택하고 **시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-138">In the **Customer churn model** pane, choose **Transactional** and select **Get started**.</span></span>

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="고객 이탈 모델 창에서 선택한 트랜잭션 옵션이 있는 스크린샷.":::

### <a name="name-model"></a><span data-ttu-id="d1d75-140">모델에 이름 붙이기</span><span class="sxs-lookup"><span data-stu-id="d1d75-140">Name model</span></span>

1. <span data-ttu-id="d1d75-141">다른 모델과 구별할 수 있도록 모델 이름을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-141">Provide a name for the model to distinguish it from other models.</span></span>

1. <span data-ttu-id="d1d75-142">공백 없이 문자와 숫자만 사용하여 출력 엔터티의 이름을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-142">Provide a name for the output entity using letters and numbers only, without any spaces.</span></span> <span data-ttu-id="d1d75-143">이것이 모델 엔터티가 사용할 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-143">That's the name that the model entity will use.</span></span> 

1. <span data-ttu-id="d1d75-144">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-144">Select **Next**.</span></span>

### <a name="define-customer-churn"></a><span data-ttu-id="d1d75-145">고객 이탈 정의</span><span class="sxs-lookup"><span data-stu-id="d1d75-145">Define customer churn</span></span>

1. <span data-ttu-id="d1d75-146">**다음 필드에서 이탈할 수 있는 고객 식별** 필드에서 이탈을 예측할 기간을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-146">Set a window of days to predict churn for in the **Identify customers who may churn in the next** field.</span></span> <span data-ttu-id="d1d75-147">예를 들어 마케팅 유지 노력에 맞춰 향후 90일 동안 고객의 이탈 위험을 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-147">For example, predict the risk of churn for your customers over the next 90 days to align to your marketing retention efforts.</span></span> <span data-ttu-id="d1d75-148">더 길거나 더 짧은 기간 동안 이탈 위험을 예측하면 이탈 위험 프로필의 요인을 해결하기가 더 어려워질 수 있지만 특정 비즈니스 요구 사항에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-148">Predicting churn risk for a longer or shorter period of time can make it more difficult to address the factors in your churn risk profile, but it depends on your specific business requirements.</span></span> 
   >[!TIP]
   > <span data-ttu-id="d1d75-149">언제든지 **저장 후 닫기** 를 선택하여 예측을 초안으로 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-149">You can select **Save and close** at any time to save the prediction as a draft.</span></span> <span data-ttu-id="d1d75-150">**내 예측** 탭에서 초안 예측을 찾아 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-150">You'll find the draft prediction in the **My predictions** tab to continue.</span></span>

1. <span data-ttu-id="d1d75-151">**고객이 구매한 적이 없는 경우 이탈한 날짜:** 필드에 이탈을 정의할 일수를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-151">Enter the number of days to define churn in the **A customer has churned if they've made no purchases in:** field.</span></span> <span data-ttu-id="d1d75-152">예를 들어 지난 30일 동안 구매한 적이 없는 고객은 비즈니스를 위해 이탈한 것으로 간주될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-152">For example, if a customer has made no purchases in the last 30 days, they might be considered as churned for your business.</span></span> 

1. <span data-ttu-id="d1d75-153">**다음** 을 선택하여 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-153">Select **Next** to continue</span></span>

### <a name="add-required-data"></a><span data-ttu-id="d1d75-154">필수 데이터 추가</span><span class="sxs-lookup"><span data-stu-id="d1d75-154">Add required data</span></span>

1. <span data-ttu-id="d1d75-155">**구매 기록** **데이터 추가** 를 선택하고 [필수 구성 요소](#prerequisites)에 설명된대로 거래/구매 내역 정보를 제공하는 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-155">Select **Add data** for **Purchase history** and choose the entity that provides the transaction/purchase history information as described in the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="d1d75-156">의미론적 필드를 구매 기록 엔터티 내의 특성에 매핑하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-156">Map the semantic fields to attributes within your purchase history entity and select **Next**.</span></span> <span data-ttu-id="d1d75-157">필드에 대한 설명은 [필수 구성 요소](#prerequisites)를 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="d1d75-157">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="구매 엔터티의 의미론적 필드를 매핑합니다.":::

1. <span data-ttu-id="d1d75-159">아래 필드가 채워지지 않은 경우 구매 기록 엔터티에서 고객 엔터티로의 관계를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-159">If the fields below aren't populated, configure the relationship from your purchase history entity to the Customer entity.</span></span>
    1. <span data-ttu-id="d1d75-160">**구매 기록 엔터티** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-160">Select the **Purchase history entity**.</span></span>
    1. <span data-ttu-id="d1d75-161">구매 기록 엔터티에서 고객을 식별하는 **필드** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-161">Select the **Field** that identifies the customer in the purchase history entity.</span></span> <span data-ttu-id="d1d75-162">고객 엔터티의 기본 고객 ID와 관련이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-162">It needs to relate to the primary customer ID of your Customer entity.</span></span>
    1. <span data-ttu-id="d1d75-163">기본 고객 엔터티와 일치하는 **고객 엔터티** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-163">Select the **Customer entity** that matches your primary customer entity.</span></span>
    1. <span data-ttu-id="d1d75-164">관계를 설명하는 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-164">Enter a name that describes the relationship.</span></span>

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="고객과의 관계 생성을 보여주는 구매 기록 페이지.":::
   
1. <span data-ttu-id="d1d75-166">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-166">Select **Next**.</span></span>

1. <span data-ttu-id="d1d75-167">원하는 경우 **고객 활동** 에 대한 **데이터 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-167">Optionally, select **Add data** for **Customer activities**.</span></span> <span data-ttu-id="d1d75-168">필수 구성 요소에 설명된 대로 고객 활동 정보를 제공하는 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-168">Choose the entity that provides the customer activity information as described in the prerequisites.</span></span>

1. <span data-ttu-id="d1d75-169">의미론적 필드를 고객 활동 엔터티 내의 특성에 매핑하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-169">Map the semantic fields to attributes within your customer activity entity and select **Next**.</span></span> <span data-ttu-id="d1d75-170">필드에 대한 설명은 [필수 구성 요소](#prerequisites)를 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="d1d75-170">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="d1d75-171">구성 중인 고객 활동 유형과 일치하는 활동 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-171">Select an activity type that matches to the type of customer activity you're configuring.</span></span> <span data-ttu-id="d1d75-172">**새로 만들기** 를 선택하고 사용 가능한 활동 유형을 선택하거나 새 유형을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-172">Select **Create new** and choose an available activity type or create a new type.</span></span>

1. <span data-ttu-id="d1d75-173">고객 활동 엔터티와 고객 엔터티 간의 관계를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-173">You'll need to configure the relationship from your customer activity entity to the Customer entity.</span></span>
    1. <span data-ttu-id="d1d75-174">고객 활동 테이블에서 고객을 식별하는 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-174">Select the field that identifies the customer in the customer activity table.</span></span> <span data-ttu-id="d1d75-175">고객 엔터티의 기본 고객 ID와 직접 관련될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-175">It can be directly related to the primary customer ID of your Customer entity.</span></span>
    1. <span data-ttu-id="d1d75-176">기본 고객 엔터티와 일치하는 고객 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-176">Select the Customer entity that matches your primary Customer entity</span></span>
    1. <span data-ttu-id="d1d75-177">관계를 설명하는 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-177">Enter a name that describes the relationship.</span></span>

1. <span data-ttu-id="d1d75-178">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-178">Select **Save**.</span></span>

1. <span data-ttu-id="d1d75-179">포함하려는 다른 고객 활동이 있는 경우 위 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-179">If you have any other customer activities you would like to include, repeat the steps above.</span></span>

1. <span data-ttu-id="d1d75-180">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-180">Select **Next**.</span></span>

### <a name="set-schedule-and-review-configuration"></a><span data-ttu-id="d1d75-181">일정 설정 및 구성 검토</span><span class="sxs-lookup"><span data-stu-id="d1d75-181">Set schedule and review configuration</span></span>

1. <span data-ttu-id="d1d75-182">모델을 재교육할 빈도를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-182">Set a frequency to retrain your model.</span></span> <span data-ttu-id="d1d75-183">이 설정은 새 데이터가 수집될 때 예측의 정확성을 업데이트하는 데 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-183">This setting is important to update the accuracy of predictions as new data is ingested.</span></span> <span data-ttu-id="d1d75-184">대부분의 비즈니스는 한 달에 한 번 재교육을 받고 예측의 정확도를 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-184">Most businesses can retrain once per month and get a good accuracy for their prediction.</span></span>

1. <span data-ttu-id="d1d75-185">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-185">Select **Next**.</span></span>

1. <span data-ttu-id="d1d75-186">예측 구성을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-186">Review the configuration of the prediction.</span></span> <span data-ttu-id="d1d75-187">표시된 값 아래에서 **편집** 을 선택하여 이전 단계로 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-187">You can go back to prior steps by selecting **Edit** under the shown value.</span></span> <span data-ttu-id="d1d75-188">또는 진행률 표시기에서 구성 단계를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-188">Or you can select a configuration step from the progress indicator.</span></span>

1. <span data-ttu-id="d1d75-189">모든 값이 올바르게 구성된 경우 **저장 후 실행** 을 선택하여 예측 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-189">If all values are configured correctly, select **Save and run** to begin the prediction process.</span></span> <span data-ttu-id="d1d75-190">**내 예측** 탭에서 예측 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-190">On the **My predictions** tab, you can see the status of your predictions.</span></span> <span data-ttu-id="d1d75-191">예측에 사용된 데이터 양에 따라 프로세스를 완료하는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-191">The process may take several hours to complete depending on the amount of data used in the prediction.</span></span>

## <a name="review-a-prediction-status-and-results"></a><span data-ttu-id="d1d75-192">예측 상태 및 결과 검토</span><span class="sxs-lookup"><span data-stu-id="d1d75-192">Review a prediction status and results</span></span>

1. <span data-ttu-id="d1d75-193">**인텔리전스** > **예측** 으로 이동하고 **내 예측** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-193">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="d1d75-194">검토하려는 예측을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-194">Select the prediction you want to review.</span></span>
   - <span data-ttu-id="d1d75-195">**예측 이름:** 생성 시 제공한 예측의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-195">**Prediction name:** Name of the prediction provided when creating it.</span></span>
   - <span data-ttu-id="d1d75-196">**예측 유형:** 예측에 사용되는 모델 유형</span><span class="sxs-lookup"><span data-stu-id="d1d75-196">**Prediction type:** Type of model used for the prediction</span></span>
   - <span data-ttu-id="d1d75-197">**출력 엔터티:** 예측의 출력을 저장할 엔터티 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-197">**Output entity:** Name of the entity to store the output of the prediction.</span></span> <span data-ttu-id="d1d75-198">**데이터** > **엔터티** 에서 이 이름을 가진 엔터티를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-198">You can find an entity with this name on **Data** > **Entities**.</span></span>
   - <span data-ttu-id="d1d75-199">**예측 필드:** 이 필드는 일부 예측 유형에 대해서만 채워지며 이탈 예측에서는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-199">**Predicted field:** This field is populated only for some types of predictions, and isn't used in churn prediction.</span></span>
   - <span data-ttu-id="d1d75-200">**상태:** 예측 실행 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-200">**Status:** Status of the prediction run.</span></span>
        - <span data-ttu-id="d1d75-201">**대기 중:** 예측은 다른 프로세스가 실행되기를 기다리고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-201">**Queued:** Prediction is waiting for other processes to run.</span></span>
        - <span data-ttu-id="d1d75-202">**새로 고치는 중:** 예측은 현재 출력 엔터티로 유입되는 결과를 생성하기 위해 실행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-202">**Refreshing:** Prediction is currently running to produce results that will flow into the output entity.</span></span>
        - <span data-ttu-id="d1d75-203">**실패:** 예측 실행에 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-203">**Failed:** Prediction run has failed.</span></span> <span data-ttu-id="d1d75-204">자세한 내용은 [로그](#troubleshoot-a-failed-prediction)를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-204">[Review the logs](#troubleshoot-a-failed-prediction) for more details.</span></span>
        - <span data-ttu-id="d1d75-205">**성공:** 예측에 성공했습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-205">**Succeeded:** Prediction has succeeded.</span></span> <span data-ttu-id="d1d75-206">세로 줄임표 아래에서 **보기** 를 선택하여 예측을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-206">Select **View** under the vertical ellipses to review the prediction</span></span>
   - <span data-ttu-id="d1d75-207">**편집됨:** 예측의 구성이 변경된 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-207">**Edited:** The date the configuration for the prediction was changed.</span></span>
   - <span data-ttu-id="d1d75-208">**마지막 새로 고침:** 출력 엔터티에서 예측을 새로 고친 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-208">**Last refreshed:** The date the prediction refreshed results in the output entity.</span></span>

1. <span data-ttu-id="d1d75-209">결과를 검토하려는 예측 옆에 있는 세로 줄임표를 선택하고 **보기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-209">Select the vertical ellipses next to the prediction you want to review results for and select **View**.</span></span>

   :::image type="content" source="media/model-subs-view.PNG" alt-text="예측의 결과를 보려면 컨트롤을 확인하세요.":::   

1. <span data-ttu-id="d1d75-211">결과 페이지에는 세 가지 기본 데이터 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-211">There are three primary sections of data within the results page:</span></span>
    1. <span data-ttu-id="d1d75-212">**교육 모델 성능:** A, B 또는 C가 가능한 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-212">**Training model performance:** A, B, or C are possible scores.</span></span> <span data-ttu-id="d1d75-213">이 점수는 예측의 성능을 나타내며 출력 엔터티에 저장된 결과를 사용하도록 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-213">This score indicates the performance of the prediction, and can help you make the decision to use the results stored in the output entity.</span></span> <span data-ttu-id="d1d75-214">점수는 다음 규칙에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-214">Scores are determined based on the following rules:</span></span>
         
         - <span data-ttu-id="d1d75-215">**A** 모델이 총 예측의 50% 이상을 정확하게 예측하고 이탈한 고객에 대한 정확한 예측 비율이 기준 비율보다 10% 이상 큰 경우.</span><span class="sxs-lookup"><span data-stu-id="d1d75-215">**A** when the model accurately predicted at least 50% of the total predictions, and when the percentage of accurate predictions for customers who churned is greater than the baseline rate by at least 10%.</span></span>
            
         - <span data-ttu-id="d1d75-216">**B** 모델이 전체 예측의 50% 이상을 정확하게 예측하고 이탈한 고객에 대한 정확한 예측 비율이 기준선보다 최대 10% 큰 경우.</span><span class="sxs-lookup"><span data-stu-id="d1d75-216">**B** when the model accurately predicted at least 50% of the total predictions, and when the percentage of accurate predictions for customers who churned is up to 10% greater than the baseline.</span></span>
            
         - <span data-ttu-id="d1d75-217">**C** 모델이 전체 예측의 50% 미만을 정확하게 예측했거나 이탈한 고객에 대한 정확한 예측의 비율이 기준보다 작은 경우.</span><span class="sxs-lookup"><span data-stu-id="d1d75-217">**C** when the model accurately predicted less 50% of the total predictions, or when the percentage of accurate predictions for customers who churned is less than the baseline.</span></span>
               
         - <span data-ttu-id="d1d75-218">**기준선** 모델에 대한 예측 시간 창에 입력(예: 1년)하고 모델은 1개월 이하에 도달할 때까지 이를 2로 나누어 다른 시간 비율을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-218">**Baseline** takes the prediction time window input for the model (for example, one year) and the model creates different fractions of time by dividing it by 2 until it reaches one month or less.</span></span> <span data-ttu-id="d1d75-219">이 분수를 사용하여 이 기간 내에 구매하지 않은 고객에 대한 비즈니스 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-219">It uses these fractions to create a business rule for customers who have not purchased in this time frame.</span></span> <span data-ttu-id="d1d75-220">이러한 고객은 이탈한 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-220">These customers are considered as churned.</span></span> <span data-ttu-id="d1d75-221">이탈 가능성이 높은 사람을 가장 잘 예측할 수 있는 시간 기반 비즈니스 규칙이 기준 모델로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-221">The time-based business rule with the highest ability to predict who is likely to churn is chosen as baseline model.</span></span>
            
    1. <span data-ttu-id="d1d75-222">**이탈 가능성(고객 수):** 고객 이탈 위험 예측에 기반한 고객 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-222">**Likelihood to churn (number of customers):** Groups of customers based on their predicted risk of churn.</span></span> <span data-ttu-id="d1d75-223">이탈 위험이 높은 고객 세그먼트를 생성하려는 경우 이 데이터가 나중에 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-223">This data can help you later if you want to create a segment of customers with high churn risk.</span></span> <span data-ttu-id="d1d75-224">이러한 세그먼트는 세그먼트 멤버십을 위한 컷오프 위치를 이해하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-224">Such segments help to understand where your cutoff should be for segment membership.</span></span>
       
    1. <span data-ttu-id="d1d75-225">**가장 영향력 있는 요소:** 예측을 만들 때 고려해야 할 요소가 많이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-225">**Most influential factors:** There are many factors that are taken into account when creating your prediction.</span></span> <span data-ttu-id="d1d75-226">각 요인에는 모델이 생성하는 집계된 예측에 대해 계산된 중요도가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-226">Each of the factors has its importance calculated for the aggregated predictions a model creates.</span></span> <span data-ttu-id="d1d75-227">이러한 요소를 사용하여 예측 결과를 검증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-227">You can use these factors to help validate your prediction results.</span></span> <span data-ttu-id="d1d75-228">또는 나중에 이 정보를 사용하여 [세그먼트 만들기 ](segments.md)를 통해 고객의 이탈 위험에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-228">Or you can use this information later to [create segments](segments.md) that could help influence churn risk for customers.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="d1d75-229">실패한 예측 문제 해결</span><span class="sxs-lookup"><span data-stu-id="d1d75-229">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="d1d75-230">**인텔리전스** > **예측** 으로 이동하고 **내 예측** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-230">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="d1d75-231">오류 로그를 보려는 예측 옆에 있는 세로 줄임표를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-231">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="d1d75-232">**로그** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-232">Select **Logs**.</span></span>

1. <span data-ttu-id="d1d75-233">모든 오류를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-233">Review all the errors.</span></span> <span data-ttu-id="d1d75-234">발생할 수 있는 여러 유형의 오류가 있으며 오류를 일으킨 조건을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-234">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="d1d75-235">예를 들어 정확하게 예측하기에 데이터가 충분하지 않은 오류는 일반적으로 추가 데이터를 Customer Insights에 로드하여 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-235">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="d1d75-236">예측 새로 고침</span><span class="sxs-lookup"><span data-stu-id="d1d75-236">Refresh a prediction</span></span>

<span data-ttu-id="d1d75-237">예측은 설정에서 구성된 대로 [데이터 새로 고침 예약](system.md#schedule-tab)에 자동으로 동일하게 갱신됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-237">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="d1d75-238">수동으로도 새로 고칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-238">You can refresh them manually too.</span></span>

1. <span data-ttu-id="d1d75-239">**인텔리전스** > **예측** 으로 이동하고 **내 예측** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-239">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="d1d75-240">새로 고치려는 예측 옆의 세로 줄임표를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-240">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="d1d75-241">**새로 고침** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-241">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="d1d75-242">예측 삭제</span><span class="sxs-lookup"><span data-stu-id="d1d75-242">Delete a prediction</span></span>

<span data-ttu-id="d1d75-243">예측을 삭제하면 출력 엔터티도 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-243">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="d1d75-244">**인텔리전스** > **예측** 으로 이동하고 **내 예측** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-244">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="d1d75-245">삭제하려는 예측 옆의 세로 줄임표를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-245">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="d1d75-246">**삭제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d75-246">Select **Delete**.</span></span>
