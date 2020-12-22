---
title: 트랜잭션 이탈 예측 샘플 가이드
description: 이 샘플 가이드를 사용하여 즉시 사용 가능한 트랜잭션 이탈 예측 모델을 사용해보세요.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 055708ed3f9f468cad83ecf976a460814bf05199
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643601"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="5a744-103">트랜잭션 이탈 예측(미리 보기) 샘플 가이드</span><span class="sxs-lookup"><span data-stu-id="5a744-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="5a744-104">이 가이드는 아래 제공된 데이터를 사용하여 Customer Insights에서 트랜잭션 이탈 예측의 엔드 투 엔드 예를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="5a744-105">이 가이드에 사용된 모든 데이터는 실제 고객 데이터가 아니며 Customer Insights 구독 내 *데모* 환경에 있는 Contoso 데이터 집합의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="5a744-106">시나리오</span><span class="sxs-lookup"><span data-stu-id="5a744-106">Scenario</span></span>

<span data-ttu-id="5a744-107">Contoso는 고품질 커피 및 커피 머신을 생산하는 회사로 Contoso Coffee 웹 사이트를 통해 판매합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="5a744-108">목표는 일반적으로 정기적으로 제품을 구매하는 고객이 향후 60일 동안 활성 고객이 되는 것을 중단할 것인지를 아는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="5a744-109">고객이 **이탈할 가능성이** 있는 고객을 파악하면 고객 유지에 집중하여 마케팅 노력을 절약 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5a744-110">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="5a744-110">Prerequisites</span></span>

