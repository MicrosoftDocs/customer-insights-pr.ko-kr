---
title: Common Data Service 관리 레이크의 엔터티에 연결
description: Common Data Service 관리 데이터 레이크에서 데이터 가져오기
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: b1cfab40c1edb32f4a7f359e1195cfb1e879a0d5
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596967"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="14cce-103">Common Data Service 관리형 데이터 레이크의 데이터에 연결</span><span class="sxs-lookup"><span data-stu-id="14cce-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="14cce-104">이 문서는 기존 Dynamics 365 고객이 Common Data Service 관리 레이크의 분석 엔터티에 빠르게 연결할 수 있는 방법에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="14cce-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="14cce-105">Common Data Service 조직의 관리자만 관리 레이크 엔터티 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14cce-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="14cce-106">중요 사항</span><span class="sxs-lookup"><span data-stu-id="14cce-106">Important considerations</span></span>

<span data-ttu-id="14cce-107">Azure Data Lake Storage와 같은 온라인 서비스에 저장된 데이터는 Dynamics 365 Customer Insights에서 데이터가 처리 또는 저장된 위치와 다른 곳에 저장될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14cce-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="14cce-108">온라인 서비스에서 데이터를 가져오거나 이에 연결하면 해당 데이터가 Dynamics 365 Customer Insights에 전송되거나 저장될 수 있음에 동의하는 것입니다. [Microsoft 보안 센터에서 자세히 알아보십시오.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="14cce-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="14cce-109">Common Data Service 관리 레이크에 연결</span><span class="sxs-lookup"><span data-stu-id="14cce-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="14cce-110">대상 그룹 인사이트에서 **데이터** > **데이터 원본** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="14cce-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="14cce-111">**데이터 원본 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14cce-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="14cce-112">**Common Data Service에 연결** 을 선택하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14cce-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="14cce-113">데이터 원본의 **이름** 을 입력하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14cce-113">Enter a **Name** for the data source and select **Next**.</span></span> <span data-ttu-id="14cce-114">이름 지침:</span><span class="sxs-lookup"><span data-stu-id="14cce-114">Name guidelines:</span></span> 
   - <span data-ttu-id="14cce-115">문자로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="14cce-115">Start with a letter.</span></span>
   - <span data-ttu-id="14cce-116">문자와 숫자만 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="14cce-116">Use letters and numbers only.</span></span> <span data-ttu-id="14cce-117">특수 문자와 공백은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14cce-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="14cce-118">3~64자 사이에서 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="14cce-118">Use between 3 and 64 characters.</span></span>

5. <span data-ttu-id="14cce-119">Common Data Service 조직의 **서버 주소** 를 제공하고 **로그인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14cce-119">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="14cce-120">![Common Data Service 서버 주소를 입력할 대화 상자](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="14cce-120">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="14cce-121">사용 가능한 목록에서 수집할 엔터티를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14cce-121">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="14cce-122">일부 엔터티가 이미 선택된 경우 다른 Dynamics 365 응용 프로그램(예: Dynamics 365 Sales Insights 또는 Customer Service Insights)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14cce-122">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="14cce-123">선택 사항은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14cce-123">You can't change the selection.</span></span> <span data-ttu-id="14cce-124">이러한 엔티티는 데이터 원본이 생성되어야 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14cce-124">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="14cce-125">![Common Data Service 조직의 엔터티 목록을 표시하는 대화 상자](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="14cce-125">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="14cce-126">선택한 내용을 저장하여 선택한 엔터티를 Common Data Service 관리형 레이크와 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="14cce-126">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="14cce-127">새로 추가된 연결은 **데이터 원본** 페이지에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14cce-127">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="14cce-128">새로 고치기 위해 대기하고 모든 엔터티가 동기화 될 때까지 엔터티 수를 0으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="14cce-128">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="14cce-129">환경의 데이터 원본 하나만 동일한 Common Data Service 관리 레이크를 동시에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14cce-129">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="14cce-130">Common Data Service 관리 레이크 데이터 원본 편집</span><span class="sxs-lookup"><span data-stu-id="14cce-130">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="14cce-131">데이터 원본을 생성한 후에만 엔터티 선택을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14cce-131">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="14cce-132">예를 들어, 만약 추가 엔티티가 Common Data Service에 추가 되었고 당신 또한 그 것들을 가져오고 싶습니다.</span><span class="sxs-lookup"><span data-stu-id="14cce-132">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="14cce-133">다른 Common Data Service에 연결하려면 [새 데이터 원본을 만듭니다](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="14cce-133">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="14cce-134">대상 그룹 인사이트에서 **데이터** > **데이터 원본** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="14cce-134">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="14cce-135">업데이트하려는 데이터 원본 옆에 있는 줄임표를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="14cce-135">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="14cce-136">목록에서 **편집** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14cce-136">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="14cce-137">사용 가능한 엔터티 목록에서 추가 엔터티를 선택하고 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14cce-137">Select additional entities from the available list of entities and select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]