---
title: 데이터 원본 개요
description: 다양한 원본에서 데이터를 가져오거나 수집하는 방법을 알아보세요.
ms.date: 09/29/2022
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
ms.openlocfilehash: f89da3cf5b56e367bd673740f80cd82ec0907b28
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610060"
---
# <a name="data-sources-overview"></a>데이터 원본 개요

Dynamics 365 Customer Insights는 광범위한 원본 집합에서 데이터를 가져올 수 있는 연결을 제공합니다. 데이터 원본에 연결하는 과정을 종종 *데이터 수집* 프로세스라고 합니다. 데이터를 수집한 후 개인화된 경험을 구축하기 위해 데이터를 [통합](data-unification.md)하고 인사이트를 생성하고 활성화할 수 있습니다.

## <a name="add-or-edit-data-sources"></a>데이터 원본 추가 또는 편집

데이터 원본을 Customer Insights에 첨부하거나 가져올 수 있습니다. 다음 링크는 데이터 원본 추가 및 편집에 대한 지침을 제공합니다.

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

## <a name="manage-existing-data-sources"></a>기존 데이터 원본 관리

**데이터** > **데이터 원본** 으로 이동하여 수집된 각 데이터 원본의 이름, 해당 상태 및 해당 원본에 대한 데이터가 마지막으로 새로 고쳐진 시간을 확인합니다. 열을 기준으로 데이터 원본 목록을 정렬하거나 검색 상자를 사용하여 관리하려는 데이터 원본을 찾을 수 있습니다.

사용 가능한 작업을 보려면 데이터 원본을 선택합니다.

:::image type="content" source="media/data_sources_showmore.png" alt-text="원본 데이터 추가됨.":::

- [**편집**](#add-or-edit-data-sources): 속성을 변경할 데이터 원본을 편집합니다.
- [**새로 고침**](#refresh-data-sources): 최신 데이터를 포함하도록 데이터 원본을 새로 고침 합니다.
- [**보강**](data-sources-enrichment.md): 통합 전에 데이터 원본을 보강합니다.
- 데이터 원본을 **삭제** 합니다. 데이터 원본은 데이터가 통합, 통찰력, 활성화 또는 내보내기와 같은 처리에 사용되지 않는 경우에만 삭제할 수 있습니다.

## <a name="refresh-data-sources"></a>데이터 원본 새로 고침

데이터 원본은 자동 일정에 따라 새로 고쳐 지거나 필요에 따라 수동으로 새로 고칠 수 있습니다. [온-프레미스 데이터 원본](connect-power-query.md#add-data-from-on-premises-data-sources)은 데이터 수집 중에 설정된 자체 일정에 따라 새로 고쳐집니다. 문제 해결 팁은 [Power Query 기반 데이터 원본 새로 고침 문제 해결](connect-power-query.md#troubleshoot-ppdf-power-query-based-data-source-refresh-issues)을 참조하세요.

연결된 데이터 원본의 경우 데이터 수집은 해당 데이터 원본에서 사용 가능한 최신 데이터를 사용합니다.

**관리** > **시스템** > [**일정**](schedule-refresh.md)으로 이동하여 수집된 데이터 원본의 시스템 예약 새로 고침을 구성합니다.

필요에 따라 데이터 원본을 새로 고침하려면 다음을 따르세요.

1. **데이터** > **데이터 원본** 으로 이동.

1. 새로 고침하려는 데이터 원본을 선택하고 **새로 고침** 을 선택합니다. 데이터 원본은 이제 수동 새로 고침을 위해 트리거됩니다. 데이터 원본를 새로 고침하면 데이터 원본에 지정된 모든 엔터티의 엔터티 스키마와 데이터가 모두 업데이트됩니다.

1. 상태를 선택하여 **진행 세부 정보** 창을 열고 진행 상황을 조회합니다. 작업을 취소하려면 창 하단에서 **작업 취소** 를 선택합니다.

## <a name="corrupt-data-sources"></a>데이터 원본 손상

수집되는 데이터에는 오류 또는 경고와 함께 데이터 수집 프로세스가 완료될 수 있는 손상된 레코드가 있을 수 있습니다.

> [!NOTE]
> 데이터 수집이 오류와 함께 완료되면 이 데이터 원본를 활용하는 후속 처리(예: 통합 또는 활동 생성)를 건너뜁니다. 경고와 함께 수집이 완료되면 후속 처리가 계속되지만 일부 레코드가 포함되지 않을 수 있습니다.

이러한 오류는 작업 세부 정보에서 볼 수 있습니다.

:::image type="content" source="media/corrupt-task-error.png" alt-text="손상된 데이터 오류를 보여주는 작업 세부 정보.":::

손상된 레코드는 시스템 생성 엔터티에 표시됩니다.

### <a name="fix-corrupt-data"></a>손상 데이터 수정

1. 손상 데이터를 보려면 **데이터** > **엔터티** 로 이동하여 **시스템** 섹션에서 손상된 엔터티를 찾습니다. 손상된 엔터티의 명명 스키마: 'DataSourceName_EntityName_corrupt'.

1. 손상된 엔터티를 선택한 다음 **데이터** 탭을 선택합니다.

1. 레코드의 손상된 필드와 이유를 식별합니다.

   :::image type="content" source="media/corruption-reason.png" alt-text="손상된 이유." lightbox="media/corruption-reason.png":::

   > [!NOTE]
   > **데이터** > **엔터티** 는 손상된 레코드의 일부만 표시합니다. 손상된 레코드를 모두 보려면 [Customer Insights 내보내기 프로세스](export-destinations.md)를 사용하여 스토리지 계정의 컨테이너로 파일을 내보냅니다. 자신의 스토리지 계정을 사용한 경우 스토리지 계정의 Customer Insights 폴더를 볼 수도 있습니다.

1. 손상된 데이터를 수정하십시오. 예를 들어 Azure Data Lake 데이터 원본의 경우 [Data Lake Storage의 데이터를 수정하거나 manifest/model.json 파일의 데이터 형식을 업데이트합니다](connect-common-data-model.md#common-reasons-for-ingestion-errors-or-corrupt-data). Power Query 데이터 원본의 경우 **Power Query - 쿼리 편집** 페이지에서 원본 파일의 데이터를 수정하고 [변환 단계에서 데이터 형식 수정](connect-power-query.md#data-type-does-not-match-data)을 수행합니다.

다음 번에 데이터 원본을 새로 고친 후 수정된 레코드는 Customer Insights에 수집되고 다운스트림 프로세스로 전달됩니다.

예를 들어, '생일' 열에는 '날짜'로 설정된 데이터 유형이 있습니다. 고객 레코드에 생일이 '01/01/19777'로 입력되어 있습니다. 시스템은 이 레코드가 손상된 것으로 플래그를 지정합니다. 소스 시스템의 생일을 '1977'로 변경합니다. 데이터 원본의 자동 새로 고침 후 필드는 이제 유효한 형식을 가지며 레코드는 손상된 엔터티에서 제거됩니다.

[!INCLUDE [footer-include](includes/footer-banner.md)]
