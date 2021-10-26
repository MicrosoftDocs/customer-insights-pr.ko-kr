---
title: Facebook Ads Manager로 Customer Insights 데이터 내보내기
description: 연결을 구성하고 Facebook 광고 관리자로 내보내는 방법을 알아봅니다.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4403c6f535f5dc60919be3717073d52640bbe61a
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/08/2021
ms.locfileid: "7619219"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>Facebook 광고 관리자로 세그먼트 목록 내보내기(프리뷰)

통합 고객 프로필 세그먼트를 Facebook 광고 관리자에 내보내 Facebook 및 Instagram에서 캠페인을 만듭니다.

## <a name="prerequisites-for-connection"></a>연결을 위한 전제 조건

- [**Facebook 비즈니스 계정**](https://business.facebook.com/)이 포함된 [**Facebook 광고 계정**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)이 있어야 합니다.
- [**Facebook 광고 계정**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)의 관리자여야 합니다.

## <a name="known-limitations"></a>알려진 제한 사항

- Facebook 광고 관리자로 내보내기당 최대 1,000만 개의 고객 프로필을 내보낼 수 있습니다.
- Facebook 광고 관리자에게 내보내기는 세그먼트로 제한됩니다.
- Facebook에서 *고객 목록* 유형의 사용자 지정 대상만 만들거나 업데이트합니다.
- 총 1,000만 개의 고객 프로필이 포함된 세그먼트를 내보내는 데 최대 90분이 걸릴 수 있습니다.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Facebook 광고 관리자 연결 설정

사용자가 내보내기를 생성하려면 관리자가 서비스에 대한 연결을 구성하고 기여자가 연결을 사용할 수 있도록 허용해야 합니다.

1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 와 **Facebook 광고 관리자** 를 선택하여 연결을 구성합니다.

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 이 연결을 사용할 수 있는 사용자를 선택합니다. 아무 조치도 취하지 않으면 기본값은 관리자입니다. 자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.

1. Facebook 광고를 사용하여 인증: 

   1. **Facebook으로 계속** 을 선택하여 Facebook 광고 계정에 로그인합니다.

   1. Facebook으로 인증한 후 **ads_management** 권한을 허용합니다.

   1. 작업할 **Facebook 광고 계정** 을 선택하십시오.

   1. 드롭다운 목록에서 **기존 사용자 지정 대상 그룹** 을 선택하거나 **새로운 사용자 지정 대상 그룹** 을 만드세요. 자세한 내용은 [**Facebook 광고 관리자의 대상 그룹**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > 이 내보내기로는 Facebook에서 *고객 목록* 유형의 사용자 지정 대상만 만들거나 업데이트할 수 있습니다. 경우에 따라 드롭다운 목록에 다양한 유형의 사용자 지정 대상이 표시됩니다. *고객 목록* 이 아닌 다른 유형을 선택하면 내보내기에 실패합니다. 

1. **데이터 개인 정보 보호 및 규정 준수** 를 검토하고 **동의함** 을 선택합니다.

1. 연결을 완료하려면 **저장** 을 선택합니다.

## <a name="configure-an-export"></a>내보내기 구성

이 유형의 연결에 대한 액세스 권한이 있는 경우 이 내보내기를 구성할 수 있습니다. 자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.

1. **데이터** > **내보내기** 로 이동합니다.

1. **대상 추가** 를 선택하여 새 내보내기를 만듭니다. 

1. **내보내기 연결** 의 **Facebook 광고 관리자** 섹션에서 연결을 선택합니다. 이 섹션 이름이 표시되지 않으면 이 유형의 연결을 사용할 수 없습니다.

1. **키 식별자 필드 선택** 에서 **이메일**, **이름과 주소** 또는 **전화** 를 선택해 Facebook 광고 관리자에 전송합니다. 

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다.

1. 선택한 키 식별자에 대해 통합 고객 엔터티의 해당 특성을 매핑합니다.
   > [!TIP]
   > **이메일** 을 키 식별자로 선택하면 가장 많이 일치하는 결과를 얻습니다. 식별자를 추가하면 일치가 향상될 수 있습니다.

1. **특성 추가** 를 선택하여 Facebook 광고 관리자에 보낼 더 많은 특성을 매핑합니다. Facebook 광고 관리자의 특성은 다음과 같은 사용자 이름으로 매핑됩니다. **FN** = **이름**, **LN** = **성**, **FI** = **첫 이니셜**, **PHONE** = **전화**, **GEN** = **성별**, **DOB** = **생년월일**, **ST** = **주**, **CT** = **도시**, **ZIP** = **우편 번호**, **COUNTRY** = **국가/지역**

1. 내보낼 세그먼트를 선택합니다.

1. **저장** 을 선택합니다.

내보내기를 저장해도 내보내기가 즉시 실행되지는 않습니다.

내보내기는 모든 [예약된 새로 고침](system.md#schedule-tab)에 따라 실행됩니다. 

[주문형으로 데이터를 내보낼](export-destinations.md#run-exports-on-demand)수도 있습니다. 

## <a name="data-privacy-and-compliance"></a>데이터 프라이버시 및 규정 준수

Dynamics 365 Customer Insights를 사용하여 Facebook 광고 관리자로 데이터를 전송하는 경우 Dynamics 365 Customer Insights 규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다. Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 Facebook 광고가 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다. 자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.
Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
