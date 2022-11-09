---
title: AdRoll로 세그먼트 내보내기(프리뷰)
description: 연결을 구성하고 AdRoll로 내보내는 방법을 알아봅니다.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 81adad4caf2d4c6f792bf920b29fc7c67eef42b0
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724720"
---
# <a name="export-segments-to-adroll-preview"></a>AdRoll로 세그먼트 내보내기(프리뷰)

통합 고객 프로필의 세그먼트를 AdRoll로 내보내고 광고에 사용합니다.

## <a name="prerequisites"></a>전제 조건

- [AdRoll 계정](https://www.adroll.com/) 및 해당 관리자 자격 증명입니다.
- [AdRoll 광고주 ID](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles)입니다.
- Customer Insights에 [세그먼트를 구성했습니다](segments.md).
- 내보낸 세그먼트의 통합 고객 프로필에는 이메일 주소를 나타내는 필드가 포함됩니다.

## <a name="known-limitations"></a>알려진 제한 사항

- BYOS(Bring Your Own Storage)와 결합된 개인 링크는 지원되지 않습니다.
- 최대 25만 개의 고객 프로필을 AdRoll로 내보낼 때마다 최대 10분이 소요될 수 있습니다. AdRoll로 내보낼 수 있는 고객 프로필의 개수는 AdRoll과의 계약에 따라 다릅니다.
- 세그먼트만 해당됩니다. 세그먼트에는 100개 이상의 고객 프로필이 포함되어야 합니다.

## <a name="set-up-connection-to-adroll"></a>AdRoll에 연결을 설정합니다.

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 를 선택하고 **AdRoll** 을 선택합니다.

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 이 연결을 사용할 수 있는 사용자를 선택합니다. 기본적으로 관리자만 해당합니다. 자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.

1. [데이터 개인 정보 보호 및 규정 준수](connections.md#data-privacy-and-compliance)를 검토하고 **동의함** 을 선택합니다.

1. **연결** 을 선택하여 해당 연결을 초기화합니다.

1. **AdRoll로 인증** 을 선택하고 AdRoll 관리자 자격 인증을 제공합니다.

1. **내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.

1. 연결을 완료하려면 **저장** 을 선택합니다.

## <a name="configure-an-export"></a>내보내기 구성

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **데이터** > **내보내기** 로 이동합니다.

1. **내보내기 추가** 를 선택합니다.

1. **내보내기 연결** 필드의 AdRoll 섹션에서 연결을 선택합니다. 사용 가능한 연결이 없으면 관리자에게 문의하십시오.

1. 내보낼 엔터티의 이름을 입력합니다.

1. **AdRoll 광고주 ID** 를 입력합니다.

1. **데이터 일치** 섹션의 **이메일** 필드에서 고객의 이메일 주소를 나타내는 필드를 선택합니다.

1. 내보낼 세그먼트를 선택합니다.

1. **저장** 을 선택합니다.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
