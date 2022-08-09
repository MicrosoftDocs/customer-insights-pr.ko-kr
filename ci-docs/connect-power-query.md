---
title: Power Query 데이터 원본에 연결(비디오 포함)
description: Power Query 커넥터를 통해 데이터를 수집합니다(비디오 포함).
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: matgos
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 7af51ed04fbd28149ea501c58e6fe71b5fa6d4b6
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207053"
---
# <a name="connect-to-a-power-query-data-source"></a>Power Query 데이터 원본에 연결

Power Query는 데이터 수집을 위한 광범위한 커넥터 세트를 제공합니다. 이러한 커넥터의 대부분은 Dynamics 365 Customer Insights의 지원을 받습니다.

Power Query 커넥터를 기반으로 데이터 원본을 추가하는 것은 일반적으로 이 섹션에 설명된 단계를 따릅니다. 그러나 사용하는 커넥터에 따라 다른 정보가 필요합니다. 자세한 내용은 [Power Query 커넥터 참조](/power-query/connectors/)에서 개별 커넥터에 대한 설명서를 참조하세요.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>새 데이터 원본 만들기

1. **데이터** > **데이터 원본** 으로 이동.

1. **데이터 원본 추가** 를 선택합니다.

1. **Microsoft Power Query** 을 선택합니다.

1. 데이터 원본에 대한 **이름** 과 **설명**(선택 사항)을 제공하고 **다음** 을 선택합니다.

