---
title: DotDigital 광고로 Customer Insights 데이터 내보내기
description: 연결을 구성하고 DotDigital로 내보내는 방법을 알아봅니다.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8b0bda638c9bc7bb9cb2fdb01be11489b44f28a5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124419"
---
# <a name="export-segments-to-dotdigital-preview"></a><span data-ttu-id="76508-103">DotDigital로 세그먼트 내보내기(프리뷰)</span><span class="sxs-lookup"><span data-stu-id="76508-103">Export segments to DotDigital (preview)</span></span>

<span data-ttu-id="76508-104">통합 고객 프로필의 세그먼트를 DotDigital 주소록으로 내보내고 이를 캠페인, 이메일 마케팅에 사용하고 DotDigital로 고객 세그먼트를 구축합니다.</span><span class="sxs-lookup"><span data-stu-id="76508-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="76508-105">연결을 위한 전제 조건</span><span class="sxs-lookup"><span data-stu-id="76508-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="76508-106">[DotDigital 계정](https://dotdigital.com/) 및 해당 관리자 자격 증명이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76508-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="76508-107">DotDigital에 기존 주소록과 해당 ID가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76508-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="76508-108">ID는 주소록을 선택하여 열 때 URL에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76508-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="76508-109">자세한 내용은 [DotDigital 주소록](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76508-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="76508-110">대상 그룹 인사이트에 [구성된 세그먼트](segments.md)가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76508-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="76508-111">내보낸 세그먼트의 통합 고객 프로필에는 이메일 주소를 나타내는 필드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="76508-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="76508-112">알려진 제한 사항</span><span class="sxs-lookup"><span data-stu-id="76508-112">Known limitations</span></span>

- <span data-ttu-id="76508-113">DotDigital로 내보낼 때마다 프로필이 최대 100만 개입니다.</span><span class="sxs-lookup"><span data-stu-id="76508-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="76508-114">DotDigital로 내보내기는 세그먼트로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="76508-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="76508-115">총 100만 개의 프로필이 있는 세그먼트를 내보내는 것은 공급자측의 제한으로 인해 최대 3시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76508-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="76508-116">DotDigital로 내보낼 수 있는 프로필 수는 DotDigital와의 계약에 따라 다르며 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="76508-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="76508-117">DotDigital에 연결을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="76508-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="76508-118">**관리자** > **연결** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="76508-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="76508-119">**연결 추가** 와 **DotDigital** 을 선택하여 연결을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="76508-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="76508-120">**표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="76508-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="76508-121">이름 및 연결 유형은 이 연결을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="76508-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="76508-122">이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="76508-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="76508-123">이 연결을 사용할 수 있는 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="76508-123">Choose who can use this connection.</span></span> <span data-ttu-id="76508-124">아무 조치도 취하지 않으면 기본값은 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="76508-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="76508-125">자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="76508-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="76508-126">**DotDigital 사용자 이름 및 암호** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="76508-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="76508-127">**[DotDigital 주소록 ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="76508-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="76508-128">**동의** 를 선택해 **데이터 프라이버시 및 규정 준수** 를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="76508-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="76508-129">**연결** 을 선택하여 DotDigital에 대한 연결을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="76508-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="76508-130">**내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="76508-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="76508-131">연결을 완료하려면 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="76508-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="76508-132">내보내기 구성</span><span class="sxs-lookup"><span data-stu-id="76508-132">Configure an export</span></span>

<span data-ttu-id="76508-133">이 유형의 연결에 대한 액세스 권한이 있는 경우 이 내보내기를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76508-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="76508-134">자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76508-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="76508-135">**데이터** > **내보내기** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="76508-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="76508-136">**대상 추가** 를 선택하여 새 내보내기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="76508-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="76508-137">**내보내기 연결** 필드의 DotDigital 섹션에서 연결을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="76508-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="76508-138">이 섹션 이름이 표시되지 않으면 사용 가능한 이 유형의 연결이 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="76508-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="76508-139">**데이터 일치** 섹션의 이메일 필드에서 고객의 **이메일** 주소를 나타내는 통합 고객 프로필의 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="76508-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="76508-140">**이름**, **성**, **전체 이름**, **성별** 및 **우편 번호** 와 같은 다른 선택 필드에 대해 동일한 단계를 반복하세요.</span><span class="sxs-lookup"><span data-stu-id="76508-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="76508-141">내보낼 세그먼트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="76508-141">Select the segments you want to export.</span></span> <span data-ttu-id="76508-142">총 100만 개의 고객 프로필을 DotDigital로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76508-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="76508-143">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="76508-143">Select **Save**.</span></span>

<span data-ttu-id="76508-144">내보내기를 저장해도 내보내기가 즉시 실행되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76508-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="76508-145">내보내기는 모든 [예약된 새로 고침](system.md#schedule-tab)에 따라 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="76508-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="76508-146">[주문형으로 데이터를 내보낼](export-destinations.md#run-exports-on-demand)수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76508-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="76508-147">DotDigital에서는 이제 [DotDigital 주소록](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)에서 세그먼트를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76508-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="76508-148">데이터 프라이버시 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="76508-148">Data privacy and compliance</span></span>

<span data-ttu-id="76508-149">Dynamics 365 Customer Insights를 사용하여 DotDigital로 데이터를 전송하는 경우 Dynamics 365 Customer Insights 규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76508-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="76508-150">Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만DotDigital이 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76508-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="76508-151">자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76508-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="76508-152">Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76508-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
