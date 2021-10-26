---
title: 메트릭 보기 및 만들기
description: 메트릭을 만들고 편집 및 삭제하는 방법.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 79600a14bc7e98dfd066270f19c353fd007e1341
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623730"
---
# <a name="view-and-create-metrics"></a>메트릭 보기 및 만들기

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

메트릭은 방문자의 행동을 이해하는 데 도움이 됩니다. 이벤트 속성을 집계하고 웹 속성의 통계 및 성능을 측정합니다.  

웹 사이트에서 마케팅 프로모션을 진행하고 있다고 가정해 보겠습니다. 메트릭을 사용하여 프로모션 기간 동안 웹 사이트를 방문한 순 방문자 또는 사용자 수를 추적할 수 있습니다. 메트릭을 분석하면 웹 사이트 대상 그룹을 더 잘 이해할 수 있습니다. [사용자 지정 보고서](custom-reports.md)에서 메트릭을 [차원](dimensions.md)과 결합하면 행동을 측정하여 사용자를 이해할 수 있습니다. 예를 들어 방문자를 신규 및 재방문 범주로 구분하여 그룹 간의 관심도와 의도의 차이를 식별할 수 있습니다.

## <a name="view-metrics"></a>메트릭 보기

참여 인사이트에는 일반적으로 사용되는 이벤트 속성 집계가 시스템 메트릭으로 포함됩니다. 

- 방문자
- 방문
- 페이지 조회
- 클릭

이러한 시스템 메트릭은 기본 이벤트의 기존 이벤트 속성을 기반으로 합니다.

1. 왼쪽 탐색 창의 **데이터** 로 이동합니다. 
1. **메트릭** 탭을 선택하여 작업 영역의 모든 메트릭 목록을 확인하십시오. 
   > [!NOTE]
   > 시스템 생성 메트릭은 읽기 전용입니다. 편집하거나 삭제할 수 없습니다. 사용자 지정 메트릭만 만들고 편집할 수 있습니다.

## <a name="create-a-metric"></a>메트릭 만들기

환경 및 작업 영역 관리자는 메트릭을 만들 수 있습니다. 메트릭을 만들기 전에 이벤트 속성을 작업 영역으로 보내야 합니다. 기본 이벤트에서 보낸 이벤트 속성을 기반으로 메트릭을 만들거나 웹 SDK를 사용하여 [사용자 지정 이벤트 속성 보내기](advanced-SDK-implementation.md)를 수행할 수 있습니다.

1. **데이터** > **메트릭** 으로 이동합니다.
1. **새 메트릭** 을 선택하여 **리소스 라이브러리** 및 **제목 없는 새 메트릭** 대화 상자를 엽니다.

   :::image type="content" source="media/new-metric.png" alt-text="이벤트에 메트릭 추가.":::

1. **제목 없는 새 메트릭** 대화 상자에서 **형식** 드롭다운 목록을 선택하고 **정수** 또는 **이중** 데이터 유형을 선택합니다. 정수는 전체 자연수입니다. 이중의 경우 소수점 한 자리와 세 자리를 선택할 수 있습니다.

   :::image type="content" source="media/create-new-metric.png" alt-text="새 메트릭 만들기.":::
   
5. **리소스 라이브러리** 창에서 메트릭의 기반이 될 이벤트 속성을 찾습니다.
6. 속성 옆에 있는 **더하기 기호(+)** 를 선택하여 수식에 사용합니다. 하나의 속성을 기반으로 하는 수식만 만들 수 있습니다. 
7. 다음 집계 함수 중 하나를 선택하십시오. 

   - 합계: 모든 값의 산술 합계 
   - 평균: 모든 값의 평균 값
   - 카운트: 값의 총 개수
   - 고유 카운트: 고유 값의 총 개수

   메트릭을 정의하면 지난 1시간 동안 메트릭의 활동 미리 보기가 표시됩니다.

1. **저장** 을 선택합니다. 
1. 메트릭의 이름을 입력하고 **저장** 을 선택합니다.

메트릭을 사용하여 [사용자 지정 보고서](custom-reports.md)를 만드는 데 최대 1분이 걸릴 수 있습니다.

## <a name="edit-a-metric"></a>메트릭 편집

사용자 메트릭만 수정할 수 있습니다.

1. **데이터** > **메트릭** 으로 이동합니다.
1. 목록에서 메트릭을 선택합니다.
1. 메트릭 정의 변경
1. **저장** 을 선택합니다.

## <a name="change-the-name-of-a-metric"></a>메트릭 이름 변경

사용자 지정 메트릭의 이름만 변경할 수 있습니다.

1. **데이터** > **메트릭** 으로 이동합니다.
1. 메트릭에 대해 **더보기 [...]** 를 선택하고 **이름 편집** 을 선택합니다.
1. 이름을 변경합니다. 
1. **이름 바꾸기** 를 선택합니다.

## <a name="delete-a-metric"></a>메트릭 삭제

사용자 메트릭만 삭제할 수 있습니다.

1. **데이터** > **메트릭** 으로 이동합니다.
1. 메트릭에 대해 **더보기 [...]** 를 선택하고 **삭제** 를 선택합니다.

   :::image type="content" source="media/delete-metric.png" alt-text="이벤트에 대한 메트릭 삭제.":::

1. **삭제** 를 선택하여 확인합니다.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
