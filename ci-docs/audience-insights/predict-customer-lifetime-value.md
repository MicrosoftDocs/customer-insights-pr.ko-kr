---
title: 고객 평생 가치(CLV) 예측
description: 향후 활성 고객의 잠재적인 수익을 예측합니다.
ms.date: 02/05/2021
ms.reviewer: wameng
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 363a46c81b5bb737d274998f9a699dc662e38d7c
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268602"
---
# <a name="customer-lifetime-value-clv-prediction-preview"></a><span data-ttu-id="d5909-103">고객 평생 가치(CLV) 예측(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="d5909-103">Customer lifetime value (CLV) prediction (Preview)</span></span>

<span data-ttu-id="d5909-104">개별 활성 고객이 정의된 미래 기간 동안 비즈니스에 가져올 잠재적 가치(수익)를 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-104">Predict potential value (revenue) that individual active customers will bring in to your business through a defined future time period.</span></span> <span data-ttu-id="d5909-105">이 기능은 다음과 같은 다양한 목표를 달성하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-105">This feature can help you achieve various goals:</span></span> 
- <span data-ttu-id="d5909-106">가치 높은 고객 고객을 식별하고 해당 인사이트를 처리</span><span class="sxs-lookup"><span data-stu-id="d5909-106">Identify high-value customers and process this insight</span></span>
- <span data-ttu-id="d5909-107">잠재 가치를 기반으로 전략적인 고객 세그먼트를 만들어 타겟팅된 판매, 마케팅 및 지원 노력을 통해 개인화된 캠페인을 실행</span><span class="sxs-lookup"><span data-stu-id="d5909-107">Create strategical customer segments based on their potential value to run personalized campaigns with targeted sales, marketing, and support efforts</span></span>
- <span data-ttu-id="d5909-108">고객 가치를 높이는 기능에 집중하여 제품 개발 지원</span><span class="sxs-lookup"><span data-stu-id="d5909-108">Guide product development by focusing on features tht increase customer value</span></span>
- <span data-ttu-id="d5909-109">영업 또는 마케팅 전략을 최적화하고 고객 지원을 위해 더 정확하게 예산을 할당</span><span class="sxs-lookup"><span data-stu-id="d5909-109">Optimize sales or marketing strategy and allocate budget more accurately for customer outreach</span></span>
- <span data-ttu-id="d5909-110">로열티 또는 보상 프로그램을 통해 가치 높은 고객 고객을 인식하고 보상</span><span class="sxs-lookup"><span data-stu-id="d5909-110">Recognize and reward high-value customers through loyalty or rewards programs</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="d5909-111">필요한 항목</span><span class="sxs-lookup"><span data-stu-id="d5909-111">Prerequisites</span></span>

<span data-ttu-id="d5909-112">시작하기 전에 CLV가 비즈니스에 어떤 의미인지 반영하십시오.</span><span class="sxs-lookup"><span data-stu-id="d5909-112">Before getting started, reflect what CLV means for your business.</span></span> <span data-ttu-id="d5909-113">현재는 트랜잭션 기반 CLV 예측을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-113">Currently, we support transaction-based CLV prediction.</span></span> <span data-ttu-id="d5909-114">고객의 예측 가치는 비즈니스 트랜잭션을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-114">The predicted value of a customer is based on history of business transactions.</span></span> <span data-ttu-id="d5909-115">예측을 만들려면 [Contributor](permissions.md) 이상의 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-115">To create the prediction, you need at least [Contributor](permissions.md) permissions.</span></span>

<span data-ttu-id="d5909-116">CLV 모델을 구성하고 실행하는 데 많은 시간이 걸리지 않으므로 다양한 입력 선호 설정으로 여러 모델을 만들고 모델 결과를 비교하여 비즈니스 요구에 가장 적합한 모델 시나리오를 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="d5909-116">Since configuring and running a CLV model doesn't take much time, consider creating several models with varying input preferences and compare model results to see which model scenario best fits your business needs.</span></span>

###  <a name="data-requirements"></a><span data-ttu-id="d5909-117">데이터 요구 사항</span><span class="sxs-lookup"><span data-stu-id="d5909-117">Data requirements</span></span>

<span data-ttu-id="d5909-118">다음 데이터는 필수이며 선택 사항으로 표시된 경우, 모델 성능 향상을 위해 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-118">The following data is required, and where marked optional, recommended for increased model performance.</span></span> <span data-ttu-id="d5909-119">모델이 처리 할 수 있는 데이터가 많을수록 예측이 더 정확해집니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-119">The more data the model can process, the more accurate the prediction will be.</span></span> <span data-ttu-id="d5909-120">따라서 가능하다면 더 많은 고객 활동 데이터를 수집하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-120">Therefore, we encourage you to ingest more customer activity data, if available.</span></span>

- <span data-ttu-id="d5909-121">고객 식별자: 트랜잭션을 개별 고객과 일치시키는 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="d5909-121">Customer Identifier: Unique identifier to match transactions to an individual customer</span></span>

