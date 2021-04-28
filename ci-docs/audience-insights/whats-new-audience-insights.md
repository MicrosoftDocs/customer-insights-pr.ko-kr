---
title: 신규 및 향후 기능
description: 새로운 기능, 개선 사항 및 버그 수정에 대한 정보입니다.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 2159481f9355de738a7b457dcf0849a45c3e08db
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896243"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a><span data-ttu-id="95587-103">Dynamics 365 Customer Insights 대상 그룹 인사이트의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="95587-103">What's new in the audience insights capability of Dynamics 365 Customer Insights</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="95587-104">최신 업데이트를 발표하게 된 것을 기쁘게 생각합니다!</span><span class="sxs-lookup"><span data-stu-id="95587-104">We're excited to announce our newest updates!</span></span> <span data-ttu-id="95587-105">이 문서는 공개 미리 보기 기능, 일반 가용성 향상 및 기능 업데이트를 요약합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-105">This article summarizes public preview features, general availability enhancements, and feature updates.</span></span> <span data-ttu-id="95587-106">장기적인 기능 계획을 보려면 [Dynamics 365 및 Power Platform 릴리스 계획](/dynamics365/release-plans/)을 살펴보십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-106">To see the long-term feature plans, take a look at the [Dynamics 365 and Power Platform release plans](/dynamics365/release-plans/).</span></span>

<span data-ttu-id="95587-107">업데이트는 지역별로 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-107">We roll out updates on a region-by-region basis.</span></span> <span data-ttu-id="95587-108">따라서 특정 지역은 다른 지역보다 먼저 기능을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-108">So certain regions might see features before others.</span></span> <span data-ttu-id="95587-109">다르게 지정하지 않으면 별도의 조치를 취할 필요가 없으며 가동 중지 시간 없이 자동으로 앱을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-109">Unless specified differently, you don't need to take any action and we'll update the app automatically with no downtime.</span></span>

> [!TIP]
> <span data-ttu-id="95587-110">기능 요청 및 제품 제안에 대한 투표를 제출하려면 [Dynamics 365 응용 프로그램 아이디어 포털](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights)로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-110">To submit and vote on feature requests and product suggestions, go to the [Dynamics 365 Application Ideas portal](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).</span></span>

## <a name="march-2021-updates"></a><span data-ttu-id="95587-111">2021년 3월 업데이트</span><span class="sxs-lookup"><span data-stu-id="95587-111">March 2021 updates</span></span>

<span data-ttu-id="95587-112">2021년 3월 업데이트에는 여러 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="95587-112">The updates in March 2021 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="activities"></a><span data-ttu-id="95587-113">활동 </span><span class="sxs-lookup"><span data-stu-id="95587-113">Activities</span></span>

