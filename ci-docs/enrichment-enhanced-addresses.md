---
title: 향상된 주소로 고객 프로필 강화(비디오 포함)
description: Microsoft 모델을 사용하여 고객 프로필의 주소 정보를 보강하고 정규화합니다.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
searchScope:
- ci-data-sources-enrichment
- ci-data-sources-enrichment-details
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 01f1c917c75e932cc69f4c7251e57524fc859dce
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081227"
---
# <a name="enrich-customer-profiles-with-enhanced-addresses"></a>향상된 주소로 고객 프로필 강화

데이터의 주소는 구조화되지 않았거나 불완전하거나 부정확할 수 있습니다. Microsoft의 모델을 사용하여 [공통 데이터 모델 형식](/common-data-model/schema/core/applicationcommon/address)으로 정규화하고 보강하여 더 나은 정확성과 인사이트를 얻으십시오.

데이터 통합 프로세스에서 일치 정확도를 향상하기 위해 [데이터 원본의 주소를 보강](data-sources-enrichment.md)할 수도 있습니다. 

## <a name="how-we-enhance-addresses"></a>주소 향상 방법

당사 모델은 주소를 향상하기 위해 2단계 프로세스를 거칩니다. 먼저 주소를 구문 분석하여 구성 요소를 식별하고 구조화된 형식에 넣습니다. 그런 다음 AI를 사용하여 주소의 값을 수정, 완성 및 표준화합니다.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWNewo]

### <a name="example"></a>예제

주소 정보는 비표준 형식이며 맞춤법 오류가 있을 수 있습니다. 이 모델은 이러한 문제를 해결하고 통합 고객 프로필에서 일관된 주소를 생성할 수 있습니다.

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a>제한 사항

향상된 주소는 수집된 주소 데이터에 이미 존재하는 값에서만 작동합니다. 모델은 다음을 수행하지 않습니다.

1. 주소가 유효한 주소인지 확인.
2. 우편 번호 또는 거리 이름과 같은 값이 유효한지 확인.
3. 인식하지 못하는 값을 변경.

이 모델은 기계 학습 기반 기술을 사용하여 주소를 향상시킵니다. 모든 기계 학습 기반 모델과 마찬가지로 100% 정확도는 보장되지 않습니다.

## <a name="supported-countries-or-regions"></a>지원되는 국가 또는 지역

현재 다음 국가 또는 지역에서 주소 보강을 지원합니다.

- 오스트레일리아
- 캐나다
- 프랑스
- 독일
- 이탈리아
- 일본
- 영국
- 미국

## <a name="configure-the-enrichment"></a>보강 구성

1. **데이터** > **보강** 으로 이동 후, **발견하기** 탭을 선택합니다.

1. **향상된 주소** 타일에서 **내 데이터 보강** 을 선택합니다.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="향상된 주소 타일의 스크린샷.":::

1. 개요를 검토한 후 **다음** 을 선택합니다.

1. **고객 데이터 세트** 를 선택하고 보강할 프로필 또는 세그먼트를 선택합니다. *고객* 엔터티는 모든 고객 프로필을 강화하는 반면 세그먼트는 해당 세그먼트에 포함된 고객 프로필만 강화합니다.

1. 데이터 집합에서 사용할 주소 형식을 선택합니다. 데이터의 주소가 단일 필드를 사용하는 경우 **단일 특성 주소** 를 선택합니다. 데이터의 주소가 둘 이상의 데이터 필드를 사용하는 경우 **다중 특성 주소** 를 선택합니다.

1. **다음** 을 선택하고 통합 고객 엔터티의 주소 필드를 매핑합니다.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="향상된 주소 필드 매핑 페이지.":::

   > [!NOTE]
   > 국가/지역은 단일 특성 및 다중 특성 주소 모두에서 필수입니다. 유효하거나 지원되는 국가/지역 값이 포함되지 않은 주소는 보강되지 않습니다.

1. 필드 매핑을 완료하려면 **다음** 을 선택합니다.

1. 보강 및 **출력 엔터티** 의 **이름** 을 제공합니다.

1. 선택 사항을 검토 한 후 **보강 저장** 을 선택합니다.

## <a name="view-enrichment-results"></a>강화 결과 보기

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**필드로 보강된 고객 수** 는 각 보강된 필드의 적용 범위에 대한 드릴다운을 제공합니다.

### <a name="overview-card"></a>개요 카드

**고객 변경 개요** 카드에는 강화 적용 범위에 대한 세부 정보가 표시됩니다.

- **처리 및 변경된 주소**: 성공적으로 보강된 주소가 있는 고객 프로필의 수입니다.
- **처리되고 변경되지 않은 주소**: 인식되었지만 변경되지 않은 주소가 있는 고객 프로필의 수입니다. 일반적으로 입력 데이터가 유효하고 보강으로 개선할 수 없는 경우에 발생합니다.
- **처리되지 않고 변경되지 않은 주소**: 인식되지 않은 주소가 있는 프로필의 수입니다. 일반적으로 유효하지 않거나 보강되지 않는 입력 데이터를 의미합니다.

## <a name="next-steps"></a>다음 단계

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
