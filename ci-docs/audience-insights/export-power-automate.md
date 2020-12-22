---
title: Power Automate 커넥터 | Microsoft Docs
description: Dynamics 365 Customer Insights의 Microsoft Power Automate에서 흐름 만들기.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406263"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="afc19-103">Power Automate 커넥터(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="afc19-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="afc19-104">데이터가 변경되면 특정 이벤트가 자동으로 발생하도록 트리거하고 [Power Automate](https://flow.microsoft.com/)에서 직접 더 복잡한 흐름을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="afc19-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="afc19-105">Power Automate 트리거</span><span class="sxs-lookup"><span data-stu-id="afc19-105">Power Automate triggers</span></span>

<span data-ttu-id="afc19-106">알림 또는 고급 작업과 같은 반복적인 작업을 자동화하는 흐름을 만들 수 있는 다양한 트리거를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afc19-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="afc19-107">데이터 원본 새로 고침이 실패하면 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="afc19-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="afc19-108">데이터 원본 새로 고침이 성공하면 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="afc19-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="afc19-109">임계값이 세그먼트에서 교차될 때 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="afc19-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="afc19-110">트리거는 임계값을 초과하는 것으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="afc19-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="afc19-111">임계값이 비즈니스 측정에서 교차될 때 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="afc19-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="afc19-112">트리거는 임계값을 초과하는 것으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="afc19-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="afc19-113">(데이터 원본, 세그먼트, 측정값 등)의 전체 새로 고침이 완료되면 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="afc19-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="afc19-114">통합 프로세스(매핑, 일치, 병합)의 새로 고침이 완료되면 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="afc19-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="afc19-115">[Power Automate에서 트리거를 구성합니다](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="afc19-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="afc19-116">Power Automate 작업</span><span class="sxs-lookup"><span data-stu-id="afc19-116">Power Automate actions</span></span>
<span data-ttu-id="afc19-117">Power Automate 커넥터는 사용 가능한 트리거 이외의 다른 조치를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="afc19-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="afc19-118">자세한 내용은 [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="afc19-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="afc19-119">대상 그룹 인사이트에서 Power Automate 흐름 만들기</span><span class="sxs-lookup"><span data-stu-id="afc19-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="afc19-120">대상 그룹 인사이트에서 **데이터** > **시스템** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="afc19-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="afc19-121">**시스템** 페이지에서 **상태** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="afc19-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="afc19-122">**데이터 소스** 섹션에서 **Flows** 를 선택하고 드롭다운 목록에서 **흐름 만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="afc19-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="afc19-123">![흐름 만들기 작업을 보여주는 Power Automate 커넥터](media/power-automate-connector-create-flow.png "흐름 만들기 작업을 보여주는 Power Automate 커넥터")</span><span class="sxs-lookup"><span data-stu-id="afc19-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="afc19-124">Power Automate에서 사용 가능한 트리거 중 하나를 선택하여 원하는 흐름을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="afc19-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="afc19-125">첫 번째 흐름을 작성하는 경우 먼저 Power Automate 커넥터를 사용하여 인증해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="afc19-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
