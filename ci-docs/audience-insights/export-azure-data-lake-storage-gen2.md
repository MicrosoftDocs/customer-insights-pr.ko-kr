---
title: Azure Data Lake Storage Gen2로 Customer Insights 데이터 내보내기
description: Azure Data Lake Storage Gen2로 연결을 구성하는 방법을 알아보세요.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477187"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="7e17f-103">Azure Data Lake Storage Gen2용 커넥터(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="7e17f-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="7e17f-104">Azure Data Lake Storage Gen2에 Customer Insights 데이터를 저장하거나 다른 애플리케이션으로 데이터를 전송하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7e17f-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="7e17f-105">Azure Data Lake Storage Gen2용 커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="7e17f-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="7e17f-106">대상 그룹 인사이트에서 **데이터** > **내보내기 대상** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7e17f-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="7e17f-107">**Azure Data Lake Storage Gen2** 에서 **설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7e17f-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="7e17f-108">**표시 이름** 필드에서 대상에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7e17f-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="7e17f-109">Azure Data Lake Storage Gen2에 대한 **계정 이름**, **계정 키** 및 **컨테이너** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7e17f-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="7e17f-110">Azure Data Lake Storage Gen2와 함께 사용할 스토리지 계정을 만드는 방법을 알아 보려면 [스토리지 계정 만들기](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e17f-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="7e17f-111">Azure Data Lake Gen2 스토리지 계정 이름 및 계정 키를 찾는 방법에 대한 자세한 내용은 [Azure Portal에서 스토리지 계정 설정 관리](https://docs.microsoft.com/azure/storage/common/storage-account-manage)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e17f-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="7e17f-112">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7e17f-112">Select **Next**.</span></span>

1. <span data-ttu-id="7e17f-113">이 대상으로 내보내려는 각 엔터티 옆의 상자를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e17f-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="7e17f-114">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7e17f-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="7e17f-115">데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="7e17f-115">Export the data</span></span>

<span data-ttu-id="7e17f-116">[주문 시 데이터를 내보낼](export-destinations.md#export-data-on-demand) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e17f-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="7e17f-117">내보내기는 [예약된 새로 고침](system.md#schedule-tab)마다 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e17f-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>