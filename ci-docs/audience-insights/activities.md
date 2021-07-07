---
title: 고객 활동
description: 고객 활동을 정의하고 고객 시간 표시줄에서 봅니다.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 342aeb33f652d5d60cd25e13969766954bf56370
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304934"
---
# <a name="customer-activities"></a><span data-ttu-id="cb5d1-103">고객 활동</span><span class="sxs-lookup"><span data-stu-id="cb5d1-103">Customer activities</span></span>

<span data-ttu-id="cb5d1-104">Dynamics 365 Customer Insights에 [다양한 데이터 소스](data-sources.md)의 고객 활동을 결합하여 활동을 시간순으로 나열하는 타임라인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="cb5d1-105">Dynamics 365 앱 또는 Power BI 대시보드에 타임라인과 [고객 카드 추가 기능](customer-card-add-in.md)을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="cb5d1-106">활동 정의</span><span class="sxs-lookup"><span data-stu-id="cb5d1-106">Define an activity</span></span>

<span data-ttu-id="cb5d1-107">데이터 원본에는 여러 데이터 원본의 트랜잭션 및 활동 데이터가 있는 엔터티가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="cb5d1-108">이러한 엔터티를 식별하고 고객의 타임라인에서 보려는 활동을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="cb5d1-109">대상 활동을 포함하는 엔터티를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="cb5d1-110">고객타임 라인에 포함되려면 엔터티는 하나 이상의 **날짜** 속성 유형을 가져야 하며 **날짜** 필드가 없는 엔터티를 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="cb5d1-111">해당 엔터티가 없으면 **활동 추가** 컨트롤을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="cb5d1-112">대상 그룹 인사이트에서 **데이터** > **활동** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="cb5d1-113">**활동 추가** 를 선택하여 활동 설정 프로세스에 대한 안내 경험을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="cb5d1-114">**활동 데이터** 단계에서 다음 필드의 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="cb5d1-115">**활동 이름**: 활동 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="cb5d1-116">**엔터티**: 거래 또는 활동 데이터가 포함된 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="cb5d1-117">**기본 키**: 레코드를 고유하게 식별하는 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="cb5d1-118">중복 값, 빈 값 또는 누락된 값을 포함해서는 안됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="이름, 엔터티 및 기본 키를 사용하여 활동 데이터를 설정합니다.":::

1. <span data-ttu-id="cb5d1-120">**다음** 을 선택하여 다음 단계로 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="cb5d1-121">**관계** 단계에서 활동 데이터를 해당 고객에 연결하도록 세부 정보를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="cb5d1-122">이 단계는 엔터티 간의 연결을 시각화합니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="cb5d1-123">**첫째**: 다른 엔터티와의 관계를 설정하는 데 사용될 활동 엔터티의 외부 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="cb5d1-124">**둘째**: 활동 엔터티와 관계가 있는 해당 소스 고객 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="cb5d1-125">데이터 통합 프로세스에 사용되는 소스 고객 엔터티에만 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="cb5d1-126">**셋째**: 이 활동 항목과 선택한 소스 고객 항목 간의 관계가 이미 있는 경우 관계 이름은 읽기 전용 모드가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="cb5d1-127">그러한 관계가 없는 경우 이 상자에 입력한 이름으로 새 관계가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-127">If no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="엔터티 관계를 정의합니다.":::

1. <span data-ttu-id="cb5d1-129">**다음** 을 선택하여 다음 단계로 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="cb5d1-130">**활동 통합** 단계에서 활동 이벤트와 활동 시작 시간을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="cb5d1-131">**필수 필드**</span><span class="sxs-lookup"><span data-stu-id="cb5d1-131">**Required fields**</span></span>
      - <span data-ttu-id="cb5d1-132">**이벤트 활동**: 이 활동의 이벤트인 필드.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-132">**Event activity**: Field that is the event for this activity.</span></span>
      - <span data-ttu-id="cb5d1-133">**타임스탬프**: 활동 시작 시간을 나타내는 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="cb5d1-134">**선택 필드**</span><span class="sxs-lookup"><span data-stu-id="cb5d1-134">**Optional fields**</span></span>
      - <span data-ttu-id="cb5d1-135">**추가 세부 정보**: 이 활동에 대한 관련 정보가 있는 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      - <span data-ttu-id="cb5d1-136">**아이콘**: 이 활동 유형을 가장 잘 나타내는 아이콘입니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-136">**Icon**: Icon that best represents this activity type.</span></span>
      - <span data-ttu-id="cb5d1-137">**웹 주소**: 이 활동에 대한 정보가 있는 URL이 포함된 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="cb5d1-138">예를 들어 이 활동을 제공하는 트랜잭션 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="cb5d1-139">이 URL은 데이터 원본의 모든 필드이거나 파워 쿼리 변환을 사용하여 새 필드로 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="cb5d1-140">URL 데이터는 [API](apis.md)를 사용하여 다운스트림에서 소비될 수 있는 *통합 활동* 엔터티에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="통합 활동 엔터티에서 고객 활동 데이터를 지정합니다.":::

