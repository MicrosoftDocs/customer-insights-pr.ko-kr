---
title: Power Query 기반 데이터 원본의 증분 새로 고침
description: Power Query를 기반으로 하는 대규모 데이터 원본에 대한 새 데이터 및 업데이트된 데이터를 새로 고칩니다.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 3d21baf9804f300802b066df0183fc8f01abba9a
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647187"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Power Query 기반 데이터 원본의 증분 새로 고침

이 문서에서는 Power Query를 기반으로 데이터 원본에 대한 증분 새로 고침을 구성하는 방법에 대해 설명합니다.

데이터 소스 증분 새로 고침은 다음과 같은 이점을 제공합니다:

- **빠른 새로 고침** - 변경된 데이터만 새로 고침됩니다. 예를 들어 지난 5일 동안의 과거 데이터 집합만 새로 고칠 수 있습니다.
- **신뢰성 향상** - 새로 고침이 작을수록 휘발성 원본 시스템에 대한 연결을 오랫동안 유지할 필요가 없으므로 연결 문제의 위험이 줄어듭니다.
- **리소스 소비 감소** - 전체 데이터의 일부만 새로 고치면 컴퓨팅 리소스를 보다 효율적으로 사용하고 환경 공간이 줄어듭니다.

## <a name="configure-incremental-refresh"></a>증분식 새로 고침 구성

Customer Insights는 증분 새로 고침을 지원하는 Power Query를 통해 가져온 데이터 원본의 증분 새로 고침을 허용합니다. 예를 들어 날짜 및 시간 필드가 있는 Azure SQL 데이터베이스는 데이터 레코드가 마지막으로 업데이트된 시간을 나타냅니다.

1. [Power Query를 기반으로 새로운 데이터 원본을 만듭니다](connect-power-query.md).

1. 데이터 원본의 **이름** 을 제공합니다.

1. [Azure SQL 데이터베이스](/power-query/connectors/azuresqldatabase)와 같이 증분 새로 고침을 지원하는 데이터 원본을 선택하십시오.

1. 수집할 엔터티 또는 테이블을 선택합니다.

1. 변환 단계를 완료하고 **다음** 을 선택합니다.

1. **증분 새로 고침 설정** 대화 상자에서 **설정** 을 선택하여 **증분 새로 고침 설정** 을 엽니다. **건너 뛰기** 를 선택하면 데이터 원본은 전체 데이터 집합을 새로 고칩니다.
   > [!TIP]
   > 기존 데이터 원본을 편집하여 나중에 증분 새로 고침을 적용할 수도 있습니다.

1. **증분 새로 고침 설정** 에서 데이터 원본을 만들 때 선택한 모든 엔터티에 대해 증분 새로 고침을 구성합니다.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="증분 새로 고침을 위해 데이터 원본에서 엔터티 구성.":::

1. 엔터티를 선택하고 다음 세부 사항을 제공하십시오.

   - **기본 키 정의**: 엔터티 또는 테이블의 기본 키를 선택하십시오.
   - **"마지막 업데이트" 필드 정의**: 이 필드에는 날짜 또는 시간 유형의 특성만 표시됩니다. 레코드가 마지막으로 업데이트 된 시점을 나타내는 특성을 선택하십시오. 증분 새로 고침 시간 프레임 내에서 레코드를 식별하는 데 사용됩니다.
   - **업데이트 확인 간격**: 증분 새로 고침 시간 프레임의 기간을 지정하십시오.

1. **저장** 을 선택하여 데이터 원본의 생성을 완료합니다. 초기 데이터 새로 고침은 전체 새로 고침입니다. 이후에 증분 데이터 새로 고침은 이전 단계에서 구성한 대로 수행됩니다.


[!INCLUDE [footer-include](includes/footer-banner.md)]
