---
title: 사용자 권한 할당
description: 사용 권한 및 사용자 역할에 대해 알아봅니다.
ms.date: 08/08/2022
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
ms.openlocfilehash: a59a672b6f7e1e67c2162ea14bb9860df0d551aa
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245427"
---
# <a name="assign-user-permissions"></a>사용자 권한 할당

Customer Insights에 대한 액세스는 관리자가 애플리케이션에 추가한 조직의 사용자로 제한됩니다. 관리자는 사용자를 추가, 수정, 삭제할 수 있습니다. 사용자는 단일 사용자, 그룹 또는 응용 프로그램일 수 있습니다. 사용자의 역할로는 다음의 세 가지 유형이 있습니다.

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
- **데이터를 통합** 하면 통합 고객 프로필 엔터티가 생성됩니다.
- **관계** 및 **활동** 을 정의합니다.
- **세그먼트** 페이지를 사용하여 세그먼트를 만듭니다.
- **측정값** 페이지를 사용하여 측정값을 만듭니다.
- **보강** 페이지에서 구성을 관리하고 고객 프로필을 보강합니다(자사 보강만 해당).
- [기여자와 공유된 연결](connections.md#allow-contributors-to-use-a-connection-for-exports)을 기반으로 내보내기를 관리하고 만듭니다.

## <a name="admin"></a>관리자

- 참가자가 사용할 수 있는 모든 권한입니다.
- 시스템 프로세스의 작업 언어 및 새로 고침 일정을 포함하여 **시스템** 페이지에서 설정을 변경하고 진단 로그를 내보냅니다.
- 사용자, API 키, 프라이빗 링크 및 키 자격 증명 모음 등 **보안** 페이지에서 설정을 변경합니다.
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

## <a name="add-users"></a>사용자 추가

1. **관리자** > **보안** 으로 이동하여 **사용자** 탭을 선택합니다.

1. **사용자 추가** 를 선택하여 **권한 추가/편집** 창을 엽니다.

1. **검색** 필드를 사용하여 추가하려는 Azure Active Directory 사용자 또는 그룹을 찾습니다. **역할** 을 선택하여 해당 사용자 또는 그룹에 할당합니다.

1. **저장** 을 선택합니다. 현재 환경은 그룹의 사용자 또는 구성원과 자동으로 공유됩니다. 사용자는 Customer Insights 앱에 액세스하고 지정된 역할에 따라 작업할 수 있습니다.

## <a name="view-current-permissions"></a>현재 사용 권한 보기

**관리자** > **보안** 으로 이동하여 **사용자** 탭을 선택하고 활성 사용자 및 해당 역할 할당 목록을 봅니다. 열을 기준으로 사용자 목록을 정렬하거나 검색 상자를 사용하여 특정 사용자를 찾을 수 있습니다.

## <a name="manage-current-users"></a>현재 사용자 관리

**관리자** > **보안** 으로 이동하여 **사용자** 탭을 선택합니다. 열을 기준으로 사용자 목록을 정렬하거나 검색 상자를 사용하여 관리하려는 사용자를 찾을 수 있습니다.

사용 가능한 작업을 보려면 사용자를 선택합니다.

- **수정** 을 통해 Customer Insights에서 사용자의 역할을 수정합니다. **저장** 을 선택하여 변경 사항을 확인합니다.
- **제거** 를 통해 사용자가 Customer Insights에 액세스하지 못하도록 제거합니다. **삭제** 를 선택하여 확인합니다.

[!INCLUDE [footer-include](includes/footer-banner.md)]
