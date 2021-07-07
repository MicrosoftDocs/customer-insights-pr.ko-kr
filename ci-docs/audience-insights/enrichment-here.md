---
title: 제3자 보강을 통한 보강 HERE Technologies
description: HERE Technologies 타사 보강에 대한 일반 정보입니다.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b3c1da0f541efb85b2ca9d87a2e3b97bbfb6ca7f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305302"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="dba61-103">HERE Technologies로 고객 프로필 보강(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="dba61-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="dba61-104">HERE Technologies는 위치 중심 데이터 및 서비스를 제공하는 위치 플랫폼 회사입니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="dba61-105">HERE Technologies의 데이터 보강 서비스를 사용하면 주소 정규화, 위도 및 경도 추출 등을 통해 고객에 대한 보다 정확한 위치 이해를 구축할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dba61-106">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="dba61-106">Prerequisites</span></span>

<span data-ttu-id="dba61-107">HERE Technologies 보강을 구성하려면 다음 필수 구성 요소가 충족되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="dba61-108">활성 HERE Technologies 구독이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="dba61-109">구독하려면 [여기에서 등록](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic)하거나 직접 [HERE Technologies에 연락](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-109">To get a subscription, you can [sign up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="dba61-110">HERE Technologies Location 보강에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="dba61-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="dba61-111">HERE [연결](connections.md)을 사용할 수 *있거나* 귀하가 [관리자](permissions.md#administrator) 권한 및 HERE Technologies API 키를 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-111">A HERE [connection](connections.md) is available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="dba61-112">보강 구성</span><span class="sxs-lookup"><span data-stu-id="dba61-112">Configure the enrichment</span></span>

1. <span data-ttu-id="dba61-113">**데이터** > **보강** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="dba61-114">HERE Technologies 타일에서 **내 데이터 보강** 을 선택하고 **시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dba61-115">![HERE Technologies 타일](media/HERE-tile.png "HERE Technologies 타일")</span><span class="sxs-lookup"><span data-stu-id="dba61-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="dba61-116">드롭다운 목록에서 [연결](connections.md)을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="dba61-116">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="dba61-117">사용 가능한 연결이 없으면 관리자에게 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="dba61-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="dba61-118">관리자인 경우 **연결 추가** 를 선택하여 연결을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="dba61-119">드롭다운 목록에서 **HERE Technologies** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-119">Choose **HERE Technologies** from the dropdown list.</span></span> 

1. <span data-ttu-id="dba61-120">**HERE Technologies에 연결** 을 선택하여 선택을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="dba61-121">**다음** 을 선택하고 HERE Technologies의 위치 데이터로 보강할 **고객 데이터 집합** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="dba61-122">**고객** 엔터티를 선택하여 모든 고객 프로필을 보강하거나 세그먼트 엔터티를 선택하여 해당 세그먼트에 포함된 고객 프로필만 보강할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="고객 데이터 집합 선택 시 스크린샷입니다.":::

1. <span data-ttu-id="dba61-124">필드를 기본 또는 보조 주소에 매핑할지 여부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="dba61-125">두 주소에 대해 필드 매핑을 지정하고 두 주소에 대해 개별적으로 프로필을 보강할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="dba61-126">예를 들어 집과 회사 주소가 있는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="dba61-127">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-127">Select **Next**.</span></span>

1. <span data-ttu-id="dba61-128">HERE Technologies에서 일치하는 위치 데이터를 찾는 데 사용해야 하는 통합 프로필의 필드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="dba61-129">**상세 주소 1** 및 **우편 번호** 필드는 선택한 기본 또는 보조 주소의 필수 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="dba61-130">더 높은 일치 정확도를 위해 더 많은 필드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dba61-131">![HERE Technologies 강화 구성 페이지](media/enrichment-HERE-configuration.png "HERE Technologies 강화 구성 페이지")</span><span class="sxs-lookup"><span data-stu-id="dba61-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="dba61-132">필드 매핑을 완료하려면 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="dba61-133">보강의 이름을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-133">Provide a name for the enrichment.</span></span> 

1. <span data-ttu-id="dba61-134">선택 사항을 검토 한 후 **보강 저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-134">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="dba61-135">HERE Technologies에 대한 연결 구성</span><span class="sxs-lookup"><span data-stu-id="dba61-135">Configure the connection for HERE Technologies</span></span> 

<span data-ttu-id="dba61-136">연결을 구성하려면 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="dba61-137">보강을 구성할 때 **연결 추가** 를 선택 *하거나* **관리자** > **연결** 로 이동하여 HERE technologies 타일에서 **설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="dba61-138">**표시 이름** 상자에 연결 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="dba61-139">유효한 HERE Technologies API 키를 제공하십시오.</span><span class="sxs-lookup"><span data-stu-id="dba61-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="dba61-140">**데이터 개인 정보 보호 및 규정 준수** 를 검토하고 **동의함** 을 선택하여 동의를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-140">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="dba61-141">**확인** 을 선택하여 구성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="dba61-142">확인을 완료한 후 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-142">After completing the verification, select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dba61-143">![HERE technologies 연결 구성 페이지](media/enrichment-HERE-connection.png "HERE technologies 연결 구성 페이지")</span><span class="sxs-lookup"><span data-stu-id="dba61-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="dba61-144">보강 결과</span><span class="sxs-lookup"><span data-stu-id="dba61-144">Enrichment results</span></span>

<span data-ttu-id="dba61-145">강화 프로세스를 시작하려면 명령 모음에서.**실행** 을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="dba61-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="dba61-146">[예약된 새로 고침](system.md#schedule-tab)으로 시스템이 자동으로 보강을 실행하도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="dba61-147">처리 시간은 고객 데이터의 크기와 HERE Technologies의 API 응답 시간에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="dba61-148">보강 프로세스가 완료되면 **내 보강** 아래에서 새로 보강 된 고객 프로필 데이터를 검토 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="dba61-149">또한 마지막 업데이트 시간과 강화 된 프로필 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="dba61-150">**보강된 데이터 보기** 를 선택하여 각 보강된 프로필의 상세 보기에 액세스할 수 있습니다 .</span><span class="sxs-lookup"><span data-stu-id="dba61-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="dba61-151">다음 단계</span><span class="sxs-lookup"><span data-stu-id="dba61-151">Next steps</span></span>

<span data-ttu-id="dba61-152">보강된 고객 데이터를 바탕으로 구축합니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="dba61-153">[세그먼트](segments.md) 및 [측정값](measures.md)을 만들고 [데이터 내보내기](export-destinations.md) 를 통해 고객에게 개인화된 경험을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-153">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="dba61-154">데이터 프라이버시 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="dba61-154">Data privacy and compliance</span></span>

<span data-ttu-id="dba61-155">Dynamics 365 Customer Insights를 사용하여 HERE Technologies로 데이터를 전송하는 경우 Dynamics 365 Customer Insights 규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="dba61-156">Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 HERE Technologies가 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="dba61-157">자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dba61-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="dba61-158">Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 보강을 언제든지 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dba61-158">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
