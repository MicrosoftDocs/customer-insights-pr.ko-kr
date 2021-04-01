---
title: SendGrid로 Customer Insights 데이터 내보내기
description: SendGrid에 연결을 구성하는 방법을 알아보세요.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597289"
---
# <a name="connector-for-sendgrid-preview"></a>SendGrid용 커넥터(미리 보기)

통합 고객 프로필의 세그먼트를 SendGrid 연락처 목록으로 내보내고 SendGrid의 캠페인 및 이메일 마케팅에 사용합니다. 

## <a name="prerequisites"></a>필요한 항목

-   [SendGrid 계정](https://sendgrid.com/) 및 해당 관리자 자격 증명이 있어야 합니다.
-   SendGrid에 기존 연락처 목록과 해당 ID가 있습니다. 자세한 내용은 [SendGrid - 연락처 관리](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)를 참조하세요.
-   대상 그룹 인사이트에 [구성된 세그먼트](segments.md)가 있어야 합니다.
-   내보낸 세그먼트의 통합 고객 프로필에는 이메일 주소를 나타내는 필드가 포함됩니다.

## <a name="connect-to-sendgrid"></a>SendGrid에 연결

1. **관리자** > **내보내기 대상** 으로 이동합니다.

1. **SendGrid** 에서 **설정** 을 선택합니다.

1. **표시 이름** 필드에서 내보내기 대상에 인식할 수 있는 이름을 지정합니다.

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="SendGrid 내보내기 구성 창입니다.":::

1. **SendGrid API 키** [SendGrid API 키](https://sendgrid.com/docs/ui/account-and-settings/api-keys/)를 입력하십시오.

1. **[SendGrid 목록 ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)** 를 입력합니다.

1. **동의** 를 선택해 **데이터 프라이버시 및 규정 준수** 를 확인합니다.

1. **연결** 을 선택하여 SendGrid에 대한 연결을 초기화합니다.

1. **내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.

1. **다음** 을 선택해 내보내기를 구성합니다.

## <a name="configure-the-connector"></a>커넥터 구성

1. **데이터 일치** 섹션의 이메일 필드에서 고객의 **이메일** 주소를 나타내는 통합 고객 프로필의 필드를 선택합니다. **이름**, **성**, **국가/지역**, **주**, **도시** 및 **우편 번호** 와 같은 다른 선택 사항 필드에 대해 동일한 단계를 반복하십시오.

1. 내보낼 세그먼트를 선택합니다. SendGrid로 **총 10만 개 이상의 고객 프로필은 내보내지 않을 것을 강력히 권고합니다**. 

1. **저장** 을 선택합니다.

## <a name="export-the-data"></a>데이터 내보내기

[주문 시 데이터를 내보낼](export-destinations.md) 수 있습니다. 내보내기는 [예약된 새로 고침](system.md#schedule-tab)마다 실행됩니다.

## <a name="known-limitations"></a>알려진 제한 사항

- SendGrid에 최대 10만 개의 프로필.
- SendGrid로 내보내기는 세그먼트로 제한됩니다.
- 최대 10만 개의 프로필을 SendGrid로 내보내는 데 최대 몇 시간이 걸릴 수 있습니다. 
- SendGrid로 내보낼 수 있는 프로필 수는 SendGrid와의 계약에 따라 다르며 제한됩니다.

## <a name="data-privacy-and-compliance"></a>데이터 프라이버시 및 규정 준수

Dynamics 365 Customer Insights를 사용하여 SendGrid로 데이터를 전송하는 경우 Dynamics 365 Customer Insights규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다. Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만, 귀하가 가질 수 있는 개인 정보 보호 또는 보안 의무를 SendGrid가 충족하도록 할 책임은 사용자에게 있습니다. 자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.
Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]