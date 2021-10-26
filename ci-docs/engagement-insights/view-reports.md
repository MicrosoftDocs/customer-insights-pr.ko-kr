---
title: 데이터 보고서 보기
description: 사용 가능한 보고서를 사용하여 사이트의 실시간 활동을 확인하세요.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 5ccdcb47db597154cf79b9f2e8fc238ab75dfde9
ms.sourcegitcommit: d9965f4bfc09391698a34042f6b44367e53819e3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2021
ms.locfileid: "7582930"
---
# <a name="view-reports"></a>보고서 보기

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

보고서는 SDK를 통해 수집된 데이터를 사용하는 데이터 시각화 모음으로, 사용자 행동을 측정하고 이해하는 데 도움이 됩니다. Dynamics 365 Customer Insights 참여 인사이트에는 웹 및 모바일 프로젝트에 대한 기본 제공(OOB) 보고서가 포함됩니다.  

## <a name="web-reports"></a>웹 보고서

왼쪽 탐색 창의 **검색** 에서 웹 보고서에 액세스할 수 있습니다.

:::image type="content" source="media/report-menu.png" alt-text="사용 가능한 보고서 목록을 표시하는 탐색.":::

### <a name="real-time-usage-report"></a>실시간 사용량 보고서

**실시간 사용량** 보고서는 매분 자동으로 새로 고침되는 사이트의 현재 활동에 대한 개요를 제공합니다. 실시간 사용량을 사용하여 사이트 트래픽에 대한 마케팅 캠페인, 언론 이벤트 및 기타 시나리오의 영향을 모니터링합니다.

### <a name="key-metrics-reports"></a>주요 메트릭 보고서

- **페이지 뷰** 에는 선택한 시간 프레임에 대한 총 페이지 뷰 수와 함께 개별 페이지의 페이지 뷰가 나열되어 있습니다.

- **방문** 은 방문 횟수 및 방문 시간에 대한 정보를 표시합니다.

- **방문자** 는 사이트의 신규 및 재방문 고유 방문자에 대해 알려줍니다.

### <a name="content-reports"></a>콘텐츠 보고서

- **연결** 은 클릭 수 및 유형에 대한 정보를 표시합니다.

- **페이지 종료** 는 방문자가 사이트를 종료하기 위해 클릭한 링크를 나열합니다.

### <a name="traffic-sources-reports"></a>트래픽 소스 보고서

- **추천인** 은 방문자를 귀하의 사이트로 유도한 도메인 및 URL을 나열합니다.

- **추적 코드** 는 방문자를 사이트로 유도한 링크의 추적 코드에 대한 세부 정보를 제공합니다.

### <a name="visitor-profiles-reports"></a>방문자 프로필 보고서

- **디바이스** 는 사이트에 액세스하는 데 사용된 물리적 디바이스를 나열합니다.

- **OS 및 브라우저** 는 사이트에 액세스할 때 실행 중이던 운영 체제 및 브라우저에 대한 인사이트를 제공합니다.

- **위치** 는 국가, 지역 및 도시별로 방문자에 대한 정보를 표시합니다.

- **언어** 는 방문자가 선호하는 언어별로 페이지 뷰를 나열합니다.

## <a name="mobile-reports"></a>모바일 보고서

모바일 보고서는 실시간 사용량, 앱 및 사용자 범주로 그룹화됩니다. 왼쪽 탐색 창의 **검색** 에서 모바일 보고서에 액세스할 수 있습니다.   

:::image type="content" source="media/mobile-reports.png" alt-text="데이터를 차트 및 목록으로 렌더링하는 실시간 사용 보고서를 보여주는 참여 인사이트의 사용자 인터페이스입니다.":::   

### <a name="real-time-usage"></a>실시간 사용량

**실시간 사용량** 은 1분마다 자동으로 새로 고침되는 모바일 앱의 현재 활동에 대한 개요를 제공합니다. 실시간 사용량을 사용하여 앱에서 현재 활성화된 사용자 및 세션 수와 상위 화면 보기를 모니터링합니다.

### <a name="app-reports"></a>앱 보고서

- **화면 보기** 는 앱의 개별 화면에 대한 화면 보기와 선택한 시간 프레임의 총 화면 보기 수를 나열합니다. 화면 이름 또는 화면 제목별로 화면 보기를 볼 수 있습니다.

- **세션** 은 세션 및 세션 길이에 대한 정보를 표시합니다.

- **재방문 빈도** 는 마지막 세션 이후 일 수로 세션 수를 그룹화합니다.

- **사용자** 는 모바일 앱에서 신규 및 재방문 사용자를 보여줍니다.

- **이벤트** 는 앱에서 수집된 모든 이벤트와 각 이벤트의 총 개수를 나열합니다.

### <a name="user-reports"></a>사용자 보고서

- **앱 버전** 은 사용자층이 사용 중인 모바일 앱의 버전을 나열합니다.

- **디바이스 및 OS 버전** 은 모바일 앱을 실행하는 디바이스 및 운영 체제에 대한 인사이트를 제공합니다.

- **위치** 는 국가, 지역 및 도시별로 앱 사용자에 대한 정보를 표시합니다.

## <a name="filter-by-time-or-date-range"></a>시간 또는 날짜 범위로 필터링

웹 또는 모바일 보고서에서 시간 프레임 또는 기간을 선택하여 값이나 기간에 집중할 수 있습니다. 

- 시간 프레임를 선택하려면 보고서 보기의 오른쪽 상단 모서리에 있는 보고서의 드롭다운 목록에서 값을 선택합니다. **고정 날짜 범위** 를 선택할 수도 있습니다. 

  :::image type="content" source="media/filter-by-time.png" alt-text="시간 또는 날짜 범위로 필터링.":::   

- 대부분의 보고서의 경우 차트 또는 목록에서 값을 선택하여 보고서를 필터링합니다.

> [!NOTE]
> 실시간 사용량 보고서에 대해 시간 범위 선택이 사용 중지됩니다. 실시간 사용 보고서의 시간 범위는 "지금"입니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
