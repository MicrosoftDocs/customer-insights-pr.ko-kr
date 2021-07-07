---
title: 타사 보강 Leadspace를 사용하여 회사 프로필 보강
description: Leadspace 타사 보강에 대한 일반 정보입니다.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0496d10c994cd077a778a6e745e3774e316765ae
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305210"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="285a2-103">Leadspace를 통한 회사 프로필 강화(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="285a2-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="285a2-104">Leadspace는 B2B 고객 데이터 플랫폼을 제공하는 데이터 과학 회사입니다.</span><span class="sxs-lookup"><span data-stu-id="285a2-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="285a2-105">통합된 고객 프로필을 보유한 고객이 회사의 데이터를 보강할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="285a2-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="285a2-106">보강에 회사 규모, 위치, 산업과 같은 더 많은 특성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="285a2-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="285a2-107">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="285a2-107">Prerequisites</span></span>

<span data-ttu-id="285a2-108">Leadspace를 구성하려면 다음 전제 조건이 충족되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="285a2-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="285a2-109">활성 Leadspace 라이선스.</span><span class="sxs-lookup"><span data-stu-id="285a2-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="285a2-110">회사의 [통합 고객 프로필](customer-profiles.md)을 갖고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="285a2-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="285a2-111">관리자가 Leadspace 연결을 이미 구성했거나 귀하가 [관리자](permissions.md#administrator) 권한 및 "영구 키"(**Leadspace 토큰**)를 가지고 있음.</span><span class="sxs-lookup"><span data-stu-id="285a2-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="285a2-112">제품에 대한 자세한 설명은 [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/)에 직접 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="285a2-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="285a2-113">보강 구성</span><span class="sxs-lookup"><span data-stu-id="285a2-113">Configure the enrichment</span></span>

1. <span data-ttu-id="285a2-114">대상 그룹 인사이트에서 **데이터** > **보강** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="285a2-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="285a2-115">Leadspace 타일에서 **내 데이터 보강** 을 선택하고 **시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="285a2-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace 타일의 스크린샷.":::

1. <span data-ttu-id="285a2-117">드롭다운 목록에서 [연결](connections.md)을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="285a2-117">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="285a2-118">사용 가능한 연결이 없으면 관리자에게 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="285a2-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="285a2-119">관리자인 경우 **연결 추가** 를 선택하고 **Leadspace** 를 선택하여 연결을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="285a2-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="285a2-120">**Leadspace에 연결** 을 선택하여 연결을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="285a2-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="285a2-121">**다음** 을 선택하고 Leadspace의 회사 데이터로 보강할 **고객 데이터 집합** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="285a2-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="285a2-122">**고객** 엔터티를 선택하여 모든 고객 프로필을 보강하거나 세그먼트 엔터티를 선택하여 해당 세그먼트에 포함된 고객 프로필만 보강할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="285a2-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="고객 데이터 집합 선택 시 스크린샷입니다.":::

1. <span data-ttu-id="285a2-124">**다음** 을 선택하고 Leadspace에서 일치하는 회사 데이터를 찾는 데 사용해야 하는 통합 프로필의 필드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="285a2-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="285a2-125">**회사의 이름** 필드는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="285a2-125">The **Name of company** field is required.</span></span> <span data-ttu-id="285a2-126">일치 정확도를 높이기 위해 **회사 웹 사이트** 및 **회사 위치** 라는 다른 필드를 최대 2개까지 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="285a2-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace 필드 매핑 창.":::

1. <span data-ttu-id="285a2-128">필드 매핑을 완료하려면 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="285a2-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="285a2-129">보강에 대한 이름을 제공하고 선택 사항을 검토한 후 **보강 저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="285a2-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="285a2-130">Leadspace에 대한 연결 구성</span><span class="sxs-lookup"><span data-stu-id="285a2-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="285a2-131">연결을 구성하려면 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="285a2-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="285a2-132">보강을 구성할 때 **연결 추가** 를 선택 *하거나* **관리자** > **연결** 로 이동하여 Leadspace 타일에서 **설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="285a2-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="285a2-133">**시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="285a2-133">Select **Get Started**.</span></span> 

1. <span data-ttu-id="285a2-134">**표시 이름** 상자에 연결 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="285a2-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="285a2-135">유효한 Leadspace 토큰을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="285a2-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="285a2-136">**데이터 개인 정보 보호 및 규정 준수** 를 검토하고 **동의함** 을 선택하여 동의를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="285a2-136">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="285a2-137">**확인** 을 선택하여 구성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="285a2-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="285a2-138">확인을 완료한 후 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="285a2-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace 연결 구성 페이지.":::

## <a name="enrichment-results"></a><span data-ttu-id="285a2-140">보강 결과</span><span class="sxs-lookup"><span data-stu-id="285a2-140">Enrichment results</span></span>

<span data-ttu-id="285a2-141">보강을 새로 고친 후 [내 보강](enrichment-hub.md) 아래에서 새로 보강된 회사 데이터를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="285a2-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="285a2-142">마지막 업데이트 시간과 보강된 프로필 수를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="285a2-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="285a2-143">**보강된 데이터 보기** 를 선택하여 각 보강된 프로필의 상세 보기에 액세스할 수 있습니다 .</span><span class="sxs-lookup"><span data-stu-id="285a2-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="285a2-144">자세한 내용은 [Leadspace API](https://support.leadspace.com/hc/en-us/sections/201997649-API)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="285a2-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="285a2-145">다음 단계</span><span class="sxs-lookup"><span data-stu-id="285a2-145">Next steps</span></span>

<span data-ttu-id="285a2-146">보강된 고객 데이터를 바탕으로 구축합니다.</span><span class="sxs-lookup"><span data-stu-id="285a2-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="285a2-147">[세그먼트](segments.md) 및 [측정값](measures.md)을 만들고 [데이터 내보내기](export-destinations.md) 를 통해 고객에게 개인화된 경험을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="285a2-147">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="285a2-148">데이터 프라이버시 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="285a2-148">Data privacy and compliance</span></span>

<span data-ttu-id="285a2-149">Dynamics 365 Customer Insights를 사용하여 Leadspace로 데이터를 전송하는 경우 Dynamics 365 Customer Insights 규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="285a2-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="285a2-150">Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 Leadspace가 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="285a2-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="285a2-151">자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="285a2-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="285a2-152">Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 보강을 언제든지 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="285a2-152">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
