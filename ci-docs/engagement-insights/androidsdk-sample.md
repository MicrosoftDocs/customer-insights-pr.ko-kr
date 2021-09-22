---
title: Android SDK 샘플
description: Android SDK에 대해 학습할 샘플 프로젝트
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ba51961bc7f9555d7dba5b6a21c8636011438d75cba87bc132b896841c467a33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035834"
---
# <a name="run-the-android-sdk-sample"></a>Android SDK 샘플 실행

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

이 샘플 Android 프로젝트는 SDK가 앱에서 작동하는 방식을 이해하는 데 도움이 됩니다. 코드를 작성할 필요가 없습니다. 수집 키를 추가하기만 하면 작업 영역에서 즉시 이벤트를 볼 수 있습니다.

## <a name="prerequisites"></a>필수 조건

- [Android Studio](https://developer.android.com/studio)
- [수집 키](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Android SDK 샘플 다운로드

1. [참여 인사이트 Android SDK 샘플 다운로드](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. 압축 파일 `ei-android-sample.zip`의 압축을 풉니다.
1. Android Studio에서 압축이 풀린 폴더를 엽니다.
1. `AndroidManifest.xml` 파일에서 `"Your-Ingestion-Key"` 문자열을 **관리자** > **작업 영역** > **설치 가이드** 에 있는 참여 인사이트의 작업 영역 수집 키로 교체합니다. 

   > [!NOTE]
   > `${applicationId}` 섹션은 교체할 필요가 없습니다. 자동으로 채워집니다.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. 샘플 프로젝트를 시작하려면 **실행** 을 선택합니다.
1. 작업 영역에서 이벤트를 봅니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
