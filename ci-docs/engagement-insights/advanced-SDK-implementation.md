---
title: 고급 웹 SDK 시나리오
description: SDK로 웹 사이트를 계측할 때 고려해야 할 고급 시나리오입니다.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 4c6646ecadbb604000d6c95b685cf6e420969a6d
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558710"
---
# <a name="advanced-web-sdk-instrumentation"></a>고급 웹 SDK 계측

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

이 문서에서는 Dynamics 365 Customer Insights 참여 인사이트 기능 SDK를 사용하여 [웹 사이트를 계측](instrument-website.md)할 때 고려할 고급 시나리오를 안내합니다.

## <a name="setting-user-details-for-your-event"></a>이벤트에 대한 사용자 세부 정보 설정

SDK를 사용하면 모든 이벤트와 함께 전송할 수있는 사용자 정보를 정의할 수 있습니다. 코드 조각 구성의 `src`, `name`, `cfg`와 유사하게 `user`(이 속성의 예상 데이터는 `IUser` 객체임)이라는 속성에서 사용자 세부 정보를 지정할 수 있습니다.

`IUser` 객체에는 다음 문자열 속성이 포함됩니다.

- **localId**: 사용자의 로컬 ID입니다.
- **authId**: 인증된 사용자 ID입니다.
- **authType**: 인증된 사용자 ID를 가져오는 데 사용되는 인증 유형입니다.
- **이름**: 사용자의 이름입니다.
- **이메일**: 사용자의 이메일 주소입니다.

다음 예제는 사용자 정보를 보내는 코드 조각를 보여줍니다. 앞에 별표 * 기호가 있는 함수가 있는 경우 함수를 사용자 지정 구현으로 대체합니다.

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

`setUser(user: IUser)` API를 호출하여 사용자 정보를 지정할 수도 있습니다. `setUser` API를 호출한 후 전송된 원격 분석에는 사용자 정보가 포함됩니다.

## <a name="adding-custom-properties-for-each-event"></a>각 이벤트에 대한 사용자 지정 속성 추가

SDK를 사용하면 모든 이벤트와 함께 보낼 수 있는 사용자 지정 속성을 지정할 수 있습니다. 맞춤 속성을 키-값 쌍을 포함하는 객체로 지정할 수 있습니다(값은 `string | number | boolean` 유형일 수 있음). 코드 스니펫 구성의 `src`, `name` 및 `cfg`와 유사한 `props`라는 속성에 객체를 추가할 수 있습니다.

다음 예제는 사용자 지정 속성을 보내는 코드 조각를 보여줍니다.

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

`setProperty(name: string, value: string | number | boolean)` API를 호출하여 사용자 지정 속성을 개별적으로 지정할 수도 있습니다.

## <a name="sending-custom-events"></a>사용자 지정 이벤트 보내기

SDK를 사용하여 사용자 지정 이벤트를 보낼 수 있습니다. 이벤트와 함께 보낼 이벤트 및 속성의 이름을 지정해야 합니다.

다음 예제는 사용자 지정 이벤트를 추적하는 코드 조각를 보여줍니다. 'NAME'은 코드 조각 구성의 `name` 키에 있는 값입니다. SDK가 로드되는 창 개체의 변수 이름이기도 합니다.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]
