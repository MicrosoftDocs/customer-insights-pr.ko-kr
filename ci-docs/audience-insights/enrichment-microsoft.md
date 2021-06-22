---
title: Microsoft의 데이터로 고객 프로필 보강
description: Microsoft의 독점 데이터를 사용하여 브랜드 및 관심사와 함께 고객 데이터를 보강하십시오.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e92360bb886739cfe477ce1d2eb62219228a0292
ms.sourcegitcommit: d4b4053f6ee8f60f1a214982c4726c9de84615ef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2021
ms.locfileid: "6245715"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>브랜드 및 관심 관계로 풍부한 고객 프로필 강화(미리 보기)

Microsoft의 독점 데이터를 사용하여 브랜드 및 관심사와 함께 고객 데이터를 보강하십시오. 이러한 선호도는 인구 통계가 비슷한 사람들과 고객의 데이터를 기반으로 결정됩니다. 이 정보는 고객을 특정 브랜드 및 관심사에 대한 선호도에 따라 더 잘 이해하고 분류할 수 있도록 도와줍니다.

대상 그룹 인사이트에서 **데이터** > **보강** 으로 이동하여 [보강 구성 및 보기](enrichment-hub.md)를 수행합니다.

브랜드 관심 보강을 구성하려면 **검색** 탭으로 이동하고 **브랜드** 타일에서 **내 데이터 보강** 을 선택합니다.

관심 관계 보강을 구성하려면 **검색** 탭으로 이동하고 **관심** 타일에서 **내 데이터 보강** 을 선택합니다.

   > [!div class="mx-imgBorder"]
   > ![브랜드 및 관심사 타일](media/BrandsInterest-tile-Hub.png "브랜드 및 관심사 타일")

## <a name="how-we-determine-affinities"></a>친화도를 결정하는 방법

Microsoft의 온라인 검색 데이터를 사용하여 다양한 인구 통계 세그먼트(연령, 성별 또는 위치로 정의됨)에서 브랜드 및 관심사에 대한 선호도를 찾습니다. 브랜드나 관심 분야에 대한 온라인 검색 양에 따라 인구 통계학적 세그먼트가 다른 세그먼트와 비교하여 해당 브랜드나 관심 분야에 얼마나 많은 유사성이 있는지가 결정됩니다.

## <a name="affinity-level-and-score"></a>선호도 수준 및 점수

보강된 모든 고객 프로필에 대해 두 가지 관련 값, 즉 선호도 수준과 선호도 점수를 제공합니다. 이러한 값은 다른 인구 통계 세그먼트와 비교하여 해당 프로필의 인구 통계 세그먼트, 브랜드 또는 관심 분야에 대한 선호도가 얼마나 강한지 결정하는 데 도움이 됩니다.

*선호도 수준* 은 4개의 수준으로 구성되며 *선호도 점수* 는 선호도 수준에 매핑되는 100점 척도로 계산됩니다.


|선호도 수준 |선호도 점수  |
|---------|---------|
|매우 높음     | 85-100       |
|높음     | 70-84        |
|중간     | 35-69        |
|낮음     | 1-34        |

선호도를 측정하기 위해 원하는 세분성에 따라 선호도 수준 또는 점수를 사용할 수 있습니다. 선호도 점수를 사용하면 더 정확한 제어가 가능합니다.

## <a name="supported-countriesregions"></a>지원되는 국가/지역

현재 지원되는 국가/지역 옵션은 오스트레일리아, 캐나다(영어), 프랑스, 독일, 영국 또는 미국(영어)입니다.

국가를 선택하려면 **브랜드 보강** 또는 **관심사 보강** 을 열고 **국가/지역** 옆에 있는 **변경** 을 선택합니다. **국가/지역 설정** 창에서 옵션을 선택하고 **적용** 을 선택합니다.

### <a name="implications-related-to-country-selection"></a>국가 선택과 관련된 시사점

