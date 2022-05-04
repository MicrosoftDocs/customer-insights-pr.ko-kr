---
title: Microsoft의 데이터로 고객 프로필 보강
description: Microsoft의 독점 데이터를 사용하여 선호도 및 음성 점유율로 고객 데이터를 보강하세요.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
searchScope:
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 5c016a394fdf485057a190d03bfed9ce5481f435
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646810"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>선호도 및 음성 점유율(미리 보기)로 고객 프로필 보강

Microsoft의 독점 데이터를 사용하여 선호도 및 SoV(음성 점유율)로 고객 데이터를 보강하세요. 이러한 선호도 및 SoV는 고객과 유사한 인구 통계를 가진 사람들의 데이터를 기반으로 합니다. 이 정보는 특정 브랜드 및 관심 분야에 대한 고객의 선호도 또는 SoV를 기반으로 고객을 더 잘 이해하고 분류하는 데 도움이 됩니다.

**데이터** > **보강** 으로 이동하여 [보강 구성 및 보기](enrichment-hub.md)를 수행합니다.

브랜드 선호도 및 SoV 보강을 구성하려면 **검색** 탭으로 이동하고 **브랜드** 타일에서 **내 데이터 보강** 을 선택하세요.

관심사 선호도 및 SoV 보강을 구성하려면 **검색** 탭으로 이동하고 **관심사** 타일에서 **내 데이터 보강** 을 선택하세요.

   > [!div class="mx-imgBorder"]
   > ![브랜드 및 관심사 타일.](media/BrandsInterest-tile-Hub.png "브랜드 및 관심사 타일")

## <a name="how-we-determine-affinities-and-sov"></a>선호도 및 SoV를 결정하는 방법

Microsoft의 온라인 검색 데이터를 사용하여 다양한 인구 통계학적 세그먼트(나이, 성별 또는 위치로 정의됨)에서 브랜드 및 관심사에 대한 선호도 및 SoV를 찾습니다. 브랜드 또는 관심사에 대한 온라인 검색량은 선호도 또는 SoV를 결정하는 기초를 형성합니다. 그러나 각각은 고객을 이해하는 다른 관점을 제공합니다.

- 관심도는 인구 통계학적 세그먼트 간의 비교입니다. 이 정보를 사용하여 다른 세그먼트와 비교하여 주어진 브랜드 또는 관심사에 대해 가장 높은 선호도를 갖는 인구 통계학적 세그먼트를 식별할 수 있습니다.

- 음성 점유율는 선택한 브랜드 또는 관심사에 대한 비교입니다. 이 정보를 사용하여 선택한 다른 브랜드 또는 관심사와 비교하여 특정 인구 통계학적 세그먼트에 대해 가장 높은 음성 점유율을 보이는 브랜드 또는 관심사를 식별할 수 있습니다.

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

## <a name="share-of-voice-sov"></a>SoV(음성 점유율)

SoV를 100점 척도로 계산합니다. 모든 보강된 고객 프로필에 대한 모든 브랜드 또는 관심사의 총 SoV는 최대 100입니다. 선호도와 달리 SoV는 선택한 브랜드 및 관심사와 관련이 있습니다. 예를 들어 선택한 브랜드가 ('Microsoft', 'GitHub') 및 ('Microsoft', 'LinkedIn')인 경우 'Microsoft'의 SoV 값이 다를 수 있습니다.

## <a name="supported-countriesregions"></a>지원되는 국가/지역

현재 지원되는 국가/지역 옵션은 오스트레일리아, 캐나다(영어), 프랑스, 독일, 영국 또는 미국(영어)입니다.

국가 또는 지역을 선택하려면 **브랜드 보강** 또는 **관심사 보강** 을 열고 **국가/지역** 옆의 **변경** 을 선택합니다. **국가/지역 설정** 창에서 옵션을 선택하고 **적용** 을 선택합니다.

### <a name="implications-related-to-country-selection"></a>국가 선택과 관련된 시사점

