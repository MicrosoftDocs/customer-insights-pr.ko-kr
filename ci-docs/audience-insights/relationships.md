---
title: 엔터티 및 엔터티 경로 간 관계
description: 여러 데이터 원본의 항목 간에 관계를 만들고 관리합니다.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171172"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="cc381-103">엔터티 간 관계</span><span class="sxs-lookup"><span data-stu-id="cc381-103">Relationships between entities</span></span>

<span data-ttu-id="cc381-104">관계는 엔터티를 연결하고 엔터티가 공통 식별자인 외래 키를 공유할 때 데이터 그래프를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="cc381-105">이 외래 키는 한 엔터티에서 다른 엔터티로 참조될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="cc381-106">연결된 엔터티를 사용하면 여러 데이터 원본을 기반으로 세그먼트 및 측정값을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="cc381-107">관계에는 세 가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="cc381-108">데이터 통합 프로세스의 일부로 시스템에서 만들어진 편집 불가능한 시스템 관계</span><span class="sxs-lookup"><span data-stu-id="cc381-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="cc381-109">데이터 원본 수집에서 자동으로 만들어진 편집 불가능한 상속된 관계</span><span class="sxs-lookup"><span data-stu-id="cc381-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="cc381-110">사용자가 만들고 구성한 편집 가능한 사용자 지정 관계</span><span class="sxs-lookup"><span data-stu-id="cc381-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="cc381-111">편집 불가능한 시스템 관계</span><span class="sxs-lookup"><span data-stu-id="cc381-111">Non-editable system relationships</span></span>

<span data-ttu-id="cc381-112">데이터 통합 과정에서 시스템 관계는 지능형 매칭을 기반으로 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="cc381-113">이러한 관계 고객 프로필 레코드를 해당 레코드와 연관시키는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="cc381-114">다음 다이어그램은 세 가지 시스템 기반 관계의 생성을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="cc381-115">고객 엔터티는 다른 엔터티와 매칭되어 통합 *고객* 엔터티를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="3개의 1-n 관계가 있는 고객 엔터티에 대한 관계 경로의 다이어그램.":::

- <span data-ttu-id="cc381-117">***CustomerToContact* 관계** 는 *고객* 엔터티와 *연락처* 엔터티 간에 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="cc381-118">*고객* 엔터티는 *연락처* 엔터티 키 필드 **contactID** 와 관련되는 키 필드 **Contact_contactID** 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="cc381-119">***CustomerToAccount* 관계** 는 *고객* 엔터티와 *거래처* 엔터티 간에 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="cc381-120">*고객* 엔터티는 *거래처* 엔터티 키 필드 **accountID** 와 관련되는 키 필드 **Account_accountID** 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="cc381-121">***CustomerToWebAccount* 관계** 는 *고객* 엔터티와 *WebAccount* 엔터티 간에 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="cc381-122">*고객* 엔터티는 *WebAccount* 엔터티 키 필드 **webaccountID** 와 관련되는 키 필드 **WebAccount_webaccountID** 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="cc381-123">편집 불가능한 상속된 관계</span><span class="sxs-lookup"><span data-stu-id="cc381-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="cc381-124">데이터 수집 프로세스 중에 시스템은 기존 관계의 데이터 원본을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="cc381-125">관계가 없는 경우 시스템이 자동으로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="cc381-126">이러한 관계는 다운스트림 프로세스에서도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="cc381-127">사용자 지정 관계 만들기</span><span class="sxs-lookup"><span data-stu-id="cc381-127">Create a custom relationship</span></span>

