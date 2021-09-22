---
title: 개선된 이벤트 생성 및 수정
description: 개선된 이벤트를 만들고 수정하는 방법.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034782"
---
# <a name="create-and-modify-refined-events"></a>개선된 이벤트 생성 및 수정

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


이벤트는 웹 사이트에서의 활동과 같은 사용자 행동을 나타내는 데이터입니다.

- *기본* 이벤트는 사용자가 페이지(이벤트 보기)를 보거나 콘텐츠(작업 이벤트)와 상호 작용할 때 기록합니다.
- *개선된* 이벤트는 기본 이벤트의 가상 보기입니다. 속성을 제거 및 추가하거나 속성 값을 기준으로 이벤트를 필터링하여 개선된 이벤트를 정의합니다.

개선된 이벤트를 사용하여 [내보낼](export-events.md) 기본 이벤트의 범위를 줄이거나 노출에 필요하지 않은 속성을 제거합니다.

## <a name="create-refined-events"></a>정교한 이벤트 만들기

기본 이벤트에서 개선된 이벤트를 만드는 방법에는 세 가지가 있습니다. 

1. **데이터**> **이벤트** 로 이동하여 다음 옵션 중 하나를 선택합니다.
    - **새 이벤트** 를 선택한 다음 **개선된 이벤트 만들기** 를 선택합니다.
    - 기본 이벤트를 선택하여 상세 보기를 열고 상단 메뉴에서 **개선된 이벤트 만들기** 를 선택합니다.
    - **더 보기[...]** 를 선택하여 기본 이벤트에 대한 바로 가기 메뉴를 엽니다. 그런 다음 **개선된 이벤트 만들기** 를 선택합니다.
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="개선된 이벤트를 만드는 옵션.":::

1. **개선된 이벤트 만들기** 대화 상자에서 다음 정보를 입력합니다.

- 새 이벤트를 만드는 경우 **기본 이벤트** 드롭다운에서 이벤트를 선택합니다.
- **개선된 이벤트 표시 이름** 상자에 이름을 입력합니다.
- 선택적으로 공백을 사용하지 않고 제안된 **실제 이름** 을 업데이트하세요.

3. **만들기** 를 선택하여 설정을 적용합니다.

1. 개선된 이벤트의 세부 정보 보기에서 **속성 추가 및 제거** 를 선택하여 **속성 편집** 창을 엽니다. 

1. 확인란을 사용하여 표시할 속성과 숨길 속성을 선택합니다. 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="개선된 이벤트의 속성 편집.":::

1. **확인** 을 선택하여 선택 사항을 적용합니다.

1. **저장** 을 선택하여 구성을 저장합니다.

## <a name="edit-refined-events"></a>개선된 이벤트 편집

개선된 이벤트의 이름과 속성을 변경할 수 있습니다.

### <a name="edit-event-name"></a>이벤트 이름 편집

1. **데이터** > **이벤트** 로 이동합니다. 
1. 이벤트에 대해 **더 보기[...]** 를 선택하고 **이름 편집** 을 선택합니다.
1. 이벤트 이름을 업데이트하고 **이름 바꾸기** 를 선택합니다.

### <a name="edit-selected-properties"></a>선택한 속성 편집

1. **데이터** > **이벤트** 로 이동하고 개선된 이벤트를 선택하여 상세 보기를 엽니다.
1. **속성 추가 및 제거** 를 선택합니다. 
1. 선택란의 선택을 편집하십시오.
1. **확인** 을 선택한 다음 **저장** 을 선택하여 변경 내용을 적용합니다.

이벤트 내보내기에 대한 정보는 [이벤트 내보내기](export-events.md)를 참조하세요.
[!INCLUDE[footer-include](../includes/footer-banner.md)]
