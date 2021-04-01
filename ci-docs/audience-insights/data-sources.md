---
title: 데이터를 수집할 데이터 원본 사용
description: 다양한 소스에서 데이터를 가져 오는 방법을 알아 봅니다.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 780dc61a82d6ed9856a37dc8f164fa946d982bbe
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595955"
---
# <a name="data-sources-overview"></a><span data-ttu-id="8e21c-103">데이터 원본 개요</span><span class="sxs-lookup"><span data-stu-id="8e21c-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="8e21c-104">Dynamics 365 Customer Insights의 대상 그룹 인사이트 기능은 광범위한 원본 집합의 데이터에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e21c-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="8e21c-105">데이터 원본에 연결하는 과정을 종종 *데이터 수집* 프로세스라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e21c-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="8e21c-106">데이터를 수집 한 후, [통합화](data-unification.md) 하고 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e21c-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="8e21c-107">데이터 원본 추가</span><span class="sxs-lookup"><span data-stu-id="8e21c-107">Add a data source</span></span>

<span data-ttu-id="8e21c-108">선택한 옵션에 따라 데이터 원본를 추가하는 방법에 대한 자세한 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e21c-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="8e21c-109">세 가지 주요 방법으로 데이터 원본를 추가 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e21c-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="8e21c-110">수십 개의 파워 쿼리 커넥터를 통해</span><span class="sxs-lookup"><span data-stu-id="8e21c-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="8e21c-111">Common Data Model 폴더로 부터</span><span class="sxs-lookup"><span data-stu-id="8e21c-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="8e21c-112">내 Common Data Service 레이크로 부터</span><span class="sxs-lookup"><span data-stu-id="8e21c-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="8e21c-113">아직 온-프레미스 데이터 소스의 데이터를 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8e21c-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="8e21c-114">수집 된 데이터 검토</span><span class="sxs-lookup"><span data-stu-id="8e21c-114">Review ingested data</span></span>

<span data-ttu-id="8e21c-115">수집 된 각 데이터 원본의 이름, 해당 상태 및 해당 소스에 대한 데이터가 마지막으로 새로 고쳐진 시간이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e21c-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="8e21c-116">모든 열을 기준으로 데이터 원본 목록을 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e21c-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8e21c-117">![데이터 원본 추가](media/configure-data-datasource-added.png "데이터 원본 추가")</span><span class="sxs-lookup"><span data-stu-id="8e21c-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="8e21c-118">상태</span><span class="sxs-lookup"><span data-stu-id="8e21c-118">Status</span></span>  |<span data-ttu-id="8e21c-119">설명</span><span class="sxs-lookup"><span data-stu-id="8e21c-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="8e21c-120">성공</span><span class="sxs-lookup"><span data-stu-id="8e21c-120">Successful</span></span>   |<span data-ttu-id="8e21c-121">**새로 고침됨** 열에 데이터 원본에 시간이 언급되면 성공적으로 수집되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8e21c-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="8e21c-122">시작되지 않음</span><span class="sxs-lookup"><span data-stu-id="8e21c-122">Not started</span></span>   |<span data-ttu-id="8e21c-123">데이터 원본에는 아직 수집된 데이터가 없거나 아직 초안 모드에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e21c-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="8e21c-124">새로 고침</span><span class="sxs-lookup"><span data-stu-id="8e21c-124">Refreshing</span></span>    |<span data-ttu-id="8e21c-125">데이터 수집이 진행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="8e21c-125">Data ingestion is in progress.</span></span> <span data-ttu-id="8e21c-126">**작업** 열에서 **새로 고침 중지** 를 선택하여 이 작업을 취소할 수 있습니다 .</span><span class="sxs-lookup"><span data-stu-id="8e21c-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="8e21c-127">데이터 원본의 새로 고침을 중지하면 마지막 새로 고침 상태로 되돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="8e21c-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="8e21c-128">실패함</span><span class="sxs-lookup"><span data-stu-id="8e21c-128">Failed</span></span>     |<span data-ttu-id="8e21c-129">데이터 수집에 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="8e21c-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="8e21c-130">데이터 원본의 **상태** 열에서 값을 선택하여 자세한 내용을 검토하십시오.</span><span class="sxs-lookup"><span data-stu-id="8e21c-130">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="8e21c-131">**진행 세부 정보** 창에서 **데이터 원본** 을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="8e21c-131">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="8e21c-132">오류 세부 정보 및 다운스트림 프로세스 업데이트를 포함한 새로 고침 상태에 대한 자세한 내용을 보려면 **세부 정보 보기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8e21c-132">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="8e21c-133">데이터 로딩에 약간 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e21c-133">Loading data can take some time.</span></span> <span data-ttu-id="8e21c-134">성공적으로 새로 고친 후 수집된 데이터는 **엔터티** 페이지에서 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e21c-134">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="8e21c-135">자세한 내용은 [엔터티](entities.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8e21c-135">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="8e21c-136">데이터 원본 새로 고침</span><span class="sxs-lookup"><span data-stu-id="8e21c-136">Refresh a data source</span></span>

<span data-ttu-id="8e21c-137">데이터 원본은 자동 일정에 따라 새로 고쳐 지거나 필요에 따라 수동으로 새로 고칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e21c-137">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="8e21c-138">**관리** > **시스템** > [**일정**](system.md#schedule-tab)으로 이동하여 수집된 모든 데이터 원본의 예약된 새로 고침을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8e21c-138">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="8e21c-139">요청 시 데이터 원본을 새로 고침하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="8e21c-139">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="8e21c-140">대상 그룹 인사이트에서 **데이터** > **데이터 원본** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8e21c-140">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="8e21c-141">새로 고치려는 데이터 원본 옆에 있는 세로 줄임표를 선택하고 드롭다운 목록에서 **새로 고침** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8e21c-141">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="8e21c-142">데이터 원본은 이제 수동 새로 고침을 위해 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e21c-142">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="8e21c-143">데이터 원본을 새로 고침하면 엔터티 스키마와 데이터 원본에 지정된 모든 엔티티의 데이터가 모두 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e21c-143">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="8e21c-144">기존 새로 고침을 취소하고 데이터 원본이 마지막 새로 고침 상태로 되돌리려면 **새로 고침 중지** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8e21c-144">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="8e21c-145">데이터 원본 삭제</span><span class="sxs-lookup"><span data-stu-id="8e21c-145">Delete a data source</span></span>

1. <span data-ttu-id="8e21c-146">대상 그룹 인사이트에서 **데이터** > **데이터 원본** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8e21c-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="8e21c-147">제거하려는 데이터 원본 옆에 있는 세로 줄임표를 선택하고 드롭다운 메뉴에서 **삭제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8e21c-147">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="8e21c-148">삭제를 확정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e21c-148">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]