- [자신의 브랜드 선택](#define-your-brands-or-interests) 시, 시스템은 선택한 국가 또는 지역을 기준으로 제안을 제공합니다.

- [산업 선택](#define-your-brands-or-interests) 시, 선택한 국가 또는 지역을 기준으로 가장 관련성이 높은 브랜드 또는 관심사를 얻을 수 있습니다.

- [프로필 보강](#refresh-enrichment) 시, 선택한 브랜드 및 관심사에 대한 데이터를 얻을 수 있는 모든 고객 프로필을 보강합니다. 선택한 국가 또는 지역에 없는 프로필을 포함합니다. 예를 들어 독일을 선택한 경우 선택한 브랜드 및 미국 내 관심사에 대한 데이터가 있으면 미국에 있는 프로필을 보강합니다.

## <a name="configure-enrichment"></a>보강 구성

안내식 경험은 보강 구성에 도움이 됩니다. 

### <a name="define-your-brands-or-interests"></a>브랜드 또는 관심 정의

다음 옵션 중 하나 또는 둘 다를 사용하여 최대 5개의 브랜드 또는 관심 분야를 선택하십시오.

- **산업**: 드롭다운 목록에서 산업을 선택한 다음 해당 산업의 상위 브랜드 또는 관심 분야에서 선택합니다.
- **자체 선택**: 조직과 관련된 브랜드 또는 관심 분야를 입력한 다음 일치하는 제안에서 선택합니다. 찾고 있는 브랜드나 관심 분야가 목록에 없는 경우 **제안** 링크를 사용하여 의견을 보내주십시오.

### <a name="review-enrichment-preferences"></a>보강 선호 설정 검토

기본 보강 선호 설정을 검토하고 필요에 따라 업데이트하십시오.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="보강 선호 설정 창의 스크린샷입니다.":::

### <a name="select-entity-to-enrich"></a>보강할 엔터티 선택

**보강된 엔터티** 를 선택하고 Microsoft의 회사 데이터로 보강할 데이터 집합을 선택합니다. 고객 엔터티를 선택하여 모든 고객 프로필을 보강하거나 세그먼트 엔터티를 선택하여 해당 세그먼트에 포함된 고객 프로필만 보강할 수 있습니다.

### <a name="map-your-fields"></a>필드 매핑

통합 고객 엔터티의 필드를 매핑하여 시스템에서 고객 데이터를 보강하는 데 사용할 인구 통계학적 세그먼트를 정의합니다. 국가/지역 및 최소한 생년월일 또는 성별 특성을 매핑합니다. 또한 하나 이상의 구/군(및 시/도) 또는 우편 번호를 매핑해야 합니다. **편집** 을 선택하고 필드의 매핑을 정의하고 완료하면 **적용** 을 선택합니다. **저장** 필드를 선택하여 매핑을 완료합니다.

다음 형식 및 값이 지원되며 값은 대소문자를 구분하지 않습니다.

- **생년월일**: 데이터 수집 시 생년월일을 날짜/시간 형식으로 변환하는 것이 좋습니다. 또는 [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html)의 "yyyy-MM-dd" 또는 "yyyy-MM-ddTHH:mm:ssZ" 형식의 문자열이 될 수 있습니다.
- **성별**: 남성, 여성, 알 수 없음
- **우편 번호**: 미국의 경우 5자리 우편 번호, 기타 모든 국가의 표준 우편 번호
- **도시**: 영어로 된 도시 이름
- **시/도**: 미국 및 캐나다의 경우 두 글자 약어입니다. 호주의 경우 2~3자의 약어입니다. 프랑스, 독일 또는 영국에는 적용되지 않습니다.
- **국가/지역**:

  - US: 미합중국, 미국, USA, US
  - CA: 캐나다, CA
  - GB: 영국, UK, 그레이트브리튼, GB, 그레이트브리튼 및 북아일랜드연합왕국, 대브리튼왕국
  - AU: 호주, 오스트레일리아, AU, 오스트레일리아연방
  - FR: 프랑스, FR, 프랑스 공화국
  - DE: 독일, 독일어, Deutschland, Allemagne, DE, 독일 연방 공화국, 독일 공화국

## <a name="review-and-name-the-enrichment"></a>보강 검토 및 이름 지정

마지막으로 정보를 검토하고 보강에 대한 이름을 제공합니다.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="관심사 검토 및 이름 지정 페이지.":::

## <a name="refresh-enrichment"></a>보강 새로 고침

인구 통계에 대한 브랜드, 관심 분야 및 필드 매핑을 구성한 후 보강을 실행합니다. 프로세스를 시작하려면 브랜드 또는 관심사 구성 페이지에서 **실행** 을 선택합니다. 또한 예약된 새로 고침의 일부로 시스템에서 자동으로 보강 기능을 실행하도록 할 수 있습니다.
고객 데이터의 크기에 따라 보강 실행이 완료되는 데 몇 분이 걸릴 수 있습니다.

> [!TIP]
> 작업/프로세스 [상태에는 6가지 유형](system.md#status-types)이 있습니다. 또한 대부분의 프로세스는 [다른 다운스트림 프로세스에 의존](system.md#refresh-policies)합니다. 프로세스 상태를 선택하여 전체 작업의 진행률에 대한 세부 사항을 볼 수 있습니다. 작업 중 하나를 선택한 다음 **자세히 보기** 참조를 선택하면, 처리 시간, 마지막 처리 날짜, 작업과 관련된 모든 오류 및 경고와 같은 추가 정보를 확인할 수 있습니다.

## <a name="enrichment-results"></a>보강 결과

보강 프로세스를 실행한 후 **내 보강** 으로 이동하여 총 보강 고객 수와 보강된 고객 프로필에 대한 브랜드 또는 관심사를 분석합니다.

:::image type="content" source="media/my-enrichments.png" alt-text="보강 프로세스를 실행한 후 결과 미리 보기":::

차트에서 **보강된 데이터 보기** 를 선택하여 풍부한 데이터를 검토합니다. 브랜드에 대한 보강 데이터는 **BrandAffinityFromMicrosoft** 엔터티로 이동합니다. 관심 분야에 대한 데이터는 **InterestAffinityFromMicrosoft** 엔터티에 있습니다. 이 엔터티는 **데이터** > **엔터티** 의 **보강** 그룹에 나열됩니다.

## <a name="see-enrichment-data-on-the-customer-card"></a>고객 카드의 보강 데이터 보기

개별 고객 카드에서 브랜드 및 관심 선호도를 볼 수도 있습니다. **고객** 으로 이동하여 고객 프로필을 선택하십시오. 고객 카드에는 해당 고객의 인구 통계학적 프로필에 있는 사람들이 선호하는 브랜드 또는 관심사에 대한 차트가 있습니다.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="보강된 데이터가 포함된 고객 카드":::

## <a name="next-steps"></a>다음 단계

보강된 고객 데이터를 바탕으로 구축합니다. [세그먼트](segments.md)를 만들고, [측정](measures.md)하고, 심지어 [데이터를 내보내](export-destinations.md) 고객에게 맞춤형 경험을 제공합니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
