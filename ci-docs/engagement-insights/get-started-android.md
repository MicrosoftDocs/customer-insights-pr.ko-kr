---
title: Android SDK로 시작하기
description: Android SDK를 개인화하고 실행하는 방법 알아보기
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 10/19/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 71ec4841303bd17d3f605547be8d6032c58a7b21
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977583"
---
# <a name="get-started-with-the-android-sdk"></a>Android SDK로 시작하기

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

이 자습서는 Dynamics 365 Customer Insights 참여 인사이트 SDK로 Android 애플리케이션을 계측하는 과정을 안내합니다. 5분 이내에 포털에서 이벤트를 볼 수 있습니다.

## <a name="configuration-options"></a>구성 옵션
다음 구성 옵션을 SDK에 전달할 수 있습니다.

- **ingestionKey**: 수집 키는 작업 영역에 이벤트를 보내는 데 사용됩니다.

## <a name="prerequisites"></a>필수 조건

- Android Studio

- 최소 Android API 수준: 16(Jelly Bean)

- 수집 키(구하는 방법에 대한 지침은 아래 참조)

## <a name="integrate-the-sdk-into-your-application"></a>SDK를 애플리케이션에 통합
작업 영역을 선택하고 Android 모바일 플랫폼을 선택하고 Android SDK를 다운로드하여 프로세스를 시작합니다.

- 왼쪽 탐색 창에서 작업 영역 전환기를 사용하여 작업 영역을 선택합니다.

- 기존 작업 영역이없는 경우 **새 작업 영역** 을 선택하고 단계에 따라 [새 작업 영역](create-workspace.md)을 만듭니다.

- 작업 영역을 만든 후 **관리자** > **작업 영역** 으로 이동한 후 **설치 가이드** 를 선택합니다.

## <a name="configure-the-sdk"></a>SDK 구성

SDK를 다운로드하면 Android Studio에서 SDK로 작업하여 이벤트를 활성화하고 정의할 수 있습니다. 이렇게 하는 방법은 두 가지가 있습니다.
### <a name="option-1-use-jitpack-recommended"></a>옵션 1: JitPack 사용(권장)
1. 루트 `build.gradle`에 JitPack 리포지토리 추가:
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. 종속성을 추가합니다:
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:v1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-use-download-link"></a>옵션 2: 다운로드 링크 사용
1. [참여 인사이트 Android SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip)를 다운로드하고 `eiandroidsdk-debug.aar` 파일을 `libs` 폴더에 배치합니다.

1. 프로젝트 수준 `build.gradle` 파일을 열고 다음 코드 조각을 추가합니다.
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

## <a name="enable-auto-instrumentation"></a>자동 계측 활성화

1. `manifests` 폴더 아래에 있는 `AndroidManifest.xml` 파일에 네트워크 및 인터넷에 대한 권한을 추가합니다.
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```

1. `AndroidManifest.xml` 파일을 통해 참여 인사이트 SDK 구성을 설정합니다.

1. **설치 가이드** 에서 XML 코드 조각을 복사합니다. `Your-Ingestion-Key`는 자동으로 채워집니다.

   > [!NOTE]
   > `${applicationId}` 섹션은 교체할 필요가 없습니다. 자동으로 채워집니다.


   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. 위의 `autoCapture` 필드를 `true` 또는 `false`로 설정하여 `View` 이벤트의 자동 캡처를 사용하거나 사용 중지합니다. 

   >[!NOTE]
   >`Action` 이벤트는 수동으로 추가해야 합니다.

1. (선택 사항) 기타 구성에는 끝점 수집기 URL 설정이 포함됩니다. `AndroidManifest.xml`의 수집 키 메타데이터 아래에 추가할 수 있습니다.

   ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
   ```

## <a name="implement-custom-events"></a>사용자 지정 이벤트 구현

SDK를 초기화한 후 `MainActivity` 환경에서 이벤트 및 해당 속성으로 작업할 수 있습니다.


Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>모든 이벤트에 대한 속성 설정(선택 사항)

Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

컨텍스트 이벤트 속성에 대해 다음 유형이 지원됩니다.
- String
- Date
- 두 배
- Long
- Boolean
- UUID

### <a name="track-an-event"></a>이벤트 추적

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

## <a name="set-user-details-for-your-event-optional"></a>이벤트에 대한 사용자 세부 정보 설정(선택 사항)

SDK를 사용하면 모든 이벤트와 함께 전송할 수있는 사용자 정보를 정의할 수 있습니다. `Analytics` 수준에서 `setUser(user: User)` API를 호출하여 사용자 정보를 지정할 수 있습니다.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

`User` 데이터 클래스에는 다음 문자열 속성이 포함됩니다.

- **localId**: 사용자의 로컬 ID입니다.
- **authId**: 인증된 사용자 ID입니다.
- **authType**: 인증된 사용자 ID를 가져오는 데 사용되는 인증 유형입니다.
- **이름**: 사용자의 이름입니다.
- **이메일**: 사용자의 이메일 주소입니다.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