- <span data-ttu-id="d5909-122">트랜잭션 이력: 아래의 의미론적 데이터 스키마가 있는 과거 트랜잭션 로그</span><span class="sxs-lookup"><span data-stu-id="d5909-122">Transaction History: Historical transactions log with below semantic data schema</span></span>
    - <span data-ttu-id="d5909-123">트랜잭션 ID: 각 트랜잭션의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="d5909-123">Transaction ID: Unique identifier of each transaction</span></span>
    - <span data-ttu-id="d5909-124">트랜잭션 날짜: 날짜, 가급적 각 트랜잭션의 타임 스탬프</span><span class="sxs-lookup"><span data-stu-id="d5909-124">Transaction date: Date, preferably a time stamp of each transaction</span></span>
    - <span data-ttu-id="d5909-125">트랜잭션 금액: 각 트랜잭션의 금전적 가치(예: 수익 또는 이익률)</span><span class="sxs-lookup"><span data-stu-id="d5909-125">Transaction amount: Monetary value (for example, revenue or profit margin) of each transaction</span></span>
    - <span data-ttu-id="d5909-126">반품에 할당된 라벨(선택 사항): 트랜잭션이 반품인지 여부를 나타내는 부울 값</span><span class="sxs-lookup"><span data-stu-id="d5909-126">Label assigned to returns (optional): Boolean value signifying whether the transaction is a return</span></span> 
    - <span data-ttu-id="d5909-127">제품 ID(선택 사항): 트랜잭션에 관련된 제품의 제품 ID</span><span class="sxs-lookup"><span data-stu-id="d5909-127">Product ID (optional): Product ID of product involved in the transaction</span></span>

- <span data-ttu-id="d5909-128">추가 데이터(선택 사항), 예시</span><span class="sxs-lookup"><span data-stu-id="d5909-128">Additional data (optional), for example</span></span>
    - <span data-ttu-id="d5909-129">웹 활동: 웹 사이트 방문 기록, 이메일 기록</span><span class="sxs-lookup"><span data-stu-id="d5909-129">Web activities: website visit history, email history</span></span>
    - <span data-ttu-id="d5909-130">로열티 활동: 로열티 보상 포인트 적립 및 사용 기록</span><span class="sxs-lookup"><span data-stu-id="d5909-130">Loyalty activities: loyalty reward points accrual and redemption history</span></span>
    - <span data-ttu-id="d5909-131">고객 서비스 로그, 서비스 요청, 불만 또는 반품 기록</span><span class="sxs-lookup"><span data-stu-id="d5909-131">Customer service log, service call, complaint, or return history</span></span>
- <span data-ttu-id="d5909-132">고객 활동에 대한 데이터(선택 사항):</span><span class="sxs-lookup"><span data-stu-id="d5909-132">Data about customer activities (optional):</span></span>
    - <span data-ttu-id="d5909-133">동일한 유형의 활동을 구별하기 위한 활동 식별자</span><span class="sxs-lookup"><span data-stu-id="d5909-133">Activity identifiers to distinguish activities of the same type</span></span>
    - <span data-ttu-id="d5909-134">고객에 대한 활동을 매핑하는 고객 식별자</span><span class="sxs-lookup"><span data-stu-id="d5909-134">Customer identifiers to map activities to your customers</span></span>
    - <span data-ttu-id="d5909-135">활동의 이름과 날짜를 포함한 활동 정보</span><span class="sxs-lookup"><span data-stu-id="d5909-135">Activity information containing the name and date of the activity</span></span>
    - <span data-ttu-id="d5909-136">활동에 대한 의미론적 데이터 스키마에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-136">The semantic data schema for activities includes:</span></span> 
        - <span data-ttu-id="d5909-137">기본 키: 활동에 대한 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="d5909-137">Primary key: A unique identifier for an activity</span></span>
        - <span data-ttu-id="d5909-138">타임스탬프: 기본 키로 식별된 이벤트 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="d5909-138">Timestamp: The date and time of the event identified by the primary key</span></span>
        - <span data-ttu-id="d5909-139">이벤트(활동 이름): 사용하려는 이벤트의 이름</span><span class="sxs-lookup"><span data-stu-id="d5909-139">Event (activity name):  The name of event you want to use</span></span>
        - <span data-ttu-id="d5909-140">세부 정보(금액 또는 가치): 고객 활동에 대한 세부 정보</span><span class="sxs-lookup"><span data-stu-id="d5909-140">Details (amount or value): Details about the customer activity</span></span>

## <a name="create-a-customer-lifetime-value-prediction"></a><span data-ttu-id="d5909-141">고객 평생 가치 예측 만들기</span><span class="sxs-lookup"><span data-stu-id="d5909-141">Create a Customer Lifetime Value prediction</span></span>