1. <span data-ttu-id="cb5d1-142">다음 단계로 이동하려면 **다음** 을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="cb5d1-143">**완료 및 검토** 를 선택하여 활동 유형을 **기타** 로 설정한 상태로 지금 활동을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="cb5d1-144">**활동 유형** 단계에서 활동 유형을 선택하고 선택적으로 Customer Insights의 다른 영역에서 사용하기 위해 일부 활동 유형을 의미론적으로 매핑하려는 경우 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="cb5d1-145">현재 *구독* 과 *SalesOrderLine* 활동 유형은 필드 매핑에 동의한 후 의미론적으로 매핑될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-145">Currently, *Subscription* and *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="cb5d1-146">활동 유형이 새 활동과 관련이 없는 경우 사용자 지정 활동 유형에 *기타* 또는 *새로 만들기* 를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="cb5d1-147">다음 단계로 이동하려면 **다음** 을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="cb5d1-148">**리뷰** 단계에서 선택 사항을 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="cb5d1-149">이전 단계로 돌아가 필요한 경우 정보를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-149">Go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="활동에 대해 지정된 필드를 검토하십시오.":::
   
1. <span data-ttu-id="cb5d1-151">**활동 저장** 을 선택하여 변경 사항을 적용하고 **완료** 를 선택하여 **데이터** > **활동** 으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="cb5d1-152">여기에서 타임라인에 표시하도록 설정된 활동을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="cb5d1-153">**활동** 페이지에서 **실행** 을 선택하여 활동을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="cb5d1-154">작업/프로세스 [상태에는 6가지 유형](system.md#status-types)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="cb5d1-155">또한 대부분의 프로세스는 [다른 다운스트림 프로세스에 의존](system.md#refresh-policies)합니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="cb5d1-156">프로세스 상태를 선택하여 전체 작업의 진행률에 대한 세부 사항을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="cb5d1-157">작업 중 하나를 선택한 다음 **자세히 보기** 참조를 선택하면, 처리 시간, 마지막 처리 날짜, 작업과 관련된 모든 오류 및 경고와 같은 추가 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="cb5d1-158">기존 활동 관리</span><span class="sxs-lookup"><span data-stu-id="cb5d1-158">Manage existing activities</span></span>

<span data-ttu-id="cb5d1-159">**데이터** > **활동** 에서 저장된 모든 활동을 보고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="cb5d1-160">각 활동은 소스, 엔터티 및 활동 유형에 대한 세부 사항도 포함하는 행으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="cb5d1-161">활동을 선택하면 다음 작업을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="cb5d1-162">**편집**: 검토 단계에서 활동 설정을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="cb5d1-163">이 단계에서 현재 구성의 일부 또는 전부를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="cb5d1-164">구성을 변경한 후 **활동 저장** 을 선택하고 **실행** 을 선택하여 변경 사항을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="cb5d1-165">**이름 바꾸기**: 선택한 활동에 대해 다른 이름을 입력할 수 있는 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-165">**Rename**: Opens a dialog where you can enter a different name for the selected activity.</span></span> <span data-ttu-id="cb5d1-166">**저장** 을 선택하여 변경 내용을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="cb5d1-167">**삭제**: 선택한 활동의 삭제를 확인하는 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="cb5d1-168">활동을 선택한 다음 삭제 아이콘을 선택하여 한 번에 둘 이상의 활동을 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="cb5d1-169">**삭제** 를 선택하여 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cb5d1-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
