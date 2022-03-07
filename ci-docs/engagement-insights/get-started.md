---
title: 참여 인사이트 기능 시작하기
description: 빠르게 시작하기 위한 도움말 리소스의 개요입니다.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 3505c15c4319c8cc8823bcd89d3b8adc944a87dd
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623685"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Dynamics 365 Customer Insights 참여 인사이트 기능 시작하기(공개 프리뷰)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

참여 인사이트 기능을 사용하면 웹 사이트에서 고객 행동을 수집하고 측정할 수 있습니다. 대상 그룹 인사이트 기능과 통합되어 고객 프로필 보고서와 함께 풍부한 실시간 행동 분석을 볼 수 있습니다. 이 문서의 링크는 환경을 빠르게 구성하고 설정하는 데 도움이 됩니다.

## <a name="step-1-review-prerequisites"></a>1단계: 필수 구성 요소 검토

먼저 활성 Microsoft Azure Active Directory(AAD) 사용자 계정이 있어야 합니다. 그런 다음 참여 인사이트 작업 영역을 설정하기 전에 다음 문서를 읽어보세요.

- Microsoft의 [서비스 약관](terms-of-service.md)을 검토하고 동의합니다.  
- [쿠키 및 사용자 동의 관리](user-consent-storage.md) 문서를 읽어보세요. 그런 다음 사용자 동의 알림을 업데이트해야 하는지 여부를 평가합니다. 이전에 "필수적이 아닌" 쿠키가 없었던 경우 사이트 정책을 업데이트해야 할 수 있습니다.
- 주요 용어 및 개념에 대한 간략한 소개는 [용어집](glossary.md)을 검토하세요.

## <a name="step-2-explore-engagement-insights"></a>2단계: 참여 인사이트 탐색

참여 인사이트를 처음 방문하면 설정을 구성하고, 정책을 검토하고, 기능을 탐색할 수 있습니다.

1. Microsoft AAD 사용자(학교 또는 직장) 계정을 사용하여 [참여 인사이트 기능 포털](https://home.ci.ai.dynamics.com/app/engagement-insights)에 로그인합니다.

1. 지역을 선택하고 이메일 업데이트 및 제안을 수신하도록 선택하려면 확인란을 선택합니다.

1. 참여 인사이트(프리뷰) **이용 약관** 및 **개인정보처리방침** 을 검토한 다음 **데모 살펴보기** 를 선택하여 이러한 설정을 수락합니다.

1. 샘플 데이터 집합을 사용하여 제품을 탐색합니다.

##  <a name="step-3-set-up-a-workspace-and-create-reports"></a>3단계: 작업 영역 설정 및 보고서 만들기

작업 영역은 실시간으로 사용자 활동을 보고 보고서를 저장 및 관리할 수 있는 곳입니다. 웹 사이트에 코드를 추가하여 *이벤트*, 사용자로부터 들어오는 활동 데이터 수집을 시작하세요.

1. [작업 영역을 만들고](create-workspace.md) 구성원을 추가합니다.

1. [웹 사이트](instrument-website.md) 또는 [모바일 앱](developer-resources.md#capture-events-from-mobile-apps)에 코드를 추가하여 작업 영역에 도달하는 사용자 활동을 확인합니다.

1. 브라우저, 장치, 운영 체제, 위치 및 언어별로 활성 사용자를 보여주는 [실시간 보고서](view-reports.md)를 봅니다. [사용자 지정 보고서](custom-reports.md)를 만들어 자신만의 시각화를 만들 수도 있습니다.

1. 신규 및 재방문 사용자를 기준으로 방문자를 정렬하는 [차원](dimensions.md), 사용자 행동을 더 잘 이해하는 데 도움이 되는 [메트릭](metrics.md), 특성 또는 웹사이트 상호작용을 기반으로 방문자의 하위 집합을 식별하는 [세그먼트](segments.md)를 만듭니다.
    
## <a name="step-4-export-data-to-other-channels"></a>4단계: 다른 채널로 데이터 내보내기

웹 분석 데이터의 *개선된 이벤트*(가상 보기)를 작성할 수 있습니다. 그런 다음 데이터를 필터링하고 Azure Data Lake Storage로 내보냅니다. 내보낸 데이터를 데이터 원본으로 수집할 수 있습니다.

1. [내보내기를 위한 개선된 이벤트를 만들고 내보냅니다](refined-events.md).

1. Azure Data Lake Storage로 [데이터를 내보냅니다](export-events.md).

1. [대상 그룹 인사이트와 참여 인사이트 간의 링크 만들기](integrate-audience-insights-engagement-insights.md)를 수행하여 두 기능 간에 데이터를 공유합니다.

1. **처음부터 알아보기** 기능으로 이전에 [인증된 사용자의 웹 이벤트를 인식](unknown-to-known.md)합니다.

1. [개인 정보가 포함된 이벤트 데이터를 삭제하고 내보내](delete-export-personal-data.md)는 방법을 알아봅니다.

## <a name="step-5-create-and-manage-funnel-reports"></a>5단계: 유입 경로 보고서 만들기 및 관리

유입 경로 보고서는 웹 사이트 또는 모바일 앱을 통해 고객 여정 중에 발생하는 단계에 대한 정보를 수집합니다. 기본 프로필 보고서 및 사용자 지정 보고서를 만드는 것 외에도 유입 경로 보고서를 만들어 고객이 구매하기 전에 취하는 경로를 식별할 수 있습니다. 

1. 결정을 알리고 최적화 및 프로세스 개선 영역을 식별하는 [유입 경로 보고서를 만듭니다](funnel-reports.md).

1. 참여 인사이트 [Android SDK](get-started-android.md) 또는 [iOS SDK](get-started-ios.md)를 사용하여 모바일 앱을 계측한 후 교차 채널 유입 경로 보고서를 만듭니다.

1. [유입 경로 인사이트](funnel-reports.md#funnel-insights)를 사용하여 유입 경로 보고서에서 단계에 대한 고객 행동에 대한 더 깊은 인사이트를 얻으세요.
 
## <a name="step-6-stay-connected"></a>6단계: 연결 유지

귀하의 적극적인 참여에 감사드리며 향후 릴리스를 개발할 때 모든 관련 피드백을 고려하겠습니다. 다음 채널 중 하나를 통해 피드백을 공유하고 문제를 보고하세요.
- [커뮤니티](https://go.microsoft.com/fwlink/?linkid=2141648)
- [피드백 제공](https://go.microsoft.com/fwlink/?linkid=2143222)
- [지원 요청](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
