---
title: Google 광고로 Customer Insights 데이터 내보내기
description: 연결을 구성하고 Google Ads로 내보내는 방법을 알아봅니다.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f4c094e486577d00d8c0c64e8527829820b335f6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759701"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="59280-103">Google Ads로 세그먼트 내보내기(프리뷰)</span><span class="sxs-lookup"><span data-stu-id="59280-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="59280-104">통합 고객 프로필의 세그먼트를 Google 광고 대상 그룹 목록으로 내보내고 이를 사용하여 Google 검색, Gmail, YouTube 및 Google 디스플레이 네트워크에서 광고합니다.</span><span class="sxs-lookup"><span data-stu-id="59280-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="59280-105">연결을 위한 전제 조건</span><span class="sxs-lookup"><span data-stu-id="59280-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="59280-106">[Google 광고 계정](https://ads.google.com/) 및 해당 관리자 자격 증명이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59280-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="59280-107">[승인된 Google Ads 개발자 토큰](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span><span class="sxs-lookup"><span data-stu-id="59280-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="59280-108">[고객 일치 정책](https://support.google.com/adspolicy/answer/6299717) 요구 사항 충족</span><span class="sxs-lookup"><span data-stu-id="59280-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="59280-109">[리마케팅 목록 크기](https://support.google.com/google-ads/answer/7558048) 요구 사항 충족</span><span class="sxs-lookup"><span data-stu-id="59280-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="59280-110">Google 광고에 기존 대상 그룹과 해당 ID가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59280-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="59280-111">자세한 내용은 [Google 광고 대상 그룹](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="59280-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="59280-112">[구성된 세그먼트](segments.md)가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59280-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="59280-113">내보낸 세그먼트의 통합 고객 프로필에는 이메일 주소, 이름 및 성을 나타내는 필드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="59280-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="59280-114">알려진 제한 사항</span><span class="sxs-lookup"><span data-stu-id="59280-114">Known limitations</span></span>

- <span data-ttu-id="59280-115">Google 광고로 내보낼 때마다 프로필이 최대 100만 개입니다.</span><span class="sxs-lookup"><span data-stu-id="59280-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="59280-116">Google 광고로 내보내기는 세그먼트로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="59280-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="59280-117">총 100만 개의 프로필이 있는 세그먼트를 내보내는 것은 공급자측의 제한으로 인해 최대 5분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59280-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="59280-118">Google 광고에서 일치하는 데 최대 48시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59280-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="59280-119">Google Ads 연결 설정</span><span class="sxs-lookup"><span data-stu-id="59280-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="59280-120">**관리자** > **연결** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="59280-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="59280-121">**연결 추가** 와 **Google Ads** 를 선택하여 연결을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="59280-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="59280-122">**표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="59280-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="59280-123">이름 및 연결 유형은 이 연결을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="59280-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="59280-124">이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="59280-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="59280-125">이 연결을 사용할 수 있는 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="59280-125">Choose who can use this connection.</span></span> <span data-ttu-id="59280-126">아무 조치도 취하지 않으면 기본값은 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="59280-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="59280-127">자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="59280-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="59280-128">**[Google 광고 고객 ID](https://support.google.com/google-ads/answer/1704344)** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="59280-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="59280-129">**[Google 광고에서 승인한 개발자 토큰](https://developers.google.com/google-ads/api/docs/first-call/dev-token)** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="59280-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="59280-130">**동의** 를 선택해 **데이터 프라이버시 및 규정 준수** 를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="59280-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="59280-131">**Google 광고로 인증** 을 선택하고 Google 광고 자격 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="59280-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="59280-132">**내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="59280-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="59280-133">연결을 완료하려면 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="59280-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="59280-134">내보내기 구성</span><span class="sxs-lookup"><span data-stu-id="59280-134">Configure an export</span></span>

<span data-ttu-id="59280-135">이 유형의 연결에 대한 액세스 권한이 있는 경우 이 내보내기를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59280-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="59280-136">자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="59280-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="59280-137">**데이터** > **내보내기** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="59280-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="59280-138">**대상 추가** 를 선택하여 새 내보내기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="59280-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="59280-139">**내보내기 연결** 필드의 Google Ads 섹션에서 연결을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="59280-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="59280-140">이 섹션 이름이 표시되지 않으면 사용 가능한 이 유형의 연결이 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="59280-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="59280-141">**[Google 광고 대상 그룹 ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** 를 입력하고 **연결** 을 선택하여 Google 광고 연결을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="59280-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="59280-142">**데이터 일치** 섹션의 이메일 필드에서 고객의 **이메일** 주소를 나타내는 통합 고객 프로필의 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="59280-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="59280-143">**이름** 및 **성** 필드에 동일한 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="59280-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="59280-144">내보낼 세그먼트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="59280-144">Select the segments you want to export.</span></span> <span data-ttu-id="59280-145">총 100만 개의 고객 프로필을 Google 광고로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59280-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="59280-146">내보내기를 저장해도 내보내기가 즉시 실행되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59280-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="59280-147">내보내기는 모든 [예약된 새로 고침](system.md#schedule-tab)에 따라 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="59280-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="59280-148">[주문형으로 데이터를 내보낼](export-destinations.md#run-exports-on-demand)수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59280-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="59280-149">데이터 프라이버시 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="59280-149">Data privacy and compliance</span></span>

<span data-ttu-id="59280-150">Dynamics 365 Customer Insights를 사용하여 Google 광고로 데이터를 전송하는 경우 Dynamics 365 Customer Insights 규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59280-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="59280-151">Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 Google 광고가 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59280-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="59280-152">자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="59280-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="59280-153">Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59280-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