1. <span data-ttu-id="d5909-142">대상 그룹 인사이트에서 **인텔리전스** > **예측** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-142">In audience insights, go to **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="d5909-143">**고객 평생 가치** 타일을 선택하고 **모델 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-143">Select the **Customer lifetime value** tile and select **Use model**.</span></span> 

1. <span data-ttu-id="d5909-144">**고객 평생 가치(미리 보기)** 창에서, **시작하기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-144">In the **Customer lifetime value (preview)** pane, select **Get started**.</span></span>

1. <span data-ttu-id="d5909-145">**이 모델 이름** 및 **출력 엔터티 이름** 을 지정하여 다른 모델이나 엔터티와 구별합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-145">**Name this model** and the **Output entity name** to distinguish them from other models or entities.</span></span>

1. <span data-ttu-id="d5909-146">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-146">Select **Next**.</span></span>

### <a name="define-model-preferences"></a><span data-ttu-id="d5909-147">모델 선호 설정 정의</span><span class="sxs-lookup"><span data-stu-id="d5909-147">Define model preferences</span></span>

1. <span data-ttu-id="d5909-148">**예측 기간** 을 설정하여 CLV를 예측하려는 미래를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-148">Set a **Prediction time period** to define how far into the future you want to predict the CLV.</span></span>    
   <span data-ttu-id="d5909-149">기본적으로 단위는 월로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-149">By default, the unit is set as months.</span></span> <span data-ttu-id="d5909-150">미래를 더 보려면 연도를 변경하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-150">You can change it to years to look further in the future.</span></span>

   > [!TIP]
   > <span data-ttu-id="d5909-151">설정한 기간 동안 CLV를 정확하게 예측하려면 비슷한 기간의 과거 데이터가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-151">To accurately predict CLV for the time period you set, you need a comparable period of historical data.</span></span> <span data-ttu-id="d5909-152">예를 들어 다음 12개월 동안을 예측하려면 최소 18~24개월의 과거 데이터를 보유하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-152">For example, if you want to predict for the next 12 months, it is recommended that you have at least 18 – 24 months of historical data.</span></span>

1. <span data-ttu-id="d5909-153">**활성 고객** 이 비즈니스에 어떤 의미인지 지정하십시오.</span><span class="sxs-lookup"><span data-stu-id="d5909-153">Specify what **Active customers** mean for your business.</span></span> <span data-ttu-id="d5909-154">고객이 활성으로 간주되는 트랜잭션이 하나 이상 있어야 하는 시간 프레임을 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="d5909-154">Set the time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="d5909-155">이 모델은 활성 고객에 대한 CLV만 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-155">The model will only predict CLV for active customers.</span></span> 
   - <span data-ttu-id="d5909-156">**모델이 구매 간격을 계산하도록 함(권장)**: 모델은 데이터를 분석하고 과거 구매를 기반으로 기간을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-156">**Let model calculate purchase interval (recommended)**: The model analyzes your data and determines a time period based on historical purchases.</span></span>
   - <span data-ttu-id="d5909-157">**수동으로 간격 설정**: 활성 고객에 대한 특정 비즈니스 정의가 있는 경우 이 옵션을 선택하고 그에 따라 기간을 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="d5909-157">**Set interval manually**: If you have a specific business definition of an active customer, choose this option and set the time period accordingly.</span></span>

