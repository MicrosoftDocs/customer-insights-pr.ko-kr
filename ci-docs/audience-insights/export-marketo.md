---
title: Marketo로 Customer Insights 데이터 내보내기
description: Marketo 연결을 구성하는 방법을 알아보세요.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e0245f2d01aabc86f43532822c056965ff7ae67a
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267089"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="c19ba-103">Marketo용 커넥터(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="c19ba-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="c19ba-104">통합 고객 프로필의 세그먼트를 내보내 캠페인을 생성하고 이메일 마케팅을 제공하며 Marketo에서 특정 고객 그룹을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c19ba-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c19ba-105">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="c19ba-105">Prerequisites</span></span>

-   <span data-ttu-id="c19ba-106">[Marketo 계정](https://login.marketo.com/) 및 해당 관리자 자격 증명이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c19ba-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c19ba-107">Marketo에 기존 목록과 해당 ID가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c19ba-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="c19ba-108">자세한 내용은 [Marketo 목록](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c19ba-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="c19ba-109">[구성된 세그먼트](segments.md)가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c19ba-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="c19ba-110">내보낸 세그먼트의 통합 고객 프로필에는 이메일 주소를 나타내는 필드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c19ba-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="c19ba-111">Marketo에 연결</span><span class="sxs-lookup"><span data-stu-id="c19ba-111">Connect to Marketo</span></span>

1. <span data-ttu-id="c19ba-112">**관리자** > **내보내기 대상** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c19ba-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c19ba-113">**Marketo** 에서 **설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c19ba-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="c19ba-114">**표시 이름** 필드에서 내보내기 대상에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c19ba-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="c19ba-115">**[Marketo 클라이언트 ID, 클라이언트 암호 및 REST 엔드포인트 호스트 이름](https://developers.marketo.com/rest-api/authentication/)** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c19ba-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="c19ba-116">**[Marketo 목록 ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c19ba-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="c19ba-117">**데이터 개인 정보 보호 및 준수** 를 확인하려면 **동의함** 을 선택하고 Marketo에 대한 연결을 초기화하려면 **연결** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c19ba-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="c19ba-118">**내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c19ba-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Marketo 연결에 대한 스크린샷 내보내기":::

1. <span data-ttu-id="c19ba-120">**다음** 을 선택해 내보내기를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c19ba-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="c19ba-121">커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="c19ba-121">Configure the connector</span></span>

1. <span data-ttu-id="c19ba-122">**데이터 일치** 섹션의 이메일 필드에서 고객의 **이메일** 주소를 나타내는 통합 고객 프로필의 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c19ba-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="c19ba-123">선택적으로 **이름**, **성**, **도시**, **주** 및 **국가/지역** 을 추가 필드로 내보내 더 개인화된 이메일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c19ba-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="c19ba-124">**특성 추가** 를 선택하여 이러한 필드를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="c19ba-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="c19ba-125">내보낼 세그먼트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c19ba-125">Select the segments you want to export.</span></span> <span data-ttu-id="c19ba-126">총 100만 개의 고객 프로필을 Marketo로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c19ba-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Marketo로 내보낼 필드 및 세그먼트 선택":::

1. <span data-ttu-id="c19ba-128">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c19ba-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c19ba-129">데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="c19ba-129">Export the data</span></span>

<span data-ttu-id="c19ba-130">[주문 시 데이터를 내보낼](export-destinations.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c19ba-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="c19ba-131">내보내기는 [예약된 새로 고침](system.md#schedule-tab)마다 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c19ba-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c19ba-132">Marketo에서 이제 [Marketo 목록](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)에 있는 세그먼트를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c19ba-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c19ba-133">알려진 제한 사항</span><span class="sxs-lookup"><span data-stu-id="c19ba-133">Known limitations</span></span>

- <span data-ttu-id="c19ba-134">Marketo로 내보낼 때마다 프로필이 최대 100만 개입니다.</span><span class="sxs-lookup"><span data-stu-id="c19ba-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="c19ba-135">Marketo로 내보내기는 세그먼트로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="c19ba-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="c19ba-136">총 100만 개의 프로필이 있는 세그먼트를 내보내려면 최대 3시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c19ba-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="c19ba-137">Marketo로 내보낼 수 있는 프로필 수는 Marketo와의 계약에 따라 다르며 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="c19ba-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c19ba-138">데이터 프라이버시 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="c19ba-138">Data privacy and compliance</span></span>

<span data-ttu-id="c19ba-139">Dynamics 365 Customer Insights를 사용하여 Marketo로 데이터를 전송하는 경우 Dynamics 365 Customer Insights규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c19ba-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c19ba-140">Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 Marketo가 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c19ba-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c19ba-141">자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c19ba-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c19ba-142">Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c19ba-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]