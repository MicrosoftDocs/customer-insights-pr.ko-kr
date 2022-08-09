---
title: 실시간 데이터 수집(미리 보기)
description: Customer Insights의 실시간 기능에 대한 일반 정보입니다.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 403cc9dbd3bddcf67f59b5cb0be936af4d268fc2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195666"
---
# <a name="real-time-data-ingestion-preview"></a>실시간 데이터 수집(미리 보기)

거의 실시간 기능을 통해 고객이 제품 또는 서비스와 수행한 최신 상호 작용을 몇 초 안에 볼 수 있습니다.

[예약된 새로 고침](system.md#schedule-tab)에는 많은 수의 레코드와 여러 가지 복잡한 작업이 포함됩니다. 먼저 데이터 원본에서 데이터를 가져옵니다. 그런 다음 데이터가 통합된 후 데이터는 추가 정보로 보강됩니다. 이 프로세스를 실행할 때마다 몇 분에서 몇 시간이 걸릴 수 있습니다.

실시간 기능은 이후에 예약된 새로 고침이 데이터 원본에서이 데이터를 가져올 때까지 즉시 사용할 데이터를 제공합니다.

실시간 업데이트는 만료 시간이 지난 후 더 이상 데이터 원본의 값을 무시하지 않습니다.

- 프로필 업데이트는 4시간 동안 유지됩니다
- 활동은 30일 동안 유지됩니다

이 값은 변경할 수 있는 API 호출 매개 변수입니다. 이 매개 변수의 사용 목적은 원본 데이터가 신뢰의 소스로 남아 있도록 하는 것입니다. 실시간 업데이트를 더 오래 포함하려면 예정된 다음 새로 고침 중에 가져오도록 데이터 원본에 추가해야 합니다.

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>통합 고객 프로필 필드의 실시간 업데이트

업데이트된 프로필은 몇 초 이내에 고객 카드 보기 또는 기타 시각화에 표시됩니다.

데이터 통합이 발생한 후 실시간 작업이 수행되므로 통합 고객 프로필에만 적용됩니다. 결과적으로 실시간 프로필 변경은 측정, 세그먼트 구성원 자격 또는 보강을 업데이트하지 않습니다.

### <a name="limitations"></a>제한 사항

- 고객 프로필은 업데이트할 수 있지만 만들거나 삭제할 수는 없습니다.
- Power BI 같은 외부 시스템으로 실시간 업데이트 내보내기는 현재로서는 불가능합니다.

## <a name="real-time-creation-of-activities"></a>활동의 실시간 생성

실시간 API를 사용하면 원본 시스템(개별 원본 레코드)의 새 활동을 통합 고객 프로필에 게시할 수 있습니다. 새 활동은 통합 고객 프로필의 타임라인에서 몇 초 내에 통합된 활동으로 제공됩니다. 고객 카드 보기 또는 구성한 다른 시간 표시줄 통합에서 시간 표시줄을 볼 수 있습니다.

> [!NOTE]
>
> - 활동은 변경할 수 없습니다. 일단 만들어진 후에는 변경되지 않습니다.
> - 현재 세그먼트 및 측정 값은 새 활동을 기반으로 업데이트되지 않습니다.
> - 실시간 API를 통해서만 추가된 활동은 내보내기의 일부가 아니며 PowerBI에 표시되지 않습니다.

실시간 API에 연결하는 방법은 다음 두 가지입니다.

- [간접적으로](#connect-via-the-dynamics-365-customer-insights-connector), [Dynamics 365 Customer Insights 커넥터](/connectors/customerinsights/) 사용
- [직접적으로](#connect-directly-to-the-real-time-api), 코드 사용

두 방법 모두 다음과 같은 전제 조건이 적용됩니다.

- Customer Insights 환경
- 통합 고객 프로필
- 구성 및 실행된 활동
- 계정을 인증하기 위한 기여자 또는 관리자 권한

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Dynamics 365 Customer Insights 커넥터를 통해 연결

실시간 API는 코드를 작성하고 배포할 필요 없이 전용 Power Platform커넥터, [Dynamics 365 Customer Insights 커넥터](/connectors/customerinsights/)에서 데이터를 수집할 수 있습니다.    
커넥터는 API와 동일한 실시간 작업을 수행할 수 있습니다. 프리미엄 커넥터에 대한 유효한 라이선스가 필요합니다. 자세한 내용은 [Power Apps 및 Power Automate 라이선싱 FAQ](/power-platform/admin/powerapps-flow-licensing-faq)를 참조하십시오.

- Power Platform [Power Apps 및/또는 Power Automate](/connectors/)
- Azure [Logic Apps](/azure/connectors/apis-list)

흐름 만들기에 대한 자세한 내용은 [Power Automate 설명서](/power-automate/)를 참조하십시오.

## <a name="connect-directly-to-the-real-time-api"></a>실시간 API에 직접 연결

자체 파이프 라인을 구축하고 실시간 API에 직접 연결하여 실시간 기능을 사용할 수 있습니다.    
원본 시스템 형식이나 UnifiedActivity 형식으로 활동을 게시할 수 있습니다. /api/instances/{instanceId}/manage/entities/UnifiedActivity에 API를 호출하여 형식을 가져옵니다.

매개 변수 및 응답을 포함한이 API의 세부 사항은 [Customer Insights API 참조](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights)의 **EntityData** 섹션에서 찾을 수 있습니다. 자세한 내용은 [Customer Insights API 작업](apis.md) 도움말 항목을 참조하세요.

## <a name="understand-your-real-time-usage-with-telemetry"></a>원격 분석으로 실시간 사용 이해

실시간 API에 대한 요청의 양에 대한 개요와 시스템에서 발생할 수 있는 문제에 대한 정보를 가져옵니다. [실시간 원격 분석에 액세스](system.md#api-usage-tab)할 수 있습니다. 


[!INCLUDE [footer-include](includes/footer-banner.md)]
