---
title: Marketo로 Customer Insights 데이터 내보내기
description: Marketo 연결을 구성하는 방법을 알아보세요.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 74d19a0448123904210c26f7b8760d00296c9cfd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597979"
---
# <a name="connector-for-marketo-preview"></a>Marketo용 커넥터(미리 보기)

통합 고객 프로필의 세그먼트를 내보내 캠페인을 생성하고 이메일 마케팅을 제공하며 Marketo에서 특정 고객 그룹을 사용합니다.

## <a name="prerequisites"></a>필수 구성 요소

-   [Marketo 계정](https://login.marketo.com/) 및 해당 관리자 자격 증명이 있어야 합니다.
-   Marketo에 기존 목록과 해당 ID가 있습니다. 자세한 내용은 [Marketo 목록](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)을 참조하세요.
-   [구성된 세그먼트](segments.md)가 있어야 합니다.
-   내보낸 세그먼트의 통합 고객 프로필에는 이메일 주소를 나타내는 필드가 포함됩니다.

## <a name="connect-to-marketo"></a>Marketo에 연결

1. **관리자** > **내보내기 대상** 으로 이동합니다.

1. **Marketo** 에서 **설정** 을 선택합니다.

1. **표시 이름** 필드에서 내보내기 대상에 인식할 수 있는 이름을 지정합니다.

1. **[Marketo 클라이언트 ID, 클라이언트 암호 및 REST 엔드포인트 호스트 이름](https://developers.marketo.com/rest-api/authentication/)** 을 입력합니다.

1. **[Marketo 목록 ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 를 입력합니다. 

1. **데이터 개인 정보 보호 및 준수** 를 확인하려면 **동의함** 을 선택하고 Marketo에 대한 연결을 초기화하려면 **연결** 을 선택합니다.

1. **내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Marketo 연결에 대한 스크린샷 내보내기":::

1. **다음** 을 선택해 내보내기를 구성합니다.

## <a name="configure-the-connector"></a>커넥터 구성

1. **데이터 일치** 섹션의 이메일 필드에서 고객의 **이메일** 주소를 나타내는 통합 고객 프로필의 필드를 선택합니다. 

1. 선택적으로 **이름**, **성**, **도시**, **주** 및 **국가/지역** 을 추가 필드로 내보내 더 개인화된 이메일을 만들 수 있습니다. **특성 추가** 를 선택하여 이러한 필드를 매핑합니다.

1. 내보낼 세그먼트를 선택합니다. 총 100만 개의 고객 프로필을 Marketo로 내보낼 수 있습니다.

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Marketo로 내보낼 필드 및 세그먼트 선택":::

1. **저장** 을 선택합니다.

## <a name="export-the-data"></a>데이터 내보내기

[주문 시 데이터를 내보낼](export-destinations.md) 수 있습니다. 내보내기는 [예약된 새로 고침](system.md#schedule-tab)마다 실행됩니다. Marketo에서 이제 [Marketo 목록](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)에 있는 세그먼트를 찾을 수 있습니다.

## <a name="known-limitations"></a>알려진 제한 사항

- Marketo로 내보낼 때마다 프로필이 최대 100만 개입니다.
- Marketo로 내보내기는 세그먼트로 제한됩니다.
- 총 100만 개의 프로필이 있는 세그먼트를 내보내려면 최대 3시간이 걸릴 수 있습니다. 
- Marketo로 내보낼 수 있는 프로필 수는 Marketo와의 계약에 따라 다르며 제한됩니다.

## <a name="data-privacy-and-compliance"></a>데이터 프라이버시 및 규정 준수

Dynamics 365 Customer Insights를 사용하여 Marketo로 데이터를 전송하는 경우 Dynamics 365 Customer Insights규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다. Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 Marketo가 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다. 자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.
Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]