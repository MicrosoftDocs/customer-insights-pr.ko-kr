---
title: LiveRamp ID 데이터 보강
description: LiveRamp 데이터로 고객 프로필을 보강합니다.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ee65cb49447df61dd5c298a84ad21bc119ead558
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8373022"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>LiveRamp의 ID 데이터로 고객 프로필 보강(프리뷰) 

LiveRamp는 결정적 오프라인 ID 확인 및 고객 데이터 통합을 제공합니다. 고객 데이터의 개인 식별자를 AbiliTec ID 그래프에 매핑하고 AbiliTec ID를 받을 수 있습니다. 그런 다음 이 ID를 사용하여 고객 데이터를 더 잘 통합할 수 있습니다. 

## <a name="prerequisites"></a>전제 조건 

보강을 구성하려면 다음 전제 조건이 충족되어야 합니다. 

- 활성 LiveRamp 구독이 있어야 합니다. 구독하려면 LiveRamp 계정 팀이나 [dynamics@liveramp.com](mailto:dynamics@liveramp.com)에 자세한 내용을 문의하세요.   

- API에 액세스하기 위한 클라이언트 ID 및 암호가 있는 활성 AbiliTec 구독입니다. 자세한 내용은 [AbiliTec API 개발자 허브](https://developers.liveramp.com/abilitec-api/)를 참조하세요. 

## <a name="supported-countriesregions"></a>지원되는 국가/지역 

LiveRamp 데이터로 고객 프로필 보강은 현재 미국에서만 지원됩니다. 

## <a name="configure-the-enrichment"></a>보강 구성 

1. **데이터** > **보강** 으로 이동 후, **발견하기** 탭을 선택합니다. 

1. **ID** 타일에서 **내 데이터 보강** 을 선택합니다. 

   :::image type="content" source="media/liveramp-tile.png" alt-text="보강 개요 페이지의 ID 타일입니다. ":::

1. 드롭다운 목록에서 [연결](connections.md)을 선택하십시오. 사용 가능한 연결이 없으면 관리자에게 문의하십시오. 관리자인 경우 **연결 추가** 를 선택하여 연결을 만들 수 있습니다. 드롭다운 목록에서 **LiveRamp** 를 선택합니다. 

1. **다음** 을 선택하고 LiveRamp의 ID 데이터로 보강하려는 **고객 데이터 세트** 를 선택합니다. *고객* 엔터티를 선택하여 모든 고객 프로필을 보강하거나 *세그먼트* 엔터티를 선택하여 해당 세그먼트에 포함된 고객 프로필만 보강할 수 있습니다. 

1. **다음** 을 선택하고 LiveRamp에서 일치하는 ID 데이터를 찾는 데 사용해야 하는 통합 프로필의 필드 유형을 정의합니다. **이름 및 주소**, **전화** 또는 **이메일** 필드 중 하나 이상이 필수입니다. 

   > [!TIP]
   > 매핑하는 주요 식별자와 필드가 많을수록 일치율이 높아질 가능성이 높아집니다. 

1. LiveRamp의 AbiliTec ID 그래프와 일치하는 데 사용할 통합 *고객* 엔터티의 필드를 매핑합니다. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="LiveRamp 보강을 위한 데이터 매핑 옵션입니다.":::

1. 필드 매핑을 완료하려면 **다음** 을 선택합니다. 

1. 보강 및 **출력 엔터티** 의 **이름** 을 제공합니다. 

1. 선택 사항을 검토 한 후 **보강 저장** 을 선택합니다. 

## <a name="configure-the-connection-for-liveramp"></a>LiveRamp에 대한 연결 구성 

[연결을 구성](connections.md)하려면 관리자여야 합니다. 보강을 구성할 때 **연결 추가** 를 선택하거나 **관리** > **연결** 로 이동하여 **LiveRamp** 타일에서 **설정** 을 선택합니다. 

:::image type="content" source="media/liveramp-connection.png" alt-text="LiveRamp AbiliTec 서비스에 대한 연결을 설정하는 구성 창입니다.":::

1. **표시 이름** 에 연결의 이름을 입력합니다. 

1. 유효한 LiveRamp 클라이언트 ID와 암호를 제공하세요. 

1. **동의함** 확인란을 선택하여 **데이터 개인 정보 및 규정 준수** 에 대한 동의를 검토하고 제공합니다. 

1. **확인** 을 선택하여 구성을 확인합니다. 

1. 연결을 완료하려면 **저장** 을 선택합니다. 

## <a name="enrichment-results"></a>보강 결과 

보강 프로세스를 시작하려면 명령 모음에서 실행 을 선택합니다. 또한 [예약된 새로 고침](system.md#schedule-tab)의 일부로 시스템이 보강을 자동으로 실행하도록 할 수 있습니다. 처리 시간은 고객 데이터의 크기에 따라 다릅니다. 

보강 프로세스가 완료되면 **내 보강** 아래에서 새로 보강된 고객 프로필 데이터를 검토할 수 있습니다. 또한 마지막 업데이트 시간과 강화 된 프로필 수를 확인할 수 있습니다. 

 **보강된 데이터 보기** 를 선택하여 각 보강된 프로필의 상세 보기에 액세스할 수 있습니다. 

## <a name="next-steps"></a>다음 단계

보강된 고객 데이터를 바탕으로 구축합니다. AbiliTec ID를 사용하여 고객 프로필을 개인 기반 보기로 통합합니다. 
[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>데이터 프라이버시 및 규정 준수 

Dynamics 365 Customer Insights에서 LiveRamp로 데이터를 전송하도록 설정하면 개인 데이터와 같이 잠재적으로 민감한 데이터를 포함하여 Dynamics 365 Customer Insights의 규정 준수 경계 외부로 데이터를 전송할 수 있습니다. Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 귀하는 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 LiveRamp가 충족하는지 확인할 책임이 있습니다. 자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)을 검토하세요. Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 보강을 언제든지 제거할 수 있습니다. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
