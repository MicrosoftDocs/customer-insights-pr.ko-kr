---
title: Power Automate 커넥터 | Microsoft Docs
description: Dynamics 365 Customer Insights의 Microsoft Power Automate에서 흐름을 만듭니다.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 409792bc3f12fca451ef038e3300758bdf9ecf3b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647216"
---
# <a name="power-automate-connector-preview"></a>Power Automate 커넥터(미리 보기)

데이터가 변경되면 특정 이벤트가 자동으로 발생하도록 트리거하고 [Power Automate](https://flow.microsoft.com/)에서 직접 더 복잡한 흐름을 관리합니다.

## <a name="known-limitations"></a>알려진 제한 사항

- 60초당 최대 100개의 호출을 할 수 있습니다. $skip 매개 변수를 사용하여 API 엔드포인트를 여러 번 호출할 수 있습니다. [$skip 매개 변수에 대해 자세히 알아보세요](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>Power Automate 트리거

트리거를 사용하여 클라우드 흐름을 만들고 알림 또는 고급 작업과 같은 반복적인 작업을 자동화합니다. 

- 데이터 원본 새로 고침이 실패하면 트리거됩니다. 
- 데이터 원본 새로 고침이 성공하면 트리거됩니다.
- 임계값이 세그먼트에서 교차될 때 트리거됩니다. 트리거는 임계값을 초과하는 것으로 제한됩니다.
- 임계값이 비즈니스 측정에서 교차될 때 트리거됩니다. 차원이 없는 비즈니스 측정값만 지원됩니다. 트리거는 임계값을 초과하는 것으로 제한됩니다.
- (데이터 원본, 세그먼트, 측정값 등)의 전체 새로 고침이 완료되면 트리거됩니다.
- 통합 프로세스(매핑, 일치, 병합)의 새로 고침이 완료되면 트리거됩니다.

[Power Automate에서 트리거를 구성합니다.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate 작업

Power Automate 커넥터는 사용 가능한 트리거 이외의 다른 조치를 제공합니다. 자세한 내용은 [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/)를 참조하십시오.

## <a name="create-a-power-automate-flow"></a>Power Automate 흐름 만들기

1. **관리자** > **내보내기 대상** 으로 이동합니다.

1. **Power Automate** 타일에서 **설정** 을 선택합니다.

1. Power Automate의 Customer Insights 커넥터(미리 보기)가 열립니다. Power Automate에 **로그인** 합니다.

1. 사용 가능한 트리거 중 하나를 선택하고 새 흐름에 단계를 더 추가합니다. 자세한 내용은 [Power Automate의 클라우드 흐름 만들기](/power-automate/get-started-logic-flow)를 참조하십시오.

흐름 사용 방법의 예: 
- 데이터 원본 새로 고침이 실패하면 Microsoft Teams 채널에 메시지를 게시합니다. 
- 세그먼트의 임계값이 초과되면 데이터 담당자에게 이메일을 보냅니다.



[!INCLUDE [footer-include](includes/footer-banner.md)]
