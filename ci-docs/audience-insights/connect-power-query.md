---
title: 파워 쿼리 커넥터를 통해 데이터 수집
description: 파워 쿼리를 기반으로 하는 데이터 원본용 커넥터.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8a170cc5b64b4b383501021232c83948e838a0e2
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406287"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="0405f-103">파워 쿼리 데이터 원본에 연결</span><span class="sxs-lookup"><span data-stu-id="0405f-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="0405f-104">파워 쿼리는 데이터를 수집하기위한 광범위한 커넥터 세트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="0405f-105">이러한 커넥터의 대부분은 Dynamics 365 Customer Insights의 지원을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="0405f-106">파워 쿼리 커넥터를 기반으로 데이터 소스를 추가하는 것은 일반적으로 다음 섹션에 설명된 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="0405f-107">그러나 사용하는 커넥터에 따라 다른 정보가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="0405f-108">자세한 내용은 개별 커넥터에 대한 [파워 쿼리 커넥터 참조 ](https://docs.microsoft.com/power-query/connectors/) 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0405f-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="0405f-109">새 데이터 원본 만들기</span><span class="sxs-lookup"><span data-stu-id="0405f-109">Create a new data source</span></span>

1. <span data-ttu-id="0405f-110">대상 그룹 인사이트에서 **데이터** > **데이터 원본** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="0405f-111">**데이터 원본 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="0405f-112">**데이터 가져오기** 방법을 선택하고 **다음** 을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="0405f-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="0405f-113">데이터 원본을 위해 **이름** 을 제공하고 데이터 원본 생성을 위해 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span>

1. <span data-ttu-id="0405f-114">[사용 가능한 커넥터](#available-power-query-data-sources) 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-114">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="0405f-115">해당 예로, **텍스트/CSV** 커넥터를 선택했습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-115">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="0405f-116">선택한 커넥터에 대해 **연결 설정** 에서 필요한 세부 정보를 입력하고 데이터 미리보기를 위해 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-116">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="0405f-117">**변환 데이터** 선택.</span><span class="sxs-lookup"><span data-stu-id="0405f-117">Select **Transform data**.</span></span> <span data-ttu-id="0405f-118">이 단계에서는 데이터 원본에 엔터티를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-118">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="0405f-119">엔터티는 데이터 세트입니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-119">Entities are datasets.</span></span> <span data-ttu-id="0405f-120">여러 데이터 집합을 포함하는 데이터베이스가 있는 경우 각 데이터 집합은 자체 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-120">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="0405f-121">**파워 쿼리-검색어 수정** 대화 상자를 통해 데이터를 검토하고 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-121">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="0405f-122">선택한 데이터 원본에서 식별된 시스템이 왼쪽 창에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-122">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0405f-123">![대화 쿼리 편집](media/data-manager-configure-edit-queries.png "대화 쿼리 편집")</span><span class="sxs-lookup"><span data-stu-id="0405f-123">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="0405f-124">데이터를 변환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-124">You can also transform your data.</span></span> <span data-ttu-id="0405f-125">편집하거나 변환할 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-125">Select an entity to edit or transform.</span></span> <span data-ttu-id="0405f-126">파워 쿼리 창의 옵션을 사용하여 변형을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-126">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="0405f-127">각 변환은 **적용 단계** 아래에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-127">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="0405f-128">파워 쿼리는 사전 빌드된 다양한 변환 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-128">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="0405f-129">자세한 내용은 [파워 쿼리 변환](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0405f-129">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="0405f-130">**쿼리 편집** 대화 상자에서 **데이터 가져 오기** 를 선택하여 데이터 원본에 엔터티를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-130">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="0405f-131">이러한 변환은 적극 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-131">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="0405f-132">CSV 파일에서 데이터를 수집하는 경우 첫 번째 행에는 종종 헤더가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-132">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="0405f-133">**테이블 변환** 으로 이동해 **머리글을 첫번째 행으로 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-133">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="0405f-134">데이터 유형이 적절하게 설정되었는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="0405f-134">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="0405f-135">파워 쿼리 창 하단에 있는 **저장** 을 선택하여 변환을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-135">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="0405f-136">저장하면 후에, **데이터** > **데이터 소스** 에서 데이터 원본를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-136">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="0405f-137">**데이터 소스** 페이지에서 새 데이터 소스가 **새로 고침** 상태로 보여집니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-137">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="0405f-138">사용 가능한 파워 쿼리 데이터 소스</span><span class="sxs-lookup"><span data-stu-id="0405f-138">Available Power Query data sources</span></span>

<span data-ttu-id="0405f-139">Customer Insights로 데이터를 가져 오기 위해 선택할 수 있는 [파워 쿼리 커넥터 참조](https://docs.microsoft.com/power-query/connectors/) 최신 커넥터 목록을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0405f-139">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="0405f-140">**Customer Insights(데이터 흐름)** 열에 확인 표시가 있는 커넥터는 파워 쿼리를 기반으로 새 데이터 소스를 만드는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-140">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="0405f-141">특정 커넥터의 문서를 검토하여 전제 조건, 제한 사항 및 기타 세부 사항에 대해 자세히 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="0405f-141">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="0405f-142">파워 쿼리 데이터 소스 수정</span><span class="sxs-lookup"><span data-stu-id="0405f-142">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="0405f-143">현재 앱 프로세스 중 하나에서 사용 중인 데이터 원본을 변경하지 못할 수도 있습니다(예를 들어, *분할*, *일치* 또는 *병합*).</span><span class="sxs-lookup"><span data-stu-id="0405f-143">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="0405f-144">**설정** 페이지를 사용하여 각 활성 프로세스의 진행 상황을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-144">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="0405f-145">프로세스가 완료되면 **데이터 원본** 페이지로 돌아가 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-145">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="0405f-146">대상 그룹 인사이트에서 **데이터** > **데이터 원본** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="0405f-147">변경하려는 데이터 원본 옆에 있는 세로 줄임표를 선택하고 드롭다운 메뉴에서 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-147">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0405f-148">![편집 옵션](media/edit-option-data-sources.png "편집 옵션")</span><span class="sxs-lookup"><span data-stu-id="0405f-148">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="0405f-149">[새 데이터 원본 만들기](#create-a-new-data-source) 섹션에 설명된 대로 **파워 쿼리-검색어 수정** 대화상자에서 변경사항 및 변환을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-149">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="0405f-150">변경 내용을 저장하기 위해 편집을 완료한 후 파워 쿼리에서 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-150">Select **Save** in Power Query after completing your edits to save your changes.</span></span>
