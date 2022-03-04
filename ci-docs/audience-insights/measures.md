---
title: 측정값 이해 및 관리
description: 측정값이 비즈니스 성과를 분석하고 반영하는 데 어떻게 도움이 되는지 알아보세요.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: c46fcc3baba1d6c92c2c0fe459a62277343cc0e4
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359795"
---
# <a name="measures-overview"></a>측정값 개요

측정값은 고객 행동과 비즈니스 성과를 더 잘 이해하는 데 도움이 됩니다. 측정값은 [통합 프로필](data-unification.md)에서 관련 가치를 확인합니다. 예를 들어, 기업은 개별 고객의 구매 내역을 이해하거나 *회사의 총 매출* 을 측정하여 비즈니스 전체의 집계된 수익을 이해하기 위해 *고객당 총 지출* 을 보고 싶어 합니다.  

측정값은 다양한 연산자와 간단한 매핑 옵션이 있는 데이터 쿼리 플랫폼인 [측정값 빌더를 사용](measure-builder.md)하여 생성됩니다. 이를 통해 데이터를 필터링하고 결과를 그룹화하고 [엔터티 관계 경로](relationships.md)를 감지하고 출력을 미리 볼 수 있습니다. [미리 정의된 템플릿을 사용](measure-templates.md)하여 효율성 있게 일반적으로 사용되는 측정값을 구성할 수 있습니다.

측정값 빌더를 사용하여 고객 데이터를 쿼리하고 인사이트를 추출하여 비즈니스 활동을 계획합니다. 예를 들어 *고객당 총 지출* 및 *고객당 총 수익* 의 측정값을 생성하면 지출이 많고 수익이 높은 고객 그룹을 식별하는 데 도움이 됩니다. 이러한 측정값을 기반으로 [세그먼트를 생성](segments.md)하여 차선책을 유도할 수 있습니다. 

## <a name="manage-your-measures"></a>측정 관리

측정값 목록은 **측정** 페이지에 있습니다.

측정값 유형, 작성자, 생성 날짜, 현황 및 상태에 대한 정보를 확인할 수 있습니다. 목록에서 측정값을 선택하면 출력을 미리 보고 CSV 파일을 다운로드할 수 있습니다.

모든 측정을 동시에 새로 고치려면 특정 측정을 선택하지 않고 **모두 새로 고침** 을 선택합니다.

:::image type="content" source="media/measure-actions.png" alt-text="단일 측정을 관리하기 위한 작업.":::

다음 옵션에 대한 목록에서 측정값을 선택하십시오.

- 세부 사항을 보려면 측정 이름을 선택합니다.
- 측정의 구성을 **편집** 합니다.
- 최신 데이터를 기반으로 측정값을 **새로 고침** 합니다.
- 측정 **이름 바꾸기** 를 수행합니다.
- 측정을 **삭제** 합니다.
- **활성화** 또는 **비활성화** 합니다. [예약된 새로 고침](system.md#schedule-tab) 중에는 비활성 측정값이 새로 고쳐지지 않습니다.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>다음 단계

기존 측정을 사용하여 [고객 세그먼트](segments.md)를 만들 수 있습니다.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
