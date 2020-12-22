---
title: Power Automate 커넥터 | Microsoft Docs
description: Dynamics 365 Customer Insights의 Microsoft Power Automate에서 흐름 만들기.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406263"
---
# <a name="power-automate-connector-preview"></a>Power Automate 커넥터(미리 보기)

데이터가 변경되면 특정 이벤트가 자동으로 발생하도록 트리거하고 [Power Automate](https://flow.microsoft.com/)에서 직접 더 복잡한 흐름을 관리합니다.

## <a name="power-automate-triggers"></a>Power Automate 트리거

알림 또는 고급 작업과 같은 반복적인 작업을 자동화하는 흐름을 만들 수 있는 다양한 트리거를 사용할 수 있습니다. 

- 데이터 원본 새로 고침이 실패하면 트리거됩니다. 
- 데이터 원본 새로 고침이 성공하면 트리거됩니다.
- 임계값이 세그먼트에서 교차될 때 트리거됩니다. 트리거는 임계값을 초과하는 것으로 제한됩니다.
- 임계값이 비즈니스 측정에서 교차될 때 트리거됩니다. 트리거는 임계값을 초과하는 것으로 제한됩니다.
- (데이터 원본, 세그먼트, 측정값 등)의 전체 새로 고침이 완료되면 트리거됩니다.
- 통합 프로세스(매핑, 일치, 병합)의 새로 고침이 완료되면 트리거됩니다.

[Power Automate에서 트리거를 구성합니다](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Power Automate 작업
Power Automate 커넥터는 사용 가능한 트리거 이외의 다른 조치를 제공합니다. 자세한 내용은 [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/)를 참조하십시오.

## <a name="create-a-power-automate-flow-in-audience-insights"></a>대상 그룹 인사이트에서 Power Automate 흐름 만들기

1. 대상 그룹 인사이트에서 **데이터** > **시스템** 으로 이동합니다.

1. **시스템** 페이지에서 **상태** 탭을 선택합니다.

1. **데이터 소스** 섹션에서 **Flows** 를 선택하고 드롭다운 목록에서 **흐름 만들기** 를 선택합니다.
   > [!div class="mx-imgBorder"]
   > ![흐름 만들기 작업을 보여주는 Power Automate 커넥터](media/power-automate-connector-create-flow.png "흐름 만들기 작업을 보여주는 Power Automate 커넥터")

1. Power Automate에서 사용 가능한 트리거 중 하나를 선택하여 원하는 흐름을 만듭니다. 첫 번째 흐름을 작성하는 경우 먼저 Power Automate 커넥터를 사용하여 인증해야 합니다.