1. <span data-ttu-id="d5909-158">**가치 높은 고객 고객** 의 백분위 수를 정의하여 모델이 비즈니스 정의에 맞는 결과를 제공할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-158">Define percentile of **High-value customer** to enable the model to provide results that fit your business definition.</span></span>
    - <span data-ttu-id="d5909-159">**모델 계산(권장)**: 모델은 데이터를 분석하고 고객의 거래 내역을 기반으로 비즈니스에 대한 가치 높은 고객 고객을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-159">**Model calculation (recommended)**: The model analyzes your data and determines what a high value customer might be for your business based on your customers’ transaction history.</span></span> <span data-ttu-id="d5909-160">이 모델은 가치 높은 고객 고객의 비율을 찾기 위해 경험 규칙(80/20 규칙 또는 파레토 원칙에서 영감을 얻음)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-160">The model uses a heuristic rule (inspired by the 80/20 rule or pareto principle) to find the proportion of high-value customers.</span></span> <span data-ttu-id="d5909-161">과거 기간 동안 비즈니스에 대한 누적 수익의 80%에 기여한 고객의 비율이 가치 높은 고객 고객으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-161">The percentage of customers that contributed to 80% cumulative revenue for your business in the historical period are considered high-value customers.</span></span> <span data-ttu-id="d5909-162">일반적으로 30-40% 미만의 고객이 누적 수익의 80%에 기여합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-162">Typically, less than 30-40% customers contribute to 80% cumulative revenue.</span></span> <span data-ttu-id="d5909-163">그러나 이 숫자는 비즈니스 및 산업에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-163">However, this number might vary depending on your business and industry.</span></span>    
    - <span data-ttu-id="d5909-164">**최고 활성 고객 비율**: 비즈니스에 대한 가치 높은 고객 고객을 최고 활성 유료 고객의 백분위 수로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-164">**Percent of top active customers**: Define high-value customers for your business as a percentile of top active paying customers.</span></span> <span data-ttu-id="d5909-165">예를 들어 이 옵션을 사용하여 가치 높은 고객 고객을 향후 유료 고객의 상위 20%로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-165">For example, you can use this option to define high-value customers as top 20% of future paying customers.</span></span>

    <span data-ttu-id="d5909-166">비즈니스에서 가치 높은 고객 고객을 다른 방식으로 정의한다면, [듣고 싶으니 알려주십시오](https://go.microsoft.com/fwlink/?linkid=2074172).</span><span class="sxs-lookup"><span data-stu-id="d5909-166">If your business defines high value customers in a different way, [let us know as we would love to hear](https://go.microsoft.com/fwlink/?linkid=2074172).</span></span>

1. <span data-ttu-id="d5909-167">**다음** 을 선택하여 다음 단계를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-167">Select **Next** to proceed to the next step.</span></span>

### <a name="add-required-data"></a><span data-ttu-id="d5909-168">필수 데이터 추가</span><span class="sxs-lookup"><span data-stu-id="d5909-168">Add required data</span></span>

1. <span data-ttu-id="d5909-169">**필수 데이터** 단계에서 **고객 트랜잭션 기록** 에 대한 **데이터 추가** 를 선택하고 [필수 구성 요소](#prerequisites)에 설명된 대로 거래 기록 정보를 제공하는 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-169">In the **Required data** step, select **Add data** for **Customer transaction history** and choose the entity that provides the transaction history information as described in the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="d5909-170">의미론적 필드를 구매 기록 엔터티 내의 특성에 매핑하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-170">Map the semantic fields to attributes within your purchase history entity and select **Next**.</span></span>

   :::image type="content" source="media/clv-add-customer-data-mapping.png" alt-text="필수 데이터의 데이터 특성을 매핑하기 위한 구성 단계의 이미지입니다.":::
 
1. <span data-ttu-id="d5909-172">아래 필드가 채워지지 않은 경우 구매 기록 엔터티에서 *고객 엔터티로* 의 관계를 구성하고 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-172">If the fields below aren't populated, configure the relationship from your purchase history entity to the *Customer* entity and select **Save**.</span></span>
    1. <span data-ttu-id="d5909-173">트랜잭션 기록 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-173">Select the transaction history entity.</span></span>
    1. <span data-ttu-id="d5909-174">구매 기록 엔터티에서 고객을 식별하는 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-174">Select the field that identifies a customer in the purchase history entity.</span></span> <span data-ttu-id="d5909-175">고객 엔터티의 기본 고객 ID와 관련이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-175">It needs to relate to the primary customer ID of your Customer entity.</span></span>
    1. <span data-ttu-id="d5909-176">기본 고객 엔터티와 일치하는 엔터티를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="d5909-176">Select the entity that matches your primary customer entity.</span></span>
    1. <span data-ttu-id="d5909-177">관계를 설명하는 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-177">Enter a name that describes the relationship.</span></span>

      :::image type="content" source="media/clv-add-customer-data-relationship.png" alt-text="고객 엔터티와의 관계를 정의하기 위한 구성 단계의 이미지입니다.":::

1. <span data-ttu-id="d5909-179">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-179">Select **Next**.</span></span>

### <a name="add-optional-data"></a><span data-ttu-id="d5909-180">선택적 데이터 추가</span><span class="sxs-lookup"><span data-stu-id="d5909-180">Add optional data</span></span>

<span data-ttu-id="d5909-181">주요 고객 상호 작용(웹, 고객 서비스 및 이벤트 로그)을 반영하는 데이터는 트랜잭션 레코드에 컨텍스트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-181">Data reflecting key customer interactions (like web, customer service, and event logs) adds context to transaction records.</span></span> <span data-ttu-id="d5909-182">고객 활동 데이터에서 더 많은 패턴을 발견하면 예측의 정확성을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-182">More patterns found in your customer activity data can improve the accuracy of the predictions.</span></span> 

1. <span data-ttu-id="d5909-183">**추가 데이터(선택 사항)** 단계에서 **데이터 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-183">In the **Additional data (optional)** step, select **Add data**.</span></span> <span data-ttu-id="d5909-184">[필수 구성 요소](#prerequisites)에 설명된 대로 고객 활동 정보를 제공하는 고객 활동 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-184">Choose the customer activity entity that provides the customer activity information as described in the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="d5909-185">의미론적 필드를 고객 활동 엔터티 내의 특성에 매핑하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-185">Map the semantic fields to attributes within your customer activity entity and select **Next**.</span></span>

   :::image type="content" source="media/clv-additional-data-mapping.png" alt-text="추가 데이터의 필드를 매핑하기 위한 구성 단계의 이미지입니다.":::

1. <span data-ttu-id="d5909-187">추가하는 고객 활동 유형과 일치하는 활동 유형을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="d5909-187">Select an activity type that matches the type of customer activity you're adding.</span></span> <span data-ttu-id="d5909-188">기존 활동 유형에서 선택하거나 새 활동 유형을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-188">Choose from existing activity types or add a new activity type.</span></span>

1. <span data-ttu-id="d5909-189">고객 활동 엔터티에서 *고객* 엔터티로의 관계를 구성하십시오.</span><span class="sxs-lookup"><span data-stu-id="d5909-189">Configure the relationship from your customer activity entity to the *Customer* entity.</span></span>
    
    1. <span data-ttu-id="d5909-190">고객 활동 테이블에서 고객을 식별하는 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-190">Select the field that identifies the customer in the customer activity table.</span></span> <span data-ttu-id="d5909-191">*고객* 엔터티의 기본 고객 ID와 직접 관련될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-191">It can be directly related to the primary customer ID of your *Customer* entity.</span></span>
    1. <span data-ttu-id="d5909-192">기본 *고객* 엔터티와 일치하는 *고객* 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-192">Select the *Customer* entity that matches your primary *Customer* entity.</span></span>
    1. <span data-ttu-id="d5909-193">관계를 설명하는 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-193">Enter a name that describes the relationship.</span></span>

   :::image type="content" source="media/clv-additional-data.png" alt-text="추가 데이터를 추가하고 예제로 채워진 활동을 구성하는 구성 흐름의 단계 이미지입니다.":::

1. <span data-ttu-id="d5909-195">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-195">Select **Save**.</span></span>    
    <span data-ttu-id="d5909-196">포함하려는 다른 고객 활동이 있는 경우 더 많은 데이터를 추가하십시오.</span><span class="sxs-lookup"><span data-stu-id="d5909-196">Add more data if there are other customer activities you want to include.</span></span>

1. <span data-ttu-id="d5909-197">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-197">Select **Next**.</span></span>

### <a name="set-update-schedule"></a><span data-ttu-id="d5909-198">업데이트 일정 설정</span><span class="sxs-lookup"><span data-stu-id="d5909-198">Set update schedule</span></span>

1. <span data-ttu-id="d5909-199">**데이터 업데이트 일정** 단계에서 최신 데이터를 기반으로 모델을 재교육할 빈도를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-199">In the **Data update schedule** step, choose the frequency to retrain your model based on the latest data.</span></span> <span data-ttu-id="d5909-200">이 설정은 새 데이터가 대상 그룹 인사이트에서 수집될 때 예측의 정확성을 업데이트하는 데 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-200">This setting is important to update the accuracy of predictions as new data is ingested in audience insights.</span></span> <span data-ttu-id="d5909-201">대부분의 비즈니스는 한 달에 한 번 재교육을 받고 예측의 정확도를 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-201">Most businesses can retrain once per month and get a good accuracy for their prediction.</span></span>

1. <span data-ttu-id="d5909-202">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-202">Select **Next**.</span></span>


### <a name="review-and-run-the-model-configuration"></a><span data-ttu-id="d5909-203">모델 구성 검토 및 실행</span><span class="sxs-lookup"><span data-stu-id="d5909-203">Review and run the model configuration</span></span>

1. <span data-ttu-id="d5909-204">**모델 세부 정보 검토** 단계에서 예측의 구성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-204">In the **Review your model details** step, validate the configuration of the prediction.</span></span> <span data-ttu-id="d5909-205">표시된 값 아래에서 **편집** 을 선택하여 예측 구성의 일부로 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-205">You can go back to any part of the prediction configuration by selecting **Edit** under the shown value.</span></span> <span data-ttu-id="d5909-206">진행률 표시기에서 구성 단계를 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-206">You can also select a configuration step from the progress indicator.</span></span>

1. <span data-ttu-id="d5909-207">모든 값이 올바르게 구성된 경우 **저장 및 실행** 을 선택하여 모델 실행을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-207">If all values are configured correctly, select **Save and run** to start running the model.</span></span> <span data-ttu-id="d5909-208">**내 예측** 탭에서 예측 프로세스의 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-208">On the **My predictions** tab, you can see the status of the prediction process.</span></span> <span data-ttu-id="d5909-209">예측에 사용된 데이터 양에 따라 프로세스를 완료하는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-209">The process may take several hours to complete depending on the amount of data used in the prediction.</span></span>

## <a name="review-prediction-status-and-results"></a><span data-ttu-id="d5909-210">예측 상태 및 결과 검토</span><span class="sxs-lookup"><span data-stu-id="d5909-210">Review prediction status and results</span></span>

### <a name="review-prediction-status"></a><span data-ttu-id="d5909-211">예측 상태 검토</span><span class="sxs-lookup"><span data-stu-id="d5909-211">Review prediction status</span></span>

1.  <span data-ttu-id="d5909-212">**인텔리전스** > **예측** 으로 이동하고 **내 예측** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-212">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>
2.  <span data-ttu-id="d5909-213">검토하려는 예측을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-213">Select the prediction you want to review.</span></span>

- <span data-ttu-id="d5909-214">**예측 이름**: 생성 시 제공한 예측의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-214">**Prediction name**: Name of the prediction provided when creating it.</span></span>
- <span data-ttu-id="d5909-215">**예측 유형**: 예측에 사용되는 모델 유형</span><span class="sxs-lookup"><span data-stu-id="d5909-215">**Prediction type**: Type of model used for the prediction</span></span>
- <span data-ttu-id="d5909-216">**출력 엔터티**: 예측의 출력을 저장할 엔터티 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-216">**Output entity**: Name of the entity to store the output of the prediction.</span></span> <span data-ttu-id="d5909-217">**데이터** > **엔터티** 로 이동하여 이 이름을 가진 엔터티를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-217">Go to **Data** > **Entities** to find the entity with this name.</span></span>
- <span data-ttu-id="d5909-218">**예측 필드**: 이 필드는 일부 예측 유형에 대해서만 채워지며 고객 평생 가치 예측에는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-218">**Predicted field**: This field is populated only for some types of predictions, and isn't used in customer lifetime value prediction.</span></span>
- <span data-ttu-id="d5909-219">**상태**: 예측 실행 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-219">**Status**: Status of the prediction run.</span></span>
    - <span data-ttu-id="d5909-220">**대기 중**: 예측은 다른 프로세스가 완료되기를 기다리고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-220">**Queued**: Prediction is waiting for other processes to complete.</span></span>
    - <span data-ttu-id="d5909-221">**새로 고치는 중**: 출력 엔터티로 유입되는 결과를 생성하기 위해 현재 예측이 실행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-221">**Refreshing**: Prediction is currently running to create results that will flow into the output entity.</span></span>
    - <span data-ttu-id="d5909-222">**실패**: 예측 실행에 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-222">**Failed**: Prediction run has failed.</span></span> <span data-ttu-id="d5909-223">자세한 내용은 [로그](#troubleshoot-a-failed-prediction)를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-223">[Review the logs](#troubleshoot-a-failed-prediction) for more details.</span></span>
    - <span data-ttu-id="d5909-224">**성공**: 예측에 성공했습니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-224">**Succeeded**: Prediction has succeeded.</span></span> <span data-ttu-id="d5909-225">예측 결과를 검토하려면 세로 줄임표 아래에서 **보기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-225">Select **View** under the vertical ellipses to review the prediction results.</span></span>
- <span data-ttu-id="d5909-226">**편집됨**: 예측의 구성이 변경된 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-226">**Edited**: The date the configuration for the prediction was changed.</span></span>
- <span data-ttu-id="d5909-227">**마지막 새로 고침**: 출력 엔터티에서 예측을 새로 고친 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-227">**Last refreshed**: The date the prediction refreshed results in the output entity.</span></span>


### <a name="review-prediction-results"></a><span data-ttu-id="d5909-228">예측 결과 검토</span><span class="sxs-lookup"><span data-stu-id="d5909-228">Review prediction results</span></span>

1. <span data-ttu-id="d5909-229">**인텔리전스** > **예측** 으로 이동하고 **내 예측** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-229">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="d5909-230">결과를 검토할 예측을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="d5909-230">Select the prediction you want to review results for.</span></span>

<span data-ttu-id="d5909-231">결과 페이지에는 세 가지 기본 데이터 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-231">There are three primary sections of data within the results page.</span></span>

- <span data-ttu-id="d5909-232">**훈련 모델 성능**: A, B 또는 C는 가능한 등급입니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-232">**Training model performance**: A, B, or C are possible grades.</span></span> <span data-ttu-id="d5909-233">이 등급은 예측의 성능을 나타내며 출력 엔터티에 저장된 결과를 사용하기로 결정하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-233">This grade indicates the performance of the prediction and can help you make the decision to use the results stored in the output entity.</span></span> <span data-ttu-id="d5909-234">**이 점수에 대해 알아보기** 를 선택하면 기본 모델 성능 메트릭과 최종 모델 성능 등급을 도출한 방법을 더 잘 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-234">Select **Learn about this score** to better understand the underlying model performance metrics and how the final model performance grade was derived.</span></span>
  
  :::image type="content" source="media/clv-model-score.png" alt-text="A 등급의 모델 점수 정보 상자 이미지입니다.":::

  <span data-ttu-id="d5909-236">시스템은 예측을 구성하는 동안 제공된 가치 높은 고객 고객의 정의를 사용하여 AI 모델이 기준 모델과 비교하여 가치 높은 고객 고객을 예측하는 방법을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-236">Using the definition of high value customers provided while configuring the prediction, the system assess how the AI model performed in predicting the high value customers as compared to a baseline model.</span></span>    

  <span data-ttu-id="d5909-237">등급은 다음 규칙에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-237">Grades are determined based on the following rules:</span></span>
  - <span data-ttu-id="d5909-238">모델이 기준 모델에 비해 가치 높은 고객 고객을 5% 이상 정확하게 예측한 경우 A입니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-238">A when the model accurately predicted at least 5% more high-value customers as compared to the baseline model.</span></span>
  - <span data-ttu-id="d5909-239">모델이 기준 모델에 비해 가치 높은 고객 고객을 0~5% 더 정확하게 예측한 경우 B입니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-239">B when the model accurately predicted between 0-5% more high-value customers as compared to the baseline model.</span></span>
  - <span data-ttu-id="d5909-240">모델이 기준 모델에 비해 더 적은 수의 가치 높은 고객 고객을 정확하게 예측한 경우 C입니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-240">C when the model accurately predicted fewer high-value customers as compared to the baseline model.</span></span>

  <span data-ttu-id="d5909-241">**모델 등급** 창에는 AI 모델 성능 및 기준 모델에 대한 추가 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-241">The **Model rating** pane shows further details about the AI model performance and the baseline model.</span></span> <span data-ttu-id="d5909-242">기준 모델은 AI 기반이 아닌 접근 방식을 사용하여 주로 고객이 구매한 기록을 기반으로 고객 평생 가치를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-242">The baseline model uses a non-AI based approach to calculate customer lifetime value based primarily on historical purchases made by customers.</span></span>     
  <span data-ttu-id="d5909-243">기준 모델이 CLV를 계산하는 데 사용하는 표준 공식:</span><span class="sxs-lookup"><span data-stu-id="d5909-243">The standard formula used to calculate CLV by the baseline model:</span></span>    

  <span data-ttu-id="d5909-244">*각 고객의 CLV = 활성 고객 창에서 고객이 구매한 월평균 구매 \* CLV 예측 기간의 개월 수 \* 모든 고객의 전체 재방문 주기율*</span><span class="sxs-lookup"><span data-stu-id="d5909-244">*CLV for each customer = Average monthly purchase made by the customer in the active customer window \* Number of months in the CLV prediction period \* Overall retention rate of all customers*</span></span>

  <span data-ttu-id="d5909-245">AI 모델은 두 가지 모델 성능 메트릭을 기반으로 기준 모델과 비교됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-245">The AI model is compared to the baseline model based on two model performance metrics.</span></span>
  
  - <span data-ttu-id="d5909-246">**가치 높은 고객 예측 성공률**</span><span class="sxs-lookup"><span data-stu-id="d5909-246">**Success rate in predicting high-value customers**</span></span>

  <span data-ttu-id="d5909-247">기준 모델과 비교하여 AI 모델을 사용한 가치 높은 고객 예측의 차이점을 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="d5909-247">See the difference in predicting high-value customers using the AI model compared to the baseline model.</span></span> <span data-ttu-id="d5909-248">예를 들어 84%의 성공률은 교육 데이터의 모든 가치 높은 고객 중에서 AI 모델이 84%를 정확하게 포착할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-248">For example, 84% success rate means that out of all the high-value customers in the training data, the AI model was able to accurately capture 84%.</span></span> <span data-ttu-id="d5909-249">그런 다음 이 성공률을 기준 모델의 성공률과 비교하여 상대적 변화를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-249">We then compare this success rate with the success rate of the baseline model to report the relative change.</span></span> <span data-ttu-id="d5909-250">이 값은 모델에 등급을 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-250">This value is used to assign a grade to the model.</span></span>

  - <span data-ttu-id="d5909-251">**오류 메트릭**</span><span class="sxs-lookup"><span data-stu-id="d5909-251">**Error metrics**</span></span>
    
  <span data-ttu-id="d5909-252">또 다른 메트릭을 사용하면 미래 가치를 예측할 때 오류 측면에서 모델의 전체 성능을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-252">Another metric lets you review the overall performance of the model in terms of error in predicting future values.</span></span> <span data-ttu-id="d5909-253">이 오류를 평가하기 위해 전체 평균 제곱근 오차(RMSE) 메트릭을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-253">We use the overall Root Mean Squared Error (RMSE) metric to assess this error.</span></span> <span data-ttu-id="d5909-254">RMSE는 정량적 데이터를 예측할 때 모델의 오류를 측정하는 표준 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-254">RMSE is a standard way to measure the error of a model in predicting quantitative data.</span></span> <span data-ttu-id="d5909-255">AI 모델의 RMSE는 기준 모델의 RMSE와 비교되고 상대적 차이가 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-255">The AI model’s RMSE is compared to the RMSE of the baseline model and the relative difference is reported.</span></span>

  <span data-ttu-id="d5909-256">AI 모델은 고객이 비즈니스에 제공하는 가치에 따라 정확한 고객 순위를 우선으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-256">The AI model prioritizes the accurate ranking of customers according to the value they bring to your business.</span></span> <span data-ttu-id="d5909-257">따라서 가치 높은 고객 예측의 성공률만이 최종 모델 등급을 도출하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-257">So only the success rate of predicting high-value customers is used to derive the final model grade.</span></span> <span data-ttu-id="d5909-258">RMSE 메트릭은 이상값에 민감합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-258">The RMSE metric is sensitive to outliers.</span></span> <span data-ttu-id="d5909-259">매우 높은 구매 값을 가진 고객 비율이 적은 시나리오에서는 전체 RMSE 메트릭이 모델 성능에 대한 전체 그림을 제공하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-259">In scenarios where you have a small percentage of customers with extraordinarily high purchase values, the overall RMSE metric might not give the full picture of the model performance.</span></span>   

- <span data-ttu-id="d5909-260">**백분위 수별 고객 가치**: 가치 높은 고객에 대한 정의를 사용하여 고객은 CLV 예측을 기반으로 저가치 및 고가치로 그룹화되고 차트에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-260">**Value of customers by percentile**: Using your definition of high-value customers, customers are grouped into low-value and high-value, based on their CLV predictions, and shown in a chart.</span></span> <span data-ttu-id="d5909-261">히스토그램의 막대 위로 마우스를 가져가면 각 그룹의 고객 수와 해당 그룹의 평균 CLV를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-261">By hovering over the bars in the histogram, you can see the number of customers in each group and the average CLV of that group.</span></span> <span data-ttu-id="d5909-262">이 데이터는 CLV 예측을 기반으로 [고객 세그먼트를 생성](segments.md) 하려는 경우 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-262">This data can help if you want to [create segments of customers](segments.md) based on their CLV predictions.</span></span>

- <span data-ttu-id="d5909-263">**가장 영향력 있는 요소**: AI 모델에 제공된 입력 데이터를 기반으로 CLV 예측을 생성할 때 다양한 요소를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-263">**Most influential factors**: Various factors are considered when creating your CLV prediction based on the input data provided to the AI model.</span></span> <span data-ttu-id="d5909-264">각 요인은 모형이 생성하는 집계된 예측에 대해 중요도가 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-264">Each of the factors has their importance calculated for the aggregated predictions a model creates.</span></span> <span data-ttu-id="d5909-265">이러한 요소를 사용하여 예측 결과를 검증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-265">You can use these factors to help validate your prediction results.</span></span> <span data-ttu-id="d5909-266">이러한 요소는 또한 모든 고객의 CLV 예측에 기여한 가장 영향력 있는 요소에 대한 더 많은 인사이트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-266">These factors also provide more insight about the most influential factors that contributed towards predicting CLV across all your customers.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="d5909-267">예측 새로 고침</span><span class="sxs-lookup"><span data-stu-id="d5909-267">Refresh a prediction</span></span>

<span data-ttu-id="d5909-268">예측은 설정에 구성된 것과 동일한 [데이터 새로 고침 예약](system.md#schedule-tab)에서 자동으로 새로 고쳐집니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-268">Predictions automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="d5909-269">수동으로도 새로 고칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-269">You can refresh them manually too.</span></span>

1. <span data-ttu-id="d5909-270">**인텔리전스** > **예측** 으로 이동하고 **내 예측** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-270">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>
2. <span data-ttu-id="d5909-271">새로 고치려는 예측 옆의 세로 줄임표를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-271">Select the vertical ellipses next to the prediction you want to refresh.</span></span>
3. <span data-ttu-id="d5909-272">**새로 고침** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-272">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="d5909-273">예측 삭제</span><span class="sxs-lookup"><span data-stu-id="d5909-273">Delete a prediction</span></span>

<span data-ttu-id="d5909-274">예측을 삭제하면 출력 엔터티도 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-274">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="d5909-275">**인텔리전스** > **예측** 으로 이동하고 **내 예측** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-275">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>
2. <span data-ttu-id="d5909-276">삭제하려는 예측 옆의 세로 줄임표를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-276">Select the vertical ellipses next to the prediction you want to delete.</span></span>
3. <span data-ttu-id="d5909-277">**삭제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-277">Select **Delete**.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="d5909-278">실패한 예측 문제 해결</span><span class="sxs-lookup"><span data-stu-id="d5909-278">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="d5909-279">**인텔리전스** > **예측** 으로 이동하고 **내 예측** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-279">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>
2. <span data-ttu-id="d5909-280">오류 로그를 보려는 예측 옆에 있는 세로 줄임표를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-280">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>
3. <span data-ttu-id="d5909-281">**로그** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-281">Select **Logs**.</span></span>
4. <span data-ttu-id="d5909-282">모든 오류를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-282">Review all the errors.</span></span> <span data-ttu-id="d5909-283">발생할 수 있는 여러 유형의 오류가 있으며 오류를 일으킨 조건을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-283">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="d5909-284">예를 들어, 정확하게 예측할 수 있는 데이터가 충분하지 않다는 오류는 일반적으로 더 많은 데이터를 대상 그룹 인사이트에 로드하여 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5909-284">For example, an error that there's not enough data to accurately predict is typically resolved by loading more data into audience insights.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]