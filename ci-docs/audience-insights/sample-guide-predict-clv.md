---
title: 고객 평생 가치 예측 샘플 가이드
description: 이 샘플 가이드를 사용하여 고객 평생 가치 예측 모델을 사용해보세요.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 73d294a285b4ad706bec7fe925c1daa0b839ddd6
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129953"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="d635d-103">고객 평생 가치(CLV) 예측 샘플 가이드</span><span class="sxs-lookup"><span data-stu-id="d635d-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="d635d-104">이 가이드를 통해 샘플 데이터를 사용하는 Customer Insights에서 고객 평생 가치(CLV) 예측의 엔드투엔드 예를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="d635d-105">시나리오</span><span class="sxs-lookup"><span data-stu-id="d635d-105">Scenario</span></span>

<span data-ttu-id="d635d-106">Contoso는 고품질 커피 및 커피 머신을 생산하는 회사입니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="d635d-107">Contoso 커피 웹 사이트를 통해 제품을 판매합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="d635d-108">회사는 고객이 향후 12개월 동안 창출할 수 있는 가치(수익)를 파악하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="d635d-109">향후 12개월 동안 고객의 기대 가치를 파악하면 고 가치 고객을 대상으로 마케팅 활동을 진행하는 데 도움이 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d635d-110">필수 조건</span><span class="sxs-lookup"><span data-stu-id="d635d-110">Prerequisites</span></span>

- <span data-ttu-id="d635d-111">대상 그룹 인사이트에서 [Contributor 권한](permissions.md) 이상.</span><span class="sxs-lookup"><span data-stu-id="d635d-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="d635d-112">[새로운 환경에서](manage-environments.md) 다음 단계를 구현하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="d635d-113">작업 1 - 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="d635d-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="d635d-114">[데이터 수집 정보](data-sources.md) 및 [파워 쿼리 커넥터를 사용하여 데이터 원본 가져오기](connect-power-query.md) 문서를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="d635d-115">다음 정보는 사용자가 일반적인 데이터 수집에 익숙하다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="d635d-116">전자상거래 플랫폼에서 고객 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="d635d-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="d635d-117">**전자상거래** 라는 데이터 원본을 만들고 가져오기 옵션을 선택한 다음 **텍스트/CSV** 커넥터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="d635d-118">전자상거래 연락처 URL인 [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts)를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="d635d-119">데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="d635d-120">아래 나열된 열의 데이터 유형을 업데이트하세요.</span><span class="sxs-lookup"><span data-stu-id="d635d-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="d635d-121">**DateOfBirth**: 날짜</span><span class="sxs-lookup"><span data-stu-id="d635d-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="d635d-122">**CreatedOn**: 날짜/시간/영역</span><span class="sxs-lookup"><span data-stu-id="d635d-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="생년월일을 현재로 변환합니다.":::

