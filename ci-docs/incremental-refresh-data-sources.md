---
title: Power Query 및 Azure Data Lake 데이터 원본에 대한 증분 새로 고침
description: Power Query 또는 Azure 데이터 레이크 데이터 원본을 기반으로 하는 대규모 데이터 원본의 새 데이터 및 업데이트된 데이터를 새로 고칩니다.
ms.date: 05/30/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: bff27bf7fec2bcb741846ae76bb1f616f459136c
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2022
ms.locfileid: "9012033"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Power Query 및 Azure Data Lake 데이터 원본에 대한 증분 새로 고침

이 문서에서는 Power Query 또는 Azure Data Lake를 기반으로 데이터 원본에 대한 증분 새로 고침을 구성하는 방법에 대해 설명합니다.

데이터 소스 증분 새로 고침은 다음과 같은 이점을 제공합니다:

- **빠른 새로 고침** - 변경된 데이터만 새로 고침됩니다. 예를 들어 지난 5일 동안의 과거 데이터 집합만 새로 고칠 수 있습니다.
- **신뢰성 향상** - 새로 고침이 작을수록 휘발성 원본 시스템에 대한 연결을 오랫동안 유지할 필요가 없으므로 연결 문제의 위험이 줄어듭니다.
- **리소스 소비 감소** - 전체 데이터의 일부만 새로 고치면 컴퓨팅 리소스를 보다 효율적으로 사용하고 환경 공간이 줄어듭니다.

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Power Query 기반 데이터 원본의 증분 새로 고침 구성

Customer Insights는 증분 새로 고침을 지원하는 Power Query를 통해 가져온 데이터 원본의 증분 새로 고침을 허용합니다. 예를 들어 날짜 및 시간 필드가 있는 Azure SQL 데이터베이스는 데이터 레코드가 마지막으로 업데이트된 시간을 나타냅니다.

1. [Power Query를 기반으로 새로운 데이터 원본을 만듭니다](connect-power-query.md).

1. [Azure SQL 데이터베이스](/power-query/connectors/azuresqldatabase)와 같이 증분 새로 고침을 지원하는 데이터 원본을 선택하십시오.

1. 수집할 엔터티 또는 테이블을 선택합니다.

1. 변환 단계를 완료하고 **다음** 을 선택합니다.

1. **증분 새로 고침 설정** 대화 상자에서 **설정** 을 선택하여 **증분 새로 고침 설정** 을 엽니다. **건너 뛰기** 를 선택하면 데이터 원본은 전체 데이터 집합을 새로 고칩니다.
   > [!TIP]
   > 기존 데이터 원본을 편집하여 나중에 증분 새로 고침을 적용할 수도 있습니다.

1. **증분 새로 고침 설정** 에서 데이터 원본을 만들 때 선택한 모든 엔터티에 대해 증분 새로 고침을 구성합니다.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="증분 새로 고침 설정 구성.":::

1. 엔터티를 선택하고 다음 세부 사항을 제공하십시오.

   - **기본 키 정의**: 엔터티 또는 테이블의 기본 키를 선택하십시오.
   - **"마지막 업데이트" 필드 정의**: 이 필드에는 날짜 또는 시간 유형의 특성만 표시됩니다. 레코드가 마지막으로 업데이트 된 시점을 나타내는 특성을 선택하십시오. 증분 새로 고침 시간 프레임 내에서 레코드를 식별하는 데 사용됩니다.
   - **업데이트 확인 간격**: 증분 새로 고침 시간 프레임의 기간을 지정하십시오.

1. **저장** 을 선택하여 데이터 원본의 생성을 완료합니다. 초기 데이터 새로 고침은 전체 새로 고침입니다. 이후에 증분 데이터 새로 고침은 이전 단계에서 구성한 대로 수행됩니다.

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>Azure Data Lake 데이터 원본에 대한 증분 새로 고침 구성

Customer Insights는 Azure Data Lake Storage에 연결된 데이터 원본에 대한 증분 새로 고침을 허용합니다. 엔터티에 대한 증분 수집 및 새로 고침을 사용하려면 Azure Data Lake 데이터 원본을 추가할 때 또는 나중에 데이터 원본을 편집할 때 해당 엔터티를 구성합니다. 엔터티 데이터 폴더에는 다음 폴더가 포함되어야 합니다.

- **FullData**: 초기 레코드를 포함하는 데이터 파일이 있는 폴더
- **IncrementalData**: 증분 업데이트를 포함하는 **yyyy/mm/dd/hh** 형식의 날짜/시간 계층 폴더가 있는 폴더입니다. **hh** 는 업데이트의 UTC 시간을 나타내며 **Upserts** 및 **Deletes** 폴더를 포함합니다. **Upserts** 에는 기존 레코드 또는 새 레코드에 대한 업데이트가 포함된 데이터 파일이 포함되어 있습니다. **삭제** 에는 제거할 레코드가 있는 데이터 파일이 포함됩니다.

1. 데이터 원본을 추가하거나 편집할 때 엔터티의 **특성** 창으로 이동합니다.

1. 특성을 검토합니다. 생성되거나 마지막으로 업데이트된 날짜 특성이 *날짜/시간* **데이터 형식** 및 *Calendar.Date* **의미 체계 유형** 으로 설정되었는지 확인하십시오. 필요한 경우 특성을 편집하고 **완료** 를 선택합니다.

1. **엔터티 선택** 창에서 엔터티를 편집합니다. **증분 수집** 확인란이 선택되어 있습니다.

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="증분 새로 고침을 위해 데이터 원본에서 엔터티 구성.":::

   1. 전체 데이터, 증분 데이터 upsert 및 증분 데이터 삭제에 대한 .csv 또는 .parquet 파일이 포함된 루트 폴더를 찾습니다.
   1. 전체 데이터와 두 증분 파일(\.csv 또는 \.parquet)에 대한 확장자를 입력합니다.
   1. **저장** 을 선택합니다.

1. **마지막 업데이트** 에서 날짜 타임스탬프 특성을 선택합니다.

1. **기본 키** 가 선택되지 않은 경우 기본 키를 선택합니다. 기본 키는 엔터티에 고유한 특성입니다. 특성이 유효한 기본 키가 되려면 중복 값, 누락 된 값 또는 null 값을 포함하지 않아야 합니다. 문자열, 정수 및 GUID 데이터 유형 특성은 기본 키로 지원됩니다.

1. **닫기** 를 선택하여 창을 저장하고 닫습니다.

1. 계속해서 데이터 원본을 추가하거나 편집합니다.

[!INCLUDE [footer-include](includes/footer-banner.md)]
