---
title: Dynamics 365 Marketing에 Customer Insights 데이터 내보내기
description: Dynamics 365 Marketing에 대한 연결을 구성하는 방법에 대해 알아봅니다.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269062"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="45147-103">Dynamics 365 Marketing용 커넥터(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="45147-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="45147-104">[세그먼트](segments.md)를 사용하여 캠페인을 생성하고 Dynamics 365 Marketing의 특정 고객 그룹에게 연락합니다.</span><span class="sxs-lookup"><span data-stu-id="45147-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="45147-105">자세한 내용은 [Dynamics 365 Marketing으로 Dynamics 365 Customer Insights에서 세그먼트 사용](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="45147-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="45147-106">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="45147-106">Prerequisite</span></span>

- <span data-ttu-id="45147-107">Customer Insights에서 마케팅으로 세그먼트를 내보내려면 먼저 Dynamics 365 Marketing에 연락처 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45147-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="45147-108">[Common Data Services를 사용하는 Dynamics 365 Marketing](connect-power-query.md)에서 연락처를 수집하는 방법에 대해 자세히 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="45147-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="45147-109">대상 그룹 인사이트에서 마케팅으로 세그먼트를 내보내면 마케팅 인스턴스에 새 연락처 레코드가 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45147-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="45147-110">마케팅의 연락처 레코드는 대상 그룹 인사이트에서 수집되고 데이터 원본으로 사용되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45147-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="45147-111">또한 세그먼트를 내보내기 전에 고객 ID를 연락처 ID에 매핑하려면 통합 고객 엔터티에 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45147-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="45147-112">Marketing용 커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="45147-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="45147-113">대상 그룹 인사이트에서 **데이터** > **내보내기 대상** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="45147-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="45147-114">**Dynamics 365 Marketing** 아래에서 **설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45147-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="45147-115">**표시 이름** 필드에서 내보내기 대상에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="45147-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="45147-116">**서버 주소** 필드에 조직의 Marketing URL을 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="45147-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="45147-117">**서버 관리자 계정** 섹션에서 **로그인** 을 선택하고 Dynamics 365 Marketing 계정을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="45147-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="45147-118">고객 ID 필드를 Dynamics 365 연락처 ID에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="45147-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="45147-119">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45147-119">Select **Next**.</span></span>

1. <span data-ttu-id="45147-120">하나 이상의 세그먼트를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="45147-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="45147-121">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45147-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="45147-122">데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="45147-122">Export the data</span></span>

<span data-ttu-id="45147-123">[주문 시 데이터를 내보낼](export-destinations.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45147-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="45147-124">내보내기는 [예약된 새로 고침](system.md#schedule-tab)마다 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="45147-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]