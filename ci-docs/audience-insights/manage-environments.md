---
title: 환경 만들기 및 관리
description: 서비스에 등록하는 방법과 환경을 관리하는 방법을 알아봅니다.
ms.date: 10/14/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: ce2fdd435a81bb04148057554c5958e3ab59f125
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645134"
---
# <a name="manage-environments"></a>환경 관리

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>환경 전환

페이지 오른쪽 상단의 **환경** 컨트롤을 선택하여 환경을 변경합니다.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="환경을 전환하는 컨트롤의 스크린샷.":::

관리자는 환경을 [생성](create-environment.md)하고 관리할 수 있습니다.

## <a name="edit-an-existing-environment"></a>기존 환경 편집

기존 환경의 세부 사항 중 일부를 편집할 수 있습니다.

1.  앱 헤더의 **환경** 선택기를 선택합니다.

2.  **편집** 아이콘을 선택합니다.

3. **환경 편집** 상자에서 환경 설정을 업데이트할 수 있습니다.

환경 설정에 대한 자세한 내용은 [새 환경 만들기](create-environment.md)를 참조하세요.

## <a name="copy-the-environment-configuration"></a>환경 구성 복사

새 환경을 생성할 때 기존 환경에서 구성을 복사하도록 선택할 수 있습니다. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="환경 설정의 설정 옵션 스크린샷.":::

조직에서 데이터를 복사할 수 있는 사용 가능한 모든 환경 목록이 표시됩니다.

다음 구성 설정이 복사됩니다.

- 수집한/가져온 데이터 원본
- 데이터 통합(맵, 일치, 병합) 구성
- 세그먼트
- 측정값
- 관계
- 활동 
- 검색 및 필터 인덱스
- 내보내기 대상
- 예약된 새로 고침
- 보강
- 모델 관리
- 역할 할당

다음 데이터는 복사되지 *않습니다*:

- 고객 프로필.
- 데이터 원본 자격 증명. 모든 데이터 원본에 대한 자격 증명을 제공하고 데이터 원본을 수동으로 새로 고쳐야 합니다.
- Common Data Model 폴더의 데이터 원본 및 Dataverse 관리형 Data Lake. 원본 환경에서와 동일한 이름으로 해당 데이터 원본을 수동으로 생성해야 합니다.

환경을 복사하면 새 환경이 생성되었다는 확인 메시지가 표시됩니다. **데이터 원본으로 이동** 을 선택하여 데이터 원본 목록을 볼 수 있습니다.

모든 데이터 원본에 **자격 증명 필요** 상태가 표시됩니다. 데이터 원본을 편집하고 자격 증명 정보를 입력하여 새로 고치십시오.

:::image type="content" source="media/data-sources-copied.png" alt-text="복사되어 인증이 필요한 데이터 소스 목록.":::

데이터 원본을 새로 고친 후 **데이터** > **통합** 으로 이동합니다. 원본 환경에서 설정을 확인할 수 있습니다. 필요에 따라 편집하거나 **실행** 을 선택하여 데이터 통합 프로세스를 시작하고 통합 고객 엔터티를 만듭니다.

데이터 통합이 완료되면 **측정** 및 **세그먼트** 로 이동하여 이들도 새로 고칩니다.

## <a name="reset-an-existing-environment"></a>기존 환경 초기화

모든 구성을 삭제하고 수집된 데이터를 제거하려는 경우 관리자로서 환경을 빈 상태로 재설정할 수 있습니다.

1.  앱 헤더의 **환경** 선택기를 선택합니다. 

2.  재설정하려는 환경을 선택하고 줄임표(**...**)를 선택합니다. 

3. **재설정** 옵션을 선택합니다. 

4.  삭제를 확인하려면 환경 이름을 입력하고 **초기화** 를 선택합니다.

## <a name="delete-an-existing-environment"></a>기존 환경 삭제

관리자는 관리하는 환경을 삭제할 수 있습니다.

1.  앱 헤더의 **환경** 선택기를 선택합니다.

2.  재설정하려는 환경을 선택하고 줄임표(**...**)를 선택합니다. 

3. **삭제** 옵션을 선택합니다. 

4.  삭제를 확인하려면 환경 이름을 입력하고 **삭제** 를 선택합니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
