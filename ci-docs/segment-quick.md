---
title: 빠른 세그먼트를 사용하여 단순 세그먼트 만들기
description: 다양한 특성을 기반으로 그룹화할 단순 고객 세그먼트를 만듭니다.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 98260371a17ff8a05912cc1bc08c67fbe9755727
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171138"
---
# <a name="create-simple-segments-with-quick-segments"></a>빠른 세그먼트를 사용하여 단순 세그먼트 만들기

빠른 세그먼트를 사용하면 단일 운영자로 간단한 세그먼트를 빠르게 구축하여 더 빠른 인사이트를 얻을 수 있습니다. 빠른 세그먼트는 **개별 고객** 의 환경에서만 지원됩니다.

## <a name="create-a-new-segment-with-quick-segments"></a>빠른 세그먼트를 사용하여 새 세그먼트 만들기

1. **세그먼트** 로 이동

1. **새로 만들기** > **다음에서 만들기** 를 선택합니다.
   - **프로필** 옵션을 선택하여 *통합 고객* 엔터티를 기반으로 하는 세그먼트를 작성합니다.
   - **측정값** 옵션을 선택하여 이전에 만든 측정값을 중심으로 세그먼트를 만듭니다.
   - **예측** 또는 **사용자 지정 모델** 기능을 사용하여 생성한 출력 엔터티 중 하나를 중심으로 세그먼트를 작성하려면 **인텔리전스** 옵션을 선택합니다.

1. **새로운 빠른 세그먼트** 대화 상자에서 **필드** 드롭다운에서 특성을 선택합니다. 선택 항목에 따라 시스템에서 다른 값을 제공합니다.
   - 범주별 필드의 경우 10개의 최상위 고객 수가 표시됩니다. **값** 을 선택하고 **검토** 를 선택합니다.
   - 숫자 특성의 경우 시스템은 각 고객의 백분위 수에 속하는 특성값을 표시합니다. **연산자** 와 **값** 을 선택한 다음 **검토** 를 선택합니다.

1. 시스템은 **예상 세그먼트 크기** 를 제공합니다. 정의한 세그먼트를 생성할지 또는 되돌아가 다른 필드를 선택할지 선택합니다.

   :::image type="content" source="media/quick-segment-name.png" alt-text="빠른 세그먼트의 이름 및 평가.":::

1. 세그먼트의 **이름** 및 **출력 엔터티 이름** 을 제공합니다. 선택적으로 [태그](work-with-tags-columns.md#manage-tags)를 추가합니다.

1. **저장** 을 선택하여 세그먼트를 만듭니다. **세그먼트** 페이지가 표시됩니다.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-steps"></a>다음 단계

[세그먼트 내보내기](export-destinations.md)를 수행하고 [고객 카드 통합](customer-card-add-in.md)을 탐색하여 다른 응용 프로그램에서 세그먼트를 사용합니다.

[!INCLUDE [footer-include](includes/footer-banner.md)]
