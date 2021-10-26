---
title: 웹 SDK 샘플 실행
description: 웹 SDK 샘플을 개인화하고 실행하는 방법을 알아봅니다.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 545f4a7e9660e339dee1070ad727d5d398eb6254
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606237"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Dynamics 365 Customer Insights 참여 인사이트의 기능에 대한 웹 SDK 샘플 실행 참여 통찰력 기능

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

참여 인사이트 기능 웹 SDK 라이브러리는 웹 사이트에서 사용할 수 있는 샘플 코드가 포함된 JavaScript 라이브러리입니다.

## <a name="prerequisites"></a>필수 조건

- [Visual Studio 코드](https://code.visualstudio.com/)를 설치합니다.
- Visual Studio Code에 [라이브 서버 확장을 설치](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)하고 라이브 서버를 실행하는 방법을 익힙니다.
- [참여 인사이트 작업 영역](create-workspace.md)이 있어야 합니다.

## <a name="run-sample"></a>샘플 실행

1. [웹 SDL 샘플을 다운로드](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip)합니다.

1. 압축 파일 `ei_websdk_sample.zip`의 압축을 풉니다.

1. Visual Studio Code에서 압축이 풀린 폴더를 엽니다.

1. 작업 영역에 대한 참여 인사이트 포털로 이동합니다. **관리** >  **작업 영역** 을 선택한 다음 **설치 가이드** 를 선택합니다. 첫 번째 옵션을 따르고 **코드 복사** 를 선택하여 JavaScript 코드 조각을 복사합니다.

1. `ei_websdk_sample.html` 파일에서 방금 복사한 코드 조각을 다음 줄에 붙여넣습니다.

   - <-- 참여 인사이트 포털의 JavaScript 코드 조각을 이 줄 아래에 붙여넣기 -->

1. 상태 표시줄에서 **라이브로 전환** 을 선택하여 Visual Studio Code에서 Live Server를 사용하여 `ei_websdk_sample.html` 파일을 엽니다.

1. 페이지를 열면 보기 이벤트가 자동으로 전송되어야 합니다. 페이지의 아무 단추나 클릭하면 액션 이벤트가 전송됩니다. **이벤트 추적** 단추는 사용자 지정 이벤트도 보냅니다. **Bing으로 이동** 단추를 선택하면 Bing 웹 사이트로 이동하기 전에 액션 이벤트가 전송됩니다.

1. 작업 영역으로 이동할 때 흐르는 이벤트를 살펴보세요. 이 작업 영역은 4단계에서 입력한 수집 키와 연결됩니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
