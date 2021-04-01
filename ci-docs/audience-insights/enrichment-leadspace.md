---
title: 타사 보강 Leadspace를 사용하여 회사 프로필 보강
description: Leadspace 타사 보강에 대한 일반 정보입니다.
ms.date: 11/24/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 41c56aece043c2d7658fd2655713e1e98775edec
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597657"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Leadspace를 통한 회사 프로필 강화(미리 보기)

Leadspace는 B2B 고객 데이터 플랫폼을 제공하는 데이터 과학 회사입니다. 통합된 고객 프로필을 보유한 고객이 회사의 데이터를 보강할 수 있습니다. 보강에는 회사 규모, 위치, 산업 등과 같은 추가 특성이 포함됩니다.

## <a name="prerequisites"></a>필수 구성 요소

Leadspace를 구성하려면 다음 전제 조건이 충족되어야 합니다.

- 활성 Leadspace 라이선스와 "영구 키"(**Leadspace 토큰** 이라고 함)가 있습니다. 그들의 제품에 대한 자세한 내용은 [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/)에 직접 문의하세요.
- [관리자](permissions.md#administrator) 권한이 있어야 합니다.
- 회사의 [통합 고객 프로필](customer-profiles.md)을 갖고 있습니다.

## <a name="configuration"></a>구성

1. 대상 그룹 인사이트에서 **데이터** > **보강** 으로 이동합니다.

1. Leadspace 타일에서 **내 데이터 보강** 을 선택합니다.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace 타일의 스크린샷.":::

1. **시작** 을 선택한 후 활성 **Leadspace 토큰**(영구 키)을 입력합니다. **동의함** 확인란을 선택하여 **데이터 개인 정보 및 규정 준수** 에 대한 동의를 검토하고 제공합니다. **Leadspace에 연결** 을 선택하여 입력을 둘 다 확인합니다.

1. **데이터 매핑** 을 선택하고 Leadspace에서 회사 데이터를 통해 보강하려는 데이터 집합을 선택합니다. *고객* 엔터티를 선택하여 모든 고객 프로필을 보강하거나 세그먼트 엔터티를 선택하여 해당 세그먼트에 포함된 고객 프로필만 보강할 수 있습니다.

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="고객 프로필과 세그먼트 보강 중에서 선택합니다.":::

1. **다음** 을 클릭하고 Leadspace에서 일치하는 회사 데이터를 찾는 데 사용해야 하는 통합 프로필의 필드를 정의합니다. **회사의 이름** 필드는 필수입니다. 일치 정확도를 높이기 위해 **회사 웹 사이트** 및 **회사 위치** 라는 다른 필드를 최대 2개까지 추가할 수 있습니다.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace 필드 매핑 창.":::
   
1. **적용** 을 선택하여 필드 매핑을 완료합니다.

1. **실행** 을 선택하여 회사 프로필을 보강합니다. 보강에 걸리는 시간은 통합 고객 프로필의 수에 따라 다릅니다.

## <a name="enrichment-results"></a>보강 결과

보강을 새로 고친 후 [내 보강](enrichment-hub.md) 아래에서 새로 보강된 회사 데이터를 검토할 수 있습니다. 마지막 업데이트 시간과 보강된 프로필 수를 찾을 수 있습니다.

**보강된 데이터 보기** 를 선택하여 각 보강된 프로필의 상세 보기에 액세스할 수 있습니다 .

자세한 내용은 [Leadspace API](https://support.leadspace.com/hc/en-us/sections/201997649-API)를 참조하십시오.

## <a name="next-steps"></a>다음 단계

보강된 고객 데이터를 바탕으로 구축합니다. [세그먼트](segments.md)를 만들고, [측정](measures.md)하고, 또한 [데이터를 내보내](export-destinations.md) 고객에게 맞춤형 경험을 제공합니다.

## <a name="data-privacy-and-compliance"></a>데이터 프라이버시 및 규정 준수

Dynamics 365 Customer Insights를 사용하여 Leadspace로 데이터를 전송하는 경우 Dynamics 365 Customer Insights 규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다. Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 Leadspace가 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다. 자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.
Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 보강을 언제든지 제거할 수 있습니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]