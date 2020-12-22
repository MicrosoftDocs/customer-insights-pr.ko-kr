---
title: Microsoft Graph로 고객 프로필 보강
description: Microsoft Graph의 독점 데이터를 사용하여 의 브랜드 및 관심 관계로 고객 데이터를 보강합니다.
ms.date: 09/28/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4f93a2337815f76b98185ecb3755e08443031748
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406275"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="6fb89-103">브랜드 및 관심 관계로 풍부한 고객 프로필 강화(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="6fb89-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="6fb89-104">Microsoft Graph의 독점 데이터를 사용하여 의 브랜드 및 관심 관계로 고객 데이터를 보강합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-104">Use proprietary data from the Microsoft Graph to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="6fb89-105">이러한 선호도는 인구 통계가 비슷한 사람들과 고객의 데이터를 기반으로 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="6fb89-106">이 정보는 고객을 특정 브랜드 및 관심사에 대한 선호도에 따라 더 잘 이해하고 분류할 수 있도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="6fb89-107">대상 그룹 인사이트에서 **데이터** > **보강** 으로 이동하여 [보강을 구성하고 봅니다](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="6fb89-107">In ausience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="6fb89-108">브랜드 관심 보강을 구성하려면 **검색** 탭으로 이동하고 **브랜드** 타일에서 **내 데이터 보강** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="6fb89-109">관심 관계 보강을 구성하려면 **검색** 탭으로 이동하고 **관심** 타일에서 **내 데이터 보강** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6fb89-110">![브랜드 및 관심사 타일](media/BrandsInterest-tile-Hub.png "브랜드 및 관심사 타일")</span><span class="sxs-lookup"><span data-stu-id="6fb89-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="about-microsoft-graph"></a><span data-ttu-id="6fb89-111">Microsoft Graph 정보</span><span class="sxs-lookup"><span data-stu-id="6fb89-111">About Microsoft Graph</span></span>

<span data-ttu-id="6fb89-112">Microsoft Graph의 온라인 검색 데이터를 사용하여 다양한 인구 통계 세그먼트(연령, 성별 또는 위치로 정의)에서 브랜드 및 관심 분야에 대한 친화성을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-112">We use online search data from the Microsoft Graph to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="6fb89-113">브랜드나 관심 분야에 대한 온라인 검색 양에 따라 인구 통계학적 세그먼트가 다른 세그먼트와 비교하여 해당 브랜드나 관심 분야에 얼마나 많은 유사성이 있는지가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

