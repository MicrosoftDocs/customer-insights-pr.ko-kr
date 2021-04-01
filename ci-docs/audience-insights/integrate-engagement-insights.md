---
title: 참여 인사이트의 웹 데이터를 대상 그룹 인사이트와 통합
description: 참여 인사이트에서 대상 그룹 인사이트로 고객에 대한 웹 정보를 가져옵니다.
ms.date: 12/17/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 14ebff30d3ec7fc52dca6f86136309a3f454fa27
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597473"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>참여 인사이트의 웹 데이터를 대상 그룹 인사이트와 통합

고객은 종종 웹 사이트를 사용하여 온라인에서 일상적인 트랜잭션을 수행합니다. Dynamics 365 Customer Insights의 참여 인사이트 기능은 웹 데이터를 소스로 통합하는 편리한 솔루션입니다. 트랜잭션, 인구 통계 또는 행동 데이터 외에도 통합 고객 프로필에서 웹 활동을 볼 수 있습니다. 이 프로필을 사용하여 세그먼트, 측정값 또는 대상 그룹 활성화에 대한 예측과 같은 추가 인사이트를 얻을 수 있습니다.

이 문서에서는 참여 인사이트에서 고객의 웹 활동 데이터를 기존 대상 그룹 인사이트 환경으로 가져오는 단계를 설명합니다.

이 예에서는 통합 고객 프로필이 포함된 환경을 가정합니다. 프로필은 설문 조사, 소매 영업 및 티켓팅 시스템의 소스와 통합되었습니다. 또한 고객의 관련 활동을 보여줍니다. 

이제 고객이 웹 속성을 방문하고 그들의 활동을 이해하고 있는지 알아보겠습니다. 예를 들어 활동에는 방문한 웹 사이트 또는 이메일로 받은 링크에서 본 제품 페이지가 포함됩니다.

## <a name="prerequisites"></a>필요한 항목

참여 인사이트의 데이터를 통합하려면 몇 가지 필수 구성 요소를 충족해야 합니다. 

- 참여 인사이트 SDK를 웹 사이트와 통합합니다. 자세한 내용은 [웹 SDK로 시작](../engagement-insights/instrument-website.md)을 참조하십시오.
- 참여 인사이트에서 웹 이벤트를 내보내려면 웹 이벤트 데이터를 대상 그룹 인사이트로 수집하는 데 사용할 ADLS Gen 2 스토리지 계정에 대한 액세스 권한이 필요합니다. 자세한 내용은 [이벤트 내보내기](../engagement-insights/export-events.md)를 참조하십시오.

## <a name="configure-refined-events-in-engagement-insights"></a>참여 인사이트에서 정제된 이벤트 구성

관리자가 참여 인사이트 SDK를 사용하여 웹 사이트를 구성한 후 사용자가 웹 페이지를 보거나 어딘가를 클릭하면 *기본 이벤트* 가 수집됩니다. 기본 이벤트는 많은 세부 정보를 포함하는 경향이 있습니다. 사용 사례에 따라 기본 이벤트에 있는 데이터의 하위 집합만 필요합니다. 참여 인사이트를 사용하면 선택한 기본 이벤트의 속성만 포함하는 *정제된 이벤트* 를 만들 수 있습니다.     

자세한 내용은 [정제된 이벤트 만들기 및 수정 ](../engagement-insights/refined-events.md)을 참조하십시오.

정제된 이벤트를 만들 때 고려할 사항: 

- 정제된 이벤트에 대한 의미 있는 이름을 제공하십시오. 이는 대상 그룹 인사이트에서 활동 이름으로 사용됩니다.
- 대상 그룹 인사이트에서 활동을 만들려면 최소한 다음 특성을 선택하십시오. 
    - Signal.Action.Name-활동 세부 정보 표시
    - Signal.User.Id-고객 ID로 매핑하는 데 사용
    - Signal.View.Uri-세그먼트 또는 측정값에 대한 기준으로 웹 주소로 사용됨
    - Signal.Export.Id-이벤트의 기본 키로 사용 <!-- system generated, do we need to list?-->
    - Signal.Timestamp-활동의 날짜와 시간을 결정

