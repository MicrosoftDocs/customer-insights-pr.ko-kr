---
title: Mailchimp 광고로 Customer Insights 데이터 내보내기
description: 연결을 구성하고 Mailchimp로 내보내는 방법을 알아봅니다.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 35848998e738c7ecc1642f2b75912ff78d85f79e
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976163"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a><span data-ttu-id="b7ae3-103">Mailchimp로 세그먼트 목록 내보내기(프리뷰)</span><span class="sxs-lookup"><span data-stu-id="b7ae3-103">Export segment lists to Mailchimp (preview)</span></span>

<span data-ttu-id="b7ae3-104">통합 고객 프로필의 세그먼트를 Mailchimp로 내보내 뉴스레터 및 이메일 캠페인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="b7ae3-105">연결을 위한 전제 조건</span><span class="sxs-lookup"><span data-stu-id="b7ae3-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="b7ae3-106">[Mailchimp 계정](https://mailchimp.com/) 및 해당 관리자 자격 증명이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b7ae3-107">Mailchimp에 기존 대상 그룹과 해당 ID가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="b7ae3-108">자세한 내용은 [Mailchimp 대상 그룹](https://mailchimp.com/help/create-audience/)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="b7ae3-109">[구성된 세그먼트](segments.md)가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="b7ae3-110">내보낸 세그먼트의 통합 고객 프로필에는 이메일 주소를 나타내는 필드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b7ae3-111">알려진 제한 사항</span><span class="sxs-lookup"><span data-stu-id="b7ae3-111">Known limitations</span></span>

- <span data-ttu-id="b7ae3-112">Mailchimp로 내보낼 때마다 프로필이 최대 100만 개입니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="b7ae3-113">Mailchimp로 내보내기는 세그먼트로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="b7ae3-114">1백만 개의 프로필이 있는 세그먼트를 내보내려면 최대 3시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="b7ae3-115">Mailchimp로 내보낼 수 있는 프로필 수는 Mailchimp와의 계약에 따라 다르며 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="b7ae3-116">Mailchimp 연결 설정</span><span class="sxs-lookup"><span data-stu-id="b7ae3-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="b7ae3-117">**관리자** > **연결** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b7ae3-118">**연결 추가** 와 **Autopilot** 을 선택하여 연결을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="b7ae3-119">**표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b7ae3-120">이름 및 연결 유형은 이 연결을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b7ae3-121">이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b7ae3-122">이 연결을 사용할 수 있는 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-122">Choose who can use this connection.</span></span> <span data-ttu-id="b7ae3-123">아무 조치도 취하지 않으면 기본값은 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b7ae3-124">자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b7ae3-125">**동의** 를 선택해 **데이터 프라이버시 및 규정 준수** 를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b7ae3-126">**연결** 을 선택하여 Mailchimp에 대한 연결을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="b7ae3-127">**Mailchimp로 인증** 을 선택하고 Mailchimp 자격 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="b7ae3-128">**내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="b7ae3-129">연결을 완료하려면 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="b7ae3-130">커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="b7ae3-130">Configure the connector</span></span>

<span data-ttu-id="b7ae3-131">이 유형의 연결에 대한 액세스 권한이 있는 경우 이 내보내기를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b7ae3-132">자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b7ae3-133">**데이터**> **내보내기** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="b7ae3-134">**대상 추가** 를 선택하여 새 내보내기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b7ae3-135">**내보내기 연결** 필드의 Mailchimp 섹션에서 연결을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="b7ae3-136">이 섹션 이름이 표시되지 않으면 사용 가능한 이 유형의 연결이 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b7ae3-137">**[Mailchimp 대상 그룹 ID](https://mailchimp.com/help/find-audience-id/)** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="b7ae3-138">**데이터 일치** 섹션의 이메일 필드에서 고객의 **이메일** 주소를 나타내는 통합 고객 프로필의 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="b7ae3-139">선택적으로 **이름** 과 **성** 을 내보내어 보다 개인화된 이메일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="b7ae3-140">**특성 추가** 를 선택하여 이러한 필드를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="b7ae3-141">내보낼 세그먼트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-141">Select the segments you want to export.</span></span> <span data-ttu-id="b7ae3-142">총 100만 개의 고객 프로필을 Mailchimp로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="b7ae3-143">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-143">Select **Save**.</span></span>

<span data-ttu-id="b7ae3-144">내보내기를 저장해도 내보내기가 즉시 실행되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b7ae3-145">내보내기는 모든 [예약된 새로 고침](system.md#schedule-tab)에 따라 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b7ae3-146">[주문형으로 데이터를 내보낼](export-destinations.md#run-exports-on-demand)수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b7ae3-147">데이터 프라이버시 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="b7ae3-147">Data privacy and compliance</span></span>

<span data-ttu-id="b7ae3-148">Dynamics 365 Customer Insights를 사용하여 Mailchimp로 데이터를 전송하는 경우 Dynamics 365 Customer Insights 규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b7ae3-149">Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 Mailchimp가 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b7ae3-150">자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b7ae3-151">Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7ae3-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
