---
title: Facebook 광고 관리자로 세그먼트 내보내기(프리뷰)(비디오 포함)
description: 연결을 구성하고 Facebook 광고 관리자로 내보내는 방법을 알아봅니다.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01be1a075db0da05dc5536aea8a33093f9a2ea13
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195022"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Facebook 광고 관리자로 세그먼트 내보내기(프리뷰)

통합 고객 프로필 세그먼트를 Facebook 광고 관리자에 내보내 Facebook 및 Instagram에서 캠페인을 만듭니다.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>전제 조건

- [Facebook 광고 계정](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)에는 [Facebook 비즈니스 계정](https://business.facebook.com/)이 포함됩니다.
- [Facebook 광고 계정](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)의 관리자 권한입니다.

## <a name="known-limitations"></a>알려진 제한 사항

- 최대 1,000만 개의 고객 프로필을 Facebook 광고 관리자로 내보낼 때마다 최대 90분이 소요될 수 있습니다.
- 세그먼트만 해당됩니다.
- [사용자 지정 대상 그룹](https://www.facebook.com/business/help/744354708981227?id=2469097953376494)의 Facebook *고객 목록* 유형만 해당됩니다.
  > [!NOTE]
  > 경우에 따라 드롭다운 목록에 다양한 유형의 사용자 지정 대상 그룹이 표시됩니다. *고객 목록* 이 아닌 다른 유형을 선택하면 내보낼 수 없습니다.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Facebook 광고 관리자 연결 설정

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 를 선택하고 **Facebook 광고 관리자** 를 선택합니다.

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. [기여자가 내보내기 위해 연결을 사용](connections.md#allow-contributors-to-use-a-connection-for-exports)할 수 있습니다.

1. Facebook 광고를 사용하여 인증:

   1. **Facebook으로 계속** 을 선택하여 Facebook 광고 계정에 로그인합니다.

   1. Facebook으로 인증한 후 **ads_management** 권한을 허용합니다.

   1. 작업할 **Facebook 광고 계정** 을 선택하십시오.

   1. 드롭다운 목록에서 **기존 사용자 지정 대상 그룹** 을 선택하거나 **새로운 사용자 지정 대상 그룹** 을 만드세요.

1. [데이터 개인 정보 보호 및 규정 준수](connections.md#data-privacy-and-compliance)를 검토하고 **동의함** 을 선택합니다.

1. 연결을 완료하려면 **저장** 을 선택합니다.

## <a name="configure-an-export"></a>내보내기 구성

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **데이터** > **내보내기** 로 이동합니다.

1. **내보내기 추가** 를 선택합니다.

1. **내보내기 연결** 필드의 Facebook 광고 관리자 섹션에서 연결을 선택합니다. 사용 가능한 연결이 없으면 관리자에게 문의하십시오.

1. 내보낼 엔터티의 이름을 입력합니다.

1. **데이터 연결** 필드에서 **이메일**, **이름과 주소** 또는 **전화번호** 를 선택하여 Facebook 광고 관리자에게 전송합니다.

1. 선택한 키 식별자에 대해 통합 고객 엔터티의 해당 특성을 매핑합니다.
   > [!TIP]
   > **이메일** 을 키 식별자로 선택하면 가장 많이 일치하는 결과를 얻습니다. 식별자를 추가하면 일치가 향상될 수 있습니다.

1. **특성 추가** 를 선택하여 Facebook 광고 관리자에 보낼 더 많은 특성을 매핑합니다. Facebook 광고 관리자의 특성은 다음과 같은 사용자 이름으로 매핑됩니다. **FN** = **이름**, **LN** = **성**, **FI** = **첫 이니셜**, **PHONE** = **전화**, **GEN** = **성별**, **DOB** = **생년월일**, **ST** = **주**, **CT** = **도시**, **ZIP** = **우편 번호**, **COUNTRY** = **국가/지역**

1. 내보낼 세그먼트를 선택합니다.

1. **저장** 을 선택합니다.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
