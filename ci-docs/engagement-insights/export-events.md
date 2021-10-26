---
title: 개선된 이벤트 내보내기
description: 개선된 이벤트 및 기본 이벤트를 내보내는 방법.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7881f8f63134170a7f76e3c75dcfc5fa8930754b
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606236"
---
# <a name="export-events"></a>이벤트 내보내기

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

이벤트는 사용자 행동을 나타냅니다. 이는 사용자가 페이지(이벤트 보기)를 보거나 콘텐츠(작업 이벤트)와 상호 작용할 때 기록합니다. 보고서에 표시할 데이터의 속성을 결정할 수 있는 경우이 데이터 가상 보기를 *개선된 이벤트* 라고 합니다. 자세한 내용은 [이벤트 만들기 및 수정](refined-events.md)을 참조하세요.

- 이벤트 및 개선된 이벤트를 외부 저장소로 내보낼 수 있습니다. 
- 내보내기는 정방향 데이터 스트림입니다. 스트림은 다시 채울 수 없습니다. 
- 내보내기에는 고정된 스키마가 있습니다. 이벤트에 사용자 지정 속성을 추가하면 해당 속성이 포함되지 않습니다. 새 내보내기를 만들어야 합니다.

## <a name="prerequisites"></a>필수 조건

내보내기를 설정하기 전에 Azure Portal에 대한 액세스 권한과 활성 구독이 있어야 합니다. 내보내기 프로세스 중에 스토리지 계정 정보가 필요합니다. 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>Azure Data Lake Storage Gen 2 계정 만들기

1. Azure Portal에 로그인하고 [새 스토리지 계정을 만듭니다](/azure/storage/common/storage-account-create). 

1. **고급** 탭에서 **계층 구조 네임스페이스** 를 사용 설정했는지 확인합니다. 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="고급 탭에서 계층 구조 네임스페이스 사용.":::

1. 배포가 완료되면 새로 만든 스토리지 계정으로 이동합니다. 탐색 창에서 **설정** > **액세스 키** 를 선택합니다.. 

1. **계정 이름** 과 **키** 를 복사하여 새 내보내기를 만들 때 사용합니다.
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="스토리지 계정의 액세스 키.":::

## <a name="export-events"></a>내보내기 이벤트

**이벤트 내보내기** 대화 상자를 불러오는 방법은 두 가지입니다. 
- **데이터** > **전문가** 로 이동한 다음 **새로운 내보내기** 를 선택합니다.
- **데이터** > **이벤트** 로 이동하여 내보내려는 이벤트 옆의 **더 보기 [...]** 를 선택한 후 드롭다운 메뉴에서 **내보내기** 를 선택합니다. 

:::image type="content" source="media/new-export.png" alt-text="새 내보내기 만들기.":::

내보내기를 만드는 단계를 안내합니다.

1. **내보내기 이름** 을 제공하고 **다음** 을 선택합니다.

1. **이벤트 선택** 드롭다운 목록에서 내보내기에 포함할 기본 이벤트 및 정제된 이벤트를 선택합니다. 

1. **파일 구조** 섹션에서 케이던스(시간별 또는 매일)를 선택하여 대상 스토리지에 새 파일을 만들고 **다음** 을 선택합니다. 이벤트가 도착하면 지속적으로 내보내집니다.

1. **형식 선택** 대화 상자에서 내보내기 형식을 선택합니다. **Common Data Model**, **CSV** 및 **JSON** 형식 중에서 선택합니다. 다른 Dynamics 365 애플리케이션과 함께 내보내기를 사용하려면 **Common Data Model** 형식을 사용하는 것이 좋습니다.

1. **대상 선택** 대화 상자에서 Azure Data Lake Storage Gen 2 위치를 지정합니다.
    1. **ADLS Gen 2 계정 이름** 은 내보내기를 저장할 스토리지 계정의 이름입니다. 
    1. **폴더 경로** 내보내기가 파일 시스템에서 저장되어야 하는 위치와 스토리지 계정의 디렉터리 구조를 정의합니다.
    1. **공유 키** 스토리지 계정에 대한 Azure Portal에서 사용할 수 있습니다.

1. 선택 사항을 검토하고 확인하여 완료합니다.

## <a name="view-and-manage-exports"></a>디바이스 보기 및 관리

내보내기를 설정했으면 **데이터** > **내보내기** 에서 볼 수 있습니다. 기존 내보내기를 편집하거나 삭제하려면 **더 보기[...]** 를 선택합니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
