---
title: Customer Insights에서 다른 서비스에 대한 연결.
description: 다른 서비스와 데이터를 공유합니다.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 17e04b243e9b3d4375c86f5a890a18be35956835
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304980"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="4d9c4-103">연결(프리뷰) 개요</span><span class="sxs-lookup"><span data-stu-id="4d9c4-103">Connections (preview) overview</span></span>

<span data-ttu-id="4d9c4-104">연결은 Customer Insights와의 데이터 공유를 가능하게 하는 핵심입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="4d9c4-105">각 연결은 특정 서비스와 데이터 공유를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="4d9c4-106">연결은 [타사 보강 구성](enrichment-hub.md)과 [내보내기 구성](export-destinations.md)의 기반이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="4d9c4-107">동일한 연결을 여러 번 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="4d9c4-108">예를 들어 Dynamics 365 Marketing에 대한 하나의 연결은 여러 내보내기에 대해 작동하고 하나의 Leadspace 연결은 여러 보강에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="4d9c4-109">**관리자** > **연결** 로 이동하여 연결을 만들고 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="4d9c4-110">**연결** 탭은 모든 활성 연결을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="4d9c4-111">목록에는 각 연결에 대한 행이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="4d9c4-112">빠른 개요, 설명을 확인하고 **발견** 탭에서 각 확장성 옵션으로 수행할 수 있는 작업을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="4d9c4-113">내보내기</span><span class="sxs-lookup"><span data-stu-id="4d9c4-113">Exports</span></span>

<span data-ttu-id="4d9c4-114">관리자만 새 연결을 구성할 수 있지만 기여자에게 기존 연결을 사용할 수 있는 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="4d9c4-115">관리자는 데이터가 이동할 수 있는 위치를 제어하고 기여자는 필요에 맞는 페이로드와 빈도를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="4d9c4-116">자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="4d9c4-117">보강</span><span class="sxs-lookup"><span data-stu-id="4d9c4-117">Enrichments</span></span>

<span data-ttu-id="4d9c4-118">관리자만 새 연결을 구성 할 수 있지만 생성된 연결은 관리자와 기여자 모두가 항상 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="4d9c4-119">관리자는 자격 증명을 관리하고 데이터 전송에 동의합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="4d9c4-120">그런 다음 관리자와 기여자 모두가 연결을 보강하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="4d9c4-121">새 연결 추가</span><span class="sxs-lookup"><span data-stu-id="4d9c4-121">Add a new connection</span></span>

<span data-ttu-id="4d9c4-122">연결을 추가하려면 [관리자 권한](permissions.md)이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="4d9c4-123">다른 Microsoft 서비스에 연결하는 경우 두 서비스가 동일한 조직에 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="4d9c4-124">**관리자** > **연결(프리뷰)** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="4d9c4-125">**연결** 탭으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="4d9c4-126">새 연결을 만들려면 **연결 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="4d9c4-127">드롭다운 메뉴에서 생성하려는 연결 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-127">Choose from the dropdown menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="4d9c4-128">**연결 설정** 창에서 필요한 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="4d9c4-129">**표시 이름** 및 연결 유형은 연결을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="4d9c4-130">이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="4d9c4-131">정확한 필드는 연결하는 서비스에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="4d9c4-132">대상 서비스에 대한 기사에서 특정 연결 유형의 세부 사항에 대해 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="4d9c4-133">연결을 만들려면 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="4d9c4-134">**검색** 탭의 타일에서 **설정** 을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="4d9c4-135">기여자가 내보내기에 연결을 사용하도록 허용</span><span class="sxs-lookup"><span data-stu-id="4d9c4-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="4d9c4-136">내보내기 연결을 설정하거나 편집 할 때 이 특정 연결을 사용하여 [내보내기](export-destinations.md)를 정의할 수 있는 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="4d9c4-137">기본적으로 관리자 역할을 가진 사용자는 연결을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="4d9c4-138">이 설정은 **이 연결을 사용할 수 있는 사람 선택** 에서 변경할 수 있으며 기여자 역할을 가진 사용자가 이 연결을 사용하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="4d9c4-139">기여자는 연결을 보거나 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="4d9c4-140">내보내기를 만들 때 표시 이름 및 해당 유형만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="4d9c4-141">연결을 공유하면 기여자가 연결을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="4d9c4-142">기여자는 내보내기를 설정할 때 공유 연결을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="4d9c4-143">이 특정 연결을 사용하는 모든 내보내기를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="4d9c4-144">기여자가 이미 정의한 내보내기를 유지하면서 이 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="4d9c4-145">연결 편집</span><span class="sxs-lookup"><span data-stu-id="4d9c4-145">Edit a connection</span></span>

1. <span data-ttu-id="4d9c4-146">**관리자** > **연결(프리뷰)** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="4d9c4-147">**연결** 탭으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="4d9c4-148">편집할 연결의 세로 줄임표를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="4d9c4-149">**편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-149">Select **Edit**.</span></span>

1. <span data-ttu-id="4d9c4-150">업데이트할 값을 변경하고 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="4d9c4-151">연결 제거</span><span class="sxs-lookup"><span data-stu-id="4d9c4-151">Remove a connection</span></span>

<span data-ttu-id="4d9c4-152">제거하려는 연결이 보강 또는 내보내기에 사용되는 경우 먼저 연결을 분리하거나 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="4d9c4-153">제거 대화 상자는 관련 보강 또는 내보내기로 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> 

<span data-ttu-id="4d9c4-154">분리된 보강 및 내보내기가 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="4d9c4-155">[보강](enrichment-hub.md) 또는 [내보내기](export-destinations.md) 페이지에서 다른 연결을 추가하여 다시 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="4d9c4-156">**관리자** > **연결(프리뷰)** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="4d9c4-157">**연결** 탭으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="4d9c4-158">제거할 연결의 세로 줄임표를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="4d9c4-159">드롭다운 메뉴에서 **제거** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="4d9c4-160">확인 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="4d9c4-161">이 연결을 사용하는 보강 또는 내보내기가 있는 경우 단추를 선택하여 연결을 사용하는 항목을 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="4d9c4-162">**내보내기:** 연결을 제거할 수 있도록 내보내기를 제거하거나 연결을 끊도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="4d9c4-163">내보내기를 끊기 위해 관리자는 **연결 해제** 작업을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="4d9c4-164">이 작업은 개별 및 선택한 여러 내보내기에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="4d9c4-165">연결을 끊으면 내보내기 구성이 유지되지만 다른 연결이 추가될 때까지 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="4d9c4-166">**보강:** 연결을 제거할 수 있도록 보강을 제거하거나 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="4d9c4-167">연결에 더 이상 종속성이 없으면 **관리자** > **연결** 로 돌아가 연결을 다시 제거하십시오.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="4d9c4-168">**제거** 를 선택하여 삭제를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-168">To confirm the deletion, select **Remove**.</span></span>

