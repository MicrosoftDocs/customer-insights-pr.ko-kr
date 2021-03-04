---
title: Facebook Ads Manager로 Customer Insights 데이터 내보내기
description: Facebook 광고 관리자에 대한 연결을 구성하는 방법 알아보기.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c839f9dc7e403412c0e3d936392d45a43bc63545
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269982"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="45fb6-103">Facebook 광고 관리자용 커넥터(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="45fb6-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="45fb6-104">통합 고객 프로필 세그먼트를 Facebook 광고 관리자에 내보내 Facebook 및 Instagram에서 캠페인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45fb6-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="45fb6-105">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="45fb6-105">Prerequisites</span></span>

- <span data-ttu-id="45fb6-106">[**Facebook 비즈니스 계정**](https://business.facebook.com/)이 포함된 [**Facebook 광고 계정**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45fb6-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="45fb6-107">[**Facebook 광고 계정**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)의 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45fb6-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="45fb6-108">Facebook 광고 관리자에 연결</span><span class="sxs-lookup"><span data-stu-id="45fb6-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="45fb6-109">**관리자** > **내보내기 대상** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="45fb6-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="45fb6-110">**Facebook 광고 관리자** 아래에서 **설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45fb6-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="45fb6-111">**표시 이름** 필드에서 내보내기 대상에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="45fb6-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="45fb6-112">**Facebook으로 계속** 을 선택하고 Facebook 광고 계정에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="45fb6-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="45fb6-113">Facebook으로 인증한 후 **ads_management** 권한을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="45fb6-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="45fb6-114">작업할 **Facebook 광고 계정** 을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="45fb6-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="45fb6-115">드롭다운 목록에서 **기존 사용자 지정 대상 그룹** 을 선택하거나 **새 사용자 지정 대상 그룹** 을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45fb6-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="45fb6-116">자세한 내용은 [**Facebook 광고 관리자의 대상 그룹**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="45fb6-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="45fb6-117">**동의** 를 선택해 **데이터 프라이버시 및 규정 준수** 를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="45fb6-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="45fb6-118">**다음** 을 선택해 내보내기를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="45fb6-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="45fb6-119">커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="45fb6-119">Configure the connector</span></span>

1. <span data-ttu-id="45fb6-120">**키 식별자 필드 선택** 에서 **이메일**, **이름과 주소** 또는 **전화** 를 선택해 Facebook 광고 관리자에 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="45fb6-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="45fb6-121">선택한 키 식별자에 대해 통합 고객 엔터티의 해당 특성을 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="45fb6-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="45fb6-122">[도움말] **이메일** 을 키 식별자로 선택하면 가장 많이 일치하는 결과를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="45fb6-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="45fb6-123">식별자를 추가하면 일치가 향상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45fb6-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="45fb6-124">**특성 추가** 를 선택해 추가 특성을 매핑하고 Facebook 광고 관리자로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="45fb6-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="45fb6-125">Facebook 광고 관리자의 특성은 다음과 같은 사용자 이름으로 매핑됩니다. **FN** = **이름**, **LN** = **성**, **FI** = **첫 이니셜**, **PHONE** = **전화**, **GEN** = **성별**, **DOB** = **생년월일**, **ST** = **주**, **CT** = **도시**, **ZIP** = **우편 번호**, **COUNTRY** = **국가/지역**</span><span class="sxs-lookup"><span data-stu-id="45fb6-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="45fb6-126">내보낼 세그먼트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45fb6-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="45fb6-127">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45fb6-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="45fb6-128">데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="45fb6-128">Export the data</span></span>

<span data-ttu-id="45fb6-129">[주문 시 데이터를 내보낼](export-destinations.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45fb6-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="45fb6-130">내보내기는 [예약된 새로 고침](system.md#schedule-tab)마다 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="45fb6-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="45fb6-131">알려진 제한 사항</span><span class="sxs-lookup"><span data-stu-id="45fb6-131">Known limitations</span></span>

- <span data-ttu-id="45fb6-132">Facebook 광고 관리자에게 내보내기당 최대 1,000만 개의 고객 프로필</span><span class="sxs-lookup"><span data-stu-id="45fb6-132">Up to 10 million customer profile per export to Facebook Ads Manager</span></span> 
- <span data-ttu-id="45fb6-133">Facebook 광고 관리자에게 내보내기는 세그먼트로 제한</span><span class="sxs-lookup"><span data-stu-id="45fb6-133">Export to Facebook Ads Manager is limited to segments</span></span>
- <span data-ttu-id="45fb6-134">총 1,000만 개의 프로필이 있는 세그먼트 내보내기를 완료하는 데 최대 90분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45fb6-134">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="45fb6-135">데이터 프라이버시 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="45fb6-135">Data privacy and compliance</span></span>

<span data-ttu-id="45fb6-136">Dynamics 365 Customer Insights를 사용하여 Facebook 광고 관리자로 데이터를 전송하는 경우 Dynamics 365 Customer Insights 규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45fb6-136">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="45fb6-137">Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 Facebook 광고가 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45fb6-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="45fb6-138">자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45fb6-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="45fb6-139">Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45fb6-139">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]