---
title: 파워 쿼리 기반 데이터 원본에 대한 증분 새로 고침
description: 파워 쿼리를 기반 대규모 데이터 소스의 신규 및 업데이트 데이터 새로 고침.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d4b01be75d25fa0e120904924a193171eefec579
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268556"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="fa362-103">파워 쿼리 기반 데이터 원본에 대한 증분 새로 고침 | Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="fa362-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="fa362-104">데이터 소스 증분 새로 고침은 다음과 같은 이점을 제공합니다:</span><span class="sxs-lookup"><span data-stu-id="fa362-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="fa362-105">**빠른 새로 고침** - 변경된 데이터만 새로 고침됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa362-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="fa362-106">예를 들어 지난 5일 동안의 과거 데이터 집합만 새로 고칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa362-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="fa362-107">**신뢰성 향상** - 새로 고침이 작을수록 휘발성 원본 시스템에 대한 연결을 오랫동안 유지할 필요가 없으므로 연결 문제의 위험이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa362-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="fa362-108">**리소스 소비 감소** - 전체 데이터의 일부만 새로 고치면 컴퓨팅 리소스를 보다 효율적으로 사용하고 환경 공간이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa362-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="fa362-109">증분 새로 고침 구성</span><span class="sxs-lookup"><span data-stu-id="fa362-109">Configure incremental refresh</span></span>

<span data-ttu-id="fa362-110">대상 그룹 인사이트를 사용하면 증분 수집을 지원하는 파워 쿼리를 통해 가져온 데이터 원본을 증분 새로 고침할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa362-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="fa362-111">예를 들어 날짜 및 시간 필드가 있는 Azure SQL 데이터베이스는 데이터 레코드가 마지막으로 업데이트된 시간을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fa362-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="fa362-112">[파워 쿼리를 기반으로 새 데이터 원본를 만듭니다](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="fa362-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="fa362-113">데이터 원본의 이름을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fa362-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="fa362-114">Azure SQL 데이터베이스와 같이 증분 새로 고침을 지원하는 데이터 원본을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="fa362-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="fa362-115">수집할 엔터티 또는 테이블을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fa362-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="fa362-116">변환 단계를 완료하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fa362-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="fa362-117">**증분 새로 고침 설정** 대화 상자에서 **설정** 을 선택하여 **증분 새로 고침 설정** 을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fa362-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="fa362-118">**건너 뛰기** 를 선택하면 데이터 원본은 전체 데이터 집합을 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="fa362-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="fa362-119">기존 데이터 원본을 편집하여 나중에 증분 새로 고침을 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa362-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="fa362-120">**증분 새로 고침 설정** 에서 데이터 원본을 만들 때 선택한 모든 엔터티에 대해 증분 새로 고침을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="fa362-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fa362-121">![증분 새로 고침을 위해 데이터 원본에서 엔터티 구성](media/incremental-refresh-settings.png "증분 새로 고침을 위해 데이터 원본에서 엔터티 구성")</span><span class="sxs-lookup"><span data-stu-id="fa362-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="fa362-122">엔터티를 선택하고 다음 세부 사항을 제공하십시오.</span><span class="sxs-lookup"><span data-stu-id="fa362-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="fa362-123">**기본 키 정의**: 엔터티 또는 테이블의 기본 키를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="fa362-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="fa362-124">**"마지막 업데이트" 필드 정의**: 이 필드에는 날짜 또는 시간 유형의 특성만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa362-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="fa362-125">레코드가 마지막으로 업데이트 된 시점을 나타내는 특성을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="fa362-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="fa362-126">증분 새로 고침 시간 프레임 내에서 레코드를 식별하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa362-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="fa362-127">**업데이트 확인 간격**: 증분 새로 고침 시간 프레임의 기간을 지정하십시오.</span><span class="sxs-lookup"><span data-stu-id="fa362-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="fa362-128">**저장** 을 선택하여 데이터 원본의 생성을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="fa362-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="fa362-129">초기 데이터 새로 고침은 전체 새로 고침입니다.</span><span class="sxs-lookup"><span data-stu-id="fa362-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="fa362-130">이후에 증분 데이터 새로 고침은 이전 단계에서 구성한 대로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa362-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]