---
title: 타사 보강 HERE Technologies로 보강
description: HERE Technologies 타사 보강에 대한 일반 정보입니다.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668686"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="2fc87-103">HERE Technologies로 고객 프로필 보강(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="2fc87-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="2fc87-104">HERE Technologies는 위치 중심 데이터 및 서비스를 제공하는 위치 플랫폼 회사입니다.</span><span class="sxs-lookup"><span data-stu-id="2fc87-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="2fc87-105">HERE Technologies의 데이터 보강 서비스를 사용하면 주소 정규화, 위도 및 경도 추출 등을 통해 고객에 대한 보다 정확한 위치 이해를 구축할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fc87-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2fc87-106">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="2fc87-106">Prerequisites</span></span>

<span data-ttu-id="2fc87-107">HERE Technologies 보강을 구성하려면 다음 필수 구성 요소가 충족되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc87-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="2fc87-108">활성 HERE Technologies 구독이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc87-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="2fc87-109">구독을 받으려면 [여기에 등록](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic)하거나 직접 [HERE Technologies에 연락](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fc87-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="2fc87-110">HERE Technologies Location 보강에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="2fc87-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="2fc87-111">HERE Technologies API 키가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc87-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="2fc87-112">[관리자](permissions.md#administrator) 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc87-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="2fc87-113">구성</span><span class="sxs-lookup"><span data-stu-id="2fc87-113">Configuration</span></span>

1. <span data-ttu-id="2fc87-114">**데이터** > **보강** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc87-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="2fc87-115">HERE Technologies 타일에서 **내 데이터 보강을 선택** 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc87-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2fc87-116">![HERE Technologies 타일](media/HERE-tile.png "HERE Technologies 타일")</span><span class="sxs-lookup"><span data-stu-id="2fc87-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="2fc87-117">활성 **HERE Technologies API 키** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc87-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="2fc87-118">**동의함** 확인란을 선택하여 **데이터 개인 정보 및 규정 준수** 에 대한 동의를 검토하고 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc87-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="2fc87-119">**HERE에 연결** 을 선택하여 입력을 둘 다 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc87-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1. <span data-ttu-id="2fc87-120">**데이터 추가** 를 선택하고 필드를 기본 또는 보조 주소에 매핑할지 여부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc87-120">Select **Add data** and choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="2fc87-121">두 주소(예: 집 및 회사 주소)에 대한 필드 매핑을 지정하고 두 주소에 대해 개별적으로 프로필을 보강할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fc87-121">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="2fc87-122">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc87-122">Select **Next**.</span></span>

1. <span data-ttu-id="2fc87-123">HERE Technologies에서 일치하는 위치 데이터를 찾는 데 사용해야 하는 통합 프로필의 필드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc87-123">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="2fc87-124">**상세 주소 1** 및 **우편 번호** 필드는 선택한 기본 또는 보조 주소의 필수 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="2fc87-124">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="2fc87-125">더 높은 일치 정확도를 위해 더 많은 필드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fc87-125">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2fc87-126">![HERE Technologies 강화 구성 페이지](media/enrichment-HERE-configuration.png "HERE Technologies 강화 구성 페이지")</span><span class="sxs-lookup"><span data-stu-id="2fc87-126">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="2fc87-127">**적용** 을 선택하여 필드 매핑을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc87-127">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="2fc87-128">보강 결과</span><span class="sxs-lookup"><span data-stu-id="2fc87-128">Enrichment results</span></span>

<span data-ttu-id="2fc87-129">강화 프로세스를 시작하려면 명령 모음에서.**실행** 을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="2fc87-129">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="2fc87-130">[예약된 새로 고침](system.md#schedule-tab)으로 시스템이 자동으로 보강을 실행하도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fc87-130">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2fc87-131">처리 시간은 고객 데이터의 크기와 HERE Technologies의 API 응답 시간에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="2fc87-131">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="2fc87-132">보강 프로세스가 완료되면 **내 보강** 아래에서 새로 보강 된 고객 프로필 데이터를 검토 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fc87-132">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="2fc87-133">또한 마지막 업데이트 시간과 강화 된 프로필 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fc87-133">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="2fc87-134">**보강된 데이터 보기** 를 선택하여 각 보강된 프로필의 상세 보기에 액세스할 수 있습니다 .</span><span class="sxs-lookup"><span data-stu-id="2fc87-134">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2fc87-135">다음 단계</span><span class="sxs-lookup"><span data-stu-id="2fc87-135">Next steps</span></span>

<span data-ttu-id="2fc87-136">보강된 고객 데이터를 바탕으로 구축합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc87-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="2fc87-137">[세그먼트](segments.md)를 만들고, [측정](measures.md)하고, 또한 [데이터를 내보내](export-destinations.md) 고객에게 맞춤형 경험을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc87-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2fc87-138">데이터 프라이버시 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="2fc87-138">Data privacy and compliance</span></span>

<span data-ttu-id="2fc87-139">Dynamics 365 Customer Insights를 사용하여 HERE Technologies로 데이터를 전송하는 경우 Dynamics 365 Customer Insights 규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fc87-139">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2fc87-140">Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 HERE Technologies가 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fc87-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="2fc87-141">자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2fc87-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="2fc87-142">Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 보강을 언제든지 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fc87-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
