---
title: AdRoll로 Customer Insights 데이터 내보내기
description: AdRoll 연결을 구성하는 방법을 알아보십시오.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697082"
---
# <a name="connector-for-adroll-preview"></a>AdRoll용 커넥터(프리뷰)

통합 고객 프로필의 세그먼트를 AdRoll로 내보내고 광고에 사용합니다. 

## <a name="prerequisites"></a>필요한 항목

-   [AdRoll 거래처](https://www.adroll.com/) 및 해당 관리자 자격 증명이 있어야 합니다.
-   대상 그룹 인사이트에 [구성된 세그먼트](segments.md)가 있어야 합니다.
-   내보낸 세그먼트의 통합 고객 프로필에는 이메일 주소를 나타내는 필드가 포함됩니다.

## <a name="connect-to-adroll"></a>AdRoll에 연결

1. **관리자** > **내보내기 대상** 으로 이동합니다.

1. **AdRoll** 에서 **설정** 을 선택합니다.

1. **표시 이름** 필드에서 내보내기 대상에 인식할 수 있는 이름을 지정합니다.

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="AdRoll 연결을 위한 구성 창입니다.":::

1. **동의** 를 선택해 **데이터 프라이버시 및 규정 준수** 를 확인합니다.

1. **연결** 을 선택하여 AdRoll에 대한 연결을 초기화합니다.

1. **AdRoll로 인증** 을 선택하고 AdRoll 관리자 자격 인증을 제공합니다. 

1. **내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.

1. **AdRoll 광고주 ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles)을 입력합니다.

1. **다음** 을 선택해 내보내기를 구성합니다.

## <a name="configure-the-connector"></a>커넥터 구성

1. **데이터 일치** 섹션의 이메일 필드에서 고객의 **이메일** 주소를 나타내는 통합 고객 프로필의 필드를 선택합니다. 세그먼트를 AdRoll로 내보내는 데 필요합니다.

1. 내보낼 세그먼트를 선택합니다. 구성원이 100명 이상인 세그먼트를 선택합니다. 더 작은 세그먼트는 내보낼 수 없습니다. 또한 내보낼 세그먼트의 최대 크기는 내보내기당 250,000명입니다. 

1. **저장** 을 선택합니다.

## <a name="export-the-data"></a>데이터 내보내기

[주문 시 데이터를 내보낼](export-destinations.md) 수 있습니다. 내보내기는 [예약된 새로 고침](system.md#schedule-tab)마다 실행됩니다.

## <a name="known-limitations"></a>알려진 제한 사항

- 내보내기당 25만 개의 고객 프로필을 AdRoll로 내보낼 수 있습니다.
- 프로필이 100개 미만인 세그먼트는 AdRoll로 내보낼 수 없습니다. 
- AdRoll로 내보내기는 세그먼트로 제한됩니다.
- 최대 250,000개의 프로필을 AdRoll로 내보내는 데 최대 10분이 걸릴 수 있습니다. 
- AdRoll로 내보낼 수 있는 프로필 수는 AdRoll과의 계약에 따라 다르며 제한됩니다.

## <a name="data-privacy-and-compliance"></a>데이터 프라이버시 및 규정 준수

Dynamics 365 Customer Insights를 사용하여 AdRoll로 데이터를 전송하는 경우 Dynamics 365 Customer Insights 규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다. Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 AdRoll가 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다. 자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.

Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.