- [자신의 브랜드 선택](#define-your-brands-or-interests) 시, 시스템은 선택한 국가 또는 지역을 기준으로 제안을 제공합니다.

- [산업 선택](#define-your-brands-or-interests) 시, 선택한 국가 또는 지역을 기준으로 가장 관련성이 높은 브랜드 또는 관심사를 얻을 수 있습니다.

- [프로필을 보강](#refresh-enrichment)할 때 선택한 국가 또는 지역에 없는 프로필을 포함하여 선택한 브랜드 및 관심사에 대한 데이터를 얻는 모든 고객 프로필을 보강합니다. 예를 들어 독일을 선택한 경우 선택한 브랜드 및 미국 내 관심사에 대한 데이터가 있으면 미국에 있는 프로필을 보강합니다.

## <a name="configure-enrichment"></a>보강 구성

안내식 경험은 보강 구성에 도움이 됩니다. 

### <a name="define-your-brands-or-interests"></a>브랜드 또는 관심 정의

다음 옵션 중 하나 또는 둘 다를 사용하여 최대 5개의 브랜드 또는 관심 분야를 선택하십시오.

- **업종**: 드롭다운 목록에서 업종을 선택한 다음 해당 업종의 상위 브랜드 또는 관심사에서 선택합니다.
- **자체 선택**: 조직과 관련된 브랜드 또는 관심 분야를 입력한 다음 일치하는 제안에서 선택합니다. 찾고 있는 브랜드나 관심 분야가 목록에 없는 경우 **제안** 링크를 사용하여 의견을 보내주십시오.

### <a name="review-enrichment-preferences"></a>보강 선호 설정 검토

기본 보강 선호 설정을 검토하고 필요에 따라 업데이트하십시오.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="보강 선호 설정 창의 스크린샷입니다.":::

### <a name="select-entity-to-enrich"></a>보강할 엔터티 선택

**보강된 엔터티** 를 선택하고 Microsoft의 데이터로 보강할 데이터 집합을 선택합니다. 고객 엔터티를 선택하여 모든 고객 프로필을 보강하거나 세그먼트 엔터티를 선택하여 해당 세그먼트에 포함된 고객 프로필만 보강할 수 있습니다.

### <a name="map-your-fields"></a>필드 매핑

통합 고객 엔터티의 필드를 매핑하여 시스템에서 고객 데이터를 보강하는 데 사용할 인구 통계학적 세그먼트를 정의합니다. 국가/지역 및 최소한 생년월일 또는 성별 특성을 매핑합니다. 또한 하나 이상의 구/군(및 시/도) 또는 우편 번호를 매핑해야 합니다. **편집** 을 선택하고 필드의 매핑을 정의하고 완료하면 **적용** 을 선택합니다. **저장** 필드를 선택하여 매핑을 완료합니다.

다음 형식 및 값이 지원되며 값은 대소문자를 구분하지 않습니다.

- **생년월일**: 데이터 수집 시 생년월일을 날짜/시간 형식으로 변환하는 것이 좋습니다. 또는 [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) 형식 "yyyy-MM-dd" 또는 "yyyy-MM-ddTHH:mm:ss"의 문자열일 수 있습니다.
- **성별**: 남성, 여성, 알 수 없음.
- **우편 번호**: 미국의 경우 5자리 우편 번호, 그 외 지역의 표준 우편 번호입니다.
- **도시**: 영어로 된 도시 이름.
- **시/도**: 미국 및 캐나다의 경우 두 글자 약어입니다. 호주의 경우 2~3자의 약어입니다. 프랑스, 독일 또는 영국에는 적용되지 않습니다.
- **국가/지역**:

  - US: 미합중국, 미국, USA, US
  - CA: 캐나다, CA
  - GB: 영국, UK, 그레이트브리튼, GB, 그레이트브리튼 및 북아일랜드연합왕국, 대브리튼왕국
  - AU: 오스트레일리아, AU, 오스트레일리아 연방
  - FR: 프랑스, FR, 프랑스 공화국
  - DE: 독일, 독일어, Deutschland, Allemagne, DE, 독일 연방 공화국, 독일 공화국

## <a name="review-and-name-the-enrichment"></a>보강 검토 및 이름 지정

마지막으로 정보를 검토하고 보강에 대한 이름을 제공합니다.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="관심사 검토 및 이름 지정 페이지.":::

## <a name="refresh-enrichment"></a>보강 새로 고침

인구 통계에 대한 브랜드, 관심 분야 및 필드 매핑을 구성한 후 보강을 실행합니다. 프로세스를 시작하려면 브랜드 또는 관심사 구성 페이지에서 **실행** 을 선택합니다. 또한 예약된 새로 고침의 일부로 시스템에서 자동으로 보강 기능을 실행하도록 할 수 있습니다.

고객 데이터의 크기에 따라 보강 실행이 완료되는 데 몇 분이 걸릴 수 있습니다.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>보강 결과

보강 프로세스를 실행한 후 **내 보강** 으로 이동하여 총 보강 고객 수와 보강된 고객 프로필에 대한 브랜드 또는 관심사를 분석합니다.

:::image type="content" source="media/my-enrichments.png" alt-text="보강 프로세스를 실행한 후 결과 미리 보기.":::

시간 경과에 따라 보강된 고객 프로필 수와 보강된 엔터티의 미리 보기가 포함된 차트를 찾을 수 있습니다. **선호도 수준** 또는 **음성 점유율** 차트에서 **자세히 보기** 를 선택하여 보강된 데이터를 검토합니다. 브랜드에 대한 보강된 데이터는 **BrandAffinityFromMicrosoft** 및 **BrandShareOfVoiceFromMicrosoft** 엔터티로 이동합니다. 관심 데이터는 **InterestAffinityFromMicrosoft** 및 **InterestShareOfVoiceFromMicrosoft** 엔터티에 있습니다. 이 엔터티는 **데이터** > **엔터티** 의 **보강** 그룹에 나열됩니다.

## <a name="see-enrichment-data-on-the-customer-card"></a>고객 카드의 보강 데이터 보기

브랜드 및 관심사 SoV는 개별 고객 카드에서도 볼 수 있습니다. **고객** 으로 이동하여 고객 프로필을 선택하십시오. 고객 카드에서 해당 고객의 인구 통계 프로필에 있는 사람들을 기반으로 하는 브랜드 또는 관심사 SoV에 대한 차트를 찾을 수 있습니다.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="보강된 데이터가 포함된 고객 카드.":::

## <a name="next-steps"></a>다음 단계

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
