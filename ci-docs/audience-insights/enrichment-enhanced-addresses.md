---
title: 주소 향상 보강
description: Microsoft 모델을 사용하여 고객 프로필의 주소 정보를 보강하고 정규화합니다.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e0ca731f944da9a7eaae7c2dc2d7568b6386089f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305440"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="d9cc3-103">향상된 주소로 고객 프로필 강화</span><span class="sxs-lookup"><span data-stu-id="d9cc3-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="d9cc3-104">데이터의 주소는 구조화되지 않았거나 불완전하거나 부정확할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="d9cc3-105">Microsoft의 모델을 사용하여 [공통 데이터 모델 형식](/common-data-model/schema/core/applicationcommon/address)으로 정규화하고 보강하여 더 나은 정확성과 인사이트를 얻으십시오.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="d9cc3-106">주소 향상 방법</span><span class="sxs-lookup"><span data-stu-id="d9cc3-106">How we enhance addresses</span></span>

<span data-ttu-id="d9cc3-107">당사 모델은 주소를 향상하기 위해 2단계 프로세스를 거칩니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="d9cc3-108">먼저 주소를 구문 분석하여 구성 요소를 식별하고 구조화된 형식에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="d9cc3-109">그런 다음 AI를 사용하여 주소의 값을 수정, 완성 및 표준화합니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-109">Then, we use AI to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="d9cc3-110">예제</span><span class="sxs-lookup"><span data-stu-id="d9cc3-110">Example</span></span>

<span data-ttu-id="d9cc3-111">주소 정보는 비표준 형식이며 맞춤법 오류가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-111">Address information might be in a nonstandard format and contain spelling errors.</span></span> <span data-ttu-id="d9cc3-112">이 모델은 이러한 문제를 해결하고 통합 고객 프로필에서 일관된 주소를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="d9cc3-113">제한 사항</span><span class="sxs-lookup"><span data-stu-id="d9cc3-113">Limitations</span></span>

<span data-ttu-id="d9cc3-114">향상된 주소는 수집된 주소 데이터에 이미 있는 값으로만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="d9cc3-115">모델은 다음을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-115">The model doesn't:</span></span> 

1. <span data-ttu-id="d9cc3-116">주소가 유효한 주소인지 확인.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="d9cc3-117">우편 번호 또는 거리 이름과 같은 값이 유효한지 확인.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="d9cc3-118">인식하지 못하는 값을 변경.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="d9cc3-119">이 모델은 기계 학습 기반 기술을 사용하여 주소를 향상시킵니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="d9cc3-120">기계 학습 기반 모델과 마찬가지로 모델이 입력 값을 변경할 때 높은 신뢰도 임계값을 적용하지만 100% 정확도는 보장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-120">While we apply a high confidence threshold for when the model changes an input value, as with any machine learning-based model, 100 percent accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="d9cc3-121">지원되는 국가 또는 지역</span><span class="sxs-lookup"><span data-stu-id="d9cc3-121">Supported countries or regions</span></span>

<span data-ttu-id="d9cc3-122">현재 다음 국가 또는 지역에서 주소 보강을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="d9cc3-123">오스트레일리아</span><span class="sxs-lookup"><span data-stu-id="d9cc3-123">Australia</span></span>
- <span data-ttu-id="d9cc3-124">캐나다</span><span class="sxs-lookup"><span data-stu-id="d9cc3-124">Canada</span></span>
- <span data-ttu-id="d9cc3-125">영국</span><span class="sxs-lookup"><span data-stu-id="d9cc3-125">United Kingdom</span></span>
- <span data-ttu-id="d9cc3-126">미국</span><span class="sxs-lookup"><span data-stu-id="d9cc3-126">United States</span></span>

<span data-ttu-id="d9cc3-127">주소에는 국가/지역 값이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="d9cc3-128">지원되지 않는 국가 또는 지역의 주소와 제공된 국가 또는 지역이 없는 주소는 처리하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="d9cc3-129">보강 구성</span><span class="sxs-lookup"><span data-stu-id="d9cc3-129">Configure the enrichment</span></span>

1. <span data-ttu-id="d9cc3-130">**데이터** > **보강** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="d9cc3-131">**향상된 주소** 타일에서 **내 데이터 보강** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="향상된 주소 타일의 스크린샷.":::

1. <span data-ttu-id="d9cc3-133">**고객 데이터 집합** 을 선택하고 보강하려는 주소가 포함된 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="d9cc3-134">*고객* 엔터티를 선택하여 모든 고객 프로파일의 주소를 보강하거나 세그먼트 엔터티를 선택하여 해당 세그먼트에 포함된 고객 프로필의 주소만 보강할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="d9cc3-135">데이터 집합에서 사용할 주소 형식을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="d9cc3-136">데이터의 주소가 단일 필드를 사용하는 경우 **단일 특성 주소** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="d9cc3-137">데이터의 주소가 둘 이상의 데이터 필드를 사용하는 경우 **다중 특성 주소** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d9cc3-138">국가/지역은 단일 특성 및 다중 특성 주소 모두에서 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-138">Country/Region is mandatory in both single-attribute and multiple-attribute addresses.</span></span> <span data-ttu-id="d9cc3-139">유효하거나 지원되는 국가/지역 값이 포함되지 않은 주소는 보강되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-139">Addresses that don't contain valid or supported country/region values won't be enriched.</span></span>

1.  <span data-ttu-id="d9cc3-140">통합 고객 엔터티의 주소 필드를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="향상된 주소 필드 매핑 페이지.":::

1. <span data-ttu-id="d9cc3-142">필드 매핑을 완료하려면 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="d9cc3-143">보강 및 출력 엔터티의 이름을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="d9cc3-144">선택 사항을 검토 한 후 **보강 저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="d9cc3-145">보강 결과</span><span class="sxs-lookup"><span data-stu-id="d9cc3-145">Enrichment results</span></span>

<span data-ttu-id="d9cc3-146">강화 프로세스를 시작하려면 명령 모음에서.**실행** 을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="d9cc3-147">[예약된 새로 고침](system.md#schedule-tab)으로 시스템이 자동으로 보강을 실행하도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d9cc3-148">처리 시간은 고객 데이터의 크기에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="d9cc3-149">보강 프로세스가 완료되면 **내 보강** 아래에서 새로 보강 된 고객 프로필 데이터를 검토 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="d9cc3-150">또한 마지막 업데이트 시간과 강화 된 프로필 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="d9cc3-151">**보강된 데이터 보기** 를 선택하여 각 보강된 프로필의 상세 보기에 액세스할 수 있습니다 .</span><span class="sxs-lookup"><span data-stu-id="d9cc3-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d9cc3-152">다음 단계</span><span class="sxs-lookup"><span data-stu-id="d9cc3-152">Next steps</span></span>

<span data-ttu-id="d9cc3-153">보강된 고객 데이터를 바탕으로 구축합니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="d9cc3-154">[세그먼트](segments.md) 및 [측정값](measures.md)을 만들고 [데이터 내보내기](export-destinations.md) 를 통해 고객에게 개인화된 경험을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc3-154">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