- <span data-ttu-id="95587-114">**활동 마법사 및 의미 유형** 활동 매핑 생성을 안내하고 단순화하기 위해 활동 매핑 경험을 개선하고 업데이트했습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-114">**Activity wizard and semantic types** We have improved and updated our activity mapping experience to guide and simplify the creation of activity mapping.</span></span> <span data-ttu-id="95587-115">이 새로운 경험에서 사용자는 프로세스의 각 단계를 완료하는 데 도움이되는 안내식 경험을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95587-115">In this new experience, users get a guided experience to help completing of each step of the process.</span></span> <span data-ttu-id="95587-116">활동 매핑 단계에서 사용자는 다양한 활동 유형 중에서 선택하는 것 외에도 *구독* 및/또는 *SalesOrderLine* 를 위한 데이터를 산업 표준 스키마에 의미론적으로 매핑할 수 있으며 이는 다운스트림 소비에 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-116">At the activity mapping step, in addition to choosing from many activity types, the user can choose to semantically map data for *Subscription* and/or *SalesOrderLine* to industry standard schemas, which can be used for downstream consumption.</span></span>    
  <span data-ttu-id="95587-117">자세한 내용은 [고객 활동](activities.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-117">For more information, see [Customer activities](activities.md).</span></span>

### <a name="data-ingestion"></a><span data-ttu-id="95587-118">데이터 수집</span><span class="sxs-lookup"><span data-stu-id="95587-118">Data ingestion</span></span>

- <span data-ttu-id="95587-119">**Power Platform 데이터 흐름 및 게이트웨이를 사용하여 온-프레미스 데이터 소스에 연결** Customer Insights의 게이트웨이와 Power Platform 또는 Dataverse 연결된 환경을 사용하는 Power Platform 데이터 흐름 및 온-프레미스 연결 프리뷰를 발표하게 되어 기쁘게 생각합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-119">**Connect to on-premises data sources using Power Platform dataflows and gateways** We are pleased to announce the preview of Power Platform dataflows and on-premises connectivity using gateways in Customer Insights with an associated Power Platform or Dataverse environment.</span></span> <span data-ttu-id="95587-120">연결된 Dataverse 환경이 있는 Customer Insights 환경에서 생성된 모든 새 데이터 소스는 환경은 기본적으로 온-프레미스 데이터 연결과 풍부한 커넥터 및 변환 기능을 제공하는 Power Platform 데이터 흐름으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="95587-120">Any new data sources created in a Customer Insights environment with a linked Dataverse environment will default to Power Platform dataflows bringing in the on-premises data connectivity and a rich set of connectors and transformation capabilities.</span></span>

### <a name="extensibility"></a><span data-ttu-id="95587-121">확장성</span><span class="sxs-lookup"><span data-stu-id="95587-121">Extensibility</span></span>

- <span data-ttu-id="95587-122">**연결 및 내보내기로 구성된 내보내기** **내보내기 대상** 페이지에서 **연결** 로 이름을 바꾸고 **내보내기** 를 위한 별도의 페이지를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-122">**Exports organized in connections and exports** We have changed the name of the **Export destinations** page to **Connections** and added a separate page for **Exports**.</span></span> <span data-ttu-id="95587-123">이 업데이트의 일부로 기존 내보내기를 연결 쌍과 해당 연결을 사용하는 내보내기 쌍으로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-123">As part of this update, we'll transition existing exports into pairs of a connection and an export using that connection.</span></span> <span data-ttu-id="95587-124">관리자는 이제 **연결** 페이지에서 외부로 나가는 데이터를 보다 명확하게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-124">Administrators now have more clarity over outgoing data on the **Connections** page.</span></span> <span data-ttu-id="95587-125">모든 사용자 역할은 **수출** 페이지에 액세스 권한이 있지만 관리자만 기여자가 공유 연결을 사용하여 특정 내보내기를 편집할 수 있도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-125">All user roles have access to the **Exports** page, but only administrators can choose to allow contributors to edit specific exports with shared connections.</span></span>     
  <span data-ttu-id="95587-126">자세한 내용은 [연결 개요](connections.md) 및 [수출 개요](export-destinations.md)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-126">For more information, see [Connections overview](connections.md) and [Exports overview](export-destinations.md).</span></span>

- <span data-ttu-id="95587-127">**Campaign Monitor로 세그먼트 내보내기** Campaign Monitor를 포함하도록 내보내기 대상을 확장했습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-127">**Export segments to Campaign Monitor** We have extended our export destinations to include Campaign Monitor.</span></span> <span data-ttu-id="95587-128">이제 Customer Insights에서 Campaign Monitor 목록으로 세그먼트를 내보내고 이를 마케팅 캠페인의 기준으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-128">You can now export segments from Customer Insights to Campaign Monitor lists and use them as the baseline for your marketing campaigns.</span></span>    
   <span data-ttu-id="95587-129">자세한 내용은 [Campaign Monitor로 내보내기](export-campaign-monitor.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-129">For more information, see [Export to Campaign Monitor](export-campaign-monitor.md).</span></span>

- <span data-ttu-id="95587-130">**Constant Contact로 세그먼트 내보내기** Constant Contact를 포함하도록 내보내기 대상을 확장했습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-130">**Export segments to Constant Contact** We have extended our export destinations to include Constant Contact.</span></span> <span data-ttu-id="95587-131">이제 Customer Insights에서 Constant Contact 목록으로 세그먼트를 내보내고 이를 마케팅 캠페인의 기준으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-131">You can now export segments from Customer Insights to Constant Contact lists and use them as the baseline for your marketing campaigns.</span></span>   
   <span data-ttu-id="95587-132">자세한 내용은 [Constant Contact로 내보내기](export-constant-contact.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-132">For more information, see [Export to Constant Contact](export-constant-contact.md).</span></span>

- <span data-ttu-id="95587-133">**RollWorks로 세그먼트 내보내기** RollWorks를 포함하도록 내보내기 대상을 확장했습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-133">**Export segments to RollWorks** We have extended our export destinations to include RollWorks.</span></span> <span data-ttu-id="95587-134">이제 Customer Insights에서 RollWorks 대상으로 세그먼트를 내보내고 이를 B2B 광고의 기준으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-134">You can now export segments from Customer Insights to RollWorks audiences and use them as the baseline for your B2B advertising.</span></span>    
   <span data-ttu-id="95587-135">자세한 내용은 [RollWorks로 데이터 내보내기](export-rollworks.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-135">For more information, see [Export to RollWorks ](export-rollworks.md).</span></span>

- <span data-ttu-id="95587-136">**Snapchat으로 세그먼트 내보내기** Snapchat을 포함하도록 내보내기 대상을 확장했습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-136">**Export segments to Snapchat** We have extended our export destinations to include Snapchat.</span></span> <span data-ttu-id="95587-137">이제 Customer Insights에서 Snapchat 대상으로 세그먼트를 내보내고 이를 광고의 기준으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-137">You can now export segments from Customer Insights to Snapchat audiences and use them as the baseline for your advertising.</span></span>     
   <span data-ttu-id="95587-138">자세한 내용은 [Snapchat으로 데이터 내보내기](export-snapchat.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-138">For more information, see [Export to Snapchat](export-snapchat.md).</span></span>

### <a name="predictions"></a><span data-ttu-id="95587-139">예측</span><span class="sxs-lookup"><span data-stu-id="95587-139">Predictions</span></span>

- <span data-ttu-id="95587-140">**예측 제품 추천에 제품 필터 사용** 제품 추천 모델에 제품 필터를 사용하는 기능을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-140">**Use product filters in predictive product recommendations** We have added the capability to use product filters in our product recommendation model.</span></span> <span data-ttu-id="95587-141">이제 제품의 하위 집합만 사용하는 예측을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-141">You can now create a prediction that uses only a subset of your products.</span></span>    
   <span data-ttu-id="95587-142">자세한 내용은 [제품 필터 구성](predict-product-recommendation.md#configure-product-filters)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-142">For more information, see [Configure product filters](predict-product-recommendation.md#configure-product-filters).</span></span>

- <span data-ttu-id="95587-143">**모델 예측에서 세그먼트 만들기** 예측 모델의 결과를 사용하여 세그먼트를 만드는 빠른 방법을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-143">**Create segments from model predictions** We have added a quick way to create segments using the results of a prediction model.</span></span> <span data-ttu-id="95587-144">모델 결과 페이지에서 **세그먼트 만들기** 옵션을 선택하여 쉽게 새 세그먼트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-144">From the model results page, you can easily create a new segment by selecting the new **Create segment** option.</span></span>    
  <span data-ttu-id="95587-145">자세한 내용은 [예측 모델을 기반으로 세그먼트 만들기](prediction-based-segment.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-145">For more information, see [Create a segment based on a prediction model](prediction-based-segment.md).</span></span>

- <span data-ttu-id="95587-146">**제품 추천에 대한 설명** 제품 권장 사항을 생성하기 위해 AI 모델에서 학습한 주요 요소와 이러한 요소가 제품 권장 사항에 기여하는 정도를 설명하는 정보를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-146">**Explanations for product recommendations** We have added information explaining the key factors learned by the AI model to generate product recommendations and the degree to which those factors contribute towards the product recommendations.</span></span> <span data-ttu-id="95587-147">이 정보는 모델 결과 화면에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="95587-147">This information is added to the model results screen.</span></span>    
   <span data-ttu-id="95587-148">자세한 내용은 [예측 상태 및 결과를 검토](predict-product-recommendation.md#review-a-prediction-status-and-results)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-148">For more information, see [Review a prediction status and results](predict-product-recommendation.md#review-a-prediction-status-and-results).</span></span>

## <a name="february-2021-updates"></a><span data-ttu-id="95587-149">2021년 2월 업데이트</span><span class="sxs-lookup"><span data-stu-id="95587-149">February 2021 updates</span></span>

<span data-ttu-id="95587-150">2021년 2월 업데이트에는 여러 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="95587-150">The updates in February 2021 include several features, performance upgrades, and bug fixes.</span></span>

#### <a name="extensibility"></a><span data-ttu-id="95587-151">확장성</span><span class="sxs-lookup"><span data-stu-id="95587-151">Extensibility</span></span>

- <span data-ttu-id="95587-152">**AdRoll로 세그먼트 내보내기**</span><span class="sxs-lookup"><span data-stu-id="95587-152">**Export segments to AdRoll**</span></span>

  <span data-ttu-id="95587-153">AdRoll을 포함하도록 내보내기 대상을 확장했습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-153">We have extended our export destinations to include AdRoll.</span></span> <span data-ttu-id="95587-154">이제 Customer Insights에서 AdRoll 대상 그룹으로 세그먼트를 내보내고 이를 광고의 기준으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-154">You can now export segments from Customer Insights to AdRoll audiences and use them as the baseline for your advertising.</span></span> <span data-ttu-id="95587-155">자세한 내용은 [AdRoll용 커네터](export-adroll.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-155">For more information, see [Connector for AdRoll](export-adroll.md).</span></span>

#### <a name="segments"></a><span data-ttu-id="95587-156">세그먼트</span><span class="sxs-lookup"><span data-stu-id="95587-156">Segments</span></span>
 
- <span data-ttu-id="95587-157">**중복 항목 만들기**</span><span class="sxs-lookup"><span data-stu-id="95587-157">**Duplicate a segment**</span></span>
  
  <span data-ttu-id="95587-158">기존 세그먼트를 기반으로 새 세그먼트를 만들려면 이제 세그먼트를 복제하고 복제된 세그먼트를 편집하여 더 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-158">To create a new segment based on an existing one, you can now duplicate a segment and edit the duplicated segment to refine it further.</span></span> 

- <span data-ttu-id="95587-159">**세그먼트에 추가 속성 추가**</span><span class="sxs-lookup"><span data-stu-id="95587-159">**Add additional attributes to a segment**</span></span>

  <span data-ttu-id="95587-160">이제 이러한 속성이 고객 프로필의 일부가 아닌 경우에도 세그먼트 출력에 특성을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-160">You can now include attributes in your segment output, even if these attributes are not part of the customer profile.</span></span> <span data-ttu-id="95587-161">예를 들어, 고객 엔터티와M:1 관계가 있는 구독 엔터티의 일부인 경우에도 세그먼트에 구독 ID를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-161">For example, include subscription IDs in a segment even though it is part of the subscription entity that has a M:1 relation with the customer entity.</span></span> <span data-ttu-id="95587-162">특성이 고객 엔터티와 관련된 엔터티에 속하는 한 이제 이러한 특성을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-162">As long as the attribute belongs to an entity related to the customer entity you can now include these attributes.</span></span>  

#### <a name="predictions"></a><span data-ttu-id="95587-163">예측</span><span class="sxs-lookup"><span data-stu-id="95587-163">Predictions</span></span>

- <span data-ttu-id="95587-164">**예측 제품 추천 만들기**</span><span class="sxs-lookup"><span data-stu-id="95587-164">**Create predictive product recommendations**</span></span>

  <span data-ttu-id="95587-165">고객이 구매에 관심을 갖는 것이 무엇인지 이해하는 것은 개인 설정 및 참여를 통해 비즈니스 수익을 개선하고 고객 충성도를 구축하는 데 필요한 첫 번째 단계 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="95587-165">Understanding what customers are interested in purchasing is one of the first steps needed to improve business revenue and build customer loyalty through personalization and engagement.</span></span> <span data-ttu-id="95587-166">고객의 관심사에 맞지 않는 제품에 대한 추천을 제공하면 고객과 비즈니스 사이에 단절감이 생길 수 있으며 궁극적으로 고객의 전반적인 잠재적 수익과 경험을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-166">Providing recommendations for products that aren’t aligned to your customer’s interests can create a sense of disconnect between the customer and your business, and ultimately limit the overall potential revenue and experience for a customer.</span></span> 

  <span data-ttu-id="95587-167">자체 데이터를 사용하여 이제 고객이 미래에 구매할 가능성이 있는 제품에 대한 예측을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-167">Using your own data, you can now create predictions for what products your customers are likely to purchase in the future.</span></span> <span data-ttu-id="95587-168">자세한 내용은 [제품 추천 예측](predict-product-recommendation.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-168">For more information, see [Product recommendation prediction](predict-product-recommendation.md).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="95587-169">시스템 관리</span><span class="sxs-lookup"><span data-stu-id="95587-169">System administration</span></span>

- <span data-ttu-id="95587-170">**복사 환경은 더 많은 유형의 데이터 원본을 지원함**</span><span class="sxs-lookup"><span data-stu-id="95587-170">**Copy environment support more types of data sources**</span></span>

  <span data-ttu-id="95587-171">관리자는 동일한 조직의 새 환경에 환경 구성을 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-171">Admins can copy environment configurations to a new environment in the same organization.</span></span> <span data-ttu-id="95587-172">이 기능은 데이터 원본을 기반으로 하는 Common Data Service 데이터 레이크 또는 Common Data Model 폴더가 사용되는 사례에 대해 복사 환경 기능을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-172">This feature extends the copy environment functionality for cases in which data sources based on a Common Data Service data lake or a Common Data Model folder are used.</span></span>

## <a name="january-2021-updates"></a><span data-ttu-id="95587-173">2021년 1월 업데이트</span><span class="sxs-lookup"><span data-stu-id="95587-173">January 2021 updates</span></span>

<span data-ttu-id="95587-174">2021년 1월 업데이트에는 여러 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="95587-174">The updates in January 2021 include several features, performance upgrades, and bug fixes.</span></span>

#### <a name="extensibility"></a><span data-ttu-id="95587-175">확장성</span><span class="sxs-lookup"><span data-stu-id="95587-175">Extensibility</span></span>

- <span data-ttu-id="95587-176">**SFTP 내보내기를 위한 확장된 기능 및 향상된 성능** 이제 Customer Insights의 모든 출력 엔터티를 SFTP 호스트로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-176">**Extended functionality and enhanced performance for SFTP export** You can now export all output entities from Customer Insights to an SFTP host.</span></span> <span data-ttu-id="95587-177">이전에는 내보내기가 세그먼트 엔터티로 제한되어 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-177">Previously, export was limited to segment entities.</span></span> <span data-ttu-id="95587-178">또한 SFTP 내보내기의 성능은 SFTP 호스트의 성능에 따라 더 짧은 시간에 더 많은 데이터 볼륨을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-178">Additionally, the performance of the SFTP export allows more data volume in less time, depending on the performance of your SFTP host.</span></span>    
  <span data-ttu-id="95587-179">자세한 내용은 [SFTP용 커넥터(미리 보기)](export-sftp.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-179">For more information, see [Connector for SFTP (preview)](export-sftp.md).</span></span>  

#### <a name="segments"></a><span data-ttu-id="95587-180">세그먼트</span><span class="sxs-lookup"><span data-stu-id="95587-180">Segments</span></span>

- <span data-ttu-id="95587-181">**메트릭을 개선하기 위한 기계 학습 기반 제안된 세그먼트** 세그먼트를 발견하고 만드는 새로운 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-181">**Machine learning powered suggested segments to improve metrics** There's a new way do discover and create segments.</span></span> <span data-ttu-id="95587-182">시스템은 AI 모델을 사용하여 이미 추적 중인 KPI(측정값)를 개선하는 데 도움이 될 수 있는 세그먼트를 제안합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-182">The system uses an AI model to suggest segments that can help improve a KPI (measure) you are already tracking.</span></span> <span data-ttu-id="95587-183">측정값 또는 다른 기본 특성에서 선택한 특성의 영향 정도를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="95587-183">We show the extent of influence of attributes that you select on a measure or another primary attribute.</span></span> <span data-ttu-id="95587-184">이 정보는 기회를 제공하는 잠재적인 세그먼트를 찾는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95587-184">This information helps finding potential segments that present opportunities.</span></span>    
  <span data-ttu-id="95587-185">자세한 내용은 [제안된 세그먼트(미리 보기)](suggested-segments.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-185">For more information, see [Suggested segments (preview)](suggested-segments.md).</span></span>

#### <a name="data-unification"></a><span data-ttu-id="95587-186">데이터 통합</span><span class="sxs-lookup"><span data-stu-id="95587-186">Data unification</span></span>

- <span data-ttu-id="95587-187">**향상된 일치 환경** 데이터 통합 영역에서 일치 환경이 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-187">**Enhanced match experience** In the data unification area, the match experience was updated.</span></span> <span data-ttu-id="95587-188">일치 작동 방식을 자세히 설명하는 자세한 통계를 포함한 일치 규칙을 구성하고 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-188">It lets you configure and view the match rules, including detailed stats to further explain how matching works.</span></span> <span data-ttu-id="95587-189">구성, 드래그 앤 드롭 일치 규칙 등을 유지하면서 일치 규칙이 더 이상 활동하지 않도록 비활성화하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-189">There are options to disable a match rule so it's no longer active while retaining the configuration, drag and drop match rules, and more.</span></span>
  <span data-ttu-id="95587-190">자세한 내용은 [엔터티 일치](match-entities.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-190">For more information, see [Match entities](match-entities.md).</span></span>

- <span data-ttu-id="95587-191">**일치 프로세스의 중복 제거 출력을 엔티티로 사용할 수 있음** 일치 프로세스의 중복 제거 프로세스 출력은 이제 추가 분석을 위해 별도의 엔터티에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="95587-191">**Deduplication output from the match process is available as an entity** Deduplication process output from the match process is now written into a separate entity for further analysis.</span></span> <span data-ttu-id="95587-192">이 엔터티는 중복 제거 프로세스에 사용되는 필드와 승자 레코드 및 승자 레코드와 병합되는 해당 대체 레코드로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="95587-192">This entity consists of the fields used in the deduplication process and the winner record and the corresponding alternate records that get merged with the winner record.</span></span>
  <span data-ttu-id="95587-193">자세한 내용은 [엔터티로서 중복 제거 출력](match-entities.md#deduplication-output-as-an-entity)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-193">For more information, see [Deduplication output as an entity](match-entities.md#deduplication-output-as-an-entity).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="95587-194">시스템 관리</span><span class="sxs-lookup"><span data-stu-id="95587-194">System administration</span></span>

- <span data-ttu-id="95587-195">**Microsoft Dataverse에 원활한 데이터 공유** 이제 Microsoft Dataverse 관리형 Data Lake를 사용하여 Microsoft Dataverse 응용 프로그램과 Customer Insights 결과를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-195">**Seamlessly share data to Microsoft Dataverse** You can now share Customer Insights output with Microsoft Dataverse applications using the Microsoft Dataverse Managed Data Lake.</span></span> <span data-ttu-id="95587-196">Dataverse 환경을 Customer Insights와 연결하면 데이터 공유를 활성화할 수 있는 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="95587-196">Once you associate a Dataverse environment with Customer Insights, you get the option to enable data sharing.</span></span>
  <span data-ttu-id="95587-197">자세한 내용은 [환경 관리](manage-environments.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-197">For more information, see [Manage environments](manage-environments.md).</span></span>


## <a name="december-2020-updates"></a><span data-ttu-id="95587-198">2020년 12월 업데이트</span><span class="sxs-lookup"><span data-stu-id="95587-198">December 2020 updates</span></span>

<span data-ttu-id="95587-199">2020년 12월 업데이트에는 여러 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="95587-199">The updates in December 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-december-2020"></a><span data-ttu-id="95587-200">2020년 12월의 새로운 기능 및 업데이트된 기능</span><span class="sxs-lookup"><span data-stu-id="95587-200">New and updated features in December 2020</span></span>

#### <a name="data-enrichment"></a><span data-ttu-id="95587-201">데이터 보강</span><span class="sxs-lookup"><span data-stu-id="95587-201">Data enrichment</span></span>

- <span data-ttu-id="95587-202">**향상된 브랜드 및 관심사 선호도 보강**</span><span class="sxs-lookup"><span data-stu-id="95587-202">**Improved Brand and Interest affinity enrichments**</span></span>
  
  <span data-ttu-id="95587-203">더 쉽게 이해하고 사용할 수 있도록 선호도 점수를 단순화했습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-203">We simplified our affinity scores to make them easier to understand and use.</span></span> <span data-ttu-id="95587-204">이제 특정 브랜드 또는 관심사에 대한 고객의 선호도를 기반으로 고객을 신속하게 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-204">You can now quickly identify customers based on how much affinity they have for a given brand or interest.</span></span>

  <span data-ttu-id="95587-205">또한 고객 프로필을 보강하는 방법을 더 잘 제어하기 위해 새로운 구성 옵션을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-205">Additionally, we have added new configuration options to better control how you want your customer profiles to be enriched.</span></span> 

  <span data-ttu-id="95587-206">자세한 내용은 [브랜드 및 관심 선호도로 고객 프로필 강화](enrichment-microsoft.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-206">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft.md).</span></span>

- <span data-ttu-id="95587-207">**보강할 프로필 제어**</span><span class="sxs-lookup"><span data-stu-id="95587-207">**Control which profiles to enrich**</span></span>

  <span data-ttu-id="95587-208">이제 기본 고객 엔터티 대신 세그먼트 엔터티를 선택하는 옵션을 사용하여 고객 프로필의 하위 집합만 보강할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-208">You can now enrich only a subset of your customer profiles with the option to select a segment entity instead of the default customer entity.</span></span> <span data-ttu-id="95587-209">보강하려는 고객 프로필로 세그먼트를 만들어 고객 데이터 집합에 대한 보강 구성에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-209">Create a segment with the customer profiles you would like to enrich and select it in the enrichment configuration for your customer data set.</span></span>
  <span data-ttu-id="95587-210">이 기능은 현재 Experian 및 HERE Technologies에서 제공하는 보강에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-210">This feature is currently available only for enrichments provided by Experian and HERE Technologies.</span></span> <span data-ttu-id="95587-211">조만간 더 많은 기능을 보강할 수 있도록 이 기능을 활성화할 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="95587-211">We will be enabling this capability to more enrichments soon.</span></span>

  <span data-ttu-id="95587-212">자세한 내용은 [Experian의 인구 통계로 고객 프로필 보강](enrichment-experian.md) 또는 [HERE Technologies를 통한 고객 프로필 보강](enrichment-here.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-212">For more information, see [Enrich customer profiles with demographics from Experian](enrichment-experian.md) or [Enrichment of customer profiles with HERE Technologies](enrichment-here.md).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="95587-213">확장성</span><span class="sxs-lookup"><span data-stu-id="95587-213">Extensibility</span></span>

- <span data-ttu-id="95587-214">**Autopilot를 통해 세그먼트 활성화**</span><span class="sxs-lookup"><span data-stu-id="95587-214">**Activate your segments through Autopilot**</span></span>

  <span data-ttu-id="95587-215">세그먼트를 Autopilot로 내보내고 마케팅 목적으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-215">Export segments to Autopilot and use them for marketing purposes.</span></span> <span data-ttu-id="95587-216">자세한 내용은 [Autopilot용 커넥터(미리 보기)](export-autopilot.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-216">For more information, see [Connector for Autopilot (preview)](export-autopilot.md).</span></span>

- <span data-ttu-id="95587-217">**SendGrid를 통해 세그먼트 활성화**</span><span class="sxs-lookup"><span data-stu-id="95587-217">**Activate your segments through SendGrid**</span></span>

  <span data-ttu-id="95587-218">세그먼트를 SendGrid로 내보내고 마케팅 목적으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-218">Export segments to SendGrid and use them for marketing purposes.</span></span> <span data-ttu-id="95587-219">자세한 내용은 [SendGrid용 커넥터](export-sendgrid.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-219">For more information, see [Connector for SendGrid](export-sendgrid.md).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="95587-220">시스템 관리</span><span class="sxs-lookup"><span data-stu-id="95587-220">System administration</span></span>

- <span data-ttu-id="95587-221">**업데이트된 환경 관리 경험**</span><span class="sxs-lookup"><span data-stu-id="95587-221">**Updated environment management experience**</span></span>
  
  <span data-ttu-id="95587-222">이제 앱 헤더의 환경 선택기에서 직접 환경을 생성, 편집, 삭제 및 재설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-222">You can now create, edit, delete, and reset environments directly from the environment picker in the app header.</span></span> 
  
  <span data-ttu-id="95587-223">또한 사용중인 환경이 환경 패널 상단에 고정되므로 더 이상 검색할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-223">Additionally, the environment you are using will be pinned at the top of the environment panel so you don't need to search for it anymore.</span></span>

  <span data-ttu-id="95587-224">자세한 내용은 [환경 관리](manage-environments.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-224">For more information, see [Manage environments](manage-environments.md).</span></span>

## <a name="november-2020-updates"></a><span data-ttu-id="95587-225">2020년 11월 업데이트</span><span class="sxs-lookup"><span data-stu-id="95587-225">November 2020 updates</span></span>

<span data-ttu-id="95587-226">2020년 11월 업데이트에는 여러 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="95587-226">The updates in November 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-november-2020"></a><span data-ttu-id="95587-227">2020년 11월의 새로운 기능 및 업데이트된 기능</span><span class="sxs-lookup"><span data-stu-id="95587-227">New and updated features in November 2020</span></span>

#### <a name="data-enrichment"></a><span data-ttu-id="95587-228">데이터 보강</span><span class="sxs-lookup"><span data-stu-id="95587-228">Data enrichment</span></span>

- <span data-ttu-id="95587-229">**SFTP(보안 파일 전송 프로토콜) 사용자 지정 가져오기를 통해 자체 보강 데이터 가져 오기**</span><span class="sxs-lookup"><span data-stu-id="95587-229">**Bring your own enrichment data via Secure File Transfer Protocol (SFTP) custom import**</span></span>
  
  <span data-ttu-id="95587-230">SFTP 사용자 지정 가져오기를 사용하면 데이터 통합 프로세스를 거치지 않아도 되는 보강 데이터를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-230">SFTP custom import lets you import enrichment data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="95587-231">SFTP 사용자 지정 가져오기에 대해 자세히 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="95587-231">Learn more about SFTP custom import.</span></span>

  <span data-ttu-id="95587-232">자세한 내용은 [사용자 지정 데이터로 고객 프로필 강화(미리 보기)](enrichment-SFTP-custom-import.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-232">For more information, see [Enrich customer profiles with custom data (preview)](enrichment-SFTP-custom-import.md).</span></span>
 
- <span data-ttu-id="95587-233">**HERE Technologies의 위치 데이터로 고객 데이터 보강**</span><span class="sxs-lookup"><span data-stu-id="95587-233">**Enrich your customer data with location data from HERE Technologies**</span></span>

  <span data-ttu-id="95587-234">HERE Technologies의 데이터 보강 서비스를 사용하면 주소 정규화, 위도 및 경도 추출 등을 통해 고객에 대한 보다 정확한 위치 이해를 구축할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-234">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span> <span data-ttu-id="95587-235">HERE Technologies로 보강하는 방법에 대해 자세히 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="95587-235">Learn more about enriching with HERE Technologies.</span></span>

  <span data-ttu-id="95587-236">자세한 내용은 [HERE Technologies로 고객 프로필 보강(미리 보기)](enrichment-here.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-236">For more information, see [Enrichment of customer profiles with HERE Technologies](enrichment-here.md).</span></span>

#### <a name="data-unification"></a><span data-ttu-id="95587-237">데이터 통합</span><span class="sxs-lookup"><span data-stu-id="95587-237">Data unification</span></span>

- <span data-ttu-id="95587-238">**스토리지 계정에서 선택한 엔터티 및 필드에 대한 데이터 프로파일링을 활성화하는 유연성**</span><span class="sxs-lookup"><span data-stu-id="95587-238">**Flexibility to enable data profiling on selected entities and fields from your storage account**</span></span>

  <span data-ttu-id="95587-239">데이터 수집 프로세스의 일부로 데이터 프로파일링을 사용하도록 설정하려는 Azure Data Lake 스토리지 계정의 Common Data Model 폴더에서 데이터 엔터티 및 필드를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-239">You can indicate which data entities and fields from a Common Data Model folder in your Azure Data Lake storage account you want to enable data profiling as part of the data ingestion process.</span></span>

  <span data-ttu-id="95587-240">자세한 내용은 [Common Data Model 폴더에 연결](connect-common-data-model.md#connect-to-a-common-data-model-folder)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-240">For more information, see [Connect to a Common Data Model folder](connect-common-data-model.md#connect-to-a-common-data-model-folder).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="95587-241">확장성</span><span class="sxs-lookup"><span data-stu-id="95587-241">Extensibility</span></span>

- <span data-ttu-id="95587-242">**Google 광고를 통해 세그먼트 활성화**</span><span class="sxs-lookup"><span data-stu-id="95587-242">**Activate your segments through Google Ads**</span></span>

  <span data-ttu-id="95587-243">통합 고객 프로필의 세그먼트를 Google 광고 대상 그룹 목록으로 내보내고 이러한 목록을 사용하여 Google 검색, Gmail, YouTube 및 Google 디스플레이 네트워크에서 광고합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-243">Export segments from to Google Ads audience lists and use these lists to advertise on Google Search, Google Display Network, YouTube, and Gmail.</span></span> <span data-ttu-id="95587-244">Google 광고를 통해 세그먼트를 활성화하는 방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="95587-244">Learn more about activating your segments through Google Ads.</span></span>

  <span data-ttu-id="95587-245">자세한 내용은 [Google 광고용 커네터](export-google-ads.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-245">For more information, see [Connector for Google Ads](export-google-ads.md).</span></span>

- <span data-ttu-id="95587-246">**Marketo를 통해 세그먼트 활성화**</span><span class="sxs-lookup"><span data-stu-id="95587-246">**Activate your segments through Marketo**</span></span>

  <span data-ttu-id="95587-247">Marketo 대상 그룹에게 세그먼트를 내보내고 이러한 대상 그룹을 마케팅 자동화에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-247">Export segments to Marketo audiences and use these audiences for marketing automation.</span></span> <span data-ttu-id="95587-248">Marketo를 통해 세그먼트를 활성화하는 방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="95587-248">Learn more about activating your segments through Marketo.</span></span> 

  <span data-ttu-id="95587-249">자세한 내용은 [Marketo용 커네터](export-marketo.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-249">For more information, see [Connector for Marketo](export-marketo.md).</span></span>

- <span data-ttu-id="95587-250">**DotDigital을 통해 세그먼트 활성화**</span><span class="sxs-lookup"><span data-stu-id="95587-250">**Activate your segments through DotDigital**</span></span>

  <span data-ttu-id="95587-251">세그먼트를 DotDigital로 내보내고 마케팅 목적으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-251">Export segments to DotDigital and use them for marketing purposes.</span></span> <span data-ttu-id="95587-252">DotDigital을 통해 세그먼트를 활성화하는 방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="95587-252">Learn more about activating your segments through DotDigital.</span></span> 

  <span data-ttu-id="95587-253">자세한 내용은 [DotDigital용 커네터](export-dotdigital.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-253">For more information, see [Connector for DotDigital](export-dotdigital.md).</span></span>

#### <a name="predictions"></a><span data-ttu-id="95587-254">예측</span><span class="sxs-lookup"><span data-stu-id="95587-254">Predictions</span></span>

- <span data-ttu-id="95587-255">**트랜잭션 이탈 예측**</span><span class="sxs-lookup"><span data-stu-id="95587-255">**Predict transactional churn**</span></span>

  <span data-ttu-id="95587-256">트랜잭션 이탈 예측 기능을 사용하면 데이터 과학자의 도움 없이 고객이 제품 또는 서비스 구매를 중단할 가능성을 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-256">The transaction churn prediction feature enables you, without the help of a data scientist, to predict the likelihood of a customer to stop purchasing products or services.</span></span>  <span data-ttu-id="95587-257">예측 점수를 사용하면 고객 가치와 같은 고객에 대한 다른 정보를 결합하여 이탈 위험이 높거나 가치가 높은 고객 세그먼트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-257">Using the prediction score, you can combine other information about your customers, like customer value, to create segments of high churn risk or high value customers.</span></span> <span data-ttu-id="95587-258">이 세그먼트를 사용하여 마케팅 활동, 고객 지원 및 기타 시나리오를 통해 고객을 직접 타겟팅하여 이탈 위험을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="95587-258">Use this segment to directly target customers through marketing activities, customer support, and other scenarios to reduce churn risk.</span></span>
 
  <span data-ttu-id="95587-259">이탈의 정의를 비즈니스에 특정한 시간 기반 창으로 구성하고 고객이 이탈한 것으로 간주되는시기를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-259">Configure the definition of churn as a time-based window specific to your business and define when customers are considered churned.</span></span> <span data-ttu-id="95587-260">예를 들어 식료품점에서는 지난 30일 동안 구매한 적이 없는 고객을 이탈한 것으로 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-260">For example, a grocery store may want to consider a customer churned if they have not purchased anything in the past 30 days.</span></span>
 
  <span data-ttu-id="95587-261">예측을 계속 생성하면 필요한 데이터를 안내하고 비즈니스에 대한 데이터를 고객의 이탈을 예측하는 데 필요한 필드에 매핑 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-261">As you continue creating the prediction, we'll guide you what data is needed, and enable you to map data about your business to fields required to predict churn for your customers.</span></span> <span data-ttu-id="95587-262">변화하는 비즈니스 환경에 적응하기 위해 시스템의 새로운 정보를 기반으로 모델을 재교육하는 일정을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-262">You can also set a schedule to retrain the model based on new information in your system to adapt to changing business circumstances.</span></span>
 
  <span data-ttu-id="95587-263">자세한 내용은 [트랜잭션 이탈 예측(미리 보기)](predict-transactional-churn.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-263">For more information, see [Transactional churn prediction (preview)](predict-transactional-churn.md).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="95587-264">시스템 관리</span><span class="sxs-lookup"><span data-stu-id="95587-264">System administration</span></span>

- <span data-ttu-id="95587-265">**환경 재설정**</span><span class="sxs-lookup"><span data-stu-id="95587-265">**Reset environment**</span></span>

  <span data-ttu-id="95587-266">새로 시작하려면 선택한 인스턴스의 환경에서 모든 항목을 재설정합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-266">Reset everything in an environment of a selected instance to start fresh.</span></span>

  <span data-ttu-id="95587-267">자세한 내용은 [기존 환경 초기화](manage-environments.md#reset-an-existing-environment)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-267">For more information, see [Reset an existing environment](manage-environments.md#reset-an-existing-environment).</span></span>


- <span data-ttu-id="95587-268">**서비스 주체를 사용하여 Azure Data Lake 스토리지 계정에 연결**</span><span class="sxs-lookup"><span data-stu-id="95587-268">**Connect to your Azure Data Lake storage account using a service principal**</span></span>

  <span data-ttu-id="95587-269">Azure 서비스 주체를 사용하여 스토리지 계정에 데이터 출력을 쓰고 데이터를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-269">Write data output to and read data from your storage account using an Azure service principal.</span></span> <span data-ttu-id="95587-270">기존 스토리지 계정 연결은 계정 키를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-270">Existing storage account connections can continue to use the account key.</span></span> <span data-ttu-id="95587-271">또한 앞으로 서비스 주체를 사용할 수 있는 업그레이드 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-271">They also offer an upgrade option to use the service principal moving forward.</span></span> <span data-ttu-id="95587-272">새 연결은 스토리지 계정에 대한 서비스 주체 인증 방법을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-272">New connections will be based on the service principal authentication method for your storage account.</span></span>

  <span data-ttu-id="95587-273">자세한 내용은 대상 그룹 인사이트를 위해 [Azure 서비스 주체를 사용하여 Azure Data Lake Storage Gen2 계정에 연결](connect-service-principal.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-273">For more information, see [Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights](connect-service-principal.md).</span></span>

## <a name="october-2020-updates"></a><span data-ttu-id="95587-274">2020년 10월 업데이트</span><span class="sxs-lookup"><span data-stu-id="95587-274">October 2020 updates</span></span>

<span data-ttu-id="95587-275">2020년 10월 업데이트에는 여러 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="95587-275">The updates in October 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-october-2020"></a><span data-ttu-id="95587-276">2020년 10월의 새로운 기능 및 업데이트된 기능</span><span class="sxs-lookup"><span data-stu-id="95587-276">New and updated features in October 2020</span></span>

#### <a name="extensibility"></a><span data-ttu-id="95587-277">확장성</span><span class="sxs-lookup"><span data-stu-id="95587-277">Extensibility</span></span>

- <span data-ttu-id="95587-278">**Mailchimp에 내보내기**</span><span class="sxs-lookup"><span data-stu-id="95587-278">**Export to Mailchimp**</span></span>

<span data-ttu-id="95587-279">Mailchimp의 기존 대상 목록으로 세그먼트를 내보내 고객에게 개인화된 이메일 경험을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-279">Export segments to existing audience lists in Mailchimp to provide a personalized email experience for your customers.</span></span>

<span data-ttu-id="95587-280">자세한 내용은 [Mailchimp용 커네터](export-mailchimp.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-280">For more information, see [Connector for Mailchimp](export-mailchimp.md).</span></span>

#### <a name="data-enrichment"></a><span data-ttu-id="95587-281">데이터 보강</span><span class="sxs-lookup"><span data-stu-id="95587-281">Data enrichment</span></span>

- <span data-ttu-id="95587-282">**일치 엔터티에서 원본 레코드 중복 제거**</span><span class="sxs-lookup"><span data-stu-id="95587-282">**Deduplicate the source records in a Match entity**</span></span>

<span data-ttu-id="95587-283">중복 레코드를 식별하기 위해 일치 프로세스에 사용되는 엔터티에 대한 중복 제거 규칙을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-283">Specify deduplication rules on entities used in the match process to identify duplicate records.</span></span> <span data-ttu-id="95587-284">하나의 레코드로 병합하고 모든 소스 레코드를이 병합된 레코드에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-284">Merge them into one record and link all the source records to this merged record.</span></span> <span data-ttu-id="95587-285">이 중복 제거된 레코드는 엔터티 간 일치 프로세스에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="95587-285">This deduplicated record will then be used in the cross-entity matching process.</span></span>

<span data-ttu-id="95587-286">자세한 내용은 [일치 항목에 대한 중복 제거 정의](match-entities.md#define-deduplication-on-a-match-entity)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-286">For more information, see [Define deduplication on a match entity](match-entities.md#define-deduplication-on-a-match-entity).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="95587-287">시스템 관리</span><span class="sxs-lookup"><span data-stu-id="95587-287">System administration</span></span>

- <span data-ttu-id="95587-288">**오케스트레이션: 병합의 새로운 새로 고침 옵션**</span><span class="sxs-lookup"><span data-stu-id="95587-288">**Orchestration: New refresh option in Merge**</span></span>

<span data-ttu-id="95587-289">오늘까지 병합 프로세스를 실행할 때 시스템은 병합 및 후속 프로세스에 의존하는 모든 다운 스트림 프로세스를 실행했습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-289">Until today, when you run the merge process, the system ran all the downstream processes that depend on merge and subsequent processes.</span></span> <span data-ttu-id="95587-290">이제 병합 프로세스(통합 고객 엔터티)의 출력을 세그먼트 또는 측정과 같은 다운스트림 처리에 사용하기 전에 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-290">You can now verify the output of the merge process (the unified customer entity) before using it in downstream processing like segments or measures.</span></span>
<span data-ttu-id="95587-291">병합 페이지에서 이제 병합 단계만 실행하고 이 프로세스만 실행하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-291">On the merge page, you can now choose to run only the merge step and run only this process.</span></span> <span data-ttu-id="95587-292">모든 다운스트림 프로세스도 새로 고치려면 병합 및 다운스트림 프로세스 실행을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-292">To refresh all the downstream processes too, you can choose run merge and downstream processes.</span></span> 

## <a name="september-2020-updates"></a><span data-ttu-id="95587-293">2020년 9월 업데이트</span><span class="sxs-lookup"><span data-stu-id="95587-293">September 2020 updates</span></span>

<span data-ttu-id="95587-294">2020년 9월 업데이트에는 여러 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="95587-294">The updates in September 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-september-2020"></a><span data-ttu-id="95587-295">2020년 9월의 새로운 기능 및 업데이트된 기능</span><span class="sxs-lookup"><span data-stu-id="95587-295">New and updated features in September 2020</span></span>

#### <a name="activities"></a><span data-ttu-id="95587-296">작업</span><span class="sxs-lookup"><span data-stu-id="95587-296">Activities</span></span>

- <span data-ttu-id="95587-297">**특성 의미론의 지능형 예측**</span><span class="sxs-lookup"><span data-stu-id="95587-297">**Intelligent prediction of attribute semantics**</span></span>

<span data-ttu-id="95587-298">이 새로운 기능은 데이터 통합 프로세스에 전달되는 입력 특성의 의미 유형을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-298">This new feature predicts the semantic types of input attributes that are passed on to the data unification process.</span></span> <span data-ttu-id="95587-299">정확도를 높이고 시간을 절약하는 기계 학습 모델을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-299">It uses machine learning models that improve accuracy and save time.</span></span>

#### <a name="enrichments"></a><span data-ttu-id="95587-300">보강</span><span class="sxs-lookup"><span data-stu-id="95587-300">Enrichments</span></span>

- <span data-ttu-id="95587-301">**Experian의 인구 통계 보강**</span><span class="sxs-lookup"><span data-stu-id="95587-301">**Demographics enrichment from Experian**</span></span>

<span data-ttu-id="95587-302">Experian의 인구 통계 보강이 이제 미리 보기로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="95587-302">The demographics enrichment from Experian is now available in preview.</span></span> <span data-ttu-id="95587-303">Experian은 소비자 및 기업 신용보고 및 마케팅 서비스 분야의 글로벌 리더입니다.</span><span class="sxs-lookup"><span data-stu-id="95587-303">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="95587-304">[Experian의 데이터 보강 서비스](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)를 사용하면 가구 규모, 소득 등과 같은 인구 통계 데이터로 고객 프로필을 강화하여 고객에 대한 더 깊은 이해를 구축할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-304">With [Experian’s data enrichment services](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage), you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

<span data-ttu-id="95587-305">이 기능을 사용하려면 활성 Experian 구독이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-305">To use this feature, you must have an active Experian subscription.</span></span>

<span data-ttu-id="95587-306">자세한 내용은 [Experian의 인구 통계로 고객 프로필 보강](enrichment-experian.md)을 참고하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-306">For more information, see [Enrich customer profiles with demographics from Experian](enrichment-experian.md)</span></span>


#### <a name="system-administration"></a><span data-ttu-id="95587-307">시스템 관리</span><span class="sxs-lookup"><span data-stu-id="95587-307">System administration</span></span>

- <span data-ttu-id="95587-308">**작업 세부 정보 창**</span><span class="sxs-lookup"><span data-stu-id="95587-308">**Task details pane**</span></span>

<span data-ttu-id="95587-309">작업 세부 정보 창에서는 시스템에서 실행하는 작업에 대한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-309">The task details pane enables you to see details about tasks that the system runs.</span></span> <span data-ttu-id="95587-310">구성 문제를 식별하고 솔루션을 찾는 편리한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="95587-310">It's a handy way to identify issues with the configuration and find solutions.</span></span>
<span data-ttu-id="95587-311">오류 메시지를 검토하여 잠재적 문제를 해결하는 방법을 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-311">Review the error messages see how you address potential issues.</span></span>
 
- <span data-ttu-id="95587-312">**더 많은 페이지에 추가된 처리 정보**</span><span class="sxs-lookup"><span data-stu-id="95587-312">**Processing information added to more pages**</span></span>

<span data-ttu-id="95587-313">이 개선 사항은 **엔터티** 및 **고객** 페이지의 엔터티의 상태에 대한 정보를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-313">This improvement adds information about the status of your entities on the **Entities** and **Customers** page.</span></span>
 
<span data-ttu-id="95587-314">또한 이 두 페이지 모두에서 작업 세부 정보와 함께 프로세스 진행 상황에 대한 세부 정보를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-314">Additionally, you can find details about the progress of processes, along with the task details, on both of these pages.</span></span>

- <span data-ttu-id="95587-315">**시스템 상태 페이지 개선**</span><span class="sxs-lookup"><span data-stu-id="95587-315">**Improvements to system status page**</span></span>

<span data-ttu-id="95587-316">데이터 내보내기를 검토할 때 **시스템** > **상태** 에서 상태 세부 정보 표의 구조를 개선했습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-316">We improved the structure of the status details table on **System** > **Status** when reviewing data exports.</span></span>
 
<span data-ttu-id="95587-317">또한 **세부 정보** 열의 오류가 더 상세하고 실행 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-317">Additionally, errors in the **Details** column are now more detailed and actionable.</span></span> 
 
- <span data-ttu-id="95587-318">**취소는 작업을 이전 상태로 되돌립니다.**</span><span class="sxs-lookup"><span data-stu-id="95587-318">**Cancel reverts job back to previous state**</span></span>

<span data-ttu-id="95587-319">예를 들어 매치 프로세스에서 작업을 취소하면 최근 상태로 되돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="95587-319">When you cancel a task, for example, in the match process, it will revert back to its latest state.</span></span> <span data-ttu-id="95587-320">예를 들어 매치 프로세스가 어제 완료되었고 오늘 취소하면 어제의 성공 상태로 되돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="95587-320">For example, if the Match process completed yesterday and you cancel it today, it will revert to yesterday's successful state.</span></span>


## <a name="august-2020-updates"></a><span data-ttu-id="95587-321">2020년 8월 업데이트</span><span class="sxs-lookup"><span data-stu-id="95587-321">August 2020 updates</span></span>

<span data-ttu-id="95587-322">2020년 8월 업데이트에는 여러 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="95587-322">The updates in August 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-august-2020"></a><span data-ttu-id="95587-323">2020년 8월의 새로운 기능 및 업데이트된 기능</span><span class="sxs-lookup"><span data-stu-id="95587-323">New and updated features in August 2020</span></span>

#### <a name="data-unification"></a><span data-ttu-id="95587-324">데이터 통합</span><span class="sxs-lookup"><span data-stu-id="95587-324">Data unification</span></span>

- <span data-ttu-id="95587-325">**데이터 통합 중 지도 단계에 대한 경험 개선**</span><span class="sxs-lookup"><span data-stu-id="95587-325">**Improved experience for the map stage during data unification**</span></span>

  <span data-ttu-id="95587-326">데이터 통합 프로세스에서 지도 단계에 대한 경험을 통해 엔티티, 속성을 선택하고 보다 원활한 방식으로 의미를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-326">The experience to the map stage in the data unification process lets you select entities, attributes, and define semantics in a more seamless way.</span></span>

  <span data-ttu-id="95587-327">변경 내용:</span><span class="sxs-lookup"><span data-stu-id="95587-327">The changes include:</span></span>
  
  - <span data-ttu-id="95587-328">엔터티 및 필드를 추가하는 데 필요한 상호 작용 감소</span><span class="sxs-lookup"><span data-stu-id="95587-328">fewer interactions required to add entities and fields</span></span>
  - <span data-ttu-id="95587-329">지도 페이지의 향상된 검색 기능</span><span class="sxs-lookup"><span data-stu-id="95587-329">improved search capabilities on the map page</span></span>
  - <span data-ttu-id="95587-330">제안된 필드 유형의 시각적이고 쉬운 식별</span><span class="sxs-lookup"><span data-stu-id="95587-330">visual and easy identification of the suggested field type</span></span>

#### <a name="enrichment"></a><span data-ttu-id="95587-331">보강</span><span class="sxs-lookup"><span data-stu-id="95587-331">Enrichment</span></span>

- <span data-ttu-id="95587-332">**더 많은 시장에서 사용 가능한 관심사 선호도 보강**</span><span class="sxs-lookup"><span data-stu-id="95587-332">**Interest affinities enrichment available in more markets**</span></span>

  <span data-ttu-id="95587-333">관심사 선호도 보강의 가용성을 미국을 넘어 캐나다, 호주, 영국, 프랑스 및 독일의 5개 시장으로 확장하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-333">We're extending the availability of the interest affinities enrichment beyond the United States to five other markets: Canada, Australia, United Kingdom, France, and Germany.</span></span> <span data-ttu-id="95587-334">이 확장을 통해 이러한 시장에 대한 더 많은 관심사를 포함한 고객 데이터를 보강할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-334">With this extension, you can enrich your customer data with more interests applicable to these markets.</span></span> <span data-ttu-id="95587-335">또한 Microsoft의 로컬 독점 데이터를 사용하여 이러한 시장에 있는 고객 프로필을 보강합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-335">We'll also enrich your customer profiles that are located in these markets by using local proprietary data from Microsoft.</span></span>
  <span data-ttu-id="95587-336">자세한 내용은 [브랜드 및 관심 선호도로 고객 프로필 보강](enrichment-microsoft.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-336">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft.md)</span></span>


## <a name="july-2020-updates"></a><span data-ttu-id="95587-337">2020년 7월 업데이트</span><span class="sxs-lookup"><span data-stu-id="95587-337">July 2020 updates</span></span>

<span data-ttu-id="95587-338">2020년 7월 업데이트에는 여러 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="95587-338">The updates in July 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-july-2020"></a><span data-ttu-id="95587-339">2020년 7월 새로운 기능 및 업데이트된 기능</span><span class="sxs-lookup"><span data-stu-id="95587-339">New and updated features in July 2020</span></span>

#### <a name="extensibility"></a><span data-ttu-id="95587-340">확장성</span><span class="sxs-lookup"><span data-stu-id="95587-340">Extensibility</span></span>

- <span data-ttu-id="95587-341">**통합 프로세스 완료를 위한 Power Automate 트리거**</span><span class="sxs-lookup"><span data-stu-id="95587-341">**Power Automate trigger for completed unification process**</span></span>

  <span data-ttu-id="95587-342">Power Automate에 대한 트리거를 확장하여 통합 프로세스(맵, 일치, 병합)의 새로 고침이 완료되면 알림 또는 작업을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-342">We have extended our triggers for Power Automate and let you create a notification or action when a refresh of the unification process (map, match, merge) is completed.</span></span>    
  <span data-ttu-id="95587-343">자세한 내용은 [Power Automate 커넥터](export-power-automate.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-343">For more information, see [Power Automate connector](export-power-automate.md)</span></span>

#### <a name="enrichment"></a><span data-ttu-id="95587-344">보강</span><span class="sxs-lookup"><span data-stu-id="95587-344">Enrichment</span></span>

- <span data-ttu-id="95587-345">**더 많은 시장에서 사용 가능한 브랜드 선호도 보강**</span><span class="sxs-lookup"><span data-stu-id="95587-345">**Brand affinities enrichment available in more markets**</span></span>

  <span data-ttu-id="95587-346">브랜드 선호도 보강의 가용성을 미국을 넘어 캐나다, 호주, 영국, 프랑스 및 독일의 5개 시장으로 확장하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-346">We're extending the availability of the brand affinities enrichment beyond the United States to five other markets: Canada, Australia, United Kingdom, France, and Germany.</span></span> <span data-ttu-id="95587-347">이 확장을 통해 이러한 시장의 현지 브랜드로 고객 데이터를 풍부하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-347">With this extension, you can enrich your customer data with local brands in these markets.</span></span> <span data-ttu-id="95587-348">또한 Microsoft의 로컬 독점 데이터를 사용하여 이러한 시장에 있는 고객 프로필을 보강합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-348">We'll also enrich your customer profiles that are located in these markets by using local proprietary data from Microsoft.</span></span>
  <span data-ttu-id="95587-349">자세한 내용은 [브랜드 및 관심 선호도로 고객 프로필 보강](enrichment-microsoft.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-349">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft.md)</span></span>

## <a name="june-2020-updates"></a><span data-ttu-id="95587-350">2020년 6월 업데이트</span><span class="sxs-lookup"><span data-stu-id="95587-350">June 2020 updates</span></span>

<span data-ttu-id="95587-351">2020년 6월 업데이트에는 여러 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="95587-351">The updates in June 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-june-2020"></a><span data-ttu-id="95587-352">2020년 6월 새로운 기능 및 업데이트된 기능</span><span class="sxs-lookup"><span data-stu-id="95587-352">New and updated features in June 2020</span></span>

#### <a name="enrichment"></a><span data-ttu-id="95587-353">보강</span><span class="sxs-lookup"><span data-stu-id="95587-353">Enrichment</span></span>

- <span data-ttu-id="95587-354">**Leadspace의 회사 데이터로 보강**</span><span class="sxs-lookup"><span data-stu-id="95587-354">**Enrichment with company data from Leadspace**</span></span>
  
  <span data-ttu-id="95587-355">Leadspace에서 관련 회사 데이터를 조회하는 데 사용되는 통합 고객 프로필의 필드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-355">Define fields in unified customer profiles that are used to look up related company data from Leadspace.</span></span> <span data-ttu-id="95587-356">보강 프로세스를 실행한 후 B2B 프로필은 회사 규모, 위치, 산업 등 더 많은 특성으로 보강됩니다.</span><span class="sxs-lookup"><span data-stu-id="95587-356">After running the enrichment process, B2B profiles are enriched with more attributes including company size, location, industry, and more.</span></span>    
  <span data-ttu-id="95587-357">이 공동 작업을 통해 타사 서비스의 입력으로 데이터 품질을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-357">This collaboration allows you to improve the quality of your data with input from third-party services.</span></span> <span data-ttu-id="95587-358">이 보강을 사용하려면 B2B 회사 데이터에 액세스할 수 있는 Leadspace의 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-358">To use this enrichment, you'll need a license from Leadspace to access its B2B company data.</span></span> <span data-ttu-id="95587-359">시스템은 해당 라이선스를 사용하여 데이터를 지속적으로 보강합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-359">The system will use that license to keep your data enriched continuously.</span></span>    
  <span data-ttu-id="95587-360">자세한 내용은 [Leadspace로 회사 프로필 보강](enrichment-leadspace.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-360">For more information, see [Enrichment of company profiles with Leadspace](enrichment-leadspace.md).</span></span>

- <span data-ttu-id="95587-361">**보강 허브 페이지**</span><span class="sxs-lookup"><span data-stu-id="95587-361">**Enrichment hub page**</span></span>

  <span data-ttu-id="95587-362">자사 및 타사 보강 공급자의 사용 가능한 모든 데이터 보강은 동일한 위치에서 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="95587-362">All available data enrichment from first- and third-party enrichment providers gets configured in the same place.</span></span> <span data-ttu-id="95587-363">데이터 보강 구성은 공통 위치에서 관리되는 원활한 경험입니다.</span><span class="sxs-lookup"><span data-stu-id="95587-363">Configuring data enrichment is a seamless experience that is managed from a common place.</span></span>    
  <span data-ttu-id="95587-364">자세한 내용은 [고객 프로필 보강](enrichment-hub.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-364">For more information, see [Enrichment for customer profiles](enrichment-hub.md).</span></span>

- <span data-ttu-id="95587-365">**별도의 브랜드 및 관심 선호도 강화**</span><span class="sxs-lookup"><span data-stu-id="95587-365">**Separate brand and interest affinity enrichment**</span></span>

  <span data-ttu-id="95587-366">이제 브랜드 및 관심 선호도 유사성을 두 개의 독립적인 보강으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-366">The brands and interests affinities are now available as two independent enrichments.</span></span> <span data-ttu-id="95587-367">분리된 보강은 비즈니스 요구 사항이나 필요에 따라 개별적으로 구성하고 관리할 수 있는 유연성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-367">Separated enrichments give you the flexibility to configure and manage them individually, depending on your business requirements or needs.</span></span>    
  <span data-ttu-id="95587-368">자세한 내용은 [브랜드 및 관심 선호도로 고객 프로필 강화](enrichment-microsoft.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-368">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft.md).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="95587-369">확장성</span><span class="sxs-lookup"><span data-stu-id="95587-369">Extensibility</span></span>

- <span data-ttu-id="95587-370">**Dynamics 365 고객 카드 추가 기능의 통합 활동을 위한 클릭 가능한 URL**</span><span class="sxs-lookup"><span data-stu-id="95587-370">**Clickable URLs for unified activities on the Dynamics 365 Customer Card Add-in**</span></span>

  <span data-ttu-id="95587-371">고객 카드 추가 기능의 통합 활동은 활동 구성 중에 이러한 URL이 정의된 경우 클릭 가능한 URL을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-371">The unified activities in the Customer Card Add-in are now showing clickable URLs if such URLs have been defined during the configuration of activities.</span></span>    
  <span data-ttu-id="95587-372">자세한 내용은 [고객 카드 추가 기능](customer-card-add-in.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-372">For more information, see [Customer Card Add-in](customer-card-add-in.md).</span></span>

- <span data-ttu-id="95587-373">**Dynamics 365 고객 카드 추가 기능에서 사용할 수 있는 브랜드 및 관심 선호도**</span><span class="sxs-lookup"><span data-stu-id="95587-373">**Brand and interest affinities available on the Dynamics 365 Customer Card Add-in**</span></span>

  <span data-ttu-id="95587-374">Dynamics 365 고객 카드 추가 기능에 대한 새로운 컨트롤을 사용하면 Dynamics 365의 고객 참여 앱에서 연락처에 브랜드 및 관심 강화를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-374">A new control on the Dynamics 365 Customer Card Add-in lets you show brand and interest enrichments on your contacts in customer engagement apps in Dynamics 365.</span></span>    
  <span data-ttu-id="95587-375">자세한 내용은 [고객 카드 추가 기능](customer-card-add-in.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-375">For more information, see [Customer Card Add-in](customer-card-add-in.md).</span></span>

- <span data-ttu-id="95587-376">**더 많은 Power Automate 트리거**</span><span class="sxs-lookup"><span data-stu-id="95587-376">**More Power Automate triggers**</span></span>

  <span data-ttu-id="95587-377">Power Automate에 대한 트리거를 확장하고 다음 트리거를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-377">We have extended our triggers for Power Automate and added the following triggers:</span></span>
  - <span data-ttu-id="95587-378">자동화된 전체 새로 고침(데이터 원본, 통합, 세그먼트, 측정, 내보내기)이 완료되면 알림을 받거나 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-378">Get a notification or perform an action when an automated full refresh (data sources, unification, segments, measures, exports) completes</span></span>
  - <span data-ttu-id="95587-379">비즈니스 측정에 대한 임계값을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-379">Define a threshold for a business measure.</span></span> <span data-ttu-id="95587-380">예를 들어, 정의된 임계값이 전달될 때 전송되는 알림을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-380">For example, you can create a notification that gets sent when the defined threshold is passed.</span></span> <span data-ttu-id="95587-381">또한 트리거는 Power Automate에서 더 복잡한 워크플로를 구축할 수 있는 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-381">Additionally, the trigger brings information that allows you to build more complex workflows in Power Automate.</span></span>    
  <span data-ttu-id="95587-382">자세한 내용은 [Power Automate 커넥터](export-power-automate.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-382">For more information, see [Power Automate connector](export-power-automate.md)</span></span>

- <span data-ttu-id="95587-383">**Facebook 광고 관리자로 내보내기**</span><span class="sxs-lookup"><span data-stu-id="95587-383">**Export to Facebook Ads Manager**</span></span>
  
  <span data-ttu-id="95587-384">이 기능을 사용하면 세그먼트를 Facebook 광고 관리자로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-384">This capability lets you export segments to Facebook Ads Manager.</span></span> <span data-ttu-id="95587-385">세그먼트는 Facebook 마케팅 캠페인 및 광고의 통합 고객 프로필을 사용하기 위해 사용자 지정 대상으로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="95587-385">Segments are exported as custom audiences to use unified customer profiles in Facebook marketing campaigns and ads.</span></span> <span data-ttu-id="95587-386">사용자 지정 고객은 또한 Instagram에서 Facebook 광고 관리자를 통해 캠페인을 만드는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-386">The custom audiences are also usable to create campaigns on Instagram through Facebook Ads Manager.</span></span>    
  <span data-ttu-id="95587-387">자세한 내용은 [Facebook 광고 관리자용 커넥터](export-facebook.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-387">For more information, see [Connector for Facebook Ads Manager](export-facebook.md).</span></span>

#### <a name="predictions"></a><span data-ttu-id="95587-388">예측</span><span class="sxs-lookup"><span data-stu-id="95587-388">Predictions</span></span>

- <span data-ttu-id="95587-389">**구독 이탈 예측**</span><span class="sxs-lookup"><span data-stu-id="95587-389">**Subscription churn prediction**</span></span>

  <span data-ttu-id="95587-390">안내식 경험을 따라 클라우드 서비스, 고객 멤버십 및 기타 부문과 같은 구독 영역에서 이탈 예측을 생성하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-390">Follow a guided experience to create churn prediction in subscription areas like cloud services, customer membership, and other sectors.</span></span> 

  <span data-ttu-id="95587-391">구독 이탈 예측 기능을 사용하면 데이터 과학자의 개입 없이 고객이 구독 기반 제품 또는 서비스의 사용을 중지할 가능성을 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-391">The subscription churn prediction feature enables you to predict the likelihood of a customer stopping the use of subscription-based products or services without engaging a data scientist.</span></span> <span data-ttu-id="95587-392">예측 점수를 사용하면 고객에 대한 다른 정보를 결합하여 이탈 위험이 높은 세그먼트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-392">Using the prediction score, you can combine other information about your customers to create segments of high churn risk.</span></span> <span data-ttu-id="95587-393">이 세그먼트의 도움으로 마케팅, 고객 지원 및 기타 시나리오에서 고객을 직접 타겟팅하여 특정 고객의 이탈 위험을 줄여 수익을 개선하고 비용을 절감할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-393">With the help of this segment, you can directly target customers in marketing, customer support, and other scenarios to reduce the risk of churn for specific customers to improve revenue and reduce cost.</span></span>

  <span data-ttu-id="95587-394">경험 내에서 이탈의 정의를 비즈니스에 특정한 시간 기반 기간으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-394">Within the experience, you can configure the definition of churn as a time-based window specific to your business.</span></span> <span data-ttu-id="95587-395">예를 들어 월간 구독 프로세스가 있는 비디오 스트리밍 비즈니스에서는 구독 만료 후 15일 후에 고객이 이탈한 것으로 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-395">For example, a video streaming business that has a monthly subscription process might want to consider a customer to have churned after 15 days after the expiration of their subscription.</span></span>

  <span data-ttu-id="95587-396">예측을 계속 진행하면 필요한 데이터를 안내하여 고객의 이탈을 예측하는 데 필요한 필드에 비즈니스 데이터를 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-396">As you continue through the prediction, we'll guide you through what data is needed, and enable you to map data about your business to fields required to predict churn for your customers.</span></span> <span data-ttu-id="95587-397">비즈니스 정보가 변경되면 변화하는 비즈니스 환경에 적응하기 위해 시스템의 새 정보에 대해 재교육하는 일정을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-397">As business information changes, you can also set a schedule to retrain on new information in your system to adapt to changing business circumstances.</span></span>    
  <span data-ttu-id="95587-398">자세한 내용은 [구독 이탈 예측(미리 보기)](predict-subscription-churn.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-398">For more information, see [Subscription churn prediction (preview)](predict-subscription-churn.md).</span></span>

#### <a name="segments"></a><span data-ttu-id="95587-399">세그먼트</span><span class="sxs-lookup"><span data-stu-id="95587-399">Segments</span></span>

- <span data-ttu-id="95587-400">**유사 고객 찾기**</span><span class="sxs-lookup"><span data-stu-id="95587-400">**Find similar customers**</span></span>
  
  <span data-ttu-id="95587-401">인공 지능을 사용하여 고객 기반에서 유사한 고객을 찾으십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-401">Find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="95587-402">이진 분류 기계 학습 모델은 확장된 세그먼트의 고객에게 유사성 점수를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-402">A binary classification machine learning model assigns a similarity score to customers in the expanded segment.</span></span> <span data-ttu-id="95587-403">점수는 원본세그먼트의 고객과의 유사성을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-403">The score is based on the similarity to customers in the source segment.</span></span> <span data-ttu-id="95587-404">유사성 점수에 따라 고객 프로필이 새로 생성된 세그먼트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="95587-404">Depending on the similarity score, customer profiles are added to a newly created segment.</span></span>

  <span data-ttu-id="95587-405">디지털 마케팅에서 유사 모델링이라고도 하는 AI 모델을 사용하여 더 많은 특성을 고려하여 고객의 다른 세그먼트와 유사한 고객을 찾는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="95587-405">Sometimes referred to as lookalike modeling in digital marketing, it uses an AI model to help find customers who are similar to another segment of your customers by factoring in more attributes.</span></span> <span data-ttu-id="95587-406">특성을 선택할 수 있을 뿐만 아니라 이 새 세그먼트에 있어야 하는 최대 고객 수를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-406">It not only allows you to pick the attributes but also allows you to specify the maximum number of customers who should be in this new segment.</span></span> <span data-ttu-id="95587-407">그런 다음 AI 모델은 선택한 특성을 기반으로 각 고객의 유사성 점수를 계산하고 평균 유사성 점수가 더 높은 고객을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-407">The AI model will then compute similarity scores for each customer based on your selected attributes and find customers with the higher average similarity score.</span></span> <span data-ttu-id="95587-408">결과 세그먼트에는 원래 세그먼트의 고객과 비슷해 보이는 고객이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="95587-408">The resulting segment will include customers who look similar to the customer in your original segment.</span></span>    
  <span data-ttu-id="95587-409">자세한 내용은 [유사한 고객](find-similar-customer-segments.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-409">For more information, see [Similar Customers](find-similar-customer-segments.md).</span></span>

- <span data-ttu-id="95587-410">**세그먼트 겹침 및 차별화 요소**</span><span class="sxs-lookup"><span data-stu-id="95587-410">**Segment overlap and differentiators**</span></span>

  <span data-ttu-id="95587-411">세그먼트 겹침을 통해 두 개 이상의 세그먼트에 공통적인 고객 수와 고객을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-411">Segment overlap lets you see how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="95587-412">예를 들어, 지출이 많은 세그먼트가 만족도가 높은 고객 세그먼트와 어떻게 겹치는지 또는 이탈하는 고객 세그먼트가 만족도가 낮은 고객 세그먼트와 어떻게 겹치는지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-412">For example, how a high-spenders segment overlaps with a high-satisfaction customers segment or how a churning customer segment overlaps with a low-satisfaction customers segment.</span></span> <span data-ttu-id="95587-413">또한 선택한 추가 특성을 기반으로 오버랩이 어떻게 변경되는지 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-413">Additionally, you can analyze how the overlap changes based on an extra attribute of your choice.</span></span>

  <span data-ttu-id="95587-414">세그먼트 차별화 요소는 한 세그먼트를 나머지 고객 또는 다른 세그먼트와 차별화하는 요소를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="95587-414">Segment differentiators reveal what differentiates one segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="95587-415">세그먼트를 식별하기만 하면 시스템이 가장 강력한 차별화 요소에서 가장 약한 항목까지 순위가 매겨진 차별화 요소 목록의 형태로 세그먼트를 구별하는 프로필 속성과 측정 값을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-415">All you need to do is identify a segment and the system will identify profile attributes and measures that distinguish the segment in the form of a ranked list of differentiators—from the strongest differentiator to the weakest.</span></span>    
  <span data-ttu-id="95587-416">자세한 내용은 [세그먼트 인사이트(미리 보기)](segment-insights.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-416">For more information, see [Segment insights (preview)](segment-insights.md).</span></span>

- <span data-ttu-id="95587-417">**세그먼트 수명**</span><span class="sxs-lookup"><span data-stu-id="95587-417">**Segment lifetime**</span></span>
  
  <span data-ttu-id="95587-418">세그먼트를 활성화 또는 비활성화하는 일정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-418">Define a schedule to activate or deactivate a segment.</span></span>    
  <span data-ttu-id="95587-419">자세한 내용은 [기존 세그먼트 관리](segments.md#manage-existing-segments)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-419">For more information, see [Manage existing segments](segments.md#manage-existing-segments).</span></span>

## <a name="may-2020-updates"></a><span data-ttu-id="95587-420">2020년 5월 업데이트</span><span class="sxs-lookup"><span data-stu-id="95587-420">May 2020 updates</span></span>

<span data-ttu-id="95587-421">2020년 5월 업데이트에는 몇 가지 기능, 성능 업그레이드 및 버그 수정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-421">The updates in May 2020 includes several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-may-2020"></a><span data-ttu-id="95587-422">2020년 5월의 새로운 기능 및 업데이트된 기능</span><span class="sxs-lookup"><span data-stu-id="95587-422">New and updated features in May 2020</span></span>

#### <a name="data-ingestion"></a><span data-ttu-id="95587-423">데이터 수집</span><span class="sxs-lookup"><span data-stu-id="95587-423">Data ingestion</span></span>

- <span data-ttu-id="95587-424">**실시간 데이터 수집: 기록 보기**</span><span class="sxs-lookup"><span data-stu-id="95587-424">**Real-time data ingestion: history views**</span></span>

  <span data-ttu-id="95587-425">API를 사용하여 실시간 업데이트를 수집하면 이러한 업데이트에 대해 최대 30일의 집계 기록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-425">When using our API to ingest real-time updates, you can see up to 30 days of aggregated history for these updates.</span></span> <span data-ttu-id="95587-426">결과, 원본 시스템 및 기타 유용한 메타데이터를 포함하여 성공 또는 실패한 모든 API 호출의 집계에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-426">You have access to aggregates of all successful or failed API calls including their outcome, source system, and other useful metadata.</span></span>    
  <span data-ttu-id="95587-427">자세한 내용은 [실시간 데이터 수집](real-time-data-ingestion.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-427">For more information, see [Real-time data ingestion](real-time-data-ingestion.md).</span></span>

- <span data-ttu-id="95587-428">**실시간 데이터 수집: 프로필 업데이트**</span><span class="sxs-lookup"><span data-stu-id="95587-428">**Real-time data ingestion: profile updates**</span></span>

  <span data-ttu-id="95587-429">실시간 데이터 수집이 확장되어 몇 초 안에 특정 사용자 프로필 필드의 변경 사항을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-429">This extension of the real-time data ingestion lets you see, within seconds, changes to specific user profile fields.</span></span>    
  <span data-ttu-id="95587-430">활동을 위한 실시간 기능 외에도 시스템은 프로파일 필드에 대한 짧은 지연 업데이트를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-430">In addition to the real-time functionality for activities, the system supports low latency updates to profile fields.</span></span> <span data-ttu-id="95587-431">프로필 필드에 대한 실시간 업데이트는 만료 시간을 가지므로 예약된 새로 고침을 대체하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-431">Real-time updates for profile fields have an expiration time and are therefore not a replacement for scheduled refreshes.</span></span>    
  <span data-ttu-id="95587-432">자세한 내용은 [실시간 데이터 수집](real-time-data-ingestion.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-432">For more information, see [Real-time data ingestion](real-time-data-ingestion.md).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="95587-433">확장성</span><span class="sxs-lookup"><span data-stu-id="95587-433">Extensibility</span></span>

- <span data-ttu-id="95587-434">**고객 카드 추가 기능에서 업데이트된 타임라인 및 페이지 매김**</span><span class="sxs-lookup"><span data-stu-id="95587-434">**Updated timeline and pagination on the Customer Card Add-in**</span></span>

  <span data-ttu-id="95587-435">고객 카드 추가 기능 솔루션의 시간 표시줄은 활동 시간 표시줄과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-435">The timeline of the Customer Card Add-in solution matches the activity timeline.</span></span> <span data-ttu-id="95587-436">타임라인의 페이지 매김이 개선되어 한 번에 최대 50개의 활동이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="95587-436">The pagination of the timeline improved, showing up to 50 activities at once.</span></span> <span data-ttu-id="95587-437">또한 시간 표시줄에 더 많은 활동을 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-437">It also allows loading more activities in the timeline.</span></span>    
  <span data-ttu-id="95587-438">자세한 내용은 [고객 카드 추가 기능](customer-card-add-in.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-438">For more information, see [Customer Card Add-in](customer-card-add-in.md).</span></span>

- <span data-ttu-id="95587-439">**세그먼트 변경을 위한 Power Automate 트리거**</span><span class="sxs-lookup"><span data-stu-id="95587-439">**Power Automate trigger for segment changes**</span></span>

  <span data-ttu-id="95587-440">Power Automate에 대한 트리거는 흐름을 구축할 수 있는 대상을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-440">Triggers for Power Automate define what you can build a flow from.</span></span> <span data-ttu-id="95587-441">새로 추가된 트리거를 사용하면 세그먼트에 대한 임계값을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-441">The newly added trigger lets you define a threshold for a segment.</span></span> <span data-ttu-id="95587-442">예를 들어, 정의된 임계값이 전달될 때 전송되는 알림을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-442">For example, you can create a notification that gets sent when the defined threshold is passed.</span></span>    
  <span data-ttu-id="95587-443">자세한 내용은 [Power Automate 커넥터](export-power-automate.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-443">For more information, see [Power Automate connector](export-power-automate.md).</span></span>

- <span data-ttu-id="95587-444">**사용자 지정 모델에 대한 다중 테넌트 지원**</span><span class="sxs-lookup"><span data-stu-id="95587-444">**Multitenant support for custom models**</span></span>

  <span data-ttu-id="95587-445">다른 Azure Machine Learning 테넌트의 웹 서비스를 사용하여 사용자 지정 모델에 대한 워크플로를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-445">Configure workflows for custom models with a web service of a different Azure Machine Learning tenant.</span></span> <span data-ttu-id="95587-446">사용자 지정 모델에 대한 새 워크플로를 만들 때 Azure Machine Learning 테넌트에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-446">You can sign in to the Azure Machine Learning tenant when creating a new workflow for custom models.</span></span> <span data-ttu-id="95587-447">이 기능은 사용자 지정 Azure Machine Learning 웹 서비스와 통합하는 기존 기능에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="95587-447">This capability is an addition to the existing capability of integrating with your own custom Azure Machine Learning web service.</span></span>    
  <span data-ttu-id="95587-448">자세한 내용은 [사용자 지정 기계 학습 모델](custom-models.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-448">For more information, see [Custom machine learning models](custom-models.md).</span></span>

#### <a name="segments"></a><span data-ttu-id="95587-449">세그먼트</span><span class="sxs-lookup"><span data-stu-id="95587-449">Segments</span></span>

- <span data-ttu-id="95587-450">**엔터티 경로 자동화**</span><span class="sxs-lookup"><span data-stu-id="95587-450">**Entity path automation**</span></span>

  <span data-ttu-id="95587-451">세그먼트를 만들 때 사용자는 엔터티 경로를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-451">When creating a segment, users need to define the entity path.</span></span> <span data-ttu-id="95587-452">이 기능은 엔터티 경로 정의를 자동화하기 위한 첫 번째 단계를 수행하므로 원하는 세분화 기준에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-452">This capability takes a first step at automating the entity path definition so you can focus on the segmentation criteria that you have in mind.</span></span>    
  <span data-ttu-id="95587-453">고객을 분류하려는 엔터티가 통합 고객 엔터티와 직접 관련된 경우 더 이상 엔터티 경로를 정의할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-453">If the entity by which you want to segment your customers is directly related to the unified customer entity, you won't need to define the entity path anymore.</span></span> <span data-ttu-id="95587-454">그러나 가능한 엔터티 경로가 둘 이상인 경우 여전히 수동으로 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-454">However, if there is more than one possible entity path, you still need to define it manually.</span></span>

- <span data-ttu-id="95587-455">**여러 세그먼트에 대한 작업**</span><span class="sxs-lookup"><span data-stu-id="95587-455">**Actions on multiple segments**</span></span>
  
  <span data-ttu-id="95587-456">사용자는 한 번의 클릭으로 여러 세그먼트를 선택하고 세그먼트 새로 고침과 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-456">Users can select multiple segments and take actions on them, like refreshing the segments, with a single click.</span></span>    

- <span data-ttu-id="95587-457">**세그먼트 새로 고침**</span><span class="sxs-lookup"><span data-stu-id="95587-457">**Refresh segments**</span></span>

  <span data-ttu-id="95587-458">사용자는 단일 세그먼트를 새로 고치거나 새로 고칠 세그먼트만 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-458">Users can refresh a single segment or select only the segments they want to refresh.</span></span>    

  
- <span data-ttu-id="95587-459">**복합 세그먼트 개선**</span><span class="sxs-lookup"><span data-stu-id="95587-459">**Improvements to compounded segments**</span></span>

  <span data-ttu-id="95587-460">사용자는 다른 세그먼트를 기반으로 세그먼트를 작성, 편집 및 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-460">Users can create, edit, and delete segments that are based on other segments.</span></span> <span data-ttu-id="95587-461">예를 들어, 세 번째 세그먼트에 구성된 다른 세그먼트에 구성된 세그먼트입니다.</span><span class="sxs-lookup"><span data-stu-id="95587-461">For example, a segment constructed on another segment that was constructed on a third segment.</span></span>    

- <span data-ttu-id="95587-462">**세그먼트 목록 페이지**</span><span class="sxs-lookup"><span data-stu-id="95587-462">**Segment list page**</span></span>

  <span data-ttu-id="95587-463">새로운 세그먼트 페이지 디자인에서는 목록 형식을 사용하여 한 번에 더 많은 세그먼트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-463">The new design of the segments page uses a list format that lets you see more segments at once.</span></span> <span data-ttu-id="95587-464">세그먼트를 빨리 찾기 위해 검색 필드가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-464">A search field is added to find segments quickly.</span></span> <span data-ttu-id="95587-465">사용자는 이제 여러 세그먼트를 한 번에 다운로드 또는 삭제하는 등의 작업을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-465">Users can now apply actions like downloading or deleting on multiple segments at once.</span></span> <span data-ttu-id="95587-466">새로운 추세 경험이 도입되어 세그먼트의 중요한 변화를 신속하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-466">A new trend experience is introduced to quickly identify significant changes on segments.</span></span>    
  <span data-ttu-id="95587-467">자세한 내용은 [세그먼트 만들기 및 관리](segments.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-467">For more information, see [Create and manage segments](segments.md).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="95587-468">시스템 관리</span><span class="sxs-lookup"><span data-stu-id="95587-468">System administration</span></span>

- <span data-ttu-id="95587-469">**Microsoft Dynamics 365 Online Government에서 사용할 수 있는 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="95587-469">**Customer Insights available in Microsoft Dynamics 365 Online Government**</span></span>

  <span data-ttu-id="95587-470">상호 작용을 위한 채널이 점점 더 많아짐에 따라 시민 데이터가 무수한 시스템에 분산되어 데이터가 분리되고 시민 상호 작용에 대한 단편화된 정보가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="95587-470">With more and more channels for interactions, citizen data is scattered across myriad systems, leading to siloed data, and a fragmented view of information about citizen interactions.</span></span> <span data-ttu-id="95587-471">채널을 통한 각 시민의 상호 작용을 완전히 파악하지 않으면 정부가 대규모로 현대화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-471">Without a complete view of each citizen's interactions across channels, it's impossible for governments to modernize at scale.</span></span> <span data-ttu-id="95587-472">Microsoft는 일관되고 반응적인 경험에 대한 시민의 기대에 부응하기 위해 정부의 기술 요구를 지원하기 위해 노력하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-472">Microsoft is committed to supporting the technology needs of government to keep up with citizen expectations for consistent and responsive experiences.</span></span>    
  <span data-ttu-id="95587-473">2020 릴리스 웨이브 1로 Dynamics 365 Customer Insights는 미국 정부 기관의 높은 규정 준수 요구를 충족하도록 구축된 환경인 GCC(정부 커뮤니티 클라우드)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-473">With 2020 release wave 1, Dynamics 365 Customer Insights will be available for the Government Community Cloud (GCC), an environment built to meet the higher compliance needs of United States government agencies.</span></span> <span data-ttu-id="95587-474">기관은 시민에 대한 통일된 관점을 확보하고 사전 구축된 AI를 사용하여 상호 작용을 개선하고 직원에게 권한을 부여하며 커뮤니티를 변화시키는 통찰력을 도출하는 동시에 IT 복잡성을 줄이고 미국 규정 준수 및 보안 표준을 충족시킵니다.</span><span class="sxs-lookup"><span data-stu-id="95587-474">Agencies gain a unified view of citizens and use prebuilt AI to derive insights that improve interactions, empower employees, and transform communities, while reducing IT complexity and meeting United States compliance and security standards.</span></span> <span data-ttu-id="95587-475">Dynamics 365 Government는 미국 연방 기관이 FedRAMP(Federal Risk and Authorization Management Program)의 까다로운 요구 사항을 충족하므로 미국 연방 기관이 Microsoft Cloud의 비용 절감 및 엄격한 보안 혜택을 누릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-475">Dynamics 365 Government meets the demanding requirements of the US Federal Risk and Authorization Management Program (FedRAMP), enabling United States federal agencies to benefit from the cost savings and rigorous security of the Microsoft Cloud.</span></span>

## <a name="april-2020-updates"></a><span data-ttu-id="95587-476">2020년 4월 업데이트</span><span class="sxs-lookup"><span data-stu-id="95587-476">April 2020 updates</span></span>

<span data-ttu-id="95587-477">2020년 4월 업데이트에는 몇 가지 기능, 성능 업그레이드 및 버그 수정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-477">The updates in April 2020 includes several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-april-2020"></a><span data-ttu-id="95587-478">2020년 4월의 새로운 기능 및 업데이트된 기능</span><span class="sxs-lookup"><span data-stu-id="95587-478">New and updated features in April 2020</span></span>

#### <a name="activities"></a><span data-ttu-id="95587-479">활동</span><span class="sxs-lookup"><span data-stu-id="95587-479">Activities</span></span>

- <span data-ttu-id="95587-480">**활동 엔터티를 표준 활동 유형에 매핑**</span><span class="sxs-lookup"><span data-stu-id="95587-480">**Map activity entity to standard activity type**</span></span>
  
  <span data-ttu-id="95587-481">현재 활동 구성 및 스토리지는 타임라인에서 볼 수 있도록 정적 디자인을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-481">Activity configuration and storage are currently based on a static design to view them in a timeline.</span></span> <span data-ttu-id="95587-482">AI 모델에서 여러 사용 사례를 사용할 수 있는 활동의 의미론적 의미는 현재 완전히 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-482">The semantic meaning of activities, which has potential for multiple use-cases in AI models, isn't fully used at the moment.</span></span> <span data-ttu-id="95587-483">우리는 활동 유형과 활동에 대한 의미론적 이해를 바탕으로 활동 타임라인을 보다 역동적으로 만들 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="95587-483">We plan to make the activity timeline more dynamic, based on the activity type and better semantic understanding of the activities.</span></span> <span data-ttu-id="95587-484">이 기능은 수집된 활동에 대해 Common Data Model에 정의된 활동 유형을 식별하는 데 목적이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-484">This feature aims to identify the activity type as defined in Common Data Model for any ingested activity.</span></span>
  <span data-ttu-id="95587-485">자세한 내용은 [고객 활동](activities.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-485">For more information, see [Customer activities](activities.md).</span></span>

#### <a name="data-ingestion"></a><span data-ttu-id="95587-486">데이터 수집</span><span class="sxs-lookup"><span data-stu-id="95587-486">Data ingestion</span></span>

- <span data-ttu-id="95587-487">**실시간 데이터 수집: 활동**</span><span class="sxs-lookup"><span data-stu-id="95587-487">**Real-time data ingestion: activities**</span></span>
  
  <span data-ttu-id="95587-488">실시간 데이터 수집 기능은 이후에 예약된 새로 고침이 데이터 원본에서이 데이터를 가져올 때까지 즉시 사용할 데이터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-488">Real-time data ingestion provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>    
  <span data-ttu-id="95587-489">자세한 내용은 [실시간 데이터 수집](real-time-data-ingestion.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-489">For more information, see [Real-time data ingestion](real-time-data-ingestion.md).</span></span>

- <span data-ttu-id="95587-490">**데이터 준비 개선**</span><span class="sxs-lookup"><span data-stu-id="95587-490">**Improvements to data preparation**</span></span>
  
  <span data-ttu-id="95587-491">엔터티에서 수집된 데이터에 대해 자세히 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-491">Learn more about the data ingested in an entity.</span></span> <span data-ttu-id="95587-492">데이터 요약을 통해 적절한 조치를 취하는 데 도움이 되는 데이터 품질 특성을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-492">With the data summary, you can understand the data quality characteristics that can help to take appropriate action.</span></span>    
  <span data-ttu-id="95587-493">자세한 내용은 [엔터티 데이터 살펴보기](entities.md#exploring-a-specific-entitys-data)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-493">For more information, see [Explore entity data](entities.md#exploring-a-specific-entitys-data).</span></span>

- <span data-ttu-id="95587-494">**Common Data Service로 Dynamics 365에서 분석 데이터 수집**</span><span class="sxs-lookup"><span data-stu-id="95587-494">**Ingest analytical data from Dynamics 365 with Common Data Service**</span></span>
  
  <span data-ttu-id="95587-495">Common Data Service는 데이터 원본을 만드는 방법으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-495">Common Data Service is available as a way to create data sources.</span></span> <span data-ttu-id="95587-496">기존 Dynamics 365 고객은 Common Data Service에서 Customer Insights로 분석 엔터티를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-496">Existing Dynamics 365 customers can ingest analytical entities from Common Data Service to Customer Insights.</span></span> <span data-ttu-id="95587-497">단일 데이터 원본은 동시에 동일한 Common Data Service 관리형 레이크를 Customer Insights 환경에서 동시에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-497">A single data source can simultaneously use the same Common Data Service-managed lake in a Customer Insights environment.</span></span>    
  <span data-ttu-id="95587-498">자세한 내용은 [Common Data Service 관리형 데이터 레이크에서 데이터에 연결](connect-common-data-service-lake.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-498">For more information, see [Connect to data in a Common Data Service managed data lake](connect-common-data-service-lake.md).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="95587-499">확장성</span><span class="sxs-lookup"><span data-stu-id="95587-499">Extensibility</span></span>

- <span data-ttu-id="95587-500">**LiveRamp로 내보내기**</span><span class="sxs-lookup"><span data-stu-id="95587-500">**Export to LiveRamp**</span></span>

  <span data-ttu-id="95587-501">LiveRamp®에서 데이터를 활성화하여 디지털, 소셜 및 TV 에코시스템에서 500개 이상의 플랫폼에 연결하십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-501">Activate your data in LiveRamp® to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="95587-502">LiveRamp의 데이터를 사용하여 광고 캠페인을 타겟팅, 억제 및 개인화하십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-502">Use your data in LiveRamp for targeting, suppressing, and personalizing ad campaigns.</span></span>    
  <span data-ttu-id="95587-503">자세한 내용은 [LiveRamp&reg; 커넥터](export-liveramp.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-503">For more information, see [LiveRamp&reg; connector](export-liveramp.md).</span></span>

- <span data-ttu-id="95587-504">**Customer Insights Teams 추가 기능**</span><span class="sxs-lookup"><span data-stu-id="95587-504">**Customer Insights Teams Add-in**</span></span>
  
  <span data-ttu-id="95587-505">봇은 통합 고객 프로필을 위한 조회 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-505">The bot provides lookup capabilities for unified customer profiles.</span></span> <span data-ttu-id="95587-506">결과 고객 프로필에서 최대 15개의 필드가 있는 카드가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="95587-506">It will show a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="95587-507">여러 개의 일치 항목은 프로필을 선택할 수 있는 결과 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-507">Multiple matches return a list of results where you can select a profile.</span></span>    
  <span data-ttu-id="95587-508">자세한 내용은 [Customer Insights용 Teams 봇](export-teams-bot.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-508">For more information, see [Teams bot for Customer Insights](export-teams-bot.md).</span></span>

#### <a name="measures"></a><span data-ttu-id="95587-509">측정값</span><span class="sxs-lookup"><span data-stu-id="95587-509">Measures</span></span>

- <span data-ttu-id="95587-510">**측정값 목록 페이지**</span><span class="sxs-lookup"><span data-stu-id="95587-510">**Measure list page**</span></span>
  
  <span data-ttu-id="95587-511">측정값 페이지의 개선 사항에는 단일 측정값 및 한 번에 여러 측정값에 대한 작업 지원이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="95587-511">Improvements to the measures page include support for actions on a single measure and on multiple measures at once.</span></span> <span data-ttu-id="95587-512">또한 측정값을 빠르게 찾고 추적할 수 있는 검색 필드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-512">Additionally, you'll find a search field to find and track measures quickly.</span></span>    
  <span data-ttu-id="95587-513">자세한 내용은 [세그먼트 만들기 및 관리](segments.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-513">For more information, see [Create and manage segments](segments.md).</span></span>

- <span data-ttu-id="95587-514">**복합 측정값 개선**</span><span class="sxs-lookup"><span data-stu-id="95587-514">**Improvements to compounded measures**</span></span>
  
  <span data-ttu-id="95587-515">사용자는 다른 측정값을 기반으로 측정값을 작성, 편집 및 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-515">Users can create, edit, and delete measures that are based on other measures.</span></span> <span data-ttu-id="95587-516">예를 들어, 세 번째 측정값에 구성된 다른 측정값에 구성된 측정값입니다.</span><span class="sxs-lookup"><span data-stu-id="95587-516">For example, a measure constructed on another measure that was constructed on a third measure.</span></span>

#### <a name="segments"></a><span data-ttu-id="95587-517">세그먼트</span><span class="sxs-lookup"><span data-stu-id="95587-517">Segments</span></span>

- <span data-ttu-id="95587-518">**다른 연산자**</span><span class="sxs-lookup"><span data-stu-id="95587-518">**Another operator**</span></span>
  
  <span data-ttu-id="95587-519">인세트 연산자를 사용하면 몇 가지 가능한 문자열 값으로 고객을 세분화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-519">The In-set operator allows segmentation for customers by several possible string values.</span></span> <span data-ttu-id="95587-520">이 연산자를 추가하기 전에 여러 OR 조건을 가진 세그먼트를 구성해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-520">Before this operator was added, you had to construct such segments with multiple OR conditions.</span></span> <span data-ttu-id="95587-521">인세트 연산자를 사용하면 단일 조건으로 이를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-521">The In-set operator lets you do that with a single condition.</span></span>    
  <span data-ttu-id="95587-522">자세한 내용은 [세그먼트 만들기 및 관리](segments.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95587-522">For more information, see [Create and manage segments](segments.md).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="95587-523">시스템 관리</span><span class="sxs-lookup"><span data-stu-id="95587-523">System administration</span></span>

- <span data-ttu-id="95587-524">**구성 설정을 새 환경으로 복사**</span><span class="sxs-lookup"><span data-stu-id="95587-524">**Copy configuration settings to a new environment**</span></span>
  
  <span data-ttu-id="95587-525">한 환경에서 다른 환경으로 구성을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-525">Copy your configuration from one environment to another.</span></span> <span data-ttu-id="95587-526">새 환경을 만드는 동안 구성을 복사할 기존 환경을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-526">While creating a new environment, you can select an existing environment you want to copy the configuration from.</span></span> <span data-ttu-id="95587-527">현재 데이터 원본, 데이터 통합, 관계, 측정 및 복사할 세그먼트를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="95587-527">We currently support data sources, data unification, relationships, measures, and segments to be copied.</span></span> <span data-ttu-id="95587-528">데이터 원본 자격 증명 및 실제 데이터는 복사되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95587-528">Data source credentials and actual data aren't copied.</span></span>    
  <span data-ttu-id="95587-529">자세한 내용은 [환경 관리](manage-environments.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95587-529">For more information, see [Manage environments](manage-environments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]