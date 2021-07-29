---
title: AdRoll로 Customer Insights 데이터 내보내기
description: 연결을 구성하고 AdRoll로 내보내는 방법을 알아봅니다.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 67bfa23d56b26ae592efa4d7197713664bb02623
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304841"
---
# <a name="export-segments-to-adroll-preview"></a><span data-ttu-id="22c7d-103">AdRoll로 세그먼트 내보내기(프리뷰)</span><span class="sxs-lookup"><span data-stu-id="22c7d-103">Export segments to AdRoll (preview)</span></span>

<span data-ttu-id="22c7d-104">통합 고객 프로필의 세그먼트를 AdRoll로 내보내고 광고에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="22c7d-105">연결을 위한 전제 조건</span><span class="sxs-lookup"><span data-stu-id="22c7d-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="22c7d-106">[AdRoll 거래처](https://www.adroll.com/) 및 해당 관리자 자격 증명이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="22c7d-107">대상 그룹 인사이트에 [구성된 세그먼트](segments.md)가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="22c7d-108">내보낸 세그먼트의 통합 고객 프로필에는 이메일 주소를 나타내는 필드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="22c7d-109">알려진 제한 사항</span><span class="sxs-lookup"><span data-stu-id="22c7d-109">Known limitations</span></span>

- <span data-ttu-id="22c7d-110">AdRoll에 한 번에 최대 250,000개의 프로필을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-110">You can export up to 250,000 profiles at a time to AdRoll.</span></span>
- <span data-ttu-id="22c7d-111">프로필이 100개 미만인 세그먼트는 AdRoll로 내보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="22c7d-112">AdRoll로 내보내기는 세그먼트로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="22c7d-113">최대 250,000개의 프로필을 AdRoll로 내보내는 데 최대 10분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-113">Exporting up to 250,000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="22c7d-114">AdRoll로 내보낼 수 있는 프로필 수는 AdRoll과의 계약에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-114">The number of profiles that you can export to AdRoll is dependent on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="22c7d-115">AdRoll에 연결을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="22c7d-116">**관리자** > **연결** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="22c7d-117">**연결 추가** 와 **AdRoll** 을 선택하여 연결을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="22c7d-118">**표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="22c7d-119">이름 및 연결 유형은 이 연결을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="22c7d-120">이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="22c7d-121">이 연결을 사용할 수 있는 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-121">Choose who can use this connection.</span></span> <span data-ttu-id="22c7d-122">아무 조치도 취하지 않으면 기본값은 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="22c7d-123">자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="22c7d-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="22c7d-124">**동의** 를 선택해 **데이터 프라이버시 및 규정 준수** 를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="22c7d-125">**연결** 을 선택하여 AdRoll에 대한 연결을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="22c7d-126">**AdRoll로 인증** 을 선택하고 AdRoll 관리자 자격 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="22c7d-127">**내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="22c7d-128">연결을 완료하려면 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="22c7d-129">내보내기 구성</span><span class="sxs-lookup"><span data-stu-id="22c7d-129">Configure an export</span></span>

<span data-ttu-id="22c7d-130">이 유형의 연결에 대한 액세스 권한이 있는 경우 이 내보내기를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="22c7d-131">자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="22c7d-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="22c7d-132">**데이터** > **내보내기** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="22c7d-133">**대상 추가** 를 선택하여 새 내보내기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="22c7d-134">**내보내기 연결** 필드의 AdRoll 섹션에서 연결을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="22c7d-135">이 섹션 이름이 표시되지 않으면 이 유형의 연결을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-135">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="22c7d-136">**AdRoll 광고주 ID** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-136">Enter your **AdRoll Advertiser ID**.</span></span> <span data-ttu-id="22c7d-137">자세한 내용은 [AdRoll 광고주 프로필](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles)을 참고하세요.</span><span class="sxs-lookup"><span data-stu-id="22c7d-137">For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="22c7d-138">**데이터 일치** 섹션의 이메일 필드에서 고객의 **이메일** 주소를 나타내는 통합 고객 프로필의 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="22c7d-139">세그먼트를 AdRoll로 내보내는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-139">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="22c7d-140">내보낼 세그먼트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-140">Select the segments you want to export.</span></span> <span data-ttu-id="22c7d-141">구성원이 100명 이상인 세그먼트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-141">Select a segment with a least 100 members.</span></span> <span data-ttu-id="22c7d-142">더 작은 세그먼트는 내보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-142">You can't export smaller segments.</span></span> <span data-ttu-id="22c7d-143">또한 내보낼 세그먼트의 최대 크기는 내보내기당 250,000명입니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-143">Additionally the maximum size of a segment to export is 250,000 members per export.</span></span> 

1. <span data-ttu-id="22c7d-144">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-144">Select **Save**.</span></span>

<span data-ttu-id="22c7d-145">내보내기를 저장해도 내보내기가 즉시 실행되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-145">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="22c7d-146">내보내기는 모든 [예약된 새로 고침](system.md#schedule-tab)에 따라 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-146">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="22c7d-147">[주문형으로 데이터를 내보낼](export-destinations.md#run-exports-on-demand)수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-147">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="22c7d-148">데이터 프라이버시 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="22c7d-148">Data privacy and compliance</span></span>

<span data-ttu-id="22c7d-149">Dynamics 365 Customer Insights를 사용하여 AdRoll로 데이터를 전송하는 경우 Dynamics 365 Customer Insights 규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-149">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="22c7d-150">Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 AdRoll가 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="22c7d-151">자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="22c7d-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="22c7d-152">Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22c7d-152">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>