---
title: 작업 영역 및 환경 관리
description: 작업 영역 및 환경 생성, 이름 변경 및 삭제하는 방법입니다
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 09/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: a5b48db5ae23ea65bf608d67348d493bfdc7678f
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486043"
---
# <a name="manage-environments-and-workspaces"></a>환경 및 작업 영역 관리

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>개요

작업 영역은 이벤트와 보고서를 저장하고 관리하는 공간입니다. 사용자 활동을 실시간으로 볼 수 있는 곳입니다. 작업 영역을 만들 때 작업 영역으로 보낼 데이터 유형을 선택합니다. 현재 웹 데이터 및 모바일 앱이 지원됩니다.

환경은 작업 영역과 연결을 관리하는 공간입니다. 환경을 사용하는 방법은 조직과 사용 사례에 따라 다릅니다. 이렇게 만들 수 있는 작업의 예는 다음과 같습니다.

-   단일 환경.
-   테스트 및 프로덕션을 위한 별도의 환경.
-   각 대상 그룹에 대한 관련 이벤트를 포함하는 조직의 특정 팀 또는 부서를 위한 별도의 환경.
-   회사의 여러 글로벌 지점을 위한 별도의 환경.
-   Customer Insights 대상 그룹 인사이트 기능에 연결.

## <a name="choose-an-environment-and-create-a-workspace"></a>환경 선택 및 작업 영역 만들기 

모든 작업 영역은 환경에 있어야 합니다. 기존 환경을 선택하거나 작업 영욕을 만들 때 새로 만들 수 있습니다. 그런 다음 작업 영역 구성원을 추가하고 데이터 수집을 시작할 수 있습니다.

**첫 번째 작업 영역을 만들려면**

1. 참여 인사이트의 작업 영역 전환기에서 **새로 만들기** 를 선택합니다. 

   :::image type="content" source="media/New-workspace.png" alt-text="Customer Insights 페이지 작업 영역 선택기.":::

1. 목록에서 환경을 선택하거나 **새 환경 만들기** 를 선택합니다.

1. **작업 영역 이름** 에서 이름을 입력합니다. 

1. 웹 사이트 또는 모바일 앱에서 발생하는 상황을 측정할지 여부에 따라 생성하려는 환경 유형을 선택합니다. 

1. **역할** 목록에서 구성원을 추가하고 권한 수준을 할당할 수 있습니다. 그런 다음 **완료** 를 선택하여 작업 영역을 생성하거나 **다음** 을 선택하여 코드를 설치합니다. 

1. 코드 조각을 설치하여 데이터 수신을 시작한 다음 **완료** 를 선택합니다. 

## <a name="manage-a-workspace"></a>작업 영역 관리

한 환경에서 동시에 여러 작업 영역을 유지할 수 있습니다. [역할](user-roles.md)에 따라 작업 방법이 결정됩니다. 

 - 작업 영역을 관리하려면 환경 관리자 또는 작업 영역 관리자여야 합니다.
 - 작업 영역 관리자는 기존 작업 영역의 이름을 바꾸거나 삭제할 수 있습니다. 

### <a name="edit-a-workspace-name"></a>작업 영역 이름 편집

1. **관리** > **작업 영역** 으로 이동하고 **설정** 을 선택합니다.

1. **작업 영역 이름** 상자에 새 이름을 입력합니다.

1. **저장** 을 선택하여 변경 내용을 적용합니다.

### <a name="delete-a-workspace"></a>작업 영역 삭제

작업 영역을 삭제하면 포함된 모든 콘텐츠, 데이터, 설정 및 권한이 영구적으로 삭제됩니다. 이 작업은 실행 취소할 수 없습니다.

1. **관리** > **작업 영역** 으로 이동하고 **설정** 을 선택합니다.

1. **작업 영역 삭제** 를 선택합니다. 

1. **작업 영역 삭제** 대화 상자에서 **CONFIRM DELETE** 를 입력합니다. 

1. 작업 영역을 영구적으로 삭제하려면 **삭제** 를 선택하세요.

### <a name="manage-workspace-members"></a>작업 영역 구성원 관리

1. **관리** > **작업 영역** 으로 이동하고 **구성원** 을 선택합니다.

1. **구성원 추가** 를 선택하여 액세스 권한을 부여하고 [역할을 할당](user-roles.md)합니다. 현재는 **작업 영역 관리자** 만 사용할 수 있습니다.

1. **구성원 추가** 를 선택하여 작업 영역에 추가합니다.

## <a name="manage-an-environment"></a>환경 관리

환경 관리자는 왼쪽 탐색 창에서 환경에 액세스할 수 있습니다. 환경 설정, 기타 환경 관리자 및 작업 영역을 구성할 수 있습니다. 관리 센터의 다른 영역간에 이동하려면 탭을 선택하세요.

:::image type="content" source="media/New-environment.png" alt-text="환경 관리 센터 설정.":::

### <a name="create-an-environment"></a>환경 만들기

1. 작업 영역 선택기에서 **+새로 만들기** 를 선택합니다.

1. 안내 환경에서 **환경** 드롭다운 메뉴를 열고 **새 환경 만들기** 를 선택합니다. 

1. **환경 이름** 을 제공합니다.

   :::image type="content" source="media/create-environment.png" alt-text="환경 세부 정보를 지정하려면 안내 환경을 단계적으로 진행합니다.":::

1. **지역** 을 선택하고 **다음** 을 선택합니다. 

1. 작업 영역 이름을 제공하고 생성할 작업 영역 유형을 선택합니다. 

1.  선택적으로 구성원을 추가하고 코드 조각 코드를 복사하여 생성 프로세스를 완료합니다.

### <a name="rename-an-environment"></a>환경의 이름 바꾸기

1. **관리** > **환경** 으로 이동하고 **설정** 을 선택합니다.

1. **환경 이름** 을 업데이트하고 **저장** 을 선택하여 변경 사항을 적용합니다.

### <a name="manage-environment-members"></a>환경 구성원 관리

1. **관리** > **환경** 으로 이동하고 **구성원** 을 선택합니다.

1. **구성원 추가** 를 선택하여 구성원을 업데이트하고 [역할을 할당](user-roles.md)합니다. 현재는 **환경 관리자** 만 사용할 수 있습니다.

1. **구성원 추가** 를 선택하여 환경에 추가합니다.

### <a name="delete-an-environment"></a>환경 삭제

환경 관리자는 환경을 삭제할 수 있습니다. 환경을 삭제하려면 먼저 환경 아래에 있는 모든 작업 영역을 제거해야 합니다.

1. **관리** > **환경** 으로 이동하고 **설정** 을 선택합니다.

1. **환경 삭제** 를 선택합니다. 

1. **작업 영역 삭제** 대화 상자에서 **CONFIRM DELETE** 를 입력합니다. 

1. 환경을 영구적으로 삭제하려면 **삭제** 를 선택하십시오.

## <a name="manage-connections"></a>연결 관리

대상 그룹 인사이트에 대한 연결을 설정하면 통합 고객 프로필을 기반으로 한 참여 인사이트에서 보고서를 볼 수 있습니다. 

자세한 정보는 [대상 그룹 인사이트와 참여 인사이트 사이에 링크 만들기](integrate-audience-insights-engagement-insights.md)를 참조하십시오.

## <a name="manage-personal-data"></a>개인 데이터 관리

고객의 개인 데이터를 보호하기 위해 최종 사용자 식별 데이터를 삭제하거나 내보낼 수 있습니다.

자세한 내용은[ 개인 정보가 포함 된 이벤트 데이터 삭제 및 내보내기](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
