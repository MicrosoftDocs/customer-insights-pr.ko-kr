---
title: 엔터티 및 엔터티 경로 간 관계
description: 여러 데이터 원본의 항목 간에 관계를 만들고 관리합니다.
ms.date: 04/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c25bfcb8e2a8223498dd1a5e8cfb3712a40ab85e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595220"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="6c11f-103">엔터티 간 관계</span><span class="sxs-lookup"><span data-stu-id="6c11f-103">Relationships between entities</span></span>

<span data-ttu-id="6c11f-104">관계 엔터티가 한 엔터티에서 다른 엔터티로 참조할 수 있는 공통 식별자(외래 키)를 공유할 때 엔터티를 연결하고 데이터 그래프를 생성하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="6c11f-105">연결된 엔터티를 사용하면 여러 데이터 원본을 기반으로 세그먼트 및 측정값을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="6c11f-106">관계에는 다음과 같은 두 가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-106">There are two types of relationships.</span></span> <span data-ttu-id="6c11f-107">편집할 수 없는 시스템 관계 - 자동으로 생성되며 사용자가 만들고 구성한 사용자 지정 관계입니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="6c11f-108">일치 및 병합 프로세스 동안 시스템 관계 지능형 일치를 기반으로 배경에서 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="6c11f-109">이러한 관계 고객 프로필 레코드를 다른 해당 엔터티의 레코드와 연관시키는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="6c11f-110">다음 다이어그램에서는 고객 엔터티가 추가 엔터티와 일치하여 최종 고객 프로필 엔터티를 생성할 때 세 가지 시스템 관계를 만드는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6c11f-111">![관계 만들기](media/relationships-entities-merge.png "관계 만들기")</span><span class="sxs-lookup"><span data-stu-id="6c11f-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="6c11f-112">***CustomerToContact* 관계** 는 고객 엔터티와 연락처 엔터티 간에 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="6c11f-113">고객 엔터티는 연락처 엔터티 키 필드 **contactId** 와 관련되는 키 필드 **Contact_contactId** 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="6c11f-114">***CustomerToAccount* 관계** 는 고객 엔터티와 거래처 엔터티 간에 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-114">***CustomerToAccount* relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="6c11f-115">고객 엔터티는 거래처 엔터티 키 필드 **accountId** 와 관련되는 키 필드 **Account_accountId** 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="6c11f-116">***CustomerToWebAccount* 관계** 는 고객 엔터티와 WebAccount 엔터티 간에 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-116">***CustomerToWebAccount* relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="6c11f-117">고객 엔터티는 WebAccount 엔터티 키 필드 **webaccountId** 와 관련되는 키 필드 **WebAccount_webaccountId** 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="6c11f-118">관계 만들기</span><span class="sxs-lookup"><span data-stu-id="6c11f-118">Create a relationship</span></span>

<span data-ttu-id="6c11f-119">**관계** 페이지에서 사용자 지정 관계를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="6c11f-120">각 관계는 소스 엔터티(외래 키를 보유하는 엔터티)와 대상 엔터티(원본 엔터티의 외래 키가 가리키는 엔터티)로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="6c11f-121">대상 그룹 인사이트에서 **데이터** > **데이터 원본** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="6c11f-122">**새 관계** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="6c11f-123">**관계 추가** 창에 다음 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6c11f-124">![관계 세부 정보 입력](media/relationships-add.png "관계 세부 정보 입력")</span><span class="sxs-lookup"><span data-stu-id="6c11f-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="6c11f-125">**관계 이름**: 관계의 목적을 반영하는 이름입니다(예: **AccountWebLogs).**</span><span class="sxs-lookup"><span data-stu-id="6c11f-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="6c11f-126">**설명**: 관계에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="6c11f-127">**원본 엔터티**: 관계에서 원본으로 사용되는 엔터티(예: WebLog)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="6c11f-128">**카디널리티**: 원본 엔터티 레코드의 카디널리티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="6c11f-129">예를 들어 "다수"는 여러 웹블로그 레코드가 하나의 WebAccount와 관련이 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="6c11f-130">**원본 키 필드**: 원본 엔터티의 외래 키 필드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="6c11f-131">예를 들어 WebLog에는 **accountId** 외래 키 필드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="6c11f-132">**대상 엔터티**: 관계에서 대상으로 사용되는 엔터티(예: WebAccount)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="6c11f-133">**카디널리티**: 대상 엔터티 레코드의 카디널리티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="6c11f-134">예를 들어 "하나"는 여러 웹블로그 레코드가 하나의 WebAccount와 관련이 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="6c11f-135">**대상 키 필드**: 이 필드는 대상 엔터티의 키 필드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="6c11f-136">예를 들어 WebAccount에는 **accountId** 키 필드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="6c11f-137">다대일 및 일대일 관계만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="6c11f-138">다대일 관계는 두 개의 다대일 관계 및 링크 엔터티(원본 엔터티와 대상 엔터티를 연결하는 데 사용되는 엔터티)를 사용하여 다대다 관계를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="6c11f-139">관계 삭제</span><span class="sxs-lookup"><span data-stu-id="6c11f-139">Delete a relationship</span></span>

1. <span data-ttu-id="6c11f-140">대상 그룹 인사이트에서 **데이터** > **데이터 원본** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="6c11f-141">삭제하려는 관계의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="6c11f-142">**관계** 표 상단에서 **삭제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="6c11f-143">삭제를 확정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="6c11f-144">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6c11f-144">Next step</span></span>

<span data-ttu-id="6c11f-145">시스템 및 사용자 지정 관계는 더 이상 격리되지 않은 여러 데이터 원본을 기반으로 세그먼트를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c11f-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="6c11f-146">자세한 내용은 [세그먼트](segments.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6c11f-146">For more information, see [Segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]