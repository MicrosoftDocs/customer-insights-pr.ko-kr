---
title: 참여 인사이트의 웹 데이터를 대상 그룹 인사이트와 통합
description: 참여 인사이트에서 대상 그룹 인사이트로 고객에 대한 웹 정보를 가져옵니다.
ms.date: 12/17/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9a4cb77bb4c6ef0d88b3f00802f66baab5520a07
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896427"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a><span data-ttu-id="fa990-103">참여 인사이트의 웹 데이터를 대상 그룹 인사이트와 통합</span><span class="sxs-lookup"><span data-stu-id="fa990-103">Integrate web data from engagement insights with audience insights</span></span>

<span data-ttu-id="fa990-104">고객은 종종 웹 사이트를 사용하여 온라인에서 일상적인 트랜잭션을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-104">Customers often do their day to day transactions online using web sites.</span></span> <span data-ttu-id="fa990-105">Dynamics 365 Customer Insights의 참여 인사이트 기능은 웹 데이터를 소스로 통합하는 편리한 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-105">The engagement insights capability in Dynamics 365 Customer Insights is a handy solution to integrate web data as a source.</span></span> <span data-ttu-id="fa990-106">트랜잭션, 인구 통계 또는 행동 데이터 외에도 통합 고객 프로필에서 웹 활동을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-106">In addition to transactional, demographic, or behavioral data we can see activities on the web in unified customer profiles.</span></span> <span data-ttu-id="fa990-107">이 프로필을 사용하여 세그먼트, 측정값 또는 대상 그룹 활성화에 대한 예측과 같은 추가 인사이트를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-107">We can use this profile to gain additional insights like segments, measures, or predictions for audience activation.</span></span>

<span data-ttu-id="fa990-108">이 문서에서는 참여 인사이트에서 고객의 웹 활동 데이터를 기존 대상 그룹 인사이트 환경으로 가져오는 단계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-108">This article describes the steps to bring your customers’ web activity data from engagement insights into your existing audience insights environment.</span></span>

<span data-ttu-id="fa990-109">이 예에서는 통합 고객 프로필이 포함된 환경을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-109">In this example, we assume an environment that contains unified customer profiles.</span></span> <span data-ttu-id="fa990-110">프로필은 설문 조사, 소매 영업 및 티켓팅 시스템의 소스와 통합되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-110">The profiles were unified with sources from surveys, retail sales, and a ticketing system.</span></span> <span data-ttu-id="fa990-111">또한 고객의 관련 활동을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-111">It also shows the related activities of the customers.</span></span> 

<span data-ttu-id="fa990-112">이제 고객이 웹 속성을 방문하고 그들의 활동을 이해하고 있는지 알아보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-112">We now want to know if a customer visits our web properties and understand their activities.</span></span> <span data-ttu-id="fa990-113">예를 들어 활동에는 방문한 웹 사이트 또는 이메일로 받은 링크에서 본 제품 페이지가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-113">Activities include, for example, visited websites or viewed product pages from a link received in an email.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fa990-114">필요한 항목</span><span class="sxs-lookup"><span data-stu-id="fa990-114">Prerequisites</span></span>

<span data-ttu-id="fa990-115">참여 인사이트의 데이터를 통합하려면 몇 가지 필수 구성 요소를 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-115">To integrate data from engagement insights, a few prerequisites need to be met:</span></span> 

- <span data-ttu-id="fa990-116">참여 인사이트 SDK를 웹 사이트와 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-116">Integrate the engagement insights SDK with your website.</span></span> <span data-ttu-id="fa990-117">자세한 내용은 [웹 SDK로 시작](../engagement-insights/instrument-website.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fa990-117">For more information, see [Get started with the web SDK](../engagement-insights/instrument-website.md).</span></span>
- <span data-ttu-id="fa990-118">참여 인사이트에서 웹 이벤트를 내보내려면 웹 이벤트 데이터를 대상 그룹 인사이트로 수집하는 데 사용할 ADLS Gen 2 스토리지 계정에 대한 액세스 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-118">Exporting web events from engagement insights requires access to an ADLS Gen 2 storage account that will be used to ingest the web events data to audience insights.</span></span> <span data-ttu-id="fa990-119">자세한 내용은 [이벤트 내보내기](../engagement-insights/export-events.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fa990-119">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="configure-refined-events-in-engagement-insights"></a><span data-ttu-id="fa990-120">참여 인사이트에서 정제된 이벤트 구성</span><span class="sxs-lookup"><span data-stu-id="fa990-120">Configure refined events in engagement insights</span></span>

