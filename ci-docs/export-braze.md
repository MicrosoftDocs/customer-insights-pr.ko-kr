---
title: Braze로 세그먼트 내보내기(프리뷰)
description: 연결을 구성하고 Braze로 내보내는 방법을 알아보세요.
ms.date: 10/06/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 2f52eb8196e057f934c8d2b5ac0518ce121606b6
ms.sourcegitcommit: 003c1929f730d7d505c108aba84f6269f4c98978
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2022
ms.locfileid: "9655278"
---
# <a name="export-segments-to-braze-preview"></a>Braze로 세그먼트 내보내기(프리뷰)

Unified customer profile의 세그먼트를 Braze로 내보내고 마케팅 활동에 사용합니다.

## <a name="prerequisites"></a>전제 조건

- [Braze 계정](https://www.braze.com/) 및 해당 관리자 자격 증명입니다.
- [Braze API 키](https://www.braze.com/docs/api/basics/)
- [Braze REST 끝점](https://www.braze.com/docs/api/basics/#api-definitions) 
- Customer Insights에 [세그먼트를 구성했습니다](segments.md).
- 내보낸 세그먼트의 Unified customer profile에는 이메일 주소와 Braze 고객 ID를 나타내는 필드가 있습니다.

## <a name="known-limitations"></a>알려진 제한 사항

- 최대 100만 개의 고객 프로필을 Braze로 내보내는 데 최대 40분이 소요될 수 있습니다. Braze로 내보낼 수 있는 고객 프로필의 개수는 Braze와 체결한 계약에 따라 다릅니다.
- 세그먼트만 해당됩니다.
- Azure Private Link는 Braze 내보내기에 지원되지 않습니다.

## <a name="set-up-connection-to-braze"></a>Braze에 연결 설정

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 를 선택하고 **Braze** 를 선택합니다.

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 이 연결을 사용할 수 있는 사용자를 선택합니다. 기본적으로 관리자만 해당합니다. 자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.

1. 계속 로그인하려면 Braze API 키를 제공하세요.

1. [데이터 개인 정보 보호 및 규정 준수](connections.md#data-privacy-and-compliance)를 검토하고 **동의함** 을 선택합니다.

1. **연결** 을 선택하여 해당 연결을 초기화합니다.

1. **내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.

1. 연결을 완료하려면 **저장** 을 선택합니다.

## <a name="configure-an-export"></a>내보내기 구성

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **데이터** > **내보내기** 로 이동합니다.

1. **내보내기 추가** 를 선택합니다.

1. **내보내기 연결** 필드의 Braze 섹션에서 연결을 선택합니다. 사용 가능한 연결이 없으면 관리자에게 문의하십시오.

1. REST 끝점을 **호스트 이름** 필드에 `rest.iad-03.braze.com` 형식으로 입력합니다.

1. 내보낼 엔터티의 이름을 입력합니다.

1. **데이터 일치** 섹션의 **이메일** 필드에서 고객의 이메일 주소를 나타내는 필드를 선택합니다. **고객 ID** 필드에서 고객의 Braze ID를 나타내는 필드를 선택하세요. Braze의 세그먼트는 Dynamics 365 Customer Insights에서와 동일한 세그먼트 이름으로 생성됩니다. 데이터를 일치시키기 위해 옵션 필드를 더 선택할 수 있습니다.

1. 내보내려는 엔터티 또는 세그먼트를 선택합니다.

1. **저장** 을 선택합니다.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
