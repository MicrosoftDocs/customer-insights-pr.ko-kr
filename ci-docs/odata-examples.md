---
title: Customer Insights API에 대한 OData 쿼리 예제
description: Customer Insights API를 쿼리하여 데이터를 검토하기 위해 OData(Open Data Protocol)에 대해 일반적으로 사용되는 예입니다.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 26e56a3bab01ba55284a52e72efbcbfbaadaad6f
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387210"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>Customer Insights API에 대한 OData 쿼리 예제

OData(Open Data Protocol)는 HTTP와 같은 핵심 프로토콜을 기반으로 구축된 데이터 액세스 프로토콜입니다. 웹용 REST와 같이 일반적으로 허용되는 방법론을 사용합니다. OData 서비스를 사용하는 데 사용할 수 있는 다양한 종류의 라이브러리와 도구가 있습니다.

[Customer Insights API](apis.md)를 기반으로 고유한 구현을 구축하는 데 도움이 되도록 자주 요청되는 몇 가지 예시 쿼리를 검토하십시오.

대상 환경에서 작동하도록 쿼리 샘플을 수정합니다.

- {serviceRoot}:`https://api.ci.ai.dynamics.com/v1/instances/{instanceId}/data` 여기서{instanceId}는 쿼리하려는 Customer Insights 환경의 GUID입니다. [ListAllInstances 작업](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances)을 사용하면 액세스 권한이 있는 {InstanceId}를 찾을 수 있습니다.
- {CID}: 통합 고객 레코드의 GUID입니다. 예: `ce759201f786d590bf2134bff576c369`
- {AlternateKey}: 데이터 원본에 있는 고객 레코드의 기본 키 식별자입니다. 예: `CNTID_1002`
- {DSname}: Customer Insights에 수집되는 데이터 원본의 엔터티 이름이 있는 문자열입니다. 예: `Website_contacts`
- {SegmentName}: Customer Insights에 있는 세그먼트의 출력 엔터티 이름이 있는 문자열입니다. 예: `Male_under_40`

## <a name="customer"></a>고객 님

*고객* 엔터티에 대한 샘플 쿼리입니다.

|쿼리 유형 |예  | 노트  |
|---------|---------|---------|
|단일 고객 ID     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|대체 키    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  대체 키는 통합 고객 엔터티에 유지됩니다       |
|선택   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|-    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|대체 키 + In   | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|검색  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   검색 문자열에 대한 상위 10개 결과를 반환합니다      |
|세그먼트 구성원 자격  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | 세그먼트화 엔터티에서 미리 설정된 행 수를 반환합니다.      |
|고객용 세그먼트 멤버십 | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'&IsMemberOfSegment('{SegmentName}')`     | 고객이 지정된 세그먼트의 구성원인 경우 고객 프로필을 반환함     |

## <a name="unified-activity"></a>통합 활동

*UnifiedActivity* 엔터티에 대한 샘플 쿼리입니다.

|쿼리 유형 |예  | 노트  |
|---------|---------|---------|
|CID 활동     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | 특정 고객 프로필의 활동을 나열합니다 |
|활동 시간 프레임    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  시간 프레임의 고객 프로필 활동       |
|활동 유형입니다.    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|표시 이름별 활동     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|활동 정렬    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  오름차순 또는 내림차순 활동 정렬       |
|세그먼트 멤버십에서 확장된 활동  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>다른 예제

다른 엔터티에 대한 샘플 쿼리입니다.

|쿼리 유형 |예  | 노트  |
|---------|---------|---------|
|CID 측정    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|보강된 CID 브랜드    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|보강된 CID 관심사    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|In-Clause + 확장     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>지원되지 않는 OData 쿼리

다음 쿼리는 Customer Insights에서 지원되지 않습니다.

- 수집된 원본 엔터티의 `$filter`. Customer Insights에서 생성하는 시스템 엔터티에 대해서만 $filter 쿼리를 실행할 수 있습니다.
- `$search` 쿼리에서 `$expand`. 예: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- 특성의 하위 집합만 선택된 경우 `$select`에서 `$expand`. 예: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand`는 특정 고객에 대한 브랜드 또는 관심도를 보강합니다. 예: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- 대체 키를 통해 예측 모델 출력 엔터티를 쿼리합니다. 예: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
