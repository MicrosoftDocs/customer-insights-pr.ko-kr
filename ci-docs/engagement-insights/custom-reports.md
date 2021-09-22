---
title: 사용자 지정 보고서 정보
description: 사용자 지정 보고서를 만드는 방법을 알아봅니다.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 2540221710786dc1c84b231fbb23b9749b601cc6a2aeb78614e16002302a80a9
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036971"
---
# <a name="create-and-edit-custom-reports"></a>사용자 지정 보고서 만들기 및 편집

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

기본 보고서 외에도 차트 및 테이블 시각화가 포함된 사용자 지정 보고서를 작성하여 사용자 행동을 이해하는 데 도움을 줄 수 있습니다. 이 도움말에서는 테이블 및 차트 시각화를 사용하여 필요한 데이터로 보고서를 만드는 방법을 설명합니다. 

## <a name="create-a-custom-report"></a>사용자 지정 보고서 만들기

1. **분석** > **사용자 지정** 으로 이동하여 사용자 지정 보고서 목록에 액세스할 수 있습니다.

1. 사용자 지정 보고서 만들기를 시작하려면 **새로운 보고서** 를 선택합니다.

   :::image type="content" source="media/new-custom-report.png" alt-text="새로운 사용자 지정 보고서.":::

1. 작성하려는 보고서 유형을 결정합니다.

    - 명령 모음에서 **시각적 개체 추가** 를 선택하여 기본 테이블 시각화를 만듭니다.
    - 또는 **보고서 편집기** 창에서 열, 막대, 선, 영역, 파이, 도넛 또는 테이블 시각화를 선택합니다.

1. **데이터** 패널에서 표시할 사용 가능한 **메트릭**(예 : 페이지 조회) 중 하나를 선택합니다. 그런 다음 시각화에 표시할 **차원**(예: 국가)을 추가합니다. 선택할 추가 옵션 추가에 대한 자세한 내용은 [메트릭 보기 및 만들기](metrics.md)와 [차원 보기 및 만들기](dimensions.md)를 참조하십시오.

1. **시각화 편집기** 창에서 **디자인** 을 선택하여 **제목 텍스트** 를 추가하고 **위치**, **데이터 레이블** 및 **축** 을 설정합니다.  다른 차트 유형을 선택하여 시각화를 변경할 수도 있습니다.

1. 시각화의 크기와 위치를 변경할 수 있습니다.
   - 시각화를 선택한 다음 모서리 또는 테두리 중 하나를 끌어 크기를 조정합니다.
   - 시각화를 선택하고 새 위치로 이동합니다. 화살표 키를 사용하여 위치를 변경할 수도 있습니다.
1. 다른 시각화를 추가하려면 명령 모음에서 **시각적 개체 추가** 를 선택합니다.
1. 보고서에 대해 원하는 시각화를 추가한 후 명령 모음에서 **저장** 을 선택합니다.

1. 사용자 지정 보고서의 이름을 제공하고 **저장** 을 선택하여 작성합니다.
 
## <a name="edit-a-custom-report"></a>사용자 지정 보고서 편집

1. **분석** > **사용자 지정** 으로 이동하여 사용자 지정 보고서 목록에 액세스할 수 있습니다.

1. 사용자 지정 보고서 목록에서 **더 보기 [...]** 를 선택합니다. 

1. 보고서 이름을 변경하려면 **세부 정보 편집** 을 선택합니다.

1. 보고서 이름을 선택하고 **시각적 개체 추가** 및 **편집** 옵션을 사용하여 시각화를 추가, 제거, 위치 변경 또는 크기 조정합니다.

1. 시각화 속성을 변경하려면 **...** 를 선택한 다음 **시각적 개체 편집** 을 선택합니다.

   :::image type="content" source="media/edit-visual-control.png" alt-text="사용자 지정 보고서에 대한 차트 속성 편집.":::

1. 보고서를 편집한 후 **저장** 을 선택하여 변경 내용을 적용합니다. 

## <a name="delete-a-custom-report"></a>사용자 지정 보고서 삭제

1. **분석** > **사용자 지정** 으로 이동하여 사용자 지정 보고서 목록에 액세스할 수 있습니다.

1. 사용자 지정 보고서 목록에서 **...** 를 선택합니다.

1. 보고서를 제거하려면 **삭제** 를 선택합니다.

1. 보고서를 영구적으로 제거하려면 삭제를 확인합니다.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
