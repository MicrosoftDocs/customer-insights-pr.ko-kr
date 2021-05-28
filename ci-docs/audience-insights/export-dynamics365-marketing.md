---
title: Dynamics 365 Marketing에 Customer Insights 데이터 내보내기
description: 연결을 구성하고 Dynamics 365 Marketing으로 내보내는 방법을 알아봅니다.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 195bee789dc043057b47c12c8d93e6d53edb59cd
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976808"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="33536-103">Dynamics 365 Marketing에 세그먼트 사용(프리뷰)</span><span class="sxs-lookup"><span data-stu-id="33536-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="33536-104">[세그먼트](segments.md)를 사용하여 캠페인을 생성하고 Dynamics 365 Marketing의 특정 고객 그룹에게 연락합니다.</span><span class="sxs-lookup"><span data-stu-id="33536-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="33536-105">자세한 내용은 [Dynamics 365 Marketing으로 Dynamics 365 Customer Insights에서 세그먼트 사용](/dynamics365/marketing/customer-insights-segments)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="33536-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="33536-106">연결을 위한 전제 조건</span><span class="sxs-lookup"><span data-stu-id="33536-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="33536-107">Customer Insights에서 마케팅으로 세그먼트를 내보내려면 먼저 Dynamics 365 Marketing에 연락처 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33536-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="33536-108">[Common Data Services를 사용하는 Dynamics 365 Marketing](connect-power-query.md)에서 연락처를 수집하는 방법에 대해 자세히 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="33536-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="33536-109">대상 그룹 인사이트에서 마케팅으로 세그먼트를 내보내면 마케팅 인스턴스에 새 연락처 레코드가 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33536-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="33536-110">마케팅의 연락처 레코드는 대상 그룹 인사이트에서 수집되고 데이터 원본으로 사용되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33536-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="33536-111">또한 세그먼트를 내보내기 전에 고객 ID를 연락처 ID에 매핑하려면 통합 고객 엔터티에 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33536-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="33536-112">Marketing에 연결을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="33536-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="33536-113">**관리자** > **연결** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="33536-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="33536-114">**연결 추가** 와 **Dynamics 365 Marketing** 을 선택하여 연결을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="33536-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="33536-115">**표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="33536-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="33536-116">이름 및 연결 유형은 이 연결을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="33536-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="33536-117">이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="33536-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="33536-118">이 연결을 사용할 수 있는 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="33536-118">Choose who can use this connection.</span></span> <span data-ttu-id="33536-119">아무 조치도 취하지 않으면 기본값은 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="33536-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="33536-120">자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="33536-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="33536-121">**서버 주소** 필드에 조직의 Marketing URL을 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="33536-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="33536-122">**서버 관리자 계정** 섹션에서 **로그인** 을 선택하고 Dynamics 365 Marketing 계정을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="33536-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="33536-123">고객 ID 필드를 Dynamics 365 연락처 ID에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="33536-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="33536-124">연결을 완료하려면 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="33536-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="33536-125">내보내기 구성</span><span class="sxs-lookup"><span data-stu-id="33536-125">Configure an export</span></span>

<span data-ttu-id="33536-126">이 유형의 연결에 대한 액세스 권한이 있는 경우 이 내보내기를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33536-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="33536-127">자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33536-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="33536-128">**데이터** > **내보내기** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="33536-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="33536-129">**대상 추가** 를 선택하여 새 내보내기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="33536-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="33536-130">**내보내기 연결** 필드의 Dynamics 365 Marketing 섹션에서 연결을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="33536-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="33536-131">이 섹션 이름이 표시되지 않으면 사용 가능한 이 유형의 연결이 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="33536-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="33536-132">하나 이상의 세그먼트를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="33536-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="33536-133">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="33536-133">Select **Save**.</span></span>

<span data-ttu-id="33536-134">내보내기를 저장해도 내보내기가 즉시 실행되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33536-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="33536-135">내보내기는 모든 [예약된 새로 고침](system.md#schedule-tab)에 따라 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="33536-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="33536-136">[주문형으로 데이터를 내보낼](export-destinations.md#run-exports-on-demand)수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33536-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
