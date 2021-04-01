---
title: Azure Data Lake Storage Gen2로 Customer Insights 데이터 내보내기
description: Azure Data Lake Storage Gen2로 연결을 구성하는 방법을 알아보세요.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596645"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="10707-103">Azure Data Lake Storage Gen2용 커넥터(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="10707-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="10707-104">Azure Data Lake Storage Gen2에 Customer Insights 데이터를 저장하거나 다른 애플리케이션으로 데이터를 전송하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10707-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="10707-105">Azure Data Lake Storage Gen2용 커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="10707-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="10707-106">대상 그룹 인사이트에서 **데이터** > **내보내기 대상** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="10707-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="10707-107">**Azure Data Lake Storage Gen2** 에서 **설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="10707-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="10707-108">**표시 이름** 필드에서 대상에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="10707-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="10707-109">Azure Data Lake Storage Gen2에 대한 **계정 이름**, **계정 키** 및 **컨테이너** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="10707-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="10707-110">Azure Data Lake Storage Gen2와 함께 사용할 스토리지 계정을 만드는 방법을 알아 보려면 [스토리지 계정 만들기](/azure/storage/blobs/create-data-lake-storage-account)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="10707-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="10707-111">Azure Data Lake Gen2 스토리지 계정 이름 및 계정 키를 찾는 방법에 대한 자세한 내용은 [Azure Portal에서 스토리지 계정 설정 관리](/azure/storage/common/storage-account-manage)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="10707-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="10707-112">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="10707-112">Select **Next**.</span></span>

1. <span data-ttu-id="10707-113">이 대상으로 내보내려는 각 엔터티 옆의 상자를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="10707-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="10707-114">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="10707-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="10707-115">데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="10707-115">Export the data</span></span>

<span data-ttu-id="10707-116">[주문 시 데이터를 내보낼](export-destinations.md#export-data-on-demand) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10707-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="10707-117">내보내기는 [예약된 새로 고침](system.md#schedule-tab)마다 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="10707-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>