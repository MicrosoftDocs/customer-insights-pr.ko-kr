---
title: Microsoft Dataverse의 Customer Insights 데이터
description: Customer Insights 엔터티를 Microsoft Dataverse에서 테이블로 사용합니다.
ms.date: 06/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 7157ad930f3cea17c12bd4f95028d291483329d3
ms.sourcegitcommit: e5425f060c8d80f9510283dc610ce70a4e709b1e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/15/2021
ms.locfileid: "6259199"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Microsoft Dataverse에서 Customer Insights 데이터로 작업

Customer Insights는 [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md)에서 사용 가능한 출력 엔터티를 만드는 옵션을 제공합니다. 이 통합을 통해 로우 코드/코드 없음 접근 방식을 통해 손쉬운 데이터 공유 및 사용자 지정 개발이 가능합니다. 출력 엔터티는 Dataverse에서 테이블로 사용할 수 있습니다. 이러한 테이블은 Power Apps을 통해 [Power Automate를 통한 자동화된 워크플로](/power-automate/getting-started), [모델 기반 앱](/powerapps/maker/model-driven-apps/) 및 [캔버스 앱](/powerapps/maker/canvas-apps/)과 같은 시나리오를 활성화합니다. Dataverse 테이블을 기반으로 하는 다른 애플리케이션에 데이터를 사용할 수 있습니다. 현재 구현은 주로 주어진 고객 ID에 대해 사용 가능한 대상 그룹 인사이트 항목에서 데이터를 가져올 수 있는 조회를 지원합니다.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Customer Insights에 Dataverse 환경 연결

**기존 Dataverse 환경이 있는 조직**