- <span data-ttu-id="5a744-111">Customer Insights에 최소한 [기여자 권한](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="5a744-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="5a744-112">[새로운 환경에서](manage-environments.md) 다음 단계를 구현하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="5a744-113">작업 1 - 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="5a744-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="5a744-114">파워 쿼리 커넥터를 사용하여 [데이터 수집](data-sources.md) 및 [데이터 원본 가져오기](connect-power-query.md)에 대한 문서를 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="5a744-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="5a744-115">다음 정보는 사용자가 일반적인 데이터 수집에 익숙하다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="5a744-116">전자상거래 플랫폼에서 고객 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="5a744-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="5a744-117">**전자상거래** 라는 데이터 원본을 만들고 가져오기 옵션을 선택한 다음 **텍스트/CSV** 커넥터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="5a744-118">전자상거래 연락처 URL인 https://aka.ms/ciadclasscontacts를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="5a744-119">데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="5a744-120">아래 나열된 열의 데이터 유형을 업데이트하세요.</span><span class="sxs-lookup"><span data-stu-id="5a744-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="5a744-121">**DateOfBirth**: 날짜</span><span class="sxs-lookup"><span data-stu-id="5a744-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="5a744-122">**CreatedOn**: 날짜/시간/영역</span><span class="sxs-lookup"><span data-stu-id="5a744-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="5a744-123">![날짜로 DoB 전환](media/ecommerce-dob-date.PNG "생년월일을 현재로 변환")</span><span class="sxs-lookup"><span data-stu-id="5a744-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="5a744-124">오른쪽 창의 '이름' 필드에서 데이터 원본의 이름을 **쿼리** 에서 **eCommerceContacts** 로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="5a744-125">데이터 원본을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="5a744-126">온라인 구매 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="5a744-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="5a744-127">동일한 **전자상거래** 데이터 원본에 다른 데이터 원본을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="5a744-128">**텍스트/CSV** 커넥터를 다시 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="5a744-129">**온라인 구매** 데이터 URL인 https://aka.ms/ciadclassonline을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="5a744-130">데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="5a744-131">아래 나열된 열의 데이터 유형을 업데이트하세요.</span><span class="sxs-lookup"><span data-stu-id="5a744-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="5a744-132">**PurchasedOn**: 날짜/시간</span><span class="sxs-lookup"><span data-stu-id="5a744-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="5a744-133">**TotalPrice**: 통화</span><span class="sxs-lookup"><span data-stu-id="5a744-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="5a744-134">오른쪽 창의 '이름' 필드에서 데이터 원본의 이름을 **쿼리** 에서 **eCommercePurchases** 로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-134">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="5a744-135">데이터 원본을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="5a744-136">충성도 스키마에서 고객 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="5a744-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="5a744-137">**LoyaltyScheme** 이라는 데이터 원본을 만들고 가져오기 옵션을 선택한 다음 **텍스트/CSV** 커넥터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="5a744-138">전자상거래 연락처 URL인 https://aka.ms/ciadclasscustomerloyalty를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="5a744-139">데이터를 편집하는 동안 **변환** 을 선택한 다음 **첫 번째 행을 헤더로 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="5a744-140">아래 나열된 열의 데이터 유형을 업데이트하세요.</span><span class="sxs-lookup"><span data-stu-id="5a744-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="5a744-141">**DateOfBirth**: 날짜</span><span class="sxs-lookup"><span data-stu-id="5a744-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="5a744-142">**RewardsPoints**: 정수</span><span class="sxs-lookup"><span data-stu-id="5a744-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="5a744-143">**CreatedOn**: 날짜/시간</span><span class="sxs-lookup"><span data-stu-id="5a744-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="5a744-144">오른쪽 창의 '이름' 필드에서 데이터 원본의 이름을 **쿼리** 에서 **loyCustomers** 로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-144">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="5a744-145">데이터 원본을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="5a744-146">작업 2 - 데이터 통합</span><span class="sxs-lookup"><span data-stu-id="5a744-146">Task 2 - Data unification</span></span>

<span data-ttu-id="5a744-147">데이터를 수집 한 후 이제 **매핑, 일치, 병합** 프로세스를 시작하여 통합 고객 프로필을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="5a744-148">자세한 내용은 [데이터 통합](data-unification.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5a744-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="5a744-149">매핑</span><span class="sxs-lookup"><span data-stu-id="5a744-149">Map</span></span>

1. <span data-ttu-id="5a744-150">데이터를 수집한 후 전자상거래 및 충성도 데이터의 연락처를 공통 데이터 유형에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="5a744-151">**데이터** > **통합** > **매핑** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="5a744-152">고객 프로필을 나타내는 엔터티(**eCommerceContacts** 및 **loyCustomers**)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="전자상거래와 충성도 데이터 원본을 통합합니다.":::

1. <span data-ttu-id="5a744-154">**eCommerceContacts** 의 기본 키로 **ContactId** 를 선택하고 **loyCustomers** 의 기본 키로 **LoyaltyID** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="LoyaltyId를 기본 키로 통합합니다.":::

### <a name="match"></a><span data-ttu-id="5a744-156">일치</span><span class="sxs-lookup"><span data-stu-id="5a744-156">Match</span></span>

1. <span data-ttu-id="5a744-157">**일치 탭** 으로 이동한 다음 **순서 설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="5a744-158">**기본** 드롭다운 목록에서 **eCommerceContacts : eCommerce** 를 기본 소스로 선택하고 모든 레코드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-158">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="5a744-159">**엔터티 2** 드롭다운 목록에서 **loyCustomers : LoyaltyScheme** 을 선택하고 모든 레코드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-159">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="전자상거래와 충성도 데이터 원본을 통합합니다.":::

1. <span data-ttu-id="5a744-161">**새 규칙 만들기** 선택</span><span class="sxs-lookup"><span data-stu-id="5a744-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="5a744-162">FullName을 사용하여 첫 번째 조건을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="5a744-163">eCommerceContacts의 경우 **FullName** 드롭다운에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-163">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="5a744-164">loyCustomers의 경우 **FullName** 드롭다운에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-164">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="5a744-165">**정규화** 드롭다운을 선택하고 **유형(전화, 이름, 주소, ...)** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="5a744-166">**정밀도 수준**: **기본** 및 **값**: **높음** 을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="5a744-167">새 규칙의 이름에 **FullName, Email** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="5a744-168">**조건 추가** 를 선택하여 이메일 주소에 대한 두 번째 조건을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="5a744-169">엔터티 eCommerceContacts의 경우 드롭다운에서 **이메일** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-169">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="5a744-170">엔터티 loyCustomers의 경우 드롭다운에서 **이메일** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-170">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="5a744-171">정규화를 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="5a744-172">**정밀도 수준**: **기본** 및 **값**: **높음** 을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="이름 및 이메일에 대한 일치 규칙을 통합합니다.":::

7. <span data-ttu-id="5a744-174">**저장** 및 **실행** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="5a744-175">병합</span><span class="sxs-lookup"><span data-stu-id="5a744-175">Merge</span></span>

1. <span data-ttu-id="5a744-176">**병합** 탭으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="5a744-177">**loyCustomers** 엔터티의 **ContactId** 에서 표시 이름을 **ContactIdLOYALTY** 로 변경하여 수집된 다른 ID와 구별합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="포인트 ID에서 contactid의 이름을 바꿉니다.":::

1. <span data-ttu-id="5a744-179">**저장** 및 **실행** 을 선택하여 병합 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="5a744-180">작업 3 - 트랜잭션 이탈 구성 예측</span><span class="sxs-lookup"><span data-stu-id="5a744-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="5a744-181">통합된 고객 프로필을 사용하면 이제 구독 이탈 예측을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="5a744-182">자세한 단계는 [구독 이탈 예측(미리보기)](predict-subscription-churn.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a744-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="5a744-183">**인텔리전스** > **검색** 으로 이동하여 **고객 이탈 모델** 을 사용하도록 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="5a744-184">**트랜잭션** 옵션을 선택하고 **시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="5a744-185">모델 이름을 **OOB 전자상거래 트랜잭션 이탈 예측** 과 출력 엔터티 **OOBeCommerceChurnPrediction** 으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="5a744-186">이탈 모델에 대한 두 가지 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="5a744-187">**예측 창**: **최소 60** 일.</span><span class="sxs-lookup"><span data-stu-id="5a744-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="5a744-188">이 설정은 고객 이탈을 얼마나 예측할 것인지 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="5a744-189">**이탈 정의**: **최소 60** 일.</span><span class="sxs-lookup"><span data-stu-id="5a744-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="5a744-190">구매하지 않고 고객이 이탈한 것으로 간주되는 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="모델 레버 예측 창 및 변동 정의를 선택합니다.":::

1. <span data-ttu-id="5a744-192">**구매 기록(필수)** 을 선택하고 구독 기록에 대한 **데이터 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-192">Select **Purchase History (required)** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="5a744-193">**eCommercePurchases : 전자상거래** 추가 엔터티를 추가하고 전자상거래의 필드를 모델에 필요한 해당 필드에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="5a744-194">**eCommercePurchases : 전자상거래** 엔터티와 **eCommerceContacts : 전자상거래** 에 가입하세요.</span><span class="sxs-lookup"><span data-stu-id="5a744-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="전자상거래 엔터티에 가입하세요.":::

1. <span data-ttu-id="5a744-196">**다음** 을 선택하여 모델 일정을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="5a744-197">모델은 수집된 새 데이터가 있을 때 새로운 패턴을 학습하기 위해 정기적으로 학습해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="5a744-198">이 예에서는 **월별** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="5a744-199">모든 세부 정보를 검토한 후 **저장 및 실행** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="5a744-200">작업 4 - 모델 결과 및 설명 검토</span><span class="sxs-lookup"><span data-stu-id="5a744-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="5a744-201">모델이 데이터의 학습 및 채점을 완료하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="5a744-202">이제 구독 이탈 모델 설명을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="5a744-203">자세한 내용은 [예측 상태 및 결과를 검토](predict-subscription-churn.md#review-a-prediction-status-and-results)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a744-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="5a744-204">작업 5 - 이탈 위험이 높은 고객 세그먼트 생성</span><span class="sxs-lookup"><span data-stu-id="5a744-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="5a744-205">프로덕션 모델을 실행하면 **데이터** > **엔티티** 에서 볼 수 있는 새 엔티티가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="5a744-206">모델에서 생성한 엔터티를 기반으로 새 세그먼트를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="5a744-207">**세그먼트** 로 이동</span><span class="sxs-lookup"><span data-stu-id="5a744-207">Go to **Segments**.</span></span> <span data-ttu-id="5a744-208">**새로 만들기** 를 **만들기** > **인텔리전스** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="모델 출력으로 세그먼트 생성.":::

1. <span data-ttu-id="5a744-210">**OOBSubscriptionChurnPrediction** 엔드포인트를 선택하고 세그먼트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="5a744-211">필드: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="5a744-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="5a744-212">연산자: 보다 큼</span><span class="sxs-lookup"><span data-stu-id="5a744-212">Operator: greater than</span></span>
   - <span data-ttu-id="5a744-213">값: 0.6</span><span class="sxs-lookup"><span data-stu-id="5a744-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="구독 이탈 세그먼트를 설정합니다.":::

<span data-ttu-id="5a744-215">이제 이 구독 비즈니스에 대해 이탈 위험이 높은 고객을 식별하는 동적으로 업데이트되는 세그먼트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a744-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="5a744-216">자세한 내용은 [세그먼트 만들기 및 관리](segments.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a744-216">For more information, see [Create and manage segments](segments.md).</span></span>
