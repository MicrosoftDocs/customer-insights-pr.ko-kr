---
title: Common Data Model의 Customer Insights 엔터티 스키마
description: Common Data Model에서 엔터티로 작업합니다.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 33a0562854e97b9ac5218e060f965996305627fd
ms.sourcegitcommit: d45c00a5f6cb106714366af81e8070e7f53654b3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2022
ms.locfileid: "8757440"
---
# <a name="entity-schemas-in-common-data-model"></a>Common Data Model의 엔터티 스키마



[Common Data Model](/common-data-model/)은 선언적 사양이며, 여러 비즈니스 및 생산성 애플리케이션에서 일반적으로 사용되는 개념과 활동을 나타내는 표준 엔터티의 정의입니다. 이 모델은 관측 및 분석 데이터로 확장되고 있습니다. Common Data Model은 거래처, 사업부, 서비스 케이스, 연락처, 잠재 고객, 영업 기회, 제품 등과 같은 잘 정의되고 확장 가능한 모듈식 비즈니스 엔터티뿐 아니라 활동이나 서비스 수준 약정 같은 공급업체, 작업자, 고객과의 상호 작용을 제공합니다. 누구나 Common Data Model 정의를 구축하고 확장하여 추가 비즈니스별 아이디어를 포착할 수 있습니다.

이 공유 데이터 모델을 통해 응용 프로그램과 데이터 통합자가 통합된 데이터 정의를 제공하여 보다 쉽게 공동 작업할 수 있습니다. Common Data Model에는 표준 엔터티, 관계, 계층 구조, 특성 등이 포함된 풍부한 메타데이터 시스템이 포함됩니다. Dynamics 365 앱에서 시작되었으며 260개가 넘는 표준 엔터티가 있는 GitHub에서 오픈 소스로 제공됩니다. 내부 및 외부 파트너의 대규모 시스템은 Common Data Model에 산업별 개념을 제공합니다.

오늘날 Power BI 데이터 흐름 및 Azure Data Services를 비롯한 여러 시스템 및 플랫폼이 Common Data Model 을 구현합니다. Microsoft Dataverse, Dynamics 365, Power Apps, Power BI, 곧 출시될 Azure 데이터 서비스에서 이미 지원되며 [오픈 데이터 이니셔티브](https://dynamics.microsoft.com/en-us/open-data-initiative/)에 직접적인 가치를 창출합니다.

## <a name="customer-insights-entity-schemas"></a>Customer Insights 엔터티 스키마

고객에 대한 360도 뷰를 확립하고 확장성을 위해 Common Data Model에서 Customer Insights 모델을 사용할 수 있도록 하기 위해 다음 엔터티 스키마를 공개했습니다.

| 엔터티 | 설명 |
|---------|---------|
|[CustomerActivity](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | 비즈니스에 대한 관찰 가치가 있는 사용자가 수행한 활동입니다. |
|[CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | 비즈니스 활동을 수행하거나 수행할 가능성이 있는 개인 또는 조직. |
|[MeasureDefinition](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | 0개 이상의 차원으로 분할된 KPI 정의(예: 월간 활성 사용자, 총 고객 지출, 평균 고객 확보 비용) |
|[세그먼트](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | 공통된 특성을 가진 구성원 그룹을 정의합니다. |
|[SegmentMembership](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | 주어진 세그먼트에 참여하는 구성원. |

자세한 내용은 [Common Data Model의 Customer Insights 엔터티 스키마](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview)에 대한 설명서를 참조하십시오.

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Common Data Model 엔터티 탐색기를 사용하여 엔터티 보기

[Common Data Model 엔터티 탐색기](https://microsoft.github.io/CDM/)에서 엔터티를 볼 수 있습니다. Insights 응용 프로그램 섹션에서 엔터티를 선택하여 Customer Insights 엔터티 및 해당 정의 목록을 가져옵니다.
> [!div class="mx-imgBorder"]
> ![CustomerActivity 엔터티를 보여주는 CDM 엔터티 탐색기.](media/CDM-entity-navigator.png "CustomerActivity 엔터티를 보여주는 CDM 엔터티 탐색기")


[!INCLUDE [footer-include](includes/footer-banner.md)]