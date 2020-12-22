---
title: Google 광고로 Customer Insights 데이터 내보내기
description: Google 광고 연결을 구성하는 방법을 알아보세요.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568466"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="71c4c-103">Google 광고용 커넥터(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="71c4c-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="71c4c-104">통합 고객 프로필의 세그먼트를 Google 광고 대상 그룹 목록으로 내보내고 이를 사용하여 Google 검색, Gmail, YouTube 및 Google 디스플레이 네트워크에서 광고합니다.</span><span class="sxs-lookup"><span data-stu-id="71c4c-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="71c4c-105">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="71c4c-105">Prerequisites</span></span>

-   <span data-ttu-id="71c4c-106">[Google 광고 계정](https://ads.google.com/) 및 해당 관리자 자격 증명이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c4c-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="71c4c-107">Google 광고에 기존 대상 그룹과 해당 ID가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c4c-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="71c4c-108">자세한 내용은 [Google 광고 대상 그룹](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="71c4c-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="71c4c-109">[구성된 세그먼트](segments.md)가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c4c-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="71c4c-110">내보낸 세그먼트의 통합 고객 프로필에는 이메일 주소, 이름 및 성을 나타내는 필드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c4c-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="71c4c-111">Google 광고에 연결</span><span class="sxs-lookup"><span data-stu-id="71c4c-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="71c4c-112">**관리자** > **내보내기 대상** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="71c4c-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="71c4c-113">**Google 광고** 에서 **설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="71c4c-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="71c4c-114">**표시 이름** 필드에서 내보내기 대상에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="71c4c-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="71c4c-115">**[Google 광고 고객 ID](https://support.google.com/google-ads/answer/1704344)** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="71c4c-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="71c4c-116">**[Google 광고에서 승인한 개발자 토큰](https://developers.google.com/google-ads/api/docs/first-call/dev-token)** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="71c4c-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="71c4c-117">**동의** 를 선택해 **데이터 프라이버시 및 규정 준수** 를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="71c4c-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="71c4c-118">**[Google 광고 대상 그룹 ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** 를 입력하고 **연결** 을 선택하여 Google 광고 연결을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="71c4c-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="71c4c-119">**Google 광고로 인증** 을 선택하고 Google 광고 자격 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="71c4c-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="71c4c-120">**내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="71c4c-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Google 광고 연결을 위한 스크린샷 내보내기":::

1. <span data-ttu-id="71c4c-122">**다음** 을 선택해 내보내기를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="71c4c-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="71c4c-123">커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="71c4c-123">Configure the connector</span></span>

1. <span data-ttu-id="71c4c-124">**데이터 일치** 섹션의 이메일 필드에서 고객의 **이메일** 주소를 나타내는 통합 고객 프로필의 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="71c4c-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="71c4c-125">**이름** 및 **성** 필드에 동일한 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="71c4c-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="71c4c-126">내보낼 세그먼트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="71c4c-126">Select the segments you want to export.</span></span> <span data-ttu-id="71c4c-127">총 100만 개의 고객 프로필을 Google 광고로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c4c-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="71c4c-128">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="71c4c-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="71c4c-129">데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="71c4c-129">Export the data</span></span>

<span data-ttu-id="71c4c-130">[주문 시 데이터를 내보낼](export-destinations.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c4c-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="71c4c-131">내보내기는 [예약된 새로 고침](system.md#schedule-tab)마다 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c4c-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="71c4c-132">이제 Google 광고에서 [Google 광고 대상 그룹](https://support.google.com/google-ads/answer/7558048?hl=en/) 아래에서 세그먼트를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c4c-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="71c4c-133">알려진 제한 사항</span><span class="sxs-lookup"><span data-stu-id="71c4c-133">Known limitations</span></span>

- <span data-ttu-id="71c4c-134">Google 광고로 내보낼 때마다 프로필이 최대 100만 개입니다.</span><span class="sxs-lookup"><span data-stu-id="71c4c-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="71c4c-135">Google 광고로 내보내기는 세그먼트로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c4c-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="71c4c-136">총 100만 개의 프로필이 있는 세그먼트를 내보내는 것은 공급자측의 제한으로 인해 최대 5분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c4c-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="71c4c-137">Google 광고에서 일치하는 데 최대 48시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c4c-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="71c4c-138">데이터 프라이버시 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="71c4c-138">Data privacy and compliance</span></span>

<span data-ttu-id="71c4c-139">Dynamics 365 Customer Insights를 사용하여 Google 광고로 데이터를 전송하는 경우 Dynamics 365 Customer Insights 규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c4c-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="71c4c-140">Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 Google 광고가 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c4c-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="71c4c-141">자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="71c4c-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="71c4c-142">Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c4c-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
