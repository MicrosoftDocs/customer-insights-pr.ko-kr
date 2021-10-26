---
title: 사용자 지정 보고서 정보
description: 사용자 지정 보고서를 만드는 방법을 알아봅니다.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 3fa801bfc8b0aee65c21b90de2423a3d5d5e4e26
ms.sourcegitcommit: d9965f4bfc09391698a34042f6b44367e53819e3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2021
ms.locfileid: "7582885"
---
# <a name="create-and-edit-custom-reports"></a>사용자 지정 보고서 만들기 및 편집

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

OOB(기본) 보고서 이외에도 사용자 동작을 이해하는 데 도움이 하도록 차트 및 테이블 시각화로 사용자 지정 보고서를 제작할 수 있습니다. 이 도움말에서는 테이블 및 차트 시각화를 사용하여 필요한 데이터로 보고서를 만드는 방법을 설명합니다. OOB 보고서에 대한 자세한 내용은 [보고서 보기](view-reports.md)를 참조하세요.

## <a name="create-a-custom-report"></a>사용자 지정 보고서 만들기

1. **분석** > **사용자 지정** 으로 이동하여 사용자 지정 보고서 목록에 액세스할 수 있습니다.

1. 사용자 지정 보고서 만들기를 시작하려면 **새로운 보고서** 를 선택합니다.

   :::image type="content" source="media/new-custom-report.png" alt-text="새로운 사용자 지정 보고서.":::

1. 작성하려는 보고서 유형을 결정합니다.

    - 명령 모음에서 **시각적 개체 추가** 를 선택하여 기본 테이블 시각화를 만듭니다.
    - 또는 **보고서 편집기** 창에서 열, 막대, 선, 영역, 파이, 도넛 또는 테이블 시각화를 선택합니다.

1. **시각화** 편집기 창의 **데이터** 섹션에 있는 **메트릭** 드롭다운에서 사용 가능한 옵션(예: 페이지 보기) 중 하나를 선택합니다. 시각화에 표시할 **차원**(예: 국가)을 추가할 수도 있습니다. 자세한 내용은 [메트릭 보기 및 만들기](metrics.md) 및 [차원 보기 및 만들기](dimensions.md)를 참조하세요.

   :::image type="content" source="media/page-views.png" alt-text="보고서의 메트릭 선택.":::

1. **시각화 편집기** 창의 **디자인** 섹션을 선택하여 **제목 텍스트** 를 추가하고 **제목** 을 켜고 끕니다.  **원형 차트** 와 같은 다른 차트를 선택하여 시각화 유형을 변경할 수도 있습니다.

1. 시각화의 크기와 위치를 변경하는 방법:
   - 시각화를 선택한 다음 모서리 또는 테두리 중 하나를 끌어 크기를 조정합니다.
   - 시각화를 선택하고 새 위치로 이동합니다. 화살표 키를 사용하여 위치를 변경할 수도 있습니다.
1. 다른 시각화를 추가하려면 명령 모음에서 **시각적 개체 추가** 를 선택합니다.
1. 보고서에 대해 원하는 시각화를 추가한 후 명령 모음에서 **저장** 을 선택합니다.

1. 사용자 지정 보고서의 이름을 제공하고 **저장** 을 선택하여 작성합니다.
 
## <a name="filter-a-custom-report"></a>사용자 지정 보고서 필터링

사용자 지정 보고서에서 시간 프레임 또는 기간을 선택하여 값이나 기간에 집중할 수 있습니다.

시간 프레임를 선택하려면 보고서 보기의 오른쪽 상단 모서리에 있는 보고서의 드롭다운 목록에서 값을 선택합니다. *고정 날짜 범위* 를 선택할 수도 있습니다.

:::image type="content" source="media/filter-time-date-range.png" alt-text="시간 또는 날짜 범위로 필터링.":::

대부분의 보고서에서 **+ 조건 추가** 를 선택하여 보고서를 필터링할 메트릭 또는 세그먼트를 선택합니다. 자세한 내용은 [세그먼트 보기 및 만들기](segments.md)를 참조하세요.

## <a name="edit-a-custom-report"></a>사용자 지정 보고서 편집

1. **분석** > **사용자 지정** 으로 이동하여 사용자 지정 보고서 목록에 액세스할 수 있습니다.

1. 사용자 지정 보고서 목록에서 **더 보기 [...]** 를 선택합니다. 

1. 보고서 이름을 변경하려면 **이름 편집** 을 선택합니다.

1. 보고서 이름을 선택하고 **+ 시각적 개체 추가** 및 **편집** 옵션을 사용하여 시각화를 추가, 제거, 위치 변경 또는 크기 조정합니다.

1. 시각화의 속성을 변경하려면 시각적 개체를 선택하고 **...** 를 선택한 다음 **시각적 개체 편집** 을 선택합니다.

   :::image type="content" source="media/edit-visual-control.png" alt-text="사용자 지정 보고서에 대한 차트 속성 편집.":::

1. 보고서를 편집한 후 **저장** 을 선택하여 변경 내용을 적용합니다. 

## <a name="delete-a-custom-report"></a>사용자 지정 보고서 삭제

1. **분석** > **사용자 지정** 으로 이동하여 사용자 지정 보고서 목록에 액세스할 수 있습니다.

1. 사용자 지정 보고서 목록에서 **...** 를 선택합니다.

1. 보고서를 제거하려면 **삭제** 를 선택합니다.

1. 보고서를 영구적으로 제거하려면 삭제를 확인합니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
