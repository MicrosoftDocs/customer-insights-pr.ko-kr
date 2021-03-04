---
title: API에 대한 작업
description: API를 사용하고 제한 사항을 이해합니다.
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 966db1a22e7dece1bcd89733880bce059151157f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267532"
---
# <a name="work-with-customer-insights-apis"></a>Customer Insights API에 대한 작업

Dynamics 365 Customer Insights는 Customer Insights의 데이터를 기반으로 자체 애플리케이션을 구축하는 API를 제공합니다.

> [!IMPORTANT]
> 이러한 API에 대한 자세한 내용은 [Customer Insights API 참조](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights)에 나열되어 있습니다. 여기에는 작업, 매개 변수 및 응답에 대한 추가 정보가 포함됩니다.

이 문서에서는 Customer Insights API에 액세스하고, Azure 앱 등록을 만들고, 사용 가능한 클라이언트 라이브러리를 시작하는 데 도움을 줍니다.

## <a name="get-started-trying-the-customer-insights-apis"></a>Customer Insights API로 시작하기

1. Customer Insights에 [로그인](https://home.ci.ai.dynamics.com)합니다. 아직 구독하지 않은 경우 [Customer Insights 평가판에 등록](https://aka.ms/tryci)하세요.

1. Customer Insights 환경에서 API를 사용하려면 **관리** > **권한** 으로 이동합니다. 이렇게 하려면 관리자 권한이 필요합니다.

1. **API** 탭으로 이동하고 **사용** 버튼을 선택합니다.    
   API를 사용하면 API 요청에 사용되는 인스턴스의 기본 및 보조 구독 키가 생성됩니다. **관리** > **권한** > **API** 에서 **기본 다시 생성** 또는 **보조 다시 생성** 을 선택하여 키를 다시 생성 할 수 있습니다.

   :::image type="content" source="media/enable-apis.gif" alt-text="Customer Insights API 사용":::

1. **API 탐색** 을 선택하여 API를 사용해봅니다.

1. API 작업을 선택하고 **둘러보기** 를 선택합니다.

1. 측면 창에서 **권한** 드롭다운 메뉴의 값을 **암시적** 으로 설정합니다. `Authorization` 헤더에 전달자 토큰이 추가됩니다. 구독 키가 자동으로 채워집니다.
  
1. 필요한 경우 모든 필수 쿼리 매개 변수를 추가합니다.

1. 측면 창 하단으로 스크롤하고 **보내기** 를 선택합니다.

HTTP 응답이 곧 아래에 표시됩니다.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Azure Portal에 새 앱 등록을 만듭니다.

이러한 단계는 위임된 권한을 사용하여 Azure 애플리케이션에서 Customer Insights API 사용을 시작하는 데 도움이 됩니다. 먼저 [시작 섹션](#get-started-trying-the-customer-insights-apis)을 완료했는지 확인하세요.

1. Customer Insights 데이터에 액세스할 수 있는 계정으로 [Azure Portal](https://portal.azure.com)에 로그인합니다.

1. 왼쪽에서 **앱 등록** 을 선택합니다.

1. **새 등록** 을 선택하고 애플리케이션 이름을 제공하고 계정 유형을 선택합니다.
   원하는 경우 리디렉션 URL을 추가합니다. http://localhost는 로컬 컴퓨터에서 애플리케이션을 개발하는 데 충분합니다.

1. 새 앱 등록에서 **API 권한** 으로 이동합니다.

1. **권한 추가** 를 선택하고 측면 창에서 **Customer Insights** 를 선택합니다.

1. **권한 유형** 으로 **위임된 권한** 을 선택하고 **user_impersonation** 권한을 선택합니다.

1. **권한 추가** 를 선택합니다. 사용자 로그인없이 API에 액세스해야 하는 경우 [서버 간 애플리케이션 권한](#server-to-server-application-permissions) 섹션을 검토합니다.

1. **관리자 동의 허용...** 을 선택하여 앱 등록을 완료합니다.

MSAL(Microsoft 인증 라이브러리)에이 앱 등록을위한 애플리케이션/클라이언트 ID를 사용하여 API에 대한 요청과 함께 보낼 전달자 토큰을 얻을 수 있습니다.

MSAL에 대한 자세한 내용은 [MSAL(Microsoft 인증 라이브러리) 개요](https://docs.microsoft.com/azure/active-directory/develop/msal-overview)를 참조하세요.

Azure의 앱 등록에 대한 자세한 내용은 [새로운 Azure Portal 앱 등록 환경](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide)을 참조하세요.

클라이언트 라이브러리 API 사용에 대한 자세한 내용은 [Customer Insights 클라이언트 라이브러리](#customer-insights-client-libraries)를 참조하세요.

### <a name="server-to-server-application-permissions"></a>서버 간 애플리케이션 권한

[앱 등록 섹션](#create-a-new-app-registration-in-the-azure-portal)에서는 사용자가 인증을 위해 로그인해야 하는 앱을 등록하는 방법을 설명합니다. 사용자 상호 작용이 필요하지 않고 서버에서 실행할 수 있는 앱 등록을 만드는 방법을 알아봅니다.

1. Azure Portal의 앱 등록에서 **API 권한** 으로 이동합니다.

1. **권한 추가** 를 선택하고 측면 창에서 **Customer Insights** 를 선택합니다.

1. **권한 유형** 의 경우 **애플리케이션 권한** 을 선택하고 **CustomerInsights.Api.All** 권한을 선택합니다.

1. **권한 추가** 를 선택합니다.

1. 이 애플리케이션 권한에 대한 관리자 동의를 제공하려면 서비스 주체를 추가해야 합니다.

   1. AD(Azure Active Directory) PowerShell 모듈 설치: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`
   1. AD 계정에 연결: `Connect-AzureAD -TenantId <your tenant id>` **개요** > **Azure Active Directory** 에 테넌트 ID를 찾을 수 있습니다.
   1. 다음 명령을 실행하여 Azure AD 서비스 주체 추가: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` AppId 매개 변수는 Customer Insights API 앱과 관련됩니다.

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="서비스 주체 이름":::

1. 앱 등록을 위한 **API 권한** 으로 돌아갑니다.

1. **관리자 동의 허용...** 을 선택하여 앱 등록을 완료합니다.

1. 마지막으로 Customer Insights에서 사용자로 앱 등록 이름을 추가해야 합니다.    
   Customer Insights를 열고 **관리자** > **권한** 으로 이동하고 **사용자 추가** 를 선택합니다.

1. 앱 등록 이름을 검색하고 검색 결과에서 선택한 다음 **저장** 을 선택합니다.

## <a name="customer-insights-client-libraries"></a>Customer Insights 클라이언트 라이브러리

이 섹션은 Customer Insights API에 사용할 수 있는 클라이언트 라이브러리 사용을 시작하는 데 도움이 됩니다.

### <a name="c-nuget"></a>C# NuGet

NuGet.org에서 C# 클라이언트 라이브러리 사용을 시작하는 방법을 알아봅니다. NuGet 패키지에 대한 자세한 내용은 [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/)를 참조하세요. 현재 이 패키지는 netstandard2.0 및 netcoreapp2.0 프레임워크를 대상으로 합니다.

#### <a name="add-the-c-client-library-to-a-c-project"></a>C# 프로젝트에 C# 클라이언트 라이브러리 추가

1. Visual Studio에서 프로젝트의 **NuGet 패키지 관리자** 를 엽니다.

1. **Microsoft.Dynamics.CustomerInsights.Api** 를 검색합니다.

1. **설치** 를 선택하여 프로젝트에 패키지를 추가합니다.
   또는 다음 명령을 **NuGet 패키지 관리자 콘솔** 에 실행합니다. `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Visual Studio 프로젝트에 NuGet 패키지 추가":::

#### <a name="use-the-c-client-library"></a>C# 클라이언트 라이브러리 사용

1. [MSAL(Microsoft 인증 라이브러리)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview)을 사용하여 기존 [Azure 앱 등록](#create-a-new-app-registration-in-the-azure-portal)을 사용하여 `AccessToken`를 가져옵니다.

1. 토큰을 성공적으로 인증하고 획득한 후 추가 **DefaultRequestHeaders "인증"** 을 **전달자 <access token>** 으로 설정하고 **Ocp-Apim-Subscription-Key** 를 [Customer Insights 환경의 **구독 키**](#get-started-trying-the-customer-insights-apis)로 설정하여 새 'HttpClient'를 구성하거나 기존`HttpClient`를 사용합니다.    
   적절한 경우 **권한 부여** 헤더를 초기화합니다. 예를 들어 토큰이 만료된 경우입니다.

1. 이 `HttpClient`를 `CustomerInsights` 클라이언트의 구성에 전달합니다.

   :::image type="content" source="media/httpclient-sample.png" alt-text="httpclient 샘플":::

1. 클라이언트를 사용하여 '확장 메서드'(예: `GetAllInstancesAsync`)를 호출합니다. 기본 `Microsoft.Rest.HttpOperationResponse`에 대한 액세스를 선호하는 경우 "http 메시지 메서드"(예: `GetAllInstancesWithHttpMessagesAsync`)를 사용합니다.

1. 메서드가 여러 유형(예: `IList<InstanceInfo>` 및 `ApiErrorResult`)을 반환할 수 있으므로 응답은 `object` 유형일 수 있습니다. 반환 유형을 확인하려면 해당 작업의 [API 세부 정보 페이지](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights)에 지정된 응답 유형으로 객체를 안전하게 캐스트할 수 있습니다.    
   요청에 대한 추가 정보가 필요한 경우 **http 메시지 방법** 을 사용하여 원시 응답 객체에 액세스합니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]