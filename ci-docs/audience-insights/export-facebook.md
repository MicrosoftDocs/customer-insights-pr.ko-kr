---
title: Facebook Ads Manager로 Customer Insights 데이터 내보내기
description: Facebook 광고 관리자에 대한 연결을 구성하는 방법 알아보기.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8260e3b5e529f3d54678d9d6e11aebb2795e27fd
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643691"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>Facebook 광고 관리자용 커넥터(미리 보기)

통합 고객 프로필 세그먼트를 Facebook 광고 관리자에 내보내 Facebook 및 Instagram에서 캠페인을 만듭니다.

## <a name="prerequisites"></a>필수 구성 요소

- [**Facebook 비즈니스 계정**](https://business.facebook.com/)이 포함된 [**Facebook 광고 계정**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)이 있어야 합니다.
- [**Facebook 광고 계정**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)의 관리자여야 합니다.

## <a name="connect-to-facebook-ads-manager"></a>Facebook 광고 관리자에 연결

1. **관리자** > **내보내기 대상** 으로 이동합니다.

1. **Facebook 광고 관리자** 아래에서 **설정** 을 선택합니다.

1. **표시 이름** 필드에서 내보내기 대상에 인식할 수 있는 이름을 지정합니다.

1. **Facebook으로 계속** 을 선택하고 Facebook 광고 계정에 로그인합니다.

1. Facebook으로 인증한 후 **ads_management** 권한을 허용합니다.

1. 작업할 **Facebook 광고 계정** 을 선택하십시오.

1. 드롭다운 목록에서 **기존 사용자 지정 대상 그룹** 을 선택하거나 **새 사용자 지정 대상 그룹** 을 만듭니다. 자세한 내용은 [**Facebook 광고 관리자의 대상 그룹**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).

1. **동의** 를 선택해 **데이터 프라이버시 및 규정 준수** 를 확인합니다.

1. **다음** 을 선택해 내보내기를 구성합니다.

## <a name="configure-the-connector"></a>커넥터 구성

1. **키 식별자 필드 선택** 에서 **이메일**, **이름과 주소** 또는 **전화** 를 선택해 Facebook 광고 관리자에 전송합니다.

1. 선택한 키 식별자에 대해 통합 고객 엔터티의 해당 특성을 매핑합니다.
   > [도움말] **이메일** 을 키 식별자로 선택하면 가장 많이 일치하는 결과를 얻습니다. 식별자를 추가하면 일치가 향상될 수 있습니다.

1. **특성 추가** 를 선택해 추가 특성을 매핑하고 Facebook 광고 관리자로 보냅니다. Facebook 광고 관리자의 특성은 다음과 같은 사용자 이름으로 매핑됩니다. **FN** = **이름**, **LN** = **성**, **FI** = **첫 이니셜**, **PHONE** = **전화**, **GEN** = **성별**, **DOB** = **생년월일**, **ST** = **주**, **CT** = **도시**, **ZIP** = **우편 번호**, **COUNTRY** = **국가/지역**

1. 내보낼 세그먼트를 선택합니다.

1. **저장** 을 선택합니다.

## <a name="export-the-data"></a>데이터 내보내기

[주문 시 데이터를 내보낼](export-destinations.md) 수 있습니다. 내보내기는 [예약된 새로 고침](system.md#schedule-tab)마다 실행됩니다.

## <a name="data-privacy-and-compliance"></a>데이터 프라이버시 및 규정 준수

Dynamics 365 Customer Insights를 사용하여 Facebook 광고 관리자로 데이터를 전송하는 경우 Dynamics 365 Customer Insights 규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다. Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 Facebook 광고가 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다. 자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.
Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.
