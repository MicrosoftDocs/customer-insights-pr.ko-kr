---
title: 새 작업 영역 만들기
description: 작업 영역의 목적과 새 작업 영역을 만드는 방법.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 816f948331a06794c15000eb779f93cc7fdda202
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645318"
---
# <a name="create-a-new-workspace-and-add-members"></a>새 작업 영역을 만들고 구성원 추가

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

작업 영역은 실시간으로 사용자 활동을 확인하여 대상 그룹를 더 잘 이해할 수있는 방법입니다. 이벤트 및 보고서를 저장하고 관리하는 곳입니다.

작업 영역을 만들 때 집중할 데이터 유형을 선택합니다. 언제든지 다른 사용자 또는 구성원을 기존 작업 영역에 추가할 수 있습니다. 

## <a name="create-a-new-workspace"></a>새 작업 영역 만들기

작업 영역을 만드는 과정에는 작업 영역을 구성하기 위한 *환경* 설정 작업이 포함됩니다. 환경은 하나 이상의 작업 영역을 포함할 수 있는 공간입니다. 환경을 사용하여 작업 영역 및 Customer Insights 대상 그룹 인사이트 기능에 대한 연결을 관리할 수 있습니다.

1. 작업 영역 전환기에서 **새로 만들기** 를 선택합니다.

   :::image type="content" source="media/new-workspace.png" alt-text="탐색 창 및 설명에 설명이 있는 Customer Insights 페이지.":::

1. **작업 영역** 창에서 **작업 영역 이름** 을 입력합니다.

   :::image type="content" source="media/workspace-name.png" alt-text="작업 영역 이름 입력.":::

1. 측정하려는 플랫폼 유형(웹 또는 모바일)을 선택합니다.

1. **고급 설정 표시** 를 선택하여 다음과 같은 선택적 설정을 사용하거나 사용 중지합니다.

   - **처음부터 알아보기** 로 전환하여 웹 이벤트를 이전에 인증한 사용자와 연결합니다. 자세한 내용은 [이전에 인증된 방문자의 웹 이벤트 인](unknown-to-known.md)식을 참조하세요.
   - 이 작업 영역에 대한 봇의 웹 트래픽을 제거하려면 **봇 트래픽 필터링** 을 "사용"으로 전환합니다. 

1. 완료되면 **완료** 를 선택합니다. 

1. 코드 조각을 설치하여 데이터 수신을 시작한 다음 **마침** 을 선택하여 작업 영역을 만듭니다. 자세한 내용은 [개발자 리소스 개요](developer-resources.md)를 참조하십시오.

> [!NOTE]
> 이제 **역할** 목록에서 구성원을 추가하고 권한 수준을 할당할 수 있습니다. 자세한 내용은 [역할 및 권한](user-roles.md)을 참조하세요. 

자세한 내용은 [환경 및 작업 영역 관리](manage-environments-workspaces.md)를 참조하세요.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
