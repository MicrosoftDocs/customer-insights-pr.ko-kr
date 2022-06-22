---
title: 회사 데이터 개선
description: Microsoft의 모델을 사용하여 회사 데이터를 보강하고 정규화하십시오.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4247d59806468907d93fc7848231ec5a2985580e
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953957"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>개선된 회사 데이터로 회사 프로필 보강

Microsoft의 모델과 컴파일된 회사 데이터를 사용하여 회사 프로필을 수정, 보완 및 표준화하십시오. 정확성과 인사이트를 높이기 위해 [Common Data Model 형식](/common-data-model/schema/core/applicationcommon/account)을 사용합니다.

데이터 통합 프로세스에서 일치 정확도를 향상하기 위해 [데이터 원본의 회사 데이터를 개선](data-sources-enrichment.md)할 수도 있습니다.

미국 상장 기업의 경우 수익, 주식 시세표, 산업 등의 정보를 사용할 수 있습니다.  

## <a name="how-we-enhance-company-data"></a>회사 데이터를 개선하는 방법

우리 모델은 회사 프로필을 강화하기 위해 2단계 프로세스를 거칩니다. 첫째, 회사명을 정상화합니다. 예를 들어 *Microsft Corp* 은 *Microsoft Corporation* 으로 수정 및 표준화됩니다. Microsoft의 컴파일된 회사 데이터에서 일치하는 항목을 찾으려고 합니다. 일치하는 항목이 발견되면 회사 이름을 포함하여 수집된 회사 데이터의 정보로 회사 프로필을 보강합니다.

### <a name="example"></a>예제

회사 정보가 표준화된 형식을 따르지 않고 철자 오류가 있을 수 있습니다. 모델은 이러한 문제를 해결하고 일관된 정보를 생성하려고 합니다.

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>제한 사항

모델은 다음을 수행하지 않습니다.

- 회사의 ID를 확인합니다. 입력이 기존 조직인지 또는 회사가 출력을 표준 이름으로 사용하는지 확인하지 않습니다.
- 전 세계 기업을 포괄적으로 다룹니다. Microsoft의 편집된 회사 데이터는 전 세계적으로 적용되지만 호주, 캐나다, 영국 및 미국에서 대부분의 적용 범위를 제공합니다.
- 회사 주소를 전역적으로 표준화합니다. 현재 오스트레일리아, 캐나다, 프랑스, 독일, 이탈리아, 일본, 영국 및 미국과 같은 국가 또는 지역에서 주소 표준화를 지원합니다.
- 데이터의 정확성 또는 최신성을 보장합니다. 비즈니스 정보는 자주 변경되므로 제공되는 향상된 회사 데이터가 항상 정확하거나 최신 상태임을 보장할 수 없습니다.

## <a name="configure-the-enrichment"></a>보강 구성

1. **데이터** > **보강** 으로 이동 후, **발견하기** 탭을 선택합니다.

1. **개선된 회사 데이터** 타일에서 **내 데이터 보강** 을 선택합니다.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="회사 데이터에 대한 보강 허브의 보강 타일입니다.":::

1. 개요를 검토한 후 **다음** 을 선택합니다.

1. **고객 데이터 세트** 를 선택하고 보강할 프로필 또는 세그먼트를 선택합니다. *고객* 엔터티는 모든 고객 프로필을 강화하는 반면 세그먼트는 해당 세그먼트에 포함된 고객 프로필만 강화합니다.

1. 회사 프로필에서 Microsoft의 컴파일된 회사 데이터와 일치시키는 데 사용하는 필드 유형을 선택합니다. 이 선택은 다음 단계에서 액세스할 수 있는 매핑 필드에 영향을 줍니다.

1. **다음** 을 선택합니다.

1. Microsoft의 회사 데이터에 회사 필드를 매핑합니다. 더 높은 일치 정확도를 위해 더 많은 필드를 추가하세요.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="회사 보강을 구성할 때 데이터 매핑 단계입니다.":::

1. 필드 매핑을 완료하려면 **다음** 을 선택합니다.

1. 보강 및 **출력 엔터티** 의 **이름** 을 제공합니다.

1. 선택 사항을 검토 한 후 **보강 저장** 을 선택합니다.

1. **실행** 을 선택하여 강화 프로세스를 시작하거나 닫기를 선택하여 **강화** 페이지로 돌아갑니다.

## <a name="enrichment-results"></a>보강 결과

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

### <a name="overview-card"></a>개요 카드

**고객 변경 개요** 타일에는 강화 적용 범위에 대한 세부 정보가 표시됩니다.

- **처리 및 변경된 회사**: 성공적으로 보강된 고객 회사 프로필의 수입니다.
- **처리되고 변경되지 않은 회사**: 인식되었지만 변경되지 않은 고객 회사 프로필의 수입니다. 이는 일반적으로 입력 데이터가 유효하고 보강으로 개선할 수 없는 경우에 발생합니다.
- **처리되지 않고 변경되지 않은 회사**: 인식되지 않은 고객 회사 프로필의 수입니다. 이는 일반적으로 유효하지 않거나 보강되지 않는 입력 데이터가 있는 경우 발생합니다.

## <a name="next-steps"></a>다음 단계

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
