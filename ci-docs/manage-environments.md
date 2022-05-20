---
title: 환경 만들기 및 관리
description: 서비스에 등록하는 방법과 환경을 관리하는 방법을 알아봅니다.
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 599cbaf4e19c3a7331e92bfc54c701fefe6c69b3
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741049"
---
# <a name="manage-environments"></a>환경 관리

## <a name="switch-environments"></a>환경 전환

페이지 오른쪽 상단의 **환경** 컨트롤을 선택하여 환경을 변경합니다.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="환경을 전환하는 컨트롤의 스크린샷.":::

관리자는 환경을 [생성](create-environment.md)하고 관리할 수 있습니다.

## <a name="edit-an-existing-environment"></a>기존 환경 편집

기존 환경의 세부 사항 중 일부를 편집할 수 있습니다.

1.  앱 헤더의 **환경** 선택기를 선택합니다.

2.  **편집** 아이콘을 선택합니다.

3. **환경 편집** 상자에서 환경 설정을 업데이트할 수 있습니다.

환경 설정에 대한 자세한 내용은 [새 환경 만들기](create-environment.md)를 참조하세요.

## <a name="connect-to-microsoft-dataverse"></a>Microsoft Dataverse에 연결할 수 없음
   
**Microsoft Dataverse** 단계를 통해 Customer Insights를 Dataverse 환경과 연결할 수 있습니다. 

Dynamics 365 Marketing 또는 Power Apps의 모델 기반 애플리케이션과 같은 Dataverse를 기반으로 하는 비즈니스 애플리케이션과 데이터(프로필 및 인사이트)를 공유할 수 있는 고유한 Microsoft Dataverse 환경을 제공합니다.

