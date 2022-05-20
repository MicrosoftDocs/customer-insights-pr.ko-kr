---
title: Dynamics 365 Customer Insights API에 대한 OData 예시
description: Customer Insights API를 쿼리하여 데이터를 검토하기 위해 OData(Open Data Protocol)에 대해 일반적으로 사용되는 예입니다.
ms.date: 05/10/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 007278e1330e1a8e64d524ded8496acaf83b874c
ms.sourcegitcommit: a50c5e70d2baf4db41a349162fd1b1f84c3e03b6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740042"
---
# <a name="odata-query-examples"></a>OData 쿼리 예시

OData(Open Data Protocol)는 HTTP와 같은 핵심 프로토콜을 기반으로 구축된 데이터 액세스 프로토콜입니다. 웹용 REST와 같이 일반적으로 허용되는 방법론을 사용합니다. OData 서비스를 사용하는 데 사용할 수 있는 다양한 종류의 라이브러리와 도구가 있습니다.

이 문서에서는 [Customer Insights APIs](apis.md)를 기반으로 자체 구현을 구축하는 데 도움이 되도록 자주 요청되는 몇 가지 예제 쿼리를 나열합니다.

대상 환경에서 작동하도록 쿼리 샘플을 수정해야 합니다. 

- {serviceRoot}:`https://api.ci.ai.dynamics.com/v1/instances/{instanceId}` 여기서{instanceId}는 쿼리하려는 Customer Insights 환경의 GUID입니다. [ListAllInstances 작업](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances)을 사용하면 액세스 권한이 있는 {InstanceId}를 찾을 수 있습니다.
- {CID}: 통합 고객 레코드의 GUID입니다. 예: `ce759201f786d590bf2134bff576c369`
- {AlternateKey}: 데이터 원본에 있는 고객 레코드의 기본 키 식별자입니다. 예: `CNTID_1002`
- {DSname}: Customer Insights에 수집되는 데이터 원본의 엔터티 이름이 있는 문자열입니다. 예: `Website_contacts`
- {SegmentName}: Customer Insights에 있는 세그먼트의 출력 엔터티 이름이 있는 문자열입니다. 예: `Male_under_40`

## <a name="customer"></a>고객 님

다음 표에는 *고객* 엔터티에 대한 샘플 쿼리 집합이 포함되어 있습니다.


|쿼리 유형 |예  | 노트  |
|---------|---------|---------|
|단일 고객 ID     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|대체 키    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}' `         |  대체 키는 통합 고객 엔터티에 유지됩니다       |
|선택   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|-    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|대체 키 + In   | `Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|검색  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   검색 문자열에 대한 상위 10개 결과를 반환합니다      |
|세그먼트 구성원 자격  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10  `     | 세그먼트화 엔터티에서 미리 설정된 행 수를 반환합니다.      |

## <a name="unified-activity"></a>통합 활동

다음 표에는 *UnifiedActivity* 엔터티에 대한 샘플 쿼리 집합이 포함되어 있습니다.

|쿼리 유형 |예  | 노트  |
|---------|---------|---------|
|CID 활동     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | 특정 고객 프로필의 활동을 나열합니다 |
|활동 시간 프레임    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  시간 프레임의 고객 프로필 활동       |
|활동 유형입니다.    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|표시 이름별 활동     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’ `        | |
|활동 정렬    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  오름차순 또는 내림차순 활동 정렬       |
|세그먼트 멤버십에서 확장된 활동  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>다른 예

다음 표에는 다른 엔터티에 대한 샘플 쿼리 집합이 포함되어 있습니다.

|쿼리 유형 |예  | 노트  |
|---------|---------|---------|
|CID 측정    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|보강된 CID 브랜드    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|보강된 CID 관심사    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|In-Clause + 확장     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |
