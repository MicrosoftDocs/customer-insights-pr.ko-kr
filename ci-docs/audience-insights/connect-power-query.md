---
title: Power Query 커넥터를 통해 데이터 수집(비디오 포함)
description: Power Query를 기반으로 하는 데이터 원본용 커넥터.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 727cb9a4d754b6dbd74d6ecab1b183d41f713d8f
ms.sourcegitcommit: aadee829eff111c95eb30c0a97a68dcc87994acf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2022
ms.locfileid: "8092080"
---
# <a name="connect-to-a-power-query-data-source"></a>Power Query 데이터 원본에 연결

Power Query는 데이터 수집을 위한 광범위한 커넥터 세트를 제공합니다. 이러한 커넥터의 대부분은 Dynamics 365 Customer Insights의 지원을 받습니다. 

Power Query 커넥터를 기반으로 데이터 원본을 추가하는 것은 일반적으로 이 섹션에 설명된 단계를 따릅니다. 그러나 사용하는 커넥터에 따라 다른 정보가 필요합니다. 자세한 내용은 [Power Query 커넥터 참조](/power-query/connectors/)에서 개별 커넥터에 대한 설명서를 참조하세요.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>새 데이터 원본 만들기

1. 대상 그룹 인사이트에서 **데이터** > **데이터 원본** 으로 이동합니다.

1. **데이터 원본 추가** 를 선택합니다.

1. **Microsoft Power Query** 을 선택합니다.

1. 데이터 원본을 위해 **이름** 을 제공하고 데이터 원본 생성을 위해 **다음** 을 선택합니다.

1. [사용 가능한 커넥터](#available-power-query-data-sources) 중 하나를 선택합니다. 이 예에서는 **텍스트/CSV** 커넥터를 선택합니다.

1. 선택한 커넥터에 대해 **연결 설정** 에서 필요한 세부 정보를 입력하고 데이터 미리보기를 위해 **다음** 을 선택합니다.

1. **변환 데이터** 선택. 이 단계에서는 데이터 원본에 엔터티를 추가합니다. 엔터티는 데이터 세트입니다. 여러 데이터 집합을 포함하는 데이터베이스가 있는 경우 각 데이터 집합은 자체 엔터티입니다.

1. **Power Query - 쿼리 편집** 대화 상자를 사용하여 데이터를 검토하고 구체화할 수 있습니다. 선택한 데이터 원본에서 식별된 시스템이 왼쪽 창에 나타납니다.

   > [!div class="mx-imgBorder"]
   > ![쿼리 편집 대화.](media/data-manager-configure-edit-queries.png "대화 쿼리 편집")

1. 데이터를 변환할 수도 있습니다. 편집하거나 변환할 엔터티를 선택합니다. Power Query 창의 옵션을 사용하여 변환을 적용합니다. 각 변환은 **적용 단계** 아래에 나열됩니다. Power Query는 수많은 미리 빌드된 변환 옵션을 제공합니다. 자세한 내용은 [Power Query 변환](/power-query/power-query-what-is-power-query#transformations)을 참조하세요.

   다음 변환을 사용하는 것이 좋습니다.

   - CSV 파일에서 데이터를 수집하는 경우 첫 번째 행에는 종종 헤더가 포함됩니다. **변환** 으로 이동하고 **첫 번째 행을 헤더로 사용** 을 선택합니다.
   - 데이터 유형이 적절하게 설정되었는지 확인하십시오. 예를 들어 날짜 필드의 경우 날짜 유형을 선택합니다.

1. **쿼리 편집** 대화 상자에서 데이터 원본에 추가 엔티티를 추가하려면 **홈** 으로 이동하고 **데이터 가져오기** 를 선택합니다.

1. Power Query 창의 하단에 있는 **저장** 을 선택하여 변환을 저장합니다. 저장하면 후에, **데이터** > **데이터 소스** 에서 데이터 원본를 찾을 수 있습니다.

1. **데이터 소스** 페이지에서 새 데이터 소스가 **새로 고침** 상태로 보여집니다.

## <a name="available-power-query-data-sources"></a>사용 가능한 Power Query 데이터 원본

[Power Query 커넥터 참조](/power-query/connectors/)에서 Customer Insights로 데이터를 가져오는 데 사용할 수 있는 커넥터 목록을 확인하세요. 

**Customer Insights(데이터 흐름)** 의 체크 표시가 있는 커넥터를 Power Query를 기반으로 새 데이터 소스를 생성하는 데 사용할 수 있습니다. 특정 커넥터의 문서를 검토하여 전제 조건, 제한 사항 및 기타 세부 사항에 대해 자세히 알아보십시오.

## <a name="edit-power-query-data-sources"></a>Power Query 데이터 원본 편집

> [!NOTE]
> 현재 앱 프로세스 중 하나에서 사용 중인 데이터 원본을 변경하지 못할 수도 있습니다(예를 들어, *분할*, *일치* 또는 *병합*). 
>
> **설정** 페이지를 사용하여 각 활성 프로세스의 진행 상황을 추적할 수 있습니다. 프로세스가 완료되면 **데이터 원본** 페이지로 돌아가 변경할 수 있습니다.

1. 대상 그룹 인사이트에서 **데이터** > **데이터 원본** 으로 이동합니다.

2. 변경하려는 데이터 원본 옆의 세로 줄임표를 선택하고 드롭다운 메뉴에서 **편집** 을 선택합니다.

   > [!div class="mx-imgBorder"]
   > ![편집 옵션.](media/edit-option-data-sources.png "편집 옵션")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. [새 데이터 원본 만들기](#create-a-new-data-source) 섹션에 설명된 대로 **Power Query - 쿼리 편집** 대화 상자에서 변경 사항 및 변환을 적용합니다.

4. 편집을 완료한 후 Power Query에서 **저장** 을 선택하여 변경 사항을 저장합니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
