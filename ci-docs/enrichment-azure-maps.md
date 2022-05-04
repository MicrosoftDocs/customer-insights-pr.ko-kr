---
title: Azure Maps에서 위치 데이터로 고객 프로필 보강
description: Azure Maps 자사 보강에 대한 일반 정보.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 6a1c3791076a7dda4531664ca88632f7f1b914e3
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646533"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Azure Maps를 통한 고객 프로필 보강(프리뷰)

Azure Maps는 기본 제공 위치 인텔리전스를 통해 지리 공간 데이터를 기반으로 경험을 제공하는 위치 중심 데이터 및 서비스를 제공합니다. Azure Maps 데이터 보강 서비스는 고객에 대한 위치 정보의 정밀도를 향상시킵니다. Dynamics 365 Customer Insights에 주소 정규화, 위도 및 경도 추출과 같은 기능을 제공합니다.

## <a name="prerequisites"></a>필수 조건

Azure Maps 데이터 보강을 구성하려면 다음 필수 구성 요소가 충족되어야 합니다.

- 활성 Azure Maps 구독이 있어야 합니다. 구독을 받으려면 [가입 또는 무료 평가판 받기](https://azure.microsoft.com/services/azure-maps/)를 수행하면 됩니다.

- Azure Maps [연결](connections.md)을 사용할 수 있거나 *또는* [관리자](permissions.md#admin) 사용 권한과 활성 Azure Maps API 키가 있어야 합니다.

## <a name="configure-the-enrichment"></a>보강 구성

1. **데이터** > **보강** 으로 이동합니다. 

1. **위치** 타일에서 **내 데이터 보강** 을 선택합니다.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Azure Maps 타일.":::

1. 드롭다운 목록에서 [연결](connections.md)을 선택하십시오. Azure Maps 연결을 사용할 수 없는 경우 관리자에게 문의하세요. 관리자인 경우 [Azure Maps에 대한 연결 구성](#configure-the-connection-for-azure-maps)을 수행할 수 있습니다. 

1. **다음** 을 선택하여 선택을 확인합니다.

1. Azure Maps의 위치 데이터로 보강할 **고객 데이터 집합** 을 선택합니다. **고객** 엔터티를 선택하여 통합된 모든 고객 프로필을 보강하거나 세그먼트 엔터티를 선택하여 해당 세그먼트에 포함된 고객 프로필만 보강할 수 있습니다.

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="고객 데이터 집합을 선택할 때의 스크린샷.":::

1. 필드를 기본 및/또는 보조 주소에 매핑할지 여부를 선택합니다. 두 주소에 대한 필드 매핑을 지정하고 두 주소에 대한 프로필을 별도로 보강할 수 있습니다&mdash;예: 집 주소 및 회사 주소. **다음** 을 선택합니다.

1. Azure Maps에서 일치하는 위치 데이터를 찾는 데 사용할 통합 프로필의 필드를 정의합니다. **도로명 1** 및 **우편번호** 필드는 선택한 기본 또는 보조 주소에 필요합니다. 더 높은 일치 정확도를 위해 더 많은 필드를 추가할 수 있습니다.

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Azure Maps 보강 구성 페이지.":::

1. 필드 매핑을 완료하려면 **다음** 을 선택합니다.

1. **고급 설정** 을 수정할지 여부를 평가합니다. 이는 고급 사용 케이스를 처리할 수 있는 최대한의 유연성을 제공하기 위해 제공되지만 대부분의 경우 기본값이 적절합니다.
   - **주소 유형**: 기본 동작은 보강이 불완전하더라도 최상의 주소 일치를 반환하는 것입니다. 완전한 주소만 얻으려면&mdash;예를 들어 집 번호가 포함된 주소&mdash;**포인트 주소** 를 제외한 모든 확인란을 선택 취소합니다. 
   - **언어** : 기본적으로 주소는 해당 주소가 속한 지역의 언어로 반환됩니다. 표준화된 주소 언어를 적용하려면 드롭다운 메뉴에서 언어를 선택합니다. 예를 들어 **영어** 를 선택하면 **København, Danmark** 대신 **Copenhagen, Denmark** 가 반환됩니다.

1. 보강의 이름을 제공합니다.

1. 선택 사항을 검토한 다음 **보강 저장** 을 선택합니다.

## <a name="configure-the-connection-for-azure-maps"></a>Azure Maps에 대한 연결 구성

연결을 구성하려면 Customer Insights의 관리자여야 합니다. 보강을 구성할 때 **연결 추가** 를 선택하거나 **관리자** > **연결** 로 이동하여 Azure Maps 타일에서 **설정** 을 선택합니다.

1. **표시 이름** 상자에 연결 이름을 입력합니다.

1. 유효한 Azure Maps API 키를 제공하십시오.

1. **동의함** 확인란을 선택하여 **데이터 개인 정보 및 규정 준수** 에 대한 동의를 검토하고 제공합니다.

1. **확인** 을 선택하여 구성을 확인합니다.

1. 확인을 완료한 후 **저장** 을 선택합니다.

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Azure Maps 연결 구성 페이지.":::

## <a name="enrichment-results"></a>보강 결과

강화 프로세스를 시작하려면 명령 모음에서.**실행** 을 선택하십시오. [예약된 새로 고침](system.md#schedule-tab)으로 시스템이 자동으로 보강을 실행하도록 할 수도 있습니다. 처리 시간은 고객 데이터의 크기와 API 응답 시간에 따라 다릅니다.

보강 프로세스가 완료되면 **내 보강** 에서 새로 보강된 고객 프로필 데이터를 검토할 수 있습니다. 또한 마지막 업데이트 시간과 강화 된 프로필 수를 확인할 수 있습니다.

**보강된 데이터 보기** 를 선택하여 각 보강된 프로필의 상세 보기에 액세스할 수 있습니다 .

## <a name="next-steps"></a>다음 단계

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>데이터 프라이버시 및 규정 준수

Azure Maps에 데이터를 전송하기 위해 Dynamics 365 Customer Insights를 활성화할 때 개인 데이터와 같이 잠재적으로 민감한 데이터를 비롯하여 Dynamics 365 Customer Insights의 준수 경계를 벗어난 데이터 전송을 허용합니다. Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 귀하는 Azure Maps가 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 해야 합니다. 자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)을 참고하십시오.
Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 보강을 언제든지 제거할 수 있습니다.

[!INCLUDE [footer-include](includes/footer-banner.md)]
