---
title: API에 대한 작업
description: API를 사용하고 제한 사항을 이해합니다.
ms.date: 03/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 011fa700563c53534554a6b73e87c2391bfdf714
ms.sourcegitcommit: a872f59e6febe4d4bd678ddd0b60a1660acca0f3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "5710468"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="8aa44-103">Customer Insights API에 대한 작업</span><span class="sxs-lookup"><span data-stu-id="8aa44-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="8aa44-104">Dynamics 365 Customer Insights는 Customer Insights의 데이터를 기반으로 자체 애플리케이션을 구축하는 API를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8aa44-105">이러한 API에 대한 자세한 내용은 [Customer Insights API 참조](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights)에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="8aa44-106">여기에는 작업, 매개 변수 및 응답에 대한 추가 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="8aa44-107">이 문서에서는 Customer Insights API에 액세스하고, Azure 앱 등록을 만들고, 사용 가능한 클라이언트 라이브러리를 시작하는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="8aa44-108">Customer Insights API로 시작하기</span><span class="sxs-lookup"><span data-stu-id="8aa44-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="8aa44-109">Customer Insights에 [로그인](https://home.ci.ai.dynamics.com)합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="8aa44-110">아직 구독하지 않은 경우 [Customer Insights 평가판에 등록](https://aka.ms/tryci)하세요.</span><span class="sxs-lookup"><span data-stu-id="8aa44-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="8aa44-111">Customer Insights 환경에서 API를 사용하려면 **관리** > **권한** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="8aa44-112">이렇게 하려면 관리자 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="8aa44-113">**API** 탭으로 이동하고 **사용** 버튼을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="8aa44-114">API를 사용하면 API 요청에 사용되는 인스턴스의 기본 및 보조 구독 키가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="8aa44-115">**관리** > **권한** > **API** 에서 **기본 다시 생성** 또는 **보조 다시 생성** 을 선택하여 키를 다시 생성 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Customer Insights API 사용":::

