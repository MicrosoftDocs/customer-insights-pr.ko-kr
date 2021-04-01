---
title: 통합 고객 프로필 보강
description: 기능을 사용하여 고객 데이터를 보강합니다.
ms.date: 11/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 36e6f7f8fcd64fc2591e913910918b83bf27567b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597703"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="f678d-103">고객 프로필 보강(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="f678d-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="f678d-104">Microsoft 및 기타 파트너와 같은 소스의 데이터를 사용하여 고객 데이터를 보강합니다.</span><span class="sxs-lookup"><span data-stu-id="f678d-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="보강 허브 페이지":::

<span data-ttu-id="f678d-106">대상 그룹 인사이트에서 **데이터** > **보강** 으로 이동하여 강화 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f678d-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="f678d-107">기능 보강을 작성하거나 편집하려면 기여자 또는 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f678d-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="f678d-108">자세한 내용은 [권한](permissions.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f678d-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="f678d-109">**검색** 탭에서 다음과 같은 기능이 보강됩니다.</span><span class="sxs-lookup"><span data-stu-id="f678d-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="f678d-110">Microsoft Graph에서 제공하는 [브랜드](enrichment-microsoft-graph.md)</span><span class="sxs-lookup"><span data-stu-id="f678d-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="f678d-111">Microsoft Graph에서 제공하는 [관심사](enrichment-microsoft-graph.md).</span><span class="sxs-lookup"><span data-stu-id="f678d-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="f678d-112">Leadspace에서 제공한 [회사 데이터](enrichment-leadspace.md)</span><span class="sxs-lookup"><span data-stu-id="f678d-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="f678d-113">Experian에서 제공한 [인구 통계 자료](enrichment-experian.md)</span><span class="sxs-lookup"><span data-stu-id="f678d-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="f678d-114">HERE Technologies에서 제공한 [위치 데이터](enrichment-here.md)</span><span class="sxs-lookup"><span data-stu-id="f678d-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="f678d-115">SFTP(보안 파일 전송 프로토콜)를 통한 [사용자 지정 데이터](enrichment-SFTP-custom-import.md)</span><span class="sxs-lookup"><span data-stu-id="f678d-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="f678d-116">**내 보강** 탭에서 구성한 보강을 보고 속성을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f678d-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="f678d-117">기존 보강 관리</span><span class="sxs-lookup"><span data-stu-id="f678d-117">Manage existing enrichments</span></span>

<span data-ttu-id="f678d-118">구성된 모든 보강을 보려면 **내 보강** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f678d-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="f678d-119">각 보강은 보강에 대한 추가 정보를 포함하는 행으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f678d-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="f678d-120">사용 가능한 옵션을 보려면 보강을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="f678d-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="f678d-121">또는 목록 항목에서 줄임표(...)를 선택하여 옵션을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f678d-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="보강 목록에서 보강을 관리하는 옵션":::

- <span data-ttu-id="f678d-123">고객 프로필의 수가 보강된 강화 세부 사항 **보기**.</span><span class="sxs-lookup"><span data-stu-id="f678d-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="f678d-124">강화 구성 **편집**.</span><span class="sxs-lookup"><span data-stu-id="f678d-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="f678d-125">**운영** 최신 데이터로 고객 프로필 업데이트 강화</span><span class="sxs-lookup"><span data-stu-id="f678d-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="f678d-126">예약된 새로 고침마다 자동으로 새로 고쳐지지 않도록 기존 보강을 **비활성화**.</span><span class="sxs-lookup"><span data-stu-id="f678d-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="f678d-127">마지막으로 성공한 새로 고침의 데이터는 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f678d-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="f678d-128">예약된 새로 고침마다 자동 새로 고침을 다시 시작하도록 비활성 보강을 **활성화**.</span><span class="sxs-lookup"><span data-stu-id="f678d-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="f678d-129">보강을 **삭제** 합니다.</span><span class="sxs-lookup"><span data-stu-id="f678d-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="f678d-130">목록에서 여러 가지 보강을 선택하여 한 번에 실행하거나 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f678d-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="f678d-131">보기 및 편집 옵션은 일괄 작업으로 사용할 수 없으며 한 번에 하나의 보강에 대해서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="f678d-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]