---
title: AdRoll로 Customer Insights 데이터 내보내기
description: AdRoll 연결을 구성하는 방법을 알아보십시오.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697082"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="69dd3-103">AdRoll용 커넥터(프리뷰)</span><span class="sxs-lookup"><span data-stu-id="69dd3-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="69dd3-104">통합 고객 프로필의 세그먼트를 AdRoll로 내보내고 광고에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69dd3-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="69dd3-105">필요한 항목</span><span class="sxs-lookup"><span data-stu-id="69dd3-105">Prerequisites</span></span>

-   <span data-ttu-id="69dd3-106">[AdRoll 거래처](https://www.adroll.com/) 및 해당 관리자 자격 증명이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69dd3-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="69dd3-107">대상 그룹 인사이트에 [구성된 세그먼트](segments.md)가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69dd3-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="69dd3-108">내보낸 세그먼트의 통합 고객 프로필에는 이메일 주소를 나타내는 필드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="69dd3-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="69dd3-109">AdRoll에 연결</span><span class="sxs-lookup"><span data-stu-id="69dd3-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="69dd3-110">**관리자** > **내보내기 대상** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="69dd3-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="69dd3-111">**AdRoll** 에서 **설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="69dd3-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="69dd3-112">**표시 이름** 필드에서 내보내기 대상에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="69dd3-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="AdRoll 연결을 위한 구성 창입니다.":::

1. <span data-ttu-id="69dd3-114">**동의** 를 선택해 **데이터 프라이버시 및 규정 준수** 를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="69dd3-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="69dd3-115">**연결** 을 선택하여 AdRoll에 대한 연결을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="69dd3-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="69dd3-116">**AdRoll로 인증** 을 선택하고 AdRoll 관리자 자격 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="69dd3-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="69dd3-117">**내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="69dd3-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="69dd3-118">**AdRoll 광고주 ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="69dd3-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="69dd3-119">**다음** 을 선택해 내보내기를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="69dd3-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="69dd3-120">커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="69dd3-120">Configure the connector</span></span>

1. <span data-ttu-id="69dd3-121">**데이터 일치** 섹션의 이메일 필드에서 고객의 **이메일** 주소를 나타내는 통합 고객 프로필의 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="69dd3-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="69dd3-122">세그먼트를 AdRoll로 내보내는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="69dd3-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="69dd3-123">내보낼 세그먼트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="69dd3-123">Select the segments you want to export.</span></span> <span data-ttu-id="69dd3-124">구성원이 100명 이상인 세그먼트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="69dd3-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="69dd3-125">더 작은 세그먼트는 내보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69dd3-125">You can't export smaller segments.</span></span> <span data-ttu-id="69dd3-126">또한 내보낼 세그먼트의 최대 크기는 내보내기당 250,000명입니다.</span><span class="sxs-lookup"><span data-stu-id="69dd3-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="69dd3-127">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="69dd3-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="69dd3-128">데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="69dd3-128">Export the data</span></span>

<span data-ttu-id="69dd3-129">[주문 시 데이터를 내보낼](export-destinations.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69dd3-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="69dd3-130">내보내기는 [예약된 새로 고침](system.md#schedule-tab)마다 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="69dd3-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="69dd3-131">알려진 제한 사항</span><span class="sxs-lookup"><span data-stu-id="69dd3-131">Known limitations</span></span>

- <span data-ttu-id="69dd3-132">내보내기당 25만 개의 고객 프로필을 AdRoll로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69dd3-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="69dd3-133">프로필이 100개 미만인 세그먼트는 AdRoll로 내보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69dd3-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="69dd3-134">AdRoll로 내보내기는 세그먼트로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="69dd3-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="69dd3-135">최대 250,000개의 프로필을 AdRoll로 내보내는 데 최대 10분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69dd3-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="69dd3-136">AdRoll로 내보낼 수 있는 프로필 수는 AdRoll과의 계약에 따라 다르며 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="69dd3-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="69dd3-137">데이터 프라이버시 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="69dd3-137">Data privacy and compliance</span></span>

<span data-ttu-id="69dd3-138">Dynamics 365 Customer Insights를 사용하여 AdRoll로 데이터를 전송하는 경우 Dynamics 365 Customer Insights 규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69dd3-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="69dd3-139">Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 AdRoll가 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69dd3-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="69dd3-140">자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69dd3-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="69dd3-141">Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69dd3-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