1. <span data-ttu-id="8aa44-117">**API 탐색** 을 선택하여 [API를 사용해 봅니다](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span><span class="sxs-lookup"><span data-stu-id="8aa44-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="8aa44-118">API 작업을 선택하고 **둘러보기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="8aa44-119">측면 창에서 **권한** 드롭다운 메뉴의 값을 **암시적** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="8aa44-120">`Authorization` 헤더에 전달자 토큰이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="8aa44-121">구독 키가 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="8aa44-122">필요한 경우 모든 필수 쿼리 매개 변수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="8aa44-123">측면 창 하단으로 스크롤하고 **보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="8aa44-124">HTTP 응답이 곧 아래에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-124">The HTTP response will soon appear below.</span></span>


   :::image type="content" source="media/try-apis.gif" alt-text="API 테스트를 선택하는 방법을 보여주는 애니메이션 GIF입니다.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="8aa44-126">Azure Portal에 새 앱 등록을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="8aa44-127">이러한 단계는 위임된 권한을 사용하여 Azure 애플리케이션에서 Customer Insights API 사용을 시작하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-127">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="8aa44-128">먼저 [시작 섹션](#get-started-trying-the-customer-insights-apis)을 완료했는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="8aa44-128">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="8aa44-129">Customer Insights 데이터에 액세스할 수 있는 계정으로 [Azure Portal](https://portal.azure.com)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="8aa44-130">왼쪽에서 **앱 등록** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="8aa44-131">**새 등록** 을 선택하고 애플리케이션 이름을 제공하고 계정 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-131">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="8aa44-132">원하는 경우 리디렉션 URL을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="8aa44-133">http://localhost는 로컬 컴퓨터에서 애플리케이션을 개발하는 데 충분합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="8aa44-134">새 앱 등록에서 **API 권한** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="앱 등록에서 API 권한을 설정하는 애니메이션 GIF입니다.":::

1. <span data-ttu-id="8aa44-136">**권한 추가** 를 선택하고 측면 창에서 **Customer Insights** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="8aa44-137">**권한 유형** 으로 **위임된 권한** 을 선택하고 **user_impersonation** 권한을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-137">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="8aa44-138">**권한 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-138">Select **Add permissions**.</span></span> <span data-ttu-id="8aa44-139">사용자 로그인없이 API에 액세스해야 하는 경우 [서버 간 애플리케이션 권한](#server-to-server-application-permissions) 섹션을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="8aa44-140">**관리자 동의 허용...** 을 선택하여 앱 등록을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="8aa44-141">MSAL(Microsoft 인증 라이브러리)에이 앱 등록을위한 애플리케이션/클라이언트 ID를 사용하여 API에 대한 요청과 함께 보낼 전달자 토큰을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="관리자 동의를 권한 부여하는 애니메이션 GIF입니다.":::

<span data-ttu-id="8aa44-143">MSAL에 대한 자세한 내용은 [MSAL(Microsoft 인증 라이브러리) 개요](https://docs.microsoft.com/azure/active-directory/develop/msal-overview)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8aa44-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="8aa44-144">Azure의 앱 등록에 대한 자세한 내용은 [새로운 Azure Portal 앱 등록 환경](/azure/active-directory/develop/app-registration-portal-training-guide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8aa44-144">For more information about app registration in Azure, see [The new Azure portal app registration experience](/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="8aa44-145">클라이언트 라이브러리 API 사용에 대한 자세한 내용은 [Customer Insights 클라이언트 라이브러리](#customer-insights-client-libraries)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8aa44-145">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="8aa44-146">서버 간 애플리케이션 권한</span><span class="sxs-lookup"><span data-stu-id="8aa44-146">Server-to-server application permissions</span></span>

<span data-ttu-id="8aa44-147">[앱 등록 섹션](#create-a-new-app-registration-in-the-azure-portal)에서는 사용자가 인증을 위해 로그인해야 하는 앱을 등록하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="8aa44-148">사용자 상호 작용이 필요하지 않고 서버에서 실행할 수 있는 앱 등록을 만드는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="8aa44-149">Azure Portal의 앱 등록에서 **API 권한** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="8aa44-150">**권한 추가** 를 선택하고 측면 창에서 **Customer Insights** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-150">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="8aa44-151">**권한 유형** 의 경우 **애플리케이션 권한** 을 선택하고 **CustomerInsights.Api.All** 권한을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-151">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="8aa44-152">**권한 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-152">Select **Add permissions**.</span></span>

1. <span data-ttu-id="8aa44-153">이 애플리케이션 권한에 대한 관리자 동의를 제공하려면 서비스 주체를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-153">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="8aa44-154">AD(Azure Active Directory) PowerShell 모듈 설치: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="8aa44-154">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="8aa44-155">AD 계정에 연결: `Connect-AzureAD -TenantId <your tenant id>`</span><span class="sxs-lookup"><span data-stu-id="8aa44-155">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="8aa44-156">**개요** > **Azure Active Directory** 에 테넌트 ID를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-156">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="8aa44-157">다음 명령을 실행하여 Azure AD 서비스 주체 추가: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` AppId 매개 변수는 Customer Insights API 앱과 관련됩니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-157">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="서비스 주체 이름":::

1. <span data-ttu-id="8aa44-159">앱 등록을 위한 **API 권한** 으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-159">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="8aa44-160">**관리자 동의 허용...** 을 선택하여 앱 등록을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-160">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="관리자 동의를 권한 부여하는 애니메이션 GIF입니다.":::

1. <span data-ttu-id="8aa44-162">마지막으로 Customer Insights에서 사용자로 앱 등록 이름을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-162">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="8aa44-163">Customer Insights를 열고 **관리자** > **권한** 으로 이동하고 **사용자 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-163">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="8aa44-164">앱 등록 이름을 검색하고 검색 결과에서 선택한 다음 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-164">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="8aa44-165">Customer Insights 클라이언트 라이브러리</span><span class="sxs-lookup"><span data-stu-id="8aa44-165">Customer Insights client libraries</span></span>

<span data-ttu-id="8aa44-166">이 섹션은 Customer Insights API에 사용할 수 있는 클라이언트 라이브러리 사용을 시작하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-166">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="8aa44-167">모든 라이브러리 소스 코드 및 샘플 애플리케이션은 [Customer Insights GitHub 페이지](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-167">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="8aa44-168">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="8aa44-168">C# NuGet</span></span>

<span data-ttu-id="8aa44-169">NuGet.org에서 C# 클라이언트 라이브러리 사용을 시작하는 방법을 알아봅니다. NuGet 패키지에 대한 자세한 내용은 [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8aa44-169">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="8aa44-170">현재 이 패키지는 netstandard2.0 및 netcoreapp2.0 프레임워크를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-170">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="8aa44-171">C# 프로젝트에 C# 클라이언트 라이브러리 추가</span><span class="sxs-lookup"><span data-stu-id="8aa44-171">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="8aa44-172">Visual Studio에서 프로젝트의 **NuGet 패키지 관리자** 를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-172">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="8aa44-173">**Microsoft.Dynamics.CustomerInsights.Api** 를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-173">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="8aa44-174">**설치** 를 선택하여 프로젝트에 패키지를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-174">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="8aa44-175">또는 다음 명령을 **NuGet 패키지 관리자 콘솔** 에 실행합니다. `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="8aa44-175">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Visual Studio 프로젝트에 NuGet 패키지 추가":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="8aa44-177">C# 클라이언트 라이브러리 사용</span><span class="sxs-lookup"><span data-stu-id="8aa44-177">Use the C# client library</span></span>

1. <span data-ttu-id="8aa44-178">[MSAL(Microsoft 인증 라이브러리)](/azure/active-directory/develop/msal-overview)을 사용하여 기존 [Azure 앱 등록](#create-a-new-app-registration-in-the-azure-portal)을 사용하여 `AccessToken`를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-178">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="8aa44-179">토큰을 성공적으로 인증하고 획득한 후 추가 **DefaultRequestHeaders "인증"** 을 **전달자 <access token>** 으로 설정하고 **Ocp-Apim-Subscription-Key** 를 [Customer Insights 환경의 **구독 키**](#get-started-trying-the-customer-insights-apis)로 설정하여 새 'HttpClient'를 구성하거나 기존`HttpClient`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-179">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="8aa44-180">적절한 경우 **권한 부여** 헤더를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-180">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="8aa44-181">예를 들어 토큰이 만료된 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-181">For example, when the token expired.</span></span>

1. <span data-ttu-id="8aa44-182">이 `HttpClient`를 `CustomerInsights` 클라이언트의 구성에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-182">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="httpclient 샘플":::

1. <span data-ttu-id="8aa44-184">클라이언트를 사용하여 '확장 메서드'(예: `GetAllInstancesAsync`)를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-184">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="8aa44-185">기본 `Microsoft.Rest.HttpOperationResponse`에 대한 액세스를 선호하는 경우 "http 메시지 메서드"(예: `GetAllInstancesWithHttpMessagesAsync`)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-185">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="8aa44-186">메서드가 여러 유형(예: `IList<InstanceInfo>` 및 `ApiErrorResult`)을 반환할 수 있으므로 응답은 `object` 유형일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-186">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="8aa44-187">반환 유형을 확인하려면 해당 작업의 [API 세부 정보 페이지](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights)에 지정된 응답 유형으로 객체를 안전하게 캐스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-187">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="8aa44-188">요청에 대한 추가 정보가 필요한 경우 **http 메시지 방법** 을 사용하여 원시 응답 객체에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa44-188">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="8aa44-189">NodeJS 패키지</span><span class="sxs-lookup"><span data-stu-id="8aa44-189">NodeJS package</span></span>

<span data-ttu-id="8aa44-190">NPM을 통해 제공되는 NodeJS 클라이언트 라이브러리 사용: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="8aa44-190">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="8aa44-191">Python 패키지</span><span class="sxs-lookup"><span data-stu-id="8aa44-191">Python package</span></span>

<span data-ttu-id="8aa44-192">PyPi를 통해 제공되는 Python 클라이언트 라이브러리 사용: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="8aa44-192">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
