---
title: Microsoft Teams용 봇
description: 봇의 도움을 받아 Microsoft Teams에서 통합 고객 프로필을 찾아보세요.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 03299610fd41a7e142e3c9723fad56ce7f90e083
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267960"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="b41a4-103">Dynamics 365 Customer Insights의 Teams 봇(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="b41a4-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="b41a4-104">Microsoft Teams에 연결하여 봇이 Teams 채널에서 통합 고객 프로필을 조회할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41a4-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b41a4-105">![고객 레코드를 보여주는 Teams 봇](media/teams-bot.png "고객 레코드를 보여주는 Teams 봇")</span><span class="sxs-lookup"><span data-stu-id="b41a4-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b41a4-106">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="b41a4-106">Prerequisites</span></span>

<span data-ttu-id="b41a4-107">봇을 설정 및 구성하려면 다음 전제 조건이 충족되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41a4-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="b41a4-108">적어도 하나의 [데이터 원본이 추가](data-sources.md)되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41a4-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="b41a4-109">[통합 프로세스](data-unification.md)가 완료되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41a4-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="b41a4-110">필드가 [검색 및 필터 색인](search-filter-index.md)에 추가되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41a4-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="b41a4-111">Customer Insights와 Teams가 같은 조직에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41a4-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="b41a4-112">봇 구성</span><span class="sxs-lookup"><span data-stu-id="b41a4-112">Configure the bot</span></span>

1. <span data-ttu-id="b41a4-113">대상 그룹 인사이트에서 **데이터** > **내보내기 대상** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b41a4-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="b41a4-114">Microsoft Teams 타일에서 **설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b41a4-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="b41a4-115">Teams의 **앱** 영역으로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="b41a4-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="b41a4-116">Teams를 열고 왼쪽 하단에서 **앱** 을 선택하거나 [AppSource에서 직접 얻을](https://go.microsoft.com/fwlink/?linkid=2124104) 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41a4-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="b41a4-117">**Customer Insights** 를 검색해 앱을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="b41a4-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="b41a4-118">**추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b41a4-118">Select **Add**.</span></span>
1. <span data-ttu-id="b41a4-119">Teams의 Customer Insights에 로그인하면 시작 메시지가 표시되고 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41a4-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="b41a4-120">봇으로 할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="b41a4-120">Things you can do with the bot</span></span>

<span data-ttu-id="b41a4-121">봇은 통합 고객 프로필을 위한 조회 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b41a4-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="b41a4-122">**검색** 을 입력하고 검색 및 필터 색인에 추가되는 통합 고객 프로필의 이름, 이메일 주소 또는 기타 필드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b41a4-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="b41a4-123">결과 고객 프로필에서 최대 15개의 필드가 있는 카드를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="b41a4-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="b41a4-124">여러 개의 일치 항목은 프로필을 선택할 수 있는 결과 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b41a4-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="b41a4-125">검색 용어를 큰 따옴표로 묶어 추가하여 정확히 일치하는 것을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41a4-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="b41a4-126">조직에서 동일한 조직에서 여러 Customer Insights 환경을 유지 관리하는 경우 **switchinstance** 를 입력하여 봇을 연결할 환경을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41a4-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="b41a4-127">**도움말** 을 입력하여 봇에 사용 가능한 명령 목록을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="b41a4-127">Enter **help** to see a list of available commands for the bot.</span></span>  


[!INCLUDE[footer-include](../includes/footer-banner.md)]