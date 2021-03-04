---
title: 고객 활동
description: 고객 활동을 정의하고 고객 시간 표시줄에서 봅니다.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: dcef8f0547009e1488f1abe91423fa0bf5b061de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267440"
---
# <a name="customer-activities"></a><span data-ttu-id="e0331-103">고객 활동</span><span class="sxs-lookup"><span data-stu-id="e0331-103">Customer activities</span></span>

<span data-ttu-id="e0331-104">Dynamics 365 Customer Insights에서 [다양한 데이터 원본](data-sources.md)의 고객 활동을 결합하여 활동을 시간순으로 나열하는 고객 시간 표시줄을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="e0331-105">[고객 카드 추가 기능](customer-card-add-in.md)을 통해 또는 Power BI 대시보드 Dynamics 365의 고객 참여 앱에 타임라인을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="e0331-106">활동 정의</span><span class="sxs-lookup"><span data-stu-id="e0331-106">Define an activity</span></span>

<span data-ttu-id="e0331-107">데이터 원본에는 여러 데이터 원본의 트랜잭션 및 활동 데이터가 있는 엔터티가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="e0331-108">이러한 엔터티를 식별하고 고객의 타임라인에서 보려는 활동을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0331-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="e0331-109">대상 활동을 포함하는 엔터티를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0331-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="e0331-110">대상 그룹 인사이트에서 **데이터** > **활동** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="e0331-111">**활동 추가** 를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0331-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e0331-112">고객타임 라인에 포함되려면 엔터티는 하나 이상의 **날짜** 속성 유형을 가져야 하며 **날짜** 필드가 없는 엔터티를 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="e0331-113">해당 엔터티가 없으면 **활동 추가** 컨트롤을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="e0331-114">**활동 추가** 창에서 다음 필드의 값을 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0331-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="e0331-115">**엔터티**: 거래 또는 활동 데이터가 포함된 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="e0331-116">**기본 키**: 레코드를 고유하게 식별하는 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="e0331-117">중복 값, 빈 값 또는 누락된 값을 포함해서는 안됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="e0331-118">**타임스탬프**: 활동 시작 시간을 나타내는 필드를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0331-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="e0331-119">**이벤트**: 활동에 대한 이벤트 필드를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0331-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="e0331-120">**웹 주소**: 이 활동에 대한 추가 정보를 제공하는 URL을 나타내는 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="e0331-121">예를 들어 이 활동을 제공하는 트랜잭션 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="e0331-122">이 URL은 데이터 원본의 모든 필드이거나 파워 쿼리 변환을 사용하여 새 필드로 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="e0331-123">이 URL 데이터는 통합 활동 엔터티에 저장되며 API를 사용하여 다운스트림에서 소비될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="e0331-124">**세부 정보**: 선택적으로 추가 세부 사항을 위해 추가된 필드를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0331-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="e0331-125">**아이콘**: 선택적으로 이 활동을 나타내는 아이콘을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0331-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="e0331-126">**활동 유형**: 활동의 의미 정의를 가장 잘 설명하는 Common Data Model에 대한 활동 유형 참조를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="e0331-127">**관계 설정** 섹션에서 활동 데이터를 해당 고객과 연결하도록 세부 사항을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

    - <span data-ttu-id="e0331-128">**활동 엔터티 필드**: 다른 엔터티와 관계를 설정하는 데 사용될 활동 엔터티의 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-128">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="e0331-129">**고객 엔터티**: 활동 엔터티와 관계가 있는 해당 원본 고객 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-129">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="e0331-130">데이터 통합 프로세스에 사용되는 원본 고객 엔터티에만 관련될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-130">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="e0331-131">**고객 엔터티 필드**: 이 필드에는 맵 프로세스에서 선택한 원본 고객 엔터티의 기본 키가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-131">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="e0331-132">소스 고객 엔터티의이 기본 키 필드는 활동 엔터티와의 관계를 설정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-132">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="e0331-133">**이름**: 이 활동 엔터티와 선택된 원본 고객 엔터티 사이의 관계가 이미 존재하는 경우 관계 이름은 읽기 전용 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-133">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="e0331-134">그러한 관계가 존재하지 않으면 여기에 제공된 이름으로 새로운 관계가 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-134">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e0331-135">![엔터티 관계 정의](media/activities-entities-define.png "엔터티 관계 정의")</span><span class="sxs-lookup"><span data-stu-id="e0331-135">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

1. <span data-ttu-id="e0331-136">**저장** 을 선택하여 변경 내용을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="e0331-137">**활동** 페이지에서 **실행** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="e0331-138">작업/프로세스 [상태에는 6가지 유형](system.md#status-types)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="e0331-139">또한 대부분의 프로세스는 [다른 다운스트림 프로세스에 의존](system.md#refresh-policies)합니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="e0331-140">프로세스 상태를 선택하여 전체 작업의 진행률에 대한 세부 사항을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="e0331-141">작업 중 하나를 선택한 다음 **자세히 보기** 참조를 선택하면, 처리 시간, 마지막 처리 날짜, 작업과 관련된 모든 오류 및 경고와 같은 추가 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="e0331-142">활동 편집</span><span class="sxs-lookup"><span data-stu-id="e0331-142">Edit an activity</span></span>

1. <span data-ttu-id="e0331-143">대상 그룹 인사이트에서 **데이터** > **활동** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="e0331-144">편집하려는 활동 엔터티를 선택하고 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="e0331-145">또는 엔터티 행 위로 마우스를 가져간 다음 **편집** 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="e0331-146">**편집** 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="e0331-147">**활동 편집** 창에서 값을 업데이트하고 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="e0331-148">**활동** 페이지에서 **실행** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="e0331-149">활동 삭제</span><span class="sxs-lookup"><span data-stu-id="e0331-149">Delete an activity</span></span>

1. <span data-ttu-id="e0331-150">대상 그룹 인사이트에서 **데이터** > **활동** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="e0331-151">제거하려는 활동 엔터티를 선택하고 **삭제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="e0331-152">또는 엔터티 행 위로 마우스를 가져간 다음 **삭제** 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="e0331-153">또한 한 번에 여러 활동 엔터티를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e0331-154">![엔터티 관계 편집 또는 삭제](media/activities-entities-edit-delete.png "엔터티 관계 편집 또는 삭제")</span><span class="sxs-lookup"><span data-stu-id="e0331-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="e0331-155">**삭제** 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="e0331-156">삭제를 확정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0331-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]