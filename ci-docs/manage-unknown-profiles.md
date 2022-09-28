---
title: Customer Insights로 알 수 없는 프로필 관리
description: Dynamics 365 Customer Insights에서 생성 및 관리되는 알 수 없는 고객 프로필로 작업합니다.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: d7e5050ee5832df5ecf40a352f7ea8d42830fa45
ms.sourcegitcommit: f6b6a4c4ce9cf12e449488b24aab80a2cbfe0c47
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/21/2022
ms.locfileid: "9556404"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Customer Insights로 알 수 없는 프로필 관리

인터넷 사용자는 온라인에서 신원이 확인되지 않고 익명인 경우가 많습니다. 다른 기기나 채널을 사용하기 때문에 로그인하지 않은 경우 가장 충성도가 높은 고객에게도 해당됩니다. 타사 쿠키가 곧 사라질 것이므로 자사 데이터를 기반으로 사용자 기본 설정을 관리하는 것은 차별화된 개인화된 경험을 달성하는 데 중요합니다. 많은 브랜드의 경우 개인화에 대한 고객의 기대치가 높아짐에도 불구하고 알려지거나 인증된 사용자는 소수에 불과합니다. 기업은 신뢰할 수 있고 상세하며 통합된 데이터를 기반으로 고객이 누구인지 아는 것이 좋습니다.

기억에 남는 개인 설정은 고객 데이터의 풍부함과 완전성에 달려 있으며 Customer Insights는 이러한 목표를 달성하는 데 도움이 됩니다. 고객 여정의 시작 부분에 수집된 데이터의 사용을 제한하거나 중지할 필요가 없습니다. Customer Insights를 사용하면 자신의 데이터를 가져와 알 수 없는 사용자에 대한 고객 프로필을 만들 수 있습니다. 그런 다음 연락처 정보가 누락된 경우에도 해당 프로필을 사용하여 추가 작업을 수행할 수 있습니다. 웹, 모바일 또는 CRM 시스템과 같은 소스의 자사 데이터를 Customer Insights로 가져와서 고객 프로필을 지속적으로 강화합니다. 더 많은 상호 작용을 통합함에 따라 [*알려지지 않은* 고객을 *알려진* 고객으로 전환](unknown-to-known.md)합니다.

## <a name="sample-scenario"></a>샘플 시나리오

전자 상거래는 지난 10년 동안 가장 빠르게 성장한 채널입니다. 사용자가 모바일 장치를 사용하여 전자 상거래 사이트를 탐색한다고 가정합니다. 웹사이트는 방문자 "mobile_guest123"을 고유 식별자로 지정하고 온라인 활동을 기반으로 행동 활동을 수집하기 시작합니다. 예: 방문한 페이지, 해당 페이지에서 보낸 시간 또는 클릭한 링크. 당신은 그들의 이름이나 이메일 주소를 모르지만 이 데이터는 브랜드에 이 특정 사용자에 대한 의미 있는 인사이트를 제공하는 데 도움이 될 수 있습니다. 결과적으로 사용자가 다음에 사이트를 방문할 때 이러한 인사이트를 사용할 수 있습니다. "mobile_guest123"에 대한 Customer Insights를 쿼리하여 "유기적", "모바일 사전 주문 고객", "고가치 고객" 등과 같은 사용자 세그먼트 목록을 검색하거나 프로필을 검색하여 개인화된 웹 경험을 생성하십시오. 데이터를 모든 활성화 시스템으로 내보내 동일한 작업을 수행할 수도 있습니다.

## <a name="prerequisites"></a>전제 조건

- 자사 데이터를 Customer Insights로 수집
- 각 엔터티에는 기본 키로 설정된 고유 ID가 있습니다
- 개인 설정을 위한 기본 키가 있는 각 엔터티가 통합됩니다
- 웹사이트의 콘텐츠 관리 시스템은 API를 사용할 수 있습니다(Customer Insights와의 직접 통신을 기반으로 하는 웹 개인 설정용)

다음 표는 가치가 높은 웹 이벤트를 캡처할 수 있는 간단한 예를 보여줍니다.

|EventID|EventTimeStamp|UserID|PrimaryKey|EventName|
|--|--|--|--|--|
|6|2022년 9월 15일 9:00:00|abc123|CookieID1|제품 보기|
|2|2022년 9월 18일 10:05:00|abc123|CookieID1|제품 보기|
|3|2022년 9월 18일 10:10:00|abc123|CookieID1|카트에 추가|
|4|2022년 9월 21일 09:05:00|abc123|CookieID1|제품 보기|

## <a name="data-ingestion"></a>데이터 수집

데이터 수집에 사용할 수 있는 옵션에 대한 자세한 내용은 [데이터 원본 개요](data-sources.md)를 참조하세요.

## <a name="data-unification"></a>데이터 통합

고객 프로필 통합에 대한 자세한 내용은 [데이터 통합 개요](data-unification.md)를 참조하세요.

## <a name="get-insights"></a>인사이트 가져오기

데이터를 [보강](enrichment-hub.md)하고 [측정값](measures.md)을 구축하며, [세그먼트](segments.md)를 생성하여 더 활성화하세요.

예를 들어, 동일한 제품 페이지를 탐색했지만 결제를 완료하지 않은 알 수 없는 사용자의 세그먼트를 만들 수 있습니다.

## <a name="activation"></a>활성화

Customer Insights의 데이터와 작업 준비가 된 인사이트를 사용하여 개인화를 위해 Customer Insights를 사용할 수 있습니다.

1. [OData API](apis.md)를 사용하여 세그먼트 멤버십 또는 고객 프로필을 검색합니다. 더 많은 예는 [Customer Insights API에 대한 OData 쿼리 예](odata-examples.md)를 참조하십시오.

1. 데이터를 활성화 시스템으로 [내보냅니다](export-destinations.md).

예: 알 수 없는 사용자가 웹사이트를 여러 번 방문하고 다양한 가죽 신발 모델의 제품 페이지를 방문합니다. Customer Insights에서 사용할 수 있는 해당 데이터를 사용하여 가죽 신발에 관심이 있는 사람들의 세그먼트에 알 수 없는 사용자를 포함할 수 있습니다. 이 세그먼트를 사용하여 재방문자를 위한 웹사이트 구축 개인 설정을 알립니다. 다음 방문에서 사이트는 알 수 없는 사용자를 인식하고 가죽 신발에 대한 10% 쿠폰을 제공할 수 있습니다.

[!INCLUDE [footer-include](includes/footer-banner.md)]
