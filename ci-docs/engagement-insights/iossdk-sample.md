---
title: iOS SDK 샘플 실행
description: iOS SDK에 대해 학습할 샘플 프로젝트
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 053e626d06d3e17b39b448987410058e45e8ae0385f3ecdef40314cb46ae4bf4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036836"
---
# <a name="run-the-ios-sdk-sample"></a>iOS SDK 샘플 실행

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

이 샘플 iOS 프로젝트는 SDK가 앱에서 작동하는 방식을 이해하는 데 도움이 됩니다. 코드를 작성할 필요가 없습니다. 수집 키를 추가하기만 하면 작업 영역에서 즉시 이벤트를 볼 수 있습니다.

## <a name="prerequisites"></a>필수 조건

- [Xcode 버전 9+](https://developer.apple.com/xcode/downloads/)
- [수집 키](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>iOS SDK 샘플 다운로드

1. [참여 인사이트 iOS SDK 샘플 다운로드](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. 압축 파일 `ei-ios-sample.zip`의 압축을 풉니다.
1. Xcode에서 샘플 앱 프로젝트를 엽니다.
1. `EIConfig.plist` 파일에서 `ingestionKey` 필드의 `“YOUR-INGESTION-KEY”` 문자열을 **관리자** > **작업 영역** > **설치 가이드** 에 있는 참여 인사이트의 작업 영역 수집 키로 교체합니다.
1. 샘플 프로젝트를 시작하려면 **실행** 을 선택합니다.
1. 작업 영역에서 이벤트를 봅니다.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
