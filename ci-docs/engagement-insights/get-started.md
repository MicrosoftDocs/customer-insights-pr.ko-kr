---
title: 참여 인사이트 기능 시작하기
description: 빠르게 시작하기 위한 도움말 리소스의 개요입니다.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 12/21/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5ee1567cea834670a16aaa3253912b7957ce26b3
ms.sourcegitcommit: 86739a3f238162fc96837270b5d184e648fab15c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2021
ms.locfileid: "7405366"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Dynamics 365 Customer Insights 참여 인사이트 기능 시작하기(공개 프리뷰)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

참여 인사이트 기능을 사용하면 웹 사이트에서 고객 행동을 수집하고 측정할 수 있습니다. 대상 그룹 인사이트 기능과 통합되어 고객 프로필 보고서와 함께 풍부한 실시간 행동 분석을 볼 수 있습니다. 이 문서의 링크는 환경을 빠르게 구성하고 설정하는 데 도움이 됩니다.

## <a name="step-1-review-prerequisites"></a>1단계: 필수 구성 요소 검토

먼저 활성 Microsoft Azure Active Directory 사용자 계정이 있어야 합니다. 그런 다음 참여 인사이트 작업 영역을 설정하기 전에 다음 문서를 읽어보세요.

- Microsoft의 [서비스 약관](terms-of-service.md)을 검토하고 동의합니다.  
- [쿠키 및 사용자 동의 관리](user-consent-storage.md) 문서를 읽어보세요. 이 문서를 검토한 후 사용자 동의 알림을 업데이트해야 하는지 평가합니다. 이전에 "필수적이 아닌" 쿠키가 없었던 경우 사이트 정책을 업데이트해야 할 수 있습니다.
- 주요 용어 및 개념에 대한 간략한 소개는 [용어집](glossary.md)을 검토하세요.

## <a name="step-2-explore-engagement-insights"></a>2단계: 참여 인사이트 탐색

참여 인사이트를 처음 방문하면 설정을 구성하고 정책을 검토하고 제품을 탐색할 수 있습니다.

1. Microsoft Azure Active Directory 사용자 계정을 사용하여 [참여 인사이트 기능](https://pi.dynamics.com) 포털에 로그인합니다. (학교 또는 직장 계정일 수 있습니다.)

1. 지역을 선택하고 확인란을 사용하여 이메일을 통해 업데이트 및 제안을 수신할 것인지 여부를 표시하세요.

1. **참여 인사이트(프리뷰) 사용 약관** 및 **개인정보처리방침** 을 검토한 다음 **데모 탐색** 을 선택하여 동의합니다.

1. 샘플 데이터 집합을 사용하여 제품을 탐색합니다.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>3단계: 작업 영역을 설정하고 웹 사이트에 코드 추가

작업 영역은 사용자 활동을 실시간으로 보고 보고서를 저장 및 관리할 수 있는 곳입니다. 웹 사이트에 코드를 추가하여 *이벤트*, 사용자로부터 들어오는 활동 데이터 수집을 시작하세요.

1. [작업 영역을 만들고](create-workspace.md) 구성원을 추가합니다.

1. [웹 사이트](instrument-website.md) 또는 [모바일 앱](developer-resources.md#capture-events-from-mobile-apps)에 코드를 추가하여 작업 영역에 도달하는 사용자 활동을 확인합니다.

1. 브라우저, 디바이스, 운영 체제, 위치 및 언어별로 활성 사용자를 보여주는 [실시간 보고서](view-reports.md)를 봅니다. [사용자 지정 보고서](custom-reports.md)를 만들어 자신만의 시각화를 만들 수도 있습니다.
    
## <a name="step-4-export-data-to-other-channels"></a>4단계: 다른 채널로 데이터 내보내기

웹 분석 데이터의 *개선된 이벤트*(가상 보기)를 작성할 수 있습니다. 그런 다음 데이터를 필터링하고 Azure Data Lake Storage로 내보냅니다. 내보낸 데이터를 데이터 원본으로 수집할 수 있습니다. 자세한 정보는 [대상 그룹 인사이트와 참여 인사이트 사이에 링크 만들기](integrate-audience-insights-engagement-insights.md)를 참조하십시오.

1. [내보내기를 위한 개선된 이벤트를 만들고 내보냅니다](refined-events.md).

1. Data Lake Storage로 [데이터를 내보냅니다](export-events.md).

1. [개인 정보가 포함된 이벤트 데이터를 삭제하고 내보내](delete-export-personal-data.md)는 방법을 알아봅니다.
 
## <a name="step-5-stay-connected"></a>5단계: 연결 유지

적극적인 참여에 감사 드리며 향후 릴리스를 개발할 때 모든 관련 피드백을 고려할 계획입니다. 다음 채널 중 하나를 통해 피드백을 공유하고 문제를 보고하세요.
- [커뮤니티](https://go.microsoft.com/fwlink/?linkid=2141648)
- [피드백 제공](https://go.microsoft.com/fwlink/?linkid=2143222)
- [지원 요청](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
