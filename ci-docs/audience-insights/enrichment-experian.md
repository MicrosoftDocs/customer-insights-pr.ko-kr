---
title: 타사 보강 Experian으로 보강
description: Experian 타사 보강에 대한 일반 정보입니다.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896381"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="de6e4-103">자세한 내용은 Experian의 인구 통계로 고객 프로필 보강을 참고하세요 (미리보기)</span><span class="sxs-lookup"><span data-stu-id="de6e4-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="de6e4-104">Experian은 소비자 및 기업 신용보고 및 마케팅 서비스 분야의 글로벌 리더입니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="de6e4-105">Experian의 데이터 보강 서비스를 사용하면 가구 규모, 소득 등과 같은 인구 통계 데이터로 고객 프로필을 강화하여 고객에 대한 더 깊은 이해를 구축할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="de6e4-106">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="de6e4-106">Prerequisites</span></span>

<span data-ttu-id="de6e4-107">Experian 구성을 위해 다음 전제 조건이 충족되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="de6e4-108">Experian 구독이 활성화 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-108">You have an active Experian subscription.</span></span> <span data-ttu-id="de6e4-109">구독을 받으려면 직접 [Experian에 문의](https://www.experian.com/marketing-services/contact)합니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="de6e4-110">[Experian데이터 보강에 대한 자세한 정보](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="de6e4-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="de6e4-111">관리자가 Experian 연결을 이미 구성했습니다. *또는* 귀하가 [관리자](permissions.md#administrator) 권한을 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="de6e4-112">Experian이 생성한 SSH 사용 보안 전송(ST) 계정의 사용자 ID, 당사자 ID 및 모델 번호도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="de6e4-113">보강 구성</span><span class="sxs-lookup"><span data-stu-id="de6e4-113">Configure the enrichment</span></span>

1. <span data-ttu-id="de6e4-114">**데이터** > **보강** 으로 이동 후, **발견하기** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="de6e4-115">Experian 타일에서 **내 데이터 강화** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="de6e4-116">![Experian 타일](media/experian-tile.png "Experian 타일")</span><span class="sxs-lookup"><span data-stu-id="de6e4-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="de6e4-117">드롭다운 목록에서 [연결](connections.md)을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="de6e4-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="de6e4-118">사용 가능한 연결이 없으면 관리자에게 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="de6e4-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="de6e4-119">관리자인 경우 **연결 추가** 를 선택하고 드롭다운에서 Experian을 선택하여 연결을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="de6e4-120">**Experian에 연결** 을 선택하여 연결 선택을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="de6e4-121">**다음** 을 선택하고 Experian의 인구 통계 데이터로 보강할 **고객 데이터 집합** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="de6e4-122">**고객** 엔터티를 선택하여 모든 고객 프로필을 보강하거나 세그먼트 엔터티를 선택하여 해당 세그먼트에 포함된 고객 프로필만 보강할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="고객 데이터 집합 선택 시 스크린샷입니다.":::

1. <span data-ttu-id="de6e4-124">**다음** 을 선택하고 Experian에서 일치하는 인구 통계 데이터를 찾는 데 사용해야 하는 통합 프로필의 필드 유형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="de6e4-125">**이름과 주소**, **전화** 또는 **이메일** 중 하나 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="de6e4-126">더 높은 일치 정확도를 위해 최대 2개의 다른 필드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="de6e4-127">이 선택은 다음 단계에서 액세스할 수 있는 매핑 필드에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="de6e4-128">Experian에 전송된 키 식별자 속성이 많을수록 일치율이 높아질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="de6e4-129">필드 매핑을 시작하려면 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="de6e4-130">Experian에서 일치하는 인구 통계 데이터를 찾는 데 사용해야 하는 통합 프로필의 필드 유형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="de6e4-131">표시된 필드는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-131">Required fields are marked.</span></span>

1. <span data-ttu-id="de6e4-132">보강 이름과 출력 엔터티 이름을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="de6e4-133">선택 사항을 검토 한 후 **보강 저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="de6e4-134">Experian에 대한 연결 구성</span><span class="sxs-lookup"><span data-stu-id="de6e4-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="de6e4-135">연결을 구성하려면 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="de6e4-136">보강을 구성할 때 **연결 추가** 를 선택 *하거나* **관리자** > **연결** 로 이동하여 Experian 타일에서 **설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="de6e4-137">**시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="de6e4-138">**표시 이름** 상자에 연결 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="de6e4-139">Experian Secure Transport 계정에 유효한 사용자 ID, 당사자 ID 및 모델 번호를 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="de6e4-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="de6e4-140">**동의함** 확인란을 선택하여 **데이터 개인 정보 및 규정 준수** 에 대한 동의를 검토하고 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="de6e4-141">**확인** 을 선택하여 구성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="de6e4-142">확인을 완료한 후 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian 연결 구성 창.":::

## <a name="enrichment-results"></a><span data-ttu-id="de6e4-144">보강 결과</span><span class="sxs-lookup"><span data-stu-id="de6e4-144">Enrichment results</span></span>

<span data-ttu-id="de6e4-145">강화 프로세스를 시작하려면 명령 모음에서.**실행** 을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="de6e4-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="de6e4-146">[예약된 새로 고침](system.md#schedule-tab)으로 시스템이 자동으로 보강을 실행하도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="de6e4-147">처리 시간은 고객 데이터의 크기와 Experian에서 계정에 대해 설정한 보강 프로세스에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="de6e4-148">보강 프로세스가 완료되면 **내 보강** 아래에서 새로 보강 된 고객 프로필 데이터를 검토 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="de6e4-149">또한 마지막 업데이트 시간과 강화 된 프로필 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="de6e4-150">**보강된 데이터 보기** 를 선택하여 각 보강된 프로필의 상세 보기에 액세스할 수 있습니다 .</span><span class="sxs-lookup"><span data-stu-id="de6e4-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="de6e4-151">다음 단계</span><span class="sxs-lookup"><span data-stu-id="de6e4-151">Next steps</span></span>

<span data-ttu-id="de6e4-152">보강된 고객 데이터를 바탕으로 구축합니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="de6e4-153">[세그먼트](segments.md)를 만들고, [측정](measures.md)하고, 또한 [데이터를 내보내](export-destinations.md) 고객에게 맞춤형 경험을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="de6e4-154">데이터 프라이버시 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="de6e4-154">Data privacy and compliance</span></span>

<span data-ttu-id="de6e4-155">Dynamics 365 Customer Insights를 사용하여 Experian으로 데이터를 전송하는 경우 Dynamics 365 Customer Insights규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="de6e4-156">Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 Experian이 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="de6e4-157">자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de6e4-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="de6e4-158">Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 보강을 언제든지 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de6e4-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
