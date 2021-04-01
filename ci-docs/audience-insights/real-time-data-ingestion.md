---
title: 실시간 데이터 수집 및 제한
description: 대상 그룹 인사이트의 실시간 기능에 대한 일반 정보입니다.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3c84cfe7441eb026c1fd45eda1f72421388d01d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598577"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="7b41d-103">실시간 데이터 수집(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="7b41d-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="7b41d-104">거의 실시간 기능을 통해 고객이 제품 또는 서비스와 수행한 최신 상호 작용을 몇 초 안에 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="7b41d-105">[예약된 새로 고침](system.md#schedule-tab)에는 많은 수의 레코드와 여러 가지 복잡한 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="7b41d-106">먼저 데이터 원본에서 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="7b41d-107">그런 다음 데이터가 통합된 후 데이터는 추가 정보로 보강됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="7b41d-108">이 프로세스를 실행할 때마다 몇 분에서 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="7b41d-109">실시간 기능은 이후에 예약된 새로 고침이 데이터 원본에서이 데이터를 가져올 때까지 즉시 사용할 데이터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="7b41d-110">실시간 업데이트는 만료 시간이 지난 후 더 이상 데이터 원본의 값을 무시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="7b41d-111">프로필 업데이트는 4시간 동안 유지됩니다</span><span class="sxs-lookup"><span data-stu-id="7b41d-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="7b41d-112">활동은 30일 동안 유지됩니다</span><span class="sxs-lookup"><span data-stu-id="7b41d-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="7b41d-113">이 값은 변경할 수 있는 API 호출 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="7b41d-114">이 매개 변수의 사용 목적은 원본 데이터가 신뢰의 소스로 남아 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="7b41d-115">실시간 업데이트를 더 오래 포함하려면 예정된 다음 새로 고침 중에 가져오도록 데이터 원본에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="7b41d-116">통합 고객 프로필 필드의 실시간 업데이트</span><span class="sxs-lookup"><span data-stu-id="7b41d-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="7b41d-117">업데이트된 프로필은 몇 초 이내에 고객 카드 보기 또는 기타 시각화에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="7b41d-118">데이터 통합이 발생한 후 실시간 작업이 수행되므로 통합 고객 프로필에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="7b41d-119">결과적으로 실시간 프로필 변경은 측정, 세그먼트 구성원 자격 또는 보강을 업데이트하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="7b41d-120">제한 사항</span><span class="sxs-lookup"><span data-stu-id="7b41d-120">Limitations</span></span>

- <span data-ttu-id="7b41d-121">고객 프로필은 업데이트할 수 있지만 만들거나 삭제할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="7b41d-122">Power BI 같은 외부 시스템으로 실시간 업데이트 내보내기는 현재로서는 불가능합니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="7b41d-123">활동의 실시간 생성</span><span class="sxs-lookup"><span data-stu-id="7b41d-123">Real-time creation of activities</span></span>

<span data-ttu-id="7b41d-124">실시간 API를 사용하면 원본 시스템(개별 원본 레코드)의 새 활동을 통합 고객 프로필에 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="7b41d-125">새 활동은 통합 고객 프로필의 타임라인에서 몇 초 내에 통합된 활동으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="7b41d-126">고객 카드 보기 또는 구성한 다른 시간 표시줄 통합에서 시간 표시줄을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="7b41d-127">활동은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-127">Activities are immutable.</span></span> <span data-ttu-id="7b41d-128">일단 만들어진 후에는 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-128">They don't change once created.</span></span>
> - <span data-ttu-id="7b41d-129">현재 세그먼트 및 측정 값은 새 활동을 기반으로 업데이트되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="7b41d-130">실시간 API를 통해서만 추가된 활동은 내보내기의 일부가 아니며 PowerBI에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="7b41d-131">실시간 API에 연결하는 방법은 다음 두 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="7b41d-132">[간접적으로](#connect-via-the-dynamics-365-customer-insights-connector), [Dynamics 365 Customer Insights 커넥터](/connectors/customerinsights/) 사용</span><span class="sxs-lookup"><span data-stu-id="7b41d-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](/connectors/customerinsights/)</span></span>
- <span data-ttu-id="7b41d-133">[직접적으로](#connect-directly-to-the-real-time-api), 코드 사용</span><span class="sxs-lookup"><span data-stu-id="7b41d-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="7b41d-134">두 방법 모두 다음과 같은 전제 조건이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="7b41d-135">Customer Insights 환경</span><span class="sxs-lookup"><span data-stu-id="7b41d-135">A Customer Insights environment</span></span>
- <span data-ttu-id="7b41d-136">통합 고객 프로필</span><span class="sxs-lookup"><span data-stu-id="7b41d-136">Unified customer profiles</span></span>
- <span data-ttu-id="7b41d-137">구성 및 실행된 활동</span><span class="sxs-lookup"><span data-stu-id="7b41d-137">Activities configured and run</span></span>
- <span data-ttu-id="7b41d-138">계정을 인증하기 위한 기여자 또는 관리자 권한</span><span class="sxs-lookup"><span data-stu-id="7b41d-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="7b41d-139">Dynamics 365 Customer Insights 커넥터를 통해 연결</span><span class="sxs-lookup"><span data-stu-id="7b41d-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="7b41d-140">실시간 API는 코드를 작성하고 배포할 필요 없이 전용 Power Platform커넥터, [Dynamics 365 Customer Insights 커넥터](/connectors/customerinsights/)에서 데이터를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="7b41d-141">커넥터는 API와 동일한 실시간 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="7b41d-142">프리미엄 커넥터에 대한 유효한 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="7b41d-143">자세한 내용은 [Power Apps 및 Power Automate 라이선싱 FAQ](/power-platform/admin/powerapps-flow-licensing-faq)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7b41d-143">For more information, see [Power Apps and Power Automate licensing FAQs](/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="7b41d-144">Power Platform [Power Apps 및/또는 Power Automate](/connectors/)</span><span class="sxs-lookup"><span data-stu-id="7b41d-144">Power Platform [Power Apps and/or Power Automate](/connectors/)</span></span>
- <span data-ttu-id="7b41d-145">Azure [Logic Apps](/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="7b41d-145">Azure [Logic Apps](/azure/connectors/apis-list)</span></span>

<span data-ttu-id="7b41d-146">흐름 만들기에 대한 자세한 내용은 [Power Automate 설명서](/power-automate/)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7b41d-146">For details about creating flows, see the [Power Automate documentation](/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="7b41d-147">실시간 API에 직접 연결</span><span class="sxs-lookup"><span data-stu-id="7b41d-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="7b41d-148">자체 파이프 라인을 구축하고 실시간 API에 직접 연결하여 실시간 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="7b41d-149">원본 시스템 형식이나 UnifiedActivity 형식으로 활동을 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="7b41d-150">/api/instances/{instanceId}/manage/entities/UnifiedActivity에 API를 호출하여 형식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="7b41d-151">매개 변수 및 응답을 포함한이 API의 세부 사항은 [Customer Insights API 참조](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights)의 **EntityData** 섹션에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="7b41d-152">자세한 내용은 [Customer Insights API 작업](apis.md) 도움말 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7b41d-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="7b41d-153">원격 분석으로 실시간 사용 이해</span><span class="sxs-lookup"><span data-stu-id="7b41d-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="7b41d-154">실시간 API에 대한 요청의 양에 대한 개요와 시스템에서 발생할 수 있는 문제에 대한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="7b41d-155">[실시간 원격 분석에 액세스](system.md#api-usage-tab)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b41d-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]