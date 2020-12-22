---
title: GDPR에 따른 데이터 주체 권한(DSR) 요청 | Microsoft Docs
description: Dynamics 365 Customer Insights 대상 그룹 통계 기능에 대한 데이터 주체 요청에 응답합니다.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f276a73feca52023391ad92fbc84359921b85328
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406294"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="4a06f-103">GDPR에 따른 데이터 주체 권한(DSR) 요청</span><span class="sxs-lookup"><span data-stu-id="4a06f-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="4a06f-104">Dynamics 365 Customer Insights 대상 그룹 인사이트 기능에 대한 GDPR 데이터 주체 삭제 요청에 응답</span><span class="sxs-lookup"><span data-stu-id="4a06f-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="4a06f-105">조직의 고객 데이터에서 개인 데이터를 "제거할 수 있는 권한"은 일반 데이터 보호 규정(GDPR)에서 핵심적인 보호입니다.</span><span class="sxs-lookup"><span data-stu-id="4a06f-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="4a06f-106">개인 데이터 제거에는 감사 로그 정보를 제외한 모든 개인 데이터 및 시스템 생성 로그 제거가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a06f-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="4a06f-107">데이터 주체 삭제 요청 관리</span><span class="sxs-lookup"><span data-stu-id="4a06f-107">Manage data subject delete requests</span></span>

<span data-ttu-id="4a06f-108">대상 그룹 인사이트는 특정 고객 또는 Customer Insights 사용자의 개인 데이터를 삭제하기 위해 다음과 같은 제품 내 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4a06f-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="4a06f-109">**고객 데이터에 대한 삭제 요청 관리**: Customer Insights의 고객 데이터는 Customer Insights 외부의 원래 데이터 원본에서 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a06f-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="4a06f-110">모든 GDPR 삭제 요청은 원래 데이터 원본에서 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a06f-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="4a06f-111">**Customer Insights 사용자 데이터에 대한 삭제 요청 관리**: 사용자 데이터는 Customer Insights에서 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a06f-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="4a06f-112">모든 GDPR 삭제 요청은 Customer Insights에서 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a06f-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="4a06f-113">고객 데이터에 대한 삭제 요청 관리</span><span class="sxs-lookup"><span data-stu-id="4a06f-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="4a06f-114">Customer Insights 관리자는 다음 단계에 따라 데이터 원본에서 삭제된 고객 데이터를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a06f-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="4a06f-115">Dynamics 365 Customer Insights에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="4a06f-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="4a06f-116">대상 그룹 인사이트에서 **데이터** > **데이터 원본** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4a06f-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="4a06f-117">삭제된 고객 데이터가 포함된 목록의 각 데이터 원본의 경우:</span><span class="sxs-lookup"><span data-stu-id="4a06f-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="4a06f-118">(...)을 선택하고 **새로 고침** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a06f-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="4a06f-119">**상태** 아래에서 데이터 원본의 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4a06f-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="4a06f-120">확인 표시는 새로 고침이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4a06f-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="4a06f-121">경고 삼각형은 문제가 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="4a06f-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="4a06f-122">경고 삼각형이 표시되면 D365CI@microsoft.com에 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="4a06f-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4a06f-123">![고객 데이터에 대한 GDPR 삭제 요청 처리](media/gdpr-data-sources.png "고객 데이터에 대한 GDPR 삭제 요청 처리")</span><span class="sxs-lookup"><span data-stu-id="4a06f-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="4a06f-124">사용자 데이터에 대한 삭제 요청 관리</span><span class="sxs-lookup"><span data-stu-id="4a06f-124">Manage delete requests for user data</span></span>

<span data-ttu-id="4a06f-125">Customer Insights 관리자는 다음 단계에 따라 Customer Insights 사용자 데이터를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a06f-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="4a06f-126">Dynamics 365 Customer Insights에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="4a06f-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="4a06f-127">대상 그룹 인사이트에서 **관리** > **권한** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4a06f-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="4a06f-128">삭제하려는 사용자의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a06f-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="4a06f-129">**제거** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a06f-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4a06f-130">![사용자 데이터에 대한 GDPR 삭제 요청 처리](media/gdpr-permissions.png "사용자 데이터에 대한 GDPR 삭제 요청 처리")</span><span class="sxs-lookup"><span data-stu-id="4a06f-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="4a06f-131">GDPR 데이터 주체 내보내기 요청에 응답</span><span class="sxs-lookup"><span data-stu-id="4a06f-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="4a06f-132">일반 데이터 보호 규정(GDPR)을 향한 여정에서 귀하와 파트너 관계를 맺겠다는 약속의 일환으로, 준비에 도움이 되는 문서를 개발했습니다.</span><span class="sxs-lookup"><span data-stu-id="4a06f-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="4a06f-133">이 문서에서는 대상 그룹 인사이트를 사용할 때 GDPR 규정 준수를 지원하기 위해 오늘 수행할 수 있는 단계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4a06f-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="4a06f-134">내보내기 및 보기 요청 관리</span><span class="sxs-lookup"><span data-stu-id="4a06f-134">Manage export and view requests</span></span>

<span data-ttu-id="4a06f-135">데이터 이식성의 권리는 데이터 주체가 다른 데이터 컨트롤러로 전송될 수 있는 전자 형식(“구조화되고, 일반적으로 사용되며, 기계 판독 가능하며, 상호 운용 가능한 형식”으로 정의됨)으로 개인 데이터의 복사본을 요청할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a06f-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="4a06f-136">고객 데이터 내보내기(테넌트 관리자)</span><span class="sxs-lookup"><span data-stu-id="4a06f-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="4a06f-137">테넌트 관리자는 다음 단계에 따라 데이터를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a06f-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="4a06f-138">요청에 고객의 전자 메일 주소를 지정하여 D365CI@microsoft.com으로 전자 메일을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="4a06f-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="4a06f-139">Customer Insights 팀은 등록된 테넌트 관리자 이메일 주소로 이메일을 보내 데이터 내보내기 확인을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="4a06f-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="4a06f-140">요청한 고객의 데이터를 내보내려면 확인을 승인합니다.</span><span class="sxs-lookup"><span data-stu-id="4a06f-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="4a06f-141">테넌트 관리자 전자 메일 주소를 통해 내보낸 데이터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="4a06f-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="4a06f-142">사용자 데이터 내보내기(테넌트 관리자)</span><span class="sxs-lookup"><span data-stu-id="4a06f-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="4a06f-143">요청에 사용자의 전자 메일 주소를 지정하여 D365CI@microsoft.com으로 전자 메일을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="4a06f-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="4a06f-144">Customer Insights 팀은 등록된 테넌트 관리자 이메일 주소로 이메일을 보내 데이터 내보내기 확인을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="4a06f-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="4a06f-145">요청한 사용자의 데이터를 내보내려면 확인을 승인합니다.</span><span class="sxs-lookup"><span data-stu-id="4a06f-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="4a06f-146">테넌트 관리자 전자 메일 주소를 통해 내보낸 데이터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="4a06f-146">Receive the exported data through the tenant admin email address.</span></span>
