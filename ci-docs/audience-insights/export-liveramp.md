---
title: LiveRamp 커넥터
description: LiveRamp에 데이터를 내보내는 방법을 알아봅니다.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 64d781f52e8124fc3e83a7b84f468830c5249cfd
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270166"
---
# <a name="liverampreg-connector-preview"></a>LiveRamp&reg; 커넥터 (미리 보기)

LiveRamp에서 데이터를 활성화하여 디지털, 소셜 및 TV 에코시스템에서 500개 이상의 플랫폼에 연결하십시오. LiveRamp의 데이터를 사용하여 광고 캠페인의 대상을 설정하고, 숨기고, 개인 설정하십시오.

## <a name="prerequisites"></a>필수 구성 요소

- 이 커넥터를 사용하려면 LiveRamp 구독이 필요합니다.
- 구독을 얻으려면 직접 [LiveRamp에 문의](https://liveramp.com/contact/)하십시오. [LiveRamp 온보딩에 대해 자세히 알아보십시오](https://liveramp.com/our-platform/data-onboarding/).

## <a name="connect-to-liveramp"></a>LiveRamp에 연결

1. 대상 그룹 인사이트에서 **데이터** > **내보내기 대상** 으로 이동합니다.

1. **LiveRamp** 타일에서 **설정** 을 선택합니다.

1. **표시 이름** 필드에서 대상에 인식할 수 있는 이름을 지정합니다.

1. SFTP(LiveRamp Secure FTP) 계정에 대한 **사용자 이름** 과 **암호** 를 제공합니다.
이 자격 증명은 LiveRamp 온보딩 자격 증명과 다를 수 있습니다.

1. **확인** 을 선택해 LiveRamp 연결을 테스트합니다.

1. 성공으로 확인한 후에 **동의함** 확인란을 선택하여 **데이터 개인 정보 및 규정 준수** 에 대한 동의를 제공하십시오.

1. **다음** 을 선택해 LiveRamp 커넥터를 설정합니다.

## <a name="configure-the-connector"></a>커넥터 구성

1. **키 식별자 선택** 필드에서 **이메일**, **이름 및 주소** 또는 **전화** 를 선택해 신원 확인을 위해 LiveRamp로 보냅니다.

1. 선택한 키 식별자에 대해 통합 고객 엔터티의 해당 특성을 매핑합니다.

1. **특성 추가** 를 선택해 LiveRamp에 보낼 추가 특성을 매핑합니다.

   > [!TIP]
   > 더 많은 주요 식별자 특성을 LiveRamp로 보내면 더 높은 일치율을 얻을 수 있습니다.

1. LiveRamp로 내보내려는 세그먼트를 선택하십시오.

1. **저장** 을 선택합니다.

> [!div class="mx-imgBorder"]
> ![특성 매핑이 있는 LiveRamp 커넥터](media/export-liveramp-segments.png "특성 매핑이 있는 LiveRamp 커넥터")

## <a name="export-the-data"></a>데이터 내보내기

내보내기를 위한 모든 전제 조건이 완료되면 곧 내보내기가 시작됩니다. 내보내기는 [예약된 새로 고침](system.md#schedule-tab)마다 실행됩니다.
내보내기가 성공적으로 완료되면 LiveRamp 온보딩에 로그인하여 데이터를 활성화하고 배포할 수 있습니다.

## <a name="data-privacy-and-compliance"></a>데이터 프라이버시 및 규정 준수

Dynamics 365 Customer Insights를 사용하여 Liveramp로 데이터를 전송하는 경우 Dynamics 365 Customer Insights규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다. Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 Liveramp가 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다. 자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.
Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.

[!INCLUDE[footer-include](../includes/footer-banner.md)]