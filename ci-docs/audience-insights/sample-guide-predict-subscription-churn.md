---
title: 구독 이탈 예측 샘플 가이드
description: 이 샘플 가이드를 사용하여 즉시 사용 가능한 구독 이탈 예측 모델을 사용해보세요.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2537cfb5dde0d1ce1af16f585f0bf91d15ea1870
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "4653988"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="f0e5e-103">구독 이탈 예측(미리 보기) 샘플 가이드</span><span class="sxs-lookup"><span data-stu-id="f0e5e-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="f0e5e-104">아래 제공된 샘플 데이터를 사용하여 구독 이탈 예측의 엔드 투 엔드 예를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="f0e5e-105">시나리오</span><span class="sxs-lookup"><span data-stu-id="f0e5e-105">Scenario</span></span>

<span data-ttu-id="f0e5e-106">Contoso는 고품질 커피 및 커피 머신을 생산하는 회사로 Contoso Coffee 웹 사이트를 통해 판매합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="f0e5e-107">최근에는 고객이 정기적으로 커피를 마실 수 있도록 구독 사업을 시작했습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="f0e5e-108">목표는 어떤 구독 고객이 앞으로 몇 달 안에 구독을 취소할 수 있는지 파악하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="f0e5e-109">고객이 **이탈할 가능성이** 있는 고객을 파악하면 고객 유지에 집중하여 마케팅 노력을 절약 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f0e5e-110">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="f0e5e-110">Prerequisites</span></span>

