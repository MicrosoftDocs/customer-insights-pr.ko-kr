---
title: Sendinblue로 세그먼트 내보내기(프리뷰)
description: 연결을 구성하고 Sendinblue로 내보내는 방법을 알아봅니다.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc4ac34c1de096e25ba6c374fe17b1da6b2f745f
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724902"
---
# <a name="export-segments-to-sendinblue-preview"></a>Sendinblue로 세그먼트 내보내기(프리뷰)

통합 고객 프로필의 세그먼트를 내보내 캠페인을 생성하고 이메일 마케팅을 제공하며 Sendinblue의 특정 고객 그룹을 사용합니다.

## <a name="prerequisites"></a>전제 조건

- [Sendinblue 계정](https://www.sendinblue.com/) 및 해당 관리자 자격 증명입니다.
- [SendinBlue API 키](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)입니다.
- Sendinblue의 기존 목록과 해당 ID입니다.
- [구성된 세그먼트](segments.md)입니다.
- 내보낸 세그먼트의 통합 고객 프로필에는 이메일 주소를 나타내는 필드가 포함됩니다.

## <a name="known-limitations"></a>알려진 제한 사항

- BYOS(Bring Your Own Storage)와 결합된 개인 링크는 지원되지 않습니다.
- 최대 100만 개의 고객 프로필을 Sendinblue로 내보낼 때마다 완료까지 최대 90분이 소요될 수 있습니다. Sendinblue로 내보낼 수 있는 고객 프로필의 개수는 Sendinblue와 체결한 계약에 따라 다릅니다.
- 세그먼트만 해당됩니다.

## <a name="set-up-connection-to-sendinblue"></a>Sendinblue 연결 설정

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 를 선택하고 **Sendinblue** 를 선택합니다.

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 이 연결을 사용할 수 있는 사용자를 선택합니다. 기본적으로 관리자만 있습니다. 자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.

1. **Sendinblue API 키** 를 입력합니다.

1. [데이터 개인 정보 보호 및 규정 준수](connections.md#data-privacy-and-compliance)를 검토하고 **동의함** 을 선택합니다.

1. **연결** 을 선택하여 해당 연결을 초기화합니다.

1. **내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.

1. 연결을 완료하려면 **저장** 을 선택합니다.

## <a name="configure-an-export"></a>내보내기 구성

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **데이터** > **내보내기** 로 이동합니다.

1. **내보내기 추가** 를 선택합니다.

1. **내보내기 연결** 필드에서 Sendinblue 섹션에서 연결을 선택합니다. 사용 가능한 연결이 없으면 관리자에게 문의하십시오.

1. 내보낼 엔터티의 이름을 입력합니다.

1. **Sendinblue 목록 ID** 를 입력합니다.

1. **데이터 일치** 섹션의 **이메일** 필드에서 고객의 이메일 주소를 나타내는 필드를 선택합니다.

1. 필요에 따라 **이름**, **성**, **전화번호** 를 내보내 더 개인 설정된 이메일을 만들 수 있습니다. **특성 추가** 를 선택하여 이러한 필드를 매핑합니다.

1. 내보낼 세그먼트를 선택합니다.

1. **저장** 을 선택합니다.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
