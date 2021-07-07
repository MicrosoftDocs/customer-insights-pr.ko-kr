---
title: Facebook Ads Manager로 Customer Insights 데이터 내보내기
description: 연결을 구성하고 Facebook 광고 관리자로 내보내는 방법을 알아봅니다.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e20c7b7fd3989d7621cb7765f38b85c8ab4adfcb
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305118"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="52457-103">Facebook 광고 관리자로 세그먼트 목록 내보내기(프리뷰)</span><span class="sxs-lookup"><span data-stu-id="52457-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="52457-104">통합 고객 프로필 세그먼트를 Facebook 광고 관리자에 내보내 Facebook 및 Instagram에서 캠페인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="52457-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="52457-105">연결을 위한 전제 조건</span><span class="sxs-lookup"><span data-stu-id="52457-105">Prerequisites for connection</span></span>

- <span data-ttu-id="52457-106">[**Facebook 비즈니스 계정**](https://business.facebook.com/)이 포함된 [**Facebook 광고 계정**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52457-106">You need to have a [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="52457-107">[**Facebook 광고 계정**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)의 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52457-107">You need to be an administrator on the [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="52457-108">알려진 제한 사항</span><span class="sxs-lookup"><span data-stu-id="52457-108">Known limitations</span></span>

- <span data-ttu-id="52457-109">Facebook 광고 관리자로 내보내기당 최대 1,000만 개의 고객 프로필을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52457-109">Up to 10 million customer profiles per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="52457-110">Facebook 광고 관리자에게 내보내기는 세그먼트로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="52457-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="52457-111">Facebook에서 *고객 목록* 유형의 사용자 지정 대상만 만들거나 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="52457-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="52457-112">총 1,000만 개의 프로필이 있는 세그먼트 내보내기를 완료하는 데 최대 90분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52457-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="52457-113">Facebook 광고 관리자 연결 설정</span><span class="sxs-lookup"><span data-stu-id="52457-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="52457-114">사용자가 내보내기를 생성하려면 관리자가 서비스에 대한 연결을 구성하고 기여자가 연결을 사용할 수 있도록 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52457-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="52457-115">**관리자** > **연결** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="52457-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="52457-116">**연결 추가** 와 **Facebook 광고 관리자** 를 선택하여 연결을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="52457-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="52457-117">**표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="52457-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="52457-118">이름 및 연결 유형은 이 연결을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="52457-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="52457-119">이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="52457-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="52457-120">이 연결을 사용할 수 있는 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52457-120">Choose who can use this connection.</span></span> <span data-ttu-id="52457-121">아무 조치도 취하지 않으면 기본값은 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="52457-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="52457-122">자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="52457-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="52457-123">Facebook 광고를 사용하여 인증:</span><span class="sxs-lookup"><span data-stu-id="52457-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="52457-124">**Facebook으로 계속** 을 선택하여 Facebook 광고 계정에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="52457-124">Select **Continue with Facebook** to sign in to your Facebook Ads account.</span></span>

   1. <span data-ttu-id="52457-125">Facebook으로 인증한 후 **ads_management** 권한을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="52457-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="52457-126">작업할 **Facebook 광고 계정** 을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="52457-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="52457-127">드롭다운 목록에서 **기존 사용자 지정 대상 그룹** 을 선택하거나 **새로운 사용자 지정 대상 그룹** 을 만드세요.</span><span class="sxs-lookup"><span data-stu-id="52457-127">Select an **Existing custom audience** from the dropdown list or create a **New custom audience**.</span></span> <span data-ttu-id="52457-128">자세한 내용은 [**Facebook 광고 관리자의 대상 그룹**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="52457-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="52457-129">이 내보내기로는 Facebook에서 *고객 목록* 유형의 사용자 지정 대상만 만들거나 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52457-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="52457-130">경우에 따라 드롭다운 목록에 다양한 유형의 사용자 지정 대상이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="52457-130">In some cases, you see custom audiences of different types in the dropdown list.</span></span> <span data-ttu-id="52457-131">*고객 목록* 이 아닌 다른 유형을 선택하면 내보내기에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="52457-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="52457-132">**데이터 개인 정보 보호 및 규정 준수** 를 검토하고 **동의함** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52457-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="52457-133">연결을 완료하려면 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52457-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="52457-134">내보내기 구성</span><span class="sxs-lookup"><span data-stu-id="52457-134">Configure an export</span></span>

<span data-ttu-id="52457-135">이 유형의 연결에 대한 액세스 권한이 있는 경우 이 내보내기를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52457-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="52457-136">자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52457-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="52457-137">**데이터** > **내보내기** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="52457-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="52457-138">**대상 추가** 를 선택하여 새 내보내기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="52457-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="52457-139">**내보내기 연결** 의 **Facebook 광고 관리자** 섹션에서 연결을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52457-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="52457-140">이 섹션 이름이 표시되지 않으면 이 유형의 연결을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="52457-140">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="52457-141">**키 식별자 필드 선택** 에서 **이메일**, **이름과 주소** 또는 **전화** 를 선택해 Facebook 광고 관리자에 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="52457-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="52457-142">**표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="52457-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="52457-143">선택한 키 식별자에 대해 통합 고객 엔터티의 해당 특성을 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="52457-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > [!TIP]
   > <span data-ttu-id="52457-144">**이메일** 을 키 식별자로 선택하면 가장 많이 일치하는 결과를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="52457-144">The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="52457-145">식별자를 추가하면 일치가 향상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52457-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="52457-146">**특성 추가** 를 선택하여 Facebook 광고 관리자에 보낼 더 많은 특성을 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="52457-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="52457-147">Facebook 광고 관리자의 특성은 다음과 같은 사용자 이름으로 매핑됩니다. **FN** = **이름**, **LN** = **성**, **FI** = **첫 이니셜**, **PHONE** = **전화**, **GEN** = **성별**, **DOB** = **생년월일**, **ST** = **주**, **CT** = **도시**, **ZIP** = **우편 번호**, **COUNTRY** = **국가/지역**</span><span class="sxs-lookup"><span data-stu-id="52457-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / ZIP Code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="52457-148">내보낼 세그먼트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52457-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="52457-149">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="52457-149">Select **Save**.</span></span>

<span data-ttu-id="52457-150">내보내기를 저장해도 내보내기가 즉시 실행되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52457-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="52457-151">내보내기는 모든 [예약된 새로 고침](system.md#schedule-tab)에 따라 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="52457-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="52457-152">[주문형으로 데이터를 내보낼](export-destinations.md#run-exports-on-demand)수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52457-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="52457-153">데이터 프라이버시 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="52457-153">Data privacy and compliance</span></span>

<span data-ttu-id="52457-154">Dynamics 365 Customer Insights를 사용하여 Facebook 광고 관리자로 데이터를 전송하는 경우 Dynamics 365 Customer Insights 규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52457-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="52457-155">Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 Facebook 광고가 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52457-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="52457-156">자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52457-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="52457-157">Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52457-157">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
