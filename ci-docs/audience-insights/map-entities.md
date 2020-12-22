---
title: 데이터 통합 시 엔터티 매핑
description: 데이터를 매핑하여 통합 고객 프로필을 만듭니다.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: e98c7717f7707d43a9fd1fc6f6b0e9c49e4e7ee0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406300"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="e7720-103">엔터티 및 특성 매핑</span><span class="sxs-lookup"><span data-stu-id="e7720-103">Map entities and attributes</span></span>

<span data-ttu-id="e7720-104">**매핑** 은 대상 그룹 인사이트의 데이터 통합 프로세스의 첫 번째 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="e7720-105">매핑은 다음 세 단계로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="e7720-106">*엔터티 선택*: 고객에 대한 보다 완전한 정보가 있는 데이터 집합으로 이어지는 결합 가능한 엔터티를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="e7720-107">*특성 선택*: 각 엔터티에 대해 *일치* 및 *병합* 단계에서 결합하고 조정할 열을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="e7720-108">이러한 열은 *특성* 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="e7720-109">*기본 키 및 의미 유형 선택*: 각 엔티티에 대해 해당 엔티티의 기본 키로 정의 할 특성을 식별하고 각 특성에 대해 해당 속성을 가장 잘 설명하는 의미 유형을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="e7720-110">일반적인 데이터 통합 흐름에 대한 자세한 내용은 [통합](data-unification.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e7720-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="e7720-111">첫 번째 엔터티 선택</span><span class="sxs-lookup"><span data-stu-id="e7720-111">Select the first entities</span></span>

1. <span data-ttu-id="e7720-112">대상 그룹 인사이트에서 **데이터** > **통합** > **매핑** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="e7720-113">**엔터티 선택** 을 선택하여 매핑 단계를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="e7720-114">사용할 엔티티와 특성을 선택합니다. *시합* 과 *병합* 단계.</span><span class="sxs-lookup"><span data-stu-id="e7720-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="e7720-115">엔터티에서 개별적으로 필요한 특성을 선택하거나 엔터티의 모든 특성을 포함 할 수 있습니다. **모든 필드 포함** 엔터티 수준의 확인란.</span><span class="sxs-lookup"><span data-stu-id="e7720-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="e7720-116">데이터 통합 프로세스를 활용하려면 두 개 이상의 엔터티를 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e7720-117">![엔터티 추가 예](media/data-manager-configure-map-add-entities-example.png "엔터티 추가 예")</span><span class="sxs-lookup"><span data-stu-id="e7720-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="e7720-118">이 예에서 우리는 **전자 상거래 연락처** 와 **충성 고객** 엔터티를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="e7720-119">이러한 엔터티를 선택하면 어떤 온라인 비즈니스 고객이 로열티 프로그램 회원인지에 대한 통찰력을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="e7720-120">매핑하려는 필수 특성을 선택하기 위해 모든 특성 및 엔터티에서 키워드를 검색 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e7720-121">![검색 필드 예](media/data-manager-configure-map-search-fields-example.png "검색 필드 예")</span><span class="sxs-lookup"><span data-stu-id="e7720-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="e7720-122">**적용** 을 선택하여 선택 사항을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="e7720-123">특성에 대한 기본 키 및 의미 유형 선택</span><span class="sxs-lookup"><span data-stu-id="e7720-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="e7720-124">엔터티를 선택한 후 **맵** 페이지에는 리뷰를 위해 선택한 엔터티가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="e7720-125">엔터티의 기본 키를 정의하고 엔터티의 특성에 대한 의미 유형을 식별하십시오.</span><span class="sxs-lookup"><span data-stu-id="e7720-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="e7720-126">**기본 키**: 각 엔터티의 기본 키로 하나의 특성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="e7720-127">특성이 유효한 기본 키가 되려면 중복 값, 누락 된 값 또는 null 값을 포함하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="e7720-128">문자열, 정수 및 GUID 데이터 형식 특성은 기본 키로 지원되며 선택할 수 있는 필드에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="e7720-129">**특성 의미 유형**: 이메일 주소 또는 이름과 같은 특성 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="e7720-130">스마트 예측 의미 체계에 AI 모델을 사용하고 시간을 절약하고 정확도를 높이려면 **지능형 매핑** 을 **사용 설정** 하세요.</span><span class="sxs-lookup"><span data-stu-id="e7720-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="e7720-131">지능형 매핑은 **유형** 필드에서 AI 기반 의미론 권장 사항을 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="e7720-132">**사용 중지** 로 설정하면 정기적인 매핑 권장 사항을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="e7720-133">사용 가능한 옵션 목록에서 의미 유형을 선택하고 제안 된 선택을 재정의 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e7720-134">![속성 유형 및 의미 예측](media/data-manager-configure-map-add-attributes-semantic-prediction.png "특성 유형 및 의미 예측")</span><span class="sxs-lookup"><span data-stu-id="e7720-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="e7720-135">사용자 지정 의미 유형을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="e7720-136">해당 특성의 유형 필드를 선택하고 사용자 지정 의미 유형 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="e7720-137">이 방법으로 시스템이 자동 식별한 특성 유형을 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="e7720-138">의미 유형이 자동으로 식별되는 모든 특성은 **매핑된 필드 검토** 부분.</span><span class="sxs-lookup"><span data-stu-id="e7720-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="e7720-139">이러한 특성과 의미 유형은 데이터 통합의 통합 단계에서 엔터티를 결합하는데 사용되므로 리뷰합니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="e7720-140">의미 체계 유형에 자동으로 매핑되지 않는 특성은 **매핑되지 않은 필드의 데이터 정의** 섹션.</span><span class="sxs-lookup"><span data-stu-id="e7720-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="e7720-141">매핑되지 않은 특성에 대한 의미 유형 필드를 선택하거나 사용자 정의 특성 유형 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e7720-142">![기본 키 및 특성 유형](media/data-manager-configure-map-add-attributes.png "기본 키 및 특성 유형")</span><span class="sxs-lookup"><span data-stu-id="e7720-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="e7720-143">고객 카드에 고객 이름을 채우려면 하나의 필드가 Person.FullName 의미 유형에 매핑되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="e7720-144">그렇지 않으면 고객 카드는 이름이 없는 것으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="e7720-145">특성 및 엔터티 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="e7720-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="e7720-146">**통합** > **맵** 에서 **필드 편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="e7720-147">**필드 편집** 창에서 특성 및 엔터티를 추가하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="e7720-148">검색 또는 스크롤을 사용하여 관심있는 특성 및 엔터티를 찾아 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="e7720-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="e7720-149">이미 일치된 특성이나 엔터티는 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e7720-150">![특성 추가 또는 제거](media/configure-data-map-edit.png "특성 추가 또는 제거")</span><span class="sxs-lookup"><span data-stu-id="e7720-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="e7720-151">**적용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="e7720-152">프로필에 이미지 추가</span><span class="sxs-lookup"><span data-stu-id="e7720-152">Add images to profiles</span></span>

<span data-ttu-id="e7720-153">엔터티에 공개적으로 사용 가능한 프로필 이미지 또는 로고에 대한 URL이 포함되어 있으면 이를 통합 고객 프로필에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="e7720-154">엔터티를 선택하고 프로필 이미지의 URL이 포함된 필드를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="e7720-155">**유형** 입력 필드에 다음 값을 수동으로 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="e7720-156">사람의 경우: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="e7720-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="e7720-157">조직의 경우: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="e7720-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="e7720-158">통합 단계를 계속하고 이미지 URL이 포함된 특성이 [통합 ](merge-entities.md)단계.</span><span class="sxs-lookup"><span data-stu-id="e7720-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="e7720-159">조직의 특성 설정</span><span class="sxs-lookup"><span data-stu-id="e7720-159">Set attributes for organizations</span></span>

<span data-ttu-id="e7720-160">조직(미리 보기)의 경우 특성 유형은 "Organization.Name"에 매핑되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="e7720-161">![기본 키 및 특성 유형 B2B](media/configure-data-map-edit-b2b.png "기본 키 및 특성 유형 B2B")</span><span class="sxs-lookup"><span data-stu-id="e7720-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="e7720-162">다음 단계</span><span class="sxs-lookup"><span data-stu-id="e7720-162">Next step</span></span>

<span data-ttu-id="e7720-163">데이터 통합 프로세스의 일부로 **일치** 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e7720-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="e7720-164">이 단계에 대해 배우려면 [**일치**](match-entities.md)를 방문하십시오.</span><span class="sxs-lookup"><span data-stu-id="e7720-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="e7720-165">다음 비디오를 확인하십시오. [시작하기: 통합 고객 프로필 만들기](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="e7720-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>
