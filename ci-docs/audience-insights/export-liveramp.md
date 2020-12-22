---
title: LiveRamp 커넥터
description: LiveRamp에 데이터를 내보내는 방법을 알아봅니다.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 86aa8c66a47ee61741082c95f05d2e5ce3f06f35
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667192"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="39331-103">LiveRamp&reg; 커넥터 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="39331-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="39331-104">LiveRamp에서 데이터를 활성화하여 디지털, 소셜 및 TV 에코시스템에서 500개 이상의 플랫폼에 연결하십시오.</span><span class="sxs-lookup"><span data-stu-id="39331-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="39331-105">LiveRamp의 데이터를 사용하여 광고 캠페인의 대상을 설정하고, 숨기고, 개인 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="39331-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="39331-106">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="39331-106">Prerequisites</span></span>

- <span data-ttu-id="39331-107">이 커넥터를 사용하려면 LiveRamp 구독이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="39331-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="39331-108">구독을 얻으려면 직접 [LiveRamp에 문의](https://liveramp.com/contact/)하십시오.</span><span class="sxs-lookup"><span data-stu-id="39331-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="39331-109">[LiveRamp 온보딩에 대해 자세히 알아보십시오](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="39331-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="39331-110">LiveRamp에 연결</span><span class="sxs-lookup"><span data-stu-id="39331-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="39331-111">대상 그룹 인사이트에서 **데이터** > **내보내기 대상** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="39331-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="39331-112">**LiveRamp** 타일에서 **설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39331-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="39331-113">**표시 이름** 필드에서 대상에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="39331-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="39331-114">SFTP(LiveRamp Secure FTP) 계정에 대한 **사용자 이름** 과 **암호** 를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="39331-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="39331-115">이 자격 증명은 LiveRamp 온보딩 자격 증명과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39331-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="39331-116">**확인** 을 선택해 LiveRamp 연결을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="39331-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="39331-117">성공으로 확인한 후에 **동의함** 확인란을 선택하여 **데이터 개인 정보 및 규정 준수** 에 대한 동의를 제공하십시오.</span><span class="sxs-lookup"><span data-stu-id="39331-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="39331-118">**다음** 을 선택해 LiveRamp 커넥터를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="39331-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="39331-119">커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="39331-119">Configure the connector</span></span>

1. <span data-ttu-id="39331-120">**키 식별자 선택** 필드에서 **이메일**, **이름 및 주소** 또는 **전화** 를 선택해 신원 확인을 위해 LiveRamp로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="39331-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="39331-121">선택한 키 식별자에 대해 통합 고객 엔터티의 해당 특성을 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="39331-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="39331-122">**특성 추가** 를 선택해 LiveRamp에 보낼 추가 특성을 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="39331-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="39331-123">더 많은 주요 식별자 특성을 LiveRamp로 보내면 더 높은 일치율을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39331-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="39331-124">LiveRamp로 내보내려는 세그먼트를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="39331-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="39331-125">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39331-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="39331-126">![특성 매핑이 있는 LiveRamp 커넥터](media/export-liveramp-segments.png "특성 매핑이 있는 LiveRamp 커넥터")</span><span class="sxs-lookup"><span data-stu-id="39331-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="39331-127">데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="39331-127">Export the data</span></span>

<span data-ttu-id="39331-128">내보내기를 위한 모든 전제 조건이 완료되면 곧 내보내기가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="39331-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="39331-129">내보내기는 [예약된 새로 고침](system.md#schedule-tab)마다 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="39331-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="39331-130">내보내기가 성공적으로 완료되면 LiveRamp 온보딩에 로그인하여 데이터를 활성화하고 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39331-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="39331-131">데이터 프라이버시 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="39331-131">Data privacy and compliance</span></span>

<span data-ttu-id="39331-132">Dynamics 365 Customer Insights를 사용하여 Liveramp로 데이터를 전송하는 경우 Dynamics 365 Customer Insights규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39331-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="39331-133">Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 Liveramp가 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39331-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="39331-134">자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39331-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="39331-135">Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39331-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>