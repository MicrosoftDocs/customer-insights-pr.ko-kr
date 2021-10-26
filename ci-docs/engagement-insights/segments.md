---
title: 세그먼트 보기 및 만들기
description: 세그먼트 및 세그먼트를 사용할 위치를 생성, 편집 및 삭제하는 방법.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: f6bba645a78173fb00dc75e6080f2aeda0b5a143
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623595"
---
# <a name="view-and-create-segments"></a>세그먼트 보기 및 만들기

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

세그먼트를 사용하면 특성 또는 웹 사이트 상호 작용을 기반으로 방문자의 하위 집합을 식별할 수 있습니다. 세그먼트를 사용하면 필터를 적용하고 해당 하위 집합을 분석할 수 있습니다. 분석은 비즈니스의 추세를 조사하고 이에 대응하는 데 도움이 될 수 있습니다. 

:::image type="content" source="media/segments-page.png" alt-text="작업 영역의 기존 세그먼트 목록을 보여주는 참여 인사이트 애플리케이션의 스크린샷입니다.":::

## <a name="view-segments"></a>세그먼트 보기

1. 왼쪽 탐색 창의 **데이터** 로 이동합니다. 

1. **세그먼트** 탭을 선택하여 작업 영역의 모든 세그먼트 목록을 확인하십시오. 

## <a name="create-a-segment"></a>세그먼트 만들기

세그먼트는 논리 연산자와 연결된 규칙 및 조건으로 구성됩니다. 조건은 선택한 차원에 필터를 적용합니다. 모든 세그먼트는 최대 5개의 차원을 사용할 수 있습니다.

다음 예는 하나의 규칙에 두 개의 조건이 있는 세그먼트를 보여줍니다. 브라우저가 Chrome이고 운영 체제가 iOS 또는 Android인 모든 웹 사이트 이벤트를 필터링합니다.

:::image type="content" source="media/segment-sample.png" alt-text="웹 사이트 이벤트를 필터링할 규칙에 두 가지 조건이 있는 예시 세그먼트입니다.":::

이 섹션에서는 *빈 세그먼트* 를 만드는 방법에 대해 처음부터 설명합니다.

1. **데이터** > **세그먼트** 로 이동합니다.

1. **새 세그먼트** 를 선택합니다.

1. **리소스 라이브러리** 에서 필터링 기준으로 사용할 속성 옆에 있는 (+)를 선택합니다. 현재는 차원에 기반해서만 세그먼트를 만들 수 있습니다.

   :::image type="content" source="media/create-new-segment.png" alt-text="새 세그먼트 만들기.":::

1. **규칙** 섹션에서 선택한 특성에 대한 연산자와 값을 선택합니다. 다음 연산이 지원됩니다.

   :::image type="content" source="media/choose-operator-segment.png" alt-text="새 세그먼트에 대한 연산자 선택.":::

   - **is**: 값을 포함하려면 정확히 일치해야 합니다. 단일 값에 여러 값을 포함하려면 **equal to** 를 사용하거나 **any of** 를 사용합니다.
   - **is not**: 값을 제외하려면 정확히 일치해야 합니다. 단일 값에 여러 값을 포함하려면 **equal to** 를 사용하거나 **any of** 를 사용합니다.
   - **starts with**: 일치하는 값이 시작하는 문자열입니다.
   - **ends with**: 일치하는 값이 끝나는 문자열입니다.
   - **contains**: 일치하는 값에 포함된 문자열입니다.

1. 그룹에 조건을 더 추가하려면 논리 연산자를 사용할 수 있습니다. 프로젝트된 특성은 집합 연산자를 사용할 때 고려됩니다.
   - **AND** 연산자: 두 조건을 모두 세분화 프로세스의 일부로 충족해야 합니다. 이 옵션은 여러 엔터티에서 조건을 정의할 때 가장 유용합니다.
   - **OR** 연산자: 세그레이션 프로세스의 일부로 조건 중 하나를 충족해야 합니다. 이 옵션은 동일한 엔터티에 대해 여러 조건을 정의할 때 가장 유용합니다.

1. **저장** 을 선택하고 세그먼트 이름을 지정합니다. 

세그먼트는 **세그먼트** 페이지에 나열되며 작업 영역의 모든 보고서 및 유입 경로에 적용할 수 있습니다.

## <a name="use-a-segment-in-a-report-or-funnel"></a>보고서 또는 유입 경로에서 세그먼트 사용

보고서 또는 유입 경로에 세그먼트를 적용하여 세그먼트의 조건에 따라 필터링할 수 있습니다. 그러나 실시간 사용 보고서에는 세그먼트를 적용할 수 없습니다.

:::image type="content" source="media/segment-reports-filter.png" alt-text="적용할 세그먼트를 선택할 수 있는 확장된 드롭다운 목록이 있는 페이지 보기 보고서입니다.":::

세그먼트를 적용하려면 보고서 또는 유입 경로를 엽니다. **+ 조건 추가** 를 선택하고 **세그먼트로 필터링** 을 선택합니다. 적용할 세그먼트를 목록에서 선택하십시오. 세그먼트가 보고서에 적용됩니다. 차트가 세그먼트를 지원하지 않으면 오류가 표시됩니다. 자세한 내용은 [유입 경로 보고서 만들기 및 관리](funnel-reports.md)를 참조하세요.
 
보고서 또는 유입 경로에 *최대 3개의 세그먼트* 를 적용할 수 있습니다.

## <a name="edit-a-segment"></a>세그먼트 편집

1. **데이터** > **세그먼트** 로 이동합니다.
1. 목록에서 세그먼트를 선택하여 엽니다. 
1. 필요에 따라 값을 변경하거나 추가합니다.
1. **저장** 을 선택하여 변경 내용을 적용합니다.

## <a name="change-the-name-of-a-segment"></a>세그먼트 이름 변경

1. **데이터** > **세그먼트** 로 이동합니다.
1. 세그먼트 목록에서 **더보기 [...]** 를 선택합니다. 
1. 드롭다운 목록에서 **이름 편집** 을 선택합니다.
1. 새로운 이름을 입력하고 **이름바꾸기** 를 선택합니다.

## <a name="delete-a-segment"></a>세그먼트 삭제

1. **데이터** > **세그먼트** 로 이동합니다.
1. 세그먼트 목록에서 **더보기 [...]** 를 선택합니다. 
1. 드롭다운 목록에서 **삭제** 를 선택합니다.
1. **삭제** 를 선택하여 확인합니다.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
