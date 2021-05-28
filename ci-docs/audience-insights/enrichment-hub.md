---
title: 통합 고객 프로필 보강
description: 기능을 사용하여 고객 데이터를 보강합니다.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c8e4a7247ccf575a62440038180010916b09d51b
ms.sourcegitcommit: f9e2fa3f11ecf11a5d9cccc376fdeb1ecea54880
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5954495"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="68795-103">고객 프로필 보강(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="68795-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="68795-104">Microsoft 및 기타 파트너와 같은 소스의 데이터를 사용하여 고객 데이터를 보강합니다.</span><span class="sxs-lookup"><span data-stu-id="68795-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="보강 허브 페이지":::

<span data-ttu-id="68795-106">대상 그룹 인사이트에서 **데이터** > **보강** 으로 이동하여 강화 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="68795-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="68795-107">기능 보강을 작성하거나 편집하려면 기여자 또는 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68795-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="68795-108">자세한 내용은 [권한](permissions.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="68795-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="68795-109">**검색** 탭에서 다음과 같은 기능이 보강됩니다.</span><span class="sxs-lookup"><span data-stu-id="68795-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="68795-110">Microsoft에서 제공한 [브랜드](enrichment-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="68795-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="68795-111">Microsoft에서 제공한 [관심사](enrichment-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="68795-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="68795-112">Microsoft 제공 [향상된 주소](enrichment-enhanced-addresses.md)</span><span class="sxs-lookup"><span data-stu-id="68795-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="68795-113">Leadspace에서 제공한 [회사 데이터](enrichment-leadspace.md)</span><span class="sxs-lookup"><span data-stu-id="68795-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="68795-114">Experian에서 제공한 [인구 통계 자료](enrichment-experian.md)</span><span class="sxs-lookup"><span data-stu-id="68795-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="68795-115">HERE Technologies에서 제공한 [위치 데이터](enrichment-here.md)</span><span class="sxs-lookup"><span data-stu-id="68795-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="68795-116">SFTP(보안 파일 전송 프로토콜)를 통한 [사용자 지정 데이터](enrichment-SFTP-custom-import.md)</span><span class="sxs-lookup"><span data-stu-id="68795-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="68795-117">**내 보강** 탭에서 구성한 보강을 보고 속성을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68795-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="68795-118">기존 보강 관리</span><span class="sxs-lookup"><span data-stu-id="68795-118">Manage existing enrichments</span></span>

<span data-ttu-id="68795-119">구성된 모든 보강을 보려면 **내 보강** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="68795-119">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="68795-120">각 보강은 보강에 대한 추가 정보를 포함하는 행으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="68795-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="68795-121">사용 가능한 옵션을 보려면 보강을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="68795-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="68795-122">목록 항목에서 줄임표(...)를 선택하여 옵션을 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68795-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="보강 목록에서 보강을 관리하는 옵션":::

- <span data-ttu-id="68795-124">고객 프로필의 수가 보강된 강화 세부 사항 **보기**.</span><span class="sxs-lookup"><span data-stu-id="68795-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="68795-125">강화 구성 **편집**.</span><span class="sxs-lookup"><span data-stu-id="68795-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="68795-126">**운영** 최신 데이터로 고객 프로필 업데이트 강화</span><span class="sxs-lookup"><span data-stu-id="68795-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="68795-127">예약된 새로 고침마다 자동으로 새로 고쳐지지 않도록 기존 보강을 **비활성화**.</span><span class="sxs-lookup"><span data-stu-id="68795-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="68795-128">마지막으로 성공한 새로 고침의 데이터는 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68795-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="68795-129">예약된 새로 고침마다 자동 새로 고침을 다시 시작하도록 비활성 보강을 **활성화**.</span><span class="sxs-lookup"><span data-stu-id="68795-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="68795-130">보강을 **삭제** 합니다.</span><span class="sxs-lookup"><span data-stu-id="68795-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="68795-131">목록에서 여러 가지 보강을 선택하여 한 번에 실행하거나 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68795-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="68795-132">보기 및 편집 옵션은 일괄 작업으로 사용할 수 없으며 한 번에 하나의 보강에 대해서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="68795-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="68795-133">보강 및 연결</span><span class="sxs-lookup"><span data-stu-id="68795-133">Enrichments and connections</span></span>

<span data-ttu-id="68795-134">타사 보강은 관리자가 자격 증명으로 설정하고 데이터 전송에 대한 동의를 제공하는 [연결](connections.md)을 사용하여 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="68795-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="68795-135">관리자와 기여자 모두가 보강을 구성하는 데 연결을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68795-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="68795-136">동일한 유형의 여러 보강</span><span class="sxs-lookup"><span data-stu-id="68795-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="68795-137">보강할 엔터티는 보강 구성 중에 지정되므로 프로필의 하위 집합만 보강할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68795-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="68795-138">예를 들어, 특정 세그먼트에 대해서만 데이터를 보강하십시오.</span><span class="sxs-lookup"><span data-stu-id="68795-138">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="68795-139">동일한 유형의 여러 보강을 구성하고 동일한 연결을 재사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68795-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="68795-140">일부 보강에는 만들 수 있는 동일한 유형의 보강 수에 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68795-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="68795-141">제한과 현재 사용은 **보강** 페이지에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68795-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
