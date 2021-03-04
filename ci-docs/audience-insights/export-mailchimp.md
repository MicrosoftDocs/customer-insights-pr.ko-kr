---
title: Mailchimp 광고로 Customer Insights 데이터 내보내기
description: Mailchimp 연결을 구성하는 방법을 알아보세요.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2b465b32fa956e3f45a23f471dc3a3183def16ef
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267181"
---
# <a name="connector-for-mailchimp-preview"></a>Mailchimp용 커넥터(미리 보기)

통합 고객 프로필의 세그먼트를 Mailchimp로 내보내 뉴스레터 및 이메일 캠페인을 만듭니다.

## <a name="prerequisites"></a>필수 구성 요소

-   [Mailchimp 계정](https://mailchimp.com/) 및 해당 관리자 자격 증명이 있어야 합니다.
-   Mailchimp에 기존 대상 그룹과 해당 ID가 있습니다. 자세한 내용은 [Mailchimp 대상 그룹](https://mailchimp.com/help/create-audience/)을 참조하세요.
-   [구성된 세그먼트](segments.md)가 있어야 합니다.
-   내보낸 세그먼트의 통합 고객 프로필에는 이메일 주소를 나타내는 필드가 포함됩니다.

## <a name="connect-to-mailchimp"></a>Mailchimp에 연결

1. **관리자** > **내보내기 대상** 으로 이동합니다.

1. **Mailchimp** 에서 **설정** 을 선택합니다.

1. **표시 이름** 필드에서 내보내기 대상에 인식할 수 있는 이름을 지정합니다.

1. **동의** 를 선택해 **데이터 프라이버시 및 규정 준수** 를 확인합니다.

1. **[Mailchimp 대상 그룹 ID](https://mailchimp.com/help/find-audience-id/)** 를 입력하고 **연결** 을 선택하여 Mailchimp 연결을 초기화합니다.

1. **Mailchimp로 인증** 을 선택하고 Mailchimp 자격 인증을 제공합니다.

1. **내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Mailchimp 연결에 대한 스크린샷 내보내기":::

1. **다음** 을 선택해 내보내기를 구성합니다.

## <a name="configure-the-connector"></a>커넥터 구성

1. **데이터 일치** 섹션의 이메일 필드에서 고객의 **이메일** 주소를 나타내는 통합 고객 프로필의 필드를 선택합니다. 

1. 선택적으로 **이름** 및 **성** 을 추가 필드로 내보내 더 개인화된 이메일을 만들 수 있습니다. **특성 추가** 를 선택하여 이러한 필드를 매핑합니다.

1. 내보낼 세그먼트를 선택합니다. 총 100만 개의 고객 프로필을 Mailchimp로 내보낼 수 있습니다.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Mailchimp로 내보낼 필드 및 세그먼트 선택":::

1. **저장** 을 선택합니다.

## <a name="export-the-data"></a>데이터 내보내기

[주문 시 데이터를 내보낼](export-destinations.md) 수 있습니다. 내보내기는 [예약된 새로 고침](system.md#schedule-tab)마다 실행됩니다. Mailchimp에서 이제 [Mailchimp 대상 그룹](https://mailchimp.com/help/create-audience/)에 있는 세그먼트를 찾을 수 있습니다.

## <a name="known-limitations"></a>알려진 제한 사항

- Mailchimp로 내보낼 때마다 프로필이 최대 100만 개입니다.
- Mailchimp로 내보내기는 세그먼트로 제한됩니다.
- 총 100만 개의 프로필이 있는 세그먼트를 내보내는 것은 공급자측의 제한으로 인해 최대 3시간이 걸릴 수 있습니다. 
- Mailchimp로 내보낼 수 있는 프로필 수는 Mailchimp와의 계약에 따라 다르며 제한됩니다.

## <a name="data-privacy-and-compliance"></a>데이터 프라이버시 및 규정 준수

Dynamics 365 Customer Insights를 사용하여 Mailchimp로 데이터를 전송하는 경우 Dynamics 365 Customer Insights 규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다. Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 Mailchimp가 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다. 자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.
Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]