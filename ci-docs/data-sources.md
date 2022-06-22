---
title: 데이터를 수집할 데이터 원본 사용
description: 다양한 소스에서 데이터를 가져 오는 방법을 알아 봅니다.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: e22977107565a0b28b74f41576a1c7ccc74f6dc1
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011757"
---
# <a name="data-sources-overview"></a>데이터 원본 개요

Dynamics 365 Customer Insights는 광범위한 원본 집합에서 데이터를 가져올 수 있는 연결을 제공합니다. 데이터 원본에 연결하는 과정을 종종 *데이터 수집* 프로세스라고 합니다. 데이터를 수집한 후 개인화된 경험을 구축하기 위해 데이터를 [통합](data-unification.md)하고 인사이트를 생성하고 활성화할 수 있습니다.

## <a name="add-data-sources"></a>데이터 원본 추가

데이터 원본을 Customer Insights에 첨부하거나 가져올 수 있습니다. 아래 링크는 데이터 원본 추가에 대한 지침을 제공합니다.

**데이터 원본 첨부**

Microsoft의 Azure 데이터 서비스 중 하나에서 준비된 데이터가 있는 경우 Customer Insights는 데이터를 다시 수집하지 않고도 데이터 원본에 쉽게 연결할 수 있습니다. 다음 옵션 중 하나를 선택합니다.
- [Azure Data Lake Storage(Common Data Model 폴더의 csv 또는 parquet 파일)](connect-common-data-model.md)
- [Azure Synapse Analytics(레이크 데이터베이스)](connect-synapse.md)
- [Microsoft Dataverse 데이터 레이크](connect-dataverse-managed-lake.md)

**가져오기 및 변환**

온-프레미스 데이터 원본, Microsoft 또는 타사 데이터를 사용하는 경우 Power Query 커넥터를 사용하여 데이터를 가져오고 변환합니다.
- [Power Query 커넥터](connect-power-query.md)

## <a name="review-data-sources"></a>데이터 원본 검토

환경이 Customer Insights 스토리지를 사용하도록 구성되었고 온-프레미스 데이터 원본을 사용하는 경우 Power Platform 데이터 흐름을 사용합니다. Power Platform 데이터 흐름을 통해 공유 데이터 원본과 다른 사람이 관리하는 데이터 원본을 볼 수 있습니다. **데이터 원본** 페이지는 다음의 세 섹션에 데이터 원본을 나열합니다.
- **공유**: 모든 Customer Insights 관리자가 관리할 수 있는 데이터 원본입니다. Power Platform 데이터 흐름, 고유한 스토리지 계정 및 Dataverse 관리 데이터 레이크에 연결하는 것이 공유 데이터 원본의 예입니다.
- **내가 관리**: 나만이 만들고 관리하는 Power Platform 데이터 흐름입니다. 다른 Customer Insights 관리자는 이러한 데이터 흐름을 볼 수만 있고 편집, 새로 고침 또는 삭제할 수 없습니다.
- **다른 사람이 관리함**: 다른 관리자가 만든 Power Platform 데이터 흐름입니다. 보는 것만 가능합니다. 도움이 필요하면 연락할 데이터 흐름의 담당자를 나열합니다.
> [!NOTE]
> 모든 엔터티는 다른 사용자가 보고 사용할 수 있습니다. 데이터 원본은 원본을 만든 사용자가 소유하지만 데이터 수집의 결과 엔터티는 Customer Insights의 모든 사용자가 사용할 수 있습니다.

환경에서 Power Platform 데이터 흐름을 사용하지 않는 경우 **데이터 원본** 페이지에는 모든 데이터 원본의 목록만 포함됩니다. 표시된 섹션이 없습니다.

**데이터** > **데이터 원본** 으로 이동하여 수집된 각 데이터 원본의 이름, 해당 상태 및 해당 원본에 대한 데이터가 마지막으로 새로 고쳐진 시간을 확인합니다. 모든 열을 기준으로 데이터 원본 목록을 정렬할 수 있습니다.

:::image type="content" source="media/configure-data-datasource-added.png" alt-text="원본 데이터 추가됨.":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

데이터를 로드하는 데 시간이 걸릴 수 있습니다. 성공적으로 새로 고친 후 수집된 데이터는 **엔터티** 페이지에서 검토할 수 있습니다. 자세한 내용은 [엔터티](entities.md)를 참조하십시오.

## <a name="refresh-data-sources"></a>데이터 원본 새로 고침

데이터 원본은 자동 일정에 따라 새로 고쳐 지거나 필요에 따라 수동으로 새로 고칠 수 있습니다. [온-프레미스 데이터 원본](connect-power-query.md#add-data-from-on-premises-data-sources)은 데이터 수집 중에 설정된 자체 일정에 따라 새로 고쳐집니다. 연결된 데이터 원본의 경우 데이터 수집은 해당 데이터 원본에서 사용 가능한 최신 데이터를 사용합니다.

**관리** > **시스템** > [**일정**](system.md#schedule-tab)으로 이동하여 수집된 데이터 원본의 시스템 예약 새로 고침을 구성합니다.

요청 시 데이터 원본을 새로 고침하려면 다음 단계를 따르세요.

1. **데이터** > **데이터 원본** 으로 이동.

1. 새로 고치려는 데이터 원본 옆의 세로 줄임표(&vellip;)를 선택하고 드롭다운 목록에서 **새로 고침** 을 선택합니다. 데이터 원본은 이제 수동 새로 고침을 위해 트리거됩니다. 데이터 원본를 새로 고침하면 데이터 원본에 지정된 모든 엔터티의 엔터티 스키마와 데이터가 모두 업데이트됩니다.

1. 기존 새로 고침을 취소하고 데이터 원본이 마지막 새로 고침 상태로 되돌리려면 **새로 고침 중지** 를 선택합니다.

## <a name="delete-a-data-source"></a>데이터 원본 삭제

데이터 원본은 데이터가 통합, 통찰력, 활성화 또는 내보내기와 같은 처리에 사용되지 않는 경우에만 삭제할 수 있습니다.

1. **데이터** > **데이터 원본** 으로 이동.

2. 제거하려는 데이터 원본 옆의 세로 줄임표(&vellip;)를 선택하고 드롭다운 메뉴에서 삭제 **삭제** 를 선택합니다.

3. 삭제를 확정합니다.


[!INCLUDE [footer-include](includes/footer-banner.md)]
