---
title: 진단 로그 내보내기(프리뷰)
description: Microsoft Azure Monitor에 로그를 보내는 방법 알아보기
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 60b039173fd938482c782c7394420d4951c222a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245933"
---
# <a name="export-diagnostic-logs-preview"></a>진단 로그 내보내기(프리뷰)

Azure Monitor를 사용해 Customer Insights에서 로그를 전달합니다. Azure Monitor 리소스 로그를 사용하면 로그를 모니터링하고 [Azure Storage](https://azure.microsoft.com/services/storage/), [ Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview)에 보내거나 [Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/)에 스트리밍할 수 있습니다.

Customer Insights는 다음 이벤트 로그를 보냅니다.

- **감사 이벤트**
  - **APIEvent** - Dynamics 365 Customer Insights UI를 통해 변경 내용 추적을 사용 설정합니다.
- **운영 이벤트**
  - **WorkflowEvent** - [데이터 원본](data-sources.md)을 설정하고 데이터를 [통합](data-unification.md), [보강](enrichment-hub.md)하며 다른 시스템으로 [내보낼](export-destinations.md) 수 있습니다. 이러한 단계는 개별적으로 수행할 수 있습니다(예: 단일 내보내기 트리거). 또한 구성된 상태로 실행할 수 있습니다(예: 통합 프로세스를 트리거하는 데이터 원본의 데이터 새로 고침, 보강을 가져오고 데이터를 다른 시스템으로 내보냄). 자세한 내용은 [WorkflowEvent 스키마](#workflow-event-schema)를 참조하십시오.
  - **APIEvent** - 고객 인스턴스에서 Dynamics 365 Customer Insights에 대한 모든 API 호출을 전송합니다. 자세한 내용은 [APIEvent 스키마](#api-event-schema)를 참조하십시오.

## <a name="set-up-the-diagnostic-settings"></a>진단 설정 구성

### <a name="prerequisites"></a>전제 조건

- 사용 중인 [Azure 구독](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- Customer Insights의 [관리자](permissions.md#admin) 권한.
- Azure 기반 대상 리소스에서 [기여자 및 사용자 액세스 관리자 역할](/azure/role-based-access-control/role-assignments-portal). 리소스는 Azure Data Lake Storage 계정, Azure 이벤트 허브 또는 Azure Log Analytics 작업 영역일 수 있습니다. 이 권한은 Customer Insights에서 진단 설정을 구성하는 동안 필요하지만, 설정을 완료한 후 변경할 수 있습니다.
- Azure Storage, Azure 이벤트 허브 또는 Azure Log Analytics 관련 [대상 요구 사항](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements)에 부합됩니다.
- 리소스가 속한 리소스 그룹에서 **독자** 이상의 역할이 있어야 합니다.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Azure Monitor로 진단 설정

1. Customer Insights에서 **관리** > **시스템** 으로 이동하고 **진단** 탭을 선택합니다.

1. **대상 추가** 를 선택합니다.

   :::image type="content" source="media/diagnostics-pane.png" alt-text="진단 연결.":::

1. **진단 대상 이름** 필드에 이름을 입력하십시오.

1. **리소스 유형**(스토리지 계정, 이벤트 허브 또는 로그 분석)을 선택합니다.

1. **구독**, **리소스 그룹**, 대상 리소스에 해당하는 **리소스** 를 선택합니다. [대상 리소스에 대한 구성](#configuration-on-the-destination-resource)에서 권한 및 로그 정보를 확인합니다.

1. [데이터 개인 정보 보호 및 규정 준수](connections.md#data-privacy-and-compliance)를 검토하고 **동의함** 을 선택합니다.

1. **시스템에 연결** 을 선택하여 대상 리소스에 연결합니다. API가 사용 중이고 이벤트를 생성하는 경우 로그는 15분 후에 대상에 표시되기 시작합니다.

## <a name="configuration-on-the-destination-resource"></a>대상 리소스에 대한 구성

리소스 유형에 대한 선택에 따라 다음과 같은 변경 사항이 자동으로 발생합니다.

### <a name="storage-account"></a>Storage account

Customer Insights 서비스 주체는 선택한 리소스에서 **스토리지 계정 기여자** 권한을 얻고 선택한 네임스페이스 아래에 두 개의 컨테이너를 만듭니다.

- **감사 이벤트** 를 포함하는 `insight-logs-audit`
- **운영 이벤트** 를 포함하는 `insight-logs-operational`

### <a name="event-hub"></a>이벤트 허브

Customer Insights 서비스 주체는 선택한 리소스에서 **Azure Event Hubs Data Owner** 권한을 얻고 선택한 네임스페이스 아래에 두 개의 Event Hubs를 만듭니다.

- **감사 이벤트** 를 포함하는 `insight-logs-audit`
- **운영 이벤트** 를 포함하는 `insight-logs-operational`

### <a name="log-analytics"></a>Log Analytics

Customer Insights 서비스 주체는 리소스에 대해 **로그 분석 기여자** 권한을 얻습니다. 로그는 선택한 Log Analytics 작업 영역의 **로그** > **테이블** > **로그 관리** 에서 사용할 수 있습니다. **로그 관리** 솔루션을 확장하고 `CIEventsAudit` 및 `CIEventsOperational` 테이블을 찾습니다.

- **감사 이벤트** 를 포함하는 `CIEventsAudit`
- **운영 이벤트** 를 포함하는 `CIEventsOperational`

**쿼리** 창 아래에서 **감사** 솔루션을 확장하고 `CIEvents`를 검색하여 제공된 예제 쿼리를 찾습니다.

## <a name="remove-a-diagnostics-destination"></a>진단 대상 제거

1. **관리자** > **시스템** 으로 이동하여 **진단** 탭을 선택합니다.

1. 목록에서 진단 대상을 선택합니다.

   > [!TIP]
   > 대상을 제거하면 로그 전달이 중지되지만 Azure 구독 기반 리소스는 삭제되지 않습니다. Azure의 리소스를 삭제하려면 **작업** 열의 링크를 선택하여 선택한 리소스에 대한 Azure Portal을 열고 거기서 삭제합니다. 그런 다음 진단 대상을 삭제합니다.

1. **작업** 열에서 **삭제** 아이콘을 선택합니다.

1. 삭제를 확인하여 대상을 제거하고 로그 전달을 중지합니다.

## <a name="log-categories-and-event-schemas"></a>로그 카테고리 및 이벤트 스키마

현재 [API 이벤트](apis.md) 및 워크플로 이벤트가 지원되며 다음 범주 및 스키마가 적용됩니다.
로그 스키마는 [Azure Monitor 공통 스키마](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema)를 따릅니다.

### <a name="categories"></a>카테고리

Customer Insights는 두 가지 범주를 제공합니다.

- **감사 이벤트**: [API 이벤트](#api-event-schema). 서비스의 구성 변경 사항을 추적합니다. `POST|PUT|DELETE|PATCH` 작업이 이 범주에 속합니다.
- **운영 이벤트**: 서비스를 사용하는 동안 생성된 [API 이벤트](#api-event-schema) 또는 [워크플로 이벤트](#workflow-event-schema)  예를 들어, `GET` 요청 또는 워크플로의 실행 이벤트.

## <a name="event-schemas"></a>이벤트 스키마

API 이벤트와 워크플로 이벤트는 구조가 같지만 몇 가지 차이점이 있습니다. 자세한 내용은 [API 이벤트 스키마](#api-event-schema) 또는 [워크플로 이벤트 스키마](#workflow-event-schema)를 참조하세요.

### <a name="api-event-schema"></a>API 이벤트 스키마

| 필드             | DataType  | 필수/선택 사항 | Description       | 예        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | 타임스탬프 | 필수 항목          | 이벤트의 타임스탬프(UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | 필수 항목          | 이벤트를 발생시킨 인스턴스의 ResourceId         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | 필수 항목          | 이 이벤트가 나타내는 작업의 이름입니다.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | 필수 항목          | 이벤트 로그 범주입니다. `Operational` 또는 `Audit` 중 하나입니다. 모든 POST/PUT/PATCH/DELETE HTTP 요청에는 `Audit` 태그가, 다른 모든 요청에는 `Operational` 태그가 지정됩니다. | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | 필수 항목          | 이벤트의 상태 `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | 선택 항목          | 이벤트의 결과 상태 작업이 REST API 호출에 해당하는 경우 HTTP 상태 코드입니다.        | `200`             |
| `durationMs`      | Long      | 선택 항목          | 작업 기간(밀리초)입니다.     | `133`     |
| `callerIpAddress` | String    | 선택 항목          | 작업이 공개적으로 사용 가능한 IP 주소에서 오는 API 호출에 해당하는 경우 호출자 IP 주소입니다.                                                 | `144.318.99.233`         |
| `identity`        | String    | 선택 항목          | 작업을 수행한 사용자 또는 애플리케이션의 ID를 설명하는 JSON 객체입니다.       | [ID](#identity-schema) 섹션을 참조하세요.     |  
| `properties`      | String    | 선택 항목          | 특정 이벤트 범주에 대한 더 많은 속성이 있는 JSON 객체.      | [속성](#api-properties-schema) 섹션을 참조하세요.    |
| `level`           | String    | 필수 항목          | 이벤트의 심각도 수준입니다.    | `Informational`, `Warning`, `Error` 또는 `Critical`.           |
| `uri`             | String    | 선택 항목          | 절대 요청 URI입니다.    |               |

#### <a name="identity-schema"></a>ID 스키마

`identity` JSON 객체에는 다음과 같은 구조가 있습니다.

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| 필드                         | Description                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | 사용자 또는 앱에 할당된 역할입니다. 자세한 내용은 [사용자 권한](permissions.md)을 참조하십시오.                                     |
| `Authorization.RequiredRoles` | 작업을 수행하는 데 필요한 역할입니다. `Admin` 역할은 모든 작업을 수행할 수 있습니다.                                                    |
| `Claims`                      | 사용자 또는 앱 JWT(JSON 웹 토큰)의 클레임입니다. 클레임 속성은 조직과 Azure Active Directory 구성에 따라 다릅니다. |

#### <a name="api-properties-schema"></a>API 속성 스키마

[API 이벤트](apis.md)에는 다음과 같은 속성이 있습니다.

| 필드                        | Description                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | 항상 `ApiEvent`, 로그 이벤트를 API 이벤트로 표시합니다.                                                                 |
| `properties.userAgent`       | 요청을 보내는 브라우저 에이전트 또는 `unknown`.                                                                        |
| `properties.method`          | HTTP 메서드: `GET/POST/PUT/PATCH/HEAD`                                                                                |
| `properties.path`            | 요청의 상대 경로입니다.                                                                                          |
| `properties.origin`          | 가져오기의 출처를 나타내는 URI 또는 `unknown`.                                                                  |
| `properties.operationStatus` | `Success`: 400 HTTP 상태 코드 < 400 <br> `ClientError`: HTTP 상태 코드 < 500 <br> `Error`: HTTP 상태 >= 500 |
| `properties.tenantId`        | 조직 ID                                                                                                        |
| `properties.tenantName`      | 조직 이름                                                                                              |
| `properties.callerObjectId`  | 호출자의 Azure Active Directory ObjectId입니다.                                                                         |
| `properties.instanceId`      | Customer Insights `instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>워크플로 이벤트 스키마

워크플로에는 여러 단계가 포함됩니다. [데이터 소스 수집](data-sources.md), 데이터 [통합](data-unification.md), [보강](enrichment-hub.md), [내보내기](export-destinations.md). 이러한 모든 단계는 개별적으로 실행되거나 다음 프로세스와 함께 조정될 수 있습니다.

#### <a name="operation-types"></a>작업 유형

| OperationType     | 그룹                                     |
| ----------------- | ----------------------------------------- |
| 수집         | [데이터 원본](data-sources.md)           |
| DataPreparation   | [데이터 원본](data-sources.md)           |
| 지도               | [데이터 통합](data-unification.md)   |
| Match             | [데이터 통합](data-unification.md)   |
| 병합             | [데이터 통합](data-unification.md)   |
| ProfileStore      | [고객 프로필](customer-profiles.md) |
| 검색            | [고객 프로필](customer-profiles.md) |
| 작업          | [활동](activities.md)                  |
| AttributeMeasures | [세그먼트 및 측정값](segments.md)      |
| EntityMeasures    | [세그먼트 및 측정값](segments.md)      |
| 측정값          | [세그먼트 및 측정값](segments.md)      |
| 세분화      | [세그먼트 및 측정값](segments.md)      |
| 보강        | [보강](enrichment-hub.md)                                          |
| 인텔리전스      | [예측](predictions-overview.md)                                          |
| AiBuilder         | [예측](predictions-overview.md)                                          |
| 인사이트          | [예측](predictions-overview.md)                                          |
| Export            | [내보내기](export-destinations.md)                                          |
| ModelManagement   | [예측](custom-models.md)                                           |
| 관계      | [데이터 통합](relationships.md)                                           |

#### <a name="field-description"></a>필드 설명

| 필드           | DataType  | 필수/선택 사항 | Description                                                                                                                                                   | 예                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | 타임스탬프 | 필수 항목          | 이벤트의 타임스탬프(UTC)                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | 필수 항목          | 이벤트를 발생시킨 인스턴스의 ResourceId                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | 필수 항목          | 이 이벤트가 나타내는 작업의 이름입니다. `{OperationType}.[WorkFlow|Task][Started|Completed]`. [작업 유형](#operation-types)을 참조하세요. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | 필수 항목          | 이벤트 로그 범주입니다. 워크플로 이벤트의 경우 항상 `Operational`                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | String    | 필수 항목          | 이벤트의 상태 `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Long      | 선택 항목          | 작업 기간(밀리초)입니다.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | 선택 항목          | 특정 이벤트 범주에 대한 더 많은 속성이 있는 JSON 객체.                                                                                        | [워크플로 속성](#workflow-properties-schema) 하위 섹션을 참조하세요.                                                                                                       |
| `level`         | String    | 필수 항목          | 이벤트의 심각도 수준입니다.                                                                                                                                  | `Informational`, `Warning` 또는 `Error`                                                                                                                                   |

#### <a name="workflow-properties-schema"></a>워크플로 속성 스키마

워크플로 이벤트에는 다음과 같은 속성이 있습니다.

| 필드              | Workflow | 작업 | Description            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | 네      | 네  | 항상 `WorkflowEvent`, 이벤트를 워크플로 이벤트로 표시합니다.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | 네      | 네  | 워크플로 실행의 식별자입니다. 워크플로 실행 내의 모든 워크플로 및 작업에는 같은 `workflowJobId`가 있습니다.                                                                                                                                   |
| `properties.operationType`                   | 네      | 네  | 작업의 식별자는 [작업 유형](#operation-types)을 참조하세요.                                                                                                                                                                               |
| `properties.tasksCount`                      | 네      | 없음   | 워크플로 전용. 워크플로가 트리거하는 작업의 수입니다                                                                                                                                                                                                       |
| `properties.submittedBy`                     | 네      | 없음   | 선택 사항. 워크플로 이벤트 전용. 워크플로를 트리거한 Azure Active Directory [사용자의 objectId](/azure/marketplace/find-tenant-object-id#find-user-object-id)는 `properties.workflowSubmissionKind`도 참조하세요.                                   |
| `properties.workflowType`                    | 네      | 없음   | `full` 또는 `incremental` 새로 고침.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | 네      | 없음   | `OnDemand` 또는 `Scheduled`                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | 네      | 없음   | `Running` 또는 `Successful`                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | 네      | 네  | UTC 타임스탬프`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | 네      | 네  | UTC 타임스탬프`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | 네      | 네  | UTC 타임스탬프`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | 네      | 네  | Customer Insights `instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | 없음       | 네  | - OperationType =`Export`의 경우, 식별자는 내보내기 구성의 guid입니다. <br> - OperationType =`Enrichment`의 경우, 보강의 guid입니다. <br> - OperationType `Measures` 및 `Segmentation`의 경우, 식별자는 엔터티 이름입니다. |
| `properties.friendlyName`                    | 없음       | 네  | 내보내기 또는 처리되는 엔터티의 사용자에게 친숙한 이름입니다.                                                                                                                                                                                           |
| `properties.error`                           | 없음       | 네  | 선택 사항. 자세한 내용이 포함된 오류 메시지입니다.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | 없음       | 네  | 선택 사항. OperationType `Export` 전용. 내보내기 유형을 식별합니다. 자세한 내용은 [내보내기 대상 개요](export-destinations.md)를 참조하세요.                                                                                          |
| `properties.additionalInfo.AffectedEntities` | 없음       | 네  | 선택 사항. OperationType `Export` 전용. 내보내기에 구성된 엔터티 목록이 포함되어 있습니다.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | 없음       | 네  | 선택 사항. OperationType `Export` 전용. 내보내기에 대한 자세한 메시지입니다.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | 없음       | 네  | 선택 사항. OperationType `Segmentation` 전용. 세그먼트에 있는 총 구성원 수를 나타냅니다.                                                                                                                                                    |

[!INCLUDE [footer-include](includes/footer-banner.md)]
