---
title: Dynamics 365 Customer Insights에서 쿠키 및 사용자 데이터 저장에 대한 사용자 동의 관리
description: 웹 사이트 방문자를 식별하기 위해 쿠키와 사용자 동의가 어떻게 사용되는지 이해합니다.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 018263220d4628690e9f0beb8453e58b0356d099
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228993"
---
# <a name="manage-cookies-and-user-consent"></a>쿠키 및 사용자 동의 관리

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dynamics 365 Customer Insights 참여 인사이트 기능은 쿠키를 사용하고 (`localStorage`) 키를 사용하여 웹 사이트 방문자를 식별합니다.

쿠키는 사용자와 웹 사이트의 상호 작용에 대한 정보를 저장하는 작은 파일입니다. 웹 브라우저에 저장됩니다. 사용자가 쿠키를 저장한 웹 사이트를 방문하면 브라우저는 해당 정보를 서버로 전송하여 사용자에게 고유한 정보를 반환합니다. 예를 들어, 사용자가 웹 사이트를 벗어나더라도 온라인 쇼핑 카트에서 선택한 항목을 보관할 수 있는 기술입니다.

## <a name="user-consent"></a>사용자 동의

[GDPR(일반 데이터 보호 규정)](/dynamics365/get-started/gdpr/)은 조직이 사용자의 개인 정보 보호 및 보안을 처리하는 방법을 규정하는 EU(유럽 연합)의 규정입니다. 쿠키는 종종 GDPR이 적용되는 온라인 식별자와 같은 "개인 데이터"를 저장하거나 수집합니다. 비즈니스에서 EU 데이터 주체를 고용 및/또는 판매하는 경우 GDPR의 영향을 받습니다. [Microsoft가 GDPR을 준수하도록 지원하는 방법에 대해 자세히 알아보세요](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

참여 인사이트 SDK가 쿠키 또는 기타 민감한 정보를 저장하도록 허용하려면 사용자가 동의했는지 여부를 지정해야 합니다. 이는 구성에서 `userConsent` 필드를 설정하여 SDK를 초기화할 때 발생합니다.

사용자 동의가 없다고 표시하는 경우 SDK는 데이터를 저장하지 않으며 사용자 행동을 추적하는 데 사용할 수 있는 이벤트를 보내지 않습니다. 이전에 저장된 데이터는 브라우저에서 삭제됩니다.

사용자 동의 값이 지정되지 않은 경우 SDK는 사용자가 동의한 것으로 간주합니다. 즉, 귀하(고객)가 SDK에서 사용자 동의 값을 지정하지 않으면 데이터가 수집됩니다. 그러나 사용자 동의 값을 'true'로 지정하면 사용자가 명시적 동의를 거부하거나 제공하지 않으면 데이터가 수집되지 않습니다.

다음은 사용자 동의 하에 웹 SDK를 초기화하는 코드 조각입니다.
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>참여 인사이트 기능의 방문자 데이터 스토리지

### <a name="cookies"></a>쿠키

- _msei
    - 익명 사용자 ID를 저장합니다. 이 쿠키는 고객 도메인에 설정되며 365일 후에 만료됩니다.

### <a name="local-storage"></a>로컬 스토리지

또한 참여 인사이트 기능은 (`localStorage`) 키를 사용하여 중요하지 않은 데이터를 추적합니다. 이 데이터는 브라우저 자체에 완전히 저장되며 서버에서 송수신되는 트래픽이 없습니다.

- *EISession.Id*
    - 세션 ID, 시작 및 만료 시기와 같이 진행 중인 사용자 세션에 대한 정보를 저장합니다.
- *EISession.Previous*
    - 현재 세션에서 이전에 방문한 페이지의 URL을 저장합니다.

로컬 저장소의 키는 자동으로 만료되지 않으며 다음 SDK 세션 동안 재설정됩니다.

## <a name="deleting-cookies"></a>쿠키 삭제

고객은 브라우저 설정을 통해 언제든지 쿠키 및 로컬 저장소 키를 수동으로 삭제할 수 있습니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