1. <span data-ttu-id="d635d-124">오른쪽 창의 '이름' 필드에서 데이터 원본의 이름을 **쿼리** 에서 **eCommerceContacts** 로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="d635d-125">데이터 원본을 **저장** 합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="d635d-126">온라인 구매 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="d635d-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="d635d-127">동일한 **전자상거래** 데이터 원본에 다른 데이터 원본을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="d635d-128">**텍스트/CSV** 커넥터를 다시 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="d635d-129">**온라인 구매** 데이터 URL인 https://aka.ms/ciadclassonline을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="d635d-130">데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="d635d-131">아래 나열된 열의 데이터 유형을 업데이트하세요.</span><span class="sxs-lookup"><span data-stu-id="d635d-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="d635d-132">**PurchasedOn**: 날짜/시간</span><span class="sxs-lookup"><span data-stu-id="d635d-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="d635d-133">**TotalPrice**: 통화</span><span class="sxs-lookup"><span data-stu-id="d635d-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="d635d-134">측면 창의 **이름** 필드에서 데이터 원본의 이름을 **쿼리** 에서 **eCommercePurchases** 로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="d635d-135">데이터 원본을 **저장** 합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="d635d-136">충성도 스키마에서 고객 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="d635d-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="d635d-137">**LoyaltyScheme** 이라는 데이터 원본을 만들고 가져오기 옵션을 선택한 다음 **텍스트/CSV** 커넥터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="d635d-138">전자상거래 연락처 URL인 https://aka.ms/ciadclasscustomerloyalty를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="d635d-139">데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="d635d-140">아래 나열된 열의 데이터 유형을 업데이트하세요.</span><span class="sxs-lookup"><span data-stu-id="d635d-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="d635d-141">**DateOfBirth**: 날짜</span><span class="sxs-lookup"><span data-stu-id="d635d-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="d635d-142">**RewardsPoints**: 정수</span><span class="sxs-lookup"><span data-stu-id="d635d-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="d635d-143">**CreatedOn**: 날짜/시간</span><span class="sxs-lookup"><span data-stu-id="d635d-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="d635d-144">오른쪽 창의 **이름** 필드에서 데이터 원본의 이름을 **쿼리** 에서 **loyCustomers** 로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="d635d-145">데이터 원본을 **저장** 합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="d635d-146">웹 사이트 리뷰에서 고객 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="d635d-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="d635d-147">**웹 사이트** 라는 데이터 원본을 만들고 가져오기 옵션을 선택한 다음 **텍스트/CSV** 커넥터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="d635d-148">전자상거래 연락처 URL인 https://aka.ms/CI-ILT/WebReviews를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="d635d-149">데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="d635d-150">아래 나열된 열의 데이터 유형을 업데이트하세요.</span><span class="sxs-lookup"><span data-stu-id="d635d-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="d635d-151">**ReviewRating**: 10진수</span><span class="sxs-lookup"><span data-stu-id="d635d-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="d635d-152">**ReviewDate**: 날짜</span><span class="sxs-lookup"><span data-stu-id="d635d-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="d635d-153">오른쪽 창의 '이름' 필드에서 데이터 원본의 이름을 **쿼리** 에서 **리뷰** 로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="d635d-154">데이터 원본을 **저장** 합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="d635d-155">작업 2 - 데이터 통합</span><span class="sxs-lookup"><span data-stu-id="d635d-155">Task 2 - Data unification</span></span>

