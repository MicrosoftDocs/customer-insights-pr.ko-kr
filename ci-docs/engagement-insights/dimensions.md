---
title: 차원 보기 및 만들기
description: 차원을 만들고 편집 및 삭제하는 방법.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 136da1e1265c7087d861712d34d011b09cb60ad5
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623640"
---
# <a name="view-and-create-dimensions"></a>차원 보기 및 만들기

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

차원은 데이터를 설명, 필터링 또는 그룹화할 수 있는 이벤트 속성입니다. 웹 사이트에서 마케팅 프로모션을 진행하는 경우 차원을 사용하여 신규 및 재방문 사용자별로 방문자를 정렬할 수 있습니다.  

참여 인사이트에는 이벤트 속성에 대한 OOB(기본) 차원이 포함됩니다. 예는 다음과 같습니다.

- 브라우저 이름
- 페이지 이름
- 장치 모델
- 운영 체제
- 국가

## <a name="view-dimensions"></a>차원 보기

차원은 기존 이벤트 속성을 기반으로 합니다. 참여 인사이트에 추적 코드를 사용하면 시스템 차원이 자동으로 생성됩니다.

1. 왼쪽 탐색 창의 **데이터** 로 이동합니다. 
1. **차원** 탭을 선택하여 작업 영역의 모든 차원 목록을 확인하십시오. 
   > [!NOTE]
   > 시스템 생성 차원은 읽기 전용입니다. 편집할 수 없습니다. 사용자 지정 차원만 만들고 편집할 수 있습니다.

## <a name="create-a-dimension"></a>차원 만들기

시스템 생성 차원 외에도 환경 및 작업 영역 관리자는 사용자 지정 차원을 생성할 수 있습니다. 사용자 지정 차원은 기본 이벤트의 기본 속성을 기반으로 하거나 [이벤트의 사용자 지정 속성](advanced-SDK-implementation.md)을 사용할 수 있습니다.

1. **데이터** > **차원** 으로 이동합니다.
1. **새 차원** 을 선택합니다.

   :::image type="content" source="media/add-dimension.png" alt-text="이벤트에 차원 추가.":::

1. **차원 만들기** 창에서 차원의 기준이 될 속성을 선택합니다. 속성 목록에는 차원에 할당되지 않은 작업 영역의 모든 속성이 표시됩니다.
   
   :::image type="content" source="media/create-new-dimension.png" alt-text="새 차원 만들기.":::
      
3. **표시 이름** 상자에 이름을 입력합니다. 선택적으로 **설명** 을 추가할 수 있습니다.
4. **만들기** 를 선택하여 차원을 저장합니다. [사용자 지정 보고서](custom-reports.md) 또는 [세그먼트](segments.md)에서 차원을 사용하려면 최대 1분이 걸릴 수 있습니다. 

## <a name="edit-a-dimension"></a>차원 편집

차원의 이름과 설명을 변경할 수 있습니다. 사용자가 만든 차원만 편집할 수 있지만 시스템 차원은 편집할 수 없습니다.


1. **데이터** > **차원** 으로 이동합니다.
1. 삭제하려는 차원을 선택합니다.
1. **차원 편집** 창에서 차원을 업데이트합니다.
1. **적용** 을 선택하여 변경 내용을 저장합니다.

## <a name="delete-a-dimension"></a>차원 삭제

사용자가 만든 차원만 삭제할 수 있으며 시스템 차원은 제거할 수 없습니다.

차원 삭제는 영구적입니다. 삭제된 차원을 사용하는 보고서 및 세그먼트는 더 이상 작동하지 않습니다. 

1. **데이터** > **차원** 으로 이동합니다.
1. 삭제하려는 차원을 선택합니다.
1. **차원 편집** 창에서 **차원 삭제** 를 선택합니다.

   :::image type="content" source="media/delete-dimension.png" alt-text="이벤트에 대한 차원 삭제.":::

1. **CONFIRM DELETE**(모두 대문자로)를 입력하여 삭제를 확인합니다. 
1. **삭제** 를 선택합니다.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
