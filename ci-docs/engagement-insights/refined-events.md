---
title: 이벤트 생성 및 수정
description: 이벤트 생성 및 수정 방법.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: dbafa2231daa82c34ee2ec8292111575e95af675
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228211"
---
# <a name="create-and-modify-events"></a>이벤트 생성 및 수정

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

이벤트는 웹 사이트에서의 활동과 같은 사용자 행동을 나타내는 데이터입니다.

- *기본* 이벤트는 사용자가 페이지(이벤트 보기)를 보거나 콘텐츠(작업 이벤트)와 상호 작용할 때 기록합니다.
- *개선된* 이벤트는 기본 이벤트의 가상 보기입니다. 속성을 제거 및 추가하거나 속성 값을 기준으로 이벤트를 필터링하여 개선된 이벤트를 정의합니다.

## <a name="prerequisites"></a>필수 조건

이벤트를 가져오려면 먼저 코드 조각을 사용하여 웹 사이트 데이터를 참여 인사이트에 연결해야 합니다. 자세한 내용은 [웹 사이트에 웹 SDK 설치](instrument-website.md)를 참조하세요.

 :::image type="content" source="media/new-events-connect-data.png" alt-text="데이터 먼저 연결.":::

## <a name="create-refined-events"></a>정교한 이벤트 만들기

개선된 이벤트를 사용하여 [내보낼](export-events.md) 기본 이벤트의 범위를 줄이거나 노출에 필요하지 않은 속성을 제거합니다.

> [!NOTE]
> 웹 SDK를 웹 사이트에 추가하면 기본 이벤트를 보고 세분화된 이벤트를 만들 수 있습니다. 

기본 이벤트를 보는 방법:

1. 왼쪽 탐색 창의 **데이터** 로 이동합니다.

1. 작업 영역의 모든 이벤트 목록을 보려면 **이벤트** 를 선택합니다.

    :::image type="content" source="media/data-events.png" alt-text="이벤트 보기.":::

기본 이벤트에서 세분화된 이벤트를 생성하는 방법: 

1. **데이터** > **이벤트** 로 이동하고 화면 상단에서 **+ 새 이벤트** 를 선택합니다.

1. **새 이벤트** 대화 상자에서 **세분화된 이벤트 만들기** 를 선택한 후 **다음** 을 선택합니다.
   
     :::image type="content" source="media/new-events-wizard.png" alt-text="새 이벤트 마법사.":::
     
1. **새 이벤트** 대화 상자에서 다음 정보를 입력합니다.

   - **기본 이벤트** 드롭다운에서 이벤트를 선택합니다.
   - **개선된 이벤트 표시 이름** 상자에 이름을 입력합니다.
   - 선택적으로 공백을 사용하지 않고 제안된 **실제 이름** 을 업데이트하세요.

1. **만들기** 를 선택하여 설정을 적용합니다.

이제 세련된 이벤트가 **이벤트** 목록에 나타납니다.

### <a name="edit-event-name"></a>이벤트 이름 편집

기본 또는 정제된 이벤트의 이름과 속성을 변경할 수 있습니다.

1. **데이터** > **이벤트** 로 이동합니다. 

1. 이벤트에 대해 **더 보기[...]** 를 선택하고 **이름 편집** 을 선택합니다.
    
     :::image type="content" source="media/create-refined-events-options.png" alt-text="개선된 이벤트를 만드는 옵션.":::

3. 이벤트 이름을 업데이트하고 **이름 바꾸기** 를 선택합니다.

### <a name="view-the-details-of-a-refined-event"></a>세분화된 이벤트의 세부 정보 보기:

1. 이벤트 목록에서 기본 또는 세분화된 **이벤트** 를 선택합니다. 

1. 화면 상단에서 **속성 추가 및 제거** 를 선택하여 **속성 편집** 창을 엽니다. 

     :::image type="content" source="media/add-remove-properties.png" alt-text="속성 추가 및 제거.":::

1. 확인란을 사용하여 표시할 속성과 숨길 속성을 선택합니다. 

   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="개선된 이벤트의 속성 편집.":::

1. **확인** 을 선택하여 선택 사항을 적용한 다음 **저장** 을 선택합니다.


### <a name="edit-selected-properties-for-a-refined-event"></a>세분화된 이벤트에 대해 선택한 속성 편집

1. **데이터** > **이벤트** 로 이동하고 개선된 이벤트를 선택하여 상세 보기를 엽니다.
1. **속성 추가 및 제거** 를 선택합니다. 
1. 선택란의 선택을 편집하십시오.
1. **확인** 을 선택한 다음 **저장** 을 선택하여 변경 내용을 적용합니다.

이벤트 내보내기에 대한 정보는 [이벤트 내보내기](export-events.md)를 참조하세요.
[!INCLUDE[footer-include](../includes/footer-banner.md)]
