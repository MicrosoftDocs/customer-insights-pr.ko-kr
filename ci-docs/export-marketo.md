---
title: Marketo로 세그먼트 내보내기(프리뷰)
description: 연결을 구성하고 Marketo로 내보내는 방법을 알아봅니다.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cba40b74b86a40fc41db856760c9361b755a8864
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724948"
---
# <a name="export-segments-to-marketo-preview"></a>Marketo로 세그먼트 내보내기(프리뷰)

통합 고객 프로필의 세그먼트를 내보내 캠페인을 생성하고 이메일 마케팅을 제공하며 Marketo에서 특정 고객 그룹을 사용합니다.

## <a name="prerequisites"></a>전제 조건

- [Marketo 계정](https://login.marketo.com/) 및 해당 관리자 자격 증명입니다.
- [Marketo 클라이언트 ID, 클라이언트 암호 및 REST 엔드포인트 호스트 이름](https://developers.marketo.com/rest-api/authentication/)입니다.
- [Marketo에 기존 목록](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)과 해당 ID가 있습니다.
- [구성된 세그먼트](segments.md)입니다.
- 내보낸 세그먼트의 통합 고객 프로필에는 이메일 주소를 나타내는 필드가 포함됩니다.

## <a name="known-limitations"></a>알려진 제한 사항

- BYOS(Bring Your Own Storage)와 결합된 개인 링크는 지원되지 않습니다.
- 최대 100만 개의 고객 프로필을 Marketo로 내보낼 때마다 최대 3시간이 소요될 수 있습니다. Marketo로 내보낼 수 있는 고객 프로필의 개수는 Marketo와 체결한 계약에 따라 다릅니다.
- 세그먼트만 해당됩니다.

## <a name="set-up-connection-to-marketo"></a>Marketo에 연결을 설정합니다.

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 를 선택하고 **Marketo** 를 선택합니다.

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 이 연결을 사용할 수 있는 사용자를 선택합니다. 기본적으로 관리자만 해당합니다. 자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.

1. **Marketo 클라이언트 ID, 클라이언트 암호 및 REST 엔드포인트 호스트 이름** 을 입력합니다. REST 끝점 호스트 이름은 https://가 없는 호스트 이름입니다. 예: xyz-abc-123.mktorest.com.

1. [데이터 개인 정보 보호 및 규정 준수](connections.md#data-privacy-and-compliance)를 검토하고 **동의함** 을 선택합니다.

1. **연결** 을 선택하여 해당 연결을 초기화합니다.

1. **내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.

1. 연결을 완료하려면 **저장** 을 선택합니다.

## <a name="configure-an-export"></a>내보내기 구성

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **데이터** > **내보내기** 로 이동합니다.

1. **내보내기 추가** 를 선택합니다.

1. **내보내기 연결** 필드의 Marketo 섹션에서 연결을 선택합니다. 사용 가능한 연결이 없으면 관리자에게 문의하십시오.

1. 내보낼 엔터티의 이름을 입력합니다.

1. **Marketo 목록 ID** 를 입력합니다. 목록 ID는 순수 숫자 값입니다. 예를 들어 Marketo 목록 ID가 ST12345A7인 경우 숫자 앞뒤의 문자를 제거하고 *12345* 를 입력합니다.

1. **데이터 매칭** 섹션에서 고객의 이메일 주소 또는 고객의 Marketo ID를 나타내는 필드를 하나 이상 선택합니다.

1. 필요에 따라 **이름** 과, **성**, **시**, **주**, **국가/지역** 을 내보내 더 개인 설정된 이메일을 만들 수 있습니다. **특성 추가** 를 선택하여 이러한 필드를 매핑합니다.

1. 내보낼 세그먼트를 선택합니다.

1. **저장** 을 선택합니다.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Marketo에서 [Marketo 목록](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)에 있는 세그먼트를 찾을 수 있습니다.

[!INCLUDE [footer-include](includes/footer-banner.md)]
