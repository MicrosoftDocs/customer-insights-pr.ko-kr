---
title: Microsoft Graph로 고객 프로필 보강
description: Microsoft Graph의 독점 데이터를 사용하여 의 브랜드 및 관심 관계로 고객 데이터를 보강합니다.
ms.date: 12/10/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2c95369c778f592bc1460799aca0fa8cff813d68
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269338"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="19987-103">브랜드 및 관심 관계로 풍부한 고객 프로필 강화(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="19987-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="19987-104">Microsoft Graph의 독점 데이터를 사용하여 의 브랜드 및 관심 관계로 고객 데이터를 보강합니다.</span><span class="sxs-lookup"><span data-stu-id="19987-104">Use proprietary data from the Microsoft Graph to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="19987-105">이러한 선호도는 인구 통계가 비슷한 사람들과 고객의 데이터를 기반으로 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="19987-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="19987-106">이 정보는 고객을 특정 브랜드 및 관심사에 대한 선호도에 따라 더 잘 이해하고 분류할 수 있도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="19987-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="19987-107">대상 그룹 인사이트에서 **데이터** > **보강** 으로 이동하여 [보강 구성 및 보기](enrichment-hub.md)를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="19987-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="19987-108">브랜드 관심 보강을 구성하려면 **검색** 탭으로 이동하고 **브랜드** 타일에서 **내 데이터 보강** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19987-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="19987-109">관심 관계 보강을 구성하려면 **검색** 탭으로 이동하고 **관심** 타일에서 **내 데이터 보강** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19987-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="19987-110">![브랜드 및 관심사 타일](media/BrandsInterest-tile-Hub.png "브랜드 및 관심사 타일")</span><span class="sxs-lookup"><span data-stu-id="19987-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="about-microsoft-graph"></a><span data-ttu-id="19987-111">Microsoft Graph 정보</span><span class="sxs-lookup"><span data-stu-id="19987-111">About Microsoft Graph</span></span>

<span data-ttu-id="19987-112">Microsoft Graph의 온라인 검색 데이터를 사용하여 다양한 인구 통계 세그먼트(연령, 성별 또는 위치로 정의)에서 브랜드 및 관심 분야에 대한 친화성을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="19987-112">We use online search data from the Microsoft Graph to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="19987-113">브랜드나 관심 분야에 대한 온라인 검색 양에 따라 인구 통계학적 세그먼트가 다른 세그먼트와 비교하여 해당 브랜드나 관심 분야에 얼마나 많은 유사성이 있는지가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="19987-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

