---
title: DotDigital 광고로 Customer Insights 데이터 내보내기
description: DotDigital 연결을 구성하는 방법을 알아보세요.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed6bd40e8575fc90258f79f60abffe54f136d274
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644456"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="54780-103">DotDigital용 커넥터(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="54780-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="54780-104">통합 고객 프로필의 세그먼트를 DotDigital 주소록으로 내보내고 이를 캠페인, 이메일 마케팅에 사용하고 DotDigital로 고객 세그먼트를 구축합니다.</span><span class="sxs-lookup"><span data-stu-id="54780-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="54780-105">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="54780-105">Prerequisites</span></span>

-   <span data-ttu-id="54780-106">[DotDigital 계정](https://dotdigital.com/) 및 해당 관리자 자격 증명이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54780-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="54780-107">DotDigital에 기존 주소록과 해당 ID가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54780-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="54780-108">ID는 주소록을 선택하여 열 때 URL에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54780-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="54780-109">자세한 내용은 [DotDigital 주소록](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="54780-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="54780-110">대상 그룹 인사이트에 [구성된 세그먼트](segments.md)가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54780-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="54780-111">내보낸 세그먼트의 통합 고객 프로필에는 이메일 주소를 나타내는 필드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="54780-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="54780-112">DotDigital에 연결</span><span class="sxs-lookup"><span data-stu-id="54780-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="54780-113">**관리자** > **내보내기 대상** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="54780-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="54780-114">**DotDigital** 에서 **설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="54780-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="54780-115">**표시 이름** 필드에서 내보내기 대상에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="54780-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="DotDigital 내보내기를 위한 구성 창.":::

1. <span data-ttu-id="54780-117">**DotDigital 사용자 이름 및 암호** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="54780-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="54780-118">**[DotDigital 주소록 ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="54780-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="54780-119">**동의** 를 선택해 **데이터 프라이버시 및 규정 준수** 를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="54780-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="54780-120">**연결** 을 선택하여 DotDigital에 대한 연결을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="54780-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="54780-121">**내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="54780-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="54780-122">**다음** 을 선택해 내보내기를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="54780-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="54780-123">커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="54780-123">Configure the connector</span></span>

1. <span data-ttu-id="54780-124">**데이터 일치** 섹션의 이메일 필드에서 고객의 **이메일** 주소를 나타내는 통합 고객 프로필의 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="54780-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="54780-125">**이름**, **성**, **전체 이름**, **성별** 및 **우편 번호** 와 같은 다른 선택 필드에 대해 동일한 단계를 반복하세요.</span><span class="sxs-lookup"><span data-stu-id="54780-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="54780-126">내보낼 세그먼트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="54780-126">Select the segments you want to export.</span></span> <span data-ttu-id="54780-127">총 100만 개의 고객 프로필을 DotDigital로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54780-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="54780-128">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="54780-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="54780-129">데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="54780-129">Export the data</span></span>

<span data-ttu-id="54780-130">[주문 시 데이터를 내보낼](export-destinations.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54780-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="54780-131">내보내기는 [예약된 새로 고침](system.md#schedule-tab)마다 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="54780-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="54780-132">DotDigital에서는 이제 [DotDigital 주소록](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)에서 세그먼트를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54780-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="54780-133">알려진 제한 사항</span><span class="sxs-lookup"><span data-stu-id="54780-133">Known limitations</span></span>

- <span data-ttu-id="54780-134">DotDigital로 내보낼 때마다 프로필이 최대 100만 개입니다.</span><span class="sxs-lookup"><span data-stu-id="54780-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="54780-135">DotDigital로 내보내기는 세그먼트로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="54780-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="54780-136">총 100만 개의 프로필이 있는 세그먼트를 내보내는 것은 공급자측의 제한으로 인해 최대 3시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54780-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="54780-137">DotDigital로 내보낼 수 있는 프로필 수는 DotDigital와의 계약에 따라 다르며 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="54780-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="54780-138">데이터 프라이버시 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="54780-138">Data privacy and compliance</span></span>

<span data-ttu-id="54780-139">Dynamics 365 Customer Insights를 사용하여 DotDigital로 데이터를 전송하는 경우 Dynamics 365 Customer Insights 규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54780-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="54780-140">Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만DotDigital이 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54780-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="54780-141">자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="54780-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="54780-142">Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54780-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
