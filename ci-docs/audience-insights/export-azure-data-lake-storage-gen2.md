---
title: Azure Data Lake Storage Gen2로 Customer Insights 데이터 내보내기
description: Azure Data Lake Storage Gen2로 연결을 구성하는 방법을 알아보세요.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760059"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="c53fc-103">Azure Data Lake Storage 2세대에 대한 연결 설정(프리뷰)</span><span class="sxs-lookup"><span data-stu-id="c53fc-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="c53fc-104">**관리자** > **연결** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c53fc-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c53fc-105">**연결 추가** 와 **Azure Data Lake 2세대** 를 선택하여 연결을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c53fc-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="c53fc-106">**표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c53fc-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="c53fc-107">이름 및 연결 유형은 이 연결을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c53fc-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="c53fc-108">이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c53fc-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c53fc-109">이 연결을 사용할 수 있는 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c53fc-109">Choose who can use this connection.</span></span> <span data-ttu-id="c53fc-110">아무 조치도 취하지 않으면 기본값은 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="c53fc-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="c53fc-111">자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c53fc-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c53fc-112">Azure Data Lake Storage Gen2에 대한 **계정 이름**, **계정 키** 및 **컨테이너** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c53fc-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="c53fc-113">Azure Data Lake Storage Gen2와 함께 사용할 스토리지 계정을 만드는 방법을 알아 보려면 [스토리지 계정 만들기](/azure/storage/blobs/create-data-lake-storage-account)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c53fc-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="c53fc-114">Azure Data Lake 2세대 스토리지 계정 이름 및 계정 키를 찾는 방법에 대한 자세한 내용은 [Azure Portal에서 스토리지 계정 설정 관리](/azure/storage/common/storage-account-manage)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c53fc-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="c53fc-115">연결을 완료하려면 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c53fc-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="c53fc-116">내보내기 구성</span><span class="sxs-lookup"><span data-stu-id="c53fc-116">Configure an export</span></span>

<span data-ttu-id="c53fc-117">이 유형의 연결에 대한 액세스 권한이 있는 경우 이 내보내기를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c53fc-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c53fc-118">자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c53fc-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c53fc-119">**데이터** > **내보내기** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c53fc-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c53fc-120">**내보내기 추가** 를 선택하여 새 내보내기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c53fc-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="c53fc-121">**내보내기 연결 필드** 의 **Azure Data Lake** 섹션에서 연결을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c53fc-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="c53fc-122">이 섹션 이름이 표시되지 않으면 사용 가능한 이 유형의 연결이 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c53fc-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="c53fc-123">이 대상으로 내보내려는 각 엔터티 옆의 상자를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="c53fc-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="c53fc-124">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c53fc-124">Select **Save**.</span></span>

<span data-ttu-id="c53fc-125">내보내기를 저장해도 내보내기가 즉시 실행되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c53fc-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="c53fc-126">내보내기는 모든 [예약된 새로 고침](system.md#schedule-tab)에 따라 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c53fc-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c53fc-127">[주문형으로 데이터를 내보낼](export-destinations.md#run-exports-on-demand)수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c53fc-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="c53fc-128">내보낸 데이터는 구성한 Azure Data Lake 2세대 스토리지 컨테이너에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c53fc-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