<span data-ttu-id="19987-114">[Microsoft Graph에 대해 자세히 알아보십시오](https://docs.microsoft.com/graph/overview).</span><span class="sxs-lookup"><span data-stu-id="19987-114">[Learn more about Microsoft Graph](https://docs.microsoft.com/graph/overview).</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="19987-115">선호도 수준 및 점수</span><span class="sxs-lookup"><span data-stu-id="19987-115">Affinity level and score</span></span>

<span data-ttu-id="19987-116">보강된 모든 고객 프로필에 대해 두 가지 관련 값, 즉 선호도 수준과 선호도 점수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="19987-116">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="19987-117">이러한 값은 다른 인구 통계 세그먼트와 비교하여 해당 프로필의 인구 통계 세그먼트, 브랜드 또는 관심 분야에 대한 선호도가 얼마나 강한지 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19987-117">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="19987-118">*선호도 수준* 은 4개의 수준으로 구성되며 *선호도 점수* 는 선호도 수준에 매핑되는 100점 척도로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="19987-118">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="19987-119">선호도 수준</span><span class="sxs-lookup"><span data-stu-id="19987-119">Affinity level</span></span> |<span data-ttu-id="19987-120">선호도 점수</span><span class="sxs-lookup"><span data-stu-id="19987-120">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="19987-121">매우 높음</span><span class="sxs-lookup"><span data-stu-id="19987-121">Very high</span></span>     | <span data-ttu-id="19987-122">85-100</span><span class="sxs-lookup"><span data-stu-id="19987-122">85-100</span></span>       |
|<span data-ttu-id="19987-123">높음</span><span class="sxs-lookup"><span data-stu-id="19987-123">High</span></span>     | <span data-ttu-id="19987-124">70-84</span><span class="sxs-lookup"><span data-stu-id="19987-124">70-84</span></span>        |
|<span data-ttu-id="19987-125">중간</span><span class="sxs-lookup"><span data-stu-id="19987-125">Medium</span></span>     | <span data-ttu-id="19987-126">35-69</span><span class="sxs-lookup"><span data-stu-id="19987-126">35-69</span></span>        |
|<span data-ttu-id="19987-127">낮음</span><span class="sxs-lookup"><span data-stu-id="19987-127">Low</span></span>     | <span data-ttu-id="19987-128">1-34</span><span class="sxs-lookup"><span data-stu-id="19987-128">1-34</span></span>        |

<span data-ttu-id="19987-129">선호도를 측정하기 위해 원하는 세분성에 따라 선호도 수준 또는 점수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19987-129">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="19987-130">선호도 점수를 사용하면 더 정확한 제어가 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="19987-130">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="19987-131">지원되는 국가/지역</span><span class="sxs-lookup"><span data-stu-id="19987-131">Supported countries/regions</span></span>

<span data-ttu-id="19987-132">현재 지원되는 국가/지역 옵션은 오스트레일리아, 캐나다(영어), 프랑스, 독일, 영국 또는 미국(영어)입니다.</span><span class="sxs-lookup"><span data-stu-id="19987-132">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="19987-133">국가를 선택하려면 **브랜드 보강** 또는 **관심사 보강** 을 열고 **국가/지역** 옆에 있는 **변경** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19987-133">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="19987-134">**국가/지역 설정** 창에서 옵션을 선택하고 **적용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19987-134">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="19987-135">국가 선택과 관련된 시사점</span><span class="sxs-lookup"><span data-stu-id="19987-135">Implications related to country selection</span></span>

- <span data-ttu-id="19987-136">[자신의 브랜드 선택](#define-your-brands-or-interests) 시, 시스템은 선택한 국가 또는 지역을 기준으로 제안을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="19987-136">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="19987-137">[산업 선택](#define-your-brands-or-interests) 시, 선택한 국가 또는 지역을 기준으로 가장 관련성이 높은 브랜드 또는 관심사를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19987-137">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="19987-138">[프로필 보강](#refresh-enrichment) 시, 선택한 브랜드 및 관심사에 대한 데이터를 얻을 수 있는 모든 고객 프로필을 보강합니다.</span><span class="sxs-lookup"><span data-stu-id="19987-138">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="19987-139">선택한 국가 또는 지역에 없는 프로필을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="19987-139">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="19987-140">예를 들어 독일을 선택한 경우 미국에서 선택한 브랜드 및 관심사에 대해 Microsoft Graph 데이터를 사용할 수 있는 경우 미국에 있는 프로필이 보강됩니다.</span><span class="sxs-lookup"><span data-stu-id="19987-140">For example, if you selected Germany, we'll enrich profiles located in the United States if we have Microsoft Graph data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="19987-141">보강 구성</span><span class="sxs-lookup"><span data-stu-id="19987-141">Configure Enrichment</span></span>

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="19987-142">브랜드 또는 관심 정의</span><span class="sxs-lookup"><span data-stu-id="19987-142">Define your brands or interests</span></span>

<span data-ttu-id="19987-143">다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19987-143">Select one of the following options:</span></span>

- <span data-ttu-id="19987-144">**산업**: 이 시스템은 산업과 관련된 최고 브랜드 또는 관심사를 식별하고 고객 데이터를 보강합니다.</span><span class="sxs-lookup"><span data-stu-id="19987-144">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="19987-145">**원하는 항목 선택**: 조직과 가장 관련이 있는 브랜드 또는 관심사 목록에서 최대 5개의 항목을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19987-145">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="19987-146">브랜드나 관심사를 추가하려면 입력 영역에 해당 브랜드나 관심사를 입력하여 일치하는 용어를 기반으로 제안을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="19987-146">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="19987-147">찾고 있는 브랜드나 관심 분야가 목록에 없는 경우 **제안** 링크를 사용하여 의견을 보내주십시오.</span><span class="sxs-lookup"><span data-stu-id="19987-147">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="19987-148">보강 선호 설정 검토</span><span class="sxs-lookup"><span data-stu-id="19987-148">Review enrichment preferences</span></span>

<span data-ttu-id="19987-149">기본 보강 선호 설정을 검토하고 필요에 따라 업데이트하십시오.</span><span class="sxs-lookup"><span data-stu-id="19987-149">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="보강 선호 설정 창의 스크린샷입니다.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="19987-151">보강할 엔터티 선택</span><span class="sxs-lookup"><span data-stu-id="19987-151">Select entity to enrich</span></span>

<span data-ttu-id="19987-152">**보강된 엔터티** 를 선택하고 Microsoft Graph에서 회사 데이터를 통해 보강하려는 데이터 집합을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19987-152">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft Graph.</span></span> <span data-ttu-id="19987-153">고객 엔터티를 선택하여 모든 고객 프로필을 보강하거나 세그먼트 엔터티를 선택하여 해당 세그먼트에 포함된 고객 프로필만 보강할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19987-153">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="19987-154">필드 매핑</span><span class="sxs-lookup"><span data-stu-id="19987-154">Map your fields</span></span>

<span data-ttu-id="19987-155">통합 고객 엔터티의 필드를 매핑하여 시스템에서 고객 데이터를 보강하는 데 사용할 인구 통계학적 세그먼트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="19987-155">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="19987-156">국가/지역 및 최소한 생년월일 또는 성별 특성을 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="19987-156">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="19987-157">또한 하나 이상의 구/군(및 시/도) 또는 우편 번호를 매핑해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19987-157">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="19987-158">**편집** 을 선택하고 필드의 매핑을 정의하고 완료하면 **적용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19987-158">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="19987-159">**저장** 필드를 선택하여 매핑을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="19987-159">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="19987-160">다음 형식 및 값이 지원되며 값은 대소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19987-160">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="19987-161">**생년월일**: 데이터 수집 시 생년월일을 날짜/시간 형식으로 변환하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="19987-161">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="19987-162">또는 [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html)의 "yyyy-MM-dd" 또는 "yyyy-MM-ddTHH:mm:ssZ" 형식의 문자열이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19987-162">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="19987-163">**성별**: 남성, 여성, 알 수 없음</span><span class="sxs-lookup"><span data-stu-id="19987-163">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="19987-164">**우편 번호**: 미국의 경우 5자리 우편 번호, 기타 모든 국가의 표준 우편 번호</span><span class="sxs-lookup"><span data-stu-id="19987-164">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="19987-165">**도시**: 영어로 된 도시 이름</span><span class="sxs-lookup"><span data-stu-id="19987-165">**City**: City name in English</span></span>
- <span data-ttu-id="19987-166">**시/도**: 미국 및 캐나다의 경우 두 글자 약어입니다.</span><span class="sxs-lookup"><span data-stu-id="19987-166">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="19987-167">호주의 경우 2~3자의 약어입니다.</span><span class="sxs-lookup"><span data-stu-id="19987-167">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="19987-168">프랑스, 독일 또는 영국에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19987-168">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="19987-169">**국가/지역**:</span><span class="sxs-lookup"><span data-stu-id="19987-169">**Country/Region**:</span></span>

  - <span data-ttu-id="19987-170">US: 미합중국, 미국, USA, US</span><span class="sxs-lookup"><span data-stu-id="19987-170">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="19987-171">CA: 캐나다, CA</span><span class="sxs-lookup"><span data-stu-id="19987-171">CA: Canada, CA</span></span>
  - <span data-ttu-id="19987-172">GB: 영국, UK, 그레이트브리튼, GB, 그레이트브리튼 및 북아일랜드연합왕국, 대브리튼왕국</span><span class="sxs-lookup"><span data-stu-id="19987-172">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="19987-173">AU: 호주, 오스트레일리아, AU, 오스트레일리아연방</span><span class="sxs-lookup"><span data-stu-id="19987-173">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="19987-174">FR: 프랑스, FR, 프랑스 공화국</span><span class="sxs-lookup"><span data-stu-id="19987-174">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="19987-175">DE: 독일, 독일어, Deutschland, Allemagne, DE, 독일 연방 공화국, 독일 공화국</span><span class="sxs-lookup"><span data-stu-id="19987-175">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="refresh-enrichment"></a><span data-ttu-id="19987-176">보강 새로 고침</span><span class="sxs-lookup"><span data-stu-id="19987-176">Refresh enrichment</span></span>

<span data-ttu-id="19987-177">인구 통계에 대한 브랜드, 관심 분야 및 필드 매핑을 구성한 후 보강을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="19987-177">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="19987-178">프로세스를 시작하려면 브랜드 또는 관심사 구성 페이지에서 **실행** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19987-178">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="19987-179">또한 예약된 새로 고침의 일부로 시스템에서 자동으로 보강 기능을 실행하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19987-179">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="19987-180">고객 데이터의 크기에 따라 보강 실행이 완료되는 데 몇 분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19987-180">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="19987-181">작업/프로세스 [상태에는 6가지 유형](system.md#status-types)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19987-181">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="19987-182">또한 대부분의 프로세스는 [다른 다운스트림 프로세스에 의존](system.md#refresh-policies)합니다.</span><span class="sxs-lookup"><span data-stu-id="19987-182">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="19987-183">프로세스 상태를 선택하여 전체 작업의 진행률에 대한 세부 사항을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19987-183">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="19987-184">작업 중 하나를 선택한 다음 **자세히 보기** 참조를 선택하면, 처리 시간, 마지막 처리 날짜, 작업과 관련된 모든 오류 및 경고와 같은 추가 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19987-184">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="19987-185">보강 결과</span><span class="sxs-lookup"><span data-stu-id="19987-185">Enrichment results</span></span>

<span data-ttu-id="19987-186">보강 프로세스를 실행한 후 **내 보강** 으로 이동하여 총 보강 고객 수와 보강된 고객 프로필에 대한 브랜드 또는 관심사를 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="19987-186">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="보강 프로세스를 실행한 후 결과 미리 보기":::

<span data-ttu-id="19987-188">차트에서 **보강된 데이터 보기** 를 선택하여 풍부한 데이터를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="19987-188">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="19987-189">브랜드에 대한 보강 데이터는 **BrandAffinityFromMicrosoft** 엔터티로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="19987-189">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="19987-190">관심 분야에 대한 데이터는 **InterestAffinityFromMicrosoft** 엔터티에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19987-190">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="19987-191">이 엔터티는 **데이터** > **엔터티** 의 **보강** 그룹에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="19987-191">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="19987-192">고객 카드의 보강 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="19987-192">See enrichment data on the customer card</span></span>

<span data-ttu-id="19987-193">개별 고객 카드에서 브랜드 및 관심 선호도를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19987-193">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="19987-194">**고객** 으로 이동하여 고객 프로필을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="19987-194">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="19987-195">고객 카드에는 해당 고객의 인구 통계학적 프로필에 있는 사람들이 선호하는 브랜드 또는 관심사에 대한 차트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19987-195">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="보강된 데이터가 포함된 고객 카드":::

## <a name="next-steps"></a><span data-ttu-id="19987-197">다음 단계</span><span class="sxs-lookup"><span data-stu-id="19987-197">Next steps</span></span>

<span data-ttu-id="19987-198">보강된 고객 데이터를 바탕으로 구축합니다.</span><span class="sxs-lookup"><span data-stu-id="19987-198">Build on top of your enriched customer data.</span></span> <span data-ttu-id="19987-199">[세그먼트](segments.md)를 만들고, [측정](measures.md)하고, 심지어 [데이터를 내보내](export-destinations.md) 고객에게 맞춤형 경험을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="19987-199">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]