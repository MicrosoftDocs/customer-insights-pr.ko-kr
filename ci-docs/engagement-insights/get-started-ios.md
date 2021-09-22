---
title: iOS SDK 시작하기
description: iOS SDK를 개인화하고 실행하는 방법 알아보기
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: de8291fc429ae6433301a47bfdf9a3271b1b77294fd58448c7aa6bd0783edc97
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036881"
---
# <a name="get-started-with-the-ios-sdk"></a>iOS SDK로 시작하기

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

이 자습서는 Dynamics 365 Customer Insights 참여 인사이트 SDK로 iOS 애플리케이션을 계측하는 과정을 안내합니다. 5분 이내에 포털에서 이벤트를 볼 수 있습니다.

## <a name="configuration-options"></a>구성 옵션

제공된 `EIConfig.plist` 파일을 통해 SDK에 다음 구성 옵션을 전달할 수 있습니다.

- **ingestionKey**: 수집 키는 프로젝트에 이벤트를 보내는 데 사용됩니다.
- **autocollectAction**: 작업 이벤트의 자동 계측을 활성화하거나 비활성화하는 부울 값입니다.
- **autocollectView**: 보기 이벤트의 자동 계측을 활성화하거나 비활성화하는 부울 값입니다.
- **endpointUrl**: 이벤트가 전달될 끝점 URL입니다.

## <a name="prerequisites"></a>필수 조건

- Xcode 버전 9+
- iOS 버전 8.2+
- 수집 키(구하는 방법에 대한 지침은 아래 참조)

## <a name="integrate-the-sdk-into-your-application"></a>SDK를 애플리케이션에 통합

작업할 작업 영역을 선택하고 iOS 모바일 플랫폼을 선택하고 SDK를 다운로드하여 프로세스를 시작합니다.

- 왼쪽 탐색 창에서 작업 영역 전환기를 사용하여 작업 영역을 선택합니다.

- 기존 작업 영역이없는 경우 **새 작업 영역** 을 선택하고 단계에 따라 [새 작업 영역](create-workspace.md)을 만듭니다.

## <a name="configure-the-sdk"></a>SDK 구성

SDK를 다운로드하면 Xcode에서 SDK로 작업하여 이벤트를 활성화하고 정의할 수 있습니다.

1. 작업 영역을 만든 후 **관리자** > **작업 영역** 으로 이동한 후 **설치 가이드** 를 선택합니다.

1. [참여 인사이트 iOS SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip)를 다운로드하고 `EIObjC.xcframework` 파일을 `Frameworks` 폴더에 배치합니다.

1. `Frameworks` 폴더가 존재하지 않는 경우 프로젝트 폴더에 만듭니다.

## <a name="enable-auto-instrumentation"></a>자동 계측 활성화
 
코딩 없이 쉽게 자동 계측을 활성화할 수 있습니다. 프로젝트가 실행되면 구성된 수집 키를 사용하여 자동으로 `view` 및 `action` 이벤트를 추적합니다. 

1. 프로젝트 디렉터리 폴더의 다음 필드에 대해 제공된 `EIConfig.plist` 파일을 업데이트 및 포함합니다.
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = 예
    - autocollectAction = 예

2. 그런 다음 Xcode의 프로젝트에 `EIConfig.plist` 파일을 추가합니다. 



자동 계측을 사용 중지하려면 프로젝트 디렉터리 폴더에 포함된 `EIConfig.plist` 파일의 다음 필드를 업데이트합니다. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>사용자 지정 이벤트 구현

1. Xcode에서 프로젝트를 열고 **일반** 설정으로 이동합니다. 
1. `EIObjC.xcframework`를 '프레임워크, 라이브러리 및 포함된 콘텐츠' 섹션의 프로젝트에 추가합니다.

1. 다음 코드 조각을 사용하여 AppDelegate.m의 프레임워크 헤더 파일을 가져옵니다.

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. didFinishLaunchingWithOptions 애플릴케이션에서 참여 인사이트 SDK를 초기화합니다.
1. **설치 가이드** 에서 XML 코드 조각을 복사합니다.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. 이벤트 추적:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>이벤트에 대한 사용자 세부 정보 설정

SDK를 사용하면 모든 이벤트와 함께 전송할 수있는 사용자 정보를 정의할 수 있습니다. SDK에서 `setUser:(nonnull EIUser *)user` API를 호출하여 사용자 정보를 지정할 수 있습니다.

`Analytics` 수준에서 사용자 세부 정보를 지정하면 모든 원격 측정에 이 정보가 있음을 의미합니다. 그러나 이벤트 수준에서 EIEvent 개체에서 `setUser:(nonnull EIUser *)user` API를 호출하여 지정하는 경우 해당 특정 이벤트에만 정보가 포함됩니다.

`EIUser` 데이터 클래스에는 다음 NSString 속성이 포함됩니다.

- **localId**: 사용자의 로컬 ID입니다.
- **authId**: 인증된 사용자 ID입니다.
- **authType**: 인증된 사용자 ID를 가져오는 데 사용되는 인증 유형입니다.
- **이름**: 사용자의 이름입니다.
- **이메일**: 사용자의 이메일 주소입니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
