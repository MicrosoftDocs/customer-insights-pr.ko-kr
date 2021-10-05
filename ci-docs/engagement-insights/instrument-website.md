---
title: 웹 사이트에 코드 추가
description: 웹 사이트에서 Dynamics 365 Customer Insights 이벤트를 캡처하기 위해 코드 조각을 추가하는 방법.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: ad835f762226d62fdb0f544627f2a76ff09a1ffd
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558901"
---
# <a name="install-the-web-sdk-on-a-website"></a>웹 사이트에 웹 SDK 설치

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

이 문서에서는 관리자가 웹 사이트에 웹 SDK(소프트웨어 개발 도구 키트)를 설치하는 방법을 설명합니다. 웹 사이트를 측정한 직후 작업 영역에 이벤트가 표시되기 시작합니다. 자세한 내용은 [작업 영역 및 환경 관리](manage-environments-workspaces.md)를 참조하세요. 모바일 앱에서 이벤트를 캡처하려면 [개발자 리소스 개요](developer-resources.md)를 참고하세요.


### <a name="prerequisites"></a>필수 조건

* 데이터를 저장하려면 작업 영역에 대한 관리자 권한이 있어야 합니다.
* 활동 데이터를 보내려면 웹 사이트 또는 프로젝트를 온라인으로 호스팅해야 합니다. 로컬 파일에서 보낸 데이터는 서버에서 허용되지 않습니다.


## <a name="add-web-sdk-to-your-website"></a>웹 사이트에 웹 SDK 추가

**관리** > **작업 영역** 으로 이동한 다음 **설치 가이드** 를 선택합니다. 웹 SDK를 추가하는 두 가지 방법이 있습니다. 첫 번째는 다운로드 링크를 사용하는 것이고 두 번째는 NPM(노드 패키지 관리자) 패키지를 설치하는 것입니다.

### <a name="option-1-using-the-download-link"></a>옵션 1: 다운로드 링크 사용

1. 코드 조각을 복사하려면 **코드 복사** 를 선택하십시오. 기본적으로 작업 영역의 수집 키는 코드 조각에 포함되어 있습니다.
  :::image type="content" source="media/copy-code.png" alt-text="코드 조각 페이지의 스크린샷.":::

1. 복사한 코드를 웹 사이트의 태그 근처 <head> 및 다른 스크립트 또는 CSS 태그 앞에 추가합니다.
1. 업데이트된 웹 사이트를 게시하고 들어오는 웹 트래픽을 캡처하기 위해 몇 분 정도 기다리세요.
1. 데이터를 보려면 탐색 창의 작업 영역 전환기에서 작업 영역을 선택합니다. 그런 다음 **검색** 섹션에서 보고서 중 하나를 선택합니다.

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>옵션 2: NPM 패키지 사용(JavaScript 기반 웹 앱에 권장)

1. [NPM 웹페이지](https://www.npmjs.com/package/engagementinsights-web)로 이동하여 지침에 따라 웹 SDK NPM 패키지를 설치 및 설정합니다.
1. 업데이트된 웹 사이트를 게시하고 들어오는 웹 트래픽을 캡처하기 위해 몇 분 정도 기다리세요.
1. 데이터를 보려면 탐색 창의 작업 영역 전환기에서 작업 영역을 선택합니다. 그런 다음 **검색** 섹션에서 보고서 중 하나를 선택합니다.

## <a name="configuration-options"></a>구성 옵션

코드 조각에서 다음 구성 옵션을 변경할 수 있습니다.

- **ingestionKey**: 작업 영역으로 이벤트를 보내는 데 사용되는 수집 키입니다. 수집 키를 변경하여 이벤트를 다른 작업 영역으로 보낼 수 있습니다. 수집 키는 각 작업 영역에 고유합니다.
- **autoCapture**: 페이지 조회 및 웹 사이트와의 상호 작용이 캡처되는지 여부를 지정합니다. 두 가지 옵션이 있습니다.
    - **view**: 페이지 조회를 수집하려면 *true* 로 설정하세요. 페이지 조회는 [기본 이벤트](glossary.md#base-event) 유형인 *보기* [이벤트](glossary.md#event)로 캡처됩니다.
    - **click**: 웹 사이트에서 방문자 상호 작용을 캡처하려면 *true* 로 설정하세요. 상호 작용은 [기본 이벤트](glossary.md#base-event) 유형인 *액션* [이벤트](glossary.md#event)로 캡처됩니다.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
