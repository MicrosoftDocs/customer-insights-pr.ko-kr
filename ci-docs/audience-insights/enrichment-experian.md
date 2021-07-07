---
title: 제3자 보강을 통한 보강 Experian
description: Experian 제3자 보강에 대한 일반 정보.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309828"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="f25cd-103">Experian 인구 통계로 고객 프로필을 보강하십시오.(프리뷰)</span><span class="sxs-lookup"><span data-stu-id="f25cd-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="f25cd-104">Experian은 소비자 및 기업 신용보고 및 마케팅 서비스 분야의 글로벌 리더입니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="f25cd-105">Experian의 데이터 보강 서비스를 사용하면 가구 규모, 소득 등과 같은 인구 통계학적 데이터로 고객 프로필을 보강하여 고객에 대한 더 깊은 이해를 구축할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f25cd-106">필수 조건</span><span class="sxs-lookup"><span data-stu-id="f25cd-106">Prerequisites</span></span>

<span data-ttu-id="f25cd-107">Experian을 구성하려면 다음 전제 조건이 충족되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="f25cd-108">활성 Experian 구독이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-108">You have an active Experian subscription.</span></span> <span data-ttu-id="f25cd-109">구독하려면 [Experian에 직접 연락](https://www.experian.com/marketing-services/contact)하세요.</span><span class="sxs-lookup"><span data-stu-id="f25cd-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="f25cd-110">[Experian 데이터 보강에 대해 자세히 알아보기](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="f25cd-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="f25cd-111">관리자가 Experian 연결을 이미 *구성했거나* 귀하가 [관리자](permissions.md#administrator) 권한을 가지고 있음.</span><span class="sxs-lookup"><span data-stu-id="f25cd-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="f25cd-112">또한 Experian에서 생성된 SSH 사용 보안 전송(ST) 계정에 대한 사용자 ID, 당사자 ID 및 모델 번호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="f25cd-113">지원되는 국가/지역</span><span class="sxs-lookup"><span data-stu-id="f25cd-113">Supported countries/regions</span></span>

<span data-ttu-id="f25cd-114">현재 미국에서만 고객 프로필 보강을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="f25cd-115">보강 구성</span><span class="sxs-lookup"><span data-stu-id="f25cd-115">Configure the enrichment</span></span>

1. <span data-ttu-id="f25cd-116">**데이터** > **보강** 으로 이동 후, **발견하기** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="f25cd-117">Experian 타일에서 **내 데이터 보강** 을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="f25cd-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f25cd-118">![Experian 합니다](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="f25cd-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="f25cd-119">드롭다운 목록에서 [연결](connections.md)을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="f25cd-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="f25cd-120">사용 가능한 연결이 없으면 관리자에게 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="f25cd-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="f25cd-121">관리자인 경우 **연결 추가** 를 선택하고 드롭다운 목록에서 Experian을 선택하여 연결을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="f25cd-122">**Experian 연결** 을 선택하여 연결 선택을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="f25cd-123">**다음** 을 선택하고 Experian 인구 통계 데이터로 보강할 **고객 데이터 집합** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="f25cd-124">**고객** 엔터티를 선택하여 모든 고객 프로필을 보강하거나 세그먼트 엔터티를 선택하여 해당 세그먼트에 포함된 고객 프로필만 보강할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="고객 데이터 집합 선택 시 스크린샷입니다.":::

1. <span data-ttu-id="f25cd-126">**다음** 을 선택하고 통합 프로필에서 Experian의 인구 통계 데이터와 일치하는 것을 찾는 데 사용해야 하는 필드 유형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="f25cd-127">**이름과 주소**, **전화** 또는 **이메일** 중 하나 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="f25cd-128">더 높은 일치 정확도를 위해 최대 2개의 다른 필드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="f25cd-129">이 선택은 다음 단계에서 액세스할 수 있는 매핑 필드에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="f25cd-130">Experian에 더 많은 키 식별자 특성을 전송하면 더 높은 일치율을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="f25cd-131">필드 매핑을 시작하려면 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="f25cd-132">통합 프로필에서 Experian의 인구 통계 데이터와 일치하는 것을 찾는 데 사용해야 하는 필드 유형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="f25cd-133">표시된 필드는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-133">Required fields are marked.</span></span>

1. <span data-ttu-id="f25cd-134">보강 이름과 출력 엔터티 이름을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="f25cd-135">선택 사항을 검토 한 후 **보강 저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="f25cd-136">Experian 연결 구성</span><span class="sxs-lookup"><span data-stu-id="f25cd-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="f25cd-137">연결을 구성하려면 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="f25cd-138">보강을 구성할 때 **연결 추가** 를 *선택하거나* **관리자** > **연결** 로 이동하여 Experian 타일에서 **설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="f25cd-139">**시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="f25cd-140">**표시 이름** 상자에 연결 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="f25cd-141">Experian 보안 전송 계정에 대한 유효한 사용자 ID, 당사자 ID 및 모델 번호를 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="f25cd-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="f25cd-142">**데이터 개인 정보 보호 및 규정 준수** 를 검토하고 **동의함** 을 선택하여 동의를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="f25cd-143">**확인** 을 선택하여 구성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="f25cd-144">확인을 완료한 후 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian연결 구성 창.":::

## <a name="enrichment-results"></a><span data-ttu-id="f25cd-146">보강 결과</span><span class="sxs-lookup"><span data-stu-id="f25cd-146">Enrichment results</span></span>

<span data-ttu-id="f25cd-147">강화 프로세스를 시작하려면 명령 모음에서.**실행** 을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="f25cd-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="f25cd-148">[예약된 새로 고침](system.md#schedule-tab)으로 시스템이 자동으로 보강을 실행하도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f25cd-149">처리 시간은 고객 데이터의 크기와 Experian에서 계정에 대해 설정한 보강 프로세스에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="f25cd-150">보강 프로세스가 완료되면 **내 보강** 아래에서 새로 보강 된 고객 프로필 데이터를 검토 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="f25cd-151">또한 마지막 업데이트 시간과 강화 된 프로필 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="f25cd-152">**보강된 데이터 보기** 를 선택하여 각 보강된 프로필의 상세 보기에 액세스할 수 있습니다 .</span><span class="sxs-lookup"><span data-stu-id="f25cd-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f25cd-153">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f25cd-153">Next steps</span></span>

<span data-ttu-id="f25cd-154">보강된 고객 데이터를 바탕으로 구축합니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="f25cd-155">[세그먼트](segments.md) 및 [측정값](measures.md)을 만들고 [데이터 내보내기](export-destinations.md) 를 통해 고객에게 개인화된 경험을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f25cd-156">데이터 프라이버시 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="f25cd-156">Data privacy and compliance</span></span>

<span data-ttu-id="f25cd-157">Experian에 데이터를 전송하기 위해 Dynamics 365 Customer Insights를 활성화할 때 개인 데이터와 같이 잠재적으로 민감한 데이터를 비롯하여 Dynamics 365 Customer Insights의 준수 경계를 벗어난 데이터 전송을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f25cd-158">Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 귀하는 Experian이 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f25cd-159">자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f25cd-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f25cd-160">Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 보강을 언제든지 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f25cd-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