<span data-ttu-id="cc381-128">관계는 외래 키를 포함하는 *소스 엔터티* 와 소스 엔터티의 외래 키가 가리키는 *대상 엔터티* 로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="cc381-129">대상 그룹 인사이트에서 **데이터** > **데이터 원본** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="cc381-130">**새 관계** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="cc381-131">**새 관계** 창에 다음 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="빈 입력 필드가 있는 새 관계 측면 창.":::

   - <span data-ttu-id="cc381-133">**관계 이름**: 관계의 목적을 나타내는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="cc381-134">예: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="cc381-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="cc381-135">**설명**: 관계에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="cc381-136">**소스 엔터티**: 관계에서 소스로 사용되는 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="cc381-137">예: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="cc381-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="cc381-138">**대상 엔터티**: 관계에서 대상으로 사용되는 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="cc381-139">예: 고객.</span><span class="sxs-lookup"><span data-stu-id="cc381-139">Example: Customer.</span></span>
   - <span data-ttu-id="cc381-140">**소스 카디널리티** : 소스 엔터티의 카디널리티를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="cc381-141">카디널리티는 집합에서 가능한 요소 수를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="cc381-142">항상 대상 카디널리티와 관련됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="cc381-143">**하나** 와 **다수** 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="cc381-144">다대일 및 일대일 관계만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="cc381-145">다대일: 여러 소스 레코드가 하나의 대상 레코드와 관련될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="cc381-146">예: 단일 고객의 여러 지원 서비스 케이스.</span><span class="sxs-lookup"><span data-stu-id="cc381-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="cc381-147">일대일: 단일 소스 레코드가 하나의 대상 레코드와 관련됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="cc381-148">예: 단일 고객에 대한 하나의 로열티 ID.</span><span class="sxs-lookup"><span data-stu-id="cc381-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="cc381-149">다대다 관계는 두 개의 다대일 관계와 소스 엔터티 및 대상 엔터티를 연결하는 연결 엔터티를 사용하여 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="cc381-150">**카디널리티**: 대상 엔터티 레코드의 카디널리티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="cc381-151">**소스 키 필드**: 소스 엔터티의 외래 키 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="cc381-152">예: SupportCase는 CaseID를 외래 키 필드로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="cc381-153">**대상 키 필드**:대상 엔터티의 키 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="cc381-154">예시 고객은 **CustomerID** 키 필드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="cc381-155">**저장** 을 선택하여 사용자 지정 관계를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="cc381-156">관계 보기</span><span class="sxs-lookup"><span data-stu-id="cc381-156">View relationships</span></span>

<span data-ttu-id="cc381-157">관계 페이지에는 만들어진 모든 관계가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="cc381-158">각 행은 관계를 나타내며 소스 엔터티, 대상 엔터티 및 카디널리티에 대한 세부 정보도 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="관계 페이지의 작업 표시줄에 있는 관계 및 옵션 목록입니다.":::

<span data-ttu-id="cc381-160">이 페이지는 기존 및 신규 관계에 대한 옵션 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="cc381-161">**새 관계:** [사용자 지정 관계 만들기](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="cc381-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="cc381-162">**시각화 도우미**: [관계 시각화 도우미 탐색](#explore-the-relationship-visualizer)을 통해 기존 관계 및 해당 카디널리티의 네트워크 다이어그램을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="cc381-163">**필터링 기준**: 목록에 표시할 관계 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="cc381-164">**관계 검색**: 관계의 속성에 대한 텍스트 기반 검색을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="cc381-165">관계 시각화 도우미 탐색</span><span class="sxs-lookup"><span data-stu-id="cc381-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="cc381-166">관계 시각화 도우미는 연결된 엔터티와 해당 카디널리티 간의 기존 관계에 대한 네트워크 다이어그램을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="cc381-167">보기를 사용자 지정하려면 상자를 캔버스에서 끌어 상자의 위치를 변경하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="관련 엔터티 간의 연결이 있는 관계 시각화 도우미 네트워크 다이어그램의 스크린샷입니다.":::

<span data-ttu-id="cc381-169">사용 가능한 옵션:</span><span class="sxs-lookup"><span data-stu-id="cc381-169">Available options:</span></span> 
- <span data-ttu-id="cc381-170">**이미지로 내보내기**: 현재 보기를 이미지 파일로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="cc381-171">**가로/세로 레이아웃으로 변경** : 엔터티 및 관계의 정렬 방식을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="cc381-172">**편집**: 편집 창에서 사용자 지정 관계의 속성을 업데이트하고 변경 사항을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="cc381-173">기존 관계 관리</span><span class="sxs-lookup"><span data-stu-id="cc381-173">Manage existing relationships</span></span> 

<span data-ttu-id="cc381-174">관계 페이지에서 각 관계는 행으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="cc381-175">관계를 선택하고 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="cc381-176">**편집**: 편집 창에서 사용자 지정 관계의 속성을 업데이트하고 변경 사항을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="cc381-177">**삭제**: 사용자 지정 관계를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="cc381-178">**보기**: 시스템 생성 및 상속된 관계 보기.</span><span class="sxs-lookup"><span data-stu-id="cc381-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="cc381-179">다음 단계</span><span class="sxs-lookup"><span data-stu-id="cc381-179">Next step</span></span>

<span data-ttu-id="cc381-180">시스템 및 사용자 지정 관계는 더 이상 격리되지 않은 여러 데이터 원본을 기반으로 한 [세그먼트 만들기](segments.md)에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc381-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
