---
title: 사용자 권한 관리
description: 사용 권한 및 사용자 역할에 대해 알아봅니다.
ms.date: 02/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-permissions
- ci-system-security
- customerInsights
ms.openlocfilehash: 30b37645cad4e795ef20579e20e3f2bbdb2afbf6
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054882"
---
# <a name="manage-user-permissions"></a>사용자 권한 관리

**권한** 페이지는 Customer Insights 사용을 위한 역할과 권한을 설정하는 곳입니다.

페이지를 보려면 관리자 권한이 있어야 합니다. 권한 페이지에 액세스하려면 **관리** > **보안** > **사용자** 로 이동하십시오.

역할에는 다음 세 가지 유형이 있습니다.

## <a name="viewer"></a>뷰어

- **홈** 및 **세그먼트** 페이지 내에서 인사이트와 세그먼트를 탐색합니다.
- **고객** 페이지를 사용하여 고객 프로필을 검색하고 필터링합니다. 필드는 검색이 가능해야 합니다.
- **보강** 페이지를 보고 탐색합니다.
- **엔터티** 페이지를 사용하여 엔터티를 탐색하고 내보냅니다.
- **시스템** 페이지를 사용하여 시스템 프로세스의 상태를 봅니다.
- **내보내기** 페이지에서 내보내기를 봅니다.
- **Power BI Customer Insights** 대시보드를 설치하고 사용합니다.

## <a name="contributor"></a>참가자

- 뷰어에서 사용할 수 있는 모든 권한입니다.
- **데이터 원본** 페이지를 사용하여 데이터를 로드하고 변환합니다.
- ***데이터 통합** 을 완료하면 통합 고객 프로필 엔터티가 됩니다.
- **관계** 및 **활동** 을 정의합니다.
- **세그먼트** 페이지를 사용하여 세그먼트를 만듭니다.
- **측정값** 페이지를 사용하여 측정값을 만듭니다.
- **보강** 페이지에서 구성을 관리하고 고객 프로필을 보강합니다(자사 보강만 해당).
- 기여자와 공유된 연결을 기반으로 내보내기를 관리하고 만듭니다. [관리자가 기여자가 내보내기에 연결을 사용하도록 허용하는 방법에 대해 자세히 알아보세요.](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>관리자

- 참가자가 사용할 수 있는 모든 권한입니다.
- 시스템 프로세스의 작업 언어 및 새로 고침 일정을 포함하여 **시스템** 페이지에서 설정을 변경합니다.
- **권한** 페이지를 사용하여 권한을 보고 추가합니다.
- **검색 및 필터 인덱스** 페이지(**고객** 페이지를 통해 액세스할 수 있음)를 사용하여 고객 페이지에 대한 검색 및 필터 정의를 설정합니다.
- 연결을 관리하고 **연결** 페이지에서 다른 사용자 역할에 허용하세요.
- **보강** 페이지에서 구성을 관리하고 고객 프로필을 보강합니다(모든 보강용).
- **내보내기** 페이지에서 내보내기를 관리하고 만듭니다.
- **고객 카드 추가 기능** 을 설치하고 사용합니다.
- **Power Apps 커넥터** 를 추가하고 사용합니다.
- [Customer Insights API](apis.md)의 사용을 설정합니다.
- 다른 관리자에게 [환경 소유권을 할당](manage-environments.md#change-the-owner-of-an-environment)합니다.

## <a name="admin-owner"></a>관리자(담당자)

- 관리자가 사용할 수 있는 모든 권한입니다.
- 환경을 [초기화 및 삭제](manage-environments.md#reset-an-existing-environment-preview)합니다.

## <a name="assign-roles-and-permissions"></a>역할 및 사용 권한 할당

1. **관리자** > **보안** > **사용자***로 이동합니다.

1. **사용자 추가** 를 선택하여 **권한 추가/편집** 창을 엽니다.

1. **검색** 필드를 사용하여 권한을 조정하려는 Azure Active Directory 사용자 또는 그룹을 찾습니다. **역할** 을 선택하여 해당 사용자 또는 그룹에 할당합니다.

1. **저장** 을 선택합니다. 현재 환경은 권한을 변경한 그룹의 사용자 또는 구성원과 자동으로 공유됩니다. 사용자는 Customer Insights 앱에 액세스하고 지정된 역할에 따라 작업할 수 있습니다.

## <a name="view-current-permissions"></a>현재 사용 권한 보기

**관리자** > **보안** > **사용자** 로 이동하여 현재 어떤 역할 할당이 활성화되어 있는지 확인합니다.

- **유형** 열은 단일 사용자, 그룹 또는 응용 프로그램을 지정합니다. 시스템은 개별 사용자 및 그룹을 지원합니다.
- 역할은 **역할** 열 아래에 지정됩니다.
- 열 제목을 선택하여 해당 열 값으로 결과를 정렬합니다.
- 페이지 상단의 **검색** 필드를 사용하여 특정 사용자를 찾습니다.


[!INCLUDE [footer-include](includes/footer-banner.md)]
