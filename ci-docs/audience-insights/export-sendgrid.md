---
title: SendGrid로 Customer Insights 데이터 내보내기
description: SendGrid에 연결을 구성하는 방법을 알아보세요.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597289"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="b946e-103">SendGrid용 커넥터(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="b946e-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="b946e-104">통합 고객 프로필의 세그먼트를 SendGrid 연락처 목록으로 내보내고 SendGrid의 캠페인 및 이메일 마케팅에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b946e-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="b946e-105">필요한 항목</span><span class="sxs-lookup"><span data-stu-id="b946e-105">Prerequisites</span></span>

-   <span data-ttu-id="b946e-106">[SendGrid 계정](https://sendgrid.com/) 및 해당 관리자 자격 증명이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b946e-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b946e-107">SendGrid에 기존 연락처 목록과 해당 ID가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b946e-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="b946e-108">자세한 내용은 [SendGrid - 연락처 관리](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b946e-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="b946e-109">대상 그룹 인사이트에 [구성된 세그먼트](segments.md)가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b946e-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="b946e-110">내보낸 세그먼트의 통합 고객 프로필에는 이메일 주소를 나타내는 필드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b946e-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="b946e-111">SendGrid에 연결</span><span class="sxs-lookup"><span data-stu-id="b946e-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="b946e-112">**관리자** > **내보내기 대상** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b946e-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b946e-113">**SendGrid** 에서 **설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b946e-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="b946e-114">**표시 이름** 필드에서 내보내기 대상에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b946e-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="SendGrid 내보내기 구성 창입니다.":::

1. <span data-ttu-id="b946e-116">**SendGrid API 키** [SendGrid API 키](https://sendgrid.com/docs/ui/account-and-settings/api-keys/)를 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="b946e-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="b946e-117">**[SendGrid 목록 ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b946e-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="b946e-118">**동의** 를 선택해 **데이터 프라이버시 및 규정 준수** 를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b946e-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b946e-119">**연결** 을 선택하여 SendGrid에 대한 연결을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="b946e-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="b946e-120">**내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b946e-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="b946e-121">**다음** 을 선택해 내보내기를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b946e-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="b946e-122">커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="b946e-122">Configure the connector</span></span>

1. <span data-ttu-id="b946e-123">**데이터 일치** 섹션의 이메일 필드에서 고객의 **이메일** 주소를 나타내는 통합 고객 프로필의 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b946e-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="b946e-124">**이름**, **성**, **국가/지역**, **주**, **도시** 및 **우편 번호** 와 같은 다른 선택 사항 필드에 대해 동일한 단계를 반복하십시오.</span><span class="sxs-lookup"><span data-stu-id="b946e-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="b946e-125">내보낼 세그먼트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b946e-125">Select the segments you want to export.</span></span> <span data-ttu-id="b946e-126">SendGrid로 **총 10만 개 이상의 고객 프로필은 내보내지 않을 것을 강력히 권고합니다**.</span><span class="sxs-lookup"><span data-stu-id="b946e-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="b946e-127">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b946e-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="b946e-128">데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="b946e-128">Export the data</span></span>

<span data-ttu-id="b946e-129">[주문 시 데이터를 내보낼](export-destinations.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b946e-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="b946e-130">내보내기는 [예약된 새로 고침](system.md#schedule-tab)마다 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b946e-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b946e-131">알려진 제한 사항</span><span class="sxs-lookup"><span data-stu-id="b946e-131">Known limitations</span></span>

- <span data-ttu-id="b946e-132">SendGrid에 최대 10만 개의 프로필.</span><span class="sxs-lookup"><span data-stu-id="b946e-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="b946e-133">SendGrid로 내보내기는 세그먼트로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="b946e-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="b946e-134">최대 10만 개의 프로필을 SendGrid로 내보내는 데 최대 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b946e-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="b946e-135">SendGrid로 내보낼 수 있는 프로필 수는 SendGrid와의 계약에 따라 다르며 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="b946e-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b946e-136">데이터 프라이버시 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="b946e-136">Data privacy and compliance</span></span>

<span data-ttu-id="b946e-137">Dynamics 365 Customer Insights를 사용하여 SendGrid로 데이터를 전송하는 경우 Dynamics 365 Customer Insights규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b946e-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b946e-138">Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만, 귀하가 가질 수 있는 개인 정보 보호 또는 보안 의무를 SendGrid가 충족하도록 할 책임은 사용자에게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b946e-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="b946e-139">자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b946e-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b946e-140">Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b946e-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]