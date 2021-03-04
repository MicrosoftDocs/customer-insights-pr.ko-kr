---
title: 제품 추천 예측 샘플 가이드
description: 이 샘플 가이드를 사용하여 즉시 사용 가능한 제품 추천 예측 모델을 사용해보세요.
ms.date: 02/10/2021
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ee873d9b7caa5f891cb2d5b8c665dec90ad0e59
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270510"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="39917-103">제품 추천 예측(미리 보기) 샘플 가이드</span><span class="sxs-lookup"><span data-stu-id="39917-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="39917-104">아래 제공된 샘플 데이터를 사용하여 제품 추천 예측의 엔드 투 엔드 예를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="39917-105">시나리오</span><span class="sxs-lookup"><span data-stu-id="39917-105">Scenario</span></span>

<span data-ttu-id="39917-106">Contoso는 고품질 커피 및 커피 머신을 생산하는 회사로 Contoso Coffee 웹 사이트를 통해 판매합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="39917-107">회사의 목표는 정기 고객에게 어떤 제품을 추천해야 하는지 이해하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="39917-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="39917-108">어떤 고객이 **구매 가능성** 이 더 높은지 알면 특정 항목에 집중함으로써 마케팅 노력을 절감할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39917-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="39917-109">필요한 항목</span><span class="sxs-lookup"><span data-stu-id="39917-109">Prerequisites</span></span>

