---
title: 시스템 새로 고침 예약
description: 시스템을 새로 고침해야 하는 시간 예약
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: ce10fcfe9906d33209270f8f6930a51b045b13e2
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246344"
---
# <a name="schedule-system-refresh"></a>시스템 새로 고침 예약

[수집된 데이터 원본](data-sources.md) 전체에 대한 자동 새로 고침을 예약합니다. 자동 새로 고침은 데이터 소스의 업데이트가 통합 고객 프로필에 반영되도록 합니다.

> [!NOTE]
> 귀사가 관리하는 Power Query 데이터 원본은 자체 일정에 따라 새로 고침됩니다. 이 Power Query 데이터 원본의 새로 고침을 예약하려면 **데이터 원본** 페이지에서 해당 데이터 소스에 대한 새로 고침 설정을 구성하세요.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform 데이터 흐름 새로 고침 설정.":::

## <a name="set-system-refresh-schedule"></a>시스템 새로 고침 예약 설정

1. **관리자** > **시스템** 으로 이동한 다음 **일정** 탭을 선택합니다.

   :::image type="content" source="media/schedule_refresh.png" alt-text="시스템 페이지에서 새로 고침 탭을 예약합니다.":::

1. 예약된 새로 고침의 기본 상태는 **꺼짐** 입니다. 예약된 새로 고침을 사용하려면 화면 상단의 토글을 **켜짐** 으로 변경합니다.

1. **매주**(기본값) 및 **매일** 새로 고침 중에서 선택합니다. 매주 새로 고침을 예약하려면 새로 고침을 실행할 날짜를 하나 이상 선택합니다.

1. **표준 시간대** 를 설정한 다음 **시간** 드롭 다운 메뉴에서 새로 고침 타이밍을 설정합니다. 하루에 여러 번 새로 고침을 예약하려면 **다른 시간 추가** 를 선택합니다.

1. **저장** 을 선택하여 변경 내용을 적용합니다.

[!INCLUDE [footer-include](includes/footer-banner.md)]
