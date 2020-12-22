---
title: Dynamics 365 Marketing에 Customer Insights 데이터 내보내기
description: Dynamics 365 Marketing에 대한 연결을 구성하는 방법에 대해 알아봅니다.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643781"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="326cc-103">Dynamics 365 Marketing용 커넥터(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="326cc-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="326cc-104">[세그먼트](segments.md)를 사용하여 캠페인을 생성하고 Dynamics 365 Marketing의 특정 고객 그룹에게 연락합니다.</span><span class="sxs-lookup"><span data-stu-id="326cc-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="326cc-105">자세한 내용은 [Dynamics 365 Marketing으로 Dynamics 365 Customer Insights에서 세그먼트 사용](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="326cc-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="326cc-106">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="326cc-106">Prerequisite</span></span>

<span data-ttu-id="326cc-107">[Common Data Service를 사용하여 수집된 Dynamics 365 Marketing](connect-power-query.md)의 연락처 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="326cc-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="326cc-108">Marketing용 커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="326cc-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="326cc-109">대상 그룹 인사이트에서 **데이터** > **내보내기 대상** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="326cc-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="326cc-110">**Dynamics 365 Marketing** 아래에서 **설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="326cc-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="326cc-111">**표시 이름** 필드에서 내보내기 대상에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="326cc-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="326cc-112">**서버 주소** 필드에 조직의 Marketing URL을 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="326cc-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="326cc-113">**서버 관리자 계정** 섹션에서 **로그인** 을 선택하고 Dynamics 365 Marketing 계정을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="326cc-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="326cc-114">고객 ID 필드를 Dynamics 365 연락처 ID에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="326cc-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="326cc-115">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="326cc-115">Select **Next**.</span></span>

1. <span data-ttu-id="326cc-116">하나 이상의 세그먼트를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="326cc-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="326cc-117">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="326cc-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="326cc-118">데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="326cc-118">Export the data</span></span>

<span data-ttu-id="326cc-119">[주문 시 데이터를 내보낼](export-destinations.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="326cc-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="326cc-120">내보내기는 [예약된 새로 고침](system.md#schedule-tab)마다 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="326cc-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
