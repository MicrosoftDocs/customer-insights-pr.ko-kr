---
title: 행동 데이터 분할에 인구통계학적 차원 사용(큐레이팅 차원)
description: 통합 프로필 큐레이팅 차원을 사용하여 대상 그룹 인사이트 고객 프로필 속성을 활성화합니다.
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 50bb800c9e097d03cc6f26f79819c741ab5e8baf
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461111"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>행동 데이터 분할에 인구통계학적 차원 사용

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

통합 프로필 인구통계학적 차원을 사용하여 참여 인사이트 사용자는 대상 그룹 인사이트 프로필 속성에 액세스할 수 있습니다. 그런 다음 웹사이트 또는 모바일 앱의 참여 인사이트로 캡처한 데이터를 포함한 행동 데이터의 대화형 분석에서 이러한 속성을 사용할 수 있습니다.

>[!NOTE]
> 참여 인사이트에는 이벤트 속성에 대한 기본 차원이 포함됩니다. 추가 정보: [차원 보기 및 만들기](dimensions.md)

## <a name="prerequisite"></a>필수 구성 요소

- 고객 프로필이 만들어지는 대상 그룹 인사이트 환경에 연결된 고객 프로필 데이터가 있는 참여 인사이트 환경. 추가 정보: [대상 그룹 인사이트와 참여 인사이트 사이에 링크 만들기](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> 대상 그룹 인사이트와 참여 인사이트 환경 간의 링크를 만든 후에는 고객 프로필 속성과 관련된 데이터만 원할 수 있으며, 이는 참여 인사이트의 차원으로 유용할 수 있습니다. 자세한 정보는 [대상 그룹 인사이트 통합 프로필 특성 및 세그먼트 활성화](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments)를 참고하십시오.<!--note from editor: Suggested. -->

## <a name="create-a-new-custom-report"></a>새 사용자 지정 보고서 만들기

1. 왼쪽 창에서 **사용자 지정** > **새 보고서** 를 선택한 후 원하는 메트릭을 선택합니다. (이 예에서는 **시간별 페이지 조회수** 를 선택했습니다.)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="메트릭 선택.":::

2. 시각화 편집기에서 **차원** 을 선택한 다음 **차원 유형** 드롭다운 메뉴에서 **인구통계** 를 선택합니다.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="인구통계 선택.":::

3. **Signal.Customer.*xxx*** 차원을 선택합니다. (이 예는 Signal.Customer.Country를 보여줍니다.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="차원 선택.":::
  
## <a name="limitations"></a>제한 사항

현재는 행동 데이터 분할에 인구통계학적 차원만 사용할 수 있습니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
