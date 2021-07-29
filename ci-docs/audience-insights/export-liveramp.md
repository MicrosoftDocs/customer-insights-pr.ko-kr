---
title: LiveRamp 커넥터
description: 연결을 구성하고 LiveRamp로 내보내는 방법을 알아봅니다.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760335"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="2c495-103">LiveRamp로 세그먼트 내보내기&reg;(프리뷰)</span><span class="sxs-lookup"><span data-stu-id="2c495-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="2c495-104">LiveRamp에서 데이터를 활성화하여 디지털, 소셜 및 TV에서 500개 이상의 플랫폼과 연결하십시오.</span><span class="sxs-lookup"><span data-stu-id="2c495-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="2c495-105">LiveRamp의 데이터를 사용하여 광고 캠페인의 대상을 설정하고, 숨기고, 개인 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="2c495-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="2c495-106">연결을 위한 전제 조건</span><span class="sxs-lookup"><span data-stu-id="2c495-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="2c495-107">이 커넥터를 사용하려면 LiveRamp 구독이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2c495-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="2c495-108">구독을 얻으려면 직접 [LiveRamp에 문의](https://liveramp.com/contact/)하십시오.</span><span class="sxs-lookup"><span data-stu-id="2c495-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="2c495-109">[LiveRamp 온보딩에 대해 자세히 알아보십시오](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="2c495-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="2c495-110">LiveRamp 연결 설정</span><span class="sxs-lookup"><span data-stu-id="2c495-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="2c495-111">**관리자** > **연결** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2c495-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="2c495-112">**연결 추가** 와 **LiveRamp** 를 선택하여 연결을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2c495-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="2c495-113">**표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2c495-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="2c495-114">이름 및 연결 유형은 이 연결을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2c495-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="2c495-115">이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2c495-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="2c495-116">이 연결을 사용할 수 있는 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2c495-116">Choose who can use this connection.</span></span> <span data-ttu-id="2c495-117">아무 조치도 취하지 않으면 기본값은 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="2c495-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="2c495-118">자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2c495-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="2c495-119">SFTP(LiveRamp Secure FTP) 계정에 대한 **사용자 이름** 과 **암호** 를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2c495-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="2c495-120">이 자격 증명은 LiveRamp 온보딩 자격 증명과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c495-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="2c495-121">**확인** 을 선택해 LiveRamp 연결을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="2c495-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="2c495-122">성공으로 확인한 후에 **동의함** 확인란을 선택하여 **데이터 개인 정보 및 규정 준수** 에 대한 동의를 제공하십시오.</span><span class="sxs-lookup"><span data-stu-id="2c495-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="2c495-123">연결을 완료하려면 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2c495-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="2c495-124">내보내기 구성</span><span class="sxs-lookup"><span data-stu-id="2c495-124">Configure an export</span></span>

<span data-ttu-id="2c495-125">이 유형의 연결에 대한 액세스 권한이 있는 경우 이 내보내기를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c495-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="2c495-126">자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c495-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2c495-127">**데이터** > **내보내기** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2c495-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2c495-128">**대상 추가** 를 선택하여 새 내보내기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2c495-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="2c495-129">**내보내기 연결** 필드의 LiveRamp 섹션에서 연결을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2c495-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="2c495-130">이 섹션 이름이 표시되지 않으면 사용 가능한 이 유형의 연결이 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2c495-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="2c495-131">**키 식별자 선택** 필드에서 **이메일**, **이름 및 주소** 또는 **전화** 를 선택해 신원 확인을 위해 LiveRamp로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="2c495-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2c495-132">![특성 매핑이 있는 LiveRamp 커넥터](media/export-liveramp-segments.png "특성 매핑이 있는 LiveRamp 커넥터")</span><span class="sxs-lookup"><span data-stu-id="2c495-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="2c495-133">선택한 키 식별자에 대해 통합 고객 엔터티의 해당 특성을 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="2c495-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="2c495-134">**특성 추가** 를 선택하여 LiveRamp에 보낼 더 많은 특성을 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="2c495-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="2c495-135">더 많은 주요 식별자 특성을 LiveRamp로 보내면 더 높은 일치율을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c495-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="2c495-136">LiveRamp로 내보내려는 세그먼트를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="2c495-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="2c495-137">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2c495-137">Select **Save**.</span></span>

<span data-ttu-id="2c495-138">내보내기를 저장해도 내보내기가 즉시 실행되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c495-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="2c495-139">내보내기는 모든 [예약된 새로 고침](system.md#schedule-tab)에 따라 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c495-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2c495-140">[주문형으로 데이터를 내보낼](export-destinations.md#run-exports-on-demand)수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c495-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2c495-141">데이터 프라이버시 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="2c495-141">Data privacy and compliance</span></span>

<span data-ttu-id="2c495-142">Dynamics 365 Customer Insights를 사용하여 Liveramp로 데이터를 전송하는 경우 Dynamics 365 Customer Insights규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c495-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2c495-143">Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 Liveramp가 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c495-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="2c495-144">자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c495-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="2c495-145">Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c495-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]