사용 사례에 중요한 이벤트 및 페이지에 초점을 맞추려면 필터를 선택하십시오. 이 예에서는 "이메일 프로모션" 작업 이름을 사용합니다.

## <a name="export-the-refined-web-events"></a>정제된 웹 이벤트 내보내기 

정제된 이벤트를 정의한 후에는 대상 그룹 인사이트에서 수집을 위한 데이터 원본으로 설정할 수 있는 Azure Data Lake Storage로 이벤트 데이터 내보내기를 구성해야 합니다. 웹 속성에서 이벤트가 이동하면 내보내기가 계속 발생합니다.

자세한 내용은 [이벤트 내보내기](../engagement-insights/export-events.md)를 참조하십시오.

## <a name="ingest-event-data-to-audience-insights"></a>이벤트 데이터를 대상 그룹 인사이트로 수집

정제된 이벤트를 정의하고 내보내기를 구성했으므로 이제 데이터를 대상 그룹 인사이트로 수집합니다. Common Data Model 폴더를 기반으로 새 데이터 원본을 만들어야 합니다. 이벤트를 내보낼 스토리지 계정의 세부 정보를 입력합니다. *default.cdm.json* 파일에서 수집할 정제된 이벤트를 선택하고 대상 그룹 인사이트에서 엔터티를 만듭니다.

자세한 내용은 [Azure Data Lake 계정을 사용하여 Common Data Model 폴더에 연결](connect-common-data-model.md)을 참조


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>정제된 이벤트 데이터를 고객 프로필의 활동으로 연결

엔터티 수집을 완료한 후 고객 프로필에 대한 활동을 구성할 수 있습니다.

자세한 내용은 [고객 활동](activities.md)을 참조하세요.

:::image type="content" source="media/web-event-activity.png" alt-text="활동 편집 창이 확장되고 필드가 채워진 활동 페이지입니다.":::

다음 매핑을 사용하여 새 활동을 구성합니다. 

- **기본 키:** 참여 인사이트의 모든 이벤트 기록에 사용할 수 있는 고유 ID인 Signal.Export.Id입니다. 이 속성은 자동으로 생성됩니다.

- **타임스탬프:** 이벤트 속성의 Signal.Timestamp입니다.

- **이벤트:** 추적하려는 이벤트 이름인 Signal.Name입니다.

- **웹 주소:** 이벤트를 생성한 페이지의 URI를 참조하는 Signal.View.Uri입니다.

- **세부 정보:** 이벤트와 연결할 정보를 나타내는 Signal.Action.Name입니다. 이 경우 선택된 속성은 이벤트가 이메일 프로모션 용임을 나타냅니다.

- **활동 유형:** 이 예에서는 기존 활동 유형 WebLog를 선택합니다. 이 선택 항목은 예측 모델을 실행하거나 이 활동 유형을 기반으로 세그먼트를 만드는 데 유용한 필터 옵션입니다.

- **관계 설정:** 이 중요한 설정은 활동을 기존 고객 프로필에 연결합니다. **Signal.User.Id** 는 수집할 SDK에 구성된 식별자이며 대상 그룹 인사이트에 구성된 다른 데이터 소스의 사용자 ID와 관련이 있습니다. 이 예에서는 데이터 통합 프로세스의 맵 단계에서 정의된 기본 키인 Signal.User.Id와 RetailCustomers:CustomerRetailId 간의 관계를 구성합니다.


활동을 처리한 후 고객 기록을 검토하고 고객 카드를 열어 시간 표시줄의 참여 인사이트에서 활동을 볼 수 있습니다. 

> [!TIP]
> 참여 인사이트 활동이 있는 고객 ID를 찾으려면 **엔터티** 로 이동하여 UnifiedActivity 엔터티에 대한 데이터를 미리 봅니다. ActivityTypeDisplay = WebLog에는 위의 예에서 구성된 참여 인사이트 활동이 포함됩니다. **고객** 페이지에서 해당 레코드 중 하나와 해당 ID에 대한 고객 ID를 복사합니다.

## <a name="next-steps"></a>다음 단계

이제 [세그먼트](segments.md), [측정값](measures.md) 및 [예측](predictions.md)을 만들어 고객과 의미 있는 관계를 맺을 수 있습니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]