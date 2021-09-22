---
title: 웹 사이트에 코드 추가
description: 웹 사이트에서 이벤트를 캡처하기 위해 코드 조각을 추가하는 방법.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b5467da775a621c436bd9ddedb272506acc1e2b31dcf7c87feb5dd11e2daae2b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035102"
---
# <a name="install-the-code-snippet-on-a-website"></a>웹 사이트에 코드 조각 설치

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

이 문서에서는 관리자가 웹 사이트에 코드 조각을 설치하는 방법을 설명합니다. 웹 사이트에 스크립트를 추가한 직후 작업 영역에서 이벤트를 보기 시작합니다. 자세한 내용은 [작업 영역 및 환경 관리](manage-environments-workspaces.md)를 참조하세요. 모바일 앱에서 이벤트를 캡처하려면 [개발자 리소스 개요](developer-resources.md)를 참고하세요.


### <a name="prerequisites"></a>필수 조건

* 데이터를 저장하려면 작업 영역에 대한 관리자 권한이 있어야 합니다.
* 활동 데이터를 보내려면 웹 사이트 또는 프로젝트를 온라인으로 호스팅해야 합니다. 로컬 파일에서 보낸 데이터는 서버에서 허용되지 않습니다.


## <a name="add-code-to-your-website"></a>웹 사이트에 코드 추가
1.  **관리** > **작업 영역** 으로 이동한 다음 **설치 가이드** 를 선택합니다.
1. 코드 조각을 복사하려면 **코드 복사** 를 선택하십시오. 기본적으로 작업 영역의 수집 키는 코드 조각에 포함되어 있습니다.
:::image type="content" source="media/copy-code.png" alt-text="코드 조각 페이지의 스크린샷.":::
3. 복사한 코드 조각을 웹 사이트에 추가하세요. <head> 태그와 다른 스크립트 또는 CSS 태그 앞에.
4.  업데이트된 웹 사이트를 게시하고 들어오는 웹 트래픽을 캡처하기 위해 몇 분 정도 기다리세요.
5.  데이터를 보려면 탐색 창의 작업 영역 전환기에서 작업 영역을 선택합니다. 그런 다음 **검색** 섹션에서 보고서 중 하나를 선택합니다.

## <a name="configuration-options"></a>구성 옵션

코드 조각에서 다음 구성 옵션을 변경할 수 있습니다.

- **ingestionKey**: 작업 영역으로 이벤트를 보내는 데 사용되는 수집 키입니다. 수집 키를 변경하여 이벤트를 다른 작업 영역으로 보낼 수 있습니다. 수집 키는 각 작업 영역에 고유합니다. 
- **autoCapture**: 페이지 조회 및 웹 사이트와의 상호 작용이 캡처되는지 여부를 지정합니다. 두 가지 옵션이 있습니다.
    - **view**: 페이지 조회를 수집하려면 *true* 로 설정하세요. 페이지 조회는 [기본 이벤트](glossary.md#base-event) 유형인 *보기* [이벤트](glossary.md#event)로 캡처됩니다.
    - **click**: 웹 사이트에서 방문자 상호 작용을 캡처하려면 *true* 로 설정하세요. 상호 작용은 [기본 이벤트](glossary.md#base-event) 유형인 *액션* [이벤트](glossary.md#event)로 캡처됩니다.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
