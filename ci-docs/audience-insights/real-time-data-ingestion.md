---
title: 실시간 데이터 수집 및 제한
description: 대상 그룹 인사이트의 실시간 기능에 대한 일반 정보입니다.
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00a72e6a67e33c8e70ccc6139c5e62020f9d3e1
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689183"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="81e4e-103">실시간 데이터 수집(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="81e4e-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="81e4e-104">거의 실시간 기능을 통해 고객이 제품 또는 서비스와 수행한 최신 상호 작용을 몇 초 안에 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="81e4e-105">[예약된 새로 고침](system.md#schedule-tab)에는 많은 수의 레코드와 여러 가지 복잡한 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="81e4e-106">먼저 데이터 원본에서 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="81e4e-107">그런 다음 데이터가 통합된 후 데이터는 추가 정보로 보강됩니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="81e4e-108">이 프로세스를 실행할 때마다 몇 분에서 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="81e4e-109">실시간 기능은 이후에 예약된 새로 고침이 데이터 원본에서이 데이터를 가져올 때까지 즉시 사용할 데이터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="81e4e-110">실시간 업데이트는 만료 시간이 지난 후 더 이상 데이터 원본의 값을 무시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="81e4e-111">프로필 업데이트는 4시간 동안 유지됩니다</span><span class="sxs-lookup"><span data-stu-id="81e4e-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="81e4e-112">활동은 30일 동안 유지됩니다</span><span class="sxs-lookup"><span data-stu-id="81e4e-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="81e4e-113">이 값은 변경할 수 있는 API 호출 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="81e4e-114">이 매개 변수의 사용 목적은 원본 데이터가 신뢰의 소스로 남아 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="81e4e-115">실시간 업데이트를 더 오래 포함하려면 예정된 다음 새로 고침 중에 가져오도록 데이터 원본에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="81e4e-116">통합 고객 프로필 필드의 실시간 업데이트</span><span class="sxs-lookup"><span data-stu-id="81e4e-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="81e4e-117">업데이트된 프로필은 몇 초 이내에 고객 카드 보기 또는 기타 시각화에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="81e4e-118">데이터 통합이 발생한 후 실시간 작업이 수행되므로 통합 고객 프로필에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="81e4e-119">결과적으로 실시간 프로필 변경은 측정, 세그먼트 구성원 자격 또는 보강을 업데이트하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="81e4e-120">제한 사항</span><span class="sxs-lookup"><span data-stu-id="81e4e-120">Limitations</span></span>

- <span data-ttu-id="81e4e-121">고객 프로필은 업데이트할 수 있지만 만들거나 삭제할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="81e4e-122">Power BI 같은 외부 시스템으로 실시간 업데이트 내보내기는 현재로서는 불가능합니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="81e4e-123">활동의 실시간 생성</span><span class="sxs-lookup"><span data-stu-id="81e4e-123">Real-time creation of activities</span></span>

<span data-ttu-id="81e4e-124">실시간 API를 사용하면 원본 시스템(개별 원본 레코드)의 새 활동을 통합 고객 프로필에 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="81e4e-125">새 활동은 통합 고객 프로필의 타임라인에서 몇 초 내에 통합된 활동으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="81e4e-126">고객 카드 보기 또는 구성한 다른 시간 표시줄 통합에서 시간 표시줄을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="81e4e-127">활동은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-127">Activities are immutable.</span></span> <span data-ttu-id="81e4e-128">일단 만들어진 후에는 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-128">They don't change once created.</span></span>
> - <span data-ttu-id="81e4e-129">현재 세그먼트 및 측정 값은 새 활동을 기반으로 업데이트되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="81e4e-130">실시간 API를 통해서만 추가된 활동은 내보내기의 일부가 아니며 PowerBI에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="81e4e-131">실시간 API에 연결하는 방법은 다음 두 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="81e4e-132">[간접적으로](#connect-via-the-dynamics-365-customer-insights-connector), [Dynamics 365 Customer Insights 커넥터](https://docs.microsoft.com/connectors/customerinsights/) 사용</span><span class="sxs-lookup"><span data-stu-id="81e4e-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/)</span></span>
- <span data-ttu-id="81e4e-133">[직접적으로](#connect-directly-to-the-real-time-api), 코드 사용</span><span class="sxs-lookup"><span data-stu-id="81e4e-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="81e4e-134">두 방법 모두 다음과 같은 전제 조건이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="81e4e-135">Customer Insights 환경</span><span class="sxs-lookup"><span data-stu-id="81e4e-135">A Customer Insights environment</span></span>
- <span data-ttu-id="81e4e-136">통합 고객 프로필</span><span class="sxs-lookup"><span data-stu-id="81e4e-136">Unified customer profiles</span></span>
- <span data-ttu-id="81e4e-137">구성 및 실행된 활동</span><span class="sxs-lookup"><span data-stu-id="81e4e-137">Activities configured and run</span></span>
- <span data-ttu-id="81e4e-138">계정을 인증하기 위한 기여자 또는 관리자 권한</span><span class="sxs-lookup"><span data-stu-id="81e4e-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="81e4e-139">Dynamics 365 Customer Insights 커넥터를 통해 연결</span><span class="sxs-lookup"><span data-stu-id="81e4e-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="81e4e-140">실시간 API는 코드를 작성하고 배포할 필요 없이 전용 Power Platform커넥터, [Dynamics 365 Customer Insights 커넥터](https://docs.microsoft.com/connectors/customerinsights/)에서 데이터를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="81e4e-141">커넥터는 API와 동일한 실시간 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="81e4e-142">프리미엄 커넥터에 대한 유효한 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="81e4e-143">자세한 내용은 [Power Apps 및 Power Automate 라이선싱 FAQ](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="81e4e-143">For more information, see [Power Apps and Power Automate licensing FAQs](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="81e4e-144">Power Platform [Power Apps 및/또는 Power Automate](https://docs.microsoft.com/connectors/)</span><span class="sxs-lookup"><span data-stu-id="81e4e-144">Power Platform [Power Apps and/or Power Automate](https://docs.microsoft.com/connectors/)</span></span>
- <span data-ttu-id="81e4e-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="81e4e-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span></span>

<span data-ttu-id="81e4e-146">흐름 만들기에 대한 자세한 내용은 [Power Automate 설명서](https://docs.microsoft.com/power-automate/)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="81e4e-146">For details about creating flows, see the [Power Automate documentation](https://docs.microsoft.com/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="81e4e-147">실시간 API에 직접 연결</span><span class="sxs-lookup"><span data-stu-id="81e4e-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="81e4e-148">자체 파이프 라인을 구축하고 실시간 API에 직접 연결하여 실시간 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="81e4e-149">원본 시스템 형식이나 UnifiedActivity 형식으로 활동을 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="81e4e-150">/api/instances/{instanceId}/manage/entities/UnifiedActivity에 API를 호출하여 형식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="81e4e-151">매개 변수 및 응답을 포함한이 API의 세부 사항은 [Customer Insights API 참조](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights)의 **EntityData** 섹션에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="81e4e-152">자세한 내용은 [Customer Insights API 작업](apis.md) 도움말 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81e4e-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="81e4e-153">원격 분석으로 실시간 사용 이해</span><span class="sxs-lookup"><span data-stu-id="81e4e-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="81e4e-154">실시간 API에 대한 요청의 양에 대한 개요와 시스템에서 발생할 수 있는 문제에 대한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="81e4e-155">**관리자** > **시스템** > **API 사용** 으로 이동하여 [실시간 원격 분석에 액세스](system.md#api-usage-tab)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-155">You can [access the real-time telemetry](system.md#api-usage-tab) by going to **Admin** > **System** > **API usage**.</span></span> <span data-ttu-id="81e4e-156">**작업** 테이블에서 실시간 메서드를 사용하는 API 작업 행에는 실시간 API 사용량을 볼 수 있는 버튼이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-156">In the **Operations** table, rows for API operations which use the real-time methods contain a button to view real-time API usage.</span></span> <span data-ttu-id="81e4e-157">버튼은 쌍안경 기호로 시각화됩니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-157">The button is visualized with a binocular symbol.</span></span> <span data-ttu-id="81e4e-158">버튼을 선택하여 현재 환경에서 실시간 API 사용에 대한 사용 세부 정보가 포함된 사이드 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-158">Select the button to open a side pane containing usage details for the real-time API usage in the current environment.</span></span>

<span data-ttu-id="81e4e-159">**그룹화 기준** 선택기를 사용하여 지난 24시간에서 30일까지의 타임라인에서 실시간 상호 작용을 가장 잘 표현할 수 있는 방법을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-159">Use the **Group by** selector to choose how to best present your real-time interactions on a timeline ranging from the last 24 hours to the last 30 days.</span></span> <span data-ttu-id="81e4e-160">API 메서드, 엔터티 규정이름(대상 엔터티), (이벤트 소스), 결과(성공 또는 실패) 또는 오류 코드별로 데이터를 그룹화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-160">You can group the data by API method, entity qualified name (ingested entity), created by (source of the event), result (success or failure) or error codes.</span></span> <span data-ttu-id="81e4e-161">데이터는 이력 차트 및 테이블로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="81e4e-161">The data is available as a history chart and as a table.</span></span>
