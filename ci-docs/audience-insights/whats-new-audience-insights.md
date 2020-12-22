---
title: 신규 및 향후 기능
description: 새로운 기능, 개선 사항 및 버그 수정에 대한 정보입니다.
ms.date: 11/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 07b4bee0445f9cd7d53a37cd405af839feb07ae3
ms.sourcegitcommit: 4004eadac7a65e50e0a409cb925958523c2b6348
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/30/2020
ms.locfileid: "4650012"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a><span data-ttu-id="b0412-103">Dynamics 365 Customer Insights 대상 그룹 인사이트의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="b0412-103">What's new in the audience insights capability of Dynamics 365 Customer Insights</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="b0412-104">최신 업데이트를 발표하게 된 것을 기쁘게 생각합니다!</span><span class="sxs-lookup"><span data-stu-id="b0412-104">We're excited to announce our newest updates!</span></span> <span data-ttu-id="b0412-105">이 문서는 공개 미리 보기 기능, 일반 가용성 향상 및 기능 업데이트를 요약합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-105">This article summarizes public preview features, general availability enhancements, and feature updates.</span></span> <span data-ttu-id="b0412-106">장기적인 기능 계획을 보려면 [Dynamics 365 및 Power Platform 릴리스 계획](https://docs.microsoft.com/dynamics365/release-plans/)을 살펴보십시오.</span><span class="sxs-lookup"><span data-stu-id="b0412-106">To see the long-term feature plans, take a look at the [Dynamics 365 and Power Platform release plans](https://docs.microsoft.com/dynamics365/release-plans/).</span></span>

<span data-ttu-id="b0412-107">다음 비디오를 시청하여 지난 6개월 동안 계획된 기능에 대해 자세히 알아볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-107">You can also watch the following video to learn more about the capabilities planned for the last six months.</span></span>

