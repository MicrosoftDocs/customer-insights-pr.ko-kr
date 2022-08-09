---
title: DotDigital로 세그먼트 내보내기(프리뷰)
description: 연결을 구성하고 DotDigital로 내보내는 방법을 알아봅니다.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cabaea84e31f8fe97bc558a8dca8d93bc40f43b7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196080"
---
# <a name="export-segments-to-dotdigital-preview"></a>DotDigital로 세그먼트 내보내기(프리뷰)

통합 고객 프로필의 세그먼트를 DotDigital 주소록으로 내보내고 이를 캠페인, 이메일 마케팅에 사용하고 DotDigital로 고객 세그먼트를 구축합니다.

## <a name="prerequisites"></a>전제 조건

- [DotDigital 계정](https://dotdigital.com/)과 [API 사용자](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user)입니다.
- [신규](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)의 DotDigital ID 또는 DotDigital의 기존 주소록입니다. ID는 주소록을 선택하여 열 때 URL에서 찾을 수 있습니다.
- Customer Insights에 [세그먼트를 구성했습니다](segments.md).
- 내보낸 세그먼트의 통합 고객 프로필에는 이메일 주소를 나타내는 필드가 포함됩니다.

## <a name="known-limitations"></a>알려진 제한 사항

- 최대 100만 고객 프로필을 DotDigital로 내보낼 때마다 공급자 측의 제한으로 인해 완료까지 최대 3시간이 소요될 수 있습니다. DotDigital로 내보낼 수 있는 고객 프로필의 개수는 DotDigital와 체결한 계약에 따라 다릅니다.
- 세그먼트만 해당됩니다.

## <a name="set-up-connection-to-dotdigital"></a>DotDigital에 연결을 설정합니다.

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 를 선택하고 **DotDigital** 을 선택합니다.

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 이 연결을 사용할 수 있는 사용자를 선택합니다. 기본적으로 관리자만 해당합니다. 자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.

1. **DotDigital API 사용자 이름과 암호** 를 입력합니다.

1. **DotDigital 주소록 ID** 를 입력합니다.

1. [데이터 개인 정보 보호 및 규정 준수](connections.md#data-privacy-and-compliance)를 검토하고 **동의함** 을 선택합니다.

1. **연결** 을 선택하여 해당 연결을 초기화합니다.

1. **내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.

1. 연결을 완료하려면 **저장** 을 선택합니다.

## <a name="configure-an-export"></a>내보내기 구성

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **데이터** > **내보내기** 로 이동합니다.

1. **내보내기 추가** 를 선택합니다.

1. **내보내기 연결** 필드의 DotDigital 섹션에서 연결을 선택합니다. 사용 가능한 연결이 없으면 관리자에게 문의하십시오.

1. 내보낼 엔터티의 이름을 입력합니다.

1. **데이터 일치** 섹션의 **이메일** 필드에서 고객의 이메일 주소를 나타내는 필드를 선택합니다.

1. 필요에 따라 **이름**, **성**, **전체 이름**, **성별**, **우편번호** 를 내보냅니다.

1. 내보낼 세그먼트를 선택합니다.

1. **저장** 을 선택합니다.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

DotDigital의 경우 [DotDigital 주소록](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)에서 세그먼트를 찾을 수 있습니다.

[!INCLUDE [footer-include](includes/footer-banner.md)]
