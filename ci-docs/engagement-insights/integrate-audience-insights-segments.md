---
title: 대상 그룹 인사이트 세그먼트를 사용하여 참여 인사이트 보고서 필터링
description: 고객 웹사이트에서 참여 인사이트로 캡처한 행동 데이터의 대화형 분석에서 대상 그룹 인사이트 세그먼트를 사용합니다.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9c8c7a1a9216e04ebee100c548afbc745af396ec
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230494"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>대상 그룹 인사이트 세그먼트를 사용하여 참여 인사이트 보고서 필터링

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

인게이지먼트 인사이트를 사용하면 웹사이트에서 참여 인사이트로 캡처한 행동 데이터의 대화형 분석에서 대상 그룹 인사이트 세그먼트를 사용합니다.

## <a name="prerequisite"></a>필수 구성 요소

- 대상 그룹 인사이트가 있는 참여 인사이트 환경은 세그먼트 및 고객 프로필이 생성되는 대상 그룹 인사이트 환경에 연결된 데이터를 세그먼트화합니다. 추가 정보: [대상 그룹 인사이트와 참여 인사이트 사이에 링크 만들기](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>대상 그룹 인사이트 세그먼트 만들기 

> [!IMPORTANT]
> 대상 그룹 인사이트 세그먼트가 참여 인사이트에 표시되려면 먼저 [병합 및 다운스트림 프로세스를 실행](../audience-insights/merge-entities.md)해야 합니다. 다운스트림 프로세스는 참여 인사이트와 공유할 대상 그룹 인사이트 세그먼트를 준비하는 고유한 테이블을 생성하기 때문에 중요합니다. (시스템 새로 고침이 예약된 경우 다운스트림 프로세스가 자동으로 포함됩니다.)

참여 인사이트의 기본 제공 보고서 또는 사용자가 만든 사용자 지정 보고서에서 대상 그룹 인사이트 세그먼트를 사용할 수 있습니다. 자세한 내용은 [기본 제공 프로필 보고서](profile-reports.md) 및 [사용자 지정 보고서 만들기 및 편집](custom-reports.md)을 참고하십시오.

**참여 인사이트 보고서에서 대상 그룹 인사이트 세그먼트를 사용하는 방법**

1. **작업 영역** 페이지에서 **데이터** 를 선택한 다음 **세그먼트** 탭을 선택합니다.

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="세그먼트 탭 선택.":::

   >[!NOTE]
   > 대상 그룹 인사이트 세그먼트를 선택하면 대상 그룹 인사이트로 이동하여 규칙 및 논리 측면에서 해당 세그먼트가 어떻게 생성되었는지 확인할 수 있습니다. 대상 그룹 인사이트 세그먼트에 대한 자세한 내용은 [세그먼트 보기 및 만들기](../audience-insights/segments.md)를 참조하십시오.

2. 기본 제공 보고서 또는 [사용자 지정 보고서 만들기](custom-reports.md)를 선택한 다음 **조건 추가** 를 선택합니다. (이 예에서는 **페이지 조회수** 보고서를 선택했습니다.)

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="조건 추가.":::

3. **세그먼트별 필터링** 을 선택하고 **세그먼트 유형** 목록을 확장한 다음 **인구통계** 를 선택합니다.

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="인구통계 세그먼트 유형 선택.":::

4. **세그먼트 이름** 목록을 확장한 다음 대상 그룹 인사이트 세그먼트를 선택합니다.

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text="세그먼트 선택.":::

5. 행동(참여 인사이트) 및 인구통계(대상 그룹 인사이트) 세그먼트를 포함하여 하나 이상의 세그먼트를 적용할 수 있습니다. 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="페이지 조회수 보고서는 미국 고객 및 홈페이지 세그먼트로 제한됩니다.":::

앞의 이미지에서 **미국 고객** 및 **홈페이지** 세그먼트가 선택되어 **페이지 조회수** 보고서가 두 세그먼트만 표시하도록 제한합니다. 


>[!NOTE]
> 대상 그룹 인사이트 세그먼트를 사용하여 참여 인사이트에서 기본 제공 보고서, 맞춤 보고서 및 유입경로를 필터링할 수 있습니다. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]