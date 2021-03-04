---
title: Power Automate 커넥터 | Microsoft Docs
description: Dynamics 365 Customer Insights의 Microsoft Power Automate에서 흐름 만들기.
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268832"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="1c13a-103">Power Automate 커넥터(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="1c13a-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="1c13a-104">데이터가 변경되면 특정 이벤트가 자동으로 발생하도록 트리거하고 [Power Automate](https://flow.microsoft.com/)에서 직접 더 복잡한 흐름을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="1c13a-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="1c13a-105">Power Automate 트리거</span><span class="sxs-lookup"><span data-stu-id="1c13a-105">Power Automate triggers</span></span>

<span data-ttu-id="1c13a-106">트리거를 사용하여 클라우드 흐름을 만들고 알림 또는 고급 작업과 같은 반복적인 작업을 자동화합니다.</span><span class="sxs-lookup"><span data-stu-id="1c13a-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="1c13a-107">데이터 원본 새로 고침이 실패하면 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c13a-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="1c13a-108">데이터 원본 새로 고침이 성공하면 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c13a-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="1c13a-109">임계값이 세그먼트에서 교차될 때 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c13a-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="1c13a-110">트리거는 임계값을 초과하는 것으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c13a-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="1c13a-111">임계값이 비즈니스 측정에서 교차될 때 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c13a-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="1c13a-112">트리거는 임계값을 초과하는 것으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c13a-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="1c13a-113">(데이터 원본, 세그먼트, 측정값 등)의 전체 새로 고침이 완료되면 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c13a-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="1c13a-114">통합 프로세스(매핑, 일치, 병합)의 새로 고침이 완료되면 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c13a-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="1c13a-115">[Power Automate에서 트리거를 구성합니다](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="1c13a-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="1c13a-116">Power Automate 작업</span><span class="sxs-lookup"><span data-stu-id="1c13a-116">Power Automate actions</span></span>
<span data-ttu-id="1c13a-117">Power Automate 커넥터는 사용 가능한 트리거 이외의 다른 조치를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1c13a-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="1c13a-118">자세한 내용은 [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1c13a-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="1c13a-119">Power Automate 흐름 만들기</span><span class="sxs-lookup"><span data-stu-id="1c13a-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="1c13a-120">대상 그룹 인사이트에서 **데이터** > **내보내기 대상** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1c13a-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="1c13a-121">**Power Automate** 타일에서 **설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1c13a-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="1c13a-122">Power Automate의 Customer Insights 커넥터(미리 보기)가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="1c13a-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="1c13a-123">Power Automate에 **로그인** 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c13a-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="1c13a-124">사용 가능한 트리거 중 하나를 선택하고 새 흐름에 단계를 더 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1c13a-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="1c13a-125">자세한 내용은 [Power Automate의 클라우드 흐름 만들기](https://docs.microsoft.com/power-automate/get-started-logic-flow)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1c13a-125">For more information, see [Create a cloud flow in Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="1c13a-126">흐름을 사용하는 방법의 예:</span><span class="sxs-lookup"><span data-stu-id="1c13a-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="1c13a-127">데이터 원본 새로 고침이 실패하면 Microsoft Teams 채널에 메시지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="1c13a-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="1c13a-128">세그먼트의 임계값이 초과되면 데이터 담당자에게 이메일을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c13a-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]