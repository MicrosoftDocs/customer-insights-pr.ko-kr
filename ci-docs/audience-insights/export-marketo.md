---
title: Marketo로 Customer Insights 데이터 내보내기
description: 연결을 구성하고 Marketo로 내보내는 방법을 알아봅니다.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5a644e286bd44d4ebf7d1837255326c005b48d6
ms.sourcegitcommit: 74cd4fa9cbb784d9dff174c0eec7b4dcb408d66b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059324"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="ebd3b-103">Marketo로 세그먼트 내보내기(프리뷰)</span><span class="sxs-lookup"><span data-stu-id="ebd3b-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="ebd3b-104">통합 고객 프로필의 세그먼트를 내보내 캠페인을 생성하고 이메일 마케팅을 제공하며 Marketo에서 특정 고객 그룹을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="ebd3b-105">연결을 위한 전제 조건</span><span class="sxs-lookup"><span data-stu-id="ebd3b-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="ebd3b-106">[Marketo 계정](https://login.marketo.com/) 및 해당 관리자 자격 증명이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ebd3b-107">Marketo에 기존 목록과 해당 ID가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="ebd3b-108">자세한 내용은 [Marketo 목록](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="ebd3b-109">[구성된 세그먼트](segments.md)가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="ebd3b-110">내보낸 세그먼트의 통합 고객 프로필에는 이메일 주소를 나타내는 필드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ebd3b-111">알려진 제한 사항</span><span class="sxs-lookup"><span data-stu-id="ebd3b-111">Known limitations</span></span>

- <span data-ttu-id="ebd3b-112">Marketo로 내보낼 때마다 프로필이 최대 100만 개입니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="ebd3b-113">Marketo로 내보내기는 세그먼트로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="ebd3b-114">총 100만 개의 프로필이 있는 세그먼트를 내보내려면 최대 3시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="ebd3b-115">Marketo로 내보낼 수 있는 프로필 수는 Marketo와의 계약에 따라 다르며 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="ebd3b-116">Marketo에 연결을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="ebd3b-117">**관리자** > **연결** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ebd3b-118">**연결 추가** 와 **Marketo** 를 선택하여 연결을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="ebd3b-119">**표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ebd3b-120">이름 및 연결 유형은 이 연결을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ebd3b-121">이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ebd3b-122">이 연결을 사용할 수 있는 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-122">Choose who can use this connection.</span></span> <span data-ttu-id="ebd3b-123">아무 조치도 취하지 않으면 기본값은 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ebd3b-124">자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ebd3b-125">**[Marketo 클라이언트 ID, 클라이언트 암호 및 REST 엔드포인트 호스트 이름](https://developers.marketo.com/rest-api/authentication/)** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span> <span data-ttu-id="ebd3b-126">REST 끝점 호스트 이름은 `https://`가 없는 호스트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-126">The REST Endpoint Hostname is the hostname only, without `https://`.</span></span> <span data-ttu-id="ebd3b-127">예: `xyz-abc-123.mktorest.com`</span><span class="sxs-lookup"><span data-stu-id="ebd3b-127">Example: `xyz-abc-123.mktorest.com`.</span></span> 

1. <span data-ttu-id="ebd3b-128">**데이터 개인 정보 보호 및 준수** 를 확인하려면 **동의함** 을 선택하고 Marketo에 대한 연결을 초기화하려면 **연결** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-128">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="ebd3b-129">**내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-129">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ebd3b-130">연결을 완료하려면 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-130">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ebd3b-131">내보내기 구성</span><span class="sxs-lookup"><span data-stu-id="ebd3b-131">Configure an export</span></span>

<span data-ttu-id="ebd3b-132">이 유형의 연결에 대한 액세스 권한이 있는 경우 이 내보내기를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-132">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ebd3b-133">자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-133">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ebd3b-134">**데이터** > **내보내기** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ebd3b-135">**대상 추가** 를 선택하여 새 내보내기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-135">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ebd3b-136">**내보내기 연결** 필드의 Marketo 섹션에서 연결을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-136">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="ebd3b-137">이 섹션 이름이 표시되지 않으면 사용 가능한 이 유형의 연결이 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-137">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ebd3b-138">**[Marketo 목록 ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-138">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span></span> <span data-ttu-id="ebd3b-139">목록 ID는 순수 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-139">The list ID is a purely numerical value.</span></span> <span data-ttu-id="ebd3b-140">예를 들어 Marketo 목록 ID가 ST12345A7인 경우 숫자 앞뒤의 문자를 제거하고 `12345`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-140">For example, if your Marketo list ID is ST12345A7, remove the character before and after the numerals and enter `12345`.</span></span> 

1. <span data-ttu-id="ebd3b-141">**데이터 일치** 섹션의 이메일 필드에서 고객의 **이메일** 주소를 나타내는 통합 고객 프로필의 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="ebd3b-142">선택적으로 **이름** 과 **성**, **도시**, **주**, **국가/지역** 을 내보내어 보다 개인화된 이메일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-142">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="ebd3b-143">**특성 추가** 를 선택하여 이러한 필드를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-143">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="ebd3b-144">내보낼 세그먼트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-144">Select the segments you want to export.</span></span> <span data-ttu-id="ebd3b-145">총 100만 개의 고객 프로필을 Marketo로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-145">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="ebd3b-146">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-146">Select **Save**.</span></span>

<span data-ttu-id="ebd3b-147">내보내기를 저장해도 내보내기가 즉시 실행되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-147">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ebd3b-148">내보내기는 모든 [예약된 새로 고침](system.md#schedule-tab)에 따라 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-148">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ebd3b-149">[주문형으로 데이터를 내보낼](export-destinations.md#run-exports-on-demand)수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-149">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="ebd3b-150">Marketo에서 이제 [Marketo 목록](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)에 있는 세그먼트를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-150">In Marketo, you can now find your segments under [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ebd3b-151">데이터 프라이버시 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="ebd3b-151">Data privacy and compliance</span></span>

<span data-ttu-id="ebd3b-152">Dynamics 365 Customer Insights를 사용하여 Marketo로 데이터를 전송하는 경우 Dynamics 365 Customer Insights규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-152">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ebd3b-153">Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 Marketo가 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-153">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ebd3b-154">자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-154">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ebd3b-155">Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-155">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
