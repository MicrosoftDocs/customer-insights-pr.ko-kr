---
title: 재방문 시 알아보기를 사용하여 이전에 인증된 방문자의 웹 이벤트 인식
description: 재방문 시 알아보기 기능을 사용하면 웹사이트의 이벤트를 이전에 인증한 방문자와 연결할 수 있습니다.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: d1bbc3315b55e2ee233dc672456e0c27e4ad0fbd5937af09cc790c96ee274000
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036791"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>이전에 인증된 방문자의 웹 이벤트 인식

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

참여 인사이트 기능의 **재방문 시 알아보기** 기능을 사용하면 웹사이트의 이벤트를 이전에 인증한 방문자와 연결할 수 있습니다. 이 기능을 비활성화하면 이전 방문에서 인증한 방문자가 다시 방문할 때 다시 인증하지 않으면 식별되지 않습니다. 

예를 들어, 한 사람이 지난 주에 웹 사이트를 방문하여 해당 사이트의 사용자 계정에 로그인하고 제품 카탈로그를 검색했습니다. 그 사람은 계정에 로그인하지 않고 더 많은 제품을 찾아보기 위해 다음 주에 돌아옵니다. **재방문 시 알아보기** 기능을 사용하는 사이트 소유자는 동일한 사람이 사이트에 돌아와서 무엇을 했는지 알 수 있습니다. 이를 통해 웹사이트 활동에 대한 보다 정확한 보고 및 분석이 가능합니다.

## <a name="enable-unknown-to-known"></a>재방문 시 알아보기 활성화

이 기능을 활성화하려면 [작업 영역 관리자](user-roles.md)여야 합니다. 

1. 참여 인사이트에서 **관리자** > **작업 영역** 으로 이동합니다. 
2. **설정** 탭을 선택합니다.
3. **재방문 시 알아보기** 섹션에서 토글을 **활성화** 로 설정합니다.

![재방문 시 알아보기 활성화](media/U2Ktoggle.png "재방문 시 알아보기 활성화")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>사이트 추적 코드 조각에 JavaScript 코드 추가하기

웹사이트는 [참여 인사이트 웹 SDK](advanced-SDK-implementation.md)를 사용하여 다음 JavaScript 샘플로 **사용자 authId** 를 캡처할 수 있습니다. **재방문 시 알아보기** 기능이 작동하려면 아래 샘플과 같이 JavaScript 코드 조각에서 authId 캡처 *및* userMapping:True 활성화를 수행해야 합니다.

```
[…]
window, document
{
src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js",
name:"myproject",
cfg:{
ingestionKey:<paste your ingestion key>",
autoCapture:{
view:true,
click:true
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
