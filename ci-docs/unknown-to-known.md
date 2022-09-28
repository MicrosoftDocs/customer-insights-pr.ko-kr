---
title: 알려진 사용자와 알 수 없는 사용자에 대한 데이터를 사용하여 경험을 개인 설정하세요.
description: 사용자의 신원을 안다면 예전 알 수 없는 사용자에 대한 정보를 통합할 수 있습니다.
ms.date: 07/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 8e3477750d82f965dc2d62174fb35554d9447b7b
ms.sourcegitcommit: 52eca81c36e93d553140f5a37cf6013aaa42623a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/03/2022
ms.locfileid: "9224303"
---
# <a name="personalize-your-experiences-with-data-about-known-and-unknown-users"></a>알려진 사용자와 알 수 없는 사용자에 대한 데이터를 사용하여 경험을 개인 설정하세요.

고객 데이터를 관리하는 것을 새로운 도전 과제라고 할 수는 없지만, 브랜드에서 제공하는 다양한 디지털 채널을 사용자가 탐색하게 됨에 따라 데이터 관리가 점차 어려워지고 있습니다. 한 채널에서 알려진 사용자(인증된)가 로그인하지 않으면 다른 채널에서는 알 수 없는 사용자(인증되지 않은)가 됩니다. 문제는 인증되지 않은 알 수 없는 사용자에게는 공통 ID가 없다는 것입니다. 이 방법은 의미 있는 프로필 특성을 연결하고 통합된 고객 프로필을 생성하는 데 사용됩니다. Customer Insights는 소스 시스템의 추적 방법에서 데이터를 수집하여 이 문제를 해결하는 데 도움이 됩니다. 알 수 없는 프로필과 알려진 프로필을 통합하면 조직에 최신 프로필과 과거 거래, 활동 및 인구 통계에 대한 전체 보기를 제공할 수 있습니다. 웹사이트, 매장 내 구매, 로열티 프로그램 등을 포함한 여러 채널에서 고객 활동을 통합할 수 있는 ID 확인 절차를 제공하여 한 단계 더 나아갈 수 있습니다.

## <a name="sample-scenario"></a>샘플 시나리오

매장에서 커피와 식품을 구매하고 온라인으로 제품을 주문하는 광범위한 고객 기반을 보유한 커피 체인에 대해 생각해 보겠습니다. 종종 온라인 방문자는 제품을 탐색할 때 인증되지 않았기 때문에 '알 수 없는 사용자'가 됩니다. 알 수 없는 사용자인 경우 커피 체인에서는 개인 설정된 서비스와 경험을 제공하기 어렵습니다. 반면에 고객이 로열티 시스템에 가입하고 자신의 계정에 로그인하면 회사에 '알려진 사용자'로 등록되며, 이를 통해 보다 개인 설정된 경험을 제공할 수 있습니다. Customer Insights는 커피 체인이 알려진 사용자 및 이전을 알 수 없는 사용자에 대한 인사이트를 얻는 데 도움이 될 수 있습니다.

Customer Insights를 통해 회사는 사용자가 로그인하고 알려진 사용자가 되게 한 다음 인증되지 않은 알 수 없는 세션의 활동 데이터를 사용해 고객 프로필과 결합할 수 있습니다. 커피 체인은 기본 제공 커넥터를 사용하여 다른 데이터 원본의 데이터를 Customer Insights로 가져와 다양한 채널의 고객 ID를 병합할 수 있습니다.

## <a name="prerequisites"></a>전제 조건

- 웹 데이터가 수집되고 모든 방문자에 대한 '방문자 ID'가 포함됩니다.
- 웹 데이터에는 로그인한 방문자에 대한 '인증된 사용자 ID'가 포함되어 있습니다. 이 ID는 로열티 시스템과 연결됩니다.
- '제품 보기' 및 '구매하기'와 같은 가치가 높은 이벤트 데이터는 이벤트의 타임스탬프 및 이벤트 ID와 함께 소스 데이터에 정의되고 포함됩니다.

다음 표는 가치가 높은 웹 이벤트를 캡처할 수 있는 간단한 예를 보여줍니다.

|EventID|EventTimeStamp|UserID|LoyaltyID|EventName|
|--|--|--|--|--|
|6|07-23-2022 10:00:00|abc123|--|제품 보기|
|2|07-23-2022 10:05:00|abc123|707|로열티에 로그인하기|
|3|07-23-2022 10:10:00|abc123|707|확인|
|4|07-23-2022 10:20:00|xyz789|--|제품 보기|

## <a name="data-ingestion"></a>데이터 수집

고객에 대한 데이터는 웹사이트에서 이벤트 데이터로 생성될 수 있으며 자체 내부 또는 타사 데이터 분석 서비스에 저장할 수 있습니다. 웹 사이트에 인증 서비스와 통합되는 인증 흐름이 있는 경우 웹 데이터에는 알려진 사용자와 알 수 없는 사용자가 포함됩니다. 사용자가 구매 거래를 완료할 수 있게 전체 세부 정보를 제공하는 eCommerce 시스템을 예로 들 수 있습니다. 또는 보상 할인을 적용 받을 유효한 수령인을 확인하기 위해 인증이 필요한 로열티 시스템도 있습니다.