<span data-ttu-id="d635d-156">데이터를 수집한 후 이제 데이터 통합 프로세스를 시작하여 통합 고객 프로필을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="d635d-157">자세한 내용은 [데이터 통합](data-unification.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d635d-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="d635d-158">매핑</span><span class="sxs-lookup"><span data-stu-id="d635d-158">Map</span></span>

1. <span data-ttu-id="d635d-159">데이터를 수집한 후 전자상거래 및 충성도 데이터의 연락처를 공통 데이터 유형에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="d635d-160">**데이터** > **통합** > **매핑** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="d635d-161">고객 프로필을 나타내는 엔터티(**eCommerceContacts** 및 **loyCustomers**)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="d635d-162">그런 다음 **적용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-162">Then, select **Apply**.</span></span>

   ![전자상거래와 충성도 데이터 원본을 통합합니다.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="d635d-164">**eCommerceContacts** 의 기본 키로 **ContactId** 를 선택하고 **loyCustomers** 의 기본 키로 **LoyaltyID** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![LoyaltyId를 기본 키로 통합합니다.](media/unify-loyaltyid.png)

1. <span data-ttu-id="d635d-166">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="d635d-167">일치</span><span class="sxs-lookup"><span data-stu-id="d635d-167">Match</span></span>

1. <span data-ttu-id="d635d-168">**일치 탭** 으로 이동한 다음 **순서 설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="d635d-169">**기본** 드롭다운 목록에서 **eCommerceContacts : eCommerce** 를 기본 소스로 선택하고 모든 레코드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-169">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="d635d-170">**엔터티 2** 드롭다운 목록에서 **loyCustomers : LoyaltyScheme** 을 선택하고 모든 레코드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-170">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![전자상거래와 충성도 데이터 원본을 통합합니다.](media/unify-match-order.png)

1. <span data-ttu-id="d635d-172">**규칙 추가** 선택</span><span class="sxs-lookup"><span data-stu-id="d635d-172">Select **Add rule**</span></span>

1. <span data-ttu-id="d635d-173">FullName을 사용하여 첫 번째 조건을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="d635d-174">eCommerceContacts의 경우 **FullName** 드롭다운에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-174">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="d635d-175">loyCustomers의 경우 **FullName** 드롭다운에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-175">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="d635d-176">**정규화** 드롭다운을 선택하고 **유형(전화, 이름, 주소, ...)** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-176">Select the **Normalize** drop-down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="d635d-177">**정밀도 수준**: **기본** 및 **값**: **높음** 을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="d635d-178">새 규칙의 이름에 **FullName, Email** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="d635d-179">**조건 추가** 를 선택하여 이메일 주소에 대한 두 번째 조건을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="d635d-180">엔터티 eCommerceContacts의 경우 드롭다운에서 **이메일** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-180">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="d635d-181">엔터티 loyCustomers의 경우 드롭다운에서 **이메일** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-181">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="d635d-182">정규화를 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="d635d-183">**정밀도 수준**: **기본** 및 **값**: **높음** 을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![이름 및 이메일에 대한 일치 규칙을 통합합니다.](media/unify-match-rule.png)

1. <span data-ttu-id="d635d-185">**완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-185">Select **Done**.</span></span>

1. <span data-ttu-id="d635d-186">**저장** 및 **실행** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="d635d-187">병합</span><span class="sxs-lookup"><span data-stu-id="d635d-187">Merge</span></span>

1. <span data-ttu-id="d635d-188">**병합** 탭으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="d635d-189">**loyCustomers** 엔터티의 **ContactId** 에서 표시 이름을 **ContactIdLOYALTY** 로 변경하여 수집된 다른 ID와 구별합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![포인트 ID에서 contactid의 이름을 바꿉니다.](media/unify-merge-contactid.png)

1. <span data-ttu-id="d635d-191">**저장** 을 선택한 후 **병합 및 다운스트림 프로세스 실행** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="d635d-192">작업 3 - 고객 평생 가치 예측 구성</span><span class="sxs-lookup"><span data-stu-id="d635d-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="d635d-193">통합된 고객 프로필을 통해 이제 고객 평생 가치 예측을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="d635d-194">자세한 단계는 [고객 평생 가치 예측(프리뷰)](predict-customer-lifetime-value.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d635d-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="d635d-195">**인텔리전스**  > **예측** 으로 이동하고 **고객 평생 가치 모델** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="d635d-196">측면 창의 정보를 살펴보고 **시작하기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="d635d-197">모델 이름을 **OOB 전자상거래 CLV 예측** 및 출력 엔터티 **OOBeCommerceCLVPrediction** 로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="d635d-198">CLV 모델에 대한 모델 기본 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="d635d-199">**예측 기간**: **12개월 또는 1년**.</span><span class="sxs-lookup"><span data-stu-id="d635d-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="d635d-200">이 설정은 고객 평생 가치를 예측할 수 있는 미래를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="d635d-201">**활성 고객**: 활성 고객이 비즈니스에 어떤 의미를 갖는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="d635d-202">고객이 활성으로 간주되는 트랜잭션이 하나 이상 있어야 하는 과거 시간 프레임를 설정합니다.으로</span><span class="sxs-lookup"><span data-stu-id="d635d-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="d635d-203">이 모델은 활성 고객에 대한 CLV만 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="d635d-204">모델이 과거 트랜잭션 데이터를 기반으로 기간을 계산하도록 하거나 특정 시간 프레임을 제공하도록 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="d635d-205">이 샘플 가이드에서는 기본 옵션인 **모델이 구매 간격을 계산** 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="d635d-206">**고 가치 고객**: 고 가치 고객을 상위 유료 고객의 백분위수로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="d635d-207">모델은 이 입력을 사용하여 고 가치 고객의 비즈니스 정의에 맞는 결과를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="d635d-208">모델이 고 가치 고객을 정의하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="d635d-209">백분위수를 도출하는 휴리스틱 규칙을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="d635d-210">또한 고 가치 고객을 미래의 상위 유료 고객의 백분위수로 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="d635d-211">이 샘플 가이드에서는 고 가치 고객을 **활성 유료 고객의 상위 30%** 로 수동으로 정의하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="CLV 모델에 대한 가이드 환경의 기본 설정 단계입니다.":::

1. <span data-ttu-id="d635d-213">**필수 데이터** 단계에서 **데이터 추가** 를 선택하여 트랜잭션 내역 데이터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="d635d-214">**eCommercePurchases : eCommerce** 엔터티를 추가하고 모델에 필요한 특성을 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="d635d-215">트랜잭션 ID: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="d635d-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="d635d-216">트랜잭션 날짜: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="d635d-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="d635d-217">트랜잭션 금액: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="d635d-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="d635d-218">제품 ID: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="d635d-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="d635d-219">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-219">Select **Next**.</span></span>

1. <span data-ttu-id="d635d-220">**eCommercePurchases : eCommerce** 엔터티와 **eCommerceContacts : eCommerce** 간의 관계를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="d635d-221">**추가 데이터(선택 사항)** 단계에서는 더 많은 고객 활동 데이터를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="d635d-222">이 데이터는 CLV에 기여할 수 있는 비즈니스와의 고객 상호 작용에 대한 더 많은 인사이트를 얻는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="d635d-223">웹 로그, 고객 서비스 로그 또는 보상 프로그램 내역과 같은 주요 고객 상호 작용을 추가하면 예측의 정확성을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="d635d-224">더 많은 고객 활동 데이터를 포함하려면 **데이터 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="d635d-225">고객 활동 엔터티를 추가하고 해당 필드 이름을 모델에 필요한 해당 필드에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="d635d-226">고객 활동 엔터티: Reviews:Website</span><span class="sxs-lookup"><span data-stu-id="d635d-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="d635d-227">기본 키: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="d635d-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="d635d-228">타임스탬프: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="d635d-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="d635d-229">이벤트(활동 이름): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="d635d-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="d635d-230">세부 정보(금액 또는 값): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="d635d-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="d635d-231">**다음** 을 선택하고 트랜잭션 데이터와 고객 데이터 간의 활동과 관계를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="d635d-232">활동 유형: 기존 선택</span><span class="sxs-lookup"><span data-stu-id="d635d-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="d635d-233">활동 레이블: 리뷰</span><span class="sxs-lookup"><span data-stu-id="d635d-233">Activity label: Review</span></span>
   - <span data-ttu-id="d635d-234">대응 레이블: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="d635d-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="d635d-235">고객 엔터티: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="d635d-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="d635d-236">관계: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="d635d-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="d635d-237">**다음** 을 선택하여 모델 일정을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="d635d-238">모델은 새로운 데이터가 수집될 때 새로운 패턴을 학습하기 위해 정기적으로 학습해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="d635d-239">이 예에서는 **월간** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="d635d-240">모든 세부 정보를 검토한 후 **저장 및 실행** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="d635d-241">작업 4 - 모델 결과 및 설명 검토</span><span class="sxs-lookup"><span data-stu-id="d635d-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="d635d-242">모델이 데이터의 학습 및 채점을 완료하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="d635d-243">다음으로 CLV 모델 결과 및 설명을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="d635d-244">자세한 내용은 [예측 상태 및 결과를 검토](predict-customer-lifetime-value.md#review-prediction-status-and-results)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d635d-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="d635d-245">작업 5 - 고 가치 고객 세그먼트 만들기</span><span class="sxs-lookup"><span data-stu-id="d635d-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="d635d-246">모델을 실행하면 **데이터** > **엔터티** 에 나열된 새 항목이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="d635d-247">모델에서 생성한 엔터티를 기반으로 새 고객 세그먼트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="d635d-248">**세그먼트** 로 이동</span><span class="sxs-lookup"><span data-stu-id="d635d-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="d635d-249">**새로 만들기** 를 선택하고 **다음에서 만들기** > **인텔리전스** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![모델 출력으로 세그먼트 생성.](media/segment-intelligence.png)

1. <span data-ttu-id="d635d-251">**OOBeCommerceCLVPrediction** 엔터티를 선택하고 및 다음과 같이 세그먼트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="d635d-252">필드: CLVScore</span><span class="sxs-lookup"><span data-stu-id="d635d-252">Field: CLVScore</span></span>
  - <span data-ttu-id="d635d-253">연산자: 보다 큼</span><span class="sxs-lookup"><span data-stu-id="d635d-253">Operator: greater than</span></span>
  - <span data-ttu-id="d635d-254">값: 1500</span><span class="sxs-lookup"><span data-stu-id="d635d-254">Value: 1500</span></span>

1. <span data-ttu-id="d635d-255">**리뷰** 를 선택하고 세그먼트를 **저장** 합니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="d635d-256">이제 향후 12개월 동안 $1500 이상의 수익을 창출할 것으로 예측되는 고객을 식별하는 세그먼트를 보유하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="d635d-257">이 세그먼트는 더 많은 데이터가 수집되면 동적으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="d635d-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="d635d-258">자세한 내용은 [세그먼트 만들기 및 관리](segments.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d635d-258">For more information, see [Create and manage segments](segments.md).</span></span>
