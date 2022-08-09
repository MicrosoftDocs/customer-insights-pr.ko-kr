---
title: LiveRamp로 세그먼트 내보내기(프리뷰)
description: 연결을 구성하고 LiveRamp로 내보내는 방법을 알아봅니다.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196724"
---
# <a name="export-segments-to-liverampreg-preview"></a>LiveRamp로 세그먼트 내보내기&reg;(프리뷰)

LiveRamp에서 데이터를 활성화하여 디지털, 소셜 및 TV에서 500개 이상의 플랫폼과 연결하십시오. LiveRamp의 데이터를 사용하여 광고 캠페인의 대상을 설정하고, 숨기고, 개인 설정하십시오.

## <a name="prerequisites"></a>전제 조건

- LiveRamp를 구독하여 이 커넥터를 사용합니다. 구독을 얻으려면 직접 [LiveRamp에 문의](https://liveramp.com/contact/)하십시오. [LiveRamp 온보딩에 대해 자세히 알아보십시오](https://liveramp.com/our-platform/data-onboarding/).

## <a name="known-limitations"></a>알려진 제한 사항

- LiveRamp 내보내기는 SFTP 내보내기 방식을 사용합니다. 방화벽 뒤에 있는 SFTP 대상은 현재 지원되지 않습니다.
- 인증을 위해 SSH 키를 사용하는 경우 [개인 키 생성](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example)을 PEM 또는 SSH.COM 형식으로 진행하는지 확인하세요. Putty를 사용하는 경우 내보내기를 통해 개인 키를 오픈 SSH로 변환합니다. 다음 개인 키 형식이 지원됩니다.
  - OpenSSL PEM 및 SSH.COM 형식의 RSA
  - OpenSSL PEM 및 SSH.COM 형식의 DSA
  - OpenSSL PEM 형식의 ECDSA 256/384/521
  - OpenSSH 키 형식의 ED25519 및 RSA
- 내보내기 런타임은 시스템 성능에 따라 다릅니다. 서버의 최소 구성으로 2개의 CPU 코어와 1Gb의 메모리를 권장합니다.
- 2개의 CPU 코어와 1Gb 메모리의 권장 최소 구성을 사용하면 최대 1억 개의 고객 프로필이 있는 엔터티를 내보내는 데 90분이 걸릴 수 있습니다.
- LiveRamp로 내보낼 수 있는 프로필이나 데이터의 실제 개수는 LiveRamp와 맺은 구독 조건에 따라 다릅니다.

## <a name="set-up-connection-to-liveramp"></a>LiveRamp 연결 설정

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 를 선택하고 **LiveRamp** 를 선택합니다.

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 이 연결을 사용할 수 있는 사용자를 선택합니다. 기본적으로 관리자만 해당합니다. 자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.

1. SSH 또는 연결에 필요한 사용자 이름/비밀번호를 통해 인증할지 여부를 선택하고 필요한 세부 정보를 제공합니다.

1. **확인** 을 선택해 LiveRamp 연결을 테스트합니다.

1. 확인이 완료되면 [데이터 개인 정보 보호 및 규정 준수](connections.md#data-privacy-and-compliance)를 검토하고 **동의함** 을 선택합니다.

1. 연결을 완료하려면 **저장** 을 선택합니다.

## <a name="configure-an-export"></a>내보내기 구성

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **데이터** > **내보내기** 로 이동합니다.

1. **내보내기 추가** 를 선택합니다.

1. **내보내기 연결** 필드의 LiveRamp 섹션에서 연결을 선택합니다. 사용 가능한 연결이 없으면 관리자에게 문의하십시오.

1. 내보낼 엔터티의 이름을 입력합니다.

1. **데이터 연결** 필드에서 **이메일**, **이름 및 주소** 또는 **전화번호** 를 선택해 ID 확인을 위해 LiveRamp로 전송합니다.

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="특성 매핑이 있는 LiveRamp 커넥터.":::

1. 선택한 키 식별자의 *고객* 엔터티의 해당 특성을 매핑합니다.

1. **특성 추가** 를 선택하여 LiveRamp에 보낼 더 많은 특성을 매핑합니다.

   > [!TIP]
   > 더 많은 주요 식별자 특성을 LiveRamp로 보내면 더 높은 일치율을 얻을 수 있습니다.

1. 내보낼 세그먼트를 선택합니다.

1. **저장** 을 선택합니다.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
