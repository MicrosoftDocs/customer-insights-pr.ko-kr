---
title: 새 환경 만들기
description: 환경의 목적과 새 작업 영역을 만드는 방법.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 8ff04a6b2ffbd513a77f7f8a33358f3d8f559c7e
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673650"
---
# <a name="create-a-new-environment"></a>새 환경 만들기 

## <a name="overview"></a>개요

환경은 작업 영역과 연결을 관리하는 공간입니다. 환경을 사용하는 방법은 조직과 사용 사례에 따라 다릅니다. 이렇게 만들 수 있는 작업의 예는 다음과 같습니다.

- 단일 환경.
- 테스트 및 프로덕션을 위한 별도의 환경.
- 각 대상 그룹에 대한 관련 이벤트를 포함하는 조직의 특정 팀 또는 부서를 위한 별도의 환경.
- 회사의 여러 글로벌 지점을 위한 별도의 환경.
- Customer Insights 대상 그룹 인사이트 기능에 연결.

## <a name="create-a-new-environment"></a>새 환경 만들기

1. 기본 배너의 오른쪽에서 환경 선택기를 선택한 다음 **+새로 만들기** 를 선택합니다.

   :::image type="content" source="media/environment-picker.png" alt-text="환경 선택기 선택.":::

1. **설정** 창에서 **환경 이름** 을 입력합니다.

1. 플랜 유형에 따라 계정 **유형** 을 선택합니다.

1. **지역** 을 선택하고 **다음** 을 선택합니다. 

1. 특정 웹 사이트 또는 앱에 대한 데이터를 수집할 수 있는 **작업 영역 이름** 을 입력합니다. 자세한 내용은 [작업 영역 만들기](create-workspace.md)를 참조하세요.

1. 만들려는 **작업 영역 유형**(웹 또는 모바일)을 선택합니다. 

1. **고급 설정 표시** 를 선택하여 다음과 같은 선택적 설정을 사용하거나 사용 중지합니다.

   - **처음부터 알아보기** 로 전환하여 웹 이벤트를 이전에 인증한 사용자와 연결합니다. 자세한 내용은 [이전에 인증된 방문자의 웹 이벤트 인식](unknown-to-known.md)을 참조하십시오.
   - 이 작업 영역에 대한 봇의 웹 트래픽을 제거하려면 **봇 트래픽 필터링** 을 "사용"으로 전환합니다. 

1. 완료되면 **완료** 를 선택합니다. 

1. 코드 조각을 설치하여 데이터 수신을 시작한 다음 **마침** 을 선택하여 작업 영역을 만듭니다. 자세한 내용은 [개발자 리소스 개요](developer-resources.md)를 참조하십시오.

> [!NOTE]
> 이제 **역할** 목록에서 구성원을 추가하고 권한 수준을 할당할 수 있습니다. 자세한 내용은 [역할 및 권한](user-roles.md)을 참조하세요. 

자세한 내용은 [환경 및 작업 영역 관리](manage-environments-workspaces.md)를 참조하세요.

## <a name="work-with-your-new-environment"></a>새로운 환경에서 작업

- [작업 영역을 만들고](../engagement-insights/create-workspace.md) 구성원을 추가합니다.
- [웹 사이트에 코드를 추가](../engagement-insights/instrument-website.md)하거나 [모바일 앱](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps)에 코드를 추가합니다.
- [실시간 보고서](../engagement-insights/view-reports.md)를 보거나 [사용자 지정 보고서](../engagement-insights/custom-reports.md)를 작성합니다.
- [내보내기를 위한 개선된 이벤트를 만들고 내보냅니다](../engagement-insights/refined-events.md).
- Data Lake Storage로 [데이터를 내보냅니다](../engagement-insights/export-events.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
