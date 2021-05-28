---
title: Dynamics 365 Sales에 Customer Insights 데이터 내보내기
description: 연결을 구성하고 Dynamics 365 Sales로 내보내는 방법을 알아봅니다.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 328bb2f26ebcea234fb645e5225930ab12f82a8b
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976234"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="235d6-103">Dynamics 365 Sales에 세그먼트 사용(프리뷰)</span><span class="sxs-lookup"><span data-stu-id="235d6-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="235d6-104">고객 데이터를 사용하여 마케팅 목록을 만들고, 워크플로에 대한 후속작업을 수행하고, Dynamics 365 Sales로 홍보 행사를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="235d6-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="235d6-105">연결을 위한 전제 조건</span><span class="sxs-lookup"><span data-stu-id="235d6-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="235d6-106">Customer Insights에서 영업으로 세그먼트를 내보내려면 먼저 Dynamics 365 Sales에 연락처 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="235d6-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="235d6-107">[Common Data Services를 사용하는 Dynamics 365 Sales](connect-power-query.md)에서 연락처를 수집하는 방법에 대해 자세히 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="235d6-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="235d6-108">대상 그룹 인사이트에서 영업으로 세그먼트를 내보내면 영업 인스턴스에 새 연락처 레코드가 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="235d6-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="235d6-109">영업의 연락처 레코드는 대상 그룹 인사이트에서 수집되고 데이터 원본으로 사용되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="235d6-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="235d6-110">또한 세그먼트를 내보내기 전에 고객 ID를 연락처 ID에 매핑하려면 통합 고객 엔터티에 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="235d6-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="235d6-111">Sales에 연결을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="235d6-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="235d6-112">**관리자** > **연결** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="235d6-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="235d6-113">**연결 추가** 와 **Dynamics 365 Sales** 를 선택하여 연결을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="235d6-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="235d6-114">**표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="235d6-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="235d6-115">이름 및 연결 유형은 이 연결을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="235d6-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="235d6-116">이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="235d6-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="235d6-117">이 연결을 사용할 수 있는 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="235d6-117">Choose who can use this connection.</span></span> <span data-ttu-id="235d6-118">아무 조치도 취하지 않으면 기본값은 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="235d6-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="235d6-119">자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="235d6-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="235d6-120">**서버 주소** 필드에 조직의 Sales URL을 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="235d6-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="235d6-121">**서버 관리자 계정** 섹션에서 **로그인** 을 선택하고 Dynamics 365 Sales 계정을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="235d6-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="235d6-122">고객 ID 필드를 Dynamics 365 연락처 ID에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="235d6-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="235d6-123">연결을 완료하려면 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="235d6-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="235d6-124">내보내기 구성</span><span class="sxs-lookup"><span data-stu-id="235d6-124">Configure an export</span></span>

<span data-ttu-id="235d6-125">이 유형의 연결에 대한 액세스 권한이 있는 경우 이 내보내기를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="235d6-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="235d6-126">자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="235d6-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="235d6-127">**데이터** > **내보내기** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="235d6-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="235d6-128">**대상 추가** 를 선택하여 새 내보내기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="235d6-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="235d6-129">**내보내기 연결** 필드의 Dynamics 365 Sales 섹션에서 연결을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="235d6-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="235d6-130">이 섹션 이름이 표시되지 않으면 사용 가능한 이 유형의 연결이 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="235d6-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="235d6-131">하나 이상의 세그먼트를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="235d6-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="235d6-132">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="235d6-132">Select **Save**</span></span>

<span data-ttu-id="235d6-133">내보내기를 저장해도 내보내기가 즉시 실행되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="235d6-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="235d6-134">내보내기는 모든 [예약된 새로 고침](system.md#schedule-tab)에 따라 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="235d6-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="235d6-135">[주문형으로 데이터를 내보낼](export-destinations.md#run-exports-on-demand)수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="235d6-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
