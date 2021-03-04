---
title: Dynamics 365 Sales에 Customer Insights 데이터 내보내기
description: Dynamics 365 Sales에 대한 연결을 구성하는 방법에 대해 알아봅니다.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269016"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="406de-103">Dynamics 365 Sales용 커넥터(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="406de-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="406de-104">고객 데이터를 사용하여 마케팅 목록을 만들고, 워크플로에 대한 후속작업을 수행하고, Dynamics 365 Sales로 홍보 행사를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="406de-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="406de-105">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="406de-105">Prerequisite</span></span>

1. <span data-ttu-id="406de-106">Customer Insights에서 영업으로 세그먼트를 내보내려면 먼저 Dynamics 365 Sales에 연락처 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="406de-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="406de-107">[Common Data Services를 사용하는 Dynamics 365 Sales](connect-power-query.md)에서 연락처를 수집하는 방법에 대해 자세히 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="406de-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="406de-108">대상 그룹 인사이트에서 영업으로 세그먼트를 내보내면 영업 인스턴스에 새 연락처 레코드가 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="406de-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="406de-109">영업의 연락처 레코드는 대상 그룹 인사이트에서 수집되고 데이터 원본으로 사용되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="406de-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="406de-110">또한 세그먼트를 내보내기 전에 고객 ID를 연락처 ID에 매핑하려면 통합 고객 엔터티에 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="406de-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="406de-111">Sales용 커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="406de-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="406de-112">대상 그룹 인사이트에서 **데이터** > **내보내기 대상** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="406de-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="406de-113">**Dynamics 365 Sales** 아래에서 **설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="406de-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="406de-114">**표시 이름** 필드에서 내보내기 대상에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="406de-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="406de-115">**서버 주소** 필드에 조직의 Sales URL을 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="406de-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="406de-116">**서버 관리자 계정** 섹션에서 **로그인** 을 선택하고 Dynamics 365 Sales 계정을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="406de-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="406de-117">고객 ID 필드를 Dynamics 365 연락처 ID에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="406de-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="406de-118">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="406de-118">Select **Next**.</span></span>

1. <span data-ttu-id="406de-119">하나 이상의 세그먼트를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="406de-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="406de-120">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="406de-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="406de-121">데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="406de-121">Export the data</span></span>

<span data-ttu-id="406de-122">[주문 시 데이터를 내보낼](export-destinations.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="406de-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="406de-123">내보내기는 [예약된 새로 고침](system.md#schedule-tab)마다 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="406de-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]