---
title: Campaign Monitor로 세그먼트 내보내기(프리뷰)
description: 연결을 구성하고 Campaign Monitor로 내보내는 방법을 알아봅니다.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 82303c7bcb269ee68419c9639ee743e13451f273
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724692"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Campaign Monitor로 세그먼트 내보내기(프리뷰)

통합 고객 프로필의 세그먼트를 Campaign Monitor로 내보내고 마케팅 활동에 사용합니다.

## <a name="prerequisites"></a>전제 조건

- [Campaign Monitor 계정](https://www.campaignmonitor.com/) 및 해당 관리자 자격 증명입니다.
- [Campaign Monitor 목록 ID](https://www.campaignmonitor.com/api/getting-started/#your-list-id)입니다.
- Campaign Monitor의 **계정 설정** 에서 [API 키를 생성](https://www.campaignmonitor.com/api/getting-started/)하여 API 목록 ID를 획득합니다.
- Customer Insights에 [세그먼트를 구성했습니다](segments.md).
- 내보낸 세그먼트의 통합 고객 프로필에는 이메일 주소를 나타내는 필드가 포함됩니다.

## <a name="known-limitations"></a>알려진 제한 사항

- BYOS(Bring Your Own Storage)와 결합된 개인 링크는 지원되지 않습니다.
- 최대 100만 개의 고객 프로필을 Campaign Monitor로 내보낼 때마다 최대 20분이 소요될 수 있습니다. Campaign Monitor로 내보낼 수 있는 고객 프로필의 개수는 Campaign Monitor와 체결한 계약에 따라 다릅니다.
- 세그먼트만 해당됩니다.

## <a name="set-up-connection-to-campaign-monitor"></a>Campaign Monitor 연결 설정

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 를 선택하고 **Campaign Monitor** 를 선택합니다.

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 이 연결을 사용할 수 있는 사용자를 선택합니다. 기본적으로 관리자만 해당합니다. 자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.

1. [데이터 개인 정보 보호 및 규정 준수](connections.md#data-privacy-and-compliance)를 검토하고 **동의함** 을 선택합니다.

1. **연결** 을 선택하여 Campaign Monitor에 대한 연결을 초기화합니다.

1. **Campaign Monitor로 인증** 을 선택하고 Campaign Monitor에 대한 관리자 자격 증명을 제공합니다.

1. **내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.

1. 연결을 완료하려면 **저장** 을 선택합니다.

## <a name="configure-an-export"></a>내보내기 구성

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **데이터** > **내보내기** 로 이동합니다.

1. **내보내기 추가** 를 선택하여 새 내보내기를 만듭니다.

1. **내보내기 연결** 필드의 Campaign Monitor 섹션에서 연결을 선택합니다. 사용 가능한 연결이 없으면 관리자에게 문의하십시오.

1. 내보낼 엔터티의 이름을 입력합니다.

1. **Campaign Monitor 목록 ID** 를 입력합니다.

1. **데이터 일치** 섹션의 **이메일** 필드에서 고객의 이메일 주소를 나타내는 필드를 선택합니다. Campaign Monitor로 세그먼트를 내보내야 합니다.

1. 내보낼 세그먼트를 선택합니다.

1. **저장** 을 선택합니다.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
