---
title: 타사 보강 HERE Technologies로 보강
description: HERE Technologies 타사 보강에 대한 일반 정보입니다.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 5d1f037377010153045c9255d2d01f98ebf1fdfd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896059"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>HERE Technologies로 고객 프로필 보강(미리 보기)

HERE Technologies는 위치 중심 데이터 및 서비스를 제공하는 위치 플랫폼 회사입니다. HERE Technologies의 데이터 보강 서비스를 사용하면 주소 정규화, 위도 및 경도 추출 등을 통해 고객에 대한 보다 정확한 위치 이해를 구축할 수 있습니다.

## <a name="prerequisites"></a>필수 구성 요소

HERE Technologies 보강을 구성하려면 다음 필수 구성 요소가 충족되어야 합니다.

- 활성 HERE Technologies 구독이 있어야 합니다. 구독을 받으려면 [여기에 등록](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic)하거나 직접 [HERE Technologies에 연락](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you)할 수 있습니다. [HERE Technologies Location 보강에 대해 자세히 알아보세요.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- 사용 가능한 HERE [연결](connections.md)이 *있거나* 귀하가 [관리자](permissions.md#administrator) 권한 및 HERE Technologies API 키를 가지고 있음.

## <a name="configure-the-enrichment"></a>보강 구성

1. **데이터** > **보강** 으로 이동합니다. 

1. HERE Technologies 타일에서 **내 데이터 보강** 을 선택하고 **시작** 을 선택합니다.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies 타일](media/HERE-tile.png "HERE Technologies 타일")

1. 드롭다운 목록에서 [연결](connections.md)을 선택하십시오. 사용 가능한 연결이 없으면 관리자에게 문의하십시오. 관리자인 경우 **연결 추가** 를 선택하여 연결을 만들 수 있습니다. 드롭다운에서 **HERE Technologies** 를 선택합니다. 

1. **HERE Technologies에 연결** 을 선택하여 선택을 확인합니다.

1.  **다음** 을 선택하고 HERE Technologies의 위치 데이터로 보강할 **고객 데이터 집합** 을 선택합니다. **고객** 엔터티를 선택하여 모든 고객 프로필을 보강하거나 세그먼트 엔터티를 선택하여 해당 세그먼트에 포함된 고객 프로필만 보강할 수 있습니다.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="고객 데이터 집합 선택 시 스크린샷입니다.":::

1. 필드를 기본 또는 보조 주소에 매핑할지 여부를 선택합니다. 두 주소에 대해 필드 매핑을 지정하고 두 주소에 대해 개별적으로 프로필을 보강할 수 있습니다. 예를 들어 집과 회사 주소가 있는 경우입니다. **다음** 을 선택합니다.

1. HERE Technologies에서 일치하는 위치 데이터를 찾는 데 사용해야 하는 통합 프로필의 필드를 정의합니다. **상세 주소 1** 및 **우편 번호** 필드는 선택한 기본 또는 보조 주소의 필수 항목입니다. 더 높은 일치 정확도를 위해 더 많은 필드를 추가할 수 있습니다.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies 강화 구성 페이지](media/enrichment-HERE-configuration.png "HERE Technologies 강화 구성 페이지")

1. 필드 매핑을 완료하려면 **다음** 을 선택합니다.

1. 보강의 이름을 제공합니다. 

1. 선택 사항을 검토 한 후 **보강 저장** 을 선택합니다.

## <a name="configure-the-connection-for-here-technologies"></a>HERE technologies에 대한 연결 구성 

연결을 구성하려면 관리자여야 합니다. 보강을 구성할 때 **연결 추가** 를 선택 *하거나* **관리자** > **연결** 로 이동하여 HERE technologies 타일에서 **설정** 을 선택합니다.

1. **표시 이름** 상자에 연결 이름을 입력합니다.

1. 유효한 HERE Technologies API 키를 제공하십시오.

1. **동의함** 확인란을 선택하여 **데이터 개인 정보 및 규정 준수** 에 대한 동의를 검토하고 제공합니다.

1. **확인** 을 선택하여 구성을 확인합니다.

1. 확인을 완료한 후 **저장** 을 선택합니다.

> [!div class="mx-imgBorder"]
   > ![HERE technologies 연결 구성 페이지](media/enrichment-HERE-connection.png "HERE technologies 연결 구성 페이지")

## <a name="enrichment-results"></a>보강 결과

강화 프로세스를 시작하려면 명령 모음에서.**실행** 을 선택하십시오. [예약된 새로 고침](system.md#schedule-tab)으로 시스템이 자동으로 보강을 실행하도록 할 수도 있습니다. 처리 시간은 고객 데이터의 크기와 HERE Technologies의 API 응답 시간에 따라 다릅니다.

보강 프로세스가 완료되면 **내 보강** 아래에서 새로 보강 된 고객 프로필 데이터를 검토 할 수 있습니다. 또한 마지막 업데이트 시간과 강화 된 프로필 수를 확인할 수 있습니다.

**보강된 데이터 보기** 를 선택하여 각 보강된 프로필의 상세 보기에 액세스할 수 있습니다 .

## <a name="next-steps"></a>다음 단계

보강된 고객 데이터를 바탕으로 구축합니다. [세그먼트](segments.md)를 만들고, [측정](measures.md)하고, 또한 [데이터를 내보내](export-destinations.md) 고객에게 맞춤형 경험을 제공합니다.

## <a name="data-privacy-and-compliance"></a>데이터 프라이버시 및 규정 준수

Dynamics 365 Customer Insights를 사용하여 HERE Technologies로 데이터를 전송하는 경우 Dynamics 365 Customer Insights 규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다. Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 HERE Technologies가 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다. 자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.
Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 보강을 언제든지 제거할 수 있습니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
