---
title: Customer Insights API에 대한 작업
description: API를 사용하고 제한 사항을 이해합니다.
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387348"
---
# <a name="work-with-customer-insights-apis"></a>Customer Insights API에 대한 작업

Dynamics 365 Customer Insights는 Customer Insights의 데이터를 기반으로 자체 애플리케이션을 빌드하는 API를 제공합니다.

> [!IMPORTANT]
> 이러한 API에 대한 자세한 내용은 [Customer Insights API 참조](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights)에 나열되어 있습니다. 여기에는 작업, 매개 변수 및 응답에 대한 추가 정보가 포함됩니다.

Customer Insights API를 사용해 보고 Azure 앱 등록을 만들고 클라이언트 라이브러리를 시작하세요.

## <a name="get-started-trying-the-customer-insights-apis"></a>Customer Insights API로 시작하기

Customer Insights API를 활성화하고 사용해 보십시오. Customer Insights 관리자는 Customer Insights에 대한 API 액세스를 활성화해야 합니다. 액세스가 활성화되면 모든 사용자가 구독 키로 API를 사용할 수 있습니다.

1. Customer Insights에 [로그인](https://home.ci.ai.dynamics.com)합니다. 아직 구독하지 않은 경우 [Customer Insights 평가판에 등록](https://aka.ms/tryci)하세요.

1. **관리자** > **보안** 으로 이동한 다음 **API** 탭을 선택합니다.

1. 환경에 대한 API 액세스 권한이 설정되지 않은 경우 **사용 설정** 을 선택합니다.

   API를 사용하면 API 요청에 사용되는 인스턴스의 기본 및 보조 구독 키가 생성됩니다. 키를 다시 생성하려면 **API** 탭에서 **기본 재생성** 또는 **보조 재생성** 을 선택합니다.

1. [**API 탐색**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances)을 선택하여 API를 사용해봅니다.

1. API 작업을 검색하여 선택하고 **사용해보기** 을 선택합니다.

   :::image type="content" source="media/try-api.png" alt-text="API를 테스트하는 방법.":::

1. 측면 창에서 **권한 부여** 드롭다운 메뉴의 값을 **암시적** 으로 설정합니다. `Authorization` 헤더는 전달자 토큰과 함께 추가됩니다. 구독 키는 자동으로 채워집니다.
  
1. 필요한 경우 모든 필수 쿼리 매개 변수를 추가합니다.

1. 측면 창 하단으로 스크롤하고 **보내기** 를 선택합니다.

   HTTP 응답이 창 하단에 표시됩니다.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Azure Portal에 새 앱 등록을 만듭니다.

위임된 권한을 사용하여 Azure 애플리케이션에서 Customer Insights API를 사용하려면 새 [앱 등록](/graph/auth-register-app-v2)을 만듭니다.

1. [시작 섹션](#get-started-trying-the-customer-insights-apis)을 완료합니다.

1. Customer Insights 데이터에 액세스할 수 있는 계정으로 [Azure Portal](https://portal.azure.com)에 로그인합니다.

1. **앱 등록** 을 검색하여 선택합니다.

1. **새 등록** 을 선택하고 애플리케이션 이름을 제공하고 계정 유형을 선택합니다.

   원하는 경우 리디렉션 URL을 추가합니다. http://localhost는 로컬 컴퓨터에서 애플리케이션을 개발하는 데 충분합니다.

1. **등록** 을 선택합니다.

1. 새 앱 등록에서 **API 권한** 으로 이동합니다.

1. **권한 추가** 를 선택하고 측면 창에서 **Customer Insights용 Dynamics 365 AI** 를 선택합니다.

1. **권한 유형** 에서 **위임된 권한** 을 선택한 후 **user_impersonation** 권한을 선택합니다.

1. **권한 추가** 를 선택합니다.

1. **관리자 동의 허용...** 을 선택하여 앱 등록을 완료합니다.

1. 사용자 로그인없이 API에 액세스하려면 [서버 간 애플리케이션 권한](#server-to-server-application-permissions)으로 이동하십시오.

[MSAL(Microsoft 인증 라이브러리)](/azure/active-directory/develop/msal-overview)에 이 앱 등록에 대한 애플리케이션/클라이언트 ID를 사용하여 API에 대한 요청과 함께 보낼 전달자 토큰을 얻을 수 있습니다.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

클라이언트 라이브러리에서 API를 사용하는 방법에 대한 자세한 내용은 [Customer Insights 클라이언트 라이브러리](#customer-insights-client-libraries)를 참고하세요.

### <a name="server-to-server-application-permissions"></a>서버 간 애플리케이션 권한

사용자 상호 작용이 필요하지 않고 서버에서 실행할 수 있는 앱 등록을 만듭니다.

1. Azure Portal의 앱 등록에서 **API 권한** 으로 이동합니다.

1. **권한 추가** 를 선택합니다.

1. **내 조직에서 사용하는 API** 탭을 선택하고 목록에서 **Customer Insights용 Dynamics 365 AI** 를 선택합니다.

1. **권한 유형** 에서 **애플리케이션 권한** 을 선택한 후 **CustomerInsights.Api.All** 권한을 선택합니다.

1. **권한 추가** 를 선택합니다.

1. 앱 등록을 위한 **API 권한** 으로 돌아갑니다.

1. **관리자 동의 허용...** 을 선택하여 앱 등록을 완료합니다.

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Customer Insights에서 사용자로 앱 등록 이름을 추가합니다.

   1. Customer Insights를 열고 **관리자** > **보안** 으로 이동하여 **사용자 추가** 를 선택합니다.

   1. 앱 등록 이름을 검색하고 검색 결과에서 선택한 다음 **저장** 을 선택합니다.

## <a name="sample-queries"></a>샘플 쿼리

API와 함께 작동하는 OData 샘플 쿼리의 짧은 목록의 경우 [OData 쿼리 예시](odata-examples.md)를 참조하십시오.

## <a name="customer-insights-client-libraries"></a>Customer Insights 클라이언트 라이브러리

Customer Insights API에 사용할 수 있는 클라이언트 라이브러리를 사용하여 시작하십시오. 모든 라이브러리 소스 코드 및 샘플 애플리케이션은 [Customer Insights GitHub 페이지](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries)에서 확인할 수 있습니다.

### <a name="c-nuget"></a>C# NuGet

NuGet.org의 C# 클라이언트 라이브러리를 사용합니다. 현재 패키지는 netstandard2.0 및 netcoreapp2.0 프레임워크를 대상으로 합니다. NuGet 패키지에 대한 자세한 내용은, [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/)를 참조하십시오.

#### <a name="add-the-c-client-library-to-a-c-project"></a>C# 프로젝트에 C# 클라이언트 라이브러리 추가

1. Visual Studio에서 프로젝트의 **NuGet 패키지 관리자** 를 엽니다.

1. **Microsoft.Dynamics.CustomerInsights.Api** 를 검색합니다.

1. **설치** 를 선택하여 프로젝트에 패키지를 추가합니다.

   또는 다음 명령을 **NuGet 패키지 관리자 콘솔** 에 실행합니다. `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>C# 클라이언트 라이브러리 사용

1. [MSAL(Microsoft 인증 라이브러리)](/azure/active-directory/develop/msal-overview)을 사용하여 기존 [Azure 앱 등록](#create-a-new-app-registration-in-the-azure-portal)을 사용하여 `AccessToken`를 가져옵니다.

1. 토큰을 성공적으로 인증하고 획득한 후에는 **DefaultRequestHeaders "승인"** 을 **무기명 "액세스 토큰"** 으로 설정하고 **Ocp-Apim-Subscription-Key** 를 [Customer Insights 환경의 **구독 키**](#get-started-trying-the-customer-insights-apis)로 설정하여 새로 만들기 또는 기존 `HttpClient`를 사용합니다.   

   적절한 경우 **권한 부여** 헤더를 초기화합니다. 예를 들어 토큰이 만료된 경우입니다.

1. 이 `HttpClient`를 `CustomerInsights` 클라이언트의 구성에 전달합니다.

   <!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. 클라이언트를 사용하여 '확장 메서드'(예: `GetAllInstancesAsync`)를 호출합니다. 기본 `Microsoft.Rest.HttpOperationResponse`에 대한 액세스를 선호하는 경우 "http 메시지 메서드"(예: `GetAllInstancesWithHttpMessagesAsync`)를 사용합니다.

1. 메서드가 여러 유형(예: `IList<InstanceInfo>` 및 `ApiErrorResult`)을 반환할 수 있으므로 응답은 `object` 유형일 가능성이 높습니다. 반환 유형을 확인하려면 해당 작업에 대해 [API 세부정보 페이지](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights)에 지정된 응답 유형의 개체를 사용합니다.

   요청에 대한 추가 정보가 필요한 경우 **http 메시지 방법** 을 사용하여 원시 응답 객체에 액세스합니다.

### <a name="nodejs-package"></a>NodeJS 패키지

NPM을 통해 제공되는 NodeJS 클라이언트 라이브러리 사용: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Python 패키지

PyPi를 통해 제공되는 Python 클라이언트 라이브러리 사용: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