이미 Dataverse을 사용하고 있는 조직은 관리자가 대상 그룹 인사이트를 설정할 때 [기존 Dataverse 환경 중 하나를 사용](manage-environments.md#create-an-environment-in-an-existing-organization)할 수 있습니다. Dataverse 환경에 URL을 제공함으로써 새로운 대상 그룹 인사이트 환경에 연결됩니다. 최상의 성능을 보장하려면 Customer Insights 및 Dataverse 환경이 동일한 지역에서 호스팅되어야 합니다.

대상 그룹 인사이트 환경을 만들 때 Dataverse 환경을 연결하려면 **고급 설정** 을 확장합니다. **Microsoft Dataverse 환경 URL** 을 제공하고 **데이터 공유 활성화** 확인란을 선택합니다.

:::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="alt":::

**새 조직**

Customer Insights를 설정할 때 새 조직을 만들면 새 Dataverse 환경이 자동으로 제공됩니다.

> [!NOTE]
> 조직에서 이미 테넌트에서 Dataverse을 사용하고 있는 경우 [Dataverse 환경 생성은 관리자가 제어](/power-platform/admin/control-environment-creation.md)한다는 것을 기억하는 것이 중요합니다. 예를 들어 조직 계정으로 새로운 대상 그룹 인사이트 환경을 설정하고 관리자가 관리자를 제외한 모든 사람에 대해 Dataverse 평가판 환경 생성을 비활성화한 경우 새 평가판 환경을 만들 수 없습니다.
> 
> Customer Insights에서 생성된 Dataverse 평가판 환경에는 3GB의 스토리지가 있으며 이는 테넌트에 부여된 전체 용량에 포함되지 않습니다. 유료 구독은 데이터베이스용으로 15GB, 파일 스토리지용으로 20GB의 Dataverse 권한을 받습니다.

## <a name="output-entities"></a>출력 엔터티

대상 그룹 insights의 일부 출력 엔터티는 Dataverse에서 테이블로 사용할 수 있습니다. 아래 섹션에서는 이러한 테이블의 예상 스키마를 설명합니다.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [보강](#enrichment)
- [예측](#prediction)


### <a name="customerprofile"></a>CustomerProfile

이 테이블에는 Customer Insights의 통합 고객 프로필이 포함되어 있습니다. 통합 고객 프로필의 스키마는 병합 프로세스에 사용되는 엔터티 및 특성에 따라 다릅니다. 고객 프로필 스키마에는 일반적으로 [CustomerProfile에 대한 Common Data Model 정의](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) 특성의 하위 집합이 포함됩니다.

### <a name="alternatekey"></a>AlternateKey

AlternateKey 테이블에는 통합 프로세스에 참여한 엔터티의 키가 포함됩니다.

|Column  |종류  |설명  |
|---------|---------|---------|
|DataSourceName    |String         | 데이터 원본의 이름입니다. 예: `datasource5`        |
|EntityName        | String        | 대상 그룹 인사이트에서 엔터티의 이름입니다. 예: `contact1`        |
|AlternateValue    |String         |고객 ID에 매핑된 대체 ID입니다. 예: `cntid_1078`         |
|KeyRing           | 여러 줄 텍스트        | JSON 값  </br> 샘플: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey": "cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|고객 ID         | String        | 통합 고객 프로필의 ID입니다.         |
|AlternateKeyId     | GUID         |  msdynci_identifier를 기반으로 하는 AlternateKey 결정론적 GUID       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> 샘플: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

이 테이블에는 Customer Insights에서 사용할 수 있는 사용자의 활동이 포함되어 있습니다.

| Column            | 종류        | 설명                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| 고객 ID        | String      | 고객 프로필 ID                                                                      |
| ActivityId        | String      | 고객 활동의 내부 ID(기본 키)                                       |
| SourceEntityName  | String      | 원본 엔터티의 이름                                                                |
| SourceActivityId  | String      | 원본 엔터티의 기본 키                                                       |
| ActivityType      | String      | 의미론적 활동 유형 또는 사용자 지정 활동의 이름                                        |
| ActivityTimeStamp | DATETIME    | 활동 타임 스탬프                                                                      |
| 직함             | String      | 활동 제목 또는 이름                                                               |
| 설명       | String      | 활동 설명                                                                     |
| URL               | String      | 활동과 관련된 특정한 외부 URL에 연결                                         |
| SemanticData      | JSON 문자열 | 활동 유형과 관련된 특정한 의미론적 매핑 필드에 대한 키 값 쌍 목록을 포함합니다. |
| RangeIndex        | String      | 활동 타임라인 및 유효 범위 쿼리를 정렬하는 데 사용되는 Unix 타임스탬프 |
| mydynci_unifiedactivityid   | GUID | 고객 활동의 내부 ID(ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

이 테이블에는 고객 특성 기반 측정값의 출력 데이터가 포함되어 있습니다.

| Column             | 종류             | 설명                 |
|--------------------|------------------|-----------------------------|
| 고객 ID         | String           | 고객 프로필 ID        |
| 측정           | JSON 문자열      | 주어진 고객의 측정 이름 및 값에 대한 키 값 쌍 목록을 포함합니다. | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | 고객 프로필 ID |


### <a name="enrichment"></a>보강

이 테이블에는 보강 프로세스의 출력이 포함되어 있습니다.

| Column               | 종류             |  설명                                          |
|----------------------|------------------|------------------------------------------------------|
| 고객 ID           | String           | 고객 프로필 ID                                 |
| EnrichmentProvider   | String           | 보강의 제공자 이름                                  |
| EnrichmentType       | String           | 보강의 유형                                      |
| 값               | JSON 문자열      | 보강 프로세스에서 생성된 특성 목록 |
| msdynci_enrichmentid | GUID             | msdynci_identifier에서 생성된 결정론적 GUID |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>예측

이 테이블에는 모델 예측의 출력이 포함되어 있습니다.

| Column               | 종류        | 설명                                          |
|----------------------|-------------|------------------------------------------------------|
| 고객 ID           | String      | 고객 프로필 ID                                  |
| ModelProvider        | String      | 모델의 제공자 이름                                      |
| 모델                | String      | 모델 이름                                                |
| 값               | JSON 문자열 | 모델에서 생성된 특성 목록 |
| msdynci_predictionid | GUID        | msdynci_identifier에서 생성된 결정론적 GUID | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |
