---
title: Microsoft Dataverse에서 Customer Insights 데이터로 작업
description: Customer Insights와 Microsoft Dataverse를 연결하고 Dataverse로 내보내는 출력 엔터티를 이해하는 방법을 알아봅니다.
ms.date: 08/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 9433c411a2c7eb0db137c6392578993d47be82a2
ms.sourcegitcommit: 8559ca47a22d1d7cd9be13531c2eaf0c1083942b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2022
ms.locfileid: "9671259"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Microsoft Dataverse에서 Customer Insights 데이터로 작업

Customer Insights는 [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro)에서 사용 가능한 출력 엔터티를 만드는 옵션을 제공합니다. 이 통합을 통해 로우 코드/코드 없음 접근 방식을 통해 손쉬운 데이터 공유 및 사용자 지정 개발이 가능합니다. [출력 엔터티](#output-entities)는 Dataverse 환경에서 테이블로 사용할 수 있습니다. Dataverse 테이블을 기반으로 하는 다른 애플리케이션의 데이터를 사용할 수 있습니다. 이러한 표를 사용하면 Power Automate을 통한 자동화된 워크플로 또는 Power Apps로 앱 빌드와 같은 시나리오를 사용할 수 있습니다.

Dataverse 환경에 연결하면 [Power Platform 데이터 흐름 및 게이트웨이를 사용하여 온프레미스 데이터 원본에서 데이터를 수집](connect-power-query.md#add-data-from-on-premises-data-sources)할 수도 있습니다.

## <a name="prerequisites"></a>전제 조건

- Customer Insights 및 Dataverse 환경은 동일한 지역에서 호스팅되어야 합니다.
- Dataverse 환경에서 설정된 전역 관리자 역할입니다. 이 [Dataverse 환경이 연결되어](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) 있는지 확인하여 특정 보안 그룹에 추가하고 해당 보안 그룹에 추가되었는지 확인하십시오.
- 연결하려는 Dataverse 환경과 이미 연결된 다른 Customer Insights 환경이 없습니다. [Dataverse 환경에 대한 기존 연결 제거](#remove-an-existing-connection-to-a-dataverse-environment) 방법을 알아보세요.
- 환경을 [내 Azure Data Lake Storage 사용](own-data-lake-storage.md)으로 구성한 경우 단일 스토리지 계정에 연결된 Microsoft Dataverse 환경입니다.

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse 스토리지 용량 획득 자격

Customer Insights를 구독하면 조직의 기존 [Dataverse 스토리지 용량](/power-platform/admin/capacity-storage)을 추가로 얻을 수 있습니다. 추가된 용량은 구독에 사용하는 프로필 개수에 따라 다릅니다.

**예제:**

예를 들어 고객 프로필 100,000개당 15GB의 데이터베이스 스토리지와 20GB의 파일 스토리지가 제공됩니다. 구독에 300,000개의 고객 프로필이 포함된 경우 총 스토리지 용량은 45GB(3 x 15GB) 데이터베이스 스토리지 및 60GB 파일 스토리지(3 x 20GB)입니다. 마찬가지로 계정이 30K인 B-to-B 구독이 있는 경우 총 스토리지 용량은 45GB(3 x 15GB) 데이터베이스 스토리지 및 60GB 파일 스토리지(3 x 20GB)입니다.

로그 용량은 늘지 않고 조직에 맞게 설정됩니다.

용량 획득 자격에 대한 자세한 내용은 [Dynamics 365 라이선싱 가이드](https://go.microsoft.com/fwlink/?LinkId=866544)를 참조하세요.

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Dataverse 환경을 Customer Insights에 연결

**Microsoft Dataverse** 단계를 통해 [Customer Insights 환경을 생성](create-environment.md)하는 동안 Customer Insights를 Dataverse 환경과 연결할 수 있습니다.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="Microsoft Dataverse와의 데이터 공유는 새로운 환경에서 자동으로 활성화됩니다.":::

1. Dataverse 환경에 대한 URL을 제공하거나 생성을 위해 비워 두십시오.

   > [!NOTE]
   > Customer Insights와 Dataverse 간의 연결을 설정한 후에는 Dataverse 환경에서 조직 이름을 바꾸지 않아야 합니다. 조직의 이름은 Dataverse URL에서 사용되며 변경된 이름으로 인해 Customer Insights와 연결이 끊길 수 있습니다.

   [Power Platform 관리자는 새로운 Dataverse 환경을 만들 수 있는 사람을 제어할 수 있습니다](/power-platform/admin/control-environment-creation). 새로운 Customer Insights 환경을 설정하려고 하지만 설정할 수 없는 경우 관리자가 관리자를 제외한 모든 사람에 대해 Dataverse 환경 생성을 비활성화했을 수 있습니다.

1. 고유한 Data Lake Storage 계정을 사용하는 경우:
   1. Dataverse와 **데이터 공유 활성화** 를 선택합니다.
   1. **권한 식별자** 를 입력합니다. 권한 식별자를 얻으려면 [자체 Azure Data Lake Storage에서 Dataverse와 데이터 공유를 활성화](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)하십시오.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>자체 Azure Data Lake Storage에서 Dataverse와 데이터 공유 활성화(프리뷰)

[자체 Azure Data Lake Storage 계정](own-data-lake-storage.md)에서 Customer Insights 환경을 설정하는 사용자에게 스토리지 계정의 `customerinsights` 컨테이너에 대한 최소 **Storage Blob 데이터 리더** 권한이 있는지 확인합니다.

> [!NOTE]
> 데이터 공유는 자체 Azure Data Lake Storage 계정을 사용하는 경우에만 적용할 수 있습니다. Customer Insights 환경에서 기본 Dataverse 스토리지를 사용하는 경우 이 설정을 사용할 수 없습니다.

### <a name="limitations"></a>제한 사항

- Dataverse 조직과 Azure Data Lake Storage 계정 간에 일대일 매핑만 가능합니다. Dataverse 조직이 스토리지 계정에 연결되면 다른 스토리지 계정에 연결할 수 없습니다. 이 제한은 Dataverse가 여러 스토리지 계정을 채우는 것을 방지합니다.
- Azure Data Lake Storage 계정은 방화벽 뒤에 있기 때문에 액세스하기 위해 Azure Private Link 설정이 필요한 경우 데이터 공유가 작동하지 않습니다. Dataverse는 현재 Private Link를 통한 비공개 엔드포인트 연결을 지원하지 않습니다.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>자체 Azure Data Lake Storage에 보안 그룹 설정

1. Azure 구독에 두 개의 보안 그룹(**Reader** 보안 그룹 하나와 **Contributor** 보안 그룹 하나)을 만들고 Microsoft Dataverse 서비스를 두 보안 그룹의 소유자로 설정합니다.

1. 이러한 보안 그룹을 통해 스토리지 계정의 `customerinsights` 컨테이너에서 액세스 제어 목록(ACL)을 관리합니다.
   1. Microsoft Dataverse 서비스 및 Dynamics 365 Marketing과 같은 Dataverse 기반 비즈니스 애플리케이션을 **읽기 전용** 권한이 있는 **Reader** 보안 그룹에 추가합니다.
   1. Customers Insights 애플리케이션 *만* **Contributor** 보안 그룹에 추가하여 프로필과 인사이트를 작성할 수 있는 **읽고 쓰기** 권한을 모두 부여합니다.

### <a name="set-up-powershell"></a>PowerShell 설정

PowerShell 스크립트를 실행하도록 PowerShell을 설정합니다.

1. 최신 버전의 [Graph용 Azure Active Directory PowerShell](/powershell/azure/active-directory/install-adv2)을 설치하십시오.
   1. PC에서 키보드의 Windows 키를 선택하고 **Windows PowerShell** 을 검색하고 **관리자 권한으로 실행** 을 선택합니다.
   1. 열리는 PowerShell 창에 `Install-Module AzureAD`를 입력합니다.

1. 3개의 모듈을 가져옵니다.
   1. PowerShell 창에서 `Install-Module -Name Az.Accounts`을 입력하고 단계를 따릅니다.
   1. `Install-Module -Name Az.Resources` 및 `Install-Module -Name Az.Storage`에 대해 반복합니다.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>PowerShell 스크립트를 실행하고 권한 식별자를 얻습니다

1. 엔지니어의 [GitHub 리포지토리](https://github.com/trin-msft/byol)에서 실행하는 데 필요한 두 개의 PowerShell 스크립트를 다운로드합니다.
   - `CreateSecurityGroups.ps1`: 테넌트 관리자 권한이 필요합니다.
   - `ByolSetup.ps1`: 스토리지 계정/컨테이너 수준에서 Storage Blob 데이터 담당자 권한이 필요합니다. 이 스크립트는 권한을 생성합니다. 스크립트를 성공적으로 실행한 후 역할 할당을 수동으로 제거할 수 있습니다.

1. Azure Data Lake Storage가 포함된 Azure 구독 ID를 제공하여 Windows PowerShell에서 `CreateSecurityGroups.ps1`을 실행합니다. 편집기에서 PowerShell 스크립트를 열어 추가 정보와 구현된 논리를 검토합니다.

   이 스크립트는 Azure 구독에 두 개의 보안 그룹을 만듭니다. 하나는 리더 그룹용이고 다른 하나는 기여자 그룹용입니다. Microsoft Dataverse 서비스는 이 두 보안 그룹의 담당자입니다.

1. 이 스크립트에 의해 생성된 보안 그룹 ID 값을 모두 `ByolSetup.ps1` 스크립트에서 사용하도록 저장합니다.

   > [!NOTE]
   > 테넌트에서 보안 그룹 생성을 비활성화할 수 있습니다. 이 경우 수동 설정이 필요하고 Azure AD 관리자는[ 보안 그룹 생성을 활성화](/azure/active-directory/enterprise-users/groups-self-service-management)해야 합니다.

1. Azure Data Lake Storage, 스토리지 계정 이름, 리소스 그룹 이름, 리더 및 기여자 보안 그룹 ID 값이 포함된 Azure 구독 ID를 제공하여 Windows PowerShell에서 `ByolSetup.ps1`을 실행합니다. 편집기에서 PowerShell 스크립트를 열어 추가 정보와 구현된 논리를 검토합니다.

   이 스크립트는 Microsoft Dataverse 서비스 및 모든 Dataverse 기반 비즈니스 애플리케이션에 필요한 역할 기반 액세스 제어를 추가합니다. 또한 `CreateSecurityGroups.ps1` 스크립트로 생성된 보안 그룹에 대한 `customerinsights` 컨테이너의 액세스 제어 목록(ACL)을 업데이트합니다. 기여자 그룹에는 *rwx* 권한이 부여되고 리더 그룹에는 *r-x* 권한만 부여됩니다.

1. 다음과 같은 출력 문자열을 복사합니다. `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. 복사한 출력 문자열을 Microsoft Dataverse 환경 구성 단계의 **권한 식별자** 필드에 입력합니다.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Microsoft Dataverse를 사용하여 자체 Azure Data Lake Storage에서 데이터를 공유할 수 있도록 하는 구성 옵션.":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Dataverse 환경에 대한 기존 연결 제거

Dataverse 환경에 연결할 때 오류 메시지 **이 CDS 조직은 이미 다른 Customer Insights 인스턴스에 연결되어 있습니다** 는 Dataverse 환경이 이미 Customer Insights 환경에서 사용되고 있음을 의미합니다. Dataverse 환경에서 전역 관리자로 기존 연결을 제거할 수 있습니다. 변경 사항을 채우는 데 몇 시간이 걸릴 수 있습니다.

1. [Power Apps](https://make.powerapps.com)로 이동합니다.
1. 환경 선택기에서 환경을 선택합니다.
1. **솔루션** 으로 이동합니다.
1. **Dynamics 365 Customer Insights 고객 카드 추가 기능(프리뷰)** 이라는 솔루션을 제거하거나 삭제합니다.

OR

1. Dataverse 환경을 엽니다.
1. **고급 설정** > **솔루션** 으로 이동합니다.
1. **CustomerInsightsCustomerCard** 솔루션을 제거합니다.

종속성으로 인해 연결 제거가 실패하면 종속성도 제거해야 합니다. 자세한 내용은 [종속성 제거](/power-platform/alm/removing-dependencies)를 참조하십시오.

## <a name="output-entities"></a>출력 엔터티

Customer Insights의 일부 출력 엔터티는 Dataverse의 테이블로 사용할 수 있습니다. 아래 섹션에서는 이러한 테이블의 예상 스키마를 설명합니다.

- [CustomerProfile](#customerprofile)
- [ContactProfile](#contactprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [보강](#enrichment)
- [예측](#prediction)
- [세그먼트 구성원 자격](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

이 테이블에는 Customer Insights의 통합 고객 프로필이 포함되어 있습니다. 통합 고객 프로필의 스키마는 데이터 통합 프로세스에 사용된 엔터티 및 특성에 따라 다릅니다. 고객 프로필 스키마에는 일반적으로 [CustomerProfile에 대한 Common Data Model 정의](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) 특성의 하위 집합이 포함됩니다. B-to-B 시나리오의 경우 고객 프로필에는 통합 거래처가 포함되고 스키마에는 일반적으로 [거래처의 공통 데이터 모델 정의](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/account) 속성의 하위 집합이 포함됩니다.

### <a name="contactprofile"></a>ContactProfile

ContactProfile에는 연락처에 대한 통합 정보가 포함되어 있습니다. 연락처는 B-to-B 시나리오에서 [거래처에 매핑된 개인](data-unification-contacts.md)입니다.

| Column                       | Type                | Description     |
| ---------------------------- | ------------------- | --------------- |
|  BirthDate            | 날짜/시간       |  연락처의 생년월일               |
|  시/군/구                 | 문자 |  연락처 주소의 시/군/구               |
|  ContactId            | 문자 |  연락처 프로필의 ID               |
|  ContactProfileId     | 고유 식별자   |  연락처에 대한 GUID               |
|  CountryOrRegion      | 문자 |  연락처 주소의 국가/지역               |
|  고객 ID           | 문자 |  연락처가 매핑된 계정의 ID               |
|  EntityName           | 문자 |  데이터를 가져오는 엔터티                |
|  FirstName            | 문자 |  연락처의 이름               |
|  성별               | 문자 |  연락처의 성별               |
|  ID                   | 문자 |  `Identifier`를 기반으로 하는 결정적 GUID               |
|  식별자           | 문자 |  연락처 프로필의 내부 ID: `ContactProfile|CustomerId|ContactId`               |
|  직함             | 문자 |  연락처의 직위               |
|  LastName             | 문자 |  연락처의 성               |
|  PostalCode           | 문자 |  연락처 주소의 우편 번호               |
|  PrimaryEmail         | 문자 |  연락처의 이메일 주소               |
|  PrimaryPhone         | 문자 |  연락처의 전화 번호               |
|  시/도      | 문자 |  연락처 주소의 시/도               |
|  StreetAddress        | 문자 |  연락처 주소의 도로명               |

### <a name="alternatekey"></a>AlternateKey

AlternateKey 테이블에는 통합 프로세스에 참여한 엔터티의 키가 포함됩니다.

|Column  |Type  |Description  |
|---------|---------|---------|
|DataSourceName    |문자         | 데이터 원본의 이름입니다. 예: `datasource5`        |
|EntityName        | 문자        | Customer Insights의 엔터티 이름입니다. 예: `contact1`        |
|AlternateValue    |문자         |고객 ID에 매핑된 대체 ID입니다. 예: `cntid_1078`         |
|KeyRing           | 문자        | JSON 값  </br> 샘플: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey": "cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|고객 ID         | 문자        | 통합 고객 프로필의 ID입니다.         |
|AlternateKeyId     | 고유 식별자        |  `Identifier`를 기반으로 하는 AlternateKey 결정적 GUID      |
|식별자 |   문자      |   `DataSourceName|EntityName|AlternateValue`  </br> 샘플: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

이 테이블에는 Customer Insights에서 사용할 수 있는 사용자의 활동이 포함되어 있습니다.

| Column            | Type        | Description                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| 고객 ID        | 문자      | 고객 프로필 ID                                                                      |
| ActivityId        | 문자      | 고객 활동의 내부 ID(기본 키)                                       |
| SourceEntityName  | 문자      | 원본 엔터티의 이름                                                                |
| SourceActivityId  | 문자      | 원본 엔터티의 기본 키                                                       |
| ActivityType      | 문자      | 의미론적 활동 유형 또는 사용자 지정 활동의 이름                                        |
| ActivityTimeStamp | 날짜/시간    | 활동 타임 스탬프                                                                      |
| Title             | 문자      | 활동 제목 또는 이름                                                               |
| Description       | 문자      | 활동 설명                                                                     |
| URL               | 문자      | 활동과 관련된 특정한 외부 URL에 연결                                         |
| SemanticData      | 문자 | 활동 유형과 관련된 특정한 의미론적 매핑 필드에 대한 키 값 쌍 목록을 포함합니다. |
| RangeIndex        | 문자      | 활동 타임라인 및 유효 범위 쿼리를 정렬하는 데 사용되는 Unix 타임스탬프 |
| UnifiedActivityId   | 고유 식별자 | 고객 활동의 내부 ID(ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

이 테이블에는 고객 특성 기반 측정값의 출력 데이터가 포함되어 있습니다.

| Column             | Type             | Description                 |
|--------------------|------------------|-----------------------------|
| 고객 ID         | 문자           | 고객 프로필 ID        |
| 측정값           | 문자      | 주어진 고객의 측정 이름 및 값에 대한 키 값 쌍 목록을 포함합니다. |
| 식별자 | 문자           | `Customer_Measure|CustomerId` |
| CustomerMeasureId | 고유 식별자     | 고객 프로필 ID |

### <a name="enrichment"></a>보강

이 테이블에는 보강 프로세스의 출력이 포함되어 있습니다.

| Column               | Type             |  Description                                          |
|----------------------|------------------|------------------------------------------------------|
| 고객 ID           | 문자           | 고객 프로필 ID                                 |
| EnrichmentProvider   | 문자           | 보강의 제공자 이름                                  |
| EnrichmentType       | 문자           | 보강의 유형                                      |
| 값               | 문자      | 보강 프로세스에서 생성된 특성 목록 |
| EnrichmentId | 고유 식별자            | `Identifier`에서 생성된 결정적 GUID |
| 식별자   | 문자           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>예측

이 테이블에는 모델 예측의 출력이 포함되어 있습니다.

| Column               | Type        | Description                                          |
|----------------------|-------------|------------------------------------------------------|
| 고객 ID           | 문자      | 고객 프로필 ID                                  |
| ModelProvider        | 문자      | 모델의 제공자 이름                                      |
| 모델                | 문자      | 모델 이름                                                |
| 값               | 문자 | 모델에서 생성된 특성 목록 |
| PredictionId | 고유 식별자       | `Identifier`에서 생성된 결정적 GUID |
| 식별자   | 문자      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>세그먼트 구성원 자격

이 테이블에는 고객 프로필의 세그먼트 구성원 자격 정보가 포함되어 있습니다.

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| 고객 ID        | 문자       | 고객 프로필 ID        |
| SegmentProvider      | 문자       | 세그먼트를 게시하는 앱입니다.      |
| SegmentMembershipType | 문자       | 이 세그먼트 멤버십 레코드에 대한 고객 유형입니다. 고객, 연락처 또는 계정과 같은 여러 유형을 지원합니다. 기본: 고객  |
| 세그먼트       | 문자  | 고객 프로필이 속한 고유 세그먼트 목록      |
| 식별자  | 문자   | 세그먼트 구성원 자격 레코드의 고유 식별자입니다. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| SegmentMembershipId | 고유 식별자      | `Identifier`에서 생성된 결정적 GUID          |

[!INCLUDE [footer-include](includes/footer-banner.md)]
