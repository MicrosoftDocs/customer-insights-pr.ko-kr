---
title: Power BI 커넥터
description: Power BI에서 Dynamics 365 Customer Insights 커넥터 사용 방법 알아보기.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406268"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="c838b-103">Power BI용 커넥터(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="c838b-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="c838b-104">Power BI Desktop을 사용하여 데이터에 대한 시각화를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c838b-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="c838b-105">통일된 고객 데이터로 추가 인사이트를 생성하고 보고서를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="c838b-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c838b-106">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="c838b-106">Prerequisites</span></span>

- <span data-ttu-id="c838b-107">통합 고객 프로필이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c838b-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="c838b-108">[Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) 최신 버전이 컴퓨터에 설치되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c838b-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="c838b-109">[Power BI Desktop에 대해 자세히 알아보기](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="c838b-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="c838b-110">Power BI용 커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="c838b-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="c838b-111">Power BI Desktop에서 **파일** > **데이터 가져오기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c838b-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="c838b-112">**더 보기** 를 선택하고 **Dynamics 365 Customer Insights** 를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c838b-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="c838b-113">결과를 선택하고 **연결** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c838b-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="c838b-114">Customer Insights에 사용하는 것과 동일한 조직 계정으로 **로그인** 하고 **연결** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c838b-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="c838b-115">이 단계에서 지정하는 계정은 Customer Insights에서 데이터를 가져오는 데 사용되며 Power BI과 같은 로그인 계정을 사용할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c838b-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="c838b-116">데이터 가져오기에 사용되는 계정을 재설정하려면 Power BI를 열고 **파일** > **옵션** > **설정** > **데이터 원본 설정** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c838b-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="c838b-117">데이터 소스 목록에서, **Dynamics 365 Customer Insights 로그인** 선택 후, **권한 지우기** 를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="c838b-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="c838b-118">**탐색기** 대화 상자에서.</span><span class="sxs-lookup"><span data-stu-id="c838b-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="c838b-119">액세스할 수 있는 모든 환경 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c838b-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="c838b-120">환경을 확장하고 폴더(엔터티, 측정값, 세그먼트, 보강)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c838b-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="c838b-121">예를 들어, 가져올 수 있는 모든 엔터티를 보려면 **엔터티** 폴더를 여세요.</span><span class="sxs-lookup"><span data-stu-id="c838b-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="c838b-122">![Power BI 커넥터 탐색기](media/power-bi-navigator.png "Power BI 커넥터 탐색기")</span><span class="sxs-lookup"><span data-stu-id="c838b-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="c838b-123">포함하고 **로드** 할 엔터티 옆의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c838b-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="c838b-124">여러 환경에서 여러 엔터티를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c838b-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="c838b-125">엔터티가 로드되는 동안 로드 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="c838b-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="c838b-126">선택한 엔터티가 모두 로드되면 Power BI 데이터를 시각화하는 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c838b-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="c838b-127">대규모 데이터 세트</span><span class="sxs-lookup"><span data-stu-id="c838b-127">Large data sets</span></span>

<span data-ttu-id="c838b-128">Power BI용 Customer Insights 커넥터는 최대 1백만 개의 고객 프로필을 포함하는 데이터 세트에서 작동하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c838b-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="c838b-129">더 큰 데이터 세트를 가져 올 수는 있으나 시간이 오래 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="c838b-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="c838b-130">또한 Power BI 한계상의 이유로 프로세스가 시간 제한에 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c838b-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="c838b-131">자세한 내용은 [Power BI : 대용량 데이터 세트에 대한 권장사항](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c838b-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="c838b-132">데이터 하위 집합으로 작업</span><span class="sxs-lookup"><span data-stu-id="c838b-132">Work with a subset of data</span></span>

<span data-ttu-id="c838b-133">데이터의 하위 집합으로 작업하는 것을 고려하십시오.</span><span class="sxs-lookup"><span data-stu-id="c838b-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="c838b-134">예를 들어 모든 고객 레코드를 Power BI로 내보내는 대신 [세그먼트](segments.md)를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c838b-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
