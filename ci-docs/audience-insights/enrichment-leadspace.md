---
title: 타사 보강 Leadspace를 사용하여 회사 프로필 보강
description: Leadspace 타사 보강에 대한 일반 정보입니다.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 685b1683b0c90eab04b130552d2cb23a8ab7a235
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673240"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Leadspace를 통한 회사 프로필 강화(미리 보기)

Leadspace는 B-to-B 고객 데이터 플랫폼을 제공하는 데이터 과학 회사입니다. 계정을 기반으로 하는 통합 고객 프로필이 있는 환경에서 데이터를 보강할 수 있습니다. 회사 규모, 위치 또는 산업과 같은 특성으로 *고객 프로필* 을 보강합니다. 직함, 가상 사용자 또는 이메일 인증과 같은 특성으로 *연락처 프로필* 을 보강합니다.

## <a name="prerequisites"></a>필수 조건

Leadspace를 구성하려면 다음 전제 조건이 충족되어야 합니다.

- 활성 Leadspace 라이선스.
- 계정을 기반으로 [통합된 고객 프로필](customer-profiles.md)이 있습니다.
- 관리자가 Leadspace 연결을 이미 구성했거나 귀하가 [관리자](permissions.md#administrator) 권한 및 "영구 키"(**Leadspace 토큰**)를 가지고 있음. 제품에 대한 자세한 설명은 [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/)에 직접 확인하십시오.

## <a name="configure-the-enrichment"></a>보강 구성

1. 대상 그룹 인사이트에서 **데이터** > **보강** 으로 이동합니다.

1. Leadspace 타일에서 **내 데이터 보강** 을 선택하고 **시작** 을 선택합니다.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace 타일의 스크린샷.":::

1. 드롭다운 목록에서 [연결](connections.md)을 선택하십시오. 사용 가능한 연결이 없으면 관리자에게 문의하십시오. 관리자인 경우 **연결 추가** 를 선택하고 **Leadspace** 를 선택하여 연결을 만들 수 있습니다. 

1. **Leadspace에 연결** 을 선택하여 연결을 확인합니다.

1. **다음** 을 선택하고 Leadspace의 회사 데이터로 보강할 **고객 데이터 집합** 을 선택합니다. **고객** 엔터티를 선택하여 모든 고객 프로필을 보강하거나 세그먼트 엔터티를 선택하여 해당 세그먼트에 포함된 고객 프로필만 보강할 수 있습니다.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="고객 데이터 집합 선택 시 스크린샷입니다.":::

1. **다음** 을 선택하고 Leadspace에서 일치하는 회사 데이터를 찾는 데 사용해야 하는 통합 프로필의 필드를 정의합니다. **회사의 이름** 필드는 필수입니다. 일치 정확도를 높이기 위해 **회사 웹 사이트** 및 **회사 위치** 라는 다른 필드를 최대 2개까지 추가할 수 있습니다.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace 필드 매핑 창.":::

1. 필드 매핑을 완료하려면 **다음** 을 선택합니다.

1. 보강하려는 *연락처 프로필* 이 있는 경우 확인란을 선택합니다. 대상 그룹 인사이트는 필수 필드를 자동으로 매핑합니다.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Leadspace 연락처 레코드 보강.":::
 
1. 보강에 대한 이름을 제공하고 선택 사항을 검토한 후 **보강 저장** 을 선택합니다.


## <a name="configure-the-connection-for-leadspace"></a>Leadspace에 대한 연결 구성 

연결을 구성하려면 관리자여야 합니다. 보강을 구성할 때 **연결 추가** 를 선택 *하거나* **관리자** > **연결** 로 이동하여 Leadspace 타일에서 **설정** 을 선택합니다.

1. **시작** 을 선택합니다. 

1. **표시 이름** 상자에 연결 이름을 입력합니다.

1. 유효한 Leadspace 토큰을 입력합니다.

1. **데이터 개인 정보 보호 및 규정 준수** 를 검토하고 **동의함** 을 선택하여 동의를 제공합니다.

1. **확인** 을 선택하여 구성을 확인합니다.

1. 확인을 완료한 후 **저장** 을 선택합니다.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace 연결 구성 페이지.":::

## <a name="enrichment-results"></a>보강 결과

보강을 새로 고친 후 [내 보강](enrichment-hub.md) 아래에서 새로 보강된 회사 데이터를 검토할 수 있습니다. 마지막 업데이트 시간과 보강된 프로필 수를 찾을 수 있습니다.

**보강된 데이터 보기** 를 선택하여 각 보강된 프로필의 상세 보기에 액세스할 수 있습니다 .

자세한 내용은 [Leadspace API](https://support.leadspace.com/hc/en-us/sections/201997649-API)를 참조하십시오.

## <a name="next-steps"></a>다음 단계


[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>데이터 프라이버시 및 규정 준수

Dynamics 365 Customer Insights를 사용하여 Leadspace로 데이터를 전송하는 경우 Dynamics 365 Customer Insights 규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다. Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 Leadspace가 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다. 자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.
Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 보강을 언제든지 제거할 수 있습니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
