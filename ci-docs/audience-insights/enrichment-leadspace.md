---
title: 타사 보강 Leadspace를 사용하여 회사 프로필 보강
description: Leadspace 타사 보강에 대한 일반 정보입니다.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668731"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="b78af-103">Leadspace를 통한 회사 프로필 강화(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="b78af-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="b78af-104">Leadspace는 B2B 고객 데이터 플랫폼을 제공하는 데이터 과학 회사입니다.</span><span class="sxs-lookup"><span data-stu-id="b78af-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="b78af-105">통합된 고객 프로필을 보유한 고객이 회사의 데이터를 보강할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b78af-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="b78af-106">보강에는 회사 규모, 위치, 산업 등과 같은 추가 특성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b78af-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b78af-107">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="b78af-107">Prerequisites</span></span>

<span data-ttu-id="b78af-108">Leadspace를 구성하려면 다음 전제 조건이 충족되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b78af-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="b78af-109">활성 Leadspace 라이선스와 "영구 키"(**Leadspace 토큰** 이라고 함)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b78af-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="b78af-110">그들의 제품에 대한 자세한 내용은 [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/)에 직접 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="b78af-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="b78af-111">[관리자](permissions.md#administrator) 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b78af-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="b78af-112">회사의 [통합 고객 프로필](customer-profiles.md)을 갖고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b78af-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="b78af-113">구성</span><span class="sxs-lookup"><span data-stu-id="b78af-113">Configuration</span></span>

1. <span data-ttu-id="b78af-114">대상 그룹 인사이트에서 **데이터** > **보강** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b78af-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="b78af-115">Leadspace 타일에서 **내 데이터 보강** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b78af-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace 타일의 스크린샷.":::

1. <span data-ttu-id="b78af-117">**시작** 을 선택한 후 활성 **Leadspace 토큰**(영구 키)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b78af-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="b78af-118">**동의함** 확인란을 선택하여 **데이터 개인 정보 및 규정 준수** 에 대한 동의를 검토하고 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b78af-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="b78af-119">**Leadspace에 연결** 을 선택하여 입력을 둘 다 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b78af-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="b78af-120">**데이터 매핑** 을 선택하고 Leadspace에서 일치하는 회사 데이터를 찾는 데 사용해야 하는 통합 프로필의 필드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b78af-120">Select **Map data** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="b78af-121">**회사의 이름** 필드는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="b78af-121">The **Name of company** field is required.</span></span> <span data-ttu-id="b78af-122">일치 정확도를 높이기 위해 **회사 웹 사이트** 및 **회사 위치** 라는 다른 필드를 최대 2개까지 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b78af-122">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace 필드 매핑 창.":::
   
1. <span data-ttu-id="b78af-124">**적용** 을 선택하여 필드 매핑을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="b78af-124">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="b78af-125">**실행** 을 선택하여 회사 프로필을 보강합니다.</span><span class="sxs-lookup"><span data-stu-id="b78af-125">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="b78af-126">보강에 걸리는 시간은 통합 고객 프로필의 수에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b78af-126">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="b78af-127">보강 결과</span><span class="sxs-lookup"><span data-stu-id="b78af-127">Enrichment results</span></span>

<span data-ttu-id="b78af-128">보강을 새로 고친 후 [내 보강](enrichment-hub.md) 아래에서 새로 보강된 회사 데이터를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b78af-128">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="b78af-129">마지막 업데이트 시간과 보강된 프로필 수를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b78af-129">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="b78af-130">**보강된 데이터 보기** 를 선택하여 각 보강된 프로필의 상세 보기에 액세스할 수 있습니다 .</span><span class="sxs-lookup"><span data-stu-id="b78af-130">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="b78af-131">자세한 내용은 [Leadspace API](https://support.leadspace.com/hc/en-us/sections/201997649-API)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b78af-131">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="b78af-132">다음 단계</span><span class="sxs-lookup"><span data-stu-id="b78af-132">Next steps</span></span>

<span data-ttu-id="b78af-133">보강된 고객 데이터를 바탕으로 구축합니다.</span><span class="sxs-lookup"><span data-stu-id="b78af-133">Build on top of your enriched customer data.</span></span> <span data-ttu-id="b78af-134">[세그먼트](segments.md)를 만들고, [측정](measures.md)하고, 또한 [데이터를 내보내](export-destinations.md) 고객에게 맞춤형 경험을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b78af-134">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b78af-135">데이터 프라이버시 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="b78af-135">Data privacy and compliance</span></span>

<span data-ttu-id="b78af-136">Dynamics 365 Customer Insights를 사용하여 Leadspace로 데이터를 전송하는 경우 Dynamics 365 Customer Insights 규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b78af-136">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b78af-137">Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 Leadspace가 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b78af-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b78af-138">자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b78af-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b78af-139">Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 보강을 언제든지 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b78af-139">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>