---
title: Power Automate 커넥터(프리뷰) | Microsoft Docs
description: Dynamics 365 Customer Insights의 Microsoft Power Automate에서 흐름을 만듭니다.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196126"
---
# <a name="power-automate-connector-preview"></a>Power Automate 커넥터(미리 보기)

데이터가 변경되면 특정 이벤트가 자동으로 발생하도록 트리거하고 [Microsoft Power Automate](https://flow.microsoft.com/)에서 직접 더 복잡한 흐름을 관리합니다.

## <a name="known-limitations"></a>알려진 제한 사항

- 60초당 최대 100개를 호출합니다. [$skip 매개 변수](/connectors/customerinsights/#get-items-from-an-entity)를 사용하여 API 엔드포인트를 여러 번 호출할 수 있습니다.

## <a name="power-automate-triggers"></a>Power Automate 트리거

트리거를 사용하여 클라우드 흐름을 만들고 알림 또는 고급 작업과 같은 반복적인 작업을 자동화합니다. 다음과 같은 경우 트리거를 사용합니다.

- 데이터 원본을 새로 고침하지 못한 경우.
- 데이터 원본을 새로 고침한 경우.
- 임계값이 세그먼트에서 교차될 경우. 트리거는 임계값을 초과하는 것으로 제한됩니다.
- 임계값이 비즈니스 측정에서 교차될 경우. 차원이 없는 비즈니스 측정값만 지원됩니다. 트리거는 임계값을 초과하는 것으로 제한됩니다.
- 예약된 새로 고침이 모두 완료된 경우. 이 트리거는 수동으로 시작된 새로 고침에 대해서는 작동하지 않습니다.
- 통합 프로세스의 새로 고침이 완료된 경우.

[Power Automate에서 트리거를 구성합니다.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate 작업

Power Automate 커넥터는 사용 가능한 트리거 이외의 다른 조치를 제공합니다. 자세한 내용은 [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/)를 참조하십시오.

## <a name="create-a-power-automate-flow"></a>Power Automate 흐름 만들기

1. **관리자** > **연결** 로 이동합니다.

1. **Power Automate** 타일에서 **설정** 을 선택합니다.

1. Power Automate의 Customer Insights 커넥터(미리 보기)가 열립니다. Power Automate에 **로그인** 합니다.

1. 사용 가능한 트리거 중 하나를 선택하고 새 흐름에 단계를 더 추가합니다. 자세한 내용은 [Power Automate의 클라우드 흐름 만들기](/power-automate/get-started-logic-flow)를 참조하십시오.

흐름 사용 방법의 예: 
- 데이터 원본 새로 고침이 실패하면 Microsoft Teams 채널에 메시지를 게시합니다. 
- 세그먼트의 임계값이 초과되면 데이터 담당자에게 이메일을 보냅니다.

[!INCLUDE [footer-include](includes/footer-banner.md)]
