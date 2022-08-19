---
title: 측정값 개요
description: 측정값이 비즈니스 성과를 분석하고 반영하는 데 어떻게 도움이 되는지 알아보세요.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: 99368a7ab2e8d7b3e53c04fbf25bb23bd2e550a9
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245381"
---
# <a name="measures-overview"></a>측정값 개요

측정값은 고객 행동과 비즈니스 성과를 더 잘 이해하는 데 도움이 됩니다. 측정값은 [통합 프로필](data-unification.md)에서 관련 가치를 확인합니다. 예를 들어, 기업은 개별 고객의 구매 내역을 이해하거나 *회사의 총 매출* 을 측정하여 비즈니스 전체의 집계된 수익을 이해하기 위해 *고객당 총 지출* 을 보고 싶어 합니다.

측정값을 생성하여 고객 데이터를 쿼리하고 인사이트를 추출하여 비즈니스 활동을 계획합니다. 예를 들어 *고객당 총지출* 및 *고객당 총수익* 의 측정값을 생성하면 지출이 많고 수익이 높은 고객 그룹을 식별하는 데 도움이 됩니다. 그런 다음 이러한 측정값을 기반으로 [세그먼트를 생성](segments.md)하여 차선책을 유도할 수 있습니다.

## <a name="create-a-measure"></a>측정값 만들기

목표 대상 그룹을 기반으로 측정값을 만드는 방법을 선택합니다.

# <a name="individual-consumers-b-to-c"></a>[개별 소비자(B2C)](#tab/b2c)

- 측정값 빌더를 사용하여 처음부터 [자체 측정값을 빌드](measure-builder.md)합니다.
- 일반적으로 사용되는 측정값에서 [미리 정의된 템플릿](measure-templates.md)을 사용합니다.

# <a name="business-accounts-b-to-b"></a>[비즈니스 어카운트(B2B)](#tab/b2b)

측정값 빌더를 사용하여 처음부터 [자체 측정값을 빌드](measure-builder.md)합니다.

---

## <a name="manage-existing-measures"></a>기존 측정값 관리

**측정값** 페이지로 이동하여 생성한 측정값, 해당 상태, 측정값 유형 및 데이터를 마지막으로 새로 고친 시간을 확인합니다. 열을 기준으로 측정값 목록을 정렬하거나 검색 상자를 사용하여 관리하려는 측정값을 찾을 수 있습니다.

사용 가능한 작업을 보려면 측정값 옆을 선택합니다. 측정값 이름을 선택하여 출력값을 미리 보고 CSV 파일을 다운로드합니다.

:::image type="content" source="media/measures-actions.png" alt-text="단일 측정을 관리하기 위한 작업."lightbox="media/measures-actions.png":::

- 측정값을 **편집** 하여 속성을 변경합니다.
- 측정값을 **새로 고침** 하여 최신 데이터를 포함합니다.
- 측정 **이름 바꾸기** 를 수행합니다.
- 측정값을 **활성화** 또는 **비활성화** 합니다. [예약된 새로 고침](schedule-refresh.md) 중에는 비활성 측정값을 새로 고침하지 않으며 **상태** 가 **건너뜀** 으로 나열되어 있으면 새로 고침이 시도되지 않았음을 나타냅니다.
- **태그** 하여 측정값용 [태그를 관리](work-with-tags-columns.md#manage-tags)합니다.
- 측정을 **삭제** 합니다.
- **열**: 표시되는 [열을 사용자 지정](work-with-tags-columns.md#customize-columns)합니다.
- **필터**: [태그를 필터링](work-with-tags-columns.md#filter-on-tags)합니다.
- **이름을 검색** 하여 측정값별로 검색합니다.

## <a name="refresh-measures"></a>측정값 새로 고침

측정값은 자동 예약에 따라 새로 고쳐지거나 필요에 따라 수동으로 새로 고칠 수 있습니다. 하나 이상의 측정값을 수동으로 새로 고치려면 측정값을 선택하고 **새로 고침** 을 실행합니다. [자동 새로 고침을 예약](schedule-refresh.md)하려면 **관리** > **시스템** > **예약** 으로 이동합니다.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
