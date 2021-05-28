---
title: Google 광고로 Customer Insights 데이터 내보내기
description: 연결을 구성하고 Google Ads로 내보내는 방법을 알아봅니다.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 73f3257a3ae6e8423f45410546535df5e3b400ce
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976326"
---
# <a name="export-segments-to-google-ads-preview"></a>Google Ads로 세그먼트 내보내기(프리뷰)

통합 고객 프로필의 세그먼트를 Google 광고 대상 그룹 목록으로 내보내고 이를 사용하여 Google 검색, Gmail, YouTube 및 Google 디스플레이 네트워크에서 광고합니다. 

## <a name="prerequisites-for-connection"></a>연결을 위한 전제 조건

-   [Google 광고 계정](https://ads.google.com/) 및 해당 관리자 자격 증명이 있어야 합니다.
-   [승인된 Google Ads 개발자 토큰](https://developers.google.com/google-ads/api/docs/first-call/dev-token) 
-   [고객 일치 정책](https://support.google.com/adspolicy/answer/6299717) 요구 사항 충족
-   [리마케팅 목록 크기](https://support.google.com/google-ads/answer/7558048) 요구 사항 충족 

-   Google 광고에 기존 대상 그룹과 해당 ID가 있습니다. 자세한 내용은 [Google 광고 대상 그룹](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)을 참조하세요.
-   [구성된 세그먼트](segments.md)가 있어야 합니다.
-   내보낸 세그먼트의 통합 고객 프로필에는 이메일 주소, 이름 및 성을 나타내는 필드가 포함됩니다.

## <a name="known-limitations"></a>알려진 제한 사항

- Google 광고로 내보낼 때마다 프로필이 최대 100만 개입니다.
- Google 광고로 내보내기는 세그먼트로 제한됩니다.
- 총 100만 개의 프로필이 있는 세그먼트를 내보내는 것은 공급자측의 제한으로 인해 최대 5분이 걸릴 수 있습니다. 
- Google 광고에서 일치하는 데 최대 48시간이 걸릴 수 있습니다.

## <a name="set-up-connection-to-google-ads"></a>Google Ads 연결 설정

1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 와 **Google Ads** 를 선택하여 연결을 구성합니다.

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 이 연결을 사용할 수 있는 사용자를 선택합니다. 아무 조치도 취하지 않으면 기본값은 관리자입니다. 자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.

1. **[Google 광고 고객 ID](https://support.google.com/google-ads/answer/1704344)** 를 입력합니다.

1. **[Google 광고에서 승인한 개발자 토큰](https://developers.google.com/google-ads/api/docs/first-call/dev-token)** 을 입력합니다.

1. **동의** 를 선택해 **데이터 프라이버시 및 규정 준수** 를 확인합니다.

1. **Google 광고로 인증** 을 선택하고 Google 광고 자격 인증을 제공합니다.

1. **내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.

1. 연결을 완료하려면 **저장** 을 선택합니다. 

## <a name="configure-an-export"></a>내보내기 구성

이 유형의 연결에 대한 액세스 권한이 있는 경우 이 내보내기를 구성할 수 있습니다. 자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.

1. **데이터** > **내보내기** 로 이동합니다.

1. **대상 추가** 를 선택하여 새 내보내기를 만듭니다.

1. **내보내기 연결** 필드의 Google Ads 섹션에서 연결을 선택합니다. 이 섹션 이름이 표시되지 않으면 사용 가능한 이 유형의 연결이 없는 것입니다.

1. **[Google 광고 대상 그룹 ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** 를 입력하고 **연결** 을 선택하여 Google 광고 연결을 초기화합니다.

1. **데이터 일치** 섹션의 이메일 필드에서 고객의 **이메일** 주소를 나타내는 통합 고객 프로필의 필드를 선택합니다. **이름** 및 **성** 필드에 동일한 단계를 반복합니다.

1. 내보낼 세그먼트를 선택합니다. 총 100만 개의 고객 프로필을 Google 광고로 내보낼 수 있습니다.

내보내기를 저장해도 내보내기가 즉시 실행되지는 않습니다.

내보내기는 모든 [예약된 새로 고침](system.md#schedule-tab)에 따라 실행됩니다. [주문형으로 데이터를 내보낼](export-destinations.md#run-exports-on-demand)수도 있습니다. 

## <a name="data-privacy-and-compliance"></a>데이터 프라이버시 및 규정 준수

Dynamics 365 Customer Insights를 사용하여 Google 광고로 데이터를 전송하는 경우 Dynamics 365 Customer Insights 규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다. Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 Google 광고가 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다. 자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.
Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
