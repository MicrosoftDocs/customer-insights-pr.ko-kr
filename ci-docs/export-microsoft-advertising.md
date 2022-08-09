---
title: Microsoft Advertising으로 세그먼트 내보내기(프리뷰)
description: 연결을 구성하고 Microsoft Advertising으로 내보내는 방법을 알아봅니다.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196540"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Microsoft Advertising으로 세그먼트 내보내기(프리뷰)

Customer Insights 세그먼트를 Microsoft Advertising으로 내보내 Customer Match 대상 그룹을 만듭니다. 이러한 대상 그룹을 광고 캠페인에 사용하십시오.

## <a name="prerequisites"></a>전제 조건

- [Microsoft Advertising 계정](https://ads.microsoft.com/) 및 해당 관리자 자격 증명입니다.
- Microsoft Advertising 고객 ID 및 계정 ID입니다. Microsoft Advertising에 로그인하여 URL 매개 변수에서 고객 ID(`cid`) 및 계정 ID(`aid`)를 찾아 확인합니다.
- Customer Match에 관한 이용 약관에 동의했습니다.
- Customer Insights에 [세그먼트를 구성했습니다](segments.md).
- 내보낸 세그먼트의 통합 고객 프로필에는 이메일 주소를 나타내는 필드가 포함됩니다.

## <a name="known-limitations"></a>알려진 제한 사항

- 최대 50만 개의 고객 프로필을 Microsoft Advertising으로 내보낼 때마다 최대 10분이 소요될 수 있습니다.
- 세그먼트만 해당됩니다.

## <a name="set-up-connection-to-microsoft-advertising"></a>Microsoft Advertising에 대한 연결 설정

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 를 선택하고 **Microsoft Advertising** 을 선택합니다.

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 이 연결을 사용할 수 있는 사용자를 선택합니다. 기본값은 관리자입니다. 자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.

1. **Microsoft Advertising 고객 ID** 를 입력합니다.

1. [데이터 개인 정보 보호 및 규정 준수](connections.md#data-privacy-and-compliance)를 검토하고 **동의함** 을 선택합니다.

1. **연결** 을 선택하여 해당 연결을 초기화합니다.

1. **Microsoft Advertising으로 인증** 을 선택하고 Microsoft Advertising에 대한 관리자 자격 증명을 제공합니다.

1. **내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.

1. 연결을 완료하려면 **저장** 을 선택합니다.

## <a name="configure-an-export"></a>내보내기 구성

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **데이터** > **내보내기** 로 이동합니다.

1. **내보내기 추가** 를 선택합니다.

1. **내보내기 연결** 필드의 Microsoft Advertising 섹션에서 연결을 선택합니다. 사용 가능한 연결이 없으면 관리자에게 문의하십시오.

1. 내보낼 엔터티의 이름을 입력합니다.

1. 내보낼 세그먼트를 선택합니다. Microsoft Advertising의 Customer Match 대상 그룹은 내보내기 위해 선택한 세그먼트의 이름으로 자동 생성됩니다. 각 세그먼트는 별도의 Customer Match 대상 그룹을 생성합니다.

1. **Microsoft Advertising 고객 ID 및 계정 ID** 를 입력합니다.

1. **데이터 일치** 섹션의 **이메일** 필드에서 고객의 이메일 주소가 있는 필드를 선택합니다.

1. **저장** 을 선택합니다.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