<span data-ttu-id="fa990-121">관리자가 참여 인사이트 SDK를 사용하여 웹 사이트를 구성한 후 사용자가 웹 페이지를 보거나 어딘가를 클릭하면 *기본 이벤트* 가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-121">After an administrator instrumented a website with the engagement insights SDK, *base events* are gathered when a user views a web page or clicks somewhere.</span></span> <span data-ttu-id="fa990-122">기본 이벤트는 많은 세부 정보를 포함하는 경향이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-122">Base events tend to contain numerous details.</span></span> <span data-ttu-id="fa990-123">사용 사례에 따라 기본 이벤트에 있는 데이터의 하위 집합만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-123">Depending on your use case, you only need a subset of the data in a base event.</span></span> <span data-ttu-id="fa990-124">참여 인사이트를 사용하면 선택한 기본 이벤트의 속성만 포함하는 *정제된 이벤트* 를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-124">Engagement insights let you create *refined events* that contain only the properties of a base event that you select.</span></span>     

<span data-ttu-id="fa990-125">자세한 내용은 [정제된 이벤트 만들기 및 수정 ](../engagement-insights/refined-events.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fa990-125">For more information, see [Create and modify refined events](../engagement-insights/refined-events.md).</span></span>

<span data-ttu-id="fa990-126">정제된 이벤트를 만들 때 고려할 사항:</span><span class="sxs-lookup"><span data-stu-id="fa990-126">Considerations when creating refined events:</span></span> 

- <span data-ttu-id="fa990-127">정제된 이벤트에 대한 의미 있는 이름을 제공하십시오.</span><span class="sxs-lookup"><span data-stu-id="fa990-127">Provide a meaningful name for the refined event.</span></span> <span data-ttu-id="fa990-128">이는 대상 그룹 인사이트에서 활동 이름으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-128">It's be used as an activity name in audience insights.</span></span>
- <span data-ttu-id="fa990-129">대상 그룹 인사이트에서 활동을 만들려면 최소한 다음 특성을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="fa990-129">Select at least the following properties to create an activity in audience insights:</span></span> 
    - <span data-ttu-id="fa990-130">Signal.Action.Name-활동 세부 정보 표시</span><span class="sxs-lookup"><span data-stu-id="fa990-130">Signal.Action.Name - indicating the activity details</span></span>
    - <span data-ttu-id="fa990-131">Signal.User.Id-고객 ID로 매핑하는 데 사용</span><span class="sxs-lookup"><span data-stu-id="fa990-131">Signal.User.Id - used to map with the customer ID</span></span>
    - <span data-ttu-id="fa990-132">Signal.View.Uri-세그먼트 또는 측정값에 대한 기준으로 웹 주소로 사용됨</span><span class="sxs-lookup"><span data-stu-id="fa990-132">Signal.View.Uri - used as a web address as a basis for segments or measures</span></span>
    - <span data-ttu-id="fa990-133">Signal.Export.Id-이벤트의 기본 키로 사용</span><span class="sxs-lookup"><span data-stu-id="fa990-133">Signal.Export.Id - to use as a primary key for events</span></span>
    - <span data-ttu-id="fa990-134">Signal.Timestamp-활동의 날짜와 시간을 결정</span><span class="sxs-lookup"><span data-stu-id="fa990-134">Signal.Timestamp - to determine the date and time for the activity</span></span>

<span data-ttu-id="fa990-135">사용 사례에 중요한 이벤트 및 페이지에 초점을 맞추려면 필터를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="fa990-135">Select the filters to focus on the events and pages that matter for your use case.</span></span> <span data-ttu-id="fa990-136">이 예에서는 "이메일 프로모션" 작업 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-136">In this example, we'll use the "Email promotion" action name.</span></span>

## <a name="export-the-refined-web-events"></a><span data-ttu-id="fa990-137">정제된 웹 이벤트 내보내기</span><span class="sxs-lookup"><span data-stu-id="fa990-137">Export the Refined Web Events</span></span> 

<span data-ttu-id="fa990-138">정제된 이벤트를 정의한 후에는 대상 그룹 인사이트에서 수집을 위한 데이터 원본으로 설정할 수 있는 Azure Data Lake Storage로 이벤트 데이터 내보내기를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-138">After defining the refined event is defined, you have to configure the export of the event data to an Azure Data Lake Storage, that can be set as a data source for ingestion in audience insights.</span></span> <span data-ttu-id="fa990-139">웹 속성에서 이벤트가 이동하면 내보내기가 계속 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-139">Exports happen constantly as the events flow from the web property.</span></span>

<span data-ttu-id="fa990-140">자세한 내용은 [이벤트 내보내기](../engagement-insights/export-events.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fa990-140">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="ingest-event-data-to-audience-insights"></a><span data-ttu-id="fa990-141">이벤트 데이터를 대상 그룹 인사이트로 수집</span><span class="sxs-lookup"><span data-stu-id="fa990-141">Ingest event data to audience insights</span></span>

<span data-ttu-id="fa990-142">정제된 이벤트를 정의하고 내보내기를 구성했으므로 이제 데이터를 대상 그룹 인사이트로 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-142">Now that you have defined the refined event and configured its export, we move on to ingesting the data to audience insights.</span></span> <span data-ttu-id="fa990-143">Common Data Model 폴더를 기반으로 새 데이터 원본을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-143">You need to create a new data source based on a Common Data Model folder.</span></span> <span data-ttu-id="fa990-144">이벤트를 내보낼 스토리지 계정의 세부 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-144">Enter the details for the storage account you export the events to.</span></span> <span data-ttu-id="fa990-145">*default.cdm.json* 파일에서 수집할 정제된 이벤트를 선택하고 대상 그룹 인사이트에서 엔터티를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-145">In the *default.cdm.json* file, select the refined event to ingest and create the entity in audience insights.</span></span>

<span data-ttu-id="fa990-146">자세한 내용은 [Azure Data Lake 계정을 사용하여 Common Data Model 폴더에 연결](connect-common-data-model.md)을 참조</span><span class="sxs-lookup"><span data-stu-id="fa990-146">For more information, see [Connect to a Common Data Model folder using an Azure Data Lake account](connect-common-data-model.md)</span></span>


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a><span data-ttu-id="fa990-147">정제된 이벤트 데이터를 고객 프로필의 활동으로 연결</span><span class="sxs-lookup"><span data-stu-id="fa990-147">Relate refined event data as an activity of a customer profile</span></span>

<span data-ttu-id="fa990-148">엔터티 수집을 완료한 후 고객 프로필에 대한 활동을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-148">After completing the entity ingestion, you can configure the activity for the customer profile.</span></span>

<span data-ttu-id="fa990-149">자세한 내용은 [고객 활동](activities.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa990-149">For more information, see [Customer activities](activities.md).</span></span>

:::image type="content" source="media/web-event-activity.png" alt-text="활동 편집 창이 확장되고 필드가 채워진 활동 페이지입니다.":::

<span data-ttu-id="fa990-151">다음 매핑을 사용하여 새 활동을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-151">Configure the new activity with the following mapping:</span></span> 

- <span data-ttu-id="fa990-152">**기본 키:** 참여 인사이트의 모든 이벤트 기록에 사용할 수 있는 고유 ID인 Signal.Export.Id입니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-152">**Primary Key:** Signal.Export.Id, a unique ID that is available for every event record in engagement insights.</span></span> <span data-ttu-id="fa990-153">이 속성은 자동으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-153">This property is automatically generated.</span></span>

- <span data-ttu-id="fa990-154">**타임스탬프:** 이벤트 속성의 Signal.Timestamp입니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-154">**Timestamp:** Signal.Timestamp in the event property.</span></span>

- <span data-ttu-id="fa990-155">**이벤트:** 추적하려는 이벤트 이름인 Signal.Name입니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-155">**Event:** Signal.Name, the event name that you want to track.</span></span>

- <span data-ttu-id="fa990-156">**웹 주소:** 이벤트를 생성한 페이지의 URI를 참조하는 Signal.View.Uri입니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-156">**Web address:** Signal.View.Uri referring to the uri of the page that created the event.</span></span>

- <span data-ttu-id="fa990-157">**세부 정보:** 이벤트와 연결할 정보를 나타내는 Signal.Action.Name입니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-157">**Details:** Signal.Action.Name to represent the information to associate with the event.</span></span> <span data-ttu-id="fa990-158">이 경우 선택된 속성은 이벤트가 이메일 프로모션 용임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-158">The selected property in this case indicates that the event is for email promotion.</span></span>

- <span data-ttu-id="fa990-159">**활동 유형:** 이 예에서는 기존 활동 유형 WebLog를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-159">**Activity type:** In this example, we choose the exsting activity type WebLog.</span></span> <span data-ttu-id="fa990-160">이 선택 항목은 예측 모델을 실행하거나 이 활동 유형을 기반으로 세그먼트를 만드는 데 유용한 필터 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-160">This selection is a useful filter option to run prediction models or create segments based on this activity type.</span></span>

- <span data-ttu-id="fa990-161">**관계 설정:** 이 중요한 설정은 활동을 기존 고객 프로필에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-161">**Set up relationship:** This important setting ties the activity to existing customer profiles.</span></span> <span data-ttu-id="fa990-162">**Signal.User.Id** 는 수집할 SDK에 구성된 식별자이며 대상 그룹 인사이트에 구성된 다른 데이터 소스의 사용자 ID와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-162">**Signal.User.Id** is the identifier configured in the SDK to be collected and that relates to the user ID in other data sources that are configured in audience insights.</span></span> <span data-ttu-id="fa990-163">이 예에서는 데이터 통합 프로세스의 맵 단계에서 정의된 기본 키인 Signal.User.Id와 RetailCustomers:CustomerRetailId 간의 관계를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-163">In this example, we configure the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was deinfed in the map step of the data unification process.</span></span>


<span data-ttu-id="fa990-164">활동을 처리한 후 고객 기록을 검토하고 고객 카드를 열어 시간 표시줄의 참여 인사이트에서 활동을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-164">After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline.</span></span> 

> [!TIP]
> <span data-ttu-id="fa990-165">참여 인사이트 활동이 있는 고객 ID를 찾으려면 **엔터티** 로 이동하여 UnifiedActivity 엔터티에 대한 데이터를 미리 봅니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-165">To find a customer id that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity.</span></span> <span data-ttu-id="fa990-166">ActivityTypeDisplay = WebLog에는 위의 예에서 구성된 참여 인사이트 활동이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-166">ActivityTypeDisplay = WebLog contain the engagement insights activity configured in the example above.</span></span> <span data-ttu-id="fa990-167">**고객** 페이지에서 해당 레코드 중 하나와 해당 ID에 대한 고객 ID를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-167">Copy the customer ID for one of those records and for that ID on the **Customers** page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fa990-168">다음 단계</span><span class="sxs-lookup"><span data-stu-id="fa990-168">Next Steps</span></span>

<span data-ttu-id="fa990-169">이제 [세그먼트](segments.md), [측정값](measures.md) 및 [예측](predictions.md)을 만들어 고객과 의미 있는 관계를 맺을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa990-169">You can now create [segments](segments.md), [measures](measures.md), and [predictions](predictions.md) to make a meaningful connection with your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]