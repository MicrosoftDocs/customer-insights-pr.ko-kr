---
title: HubSpot으로 Customer Insights 데이터 내보내기
description: 연결을 구성하고 HubSpot으로 내보내는 방법을 알아봅니다.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0281be288b2c4d9e5da7ad8e2ed25f7b51b8498e
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588910"
---
# <a name="export-segments-to-hubspot-preview"></a>HubSpot으로 세그먼트 내보내기(프리뷰)

통합 고객 프로필의 세그먼트를 HubSpot으로 내보내고 이메일 마케팅에 사용합니다.

## <a name="prerequisites-for-a-connection"></a>연결을 위한 전제 조건

- [HubSpot 계정](https://www.hubspot.com/) 및 해당 관리자 자격 증명.
- HubSpot의 [API 키](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key).
- Customer Insights에 [세그먼트를 구성했습니다](segments.md).

## <a name="known-limitations"></a>알려진 제한 사항

- HubSpot으로 내보내기당 최대 100,000개의 고객 프로필이 생성되며 완료하는 데 최대 15분이 소요될 수 있습니다. HubSpot으로 내보낼 수 있는 고객 프로필의 수는 HubSpot과의 계약에 따라 달라지고 제한됩니다.
- 세그먼트만 해당됩니다.

## <a name="set-up-connection-to-hubspot"></a>HubSpot에 연결 설정

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 와 **HubSpot.** 를 선택하여 연결을 구성합니다.

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 이 연결을 사용할 수 있는 사용자를 선택합니다. 아무 조치도 취하지 않으면 기본값은 관리자입니다. 자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.

1. 메시지가 표시되면 HubSpot 자격 증명을 입력합니다.

1. [데이터 개인 정보 보호 및 규정 준수](connections.md#data-privacy-and-compliance)를 검토하고 **동의함** 을 선택합니다.

1. **연결** 을 선택하여 HubSpot에 대한 연결을 초기화합니다.

1. **내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.

1. 연결을 완료하려면 **저장** 을 선택합니다.

## <a name="configure-an-export"></a>내보내기 구성

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **데이터** > **내보내기** 로 이동합니다.

1. **내보내기 추가** 를 선택하여 새 내보내기를 만듭니다.

1. **내보내기 연결** 필드의 HubSpot 섹션에서 연결을 선택합니다. 이 섹션 이름이 표시되지 않으면 사용 가능한 이 유형의 연결이 없는 것입니다.

1. **데이터 일치** 섹션의 **이메일** 필드에서 고객의 이메일 주소를 나타내는 필드를 선택합니다. 다른 옵션 필드에 적용하려면 동일한 단계를 반복합니다.

1. 내보낼 세그먼트를 선택합니다.

1. **저장** 을 선택합니다.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]