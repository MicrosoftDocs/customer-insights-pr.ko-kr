---
title: Microsoft Dataverse에서 Customer Insights 데이터로 작업
description: Customer Insights와 Microsoft Dataverse를 연결하고 Dataverse로 내보내는 출력 엔터티를 이해하는 방법을 알아봅니다.
ms.date: 05/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 3848e143bc7cb2f345bc698a274b92148ef00669
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833684"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Microsoft Dataverse에서 Customer Insights 데이터로 작업

Customer Insights는 출력 엔터티를 [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro)로 사용할 수 있도록 하는 옵션을 제공합니다. 이 통합을 통해 로우 코드/코드 없음 접근 방식을 통해 손쉬운 데이터 공유 및 사용자 지정 개발이 가능합니다. [출력 엔터티](#output-entities)는 Dataverse 환경에서 테이블로 사용할 수 있습니다. Dataverse 테이블을 기반으로 하는 다른 애플리케이션의 데이터를 사용할 수 있습니다. 이러한 표를 사용하면 Power Automate을 통한 자동화된 워크플로 또는 Power Apps로 앱 빌드와 같은 시나리오를 사용할 수 있습니다.

Dataverse 환경에 연결하면 [Power Platform 데이터 흐름 및 게이트웨이를 사용하여 온프레미스 데이터 원본에서 데이터를 수집](data-sources.md#add-data-from-on-premises-data-sources)할 수도 있습니다.

## <a name="prerequisites"></a>전제 조건

- Customer Insights 및 Dataverse 환경은 동일한 지역에서 호스팅되어야 합니다.
- Dataverse 환경에서 전역 관리자 역할이 있어야 합니다. 이 [Dataverse 환경이 연결되어](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) 있는지 확인하여 특정 보안 그룹에 추가하고 해당 보안 그룹에 추가되었는지 확인하십시오.
- 연결하려는 Dataverse 환경과 이미 연결된 다른 Customer Insights 환경이 없습니다. [Dataverse 환경에 대한 기존 연결 제거](#remove-an-existing-connection-to-a-dataverse-environment) 방법을 알아보세요.
- Microsoft Dataverse 환경은 단일 스토리지 계정에만 연결할 수 있습니다. 환경을 [Azure Data Lake Storage 사용](own-data-lake-storage.md)으로 구성한 경우에만 적용됩니다.

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Dataverse 환경을 Customer Insights에 연결

**Microsoft Dataverse** 단계를 통해 [Customer Insights 환경을 생성](create-environment.md)하는 동안 Customer Insights를 Dataverse 환경과 연결할 수 있습니다.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="Microsoft Dataverse와의 데이터 공유는 새로운 환경에서 자동으로 활성화됩니다.":::

관리자는 Customer Insights를 구성하여 기존 Dataverse 환경에 연결할 수 있습니다. Dataverse 환경에 대한 URL을 제공함으로써 새로운 Customer Insights 환경에 연결됩니다.

기존 Dataverse 환경을 사용하지 않으려는 경우 시스템은 테넌트의 Customer Insights 데이터에 대한 새 환경을 생성합니다. [Power Platform 관리자는 환경을 만들 수 있는 사람을 제어할 수 있습니다](/power-platform/admin/control-environment-creation). 새로운 Customer Insights 환경을 설정하고 관리자가 관리자를 제외한 모든 사람에 대해 Dataverse 환경 생성을 비활성화한 경우 새 환경을 생성하지 못할 수 있습니다.

데이터 공유 확인란을 선택하여 Dataverse와 **데이터 공유를 활성화** 합니다.

고유한 Data Lake Storage 계정을 사용하는 경우 **권한 식별자** 도 필요합니다. 권한 식별자를 가져오는 방법에 대한 자세한 내용은 다음 섹션을 검토하세요.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>자체 Azure Data Lake Storage에서 Dataverse과 데이터 공유 활성화(프리뷰)

환경에서 [내 Azure Data Lake Storage 계정을 사용](own-data-lake-storage.md)하는 경우 Microsoft Dataverse와 데이터 공유를 활성화하려면 몇 가지 추가 구성이 필요합니다. Customer Insights 환경을 설정하는 사용자는 Azure Data Lake Storage 계정의 *CustomerInsights* 컨테이너에 대해 최소한 **Storage Blob Data Reader** 권한이 있어야 합니다.

1. Azure 구독에 두 개의 보안 그룹(**Reader** 보안 그룹 하나와 **Contributor** 보안 그룹 하나)을 만들고 Microsoft Dataverse 서비스를 두 보안 그룹의 소유자로 설정합니다.
2. 이러한 보안 그룹을 통해 스토리지 계정의 CustomerInsights 컨테이너에서 액세스 제어 목록(ACL)을 관리합니다. Microsoft Dataverse 서비스 및 Dynamics 365 Marketing과 같은 Dataverse 기반 비즈니스 애플리케이션을 **읽기 전용** 권한이 있는 **Reader** 보안 그룹에 추가합니다. Customers Insights 애플리케이션 *만* **Contributor** 보안 그룹에 추가하여 프로필과 인사이트를 작성할 수 있는 **읽고 쓰기** 권한을 모두 부여합니다.

### <a name="limitations"></a>제한 사항

자신의 Azure Data Lake Storage 계정으로 Dataverse을 사용하는 경우 두 가지 제한 사항이 있습니다.

- Dataverse 조직과 Azure Data Lake Storage 계정 간에 일대일 매핑이 있습니다. Dataverse 조직이 스토리지 계정에 연결되면 다른 스토리지 계정에 연결할 수 없습니다. 이 제한은 Dataverse가 여러 스토리지 계정을 채우지 않도록 합니다.
- Azure Data Lake Storage 계정은 방화벽 뒤에 있기 때문에 액세스하기 위해 Azure Private Link 설정이 필요한 경우 데이터 공유가 작동하지 않습니다. Dataverse는 현재 Private Link를 통한 비공개 엔드포인트 연결을 지원하지 않습니다.

### <a name="set-up-powershell"></a>PowerShell 설정

PowerShell 스크립트를 실행하려면 먼저 그에 따라 PowerShell을 설정해야 합니다.

1. 최신 버전의 [Graph용 Azure Active Directory PowerShell](/powershell/azure/active-directory/install-adv2)을 설치하십시오.
   1. PC에서 키보드의 Windows 키를 선택하고 **Windows PowerShell** 을 검색하고 **관리자 권한으로 실행** 을 선택합니다.
   1. 열리는 PowerShell 창에 `Install-Module AzureAD`를 입력합니다.
2. 3개의 모듈을 가져옵니다.
    1. PowerShell 창에서 `Install-Module -Name Az.Accounts`을 입력하고 단계를 따릅니다.
    1. `Install-Module -Name Az.Resources` 및 `Install-Module -Name Az.Storage`에 대해 반복합니다.

### <a name="configuration-steps"></a>구성 단계

1. 엔지니어의 [GitHub 리포지토리](https://github.com/trin-msft/byol)에서 실행하는 데 필요한 두 개의 PowerShell 스크립트를 다운로드합니다.
    1. `CreateSecurityGroups.ps1`
       - 이 PowerShell 스크립트를 실행하려면 *테넌트 관리자* 권한이 필요합니다.
       - 이 PowerShell 스크립트는 Azure 구독에 두 개의 보안 그룹을 만듭니다. 하나는 Reader 그룹용이고 다른 하나는 Contributor 그룹용이며 Microsoft Dataverse 서비스를 이 두 보안 그룹의 소유자로 만듭니다.
       - Azure Data Lake Storage가 포함된 Azure 구독 ID를 제공하여 Windows PowerShell에서 이 PowerShell 스크립트를 실행합니다. 추가 정보와 구현된 논리를 검토하려면 편집기에서 PowerShell 스크립트를 엽니다.
       - `ByolSetup.ps1` 스크립트에서 사용할 것이기 때문에 이 스크립트에서 생성된 보안 그룹 ID 값을 모두 저장합니다.

        > [!NOTE]
        > 테넌트에서 보안 그룹 생성을 비활성화할 수 있습니다. 이 경우 수동 설정이 필요하고 Azure AD 관리자는[ 보안 그룹 생성을 활성화](/azure/active-directory/enterprise-users/groups-self-service-management)해야 합니다.

    2. `ByolSetup.ps1`
        - 이 스크립트를 실행하려면 스토리지 계정/컨테이너 수준에서 *Storage Blob 데이터 소유자* 권한이 필요합니다. 그렇지 않으면 이 스크립트가 자동으로 생성합니다. 스크립트를 성공적으로 실행한 후 역할 할당을 수동으로 제거할 수 있습니다.
        - 이 PowerShell 스크립트는 Microsoft Dataverse 서비스 및 모든 Dataverse 기반 비즈니스 애플리케이션에 필요한 톨 기반 액세스 제어(RBAC)를 추가합니다. 또한 `CreateSecurityGroups.ps1` 스크립트로 생성된 보안 그룹에 대한 CustomerInsights 컨테이너의 액세스 제어 목록(ACL)을 업데이트합니다. Contributor 그룹에는 *rwx* 권한이 있고 Reader 그룹에는 *r-x* 권한만 있습니다.
        - Azure Data Lake Storage, 스토리지 계정 이름, 리소스 그룹 이름, Reader 및 Contributor 보안 그룹 ID 값이 포함된 Azure 구독 ID를 제공하여 Windows PowerShell에서 이 PowerShell 스크립트를 실행합니다. 추가 정보와 구현된 논리를 검토하려면 편집기에서 PowerShell 스크립트를 엽니다.
        - 스크립트를 성공적으로 실행한 후 출력 문자열을 복사합니다. 출력 문자열은 다음과 같습니다. `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. 위에서 복사한 출력 문자열을 Microsoft Dataverse 환경 구성 단계의 **권한 식별자** 필드에 입력합니다.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Microsoft Dataverse를 사용하여 자체 Azure Data Lake Storage에서 데이터를 공유할 수 있도록 하는 구성 옵션.":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Dataverse 환경에 대한 기존 연결 제거

Dataverse 환경에 연결할 때 오류 메시지 **이 CDS 조직은 이미 다른 Customer Insights 인스턴스에 연결되어 있습니다** 는 Dataverse 환경이 이미 Customer Insights 환경에서 사용되고 있음을 의미합니다. Dataverse 환경에서 전역 관리자로 기존 연결을 제거할 수 있습니다. 변경 사항을 채우는 데 몇 시간이 걸릴 수 있습니다.

1. [Power Apps](https://make.powerapps.com)로 이동합니다.
1. 환경 선택기에서 환경을 선택합니다.
1. **솔루션** 으로 이동
1. **Dynamics 365 Customer Insights 고객 카드 추가 기능(프리뷰)** 이라는 솔루션을 제거하거나 삭제합니다.

OR

1. Dataverse 환경을 엽니다.
1. **고급 설정** > **솔루션** 으로 이동합니다.
1. **CustomerInsightsCustomerCard** 솔루션을 제거합니다.

종속성으로 인해 연결 제거가 실패하면 종속성도 제거해야 합니다. 자세한 내용은 [종속성 제거](/power-platform/alm/removing-dependencies)를 참조하십시오.

## <a name="output-entities"></a>출력 엔터티

Customer Insights의 일부 출력 엔터티는 Dataverse의 테이블로 사용할 수 있습니다. 아래 섹션에서는 이러한 테이블의 예상 스키마를 설명합니다.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [보강](#enrichment)
- [예측](#prediction)
- [세그먼트 구성원 자격](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

이 테이블에는 Customer Insights의 통합 고객 프로필이 포함되어 있습니다. 통합 고객 프로필의 스키마는 데이터 통합 프로세스에 사용된 엔터티 및 특성에 따라 다릅니다. 고객 프로필 스키마에는 일반적으로 [CustomerProfile에 대한 Common Data Model 정의](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) 특성의 하위 집합이 포함됩니다.

### <a name="alternatekey"></a>AlternateKey

AlternateKey 테이블에는 통합 프로세스에 참여한 엔터티의 키가 포함됩니다.

|Column  |종류  |설명  |
|---------|---------|---------|
|DataSourceName    |String         | 데이터 원본의 이름입니다. 예: `datasource5`        |
|EntityName        | String        | Customer Insights의 엔터티 이름입니다. 예: `contact1`        |
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

### <a name="segment-membership"></a>세그먼트 구성원 자격

이 테이블에는 고객 프로필의 세그먼트 구성원 자격 정보가 포함되어 있습니다.

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| 고객 ID        | String       | 고객 프로필 ID        |
| SegmentProvider      | String       | 세그먼트를 게시하는 앱입니다.      |
| SegmentMembershipType | String       | 이 세그먼트 구성원 자격 레코드의 고객 유형입니다. 고객, 연락처 또는 계정과 같은 여러 유형을 지원합니다. 기본: 고객  |
| 세그먼트       | JSON 문자열  | 고객 프로필이 속한 고유 세그먼트 목록      |
| msdynci_identifier  | String   | 세그먼트 구성원 자격 레코드의 고유 식별자입니다. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | `msdynci_identifier`에서 생성된 결정적 GUID          |

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
