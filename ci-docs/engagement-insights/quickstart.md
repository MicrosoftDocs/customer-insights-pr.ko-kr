---
title: 제품 소개 빠른 시작
description: 참여 인사이트 기능을 설정하기 위한 최초 실행 경험.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 11/05/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 95caaa1f67a7740328b67face00acaea65452eb0
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494465"
---
# <a name="first-run-experience"></a>첫 실행 환경

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dynamics 365 Customer Insights의 기능인 참여 인사이트를 사용하면 웹 사이트에서 고객 행동을 수집하고 측정할 수 있습니다. 이 문서에서는 참여 인사이트에 등록하고, 작업 영역을 설정하고, 여기에 구성원을 추가하고, 변경하는 방법을 설명합니다.

## <a name="sign-up-for-a-demo-of-engagement-insights"></a>참여 인사이트 데모 등록

활성 Microsoft Azure Active Directory 사용자 계정이 있어야 합니다. 

1. [참여 인사이트](https://home.ci.ai.dynamics.com/app/engagement-insights) 웹 사이트를 엽니다. 

1. 학교 또는 회사 계정을 사용하여 로그인합니다.

1. 지역을 선택하고 확인란을 사용하여 이메일을 통해 업데이트 및 제안을 수신할 것인지 여부를 표시하세요.

1. **참여 인사이트(프리뷰) 사용 약관** 및 **개인정보처리방침** 을 검토한 다음 **데모 탐색** 을 선택하여 동의합니다.

1. 샘플 데이터 집합을 사용하여 제품을 탐색합니다. 

## <a name="set-up-your-first-workspace-in-engagement-insights"></a>참여 인사이트에 첫 번째 작업 영역 설정

작업 영역은 이벤트와 보고서를 저장하고 관리하는 방법입니다.

첫 번째 작업 영역을 만들려면

1. 참여 인사이트에서 **데이터 연결** 을 선택하여 마법사를 시작합니다. 

:::image type="content" source="media/banner.png" alt-text="데이터 연결 단추가 있는 Customer Insights 페이지.":::

2. 새 작업 영역에서 측정할 활동 유형을 선택하세요. 현재 **웹 사이트 활동** 만 사용할 수 있습니다. **앱 활동** 및 **디바이스 활동** 은 향후 릴리스에서 사용할 수 있습니다.

1. **다음** 을 선택하여 작업 영역을 확인하고 만듭니다.

1. 웹 사이트에 코드 조각을 추가하여 참여 인사이트에서 데이터를 수신하세요. 이를 즉시 구현하거나 웹 사이트 관리자와 코드 및 지침을 공유할 수 있습니다. 나중에 코드 조각을 찾으려면 **관리** > **작업 영역** > **설치 가이드** 로 이동하세요.

   > [!IMPORTANT]
   > 웹 사이트에 코드가 구현될 때까지 데이터가 작업 영역에 표시되지 않습니다.

1. **완료** 를 선택하여 새 작업 영역을 엽니다. 

## <a name="add-members-to-an-existing-workspace"></a>기존 작업 영역에 구성원 추가

기본적으로 작업 영역을 만든 사람만 액세스할 수 있습니다. 언제든지 조직의 다른 사용자를 기존 작업 영역에 추가할 수 있습니다.

:::image type="content" source="media/add-members.png" alt-text="구성원 추가 단추에 설명선이 있는 구성원 페이지.":::

1. **관리** > **작업 영역** > **구성원** 으로 이동합니다.

2. **구성원 추가** 를 선택합니다. **구성원** 상자를 사용하여 조직의 다른 사람을 추가합니다. 한 번에 여러 구성원을 추가할 수 있습니다.

3. 새 구성원에게 할당할 **역할** 을 선택합니다. 현재는 **작업 영역 관리자** 만 선택할 수 있습니다. 향후 릴리스에서 다른 역할이 추가될 예정입니다.

4. 확인하려면 **구성원 추가** 를 선택합니다.

작업 영역에서 구성원을 제거하려면 **구성원** 페이지의 구성원 이름 옆에 있는 **...** 기호를 선택하고 드롭다운 메뉴에서 **삭제** 를 선택합니다.

## <a name="edit-a-workspace"></a>작업 영역 편집

언제든지 기존 작업 영역의 세부 정보를 편집할 수 있습니다.

:::image type="content" source="media/change-workspace-settings.png" alt-text="작업 영역 이름 및 설명에 설명이 있는 작업 영역 설정 페이지.":::

1. **관리** > **작업 영역** > **설정** 으로 이동합니다.

1. 작업 영역의 **이름** 을 변경합니다.

1. **저장** 을 선택하여 변경 내용을 적용합니다.

## <a name="add-another-new-workspace"></a>새 작업 영역 추가

:::image type="content" source="media/workspace-switcher.png" alt-text="탐색 창 및 설명에 설명이 있는 Customer Insights 페이지.":::

추가 작업 영역을 만들어 데이터를 분류할 수 있습니다.

1. 작업 영역 선택기에서 **새 작업 영역** 을 선택합니다.

1. **이름** 과 **설명**(선택 사항)을 입력합니다.

1. **만들기** 를 선택합니다.

## <a name="switch-between-workspaces"></a>작업 영역 간 전환

작업 영역 간에 변경하려면 작업 영역 전환기를 선택합니다. 새 작업 영역을 만들거나 **웹 샘플** 을 선택하여 보고서를 보고 샘플 데이터를 사용하여 기능을 사용해 볼 수도 있습니다. 



[!INCLUDE[footer-include](../includes/footer-banner.md)]