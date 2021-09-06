---
title: LiveRamp 커넥터
description: 연결을 구성하고 LiveRamp로 내보내는 방법을 알아봅니다.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7940db3efacad62ba16099849b3e3ca00d2a5cc1ed31e15a34209c0797e6ae13
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035653"
---
# <a name="export-segments-to-liverampreg-preview"></a>LiveRamp로 세그먼트 내보내기&reg;(프리뷰)

LiveRamp에서 데이터를 활성화하여 디지털, 소셜 및 TV에서 500개 이상의 플랫폼과 연결하십시오. LiveRamp의 데이터를 사용하여 광고 캠페인의 대상을 설정하고, 숨기고, 개인 설정하십시오.

## <a name="prerequisites-for-a-connection"></a>연결을 위한 전제 조건

- 이 커넥터를 사용하려면 LiveRamp 구독이 필요합니다.
- 구독을 얻으려면 직접 [LiveRamp에 문의](https://liveramp.com/contact/)하십시오. [LiveRamp 온보딩에 대해 자세히 알아보십시오](https://liveramp.com/our-platform/data-onboarding/).

## <a name="set-up-connection-to-liveramp"></a>LiveRamp 연결 설정

1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 와 **LiveRamp** 를 선택하여 연결을 구성합니다.

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 이 연결을 사용할 수 있는 사용자를 선택합니다. 아무 조치도 취하지 않으면 기본값은 관리자입니다. 자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.

1. SFTP(LiveRamp Secure FTP) 계정에 대한 **사용자 이름** 과 **암호** 를 제공합니다.
이 자격 증명은 LiveRamp 온보딩 자격 증명과 다를 수 있습니다.

1. **확인** 을 선택해 LiveRamp 연결을 테스트합니다.

1. 성공으로 확인한 후에 **동의함** 확인란을 선택하여 **데이터 개인 정보 및 규정 준수** 에 대한 동의를 제공하십시오.

1. 연결을 완료하려면 **저장** 을 선택합니다.

## <a name="configure-an-export"></a>내보내기 구성

이 유형의 연결에 대한 액세스 권한이 있는 경우 이 내보내기를 구성할 수 있습니다. 자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.

1. **데이터** > **내보내기** 로 이동합니다.

1. **대상 추가** 를 선택하여 새 내보내기를 만듭니다.

1. **내보내기 연결** 필드의 LiveRamp 섹션에서 연결을 선택합니다. 이 섹션 이름이 표시되지 않으면 사용 가능한 이 유형의 연결이 없는 것입니다.

1. **키 식별자 선택** 필드에서 **이메일**, **이름 및 주소** 또는 **전화** 를 선택해 신원 확인을 위해 LiveRamp로 보냅니다.
   > [!div class="mx-imgBorder"]
   > ![특성 매핑이 있는 LiveRamp 커넥터.](media/export-liveramp-segments.png "특성 매핑이 있는 LiveRamp 커넥터")

1. 선택한 키 식별자에 대해 통합 고객 엔터티의 해당 특성을 매핑합니다.

1. **특성 추가** 를 선택하여 LiveRamp에 보낼 더 많은 특성을 매핑합니다.

   > [!TIP]
   > 더 많은 주요 식별자 특성을 LiveRamp로 보내면 더 높은 일치율을 얻을 수 있습니다.

1. LiveRamp로 내보내려는 세그먼트를 선택하십시오.

1. **저장** 을 선택합니다.

내보내기를 저장해도 내보내기가 즉시 실행되지는 않습니다.

내보내기는 모든 [예약된 새로 고침](system.md#schedule-tab)에 따라 실행됩니다. [주문형으로 데이터를 내보낼](export-destinations.md#run-exports-on-demand)수도 있습니다. 


## <a name="data-privacy-and-compliance"></a>데이터 프라이버시 및 규정 준수

Dynamics 365 Customer Insights를 사용하여 Liveramp로 데이터를 전송하는 경우 Dynamics 365 Customer Insights규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다. Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 Liveramp가 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다. 자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.
Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
