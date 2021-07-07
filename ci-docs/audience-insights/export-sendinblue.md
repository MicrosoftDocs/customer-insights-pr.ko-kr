---
title: Customer Insights 데이터를 Sendinblue로 내보내기
description: 연결을 구성하고 Sendinblue로 내보내는 방법을 알아봅니다.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314640"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="39ad0-103">Sendinblue로 세그먼트 내보내기(프리뷰)</span><span class="sxs-lookup"><span data-stu-id="39ad0-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="39ad0-104">통합 고객 프로필의 세그먼트를 내보내 캠페인을 생성하고 이메일 마케팅을 제공하며 Sendinblue의 특정 고객 그룹을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="39ad0-105">연결을 위한 전제 조건</span><span class="sxs-lookup"><span data-stu-id="39ad0-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="39ad0-106">귀하는 [Sendinblue 계정](https://www.sendinblue.com/) 및 해당 관리자 자격 증명을 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="39ad0-107">Sendinblue에는 기존 목록과 해당 ID가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="39ad0-108">[구성된 세그먼트](segments.md)가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="39ad0-109">내보낸 세그먼트의 통합 고객 프로필에는 이메일 주소를 나타내는 필드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="39ad0-110">알려진 제한 사항</span><span class="sxs-lookup"><span data-stu-id="39ad0-110">Known limitations</span></span>

- <span data-ttu-id="39ad0-111">Sendinblue로 내보낼 때마다 최대 1백만 개의 프로필 내보내기 가능.</span><span class="sxs-lookup"><span data-stu-id="39ad0-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="39ad0-112">Sendinblue으로 내보내기는 세그먼트로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="39ad0-113">총 1백만 개의 프로필이 있는 세그먼트를 내보내는 데 최대 90분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="39ad0-114">Sendinblue로 내보낼 수 있는 프로필 수는 Sendinblue과의 계약에 따라 다르며 해당 계약의 제한을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="39ad0-115">Sendinblue 연결 설정</span><span class="sxs-lookup"><span data-stu-id="39ad0-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="39ad0-116">**관리자** > **연결** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="39ad0-117">**연결 추가** 를 선택하고 **Sendinblue** 를 선택하여 연결을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="39ad0-118">**표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="39ad0-119">이름 및 연결 유형은 이 연결을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="39ad0-120">이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="39ad0-121">이 연결을 사용할 수 있는 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-121">Choose who can use this connection.</span></span> <span data-ttu-id="39ad0-122">기본적으로 관리자만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-122">By default it's only administrators.</span></span> <span data-ttu-id="39ad0-123">자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="39ad0-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="39ad0-124">**[Sendinblue API 키](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="39ad0-125">**동의함** 을 선택하여 **데이터 개인 정보 보호 및 규정 준수** 를 확인하고 **연결** 을 선택하여 Sendinblue에 대한 연결을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="39ad0-126">**내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="39ad0-127">연결을 완료하려면 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="39ad0-128">내보내기 구성</span><span class="sxs-lookup"><span data-stu-id="39ad0-128">Configure an export</span></span>

<span data-ttu-id="39ad0-129">이 유형의 연결에 대한 액세스 권한이 있는 경우 이 내보내기를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="39ad0-130">자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39ad0-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="39ad0-131">**데이터** > **내보내기** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="39ad0-132">**대상 추가** 를 선택하여 새 내보내기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="39ad0-133">**내보내기 연결** 필드에서 Sendinblue 섹션에서 연결을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="39ad0-134">이 섹션 이름이 표시되지 않으면 사용 가능한 이 유형의 연결이 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="39ad0-135">**Sendinblue 목록 ID** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="39ad0-136">**데이터 일치** 섹션의 이메일 필드에서 고객의 **이메일** 주소를 나타내는 통합 고객 프로필의 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="39ad0-137">선택적으로 **이름**, **성**, 및 **전화** 를 내보내 더 개인화된 이메일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="39ad0-138">**특성 추가** 를 선택하여 이러한 필드를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="39ad0-139">내보낼 세그먼트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="39ad0-140">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-140">Select **Save**.</span></span>

<span data-ttu-id="39ad0-141">내보내기를 저장해도 내보내기가 즉시 실행되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="39ad0-142">내보내기는 모든 [예약된 새로 고침](system.md#schedule-tab)에 따라 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="39ad0-143">[주문형으로 데이터를 내보낼](export-destinations.md#run-exports-on-demand)수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="39ad0-144">데이터 프라이버시 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="39ad0-144">Data privacy and compliance</span></span>

<span data-ttu-id="39ad0-145">Sendinblue에 데이터를 전송하기 위해 Dynamics 365 Customer Insights를 활성화할 때 개인 데이터와 같이 잠재적으로 민감한 데이터를 비롯하여 Dynamics 365 Customer Insights의 준수 경계를 벗어난 데이터 전송을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="39ad0-146">Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 귀하는 Sendinblue가 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="39ad0-147">자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39ad0-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="39ad0-148">Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39ad0-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
