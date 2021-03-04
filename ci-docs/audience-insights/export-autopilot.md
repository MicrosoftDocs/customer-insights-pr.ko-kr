---
title: Autopilot로 Customer Insights 데이터 내보내기
description: Autopilot 연결을 구성하는 방법을 알아보세요.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269246"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="50045-103">Autopilot용 커넥터(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="50045-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="50045-104">통합 고객 프로필의 세그먼트를 Autopilot으로 내보내고 Autopilot의 이메일 마케팅에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="50045-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="50045-105">필요한 항목</span><span class="sxs-lookup"><span data-stu-id="50045-105">Prerequisites</span></span>

-   <span data-ttu-id="50045-106">[Autopilot 계정](https://www.autopilothq.com/) 및 해당 관리자 자격 증명이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50045-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="50045-107">대상 그룹 인사이트에 [구성된 세그먼트](segments.md)가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50045-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="50045-108">내보낸 세그먼트의 통합 고객 프로필에는 이메일 주소를 나타내는 필드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="50045-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="50045-109">AutoPilot에 연결</span><span class="sxs-lookup"><span data-stu-id="50045-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="50045-110">**관리자** > **내보내기 대상** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="50045-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="50045-111">**Autopilot** 에서 **설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="50045-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="50045-112">**표시 이름** 필드에서 내보내기 대상에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="50045-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Autopilot 연결을 위한 구성 창입니다.":::

1. <span data-ttu-id="50045-114">**Autopilot API 키** [Autopilot API 키](https://autopilot.docs.apiary.io/#)를 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="50045-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="50045-115">**동의** 를 선택해 **데이터 프라이버시 및 규정 준수** 를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="50045-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="50045-116">**연결** 을 선택하여 Autopilot에 대한 연결을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="50045-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="50045-117">**내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="50045-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="50045-118">**다음** 을 선택해 내보내기를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="50045-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="50045-119">커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="50045-119">Configure the connector</span></span>

1. <span data-ttu-id="50045-120">**데이터 일치** 섹션의 이메일 필드에서 고객의 **이메일** 주소를 나타내는 통합 고객 프로필의 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="50045-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="50045-121">**이름**, **성** 과 같은 다른 선택 사항 필드에 대해 동일한 단계를 반복하십시오.</span><span class="sxs-lookup"><span data-stu-id="50045-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="50045-122">내보낼 세그먼트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="50045-122">Select the segments you want to export.</span></span> <span data-ttu-id="50045-123">Autopilot로 **총 10만 개 이상의 고객 프로필은 내보내지 않을 것을 강력히 권고합니다**.</span><span class="sxs-lookup"><span data-stu-id="50045-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="50045-124">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="50045-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="50045-125">데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="50045-125">Export the data</span></span>

<span data-ttu-id="50045-126">[주문 시 데이터를 내보낼](export-destinations.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50045-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="50045-127">내보내기는 [예약된 새로 고침](system.md#schedule-tab)마다 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="50045-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="50045-128">알려진 제한 사항</span><span class="sxs-lookup"><span data-stu-id="50045-128">Known limitations</span></span>

- <span data-ttu-id="50045-129">총 10만 개의 고객 프로필을 Autopilot로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50045-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="50045-130">Autopilot로 내보내기는 세그먼트로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="50045-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="50045-131">최대 10만 개의 프로필을 Autopilot로 내보내는 데 최대 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50045-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="50045-132">Autopilot로 내보낼 수 있는 프로필 수는 Autopilot와의 계약에 따라 다르며 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="50045-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="50045-133">데이터 프라이버시 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="50045-133">Data privacy and compliance</span></span>

<span data-ttu-id="50045-134">Dynamics 365 Customer Insights를 사용하여 Autopilot로 데이터를 전송하는 경우 Dynamics 365 Customer Insights 규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50045-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="50045-135">Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만, 귀하가 가질 수 있는 개인 정보 보호 또는 보안 의무를 Autopilot가 충족하도록 할 책임은 사용자에게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50045-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="50045-136">자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50045-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="50045-137">Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50045-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]