- <span data-ttu-id="39917-110">Customer Insights에 최소한 [기여자 권한](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="39917-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="39917-111">[새로운 환경에서](manage-environments.md) 다음 단계를 구현하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="39917-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="39917-112">작업 1 - 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="39917-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="39917-113">파워 쿼리 커넥터를 사용하여 [데이터 수집](data-sources.md) 및 [데이터 원본 가져오기](connect-power-query.md)에 대한 문서를 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="39917-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="39917-114">다음 정보는 사용자가 일반적인 데이터 수집에 익숙하다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="39917-115">전자상거래 플랫폼에서 고객 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="39917-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="39917-116">**전자상거래** 라는 데이터 원본을 만들고 가져오기 옵션을 선택한 다음 **텍스트/CSV** 커넥터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="39917-117">전자상거래 연락처 URL인 https://aka.ms/ciadclasscontacts를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="39917-118">데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="39917-119">아래 나열된 열의 데이터 유형을 업데이트하세요.</span><span class="sxs-lookup"><span data-stu-id="39917-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="39917-120">**DateOfBirth**: 날짜</span><span class="sxs-lookup"><span data-stu-id="39917-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="39917-121">**CreatedOn**: 날짜/시간/영역</span><span class="sxs-lookup"><span data-stu-id="39917-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="생년월일을 현재로 변환합니다.":::

5. <span data-ttu-id="39917-123">오른쪽 창의 '이름' 필드에서 데이터 원본의 이름을 **쿼리** 에서 **eCommerceContacts** 로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="39917-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="39917-124">데이터 원본을 **저장** 합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="39917-125">온라인 구매 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="39917-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="39917-126">동일한 **전자상거래** 데이터 원본에 다른 데이터 원본을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="39917-127">**텍스트/CSV** 커넥터를 다시 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="39917-128">**온라인 구매** 데이터 URL인 https://aka.ms/ciadclassonline을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="39917-129">데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="39917-130">아래 나열된 열의 데이터 유형을 업데이트하세요.</span><span class="sxs-lookup"><span data-stu-id="39917-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="39917-131">**PurchasedOn**: 날짜/시간</span><span class="sxs-lookup"><span data-stu-id="39917-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="39917-132">**TotalPrice**: 통화</span><span class="sxs-lookup"><span data-stu-id="39917-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="39917-133">측면 창의 **이름** 필드에서 데이터 원본의 이름을 **쿼리** 에서 **eCommercePurchases** 로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="39917-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="39917-134">데이터 원본을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-134">Save the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="39917-135">충성도 스키마에서 고객 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="39917-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="39917-136">**LoyaltyScheme** 이라는 데이터 원본을 만들고 가져오기 옵션을 선택한 다음 **텍스트/CSV** 커넥터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="39917-137">전자상거래 연락처 URL인 https://aka.ms/ciadclasscustomerloyalty를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="39917-138">데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="39917-139">아래 나열된 열의 데이터 유형을 업데이트하세요.</span><span class="sxs-lookup"><span data-stu-id="39917-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="39917-140">**DateOfBirth**: 날짜</span><span class="sxs-lookup"><span data-stu-id="39917-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="39917-141">**RewardsPoints**: 정수</span><span class="sxs-lookup"><span data-stu-id="39917-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="39917-142">**CreatedOn**: 날짜/시간</span><span class="sxs-lookup"><span data-stu-id="39917-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="39917-143">오른쪽 창의 **이름** 필드에서 데이터 원본의 이름을 **쿼리** 에서 **loyCustomers** 로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="39917-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="39917-144">데이터 원본을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-144">Save the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="39917-145">작업 2 - 데이터 통합</span><span class="sxs-lookup"><span data-stu-id="39917-145">Task 2 - Data unification</span></span>

<span data-ttu-id="39917-146">데이터를 수집 한 후 이제 **매핑, 일치, 병합** 프로세스를 시작하여 통합 고객 프로필을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="39917-146">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="39917-147">자세한 내용은 [데이터 통합](data-unification.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="39917-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="39917-148">매핑</span><span class="sxs-lookup"><span data-stu-id="39917-148">Map</span></span>

1. <span data-ttu-id="39917-149">데이터를 수집한 후 전자상거래 및 충성도 데이터의 연락처를 공통 데이터 유형에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="39917-150">**데이터** > **통합** > **매핑** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="39917-151">고객 프로필을 나타내는 엔터티(**eCommerceContacts** 및 **loyCustomers**)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![전자상거래와 충성도 데이터 원본을 통합합니다.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="39917-153">**eCommerceContacts** 의 기본 키로 **ContactId** 를 선택하고 **loyCustomers** 의 기본 키로 **LoyaltyID** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![LoyaltyId를 기본 키로 통합합니다.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="39917-155">일치</span><span class="sxs-lookup"><span data-stu-id="39917-155">Match</span></span>

1. <span data-ttu-id="39917-156">**일치 탭** 으로 이동한 다음 **순서 설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="39917-157">**기본** 드롭다운 목록에서 **eCommerceContacts : eCommerce** 를 기본 소스로 선택하고 모든 레코드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="39917-158">**엔터티 2** 드롭다운 목록에서 **loyCustomers : LoyaltyScheme** 을 선택하고 모든 레코드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![전자상거래와 충성도 데이터 원본을 통합합니다.](media/unify-match-order.png)

4. <span data-ttu-id="39917-160">**새 규칙 만들기** 선택</span><span class="sxs-lookup"><span data-stu-id="39917-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="39917-161">FullName을 사용하여 첫 번째 조건을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="39917-162">eCommerceContacts의 경우 **FullName** 드롭다운에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="39917-163">loyCustomers의 경우 **FullName** 드롭다운에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="39917-164">**정규화** 드롭다운을 선택하고 **유형(전화, 이름, 주소, ...)** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="39917-165">**정밀도 수준**: **기본** 및 **값**: **높음** 을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="39917-166">새 규칙의 이름에 **FullName, Email** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="39917-167">**조건 추가** 를 선택하여 이메일 주소에 대한 두 번째 조건을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="39917-168">엔터티 eCommerceContacts의 경우 드롭다운에서 **이메일** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="39917-169">엔터티 loyCustomers의 경우 드롭다운에서 **이메일** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="39917-170">정규화를 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="39917-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="39917-171">**정밀도 수준**: **기본** 및 **값**: **높음** 을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![이름 및 이메일에 대한 일치 규칙을 통합합니다.](media/unify-match-rule.png)

7. <span data-ttu-id="39917-173">**저장** 및 **실행** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="39917-174">병합</span><span class="sxs-lookup"><span data-stu-id="39917-174">Merge</span></span>

1. <span data-ttu-id="39917-175">**병합** 탭으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="39917-176">**loyCustomers** 엔터티의 **ContactId** 에서 표시 이름을 **ContactIdLOYALTY** 로 변경하여 수집된 다른 ID와 구별합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![포인트 ID에서 contactid의 이름을 바꿉니다.](media/unify-merge-contactid.png)

1. <span data-ttu-id="39917-178">**저장** 및 **실행** 을 선택하여 병합 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="39917-179">작업 3 - 제품 추천 예측 구성</span><span class="sxs-lookup"><span data-stu-id="39917-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="39917-180">통합된 고객 프로필을 사용하면 이제 구독 이탈 예측을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39917-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="39917-181">**인텔리전스** > **예측** 으로 이동하여 **제품 추천** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="39917-182">**시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-182">Select **Get started**.</span></span>

1. <span data-ttu-id="39917-183">모델 이름을 **OOB 제품 추천 모델 예측** 으로 지정하고 출력 엔티티를 **OOBProductRecommendationModelPrediction** 으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="39917-184">모델에 대한 세 가지 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="39917-185">**제품 수**: 이 값을 **5** 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="39917-186">이 설정은 고객에게 추천할 제품 수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="39917-187">**고객이 최근에 구매한 제품을 제안하시겠습니까?**: **예** 를 선택하여 추천에 고객이 이전에 구매한 제품을 포함할 것임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="39917-187">**Suggest products customers have recently purchased?**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="39917-188">**과거 기록 보기 창:** **365 일** 이상을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="39917-189">이 설정은 모델이 추천에 대한 입력으로 사용하기 위해 고객의 활동을 되돌아 볼 기간을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="제품 추천 모델에 대한 모델 선호 설정입니다.":::

1. <span data-ttu-id="39917-191">**필수 데이터** 를 선택하고 구매 기록에 대한 **데이터 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="39917-192">**eCommercePurchases : 전자상거래** 추가 엔터티를 추가하고 전자상거래의 필드를 모델에 필요한 해당 필드에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="39917-193">**eCommercePurchases : 전자상거래** 엔터티와 **eCommerceContacts : 전자상거래** 에 가입하세요.</span><span class="sxs-lookup"><span data-stu-id="39917-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![전자상거래 엔터티에 가입하세요.](media/model-purchase-join.png)

1. <span data-ttu-id="39917-195">**다음** 을 선택하여 모델 일정을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="39917-196">모델은 수집된 새 데이터가 있을 때 새로운 패턴을 학습하기 위해 정기적으로 학습해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="39917-197">이 예에서는 **월별** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="39917-198">모든 세부 정보를 검토한 후 **저장 및 실행** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="39917-199">작업 4 - 모델 결과 및 설명 검토</span><span class="sxs-lookup"><span data-stu-id="39917-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="39917-200">모델이 데이터의 학습 및 채점을 완료하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="39917-201">이제 제품 추천 모델 설명을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39917-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="39917-202">자세한 내용은 [예측 상태 및 결과를 검토](predict-subscription-churn.md#review-a-prediction-status-and-results)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39917-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="39917-203">작업 5 - 자주 구매한 제품 세그먼트 만들기</span><span class="sxs-lookup"><span data-stu-id="39917-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="39917-204">프로덕션 모델을 실행하면 **데이터** > **엔티티** 에서 볼 수 있는 새 엔티티가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="39917-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="39917-205">모델에서 생성한 엔터티를 기반으로 새 세그먼트를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39917-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="39917-206">**세그먼트** 로 이동</span><span class="sxs-lookup"><span data-stu-id="39917-206">Go to **Segments**.</span></span> <span data-ttu-id="39917-207">**새로 만들기** 를 **만들기** > **인텔리전스** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![모델 출력으로 세그먼트 생성.](media/segment-intelligence.png)

1. <span data-ttu-id="39917-209">**OOBProductRecommendationModelPrediction** 엔드포인트를 선택하고 세그먼트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="39917-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="39917-210">필드: ProductID</span><span class="sxs-lookup"><span data-stu-id="39917-210">Field: ProductID</span></span>
   - <span data-ttu-id="39917-211">연산자: 값</span><span class="sxs-lookup"><span data-stu-id="39917-211">Operator: Value</span></span>
   - <span data-ttu-id="39917-212">값: 상위 3개 제품 ID 선택</span><span class="sxs-lookup"><span data-stu-id="39917-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="모델 결과에서 세그먼트를 만듭니다.":::

<span data-ttu-id="39917-214">이제 가장 추천하는 세 가지 제품을 구매할 의사가 있는 고객을 식별하며 동적으로 업데이트되는 세그먼트를 보유했습니다.</span><span class="sxs-lookup"><span data-stu-id="39917-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="39917-215">자세한 내용은 [세그먼트 만들기 및 관리](segments.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39917-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]