> [!VIDEO https://www.youtube.com/embed/jQh-7pscH30]

<span data-ttu-id="b0412-108">업데이트는 지역별로 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-108">We roll out updates on a region-by-region basis.</span></span> <span data-ttu-id="b0412-109">따라서 특정 지역은 다른 지역보다 먼저 기능을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-109">So certain regions might see features before others.</span></span> <span data-ttu-id="b0412-110">다르게 지정하지 않으면 별도의 조치를 취할 필요가 없으며 가동 중지 시간 없이 자동으로 앱을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-110">Unless specified differently, you don't need to take any action and we'll update the app automatically with no downtime.</span></span>

> [!TIP]
> <span data-ttu-id="b0412-111">기능 요청 및 제품 제안에 대한 투표를 제출하려면 [Dynamics 365 응용 프로그램 아이디어 포털](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights)로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="b0412-111">To submit and vote on feature requests and product suggestions, go to the [Dynamics 365 Application Ideas portal](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).</span></span>

## <a name="november-2020-updates"></a><span data-ttu-id="b0412-112">2020년 11월 업데이트</span><span class="sxs-lookup"><span data-stu-id="b0412-112">November 2020 updates</span></span>

<span data-ttu-id="b0412-113">2020년 11월 업데이트에는 여러 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-113">The updates in November 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-november-2020"></a><span data-ttu-id="b0412-114">2020년 11월의 새로운 기능 및 업데이트된 기능</span><span class="sxs-lookup"><span data-stu-id="b0412-114">New and updated features in November 2020</span></span>

#### <a name="data-enrichment"></a><span data-ttu-id="b0412-115">데이터 보강</span><span class="sxs-lookup"><span data-stu-id="b0412-115">Data enrichment</span></span>

- <span data-ttu-id="b0412-116">**SFTP(보안 파일 전송 프로토콜) 사용자 지정 가져오기를 통해 자체 보강 데이터 가져 오기**</span><span class="sxs-lookup"><span data-stu-id="b0412-116">**Bring your own enrichment data via Secure File Transfer Protocol (SFTP) custom import**</span></span>
  
  <span data-ttu-id="b0412-117">SFTP 사용자 지정 가져오기를 사용하면 데이터 통합 프로세스를 거치지 않아도 되는 보강 데이터를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-117">SFTP custom import lets you to import enrichment data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="b0412-118">SFTP 사용자 지정 가져오기에 대해 자세히 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-118">Learn more about SFTP custom import.</span></span>

  <span data-ttu-id="b0412-119">자세한 내용은 [사용자 지정 데이터로 고객 프로필 강화(미리 보기)](enrichment-SFTP-custom-import.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-119">For more information, see [Enrich customer profiles with custom data (preview)](enrichment-SFTP-custom-import.md).</span></span>
 
- <span data-ttu-id="b0412-120">**HERE Technologies의 위치 데이터로 고객 데이터 보강**</span><span class="sxs-lookup"><span data-stu-id="b0412-120">**Enrich your customer data with location data from HERE Technologies**</span></span>

  <span data-ttu-id="b0412-121">HERE Technologies의 데이터 보강 서비스를 사용하면 주소 정규화, 위도 및 경도 추출 등을 통해 고객에 대한 보다 정확한 위치 이해를 구축할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-121">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span> <span data-ttu-id="b0412-122">HERE Technologies로 보강하는 방법에 대해 자세히 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-122">Learn more about enriching with HERE Technologies.</span></span>

  <span data-ttu-id="b0412-123">자세한 내용은 [HERE Technologies로 고객 프로필 보강(미리 보기)](enrichment-here.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-123">For more information, see [Enrichment of customer profiles with HERE Technologies](enrichment-here.md).</span></span>

#### <a name="data-unification"></a><span data-ttu-id="b0412-124">데이터 통합</span><span class="sxs-lookup"><span data-stu-id="b0412-124">Data unification</span></span>

- <span data-ttu-id="b0412-125">**스토리지 계정에서 선택한 엔터티 및 필드에 대한 데이터 프로파일링을 활성화하는 유연성**</span><span class="sxs-lookup"><span data-stu-id="b0412-125">**Flexibility to enable data profiling on selected entities and fields from your storage account**</span></span>

  <span data-ttu-id="b0412-126">데이터 수집 프로세스의 일부로 데이터 프로파일링을 사용하도록 설정하려는 Azure Data Lake 스토리지 계정의 Common Data Model 폴더에서 데이터 엔터티 및 필드를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-126">You can indicate which data entities and fields from a Common Data Model folder in your Azure Data Lake storage account you want to enable data profiling as part of the data ingestion process.</span></span>

  <span data-ttu-id="b0412-127">자세한 내용은 [Common Data Model 폴더에 연결](connect-common-data-model.md#connect-to-a-common-data-model-folder)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-127">For more information, see [Connect to a Common Data Model folder](connect-common-data-model.md#connect-to-a-common-data-model-folder).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="b0412-128">확장성</span><span class="sxs-lookup"><span data-stu-id="b0412-128">Extensibility</span></span>

- <span data-ttu-id="b0412-129">**Google 광고를 통해 세그먼트 활성화**</span><span class="sxs-lookup"><span data-stu-id="b0412-129">**Activate your segments through Google Ads**</span></span>

  <span data-ttu-id="b0412-130">통합 고객 프로필의 세그먼트를 Google 광고 대상 그룹 목록으로 내보내고 이러한 목록을 사용하여 Google 검색, Gmail, YouTube 및 Google 디스플레이 네트워크에서 광고합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-130">Export segments from to Google Ads audience lists and use these lists to advertise on Google Search, Google Display Network, YouTube, and Gmail.</span></span> <span data-ttu-id="b0412-131">Google 광고를 통해 세그먼트를 활성화하는 방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-131">Learn more about activating your segments through Google Ads.</span></span>

  <span data-ttu-id="b0412-132">자세한 내용은 [Google 광고용 커네터](export-google-ads.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-132">For more information, see [Connector for Google Ads](export-google-ads.md).</span></span>

- <span data-ttu-id="b0412-133">**Marketo를 통해 세그먼트 활성화**</span><span class="sxs-lookup"><span data-stu-id="b0412-133">**Activate your segments through Marketo**</span></span>

  <span data-ttu-id="b0412-134">Marketo 대상 그룹에게 세그먼트를 내보내고 이러한 대상 그룹을 마케팅 자동화에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-134">Export segments to Marketo audiences and use these audiences for marketing automation.</span></span> <span data-ttu-id="b0412-135">Marketo를 통해 세그먼트를 활성화하는 방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-135">Learn more about activating your segments through Marketo.</span></span> 

  <span data-ttu-id="b0412-136">자세한 내용은 [Marketo용 커네터](export-marketo.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-136">For more information, see [Connector for Marketo](export-marketo.md).</span></span>

- <span data-ttu-id="b0412-137">**DotDigital을 통해 세그먼트 활성화**</span><span class="sxs-lookup"><span data-stu-id="b0412-137">**Activate your segments through DotDigital**</span></span>

  <span data-ttu-id="b0412-138">세그먼트를 DotDigital로 내보내고 마케팅 목적으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-138">Export segments to DotDigital and use them for marketing purposes.</span></span> <span data-ttu-id="b0412-139">DotDigital을 통해 세그먼트를 활성화하는 방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-139">Learn more about activating your segments through DotDigital.</span></span> 

  <span data-ttu-id="b0412-140">자세한 내용은 [DotDigital용 커네터](export-dotdigital.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-140">For more information, see [Connector for DotDigital](export-dotdigital.md).</span></span>

#### <a name="predictions"></a><span data-ttu-id="b0412-141">예측</span><span class="sxs-lookup"><span data-stu-id="b0412-141">Predictions</span></span>

- <span data-ttu-id="b0412-142">**트랜잭션 이탈 예측**</span><span class="sxs-lookup"><span data-stu-id="b0412-142">**Predict transactional churn**</span></span>

  <span data-ttu-id="b0412-143">트랜잭션 이탈 예측 기능을 사용하면 데이터 과학자의 도움 없이 고객이 제품 또는 서비스 구매를 중단할 가능성을 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-143">The transaction churn prediction feature enables you, without the help of a data scientist, to predict the likelihood of a customer to stop purchasing products or services.</span></span>  <span data-ttu-id="b0412-144">예측 점수를 사용하면 고객 가치와 같은 고객에 대한 다른 정보를 결합하여 이탈 위험이 높거나 가치가 높은 고객 세그먼트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-144">Using the prediction score, you can combine other information about your customers, like customer value, to create segments of high churn risk or high value customers.</span></span> <span data-ttu-id="b0412-145">이 세그먼트를 사용하여 마케팅 활동, 고객 지원 및 기타 시나리오를 통해 고객을 직접 타겟팅하여 이탈 위험을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-145">Use this segment to directly target customers through marketing activities, customer support, and other scenarios to reduce churn risk.</span></span>
 
  <span data-ttu-id="b0412-146">이탈의 정의를 비즈니스에 특정한 시간 기반 창으로 구성하고 고객이 이탈한 것으로 간주되는시기를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-146">Configure the definition of churn as a time-based window specific to your business and define when customers are considered churned.</span></span> <span data-ttu-id="b0412-147">예를 들어 식료품점에서는 지난 30일 동안 구매한 적이 없는 고객을 이탈한 것으로 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-147">For example, a grocery store may want to consider a customer churned if they have not purchased anything in the past 30 days.</span></span>
 
  <span data-ttu-id="b0412-148">예측을 계속 생성하면 필요한 데이터를 안내하고 비즈니스에 대한 데이터를 고객의 이탈을 예측하는 데 필요한 필드에 매핑 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-148">As you continue creating the prediction, we'll guide you what data is needed, and enable you to map data about your business to fields required to predict churn for your customers.</span></span> <span data-ttu-id="b0412-149">변화하는 비즈니스 환경에 적응하기 위해 시스템의 새로운 정보를 기반으로 모델을 재교육하는 일정을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-149">You can also set a schedule to retrain the model based on new information in your system to adapt to changing business circumstances.</span></span>
 
  <span data-ttu-id="b0412-150">자세한 내용은 [트랜잭션 이탈 예측(미리 보기)](predict-transactional-churn.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-150">For more information, see [Transactional churn prediction (preview)](predict-transactional-churn.md).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="b0412-151">시스템 관리</span><span class="sxs-lookup"><span data-stu-id="b0412-151">System administration</span></span>

- <span data-ttu-id="b0412-152">**환경 재설정**</span><span class="sxs-lookup"><span data-stu-id="b0412-152">**Reset environment**</span></span>

  <span data-ttu-id="b0412-153">새로 시작하려면 선택한 인스턴스의 환경에서 모든 항목을 재설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-153">Reset everything in an environment of a selected instance to start fresh.</span></span>

  <span data-ttu-id="b0412-154">자세한 내용은 [기존 환경 초기화](manage-environments.md#reset-an-existing-environment)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-154">For more information, see [Reset an existing environment](manage-environments.md#reset-an-existing-environment).</span></span>


- <span data-ttu-id="b0412-155">**서비스 주체를 사용하여 Azure Data Lake 스토리지 계정에 연결**</span><span class="sxs-lookup"><span data-stu-id="b0412-155">**Connect to your Azure Data Lake storage account using a service principal**</span></span>

  <span data-ttu-id="b0412-156">Azure 서비스 주체를 사용하여 스토리지 계정에 데이터 출력을 쓰고 데이터를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-156">Write data output to and read data from your storage account using an Azure service principal.</span></span> <span data-ttu-id="b0412-157">기존 스토리지 계정 연결은 계정 키를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-157">Existing storage account connections can continue to use the account key.</span></span> <span data-ttu-id="b0412-158">또한 앞으로 서비스 주체를 사용할 수 있는 업그레이드 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-158">They also offer an upgrade option to use the service principal moving forward.</span></span> <span data-ttu-id="b0412-159">새 연결은 스토리지 계정에 대한 서비스 주체 인증 방법을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-159">New connections will be based on the service principal authentication method for your storage account.</span></span>

  <span data-ttu-id="b0412-160">자세한 내용은 대상 그룹 인사이트를 위해 [Azure 서비스 주체를 사용하여 Azure Data Lake Storage Gen2 계정에 연결](connect-service-principal.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-160">For more information, see [Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights](connect-service-principal.md).</span></span>

## <a name="october-2020-updates"></a><span data-ttu-id="b0412-161">2020년 10월 업데이트</span><span class="sxs-lookup"><span data-stu-id="b0412-161">October 2020 updates</span></span>

<span data-ttu-id="b0412-162">2020년 10월 업데이트에는 여러 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-162">The updates in October 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-october-2020"></a><span data-ttu-id="b0412-163">2020년 10월의 새로운 기능 및 업데이트된 기능</span><span class="sxs-lookup"><span data-stu-id="b0412-163">New and updated features in October 2020</span></span>

#### <a name="extensibility"></a><span data-ttu-id="b0412-164">확장성</span><span class="sxs-lookup"><span data-stu-id="b0412-164">Extensibility</span></span>

- <span data-ttu-id="b0412-165">**Mailchimp에 내보내기**</span><span class="sxs-lookup"><span data-stu-id="b0412-165">**Export to Mailchimp**</span></span>

<span data-ttu-id="b0412-166">Mailchimp의 기존 대상 목록으로 세그먼트를 내보내 고객에게 개인화된 이메일 경험을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-166">Export segments to existing audience lists in Mailchimp to provide a personalized email experience for your customers.</span></span>

<span data-ttu-id="b0412-167">자세한 내용은 [Mailchimp용 커네터](export-mailchimp.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-167">For more information, see [Connector for Mailchimp](export-mailchimp.md).</span></span>

#### <a name="data-enrichment"></a><span data-ttu-id="b0412-168">데이터 보강</span><span class="sxs-lookup"><span data-stu-id="b0412-168">Data enrichment</span></span>

- <span data-ttu-id="b0412-169">**일치 엔터티에서 원본 레코드 중복 제거**</span><span class="sxs-lookup"><span data-stu-id="b0412-169">**Deduplicate the source records in a Match entity**</span></span>

<span data-ttu-id="b0412-170">중복 레코드를 식별하기 위해 일치 프로세스에 사용되는 엔터티에 대한 중복 제거 규칙을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-170">Specify deduplication rules on entities used in the match process to identify duplicate records.</span></span> <span data-ttu-id="b0412-171">하나의 레코드로 병합하고 모든 소스 레코드를이 병합된 레코드에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-171">Merge them into one record and link all the source records to this merged record.</span></span> <span data-ttu-id="b0412-172">이 중복 제거된 레코드는 엔터티 간 일치 프로세스에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-172">This deduplicated record will then be used in the cross-entity matching process.</span></span>

<span data-ttu-id="b0412-173">자세한 내용은 [일치 항목에 대한 중복 제거 정의](match-entities.md#define-deduplication-on-a-match-entity)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-173">For more information, see [Define deduplication on a match entity](match-entities.md#define-deduplication-on-a-match-entity).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="b0412-174">시스템 관리</span><span class="sxs-lookup"><span data-stu-id="b0412-174">System administration</span></span>

- <span data-ttu-id="b0412-175">**오케스트레이션: 병합의 새로운 새로 고침 옵션**</span><span class="sxs-lookup"><span data-stu-id="b0412-175">**Orchestration: New refresh option in Merge**</span></span>

<span data-ttu-id="b0412-176">오늘까지 병합 프로세스를 실행할 때 시스템은 병합 및 후속 프로세스에 의존하는 모든 다운 스트림 프로세스를 실행했습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-176">Until today, when you run the merge process, the system ran all the downstream processes that depend on merge and subsequent processes.</span></span> <span data-ttu-id="b0412-177">이제 병합 프로세스(통합 고객 엔터티)의 출력을 세그먼트 또는 측정과 같은 다운스트림 처리에 사용하기 전에 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-177">You can now verify the output of the merge process (the unified customer entity) before using it in downstream processing like segments or measures.</span></span>
<span data-ttu-id="b0412-178">병합 페이지에서 이제 병합 단계만 실행하고 이 프로세스만 실행하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-178">On the merge page, you can now choose to run only the merge step and run only this process.</span></span> <span data-ttu-id="b0412-179">모든 다운스트림 프로세스도 새로 고치려면 병합 및 다운스트림 프로세스 실행을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-179">To refresh all the downstream processes too, you can choose run merge and downstream processes.</span></span> 

## <a name="september-2020-updates"></a><span data-ttu-id="b0412-180">2020년 9월 업데이트</span><span class="sxs-lookup"><span data-stu-id="b0412-180">September 2020 updates</span></span>

<span data-ttu-id="b0412-181">2020년 9월 업데이트에는 여러 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-181">The updates in September 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-september-2020"></a><span data-ttu-id="b0412-182">2020년 9월의 새로운 기능 및 업데이트된 기능</span><span class="sxs-lookup"><span data-stu-id="b0412-182">New and updated features in September 2020</span></span>

#### <a name="activities"></a><span data-ttu-id="b0412-183">작업</span><span class="sxs-lookup"><span data-stu-id="b0412-183">Activities</span></span>

- <span data-ttu-id="b0412-184">**특성 의미론의 지능형 예측**</span><span class="sxs-lookup"><span data-stu-id="b0412-184">**Intelligent prediction of attribute semantics**</span></span>

<span data-ttu-id="b0412-185">이 새로운 기능은 데이터 통합 프로세스에 전달되는 입력 특성의 의미 유형을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-185">This new feature predicts the semantic types of input attributes that are passed on to the data unification process.</span></span> <span data-ttu-id="b0412-186">정확도를 높이고 시간을 절약하는 기계 학습 모델을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-186">It uses machine learning models that improve accuracy and save time.</span></span>

#### <a name="enrichments"></a><span data-ttu-id="b0412-187">보강</span><span class="sxs-lookup"><span data-stu-id="b0412-187">Enrichments</span></span>

- <span data-ttu-id="b0412-188">**Experian의 인구 통계 보강**</span><span class="sxs-lookup"><span data-stu-id="b0412-188">**Demographics enrichment from Experian**</span></span>

<span data-ttu-id="b0412-189">Experian의 인구 통계 보강이 이제 미리 보기로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-189">The demographics enrichment from Experian is now available in preview.</span></span> <span data-ttu-id="b0412-190">Experian은 소비자 및 기업 신용보고 및 마케팅 서비스 분야의 글로벌 리더입니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-190">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="b0412-191">[Experian의 데이터 보강 서비스](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)를 사용하면 가구 규모, 소득 등과 같은 인구 통계 데이터로 고객 프로필을 강화하여 고객에 대한 더 깊은 이해를 구축할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-191">With [Experian’s data enrichment services](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage), you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

<span data-ttu-id="b0412-192">이 기능을 사용하려면 활성 Experian 구독이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-192">To use this feature, you must have an active Experian subscription.</span></span>

<span data-ttu-id="b0412-193">자세한 내용은 [Experian의 인구 통계로 고객 프로필 보강](enrichment-experian.md)을 참고하세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-193">For more information, see [Enrich customer profiles with demographics from Experian](enrichment-experian.md)</span></span>


#### <a name="system-administration"></a><span data-ttu-id="b0412-194">시스템 관리</span><span class="sxs-lookup"><span data-stu-id="b0412-194">System administration</span></span>

- <span data-ttu-id="b0412-195">**작업 세부 정보 창**</span><span class="sxs-lookup"><span data-stu-id="b0412-195">**Task details pane**</span></span>

<span data-ttu-id="b0412-196">작업 세부 정보 창에서는 시스템에서 실행하는 작업에 대한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-196">The task details pane enables you to see details about tasks that the system runs.</span></span> <span data-ttu-id="b0412-197">구성 문제를 식별하고 솔루션을 찾는 편리한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-197">It's a handy way to identify issues with the configuration and find solutions.</span></span>
<span data-ttu-id="b0412-198">오류 메시지를 검토하여 잠재적 문제를 해결하는 방법을 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="b0412-198">Review the error messages see how you address potential issues.</span></span>
 
- <span data-ttu-id="b0412-199">**추가 페이지에 추가된 처리 정보**</span><span class="sxs-lookup"><span data-stu-id="b0412-199">**Processing information added to additional pages**</span></span>

<span data-ttu-id="b0412-200">이 개선 사항은 **엔터티** 및 **고객** 페이지의 엔터티의 상태에 대한 정보를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-200">This improvement adds information about the status of your entities on the **Entities** and **Customers** page.</span></span>
 
<span data-ttu-id="b0412-201">또한 이 두 페이지 모두에서 작업 세부 정보와 함께 프로세스 진행 상황에 대한 세부 정보를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-201">Additionally, you can find details about the progress of processes, along with the task details, on both of these pages.</span></span>

- <span data-ttu-id="b0412-202">**시스템 상태 페이지 개선**</span><span class="sxs-lookup"><span data-stu-id="b0412-202">**Improvements to system status page**</span></span>

<span data-ttu-id="b0412-203">데이터 내보내기를 검토할 때 **시스템** > **상태** 에서 상태 세부 정보 표의 구조를 개선했습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-203">We improved the structure of the status details table on **System** > **Status** when reviewing data exports.</span></span>
 
<span data-ttu-id="b0412-204">또한 **세부 정보** 열의 오류가 더 상세하고 실행 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-204">Additionally, errors in the **Details** column are now more detailed and actionable.</span></span> 
 
- <span data-ttu-id="b0412-205">**취소는 작업을 이전 상태로 되돌립니다.**</span><span class="sxs-lookup"><span data-stu-id="b0412-205">**Cancel reverts job back to previous state**</span></span>

<span data-ttu-id="b0412-206">예를 들어 매치 프로세스에서 작업을 취소하면 최근 상태로 되돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-206">When you cancel a task, for example, in the match process, it will revert back to its latest state.</span></span> <span data-ttu-id="b0412-207">예를 들어 매치 프로세스가 어제 완료되었고 오늘 취소하면 어제의 성공 상태로 되돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-207">For example, if the Match process completed yesterday and you cancel it today, it will revert to yesterday's successful state.</span></span>


## <a name="august-2020-updates"></a><span data-ttu-id="b0412-208">2020년 8월 업데이트</span><span class="sxs-lookup"><span data-stu-id="b0412-208">August 2020 updates</span></span>

<span data-ttu-id="b0412-209">2020년 8월 업데이트에는 여러 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-209">The updates in August 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-august-2020"></a><span data-ttu-id="b0412-210">2020년 8월의 새로운 기능 및 업데이트된 기능</span><span class="sxs-lookup"><span data-stu-id="b0412-210">New and updated features in August 2020</span></span>

#### <a name="data-unification"></a><span data-ttu-id="b0412-211">데이터 통합</span><span class="sxs-lookup"><span data-stu-id="b0412-211">Data unification</span></span>

- <span data-ttu-id="b0412-212">**데이터 통합 중 지도 단계에 대한 경험 개선**</span><span class="sxs-lookup"><span data-stu-id="b0412-212">**Improved experience for the map stage during data unification**</span></span>

  <span data-ttu-id="b0412-213">데이터 통합 프로세스에서 지도 단계에 대한 경험을 통해 엔티티, 속성을 선택하고 보다 원활한 방식으로 의미를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-213">The experience to the map stage in the data unification process lets you select entities, attributes, and define semantics in a more seamless way.</span></span>

  <span data-ttu-id="b0412-214">변경 내용:</span><span class="sxs-lookup"><span data-stu-id="b0412-214">The changes include:</span></span>
  
  - <span data-ttu-id="b0412-215">엔터티 및 필드를 추가하는 데 필요한 상호 작용 감소</span><span class="sxs-lookup"><span data-stu-id="b0412-215">fewer interactions required to add entities and fields</span></span>
  - <span data-ttu-id="b0412-216">지도 페이지의 향상된 검색 기능</span><span class="sxs-lookup"><span data-stu-id="b0412-216">improved search capabilities on the map page</span></span>
  - <span data-ttu-id="b0412-217">제안된 필드 유형의 시각적이고 쉬운 식별</span><span class="sxs-lookup"><span data-stu-id="b0412-217">visual and easy identification of the suggested field type</span></span>

#### <a name="enrichment"></a><span data-ttu-id="b0412-218">보강</span><span class="sxs-lookup"><span data-stu-id="b0412-218">Enrichment</span></span>

- <span data-ttu-id="b0412-219">**추가 시장에서 사용 가능한 관심사 선호도 보강**</span><span class="sxs-lookup"><span data-stu-id="b0412-219">**Interest affinities enrichment available in additional markets**</span></span>

  <span data-ttu-id="b0412-220">관심사 선호도 보강을 미국을 넘어 캐나다, 호주, 영국, 프랑스 및 독일의 5개 추가 시장으로 확장하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-220">We're extending the availability of the interest affinities enrichment beyond the United States to five additional markets: Canada, Australia, United Kingdom, France, and Germany.</span></span> <span data-ttu-id="b0412-221">이를 통해 이러한 시장에 적용할 수있는 추가 관심사로 고객 데이터를 보강할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-221">With this extension, you can enrich your customer data with additional interests applicable to these markets.</span></span> <span data-ttu-id="b0412-222">또한 Microsoft Graph의 로컬 독점 데이터를 사용하여 이러한 시장에 있는 고객 프로필을 보강할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-222">We'll also enrich your customer profiles that are located in these markets by using local proprietary data from Microsoft Graph.</span></span>
  <span data-ttu-id="b0412-223">자세한 내용은 [브랜드 및 관심 선호도로 고객 프로필 보강](enrichment-microsoft-graph.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-223">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md)</span></span>


## <a name="july-2020-updates"></a><span data-ttu-id="b0412-224">2020년 7월 업데이트</span><span class="sxs-lookup"><span data-stu-id="b0412-224">July 2020 updates</span></span>

<span data-ttu-id="b0412-225">2020년 7월 업데이트에는 여러 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-225">The updates in July 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-july-2020"></a><span data-ttu-id="b0412-226">2020년 7월 새로운 기능 및 업데이트된 기능</span><span class="sxs-lookup"><span data-stu-id="b0412-226">New and updated features in July 2020</span></span>

#### <a name="extensibility"></a><span data-ttu-id="b0412-227">확장성</span><span class="sxs-lookup"><span data-stu-id="b0412-227">Extensibility</span></span>

- <span data-ttu-id="b0412-228">**통합 프로세스 완료를 위한 Power Automate 트리거**</span><span class="sxs-lookup"><span data-stu-id="b0412-228">**Power Automate trigger for completed unification process**</span></span>

  <span data-ttu-id="b0412-229">Power Automate에 대한 트리거를 확장하여 통합 프로세스(맵, 일치, 병합)의 새로 고침이 완료되면 알림 또는 작업을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-229">We have extended our triggers for Power Automate and let you create a notification or action when a refresh of the unification process (map, match, merge) is completed.</span></span>    
  <span data-ttu-id="b0412-230">자세한 내용은 [Power Automate 커넥터](export-power-automate.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b0412-230">For more information, see [Power Automate connector](export-power-automate.md)</span></span>

#### <a name="enrichment"></a><span data-ttu-id="b0412-231">보강</span><span class="sxs-lookup"><span data-stu-id="b0412-231">Enrichment</span></span>

- <span data-ttu-id="b0412-232">**추가 시장에서 사용할 수 있는 브랜드 선호도 강화**</span><span class="sxs-lookup"><span data-stu-id="b0412-232">**Brand affinities enrichment available in additional markets**</span></span>

  <span data-ttu-id="b0412-233">브랜드 선호도 강화의 가용성을 미국을 넘어 캐나다, 호주, 영국, 프랑스 및 독일의 5개 추가 시장으로 확장하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-233">We're extending the availability of the brand affinities enrichment beyond the United States to five additional markets: Canada, Australia, United Kingdom, France, and Germany.</span></span> <span data-ttu-id="b0412-234">이 확장을 통해 이러한 시장의 현지 브랜드로 고객 데이터를 풍부하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-234">With this extension, you can enrich your customer data with local brands in these markets.</span></span> <span data-ttu-id="b0412-235">또한 Microsoft Graph의 로컬 독점 데이터를 사용하여 이러한 시장에 있는 고객 프로필을 보강할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-235">We'll also enrich your customer profiles that are located in these markets by using local proprietary data from Microsoft Graph.</span></span>
  <span data-ttu-id="b0412-236">자세한 내용은 [브랜드 및 관심 선호도로 고객 프로필 보강](enrichment-microsoft-graph.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-236">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md)</span></span>

## <a name="june-2020-updates"></a><span data-ttu-id="b0412-237">2020년 6월 업데이트</span><span class="sxs-lookup"><span data-stu-id="b0412-237">June 2020 updates</span></span>

<span data-ttu-id="b0412-238">2020년 6월 업데이트에는 여러 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-238">The updates in June 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-june-2020"></a><span data-ttu-id="b0412-239">2020년 6월 새로운 기능 및 업데이트된 기능</span><span class="sxs-lookup"><span data-stu-id="b0412-239">New and updated features in June 2020</span></span>

#### <a name="enrichment"></a><span data-ttu-id="b0412-240">보강</span><span class="sxs-lookup"><span data-stu-id="b0412-240">Enrichment</span></span>

- <span data-ttu-id="b0412-241">**Leadspace의 회사 데이터로 보강**</span><span class="sxs-lookup"><span data-stu-id="b0412-241">**Enrichment with company data from Leadspace**</span></span>
  
  <span data-ttu-id="b0412-242">Leadspace에서 관련 회사 데이터를 조회하는 데 사용되는 통합 고객 프로필의 필드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-242">Define fields in unified customer profiles that are used to look up related company data from Leadspace.</span></span> <span data-ttu-id="b0412-243">강화 프로세스를 실행한 후 B2B 프로필은 회사 규모, 위치, 산업 등을 포함한 추가 특성으로 강화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-243">After running the enrichment process, B2B profiles are enriched with additional attributes including company size, location, industry, and more.</span></span>    
  <span data-ttu-id="b0412-244">이 공동 작업을 통해 타사 서비스의 입력으로 데이터 품질을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-244">This collaboration allows you to improve the quality of your data with input from third-party services.</span></span> <span data-ttu-id="b0412-245">이 보강을 사용하려면 B2B 회사 데이터에 액세스할 수 있는 Leadspace의 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-245">To use this enrichment, you'll need a license from Leadspace to access its B2B company data.</span></span> <span data-ttu-id="b0412-246">시스템은 해당 라이선스를 사용하여 데이터를 지속적으로 보강합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-246">The system will use that license to keep your data enriched continuously.</span></span>    
  <span data-ttu-id="b0412-247">자세한 내용은 [Leadspace로 회사 프로필 보강](enrichment-leadspace.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-247">For more information, see [Enrichment of company profiles with Leadspace](enrichment-leadspace.md).</span></span>

- <span data-ttu-id="b0412-248">**보강 허브 페이지**</span><span class="sxs-lookup"><span data-stu-id="b0412-248">**Enrichment hub page**</span></span>

  <span data-ttu-id="b0412-249">자사 및 타사 보강 공급자의 사용 가능한 모든 데이터 보강은 동일한 위치에서 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-249">All available data enrichment from first- and third-party enrichment providers gets configured in the same place.</span></span> <span data-ttu-id="b0412-250">데이터 보강 구성은 공통 위치에서 관리되는 원활한 경험입니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-250">Configuring data enrichment is a seamless experience that is managed from a common place.</span></span>    
  <span data-ttu-id="b0412-251">자세한 내용은 [고객 프로필 보강](enrichment-hub.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-251">For more information, see [Enrichment for customer profiles](enrichment-hub.md).</span></span>

- <span data-ttu-id="b0412-252">**별도의 브랜드 및 관심 선호도 강화**</span><span class="sxs-lookup"><span data-stu-id="b0412-252">**Separate brand and interest affinity enrichment**</span></span>

  <span data-ttu-id="b0412-253">이제 브랜드 및 관심 선호도 유사성을 두 개의 독립적인 보강으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-253">The brands and interests affinities are now available as two independent enrichments.</span></span> <span data-ttu-id="b0412-254">분리된 보강은 비즈니스 요구 사항이나 필요에 따라 개별적으로 구성하고 관리할 수 있는 유연성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-254">Separated enrichments give you the flexibility to configure and manage them individually, depending on your business requirements or needs.</span></span>    
  <span data-ttu-id="b0412-255">자세한 내용은 [브랜드 및 관심 선호도로 고객 프로필 강화](enrichment-microsoft-graph.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-255">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="b0412-256">확장성</span><span class="sxs-lookup"><span data-stu-id="b0412-256">Extensibility</span></span>

- <span data-ttu-id="b0412-257">**Dynamics 365 고객 카드 추가 기능의 통합 활동을 위한 클릭 가능한 URL**</span><span class="sxs-lookup"><span data-stu-id="b0412-257">**Clickable URLs for unified activities on the Dynamics 365 Customer Card Add-in**</span></span>

  <span data-ttu-id="b0412-258">고객 카드 추가 기능의 통합 활동은 활동 구성 중에 이러한 URL이 정의된 경우 클릭 가능한 URL을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-258">The unified activities in the Customer Card Add-in are now showing clickable URLs if such URLs have been defined during the configuration of activities.</span></span>    
  <span data-ttu-id="b0412-259">자세한 내용은 [고객 카드 추가 기능](customer-card-add-in.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-259">For more information, see [Customer Card Add-in](customer-card-add-in.md).</span></span>

- <span data-ttu-id="b0412-260">**Dynamics 365 고객 카드 추가 기능에서 사용할 수 있는 브랜드 및 관심 선호도**</span><span class="sxs-lookup"><span data-stu-id="b0412-260">**Brand and interest affinities available on the Dynamics 365 Customer Card Add-in**</span></span>

  <span data-ttu-id="b0412-261">Dynamics 365 고객 카드 추가 기능에 대한 새로운 컨트롤을 사용하면 Dynamics 365의 고객 참여 앱에서 연락처에 브랜드 및 관심 강화를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-261">A new control on the Dynamics 365 Customer Card Add-in lets you show brand and interest enrichments on your contacts in customer engagement apps in Dynamics 365.</span></span>    
  <span data-ttu-id="b0412-262">자세한 내용은 [고객 카드 추가 기능](customer-card-add-in.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-262">For more information, see [Customer Card Add-in](customer-card-add-in.md).</span></span>

- <span data-ttu-id="b0412-263">**추가 Power Automate 트리거**</span><span class="sxs-lookup"><span data-stu-id="b0412-263">**Additional Power Automate triggers**</span></span>

  <span data-ttu-id="b0412-264">Power Automate에 대한 트리거를 확장하고 다음 트리거를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-264">We have extended our triggers for Power Automate and added the following triggers:</span></span>
  - <span data-ttu-id="b0412-265">자동화된 전체 새로 고침(데이터 원본, 통합, 세그먼트, 측정, 내보내기)이 완료되면 알림을 받거나 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-265">Get a notification or perform an action when an automated full refresh (data sources, unification, segments, measures, exports) completes</span></span>
  - <span data-ttu-id="b0412-266">비즈니스 측정에 대한 임계값을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-266">Define a threshold for a business measure.</span></span> <span data-ttu-id="b0412-267">예를 들어, 정의된 임계값이 전달될 때 전송되는 알림을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-267">For example, you can create a notification that gets sent when the defined threshold is passed.</span></span> <span data-ttu-id="b0412-268">또한 트리거는 Power Automate에서 더 복잡한 워크플로를 구축할 수 있는 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-268">Additionally, the trigger brings information that allows you to build more complex workflows in Power Automate.</span></span>    
  <span data-ttu-id="b0412-269">자세한 내용은 [Power Automate 커넥터](export-power-automate.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b0412-269">For more information, see [Power Automate connector](export-power-automate.md)</span></span>

- <span data-ttu-id="b0412-270">**Facebook 광고 관리자로 내보내기**</span><span class="sxs-lookup"><span data-stu-id="b0412-270">**Export to Facebook Ads Manager**</span></span>
  
  <span data-ttu-id="b0412-271">이 기능을 사용하면 세그먼트를 Facebook 광고 관리자로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-271">This capability lets you export segments to Facebook Ads Manager.</span></span> <span data-ttu-id="b0412-272">세그먼트는 Facebook 마케팅 캠페인 및 광고의 통합 고객 프로필을 사용하기 위해 사용자 지정 대상으로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-272">Segments are exported as custom audiences to use unified customer profiles in Facebook marketing campaigns and ads.</span></span> <span data-ttu-id="b0412-273">사용자 지정 고객은 또한 Instagram에서 Facebook 광고 관리자를 통해 캠페인을 만드는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-273">The custom audiences are also usable to create campaigns on Instagram through Facebook Ads Manager.</span></span>    
  <span data-ttu-id="b0412-274">자세한 내용은 [Facebook 광고 관리자용 커넥터](export-facebook.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-274">For more information, see [Connector for Facebook Ads Manager](export-facebook.md).</span></span>

#### <a name="predictions"></a><span data-ttu-id="b0412-275">예측</span><span class="sxs-lookup"><span data-stu-id="b0412-275">Predictions</span></span>

- <span data-ttu-id="b0412-276">**구독 이탈 예측**</span><span class="sxs-lookup"><span data-stu-id="b0412-276">**Subscription churn prediction**</span></span>

  <span data-ttu-id="b0412-277">안내식 경험을 따라 클라우드 서비스, 고객 멤버십 및 기타 부문과 같은 구독 영역에서 이탈 예측을 생성하세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-277">Follow a guided experience to create churn prediction in subscription areas like cloud services, customer membership, and other sectors.</span></span> 

  <span data-ttu-id="b0412-278">구독 이탈 예측 기능을 사용하면 데이터 과학자의 개입 없이 고객이 구독 기반 제품 또는 서비스의 사용을 중지할 가능성을 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-278">The subscription churn prediction feature enables you to predict the likelihood of a customer stopping the use of subscription-based products or services without engaging a data scientist.</span></span> <span data-ttu-id="b0412-279">예측 점수를 사용하면 고객에 대한 다른 정보를 결합하여 이탈 위험이 높은 세그먼트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-279">Using the prediction score, you can combine other information about your customers to create segments of high churn risk.</span></span> <span data-ttu-id="b0412-280">이 세그먼트의 도움으로 마케팅, 고객 지원 및 기타 시나리오에서 고객을 직접 타겟팅하여 특정 고객의 이탈 위험을 줄여 수익을 개선하고 비용을 절감할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-280">With the help of this segment, you can directly target customers in marketing, customer support, and other scenarios to reduce the risk of churn for specific customers to improve revenue and reduce cost.</span></span>

  <span data-ttu-id="b0412-281">경험 내에서 이탈의 정의를 비즈니스에 특정한 시간 기반 기간으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-281">Within the experience, you can configure the definition of churn as a time-based window specific to your business.</span></span> <span data-ttu-id="b0412-282">예를 들어 월간 구독 프로세스가 있는 비디오 스트리밍 비즈니스에서는 구독 만료 후 15일 후에 고객이 이탈한 것으로 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-282">For example, a video streaming business that has a monthly subscription process might want to consider a customer to have churned after 15 days after the expiration of their subscription.</span></span>

  <span data-ttu-id="b0412-283">예측을 계속 진행하면 필요한 데이터를 안내하여 고객의 이탈을 예측하는 데 필요한 필드에 비즈니스 데이터를 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-283">As you continue through the prediction, we'll guide you through what data is needed, and enable you to map data about your business to fields required to predict churn for your customers.</span></span> <span data-ttu-id="b0412-284">비즈니스 정보가 변경되면 변화하는 비즈니스 환경에 적응하기 위해 시스템의 새 정보에 대해 재교육하는 일정을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-284">As business information changes, you can also set a schedule to retrain on new information in your system to adapt to changing business circumstances.</span></span>    
  <span data-ttu-id="b0412-285">자세한 내용은 [구독 이탈 예측(미리 보기)](predict-subscription-churn.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-285">For more information, see [Subscription churn prediction (preview)](predict-subscription-churn.md).</span></span>

#### <a name="segments"></a><span data-ttu-id="b0412-286">세그먼트</span><span class="sxs-lookup"><span data-stu-id="b0412-286">Segments</span></span>

- <span data-ttu-id="b0412-287">**유사 고객 찾기**</span><span class="sxs-lookup"><span data-stu-id="b0412-287">**Find similar customers**</span></span>
  
  <span data-ttu-id="b0412-288">인공 지능을 사용하여 고객 기반에서 유사한 고객을 찾으십시오.</span><span class="sxs-lookup"><span data-stu-id="b0412-288">Find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="b0412-289">이진 분류 기계 학습 모델은 확장된 세그먼트의 고객에게 유사성 점수를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-289">A binary classification machine learning model assigns a similarity score to customers in the expanded segment.</span></span> <span data-ttu-id="b0412-290">점수는 원본세그먼트의 고객과의 유사성을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-290">The score is based on the similarity to customers in the source segment.</span></span> <span data-ttu-id="b0412-291">유사성 점수에 따라 고객 프로필이 새로 생성된 세그먼트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-291">Depending on the similarity score, customer profiles are added to a newly created segment.</span></span>

  <span data-ttu-id="b0412-292">디지털 마케팅에서 유사 모델링이라고도 하는 AI 모델을 사용하여 추가 특성을 고려하여 다른 고객 세그먼트와 유사한 고객을 찾는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-292">Sometimes referred to as lookalike modeling in digital marketing, it uses an AI model to help find customers who are similar to another segment of your customers by factoring in additional attributes.</span></span> <span data-ttu-id="b0412-293">특성을 선택할 수 있을 뿐만 아니라 이 새 세그먼트에 있어야 하는 최대 고객 수를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-293">It not only allows you to pick the attributes but also allows you to specify the maximum number of customers who should be in this new segment.</span></span> <span data-ttu-id="b0412-294">그런 다음 AI 모델은 선택한 특성을 기반으로 각 고객의 유사성 점수를 계산하고 평균 유사성 점수가 더 높은 고객을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-294">The AI model will then compute similarity scores for each customer based on your selected attributes and find customers with the higher average similarity score.</span></span> <span data-ttu-id="b0412-295">결과 세그먼트에는 원래 세그먼트의 고객과 비슷해 보이는 고객이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-295">The resulting segment will include customers who look similar to the customer in your original segment.</span></span>    
  <span data-ttu-id="b0412-296">자세한 내용은 [유사한 고객](find-similar-customer-segments.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b0412-296">For more information, see [Similar Customers](find-similar-customer-segments.md).</span></span>

- <span data-ttu-id="b0412-297">**세그먼트 겹침 및 차별화 요소**</span><span class="sxs-lookup"><span data-stu-id="b0412-297">**Segment overlap and differentiators**</span></span>

  <span data-ttu-id="b0412-298">세그먼트 겹침을 통해 두 개 이상의 세그먼트에 공통적인 고객 수와 고객을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-298">Segment overlap lets you see how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="b0412-299">예를 들어, 지출이 많은 세그먼트가 만족도가 높은 고객 세그먼트와 어떻게 겹치는지 또는 이탈하는 고객 세그먼트가 만족도가 낮은 고객 세그먼트와 어떻게 겹치는지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-299">For example, how a high-spenders segment overlaps with a high-satisfaction customers segment or how a churning customer segment overlaps with a low-satisfaction customers segment.</span></span> <span data-ttu-id="b0412-300">또한 선택한 추가 특성을 기반으로 겹침이 어떻게 변경되는지 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-300">Additionally, you can analyze how the overlap changes based on an additional attribute of your choice.</span></span>

  <span data-ttu-id="b0412-301">세그먼트 차별화 요소는 한 세그먼트를 나머지 고객 또는 다른 세그먼트와 차별화하는 요소를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-301">Segment differentiators reveal what differentiates one segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="b0412-302">세그먼트를 식별하기만 하면 시스템이 가장 강력한 차별화 요소에서 가장 약한 항목까지 순위가 매겨진 차별화 요소 목록의 형태로 세그먼트를 구별하는 프로필 속성과 측정 값을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-302">All you need to do is identify a segment and the system will identify profile attributes and measures that distinguish the segment in the form of a ranked list of differentiators—from the strongest differentiator to the weakest.</span></span>    
  <span data-ttu-id="b0412-303">자세한 내용은 [세그먼트 인사이트(미리 보기)](segment-insights.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b0412-303">For more information, see [Segment insights (preview)](segment-insights.md).</span></span>

- <span data-ttu-id="b0412-304">**세그먼트 수명**</span><span class="sxs-lookup"><span data-stu-id="b0412-304">**Segment lifetime**</span></span>
  
  <span data-ttu-id="b0412-305">세그먼트를 활성화 또는 비활성화하는 일정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-305">Define a schedule to activate or deactivate a segment.</span></span>    
  <span data-ttu-id="b0412-306">자세한 내용은 [기존 세그먼트 관리](segments.md#manage-existing-segments)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b0412-306">For more information, see [Manage existing segments](segments.md#manage-existing-segments).</span></span>

## <a name="may-2020-updates"></a><span data-ttu-id="b0412-307">2020년 5월 업데이트</span><span class="sxs-lookup"><span data-stu-id="b0412-307">May 2020 updates</span></span>

<span data-ttu-id="b0412-308">2020년 5월 업데이트에는 몇 가지 기능, 성능 업그레이드 및 버그 수정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-308">The updates in May 2020 includes several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-may-2020"></a><span data-ttu-id="b0412-309">2020년 5월의 새로운 기능 및 업데이트된 기능</span><span class="sxs-lookup"><span data-stu-id="b0412-309">New and updated features in May 2020</span></span>

#### <a name="data-ingestion"></a><span data-ttu-id="b0412-310">데이터 수집</span><span class="sxs-lookup"><span data-stu-id="b0412-310">Data ingestion</span></span>

- <span data-ttu-id="b0412-311">**실시간 데이터 수집: 기록 보기**</span><span class="sxs-lookup"><span data-stu-id="b0412-311">**Real-time data ingestion: history views**</span></span>

  <span data-ttu-id="b0412-312">API를 사용하여 실시간 업데이트를 수집하면 이러한 업데이트에 대해 최대 30일의 집계 기록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-312">When using our API to ingest real-time updates, you can see up to 30 days of aggregated history for these updates.</span></span> <span data-ttu-id="b0412-313">결과, 원본 시스템 및 기타 유용한 메타데이터를 포함하여 성공 또는 실패한 모든 API 호출의 집계에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-313">You have access to aggregates of all successful or failed API calls including their outcome, source system, and other useful metadata.</span></span>    
  <span data-ttu-id="b0412-314">자세한 내용은 [실시간 데이터 수집](real-time-data-ingestion.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b0412-314">For more information, see [Real-time data ingestion](real-time-data-ingestion.md).</span></span>

- <span data-ttu-id="b0412-315">**실시간 데이터 수집: 프로필 업데이트**</span><span class="sxs-lookup"><span data-stu-id="b0412-315">**Real-time data ingestion: profile updates**</span></span>

  <span data-ttu-id="b0412-316">실시간 데이터 수집이 확장되어 몇 초 안에 특정 사용자 프로필 필드의 변경 사항을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-316">This extension of the real-time data ingestion lets you see, within seconds, changes to specific user profile fields.</span></span>    
  <span data-ttu-id="b0412-317">활동을 위한 실시간 기능 외에도 시스템은 프로파일 필드에 대한 짧은 지연 업데이트를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-317">In addition to the real-time functionality for activities, the system supports low latency updates to profile fields.</span></span> <span data-ttu-id="b0412-318">프로필 필드에 대한 실시간 업데이트는 만료 시간을 가지므로 예약된 새로 고침을 대체하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-318">Real-time updates for profile fields have an expiration time and are therefore not a replacement for scheduled refreshes.</span></span>    
  <span data-ttu-id="b0412-319">자세한 내용은 [실시간 데이터 수집](real-time-data-ingestion.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b0412-319">For more information, see [Real-time data ingestion](real-time-data-ingestion.md).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="b0412-320">확장성</span><span class="sxs-lookup"><span data-stu-id="b0412-320">Extensibility</span></span>

- <span data-ttu-id="b0412-321">**고객 카드 추가 기능에서 업데이트된 타임라인 및 페이지 매김**</span><span class="sxs-lookup"><span data-stu-id="b0412-321">**Updated timeline and pagination on the Customer Card Add-in**</span></span>

  <span data-ttu-id="b0412-322">고객 카드 추가 기능 솔루션의 시간 표시줄은 활동 시간 표시줄과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-322">The timeline of the Customer Card Add-in solution matches the activity timeline.</span></span> <span data-ttu-id="b0412-323">타임라인의 페이지 매김이 개선되어 한 번에 최대 50개의 활동이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-323">The pagination of the timeline improved, showing up to 50 activities at once.</span></span> <span data-ttu-id="b0412-324">또한 타임라인에 추가 활동을 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-324">It also allows loading additional activities in the timeline.</span></span>    
  <span data-ttu-id="b0412-325">자세한 내용은 [고객 카드 추가 기능](customer-card-add-in.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-325">For more information, see [Customer Card Add-in](customer-card-add-in.md).</span></span>

- <span data-ttu-id="b0412-326">**세그먼트 변경을 위한 Power Automate 트리거**</span><span class="sxs-lookup"><span data-stu-id="b0412-326">**Power Automate trigger for segment changes**</span></span>

  <span data-ttu-id="b0412-327">Power Automate에 대한 트리거는 흐름을 구축할 수 있는 대상을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-327">Triggers for Power Automate define what you can build a flow from.</span></span> <span data-ttu-id="b0412-328">새로 추가된 트리거를 사용하면 세그먼트에 대한 임계값을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-328">The newly added trigger lets you define a threshold for a segment.</span></span> <span data-ttu-id="b0412-329">예를 들어, 정의된 임계값이 전달될 때 전송되는 알림을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-329">For example, you can create a notification that gets sent when the defined threshold is passed.</span></span>    
  <span data-ttu-id="b0412-330">자세한 내용은 [Power Automate 커넥터](export-power-automate.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b0412-330">For more information, see [Power Automate connector](export-power-automate.md).</span></span>

- <span data-ttu-id="b0412-331">**사용자 지정 모델에 대한 다중 테넌트 지원**</span><span class="sxs-lookup"><span data-stu-id="b0412-331">**Multitenant support for custom models**</span></span>

  <span data-ttu-id="b0412-332">다른 Azure Machine Learning 테넌트의 웹 서비스를 사용하여 사용자 지정 모델에 대한 워크플로를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-332">Configure workflows for custom models with a web service of a different Azure Machine Learning tenant.</span></span> <span data-ttu-id="b0412-333">사용자 지정 모델에 대한 새 워크플로를 만들 때 Azure Machine Learning 테넌트에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-333">You can sign in to the Azure Machine Learning tenant when creating a new workflow for custom models.</span></span> <span data-ttu-id="b0412-334">이 기능은 사용자 지정 Azure Machine Learning 웹 서비스와 통합하는 기존 기능에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-334">This capability is an addition to the existing capability of integrating with your own custom Azure Machine Learning web service.</span></span>    
  <span data-ttu-id="b0412-335">자세한 내용은 [사용자 지정 기계 학습 모델](custom-models.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-335">For more information, see [Custom machine learning models](custom-models.md).</span></span>

#### <a name="segments"></a><span data-ttu-id="b0412-336">세그먼트</span><span class="sxs-lookup"><span data-stu-id="b0412-336">Segments</span></span>

- <span data-ttu-id="b0412-337">**엔터티 경로 자동화**</span><span class="sxs-lookup"><span data-stu-id="b0412-337">**Entity path automation**</span></span>

  <span data-ttu-id="b0412-338">세그먼트를 만들 때 사용자는 엔터티 경로를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-338">When creating a segment, users need to define the entity path.</span></span> <span data-ttu-id="b0412-339">이 기능은 엔터티 경로 정의를 자동화하기 위한 첫 번째 단계를 수행하므로 원하는 세분화 기준에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-339">This capability takes a first step at automating the entity path definition so you can focus on the segmentation criteria that you have in mind.</span></span>    
  <span data-ttu-id="b0412-340">고객을 분류하려는 엔터티가 통합 고객 엔터티와 직접 관련된 경우 더 이상 엔터티 경로를 정의할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-340">If the entity by which you want to segment your customers is directly related to the unified customer entity, you won't need to define the entity path anymore.</span></span> <span data-ttu-id="b0412-341">그러나 가능한 엔터티 경로가 둘 이상인 경우 여전히 수동으로 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-341">However, if there is more than one possible entity path, you still need to define it manually.</span></span>

- <span data-ttu-id="b0412-342">**여러 세그먼트에 대한 작업**</span><span class="sxs-lookup"><span data-stu-id="b0412-342">**Actions on multiple segments**</span></span>
  
  <span data-ttu-id="b0412-343">사용자는 한 번의 클릭으로 여러 세그먼트를 선택하고 세그먼트 새로 고침과 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-343">Users can select multiple segments and take actions on them, like refreshing the segments, with a single click.</span></span>    

- <span data-ttu-id="b0412-344">**세그먼트 새로 고침**</span><span class="sxs-lookup"><span data-stu-id="b0412-344">**Refresh segments**</span></span>

  <span data-ttu-id="b0412-345">사용자는 단일 세그먼트를 새로 고치거나 새로 고칠 세그먼트만 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-345">Users can refresh a single segment or select only the segments they want to refresh.</span></span>    

  
- <span data-ttu-id="b0412-346">**복합 세그먼트 개선**</span><span class="sxs-lookup"><span data-stu-id="b0412-346">**Improvements to compounded segments**</span></span>

  <span data-ttu-id="b0412-347">사용자는 다른 세그먼트를 기반으로 세그먼트를 작성, 편집 및 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-347">Users can create, edit, and delete segments that are based on other segments.</span></span> <span data-ttu-id="b0412-348">예를 들어, 세 번째 세그먼트에 구성된 다른 세그먼트에 구성된 세그먼트입니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-348">For example, a segment constructed on another segment that was constructed on a third segment.</span></span>    

- <span data-ttu-id="b0412-349">**세그먼트 목록 페이지**</span><span class="sxs-lookup"><span data-stu-id="b0412-349">**Segment list page**</span></span>

  <span data-ttu-id="b0412-350">새로운 세그먼트 페이지 디자인에서는 목록 형식을 사용하여 한 번에 더 많은 세그먼트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-350">The new design of the segments page uses a list format that lets you see more segments at once.</span></span> <span data-ttu-id="b0412-351">세그먼트를 빨리 찾기 위해 검색 필드가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-351">A search field is added to find segments quickly.</span></span> <span data-ttu-id="b0412-352">사용자는 이제 여러 세그먼트를 한 번에 다운로드 또는 삭제하는 등의 작업을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-352">Users can now apply actions like downloading or deleting on multiple segments at once.</span></span> <span data-ttu-id="b0412-353">새로운 추세 경험이 도입되어 세그먼트의 중요한 변화를 신속하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-353">A new trend experience is introduced to quickly identify significant changes on segments.</span></span>    
  <span data-ttu-id="b0412-354">자세한 내용은 [세그먼트 만들기 및 관리](segments.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-354">For more information, see [Create and manage segments](segments.md).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="b0412-355">시스템 관리</span><span class="sxs-lookup"><span data-stu-id="b0412-355">System administration</span></span>

- <span data-ttu-id="b0412-356">**Microsoft Dynamics 365 Online Government에서 사용할 수 있는 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="b0412-356">**Customer Insights available in Microsoft Dynamics 365 Online Government**</span></span>

  <span data-ttu-id="b0412-357">상호 작용을 위한 채널이 점점 더 많아짐에 따라 시민 데이터가 무수한 시스템에 분산되어 데이터가 분리되고 시민 상호 작용에 대한 단편화된 정보가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-357">With more and more channels for interactions, citizen data is scattered across myriad systems, leading to siloed data, and a fragmented view of information about citizen interactions.</span></span> <span data-ttu-id="b0412-358">채널을 통한 각 시민의 상호 작용을 완전히 파악하지 않으면 정부가 대규모로 현대화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-358">Without a complete view of each citizen's interactions across channels, it's impossible for governments to modernize at scale.</span></span> <span data-ttu-id="b0412-359">Microsoft는 일관되고 반응적인 경험에 대한 시민의 기대에 부응하기 위해 정부의 기술 요구를 지원하기 위해 노력하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-359">Microsoft is committed to supporting the technology needs of government to keep up with citizen expectations for consistent and responsive experiences.</span></span>    
  <span data-ttu-id="b0412-360">2020 릴리스 웨이브 1로 Dynamics 365 Customer Insights는 미국 정부 기관의 높은 규정 준수 요구를 충족하도록 구축된 환경인 GCC(정부 커뮤니티 클라우드)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-360">With 2020 release wave 1, Dynamics 365 Customer Insights will be available for the Government Community Cloud (GCC), an environment built to meet the higher compliance needs of United States government agencies.</span></span> <span data-ttu-id="b0412-361">기관은 시민에 대한 통일된 관점을 확보하고 사전 구축된 AI를 사용하여 상호 작용을 개선하고 직원에게 권한을 부여하며 커뮤니티를 변화시키는 통찰력을 도출하는 동시에 IT 복잡성을 줄이고 미국 규정 준수 및 보안 표준을 충족시킵니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-361">Agencies gain a unified view of citizens and use prebuilt AI to derive insights that improve interactions, empower employees, and transform communities, while reducing IT complexity and meeting United States compliance and security standards.</span></span> <span data-ttu-id="b0412-362">Dynamics 365 Government는 미국 연방 기관이 FedRAMP(Federal Risk and Authorization Management Program)의 까다로운 요구 사항을 충족하므로 미국 연방 기관이 Microsoft Cloud의 비용 절감 및 엄격한 보안 혜택을 누릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-362">Dynamics 365 Government meets the demanding requirements of the US Federal Risk and Authorization Management Program (FedRAMP), enabling United States federal agencies to benefit from the cost savings and rigorous security of the Microsoft Cloud.</span></span>

## <a name="april-2020-updates"></a><span data-ttu-id="b0412-363">2020년 4월 업데이트</span><span class="sxs-lookup"><span data-stu-id="b0412-363">April 2020 updates</span></span>

<span data-ttu-id="b0412-364">2020년 4월 업데이트에는 몇 가지 기능, 성능 업그레이드 및 버그 수정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-364">The updates in April 2020 includes several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-april-2020"></a><span data-ttu-id="b0412-365">2020년 4월의 새로운 기능 및 업데이트된 기능</span><span class="sxs-lookup"><span data-stu-id="b0412-365">New and updated features in April 2020</span></span>

#### <a name="activities"></a><span data-ttu-id="b0412-366">활동 </span><span class="sxs-lookup"><span data-stu-id="b0412-366">Activities</span></span>

- <span data-ttu-id="b0412-367">**활동 엔터티를 표준 활동 유형에 매핑**</span><span class="sxs-lookup"><span data-stu-id="b0412-367">**Map activity entity to standard activity type**</span></span>
  
  <span data-ttu-id="b0412-368">현재 활동 구성 및 스토리지는 타임라인에서 볼 수 있도록 정적 디자인을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-368">Activity configuration and storage are currently based on a static design to view them in a timeline.</span></span> <span data-ttu-id="b0412-369">AI 모델에서 여러 사용 사례를 사용할 수 있는 활동의 의미론적 의미는 현재 완전히 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-369">The semantic meaning of activities, which has potential for multiple use-cases in AI models, isn't fully used at the moment.</span></span> <span data-ttu-id="b0412-370">우리는 활동 유형과 활동에 대한 의미론적 이해를 바탕으로 활동 타임라인을 보다 역동적으로 만들 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-370">We plan to make the activity timeline more dynamic, based on the activity type and better semantic understanding of the activities.</span></span> <span data-ttu-id="b0412-371">이 기능은 수집된 활동에 대해 Common Data Model에 정의된 활동 유형을 식별하는 데 목적이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-371">This feature aims to identify the activity type as defined in Common Data Model for any ingested activity.</span></span>
  <span data-ttu-id="b0412-372">자세한 내용은 [고객 활동](activities.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-372">For more information, see [Customer activities](activities.md).</span></span>

#### <a name="data-ingestion"></a><span data-ttu-id="b0412-373">데이터 수집</span><span class="sxs-lookup"><span data-stu-id="b0412-373">Data ingestion</span></span>

- <span data-ttu-id="b0412-374">**실시간 데이터 수집: 활동**</span><span class="sxs-lookup"><span data-stu-id="b0412-374">**Real-time data ingestion: activities**</span></span>
  
  <span data-ttu-id="b0412-375">실시간 데이터 수집 기능은 이후에 예약된 새로 고침이 데이터 원본에서이 데이터를 가져올 때까지 즉시 사용할 데이터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-375">Real-time data ingestion provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>    
  <span data-ttu-id="b0412-376">자세한 내용은 [실시간 데이터 수집](real-time-data-ingestion.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b0412-376">For more information, see [Real-time data ingestion](real-time-data-ingestion.md).</span></span>

- <span data-ttu-id="b0412-377">**데이터 준비 개선**</span><span class="sxs-lookup"><span data-stu-id="b0412-377">**Improvements to data preparation**</span></span>
  
  <span data-ttu-id="b0412-378">엔터티에서 수집된 데이터에 대해 자세히 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="b0412-378">Learn more about the data ingested in an entity.</span></span> <span data-ttu-id="b0412-379">데이터 요약을 통해 적절한 조치를 취하는 데 도움이 되는 데이터 품질 특성을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-379">With the data summary, you can understand the data quality characteristics that can help to take appropriate action.</span></span>    
  <span data-ttu-id="b0412-380">자세한 내용은 [엔터티 데이터 살펴보기](entities.md#exploring-a-specific-entitys-data)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b0412-380">For more information, see [Explore entity data](entities.md#exploring-a-specific-entitys-data).</span></span>

- <span data-ttu-id="b0412-381">**Common Data Service로 Dynamics 365에서 분석 데이터 수집**</span><span class="sxs-lookup"><span data-stu-id="b0412-381">**Ingest analytical data from Dynamics 365 with Common Data Service**</span></span>
  
  <span data-ttu-id="b0412-382">Common Data Service는 데이터 원본을 만드는 방법으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-382">Common Data Service is available as a way to create data sources.</span></span> <span data-ttu-id="b0412-383">기존 Dynamics 365 고객은 Common Data Service에서 Customer Insights로 분석 엔터티를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-383">Existing Dynamics 365 customers can ingest analytical entities from Common Data Service to Customer Insights.</span></span> <span data-ttu-id="b0412-384">단일 데이터 원본은 동시에 동일한 Common Data Service 관리형 레이크를 Customer Insights 환경에서 동시에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-384">A single data source can simultaneously use the same Common Data Service-managed lake in a Customer Insights environment.</span></span>    
  <span data-ttu-id="b0412-385">자세한 내용은 [Common Data Service 관리형 데이터 레이크에서 데이터에 연결](connect-common-data-service-lake.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-385">For more information, see [Connect to data in a Common Data Service managed data lake](connect-common-data-service-lake.md).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="b0412-386">확장성</span><span class="sxs-lookup"><span data-stu-id="b0412-386">Extensibility</span></span>

- <span data-ttu-id="b0412-387">**LiveRamp로 내보내기**</span><span class="sxs-lookup"><span data-stu-id="b0412-387">**Export to LiveRamp**</span></span>

  <span data-ttu-id="b0412-388">LiveRamp®에서 데이터를 활성화하여 디지털, 소셜 및 TV 에코시스템에서 500개 이상의 플랫폼에 연결하십시오.</span><span class="sxs-lookup"><span data-stu-id="b0412-388">Activate your data in LiveRamp® to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="b0412-389">광고 캠페인을 타겟팅, 억제 및 개인화하기 위해 LiveRamp의 데이터를 활용하십시오.</span><span class="sxs-lookup"><span data-stu-id="b0412-389">Leverage your data in LiveRamp for targeting, suppressing, and personalizing ad campaigns.</span></span>    
  <span data-ttu-id="b0412-390">자세한 내용은 [LiveRamp&reg; 커넥터](export-liveramp.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b0412-390">For more information, see [LiveRamp&reg; connector](export-liveramp.md).</span></span>

- <span data-ttu-id="b0412-391">**Customer Insights Teams 추가 기능**</span><span class="sxs-lookup"><span data-stu-id="b0412-391">**Customer Insights Teams Add-in**</span></span>
  
  <span data-ttu-id="b0412-392">봇은 통합 고객 프로필을 위한 조회 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-392">The bot provides lookup capabilities for unified customer profiles.</span></span> <span data-ttu-id="b0412-393">결과 고객 프로필에서 최대 15개의 필드가 있는 카드가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-393">It will show a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="b0412-394">여러 개의 일치 항목은 프로필을 선택할 수 있는 결과 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-394">Multiple matches return a list of results where you can select a profile.</span></span>    
  <span data-ttu-id="b0412-395">자세한 내용은 [Customer Insights용 Teams 봇](export-teams-bot.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-395">For more information, see [Teams bot for Customer Insights](export-teams-bot.md).</span></span>

#### <a name="measures"></a><span data-ttu-id="b0412-396">측정값</span><span class="sxs-lookup"><span data-stu-id="b0412-396">Measures</span></span>

- <span data-ttu-id="b0412-397">**측정값 목록 페이지**</span><span class="sxs-lookup"><span data-stu-id="b0412-397">**Measure list page**</span></span>
  
  <span data-ttu-id="b0412-398">측정값 페이지의 개선 사항에는 단일 측정값 및 한 번에 여러 측정값에 대한 작업 지원이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-398">Improvements to the measures page include support for actions on a single measure and on multiple measures at once.</span></span> <span data-ttu-id="b0412-399">또한 측정값을 빠르게 찾고 추적할 수 있는 검색 필드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-399">Additionally, you'll find a search field to find and track measures quickly.</span></span>    
  <span data-ttu-id="b0412-400">자세한 내용은 [세그먼트 만들기 및 관리](segments.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-400">For more information, see [Create and manage segments](segments.md).</span></span>

- <span data-ttu-id="b0412-401">**복합 측정값 개선**</span><span class="sxs-lookup"><span data-stu-id="b0412-401">**Improvements to compounded measures**</span></span>
  
  <span data-ttu-id="b0412-402">사용자는 다른 측정값을 기반으로 측정값을 작성, 편집 및 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-402">Users can create, edit, and delete measures that are based on other measures.</span></span> <span data-ttu-id="b0412-403">예를 들어, 세 번째 측정값에 구성된 다른 측정값에 구성된 측정값입니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-403">For example, a measure constructed on another measure that was constructed on a third measure.</span></span>

#### <a name="segments"></a><span data-ttu-id="b0412-404">세그먼트</span><span class="sxs-lookup"><span data-stu-id="b0412-404">Segments</span></span>

- <span data-ttu-id="b0412-405">**추가 연산자**</span><span class="sxs-lookup"><span data-stu-id="b0412-405">**Additional operator**</span></span>
  
  <span data-ttu-id="b0412-406">인세트 연산자를 사용하면 몇 가지 가능한 문자열 값으로 고객을 세분화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-406">The In-set operator allows segmentation for customers by several possible string values.</span></span> <span data-ttu-id="b0412-407">이 연산자를 추가하기 전에 여러 OR 조건을 가진 세그먼트를 구성해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-407">Before this operator was added, you had to construct such segments with multiple OR conditions.</span></span> <span data-ttu-id="b0412-408">인세트 연산자를 사용하면 단일 조건으로 이를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-408">The In-set operator lets you do that with a single condition.</span></span>    
  <span data-ttu-id="b0412-409">자세한 내용은 [세그먼트 만들기 및 관리](segments.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0412-409">For more information, see [Create and manage segments](segments.md).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="b0412-410">시스템 관리</span><span class="sxs-lookup"><span data-stu-id="b0412-410">System administration</span></span>

- <span data-ttu-id="b0412-411">**구성 설정을 새 환경으로 복사**</span><span class="sxs-lookup"><span data-stu-id="b0412-411">**Copy configuration settings to a new environment**</span></span>
  
  <span data-ttu-id="b0412-412">한 환경에서 다른 환경으로 구성을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-412">Copy your configuration from one environment to another.</span></span> <span data-ttu-id="b0412-413">새 환경을 만드는 동안 구성을 복사할 기존 환경을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-413">While creating a new environment, you can select an existing environment you want to copy the configuration from.</span></span> <span data-ttu-id="b0412-414">현재 데이터 원본, 데이터 통합, 관계, 측정 및 복사할 세그먼트를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-414">We currently support data sources, data unification, relationships, measures, and segments to be copied.</span></span> <span data-ttu-id="b0412-415">데이터 원본 자격 증명 및 실제 데이터는 복사되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0412-415">Data source credentials and actual data aren't copied.</span></span>    
  <span data-ttu-id="b0412-416">자세한 내용은 [환경 관리](manage-environments.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b0412-416">For more information, see [Manage environments](manage-environments.md).</span></span>