- <span data-ttu-id="f0e5e-111">Customer Insights에 최소한 [기여자 권한](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f0e5e-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="f0e5e-112">[새로운 환경에서](manage-environments.md) 다음 단계를 구현하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="f0e5e-113">작업 1 - 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="f0e5e-113">Task 1 - Ingest Data</span></span>

<span data-ttu-id="f0e5e-114">파워 쿼리 커넥터를 사용하여 [데이터 수집](data-sources.md) 및 [데이터 원본 가져오기](connect-power-query.md)에 대한 문서를 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="f0e5e-115">다음 정보는 사용자가 일반적인 데이터 수집에 익숙하다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="f0e5e-116">전자상거래 플랫폼에서 고객 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="f0e5e-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="f0e5e-117">**전자상거래** 라는 데이터 원본을 만들고 가져오기 옵션을 선택한 다음 **텍스트/CSV** 커넥터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="f0e5e-118">전자상거래 연락처 URL인 https://aka.ms/ciadclasscontacts를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="f0e5e-119">데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="f0e5e-120">아래 나열된 열의 데이터 유형을 업데이트하세요.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="f0e5e-121">**DateOfBirth**: 날짜</span><span class="sxs-lookup"><span data-stu-id="f0e5e-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="f0e5e-122">**CreatedOn**: 날짜/시간/영역</span><span class="sxs-lookup"><span data-stu-id="f0e5e-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="f0e5e-123">![날짜로 DoB 전환](media/ecommerce-dob-date.PNG "생년월일을 현재로 변환")</span><span class="sxs-lookup"><span data-stu-id="f0e5e-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="f0e5e-124">오른쪽 창의 '이름' 필드에서 데이터 원본의 이름을 **쿼리** 에서 **eCommerceContacts** 로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="f0e5e-125">데이터 원본을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="f0e5e-126">충성도 스키마에서 고객 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="f0e5e-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="f0e5e-127">**LoyaltyScheme** 이라는 데이터 원본을 만들고 가져오기 옵션을 선택한 다음 **텍스트/CSV** 커넥터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="f0e5e-128">전자상거래 연락처 URL인 https://aka.ms/ciadclasscustomerloyalty를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="f0e5e-129">데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="f0e5e-130">아래 나열된 열의 데이터 유형을 업데이트하세요.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="f0e5e-131">**DateOfBirth**: 날짜</span><span class="sxs-lookup"><span data-stu-id="f0e5e-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="f0e5e-132">**RewardsPoints**: 정수</span><span class="sxs-lookup"><span data-stu-id="f0e5e-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="f0e5e-133">**CreatedOn**: 날짜/시간</span><span class="sxs-lookup"><span data-stu-id="f0e5e-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="f0e5e-134">오른쪽 창의 '이름' 필드에서 데이터 원본의 이름을 **쿼리** 에서 **loyCustomers** 로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-134">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="f0e5e-135">데이터 원본을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="f0e5e-136">구독 정보 수집</span><span class="sxs-lookup"><span data-stu-id="f0e5e-136">Ingest subscription information</span></span>

1. <span data-ttu-id="f0e5e-137">**SubscriptionHistory** 이라는 데이터 원본을 만들고 가져오기 옵션을 선택한 다음 **텍스트/CSV** 커넥터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="f0e5e-138">전자상거래 연락처 URL인 https://aka.ms/ciadchurnsubscriptionhistory를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="f0e5e-139">데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="f0e5e-140">아래 나열된 열의 데이터 유형을 업데이트하세요.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="f0e5e-141">**SubscriptioID**: 정수</span><span class="sxs-lookup"><span data-stu-id="f0e5e-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="f0e5e-142">**SubscriptionAmount**: 통화</span><span class="sxs-lookup"><span data-stu-id="f0e5e-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="f0e5e-143">**SubscriptionEndDate**: 날짜/시간</span><span class="sxs-lookup"><span data-stu-id="f0e5e-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="f0e5e-144">**SubscriptionStartDate**: 날짜/시간</span><span class="sxs-lookup"><span data-stu-id="f0e5e-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="f0e5e-145">**TransactionDate**: 날짜/시간</span><span class="sxs-lookup"><span data-stu-id="f0e5e-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="f0e5e-146">**IsRecurring**: 참/거짓</span><span class="sxs-lookup"><span data-stu-id="f0e5e-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="f0e5e-147">**Is_auto_renew**: 참/거짓</span><span class="sxs-lookup"><span data-stu-id="f0e5e-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="f0e5e-148">**RecurringFrequencyInMonths**: 정수</span><span class="sxs-lookup"><span data-stu-id="f0e5e-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="f0e5e-149">오른쪽 창의 '이름' 필드에서 데이터 원본의 이름을 **쿼리** 에서 **SubscriptionHistory** 로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-149">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="f0e5e-150">데이터 원본을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="f0e5e-151">웹 사이트 리뷰에서 고객 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="f0e5e-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="f0e5e-152">**웹 사이트** 라는 데이터 원본을 만들고 가져오기 옵션을 선택한 다음 **텍스트/CSV** 커넥터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="f0e5e-153">전자상거래 연락처 URL인 https://aka.ms/ciadclasswebsite를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="f0e5e-154">데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="f0e5e-155">아래 나열된 열의 데이터 유형을 업데이트하세요.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="f0e5e-156">**ReviewRating**: 정수</span><span class="sxs-lookup"><span data-stu-id="f0e5e-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="f0e5e-157">**ReviewDate**: 날짜</span><span class="sxs-lookup"><span data-stu-id="f0e5e-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="f0e5e-158">오른쪽 창의 '이름' 필드에서 데이터 원본의 이름을 **쿼리** 에서 **webReviews** 로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="f0e5e-159">작업 2 - 데이터 통합</span><span class="sxs-lookup"><span data-stu-id="f0e5e-159">Task 2 - Data unification</span></span>

<span data-ttu-id="f0e5e-160">데이터를 수집 한 후 이제 **매핑, 일치, 병합** 프로세스를 시작하여 통합 고객 프로필을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="f0e5e-161">자세한 내용은 [데이터 통합](data-unification.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="f0e5e-162">매핑</span><span class="sxs-lookup"><span data-stu-id="f0e5e-162">Map</span></span>

1. <span data-ttu-id="f0e5e-163">데이터를 수집한 후 전자상거래 및 충성도 데이터의 연락처를 공통 데이터 유형에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="f0e5e-164">**데이터** > **통합** > **매핑** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="f0e5e-165">고객 프로필을 나타내는 엔터티(**eCommerceContacts** 및 **loyCustomers**)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="전자상거래와 충성도 데이터 원본을 통합합니다.":::

1. <span data-ttu-id="f0e5e-167">**eCommerceContacts** 의 기본 키로 **ContactId** 를 선택하고 **loyCustomers** 의 기본 키로 **LoyaltyID** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="LoyaltyId를 기본 키로 통합합니다.":::

### <a name="match"></a><span data-ttu-id="f0e5e-169">일치</span><span class="sxs-lookup"><span data-stu-id="f0e5e-169">Match</span></span>

1. <span data-ttu-id="f0e5e-170">**일치 탭** 으로 이동한 다음 **순서 설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="f0e5e-171">**기본** 드롭다운 목록에서 **eCommerceContacts : eCommerce** 를 기본 소스로 선택하고 모든 레코드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="f0e5e-172">**엔터티 2** 드롭다운 목록에서 **loyCustomers : LoyaltyScheme** 을 선택하고 모든 레코드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="전자상거래와 충성도 데이터 원본을 통합합니다.":::

1. <span data-ttu-id="f0e5e-174">**새 규칙 만들기** 선택</span><span class="sxs-lookup"><span data-stu-id="f0e5e-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="f0e5e-175">FullName을 사용하여 첫 번째 조건을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="f0e5e-176">eCommerceContacts의 경우 **FullName** 드롭다운에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="f0e5e-177">loyCustomers의 경우 **FullName** 드롭다운에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="f0e5e-178">**정규화** 드롭다운을 선택하고 **유형(전화, 이름, 주소, ...)** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="f0e5e-179">**정밀도 수준**: **기본** 및 **값**: **높음** 을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="f0e5e-180">새 규칙의 이름에 **FullName, Email** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="f0e5e-181">**조건 추가** 를 선택하여 이메일 주소에 대한 두 번째 조건을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="f0e5e-182">엔터티 eCommerceContacts의 경우 드롭다운에서 **이메일** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="f0e5e-183">엔터티 loyCustomers의 경우 드롭다운에서 **이메일** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="f0e5e-184">정규화를 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="f0e5e-185">**정밀도 수준**: **기본** 및 **값**: **높음** 을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="이름 및 이메일에 대한 일치 규칙을 통합합니다.":::

7. <span data-ttu-id="f0e5e-187">**저장** 및 **실행** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="f0e5e-188">병합</span><span class="sxs-lookup"><span data-stu-id="f0e5e-188">Merge</span></span>

1. <span data-ttu-id="f0e5e-189">**병합** 탭으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="f0e5e-190">**loyCustomers** 엔터티의 **ContactId** 에서 표시 이름을 **ContactIdLOYALTY** 로 변경하여 수집된 다른 ID와 구별합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="포인트 ID에서 contactid의 이름을 바꿉니다.":::

1. <span data-ttu-id="f0e5e-192">**저장** 및 **실행** 을 선택하여 병합 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="f0e5e-193">작업 3 - 구독 이탈 구성 예측</span><span class="sxs-lookup"><span data-stu-id="f0e5e-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="f0e5e-194">통합된 고객 프로필을 사용하면 이제 구독 이탈 예측을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="f0e5e-195">자세한 단계는 [구독 이탈 예측(미리보기)](predict-subscription-churn.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="f0e5e-196">**인텔리전스** > **검색** 으로 이동하여 **고객 이탈 모델** 을 사용하도록 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="f0e5e-197">**구독** 옵션을 선택하고 **시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="f0e5e-198">모델 이름을 **OOB 구독 이탈 예측** 과 출력 엔터티 **OOBSubscriptionChurnPrediction** 으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="f0e5e-199">이탈 모델에 대한 두 가지 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="f0e5e-200">**구독 종료 이후 일수**: **최소 60** 일.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="f0e5e-201">고객이 구독이 종료된 이후 이 기간 동안 구독을 갱신하지 않으면 이탈된 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="f0e5e-202">**이탈 정의**: **최소 93** 일.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="f0e5e-203">모델이 이탈 할 수 있는 고객을 예측하는 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="f0e5e-204">앞으로 더 멀어질수록 결과의 정확도가 떨어집니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="모델 레버 예측 창 및 변동 정의를 선택합니다.":::

1. <span data-ttu-id="f0e5e-206">**필수 데이터 추가** 를 선택하고 구독 기록에 대한 **데이터 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="f0e5e-207">**Subscription : SubscriptionHistory** 추가 엔터티를 추가하고 전자상거래의 필드를 모델에 필요한 해당 필드에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="f0e5e-208">**eCommerceContacts : eCommerce** 와 함께 **Subscription : SubscriptionHistory** 엔터티에 가입하고 관계 이름을 **eCommerceSubscription** 으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="전자상거래 엔터티에 가입하세요.":::

1. <span data-ttu-id="f0e5e-210">고객 활동 아래 **webReviews : Website** 엔터티를 추가하고 webReviews의 필드를 모델에 필요한 해당 필드에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="f0e5e-211">기본 키: ReviewId</span><span class="sxs-lookup"><span data-stu-id="f0e5e-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="f0e5e-212">타임스탬프: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="f0e5e-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="f0e5e-213">이벤트: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="f0e5e-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="f0e5e-214">웹 사이트 검토를 위한 활동을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="f0e5e-215">활동 **검토** 를 선택하고 **eCommerceContacts : eCommerce** 와 함께 **webReviews : Website** 엔티티에 참여하세요.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="f0e5e-216">**다음** 을 선택하여 모델 일정을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="f0e5e-217">모델은 수집된 새 데이터가 있을 때 새로운 패턴을 학습하기 위해 정기적으로 학습해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="f0e5e-218">이 예에서는 **월별** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="f0e5e-219">모든 세부 정보를 검토한 후 **저장 및 실행** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="f0e5e-220">작업 4 - 모델 결과 및 설명 검토</span><span class="sxs-lookup"><span data-stu-id="f0e5e-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="f0e5e-221">모델이 데이터의 학습 및 채점을 완료하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="f0e5e-222">이제 구독 이탈 모델 설명을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="f0e5e-223">자세한 내용은 [예측 상태 및 결과를 검토](predict-subscription-churn.md#review-a-prediction-status-and-results)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="f0e5e-224">작업 5 - 이탈 위험이 높은 고객 세그먼트 생성</span><span class="sxs-lookup"><span data-stu-id="f0e5e-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="f0e5e-225">프로덕션 모델을 실행하면 **데이터** > **엔티티** 에서 볼 수 있는 새 엔티티가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="f0e5e-226">모델에서 생성한 엔터티를 기반으로 새 세그먼트를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="f0e5e-227">**세그먼트** 로 이동</span><span class="sxs-lookup"><span data-stu-id="f0e5e-227">Go to **Segments**.</span></span> <span data-ttu-id="f0e5e-228">**새로 만들기** 를 **만들기** > **인텔리전스** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="모델 출력으로 세그먼트 생성.":::

1. <span data-ttu-id="f0e5e-230">**OOBSubscriptionChurnPrediction** 엔드포인트를 선택하고 세그먼트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="f0e5e-231">필드: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="f0e5e-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="f0e5e-232">연산자: 보다 큼</span><span class="sxs-lookup"><span data-stu-id="f0e5e-232">Operator: greater than</span></span>
   - <span data-ttu-id="f0e5e-233">값: 0.6</span><span class="sxs-lookup"><span data-stu-id="f0e5e-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="구독 이탈 세그먼트를 설정합니다.":::

<span data-ttu-id="f0e5e-235">이제 이 구독 비즈니스에 대해 이탈 위험이 높은 고객을 식별하는 동적으로 업데이트되는 세그먼트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="f0e5e-236">자세한 내용은 [세그먼트 만들기 및 관리](segments.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-236">For more information, see [Create and manage segments](segments.md).</span></span>