위 이벤트 데이터에 대한 예시에는 알려진 사용자와 알 수 없는 사용자의 고유한 프로필 ID가 포함되어 있습니다. 이벤트 1과 4에서는 알 수 없는 사용자이지만 이벤트 2와 3에서는 ID가 abc123인 사용자가 로열티 프로그램에 가입합니다.

:::image type="content" source="media/website-data-source.png" alt-text="Contoso 웹 사이트를 포함한 데이터 원본.":::

데이터 수집에 사용할 수 있는 옵션에 대한 자세한 내용은 [데이터 원본 개요](data-sources.md)를 참조하세요.

## <a name="data-unification"></a>데이터 통합

알 수 없는 ID를 알려진 ID와 합치면 프로필 상태(알려진 또는 알 수 없는 사용자)와 관계없이 사용자 행동을 기반으로 개인 설정을 할 수 있습니다. 모든 사용자용으로 개인 설정된 콘텐츠는 고객이 그 순간에 관심이 있는 가장 관련성 높은 제품 또는 서비스에 신속하게 도달할 수 있도록 도와줍니다.

데이터에 있는 일부 사용자가 알려진 사용자이므로 Customer Insights를 사용하여 해당 데이터를 사용자 프로필과 결합할 수 있습니다. 고객 프로필 통합에 대한 자세한 내용은 [데이터 통합 개요](data-unification.md)를 참조하세요.

1. 웹 데이터 엔터티에서 원본 필드를 선택합니다. 웹 데이터에 저장된 프로필 데이터를 사용하고 인구 통계 데이터를 사용하여 ID를 나타내는 필드를 선택합니다.

   :::image type="content" source="media/website-source-fields.png" alt-text="웹 데이터 원본용 소스 필드.":::

1. 중복 레코드를 병합하는 규칙을 추가합니다. 웹 데이터의 경우 가장 많이 채워진 데이터를 선택합니다.

1. 일치 규칙 및 조건을 구성합니다. 이 예에서 웹 프로필 이벤트 데이터는 ID에서 고객 정보가 포함된 다른 데이터 원본의 프로필과 일치합니다. 해당 기본 키 또는 ID 일치가 있는 다른 프로필의 각 엔터티와 별도의 규칙으로 ID와 일치하는 정확한 규칙을 설정합니다. 이 예에서는 웹 이벤트 프로필 데이터를 마지막으로 일치하는 엔터티로 사용하므로 다른 프로필 데이터가 먼저 결합됩니다.
   1. **모든 레코드 포함** 을 확인하지 않음: 알려진 사용자에 대한 통합 프로필을 만들고 해당하는 알 수 없는 사용자 ID를 포함합니다. 알려진 사용자가 아직 알 수 없는 사용자였던 시점의 과거 행동 활동을 보는 데 관심이 있는 시나리오에서 유용합니다.
   1. **모든 레코드 포함** 을 확인 중: 알 수 없는 사용자에 대해 별도의 프로필 레코드를 생성합니다. 알 수 없는 사용자에게 고유 고객 ID가 부여됩니다. 향후 알려진 프로필이 웹 이벤트 프로필 데이터와 연결되면 새로 알려진 사용자의 여정을 보고 알 수 없는 사용자의 과거 행동 데이터를 기반으로 한 개인 설정에 사용할 수 있습니다.

:::image type="content" source="media/website-match-rule.png" alt-text="웹사이트 데이터 원본 엔터티에 대한 규칙 일치.":::

## <a name="get-insights"></a>인사이트 가져오기

알 수 없는 사용자 및 알려진 사용자에 대한 고객 프로필이 생성되면 가치가 높은 웹 이벤트 데이터를 [활동](activities.md)으로 사용할 수 있습니다. 이러한 활동을 사용하여 더 유용한 인사이트를 얻을 수 있습니다. 예를 들어, 6개월 전에 웹사이트를 방문한 고객(아직 알 수 없는 사용자인 경우) 또는 로열티 ID가 없는 고객은 결제를 완료하지 않았습니다.

:::image type="content" source="media/website-known-unknown.png" alt-text="알려진 고객과 알 수 없는 고객의 경우 고객 페이지를 보여주는 스크린샷.":::

데이터를 [보강](enrichment-hub.md)하고 [측정값](measures.md)을 구축하며, [세그먼트](segments.md)를 생성하여 더 활성화하세요.

예를 들어, 일부 제품을 보았지만 결제는 완료하지 않은 알려진 사용자의 세그먼트를 만들 수 있습니다.

자세한 내용은 [세그먼트 개요](segments.md)에서 확인하세요.

## <a name="activate-insights"></a>인사이트 활성화하기

데이터를 내보내고 기본 인사이트를 토대로 작업하는 방법에는 여러 가지가 있습니다.

자세한 내용은 [내보내기 개요](export-destinations.md)를 참조하세요.