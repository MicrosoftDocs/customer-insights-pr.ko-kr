---
title: Customer Insights 데이터를 LinkedIn Ads로 내보내기
description: 연결을 구성하고 LinkedIn Ads로 내보내는 방법을 알아봅니다.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124518"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="194af-103">LinkedIn Ads로 세그먼트 내보내기(프리뷰)</span><span class="sxs-lookup"><span data-stu-id="194af-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="194af-104">통합 고객 프로필의 세그먼트를 LinkedIn Ads로 내보내어 Matched Audiences를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="194af-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="194af-105">회사 타겟팅 및 연락처 타겟팅에 Matched Audiences를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="194af-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="194af-106">필수 조건</span><span class="sxs-lookup"><span data-stu-id="194af-106">Prerequisites</span></span>

-   <span data-ttu-id="194af-107">[LinkedIn Campaign Manager 계정](https://business.linkedin.com/marketing-solutions/ads) 및 해당 관리자 자격 증명이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="194af-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="194af-108">대상 그룹 인사이트에 [구성된 세그먼트](segments.md)가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="194af-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="194af-109">내 보낸 세그먼트의 고객 프로필에는 이메일 주소가 있는 필드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="194af-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="194af-110">알려진 제한 사항</span><span class="sxs-lookup"><span data-stu-id="194af-110">Known limitations</span></span>

- <span data-ttu-id="194af-111">LinkedIn Ads로 내보낼 때마다 최대 10만 개의 프로필을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="194af-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="194af-112">LinkedIn Ads로 내보내기는 세그먼트로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="194af-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="194af-113">최대 10만 개의 프로필을 LinkedIn Ads으로 내보내는 데 최대 10분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="194af-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="194af-114">LinkedIn Ads에 대한 연결 설정하기</span><span class="sxs-lookup"><span data-stu-id="194af-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="194af-115">대상 그룹 Insights에서 **관리자** > **연결** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="194af-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="194af-116">**연결 추가** 와 **LinkedIn Ads** 를 선택하여 연결을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="194af-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="194af-117">**표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="194af-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="194af-118">이름 및 연결 유형은 이 연결을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="194af-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="194af-119">이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="194af-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="194af-120">이 연결을 사용할 수 있는 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="194af-120">Choose who can use this connection.</span></span> <span data-ttu-id="194af-121">아무 작업도 하지 않으면 기본값은 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="194af-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="194af-122">자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="194af-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="194af-123">[LinkedIn Campaign Manager 계정 ID](https://www.linkedin.com/help/lms/answer/a424270)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="194af-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="194af-124">**동의** 를 선택해 **데이터 프라이버시 및 규정 준수** 를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="194af-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="194af-125">**연결** 을 선택하여 Campaign Monitor에 대한 연결을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="194af-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="194af-126">**LinkedIn** 으로 인증을 선택하고 LinkedIn Campaign Manager에 대한 관리자 자격 증명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="194af-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="194af-127">**내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="194af-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="194af-128">연결을 완료하려면 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="194af-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="194af-129">내보내기 구성</span><span class="sxs-lookup"><span data-stu-id="194af-129">Configure an export</span></span>

<span data-ttu-id="194af-130">이 유형의 연결에 대한 액세스 권한이 있는 경우 내보내기를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="194af-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="194af-131">자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="194af-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="194af-132">**데이터** > **내보내기** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="194af-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="194af-133">**대상 추가** 를 선택하여 새 내보내기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="194af-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="194af-134">**내보내기 연결** 필드의 LinkedIn Ads 섹션에서 연결을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="194af-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="194af-135">이 섹션 이름이 표시되지 않으면 사용 가능한 이 유형의 연결이 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="194af-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="194af-136">LinkedIn에서 [연락처 타겟팅](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) 또는 [회사 타겟팅](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting)을 수행하기 위해 데이터를 내보낼지 여부를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="194af-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="194af-137">**데이터 매칭** 섹션에서 고객의 이메일 주소를 나타내는 통합 고객 프로필의 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="194af-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="194af-138">LinkedIn Ads로 세그먼트를 내보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="194af-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="194af-139">내보낼 세그먼트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="194af-139">Select the segments you want to export.</span></span> <span data-ttu-id="194af-140">내보내기 위해 선택한 세그먼트의 이름으로 LinkedIn Campaign Manager의 Matched Audiences가 자동으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="194af-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="194af-141">각 세그먼트는 별도의 Matched Audience를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="194af-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="194af-142">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="194af-142">Select **Save**.</span></span>

<span data-ttu-id="194af-143">내보내기를 저장해도 내보내기가 즉시 실행되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="194af-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="194af-144">내보내기는 모든 [예약된 새로 고침](system.md#schedule-tab)에 따라 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="194af-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="194af-145">[주문형으로 데이터를 내보낼](export-destinations.md#run-exports-on-demand)수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="194af-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="194af-146">데이터 프라이버시 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="194af-146">Data privacy and compliance</span></span>

<span data-ttu-id="194af-147">LinkedIn Ads로 데이터를 전송하기 위해 Dynamics 365 Customer Insights를 활성화 할 때 Dynamics 365 Customer Insights의 규정 준수 경계를 벗어나 개인 데이터와 같이 잠재적으로 민감한 데이터를 포함한 데이터의 전송을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="194af-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="194af-148">Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 귀하는 LinkedIn Ads가 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하는지 확인할 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="194af-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="194af-149">자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="194af-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="194af-150">Dynamics 365 Customer Insights 관리자는 이 기능의 사용을 중지하도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="194af-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>