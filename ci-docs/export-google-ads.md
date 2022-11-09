---
title: Google Ads로 세그먼트 내보내기(프리뷰)
description: 연결을 구성하고 Google Ads로 내보내는 방법을 알아봅니다.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a46623e609665f8031f223593a6644147e5209d8
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725086"
---
# <a name="export-segments-to-google-ads-preview"></a>Google Ads로 세그먼트 내보내기(프리뷰)

통합 고객 프로필의 세그먼트를 Google Ads 대상 그룹 목록으로 내보내고 이를 사용하여 Google 검색, Gmail, YouTube 및 Google 디스플레이 네트워크에서 광고합니다.

## <a name="prerequisites"></a>전제 조건

- [Google Ads 계정](https://ads.google.com/) 및 해당 관리자 자격 증명입니다.
- [Google Ads 고객 ID](https://support.google.com/google-ads/answer/1704344)입니다.
- [Customer Match 정책](https://support.google.com/adspolicy/answer/6299717) 요건을 충족합니다.
- [리마케팅 목록 크기](https://support.google.com/google-ads/answer/7558048) 요건을 충족합니다.
- [구성된 세그먼트](segments.md)입니다.
- 내보낸 세그먼트의 통합 고객 프로필에는 이메일 주소, 전화, 모바일 광고주 ID, 타사 사용자 ID 또는 주소를 나타내는 필드가 있습니다.

## <a name="known-limitations"></a>알려진 제한 사항

- BYOS(Bring Your Own Storage)와 결합된 개인 링크는 지원되지 않습니다.
- 최대 100만 고객 프로필을 Google Ads로 내보낼 때마다 공급자 측의 제한으로 인해 완료까지 최대 30분이 소요될 수 있습니다.
- 세그먼트만 해당됩니다.
- Google Ads와 일치시키는 데 최대 48시간이 걸릴 수 있습니다.

## <a name="set-up-connection-to-google-ads"></a>Google Ads 연결 설정

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 를 선택하고 **Google Ads** 를 선택합니다.

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 이 연결을 사용할 수 있는 사용자를 선택합니다. 기본적으로 관리자만 해당합니다. 자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.

1. Google Ads 고객 ID를 입력합니다.

1. [데이터 개인 정보 보호 및 규정 준수](connections.md#data-privacy-and-compliance)를 검토하고 **동의함** 을 선택합니다.

1. **Google 광고로 인증** 을 선택하고 Google 광고 자격 인증을 제공합니다.

1. **내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.

1. 연결을 완료하려면 **저장** 을 선택합니다.

## <a name="configure-an-export"></a>내보내기 구성

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **데이터** > **내보내기** 로 이동합니다.

1. **내보내기 추가** 를 선택합니다.

1. **내보내기 연결** 필드의 Google Ads 섹션에서 연결을 선택합니다. 사용 가능한 연결이 없으면 관리자에게 문의하십시오.

1. 내보낼 엔터티의 이름을 입력합니다.

1. 기존 대상 그룹을 사용 또는 새 그룹을 생성할지 여부를 선택합니다.
   - 기존 Google Ads 대상 그룹을 업데이트하려면 [Google Ads 대상 그룹 ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns)를 입력하세요.
   - 새 대상 그룹을 만들려면 Google 대상 그룹 ID 필드를 비워 둡니다. Customer Insights는 Google Ads 계정에 새 대상 그룹을 자동으로 생성하고 내보낸 세그먼트의 이름을 사용합니다.

1. **데이터 매칭** 섹션에서 내보낼 데이터 필드를 하나 이상 선택하고 Customer Insights에서 해당 데이터 필드를 나타내는 필드를 선택합니다.

1. 내보낼 세그먼트를 선택합니다.

1. **저장** 을 선택합니다.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
