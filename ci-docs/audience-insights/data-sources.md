---
title: 데이터를 수집할 데이터 원본 사용
description: 다양한 소스에서 데이터를 가져 오는 방법을 알아 봅니다.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 0fc13d3ac0a5176637b6fe481dabe0b2aec11649
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887902"
---
# <a name="data-sources-overview"></a>데이터 원본 개요

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Dynamics 365 Customer Insights의 대상 그룹 인사이트 기능은 광범위한 원본 집합의 데이터에 연결됩니다. 데이터 원본에 연결하는 과정을 종종 *데이터 수집* 프로세스라고 합니다. 데이터를 수집 한 후, [통합화](data-unification.md) 하고 조치를 취할 수 있습니다.

## <a name="add-a-data-source"></a>데이터 원본 추가

선택한 옵션에 따라 데이터 원본를 추가하는 방법에 대한 자세한 문서를 참조하세요.

세 가지 주요 방법으로 데이터 원본를 추가 할 수 있습니다.

- [수십 개의 파워 쿼리 커넥터를 통해](connect-power-query.md)
- [Common Data Model 폴더로 부터](connect-common-data-model.md)
- [내 Common Data Service 레이크로 부터](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>온-프레미스 데이터 소스의 데이터 추가

대상 그룹 Insights의 온-프레미스 데이터 소스에서 데이터 수집은 Power Platform 데이터 흐름을 기반으로 지원됩니다. Customer Insights에서 데이터 흐름을 활성화할 수 있습니다. 환경을 설정할 때 [Microsoft Dataverse 환경 URL을 제공](manage-environments.md#create-an-environment-in-an-existing-organization)하면 됩니다.

Dataverse 환경과 Customer Insights가 사용하는 환경을 연견ㄹ한 후 생성되는 데이터 소스는 기본적으로 [Power Platform 데이터 흐름](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365)을 사용합니다. 데이터 흐름은 데이터 게이트웨이를 사용하여 온-프레미스 연결을 지원합니다. Dataverse 환경이 연결되기 이전에 존재했던 데이터 소스를 제거하고 다시 만들어 온-프레미스 데이터 게이트웨이를 사용합니다.

기존 Power BI의 데이터 게이트웨이 또는 Power Apps 환경이 표시되고 Customer Insights에서 재사용할 수 있습니다. 데이터 소스 페이지에는 Power Platform 환경으로 이동하는 링크가 표시됩니다. 온-프레미스 데이터 게이트웨이를 보고 구성 할 수 있는 환경입니다.

:::image type="content" source="media/data-sources-onpremises-gateways.png" alt-text="Power Platform 환경으로 이동하는 링크를 보여주는 데이터 소스 페이지의 스크린샷":::

## <a name="review-ingested-data"></a>수집 된 데이터 검토

수집 된 각 데이터 원본의 이름, 해당 상태 및 해당 소스에 대한 데이터가 마지막으로 새로 고쳐진 시간이 표시됩니다. 모든 열을 기준으로 데이터 원본 목록을 정렬할 수 있습니다.

> [!div class="mx-imgBorder"]
> ![데이터 원본 추가](media/configure-data-datasource-added.png "데이터 원본 추가")

|상태  |설명  |
|---------|---------|
|성공   |**새로 고침됨** 열에 데이터 원본에 시간이 언급되면 성공적으로 수집되었습니다.
|시작되지 않음   |데이터 원본에는 아직 수집된 데이터가 없거나 아직 초안 모드에 있습니다.         |
|새로 고침    |데이터 수집이 진행 중입니다. **작업** 열에서 **새로 고침 중지** 를 선택하여 이 작업을 취소할 수 있습니다 . 데이터 원본의 새로 고침을 중지하면 마지막 새로 고침 상태로 되돌아갑니다.       |
|실패함     |데이터 수집에 오류가 발생했습니다.         |

데이터 원본의 **상태** 열에서 값을 선택하여 자세한 내용을 검토하십시오. **진행 세부 정보** 창에서 **데이터 원본** 을 확장합니다. 오류 세부 정보 및 다운스트림 프로세스 업데이트를 포함한 새로 고침 상태에 대한 자세한 내용을 보려면 **세부 정보 보기** 를 선택합니다.

데이터 로딩에 약간 시간이 걸릴 수 있습니다. 성공적으로 새로 고친 후 수집된 데이터는 **엔터티** 페이지에서 검토할 수 있습니다. 자세한 내용은 [엔터티](entities.md)를 참조하십시오.

## <a name="refresh-a-data-source"></a>데이터 원본 새로 고침

데이터 원본은 자동 일정에 따라 새로 고쳐 지거나 필요에 따라 수동으로 새로 고칠 수 있습니다. 

**관리** > **시스템** > [**일정**](system.md#schedule-tab)으로 이동하여 수집된 모든 데이터 원본의 예약된 새로 고침을 구성합니다.

요청 시 데이터 원본을 새로 고침하려면 다음 단계를 따르세요.

1. 대상 그룹 인사이트에서 **데이터** > **데이터 원본** 으로 이동합니다.

2. 새로 고치려는 데이터 원본 옆에 있는 세로 줄임표를 선택하고 드롭다운 목록에서 **새로 고침** 을 선택합니다.

3. 데이터 원본은 이제 수동 새로 고침을 위해 트리거됩니다. 데이터 원본를 새로 고침하면 데이터 원본에 지정된 모든 엔터티의 엔터티 스키마와 데이터가 모두 업데이트됩니다.

4. 기존 새로 고침을 취소하고 데이터 원본이 마지막 새로 고침 상태로 되돌리려면 **새로 고침 중지** 를 선택합니다.

## <a name="delete-a-data-source"></a>데이터 원본 삭제

1. 대상 그룹 인사이트에서 **데이터** > **데이터 원본** 으로 이동합니다.

2. 제거하려는 데이터 원본 옆에 있는 세로 줄임표를 선택하고 드롭다운 메뉴에서 **삭제** 를 선택합니다.

3. 삭제를 확정합니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