1. [사용 가능한 커넥터](#available-power-query-data-sources) 중 하나를 선택합니다. 이 예에서는 **텍스트/CSV** 커넥터를 선택합니다.

1. 선택한 커넥터에 대해 **연결 설정** 에서 필요한 세부 정보를 입력하고 데이터 미리보기를 위해 **다음** 을 선택합니다.

1. **변환 데이터** 선택.

1. **Power Query - 쿼리 편집** 대화 상자를 사용하여 데이터를 검토하고 구체화할 수 있습니다. 선택한 데이터 원본에서 식별된 시스템이 왼쪽 창에 나타납니다.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="대화 쿼리 편집":::

1. 데이터를 변환할 수도 있습니다. 편집하거나 변환할 엔터티를 선택합니다. Power Query 창의 옵션을 사용하여 변환을 적용합니다. 각 변환은 **적용된 단계** 아래에 나열됩니다. Power Query는 [이미 빌드된 변환](/power-query/power-query-what-is-power-query#transformations) 옵션을 다양하게 제공합니다.

   다음 변환을 사용하는 것이 좋습니다.

   - CSV 파일에서 데이터를 수집하는 경우 첫 번째 행에는 종종 헤더가 포함됩니다. **변환** 으로 이동하고 **첫 번째 행을 헤더로 사용** 을 선택합니다.
   - 데이터 유형이 적절하게 설정되었는지 확인하십시오. 예를 들어 날짜 필드의 경우 날짜 유형을 선택합니다.

1. **쿼리 편집** 대화 상자에서 데이터 원본에 추가 엔티티를 추가하려면 **홈** 으로 이동하고 **데이터 가져오기** 를 선택합니다. 이 데이터 원본에 대한 모든 엔터티를 추가할 때까지 5~10단계를 반복합니다. 여러 데이터 집합을 포함하는 데이터베이스가 있는 경우 각 데이터 집합은 자체 엔터티입니다.

1. **저장** 을 선택합니다. **데이터 원본** 페이지가 열리고 **새로 고침 중** 상태의 새 데이터 원본이 표시됩니다.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

데이터를 로드하는 데 시간이 걸릴 수 있습니다. 새로 고침이 완료되면, 수집된 데이터를 [**엔터티**](entities.md) 페이지에서 검토할 수 있습니다.

> [!CAUTION]
> Power Query 기반 데이터 원본은 [Dataverse의 데이터 흐름](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365)을 생성합니다. Customer Insights에서 사용되는 Power Platform 관리 센터의 데이터 흐름 이름을 바꾸지 않도록 하세요. 데이터 흐름의 이름을 바꾸면 Customer Insights 데이터 원본과 Dataverse 데이터 흐름 간의 참조 데이터에 문제가 생깁니다.

### <a name="available-power-query-data-sources"></a>사용 가능한 Power Query 데이터 원본

[Power Query 커넥터 참조](/power-query/connectors/)에서 Customer Insights로 데이터를 가져오는 데 사용할 수 있는 커넥터 목록을 확인하세요.

**Customer Insights(데이터 흐름)** 의 체크 표시가 있는 커넥터를 Power Query를 기반으로 새 데이터 소스를 생성하는 데 사용할 수 있습니다. 전제 조건, [쿼리 제한 사항](/power-query/power-query-online-limits) 및 기타 세부 사항에 대해 자세히 알아보려면 특정 커넥터의 설명서를 검토하세요.

## <a name="add-data-from-on-premises-data-sources"></a>온-프레미스 데이터 소스의 데이터 추가

온-프레미스 데이터 원본에서 데이터 수집은 Microsoft Power Platform 데이터 흐름(PPDF)을 기반으로 지원됩니다. 환경을 설정할 때 [Microsoft Dataverse 환경 URL](create-environment.md)을 제공하여 Customer Insights에서 데이터 흐름을 활성화할 수 있습니다.

Dataverse 환경을 Customer Insights와 연결 후 생성되는 데이터 원본은 기본적으로 [Power Platform 데이터 흐름](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365)을 사용합니다. 데이터 흐름은 데이터 게이트웨이를 사용하여 온 프레미스 연결을 지원합니다. [온-프레미스 데이터 게이트웨이](/data-integration/gateway/service-gateway-app)를 사용하여 Dataverse 환경이 연결되기 전에 존재했던 데이터 소스를 제거하고 다시 생성할 수 있습니다.

기존 Power BI의 데이터 게이트웨이 또는 Power Apps의 환경이 표시되고 Customer Insights에서 이를 재사용할 수 있습니다. 데이터 소스 페이지에는 온-프레미스 데이터 게이트웨이를 보고 구성할 수 있는 Microsoft Power Platform 환경에 대한 링크가 표시됩니다.

> [!IMPORTANT]
> 게이트웨이가 최신 버전으로 업데이트되었는지 확인하십시오. 게이트웨이 화면에 표시되는 프롬프트에서 직접 업데이트를 설치하고 게이트웨이를 재구성하거나 [최신 버전 다운로드](https://powerapps.microsoft.com/downloads/)를 수행할 수 있습니다. 최신 게이트웨이 버전을 사용하지 않는 경우 **키워드는 지원되지 않습니다: 구성 속성. 매개 변수 이름: 키워드** 와 같은 오류 메시지와 함께 데이터 흐름 새로 고침이 실패합니다.
>
> Customer Insights의 온-프레미스 데이터 게이트웨이를 사용할 때 발생하는 오류는 종종 구성 문제에서 기인합니다. 데이터 게이트웨이 관련 문제 해결에 대한 자세한 내용은 [온-프레미스 데이터 게이트웨이의 문제 해결](/data-integration/gateway/service-gateway-tshoot)을 참조하세요.

## <a name="edit-power-query-data-sources"></a>Power Query 데이터 원본 편집

> [!NOTE]
> 현재 앱 프로세스 중 하나에서 사용 중인 데이터 원본을 변경하지 못할 수도 있습니다(예: 분할, 데이터 병합).
>
> **설정** 페이지를 사용하여 각 활성 프로세스의 진행 상황을 추적할 수 있습니다. 프로세스가 완료되면 **데이터 원본** 페이지로 돌아가 변경할 수 있습니다.

1. **데이터** > **데이터 원본** 으로 이동.

1. 업데이트하려는 데이터 원본 옆에 있는 **편집** 을 선택합니다.

1. [새 데이터 원본 만들기](#create-a-new-data-source) 섹션에 설명된 대로 **Power Query - 쿼리 편집** 대화 상자에서 변경 사항 및 변환을 적용합니다.

1. **저장** 을 선택하여 변경 사항을 적용하고 **데이터 원본** 페이지로 돌아갑니다.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
