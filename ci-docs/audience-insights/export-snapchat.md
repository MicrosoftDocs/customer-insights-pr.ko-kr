---
title: Customer Insights 데이터를 Snapchat으로 내보내기
description: 연결을 구성하고 Snapchat으로 내보내는 방법을 알아봅니다.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6565ab81599abcc0f94465e1153f08e0bc119839
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124051"
---
# <a name="export-segments-to-snapchat-preview"></a><span data-ttu-id="d6299-103">Snapchat으로 세그먼트 내보내기(프리뷰)</span><span class="sxs-lookup"><span data-stu-id="d6299-103">Export segments to Snapchat (preview)</span></span>

<span data-ttu-id="d6299-104">통합 고객 프로필의 세그먼트를 Snapchat으로 내보내고 광고에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="d6299-105">연결을 위한 전제 조건</span><span class="sxs-lookup"><span data-stu-id="d6299-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="d6299-106">[Snapchat 비즈니스 계정](https://business.snapchat.com/), [Snapchat 광고 계정](https://ads.snapchat.com/) 및 해당 관리자 자격 증명.</span><span class="sxs-lookup"><span data-stu-id="d6299-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d6299-107">대상 그룹 인사이트에 [구성된 세그먼트](segments.md)가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="d6299-108">내보낸 세그먼트의 통합 고객 프로필에는 이메일 주소를 나타내는 필드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d6299-109">알려진 제한 사항</span><span class="sxs-lookup"><span data-stu-id="d6299-109">Known limitations</span></span>

- <span data-ttu-id="d6299-110">Snapchat으로 내보내기는 세그먼트로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="d6299-111">최대 1백만 개의 프로필을 Snapchat으로 내보내는 데 최대 15분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="d6299-112">Snapchat 연결 설정</span><span class="sxs-lookup"><span data-stu-id="d6299-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="d6299-113">**관리자** > **연결** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d6299-114">**연결 추가** 와 **Snapchat** 을 선택하여 연결을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="d6299-115">**표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d6299-116">이름 및 연결 유형은 이 연결을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d6299-117">이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d6299-118">이 연결을 사용할 수 있는 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-118">Choose who can use this connection.</span></span> <span data-ttu-id="d6299-119">아무 조치도 취하지 않으면 기본값은 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d6299-120">자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="d6299-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d6299-121">**동의** 를 선택해 **데이터 프라이버시 및 규정 준수** 를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d6299-122">**연결** 을 선택하여 Snapchat에 대한 연결을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="d6299-123">**Snapchat으로 인증** 을 선택하고 Snapchat에 대한 관리자 자격 증명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="d6299-124">**내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d6299-125">연결을 완료하려면 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d6299-126">내보내기 구성</span><span class="sxs-lookup"><span data-stu-id="d6299-126">Configure an export</span></span>

<span data-ttu-id="d6299-127">이 유형의 연결에 대한 액세스 권한이 있는 경우 이 내보내기를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d6299-128">자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d6299-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d6299-129">**데이터** > **내보내기** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d6299-130">**대상 추가** 를 선택하여 새 내보내기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d6299-131">**내보내기 연결** 필드의 Snapchat 섹션에서 연결을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="d6299-132">이 섹션 이름이 표시되지 않으면 사용 가능한 이 유형의 연결이 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d6299-133">[**Snapchat 대상 그룹 ID**](https://businesshelp.snapchat.com/s/article/custom-audiences)를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="d6299-134">**데이터 일치** 섹션의 이메일 필드에서 고객의 **이메일** 주소를 나타내는 통합 고객 프로필의 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="d6299-135">Snapchat으로 세그먼트를 내보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="d6299-136">내보낼 세그먼트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="d6299-137">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-137">Select **Save**.</span></span>

<span data-ttu-id="d6299-138">내보내기를 저장해도 내보내기가 즉시 실행되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d6299-139">내보내기는 모든 [예약된 새로 고침](system.md#schedule-tab)에 따라 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d6299-140">[주문형으로 데이터를 내보낼](export-destinations.md#run-exports-on-demand)수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d6299-141">데이터 프라이버시 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="d6299-141">Data privacy and compliance</span></span>

<span data-ttu-id="d6299-142">Snapchat으로 데이터를 전송하기 위해 Dynamics 365 Customer Insights를 활성화 할 때 Dynamics 365 Customer Insights의 규정 준수 경계를 벗어나 개인 데이터와 같이 잠재적으로 민감한 데이터를 포함한 데이터의 전송을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d6299-143">Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 귀하는 Snapchat이 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하는지 확인할 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d6299-144">자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d6299-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="d6299-145">Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6299-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