<span data-ttu-id="6fb89-114">[Microsoft Graph에 대해 자세히 알아보십시오](https://docs.microsoft.com/graph/overview).</span><span class="sxs-lookup"><span data-stu-id="6fb89-114">[Learn more about Microsoft Graph](https://docs.microsoft.com/graph/overview).</span></span>

## <a name="affinity-score-and-confidence"></a><span data-ttu-id="6fb89-115">선호도 점수 및 신뢰도</span><span class="sxs-lookup"><span data-stu-id="6fb89-115">Affinity score and confidence</span></span>

<span data-ttu-id="6fb89-116">**선호도 점수** 는 100점 척도로 계산되며 100은 브랜드 또는 관심 분야에 대한 선호도가 가장 높은 세그먼트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-116">The **affinity score** is calculated on a 100-point scale, with 100 representing the segment that has the highest affinity for a brand or interest.</span></span>

<span data-ttu-id="6fb89-117">**친화력 신뢰도** 가 100점 척도로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-117">The **affinity confidence** is also calculated on a 100-point scale.</span></span> <span data-ttu-id="6fb89-118">세그먼트가 브랜드 또는 관심 분야에 대해 선호도가 있다는 시스템의 신뢰도 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-118">It indicates the system's confidence level that a segment has an affinity for the brand or interest.</span></span> <span data-ttu-id="6fb89-119">신뢰도 수준은 세그먼트 크기와 세그먼트 세부 수준을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-119">Confidence level is based on the segment size and the segment granularity.</span></span> <span data-ttu-id="6fb89-120">세그먼트 크기는 특정 세그먼트에 대한 데이터 양에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-120">Segment size is determined by the amount of data we have for a given segment.</span></span> <span data-ttu-id="6fb89-121">세그먼트 세분성은 프로필에서 사용 가능한 속성(연령, 성별, 위치) 수에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-121">Segment granularity is determined by how many attributes (age, gender, location) are available in a profile.</span></span>

<span data-ttu-id="6fb89-122">데이터 집합의 점수는 정규화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-122">We don't normalize the scores for your dataset.</span></span> <span data-ttu-id="6fb89-123">결과적으로, 데이터 집합에 대해 가능한 모든 선호도 점수 값이 표시되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-123">Consequently, you may not see all possible affinity score values for your dataset.</span></span> <span data-ttu-id="6fb89-124">예를 들어, 데이터에 선호도 점수가 100인 보강된 고객 프로필이 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-124">For example, there may be no enriched customer profile with affinity score 100 in your data.</span></span> <span data-ttu-id="6fb89-125">특정 브랜드나 관심 분야에 대해 100점을 얻은 인구 통계학적 세그먼트에 고객이 없는 경우가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-125">That's possible if no customers exist in the demographic segment that scored 100 for a given brand or interest.</span></span>

> [!TIP]
> <span data-ttu-id="6fb89-126">선호도 점수를 사용하여 [세그먼트를 만들](segments.md) 때 적절한 점수 임계값을 결정하기 전에 데이터 집합의 선호도 점수 분포를 검토하십시오.</span><span class="sxs-lookup"><span data-stu-id="6fb89-126">When [creating segments](segments.md) using affinity scores, review the distribution of affinity scores for your dataset before deciding on the appropriate score thresholds.</span></span> <span data-ttu-id="6fb89-127">예를 들어, 특정 브랜드 또는 관심 분야에 대해 최고 선호도 점수가 25인 데이터 집합에서 선호도 점수 10은 유의한 것으로 간주될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-127">For example, an affinity score of 10 can be considered significant in a dataset that has a highest affinity score of only 25 for a given brand or interest.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="6fb89-128">지원되는 국가/지역</span><span class="sxs-lookup"><span data-stu-id="6fb89-128">Supported countries/regions</span></span>

<span data-ttu-id="6fb89-129">현재 지원되는 국가/지역 옵션은 오스트레일리아, 캐나다(영어), 프랑스, 독일, 영국 또는 미국(영어)입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-129">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="6fb89-130">국가를 선택하려면 **브랜드 보강** 또는 **관심사 보강** 을 열고 **국가/지역** 옆에 있는 **변경** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-130">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="6fb89-131">**국가/지역 설정** 창에서 옵션을 선택하고 **적용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-131">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="6fb89-132">국가 선택과 관련된 시사점</span><span class="sxs-lookup"><span data-stu-id="6fb89-132">Implications related to country selection</span></span>

- <span data-ttu-id="6fb89-133">[자신의 브랜드를 선택](#define-your-brands-or-interests)하면, 선택한 국가/지역을 기준으로 제안을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-133">When [choosing your own brands](#define-your-brands-or-interests), we will provide suggestions based on the selected country/region.</span></span>

- <span data-ttu-id="6fb89-134">[산업군 선택](#define-your-brands-or-interests)을 하시면, 선택한 국가/지역을 기준으로 가장 관련성이 높은 브랜드 또는 관심사를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-134">When [choosing an industry](#define-your-brands-or-interests), we will identify the most relevant brands or interests based on the selected country/region.</span></span>

- <span data-ttu-id="6fb89-135">[필드를 매핑](#map-your-fields)하면, 국가/지역 필드가 매핑되지 않은 경우 선택한 국가/지역의 Microsoft Graph 데이터를 사용하여 고객 프로필을 보강합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-135">When [mapping your fields](#map-your-fields), if the Country/Region field isn't mapped, we'll use Microsoft Graph data from the selected country/region to enrich your customer profiles.</span></span> <span data-ttu-id="6fb89-136">또한 해당 선택 사항을 사용하여 국가/지역 데이터가 없는 고객 프로필을 보강할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-136">We'll also use that selection to enrich your customer profiles that don't have country/region data available.</span></span>

- <span data-ttu-id="6fb89-137">[프로필을 보강](#refresh-enrichment)하면, 선택한 국가/지역에 없는 프로필을 포함하여 선택한 브랜드 및 관심 분야에 대해 Microsoft Graph 데이터를 사용할 수 있는 모든 고객 프로필을 강화합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we have Microsoft Graph data available for the selected brands and interests, including profiles that are not in the selected country/region.</span></span> <span data-ttu-id="6fb89-138">예를 들어 독일을 선택한 경우 미국에서 선택한 브랜드 및 관심사에 대해 Microsoft Graph 데이터를 사용할 수 있는 경우 미국에 있는 프로필이 보강됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-138">For example, if you selected Germany, we'll enrich profiles located in the United States if we have Microsoft Graph data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="6fb89-139">보강 구성</span><span class="sxs-lookup"><span data-stu-id="6fb89-139">Configure Enrichment</span></span>

<span data-ttu-id="6fb89-140">브랜드 또는 관심사 보강 구성은 다음 두 단계로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-140">Configuring brands or interests enrichment consists of two steps:</span></span>

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="6fb89-141">브랜드 또는 관심 정의</span><span class="sxs-lookup"><span data-stu-id="6fb89-141">Define your brands or interests</span></span>

<span data-ttu-id="6fb89-142">다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-142">Select one of the following options:</span></span>

- <span data-ttu-id="6fb89-143">**산업**: 이 시스템은 산업과 관련된 최고 브랜드 또는 관심사를 식별하고 고객 데이터를 보강합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-143">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="6fb89-144">**원하는 항목 선택**: 조직과 가장 관련이 있는 브랜드 또는 관심사 목록에서 최대 5개의 항목을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-144">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="6fb89-145">브랜드나 관심사를 추가하려면 입력 영역에 해당 브랜드나 관심사를 입력하여 일치하는 용어를 기반으로 제안을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-145">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="6fb89-146">찾고 있는 브랜드나 관심 분야가 목록에 없는 경우 **제안** 링크를 사용하여 의견을 보내주십시오.</span><span class="sxs-lookup"><span data-stu-id="6fb89-146">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="6fb89-147">필드 매핑</span><span class="sxs-lookup"><span data-stu-id="6fb89-147">Map your fields</span></span>

<span data-ttu-id="6fb89-148">통합 고객 엔터티의 필드를 둘 이상의 속성에 매핑하여 고객 데이터를 보강하는 데 사용할 인구 통계 세그먼트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-148">Map fields from your unified customer entity to at least two attributes to define the demographic segment you want us to use for enriching your customer data.</span></span> <span data-ttu-id="6fb89-149">**편집** 을 선택하고 필드의 매핑을 정의하고 완료하면 **적용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-149">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="6fb89-150">**저장** 필드를 선택하여 매핑을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-150">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="6fb89-151">다음 형식 및 값이 지원되며 값은 대소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-151">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="6fb89-152">**생년월일**: 데이터 수집 시 생년월일을 날짜/시간 형식으로 변환하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-152">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="6fb89-153">또는 [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html)의 "yyyy-MM-dd" 또는 "yyyy-MM-ddTHH:mm:ssZ" 형식의 문자열이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-153">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="6fb89-154">**성별**: 남성, 여성, 알 수 없음</span><span class="sxs-lookup"><span data-stu-id="6fb89-154">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="6fb89-155">**우편 번호**: 미국의 경우 5자리 우편 번호, 기타 모든 국가의 표준 우편 번호</span><span class="sxs-lookup"><span data-stu-id="6fb89-155">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="6fb89-156">**도시**: 영어로 된 도시 이름</span><span class="sxs-lookup"><span data-stu-id="6fb89-156">**City**: City name in English</span></span>
- <span data-ttu-id="6fb89-157">**시/도**: 미국 및 캐나다의 경우 두 글자 약어입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-157">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="6fb89-158">호주의 경우 2~3자의 약어입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-158">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="6fb89-159">프랑스, 독일 또는 영국에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-159">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="6fb89-160">**국가/지역**:</span><span class="sxs-lookup"><span data-stu-id="6fb89-160">**Country/Region**:</span></span>

  - <span data-ttu-id="6fb89-161">US: 미합중국, 미국, USA, US</span><span class="sxs-lookup"><span data-stu-id="6fb89-161">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="6fb89-162">CA: 캐나다, CA</span><span class="sxs-lookup"><span data-stu-id="6fb89-162">CA: Canada, CA</span></span>
  - <span data-ttu-id="6fb89-163">GB: 영국, UK, 그레이트브리튼, GB, 그레이트브리튼 및 북아일랜드연합왕국, 대브리튼왕국</span><span class="sxs-lookup"><span data-stu-id="6fb89-163">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="6fb89-164">AU: 호주, 오스트레일리아, AU, 오스트레일리아연방</span><span class="sxs-lookup"><span data-stu-id="6fb89-164">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="6fb89-165">FR: 프랑스, FR, 프랑스 공화국</span><span class="sxs-lookup"><span data-stu-id="6fb89-165">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="6fb89-166">DE: 독일, 독일어, Deutschland, Allemagne, DE, 독일 연방 공화국, 독일 공화국</span><span class="sxs-lookup"><span data-stu-id="6fb89-166">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="refresh-enrichment"></a><span data-ttu-id="6fb89-167">보강 새로 고침</span><span class="sxs-lookup"><span data-stu-id="6fb89-167">Refresh enrichment</span></span>

<span data-ttu-id="6fb89-168">인구 통계에 대한 브랜드, 관심 분야 및 필드 매핑을 구성한 후 보강을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-168">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="6fb89-169">프로세스를 시작하려면 브랜드 또는 관심사 구성 페이지에서 **실행** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-169">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="6fb89-170">또한 예약된 새로 고침의 일부로 시스템에서 자동으로 보강 기능을 실행하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-170">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="6fb89-171">고객 데이터의 크기에 따라 보강 실행이 완료되는 데 몇 분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-171">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="6fb89-172">작업/프로세스 [상태에는 6가지 유형](system.md#status-types)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-172">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="6fb89-173">또한 대부분의 프로세스는 [다른 다운스트림 프로세스에 의존](system.md#refresh-policies)합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-173">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="6fb89-174">프로세스 상태를 선택하여 전체 작업의 진행률에 대한 세부 사항을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-174">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="6fb89-175">작업 중 하나를 선택한 다음 **자세히 보기** 참조를 선택하면, 처리 시간, 마지막 처리 날짜, 작업과 관련된 모든 오류 및 경고와 같은 추가 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-175">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="6fb89-176">보강 결과</span><span class="sxs-lookup"><span data-stu-id="6fb89-176">Enrichment results</span></span>

<span data-ttu-id="6fb89-177">보강 프로세스를 실행한 후 **내 보강** 으로 이동하여 총 보강 고객 수와 보강된 고객 프로필에 대한 브랜드 또는 관심사를 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-177">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="보강 프로세스를 실행한 후 결과 미리 보기":::

<span data-ttu-id="6fb89-179">차트에서 **보강된 데이터 보기** 를 선택하여 풍부한 데이터를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-179">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="6fb89-180">브랜드에 대한 보강 데이터는 **BrandAffinityFromMicrosoft** 엔터티로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-180">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="6fb89-181">관심 분야에 대한 데이터는 **InterestAffinityFromMicrosoft** 엔터티에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-181">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="6fb89-182">이 엔터티는 **데이터** > **엔터티** 의 **보강** 그룹에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-182">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="6fb89-183">고객 카드의 보강 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="6fb89-183">See enrichment data on the customer card</span></span>

<span data-ttu-id="6fb89-184">개별 고객 카드에서 브랜드 및 관심 선호도를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-184">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="6fb89-185">**고객** 으로 이동하여 고객 프로필을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="6fb89-185">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="6fb89-186">고객 카드에는 해당 고객의 인구 통계학적 프로필에 있는 사람들이 선호하는 브랜드 또는 관심사에 대한 차트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-186">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="보강된 데이터가 포함된 고객 카드":::

## <a name="next-steps"></a><span data-ttu-id="6fb89-188">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6fb89-188">Next steps</span></span>

<span data-ttu-id="6fb89-189">보강된 고객 데이터를 바탕으로 구축합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-189">Build on top of your enriched customer data.</span></span> <span data-ttu-id="6fb89-190">[세그먼트](segments.md)를 만들고, [측정](measures.md)하고, 심지어 [데이터를 내보내](export-destinations.md) 고객에게 맞춤형 경험을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb89-190">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>
