---
title: Dynamics 365 Customer Insights의 Teams 봇(미리 보기)
description: 봇의 도움을 받아 Microsoft Teams에서 통합 고객 프로필을 찾아보세요.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195850"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Dynamics 365 Customer Insights의 Teams 봇(미리 보기)

Microsoft Teams에 연결하여 봇이 Teams 채널에서 통합 고객 프로필을 조회할 수 있도록 합니다.

:::image type="content" source="media/teams-bot.png" alt-text="고객 레코드를 보여주는 Teams 봇":::

## <a name="prerequisites"></a>전제 조건

- 하나 이상의 [데이터 원본이 추가](data-sources.md)되어야 합니다.
- [통합 프로세스](data-unification.md)가 완료되어야 합니다.
- 필드가 [검색 및 필터 색인](search-filter-index.md)에 추가되어야 합니다.
- Customer Insights와 Teams가 같은 조직에 있습니다.
- 환경에는 개별 고객으로 설정된 기본 대상 그룹 고객이 있습니다. 비즈니스 계정은 지원되지 않습니다.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>봇 구성

1. **관리자** > **연결** 로 이동합니다.
1. Microsoft Teams 타일에서 **설정** 을 선택합니다.
1. Teams의 **앱** 영역으로 리디렉션됩니다. Teams를 열고 왼쪽 하단에서 **앱** 을 선택하거나 [AppSource에서 직접 얻을](https://go.microsoft.com/fwlink/?linkid=2124104) 수도 있습니다.
1. **Customer Insights** 를 검색해 앱을 선택하십시오.
1. **추가** 를 선택합니다.
1. Teams의 Customer Insights에 로그인합니다. 환영 메시지가 표시됩니다.

## <a name="things-you-can-do-with-the-bot"></a>봇으로 할 수 있는 작업

봇은 통합 고객 프로필을 위한 조회 기능을 제공합니다.

- **검색** 을 입력하고 검색 및 필터 색인에 추가되는 통합 고객 프로필의 이름, 이메일 주소 또는 기타 필드를 입력합니다.

  결과 고객 프로필에서 최대 15개의 필드가 있는 카드를 받습니다. 여러 개의 일치 항목은 프로필을 선택할 수 있는 결과 목록을 반환합니다. 정확한 일치 결과를 찾으려면 검색 용어를 큰 따옴표로 묶어 추가합니다.

- 귀사의 경우 동일한 조직에서 여러 Customer Insights 환경을 유지 관리하는 경우 **switchinstance** 를 입력하여 봇을 연결할 환경을 선택할 수 있습니다.

- **도움말** 을 입력하여 봇에 사용 가능한 명령 목록을 봅니다.  

[!INCLUDE [footer-include](includes/footer-banner.md)]