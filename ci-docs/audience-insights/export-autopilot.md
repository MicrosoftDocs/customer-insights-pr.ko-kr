---
title: Autopilot로 Customer Insights 데이터 내보내기
description: 연결을 구성하고 Autopilot으로 내보내는 방법을 알아봅니다.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760151"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="91e5e-103">Autopilot으로 세그먼트 내보내기(프리뷰)</span><span class="sxs-lookup"><span data-stu-id="91e5e-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="91e5e-104">통합 고객 프로필의 세그먼트를 Autopilot으로 내보내고 Autopilot의 이메일 마케팅에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="91e5e-105">연결을 위한 전제 조건</span><span class="sxs-lookup"><span data-stu-id="91e5e-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="91e5e-106">[Autopilot 계정](https://www.autopilothq.com/) 및 해당 관리자 자격 증명이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="91e5e-107">대상 그룹 인사이트에 [구성된 세그먼트](segments.md)가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="91e5e-108">내보낸 세그먼트의 통합 고객 프로필에는 이메일 주소를 나타내는 필드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="91e5e-109">알려진 제한 사항</span><span class="sxs-lookup"><span data-stu-id="91e5e-109">Known limitations</span></span>

- <span data-ttu-id="91e5e-110">총 10만 개의 고객 프로필을 Autopilot로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="91e5e-111">Autopilot로 내보내기는 세그먼트로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="91e5e-112">최대 10만 개의 프로필을 Autopilot로 내보내는 데 최대 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="91e5e-113">Autopilot로 내보낼 수 있는 프로필 수는 Autopilot와의 계약에 따라 다르며 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="91e5e-114">Autopilot에 연결을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="91e5e-115">**관리자** > **연결** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="91e5e-116">**연결 추가** 와 **Autopilot** 을 선택하여 연결을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="91e5e-117">**표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="91e5e-118">이름 및 연결 유형은 이 연결을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="91e5e-119">이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="91e5e-120">이 연결을 사용할 수 있는 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-120">Choose who can use this connection.</span></span> <span data-ttu-id="91e5e-121">아무 조치도 취하지 않으면 기본값은 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="91e5e-122">자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="91e5e-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="91e5e-123">[Autopilot API 키](https://autopilot.docs.apiary.io/#)를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="91e5e-124">**동의** 를 선택해 **데이터 프라이버시 및 규정 준수** 를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="91e5e-125">**연결** 을 선택하여 Autopilot에 대한 연결을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="91e5e-126">**내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="91e5e-127">연결을 완료하려면 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="91e5e-128">내보내기 구성</span><span class="sxs-lookup"><span data-stu-id="91e5e-128">Configure an export</span></span>

<span data-ttu-id="91e5e-129">이 유형의 연결에 대한 액세스 권한이 있는 경우 이 내보내기를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="91e5e-130">자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="91e5e-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="91e5e-131">**데이터** > **내보내기** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="91e5e-132">**대상 추가** 를 선택하여 새 내보내기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="91e5e-133">**내보내기 연결** 필드의 Autopilot 섹션에서 연결을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="91e5e-134">이 섹션 이름이 표시되지 않으면 사용 가능한 이 유형의 연결이 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="91e5e-135">**데이터 일치** 섹션의 이메일 필드에서 고객의 **이메일** 주소를 나타내는 통합 고객 프로필의 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="91e5e-136">**이름**, **성** 과 같은 다른 선택 사항 필드에 대해 동일한 단계를 반복하십시오.</span><span class="sxs-lookup"><span data-stu-id="91e5e-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="91e5e-137">내보낼 세그먼트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-137">Select the segments you want to export.</span></span> <span data-ttu-id="91e5e-138">Autopilot로 **총 10만 개 이상의 고객 프로필은 내보내지 않을 것을 강력히 권고합니다**.</span><span class="sxs-lookup"><span data-stu-id="91e5e-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="91e5e-139">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-139">Select **Save**.</span></span>

<span data-ttu-id="91e5e-140">내보내기를 저장해도 내보내기가 즉시 실행되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="91e5e-141">내보내기는 모든 [예약된 새로 고침](system.md#schedule-tab)에 따라 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="91e5e-142">[주문형으로 데이터를 내보낼](export-destinations.md#run-exports-on-demand)수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="91e5e-143">데이터 프라이버시 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="91e5e-143">Data privacy and compliance</span></span>

<span data-ttu-id="91e5e-144">Dynamics 365 Customer Insights를 사용하여 Autopilot로 데이터를 전송하는 경우 Dynamics 365 Customer Insights 규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="91e5e-145">Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만, 귀하가 가질 수 있는 개인 정보 보호 또는 보안 의무를 Autopilot가 충족하도록 할 책임은 사용자에게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="91e5e-146">자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="91e5e-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="91e5e-147">Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91e5e-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]