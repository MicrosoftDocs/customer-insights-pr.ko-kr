---
title: 고객 카드 추가 기능 설치 및 구성
description: Dynamics 365 Customer Insights용 고객 카드 추가 기능을 설치하고 구성합니다.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f3c4a01f9ce7749eeee72f7901620dae7cb9b8d3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597335"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="7628e-103">고객 카드 추가 기능(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="7628e-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="7628e-104">Dynamics 365 앱에서 직접 고객에 대한 모든 측면 보기를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="7628e-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="7628e-105">고객 카드 추가 기능으로 인구 통계, 인사이트 및 활동 일정을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7628e-106">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="7628e-106">Prerequisites</span></span>

- <span data-ttu-id="7628e-107">통합 인터페이스가 활성화된 영업 허브 또는 고객 서비스 허브와 같은 Dynamics 365 앱, 버전 9.0 이상.</span><span class="sxs-lookup"><span data-stu-id="7628e-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="7628e-108">[Common Data Service를 사용하여 Dynamics 365 앱에서 수집](connect-power-query.md)된 고객 프로필입니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="7628e-109">고객 카드 추가 기능의 사용자는 대상 그룹 인사이트에서 [사용자로 추가](permissions.md)되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="7628e-110">[구성된 검색 및 필터 기능](search-filter-index.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="7628e-111">인구 통계 제어: 통합 고객 프로필에서 인구 통계 필드(예: 연령 또는 성별)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="7628e-112">보강 제어: 활성 [보강](enrichment-hub.md)이 고객 프로필에 적용되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="7628e-113">인텔리전스 제어: Azure Machine Learning([예측](predictions.md) 또는 [사용자 지정 모델](custom-models.md))을 사용하여 생성된 데이터 필요</span><span class="sxs-lookup"><span data-stu-id="7628e-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="7628e-114">측정값 제어: [구성된 측정값](measures.md)이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="7628e-115">시간 표시줄 제어: [구성된 활동](activities.md)이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="7628e-116">고객 카드 추가 기능 설치</span><span class="sxs-lookup"><span data-stu-id="7628e-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="7628e-117">고객 카드 추가 기능은 Dynamics 365의 Customer Engagement 앱을 위한 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="7628e-118">솔루션을 설치하려면 AppSource로 이동하고 **Dynamics 고객 카드** 를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="7628e-119">[AppSource에서 고객 카드 추가 기능](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview)을 선택하고 **지금 가져 오기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="7628e-120">솔루션을 설치하려면 Dynamics 365 앱에 대한 관리자 자격 증명으로 로그인해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="7628e-121">솔루션을 환경에 설치하는 데 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="7628e-122">고객 카드 추가 기능 구성</span><span class="sxs-lookup"><span data-stu-id="7628e-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="7628e-123">관리자로서 Dynamics 365에서 **설정** 섹션으로 이동하고 **솔루션** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="7628e-124">**Dynamics 365 Customer Insights 고객 카드 추가 기능(미리 보기)** 솔루션에 대한 **표시 이름** 링크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7628e-125">![표시 이름 선택](media/select-display-name.png "표시 이름 선택")</span><span class="sxs-lookup"><span data-stu-id="7628e-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="7628e-126">**로그인** 을 선택하고 Customer Insights를 구성하는 데 사용하는 관리자 계정의 자격 증명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7628e-127">**로그인** 단추를 선택할 때 브라우저 팝업 차단 기능이 인증 창을 차단하지 않는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="7628e-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="7628e-128">데이터를 가져오려는 환경을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="7628e-129">Dynamics 365 앱에서 레코드에 대한 필드 매핑을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="7628e-130">연락처와 매핑하려면 연락처 엔터티의 ID와 일치하는 고객 엔터티의 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="7628e-131">계정과 매핑하려면 연락처 엔터티의 ID와 일치하는 계정 엔터티의 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7628e-132">![연락처 ID 필드](media/contact-id-field.png "연락처 ID 필드")</span><span class="sxs-lookup"><span data-stu-id="7628e-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="7628e-133">**구성 저장** 을 선택하여 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="7628e-134">그런 다음 사용자가 고객 카드를 사용자 지정하고 볼 수 있도록 Dynamics 365에서 보안 역할을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="7628e-135">Dynamics 365에서 **설정** > **보안** > **사용자** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="7628e-136">사용자 역할을 편집할 사용자를 선택하고 **역할 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="7628e-137">전체 조직에 대해 카드에 표시되는 콘텐츠를 사용자 지정할 사용자에게 **Customer Insights 카드 사용자 지정자** 역할을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="7628e-138">양식에 고객 카드 제어 추가</span><span class="sxs-lookup"><span data-stu-id="7628e-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="7628e-139">연락처 양식에 고객 카드 컨트롤을 추가하려면 Dynamics 365에서에서 **설정** > **사용자 지정** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="7628e-140">**시스템 사용자 지정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="7628e-141">**연락처** 엔터티를 찾아 확장한 다음 **양식** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="7628e-142">고객 카드 컨트롤을 추가할 연락처 양식을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7628e-143">![연락처 양식 선택](media/contact-active-forms.png "연락처 양식 선택")</span><span class="sxs-lookup"><span data-stu-id="7628e-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="7628e-144">양식 편집기에서 컨트롤을 추가하려면 **필드 탐색기** 에서 컨트롤을 배치할 위치로 필드를 드래그합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="7628e-145">방금 추가한 양식에서 필드를 선택한 다음 **속성 변경** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="7628e-146">**컨트롤** 탭으로 이동하여 **컨트롤 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="7628e-147">사용 가능한 사용자 지정 컨트롤 중 하나를 선택하고 **추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="7628e-148">**필드 속성** 대화 상자에서 **양식에 레이블 표시** 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="7628e-149">컨트롤에 대해 **웹** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="7628e-150">보강 컨트롤의 경우 **enrichmentType** 필드를 구성하여 표시하고자 하는 강화 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="7628e-151">각 보강 유형에 대해 별도의 보강 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="7628e-152">**저장** 과 **게시** 를 선택하여 업데이트된 연락처 양식을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="7628e-153">게시된 연락처 양식으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-153">Go to the published contact form.</span></span> <span data-ttu-id="7628e-154">새로 추가된 컨트롤이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-154">You'll see the newly added control.</span></span> <span data-ttu-id="7628e-155">처음 사용할 때 로그인해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="7628e-156">사용자 지정 컨트롤에 표시할 내용을 사용자 지정하려면 오른쪽 상단에서 편집 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="7628e-157">고객 카드 추가 기능 업그레이드</span><span class="sxs-lookup"><span data-stu-id="7628e-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="7628e-158">고객 카드 추가 기능은 자동으로 업그레이드되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="7628e-159">최신 버전으로 업그레이드하려면 추가 기능이 설치된 Dynamics 365 앱에서 이 절차를 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="7628e-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="7628e-160">Dynamics 365 앱에서 **설정** > **사용자 지정** 으로 이동하고 **솔루션** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="7628e-161">추가 기능 테이블에서 **CustomerInsightsCustomerCard** 를 찾아 행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="7628e-162">작업 표시줄에서 **솔루션 업그레이드 적용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Dynamics 365 앱의 사용자 지정 영역에서 솔루션 업그레이드":::

1. <span data-ttu-id="7628e-164">업그레이드 프로세스를 시작하면 업그레이드가 완료될 때까지 로딩 표시기가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="7628e-165">최신 버전이 없으면 업그레이드 시 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7628e-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]