[기본 예측 모델](predictions-overview.md#out-of-box-models)을 사용하려면 Dataverse와 데이터 공유를 구성하세요. 또는 조직에서 관리하는 Microsoft Dataverse 환경 URL을 제공하여 온-프레미스 데이터 원본에서 데이터 수집을 활성화할 수 있습니다.

데이터 공유 확인란을 선택하여 Microsoft Dataverse과의 데이터 공유를 활성화하면 데이터 원본 및 기타 모든 프로세스의 전체 새로 고침이 한 번 트리거됩니다.

> [!IMPORTANT]
> 1. 데이터 공유를 활성화하려면 Customer Insights 및 Dataverse가 동일한 지역에 있어야 합니다.
> 1. Dataverse 환경에서 전역 관리자 역할이 있어야 합니다. 이 [Dataverse 환경이 연결되어](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) 있는지 확인하여 특정 보안 그룹에 추가하고 해당 보안 그룹에 추가되었는지 확인하십시오.
> 1. 기존 Customer Insights 환경은 해당 Dataverse 환경과 이미 연결되어 있지 않습니다. [Dataverse 환경에 대한 기존 연결 제거](#remove-an-existing-connection-to-a-dataverse-environment) 방법을 알아보세요.

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="Microsoft Dataverse와 데이터 공유를 활성화하는 구성 옵션":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>자체 Azure Data Lake Storage에서 Dataverse과 데이터 공유 활성화(프리뷰)

환경이 자체 Azure Data Lake Storage을 사용하여 Customer Insights 데이터를 저장하도록 구성된 경우 Microsoft Dataverse와 데이터 공유를 활성화하려면 몇 가지 추가 구성이 필요합니다.

1. Azure 구독에 두 개의 보안 그룹(**Reader** 보안 그룹 하나와 **Contributor** 보안 그룹 하나)을 만들고 Microsoft Dataverse 서비스를 두 보안 그룹의 소유자로 설정합니다.
2. 이러한 보안 그룹을 통해 스토리지 계정의 CustomerInsights 컨테이너에서 액세스 제어 목록(ACL)을 관리합니다. Microsoft Dataverse 서비스 및 Dynamics 365 Marketing과 같은 Dataverse 기반 비즈니스 애플리케이션을 **읽기 전용** 권한이 있는 **Reader** 보안 그룹에 추가합니다. Customers Insights 애플리케이션 *만* **Contributor** 보안 그룹에 추가하여 프로필과 인사이트를 작성할 수 있는 **읽고 쓰기** 권한을 모두 부여합니다.
   
#### <a name="prerequisites"></a>전제 조건

PowerShell 스크립트를 실행하려면 다음 세 가지 모듈을 가져와야 합니다. 

1. 최신 버전의 [Graph용 Azure Active Directory PowerShell](/powershell/azure/active-directory/install-adv2)을 설치하십시오.
   1. PC에서 키보드의 Windows 키를 선택하고 **Windows PowerShell** 을 검색하고 **관리자 권한으로 실행** 을 선택합니다.
   1. 열리는 PowerShell 창에 `Install-Module AzureAD`를 입력합니다.
2. 3개의 모듈을 가져옵니다.
    1. PowerShell 창에서 `Install-Module -Name Az.Accounts`을 입력하고 단계를 따릅니다. 
    1. `Install-Module -Name Az.Resources` 및 `Install-Module -Name Az.Storage`에 대해 반복합니다.

#### <a name="configuration-steps"></a>구성 단계

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
        - 스크립트를 성공적으로 실행한 후 출력 문자열을 복사합니다. 출력 문자열은 다음과 같습니다. `https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. 위에서 복사한 출력 문자열을 Microsoft Dataverse 환경 구성 단계의 **권한 식별자** 필드에 입력합니다.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Microsoft Dataverse를 사용하여 자체 Azure Data Lake Storage에서 데이터를 공유할 수 있도록 하는 구성 옵션.":::

Customer Insights는 다음 데이터 공유 시나리오를 지원하지 않습니다.
- Dataverse와 데이터 공유를 사용 설정하면 [엔터티에서 예측되거나 누락된 값 만들기](predictions.md)가 가능하지 않습니다.
- Dataverse와 데이터 공유를 활성화하면 Customer Insights 환경에서 선택적 PowerBI 내장형 보고서를 볼 수 없습니다.

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

## <a name="copy-the-environment-configuration"></a>환경 구성 복사

관리자는 새 환경을 만들 때 기존 환경에서 구성을 복사하도록 선택할 수 있습니다. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="환경 설정의 설정 옵션 스크린샷.":::

조직에서 데이터를 복사할 수 있는 사용 가능한 모든 환경 목록이 표시됩니다.

다음 구성 설정이 복사됩니다.

- 수집한/가져온 데이터 원본
- 데이터 통합 구성
- 세그먼트
- 측정값
- 관계
- 작업
- 검색 및 필터 인덱스
- 내보내기 대상
- 예약된 새로 고침
- 보강
- 모델 관리
- 역할 할당

## <a name="set-up-a-copied-environment"></a>복사한 환경 설정

환경 구성을 복사할 때 다음 데이터는 복사되지 *않습니다*.

- 고객 프로필.
- 데이터 원본 자격 증명. 모든 데이터 원본에 대한 자격 증명을 제공하고 데이터 원본을 수동으로 새로 고쳐야 합니다.
- Common Data Model 폴더 및 Dataverse 관리형 Data Lake의 데이터 원본. 원본 환경에서와 동일한 이름으로 해당 데이터 원본을 수동으로 생성해야 합니다.
- 내보내기 및 보강에 사용되는 연결 암호입니다. 연결을 다시 인증한 다음 보강 및 내보내기를 다시 활성화해야 합니다. 

환경을 복사하면 새 환경이 생성되었다는 확인 메시지가 표시됩니다. **데이터 원본으로 이동** 을 선택하여 데이터 원본 목록을 볼 수 있습니다.

모든 데이터 원본에 **자격 증명 필요** 상태가 표시됩니다. 데이터 원본을 편집하고 자격 증명 정보를 입력하여 새로 고치십시오.

:::image type="content" source="media/data-sources-copied.png" alt-text="복사되어 인증이 필요한 데이터 소스 목록.":::

데이터 원본을 새로 고친 후 **데이터** > **통합** 으로 이동합니다. 원본 환경에서 설정을 확인할 수 있습니다. 필요에 따라 편집하거나 **실행** 을 선택하여 데이터 통합 프로세스를 시작하고 통합 고객 엔터티를 만듭니다.

데이터 통합이 완료되면 **측정** 및 **세그먼트** 로 이동하여 이들도 새로 고칩니다.

내보내기 및 보강을 다시 활성화하기 전에 **관리자** > **연결** 로 이동하여 새 환경에서 연결을 다시 인증하십시오.

## <a name="change-the-owner-of-an-environment"></a>환경 담당자 변경

여러 사용자가 Customer Insights에서 관리자 권한을 가질 수 있지만 한 명의 사용자만 환경 담당자입니다. 기본적으로 처음에 환경을 만드는 사람이 관리자입니다. 환경의 관리자는 관리자 권한이 있는 다른 사용자에게 소유권을 할당할 수 있습니다.

1. 앱 헤더의 **환경** 선택기를 선택합니다.

1. **편집** 아이콘을 선택합니다.

1. **환경 편집** 상자에서 **기본 정보** 단계로 이동합니다.

1. **환경 담당자 변경** 필드에서 환경의 새 담당자를 선택합니다.  

1. **검토 및 완료** 를 선택한 다음 **업데이트** 를 선택하여 변경 사항을 적용합니다. 

## <a name="claim-ownership-of-an-environment"></a>환경 소유권 주장

환경 담당자가 조직을 떠나거나 해당 사용자 계정이 삭제되면 환경에는 담당자가 없게 됩니다. 관리자 권한이 있는 사용자는 소유권을 주장하고 새 담당자가 될 수 있습니다. 해당 사용자는 계속해서 환경을 소유하거나 [소유권을 다른 관리자에게로 변경할 수 있습니다](#change-the-owner-of-an-environment). 

소유권을 주장하려면 원래 담당자가 조직을 떠날 때 Customer Insights의 모든 페이지 상단에 표시되는 **소유권 확보** 단추를 선택합니다.

## <a name="reset-an-existing-environment"></a>기존 환경 초기화

환경 담당자는 모든 구성을 삭제하고 수집된 데이터를 제거하려는 경우 환경을 빈 상태로 재설정할 수 있습니다.

1.  앱 헤더의 **환경** 선택기를 선택합니다. 

2.  재설정하려는 환경을 선택하고 줄임표(**...**)를 선택합니다. 

3. **재설정** 옵션을 선택합니다. 

4.  삭제를 확인하려면 환경 이름을 입력하고 **초기화** 를 선택합니다.

## <a name="delete-an-existing-environment"></a>기존 환경 삭제

환경 담당자는 관리하는 환경을 삭제할 수 있습니다.

1.  앱 헤더의 **환경** 선택기를 선택합니다.

2.  재설정하려는 환경을 선택하고 줄임표(**...**)를 선택합니다. 

3. **삭제** 옵션을 선택합니다. 

4.  삭제를 확인하려면 환경 이름을 입력하고 **삭제** 를 선택합니다.

> [!NOTE]
> 환경을 삭제해도 Dataverse 환경에 대한 연결은 제거되지 않습니다. [Dataverse 환경에 대한 기존 연결 제거](#remove-an-existing-connection-to-a-dataverse-environment) 방법을 알아보십시오.


[!INCLUDE [footer-include](includes/footer-banner.md)]
