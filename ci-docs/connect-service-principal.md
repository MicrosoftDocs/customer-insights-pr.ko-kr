---
title: Azure 서비스 주체를 사용하여 Azure Data Lake Storage 계정에 연결
description: Azure 서비스 주체를 사용하여 자체 데이터 레이크에 연결합니다.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 949caa73578dbe0a511726ec045c0fd5f4621de4
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081299"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Azure 서비스 주체를 사용하여 Azure Data Lake Storage 계정에 연결

이 문서에서는 스토리지 계정 키 대신 Azure 서비스 주체를 사용하여 Dynamics 365 Customer Insights와 Azure Data Lake Storage 스토리지 계정을 연결하는 방법에 대해 설명합니다.

Azure 서비스를 사용하는 자동화 도구에는 항상 제한된 권한이 있어야 합니다. 애플리케이션이 완전한 권한이 있는 사용자로 로그인하는 대신 Azure는 서비스 주체를 제공합니다. 서비스 주체를 사용하여 안전하게 [Common Data Model 폴더를 데이터 원본으로 추가 또는 편집](connect-common-data-model.md)하거나 [환경을 생성 또는 업데이트](create-environment.md)할 수 있습니다.

> [!IMPORTANT]
>
> - 서비스 주체를 사용할 Data Lake Storage 계정은 Gen2여야 하며 [계층 구조 네임스페이스가 활성화](/azure/storage/blobs/data-lake-storage-namespace)되어 있어야 합니다. Azure Data Lake Gen1 스토리지 계정은 지원되지 않습니다.
> - 서비스 주체를 만들려면 Azure 테넌트에 대한 관리자 권한이 필요합니다.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Customer Insights에 대한 Azure 서비스 주체 만들기

Customer Insights에 대한 새 서비스 주체를 만들기 전에 조직에 이미 있는지 확인하십시오.

### <a name="look-for-an-existing-service-principal"></a>기존 서비스 주체 찾기

1. [Azure 관리 포털](https://portal.azure.com)로 이동하고 조직에 로그인합니다.

2. **Azure 서비스** 에서 **Azure Active Directory** 를 선택합니다.

3. **관리** 에서 **Microsoft 애플리케이션** 을 선택합니다.

4. **응용 프로그램 ID 시작** `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff`에 대한 필터를 추가하거나 `Dynamics 365 AI for Customer Insights` 이름을 검색합니다.

5. 일치하는 레코드를 찾으면 서비스 주체가 이미 존재한다는 의미입니다.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="기존 서비스 주체를 보여주는 스크린샷.":::

6. 결과가 반환되지 않으면 [새 서비스 주체를 생성](#create-a-new-service-principal)할 수 있습니다. 대부분의 경우 이미 존재하며 서비스 주체에게 스토리지 계정에 액세스할 수 있는 권한만 부여하면 됩니다.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>서비스 주체에게 스토리지 계정에 액세스할 수 있는 권한 부여

Azure Portal로 이동하여 Customer Insights에서 사용하려는 스토리지 계정에 대한 권한을 서비스 주체에 부여합니다. 스토리지 계정 또는 컨테이너에 다음 역할 중 하나를 할당해야 합니다.

|자격 증명|요구 사항|
|----------|------------|
|현재 로그인한 사용자|**역할**: Storage Blob 데이터 판독기, Storage Blob 기여자 또는 Storage Blob 소유자입니다.<br>**수준**: 스토리지 계정 또는 컨테이너에 대한 권한을 부여할 수 있습니다.</br>|
|Customer Insights 서비스 주체 -<br>Azure Data Lake Storage를 데이터 원본으로 사용</br>|옵션 1<ul><li>**역할**: Storage Blob 데이터 판독기, Storage Blob 데이터 기여자 또는 Storage Blob 데이터 소유자입니다.</li><li>**수준**: 저장소 계정에 대한 권한을 부여해야 합니다.</li></ul>옵션 2 *(스토리지 계정에 대한 서비스 주체 액세스를 공유하지 않음)*<ul><li>**역할 1**: Storage Blob 데이터 판독기, Storage Blob 데이터 기여자 또는 Storage Blob 데이터 소유자입니다.</li><li>**수준**: 컨테이너에 대한 권한을 부여해야 합니다.</li><li>**역할 2**: Storage Blob 데이터 위임자입니다.</li><li>**수준**: 저장소 계정에 대한 권한을 부여해야 합니다.</li></ul>|
|Customer Insights 서비스 주체 - <br>Azure Data Lake Storage를 출력 또는 대상으로 사용</br>|옵션 1<ul><li>**역할**: Storage Blob 데이터 기여자 또는 Storage Blob 소유자입니다.</li><li>**수준**: 저장소 계정에 대한 권한을 부여해야 합니다.</li></ul>옵션 2 *(스토리지 계정에 대한 서비스 주체 액세스를 공유하지 않음)*<ul><li>**역할**: Storage Blob 데이터 기여자 또는 Storage Blob 소유자입니다.</li><li>**수준**: 컨테이너에 대한 권한을 부여해야 합니다.</li><li>**역할 2**: Storage Blob 위임자입니다.</li><li>**수준**: 저장소 계정에 대한 권한을 부여해야 합니다.</li></ul>|

1. [Azure 관리 포털](https://portal.azure.com)로 이동하고 조직에 로그인합니다.

1. Customer Insights의 서비스 주체가 액세스할 수 있는 스토리지 계정을 엽니다.

1. 왼쪽 창에서 **액세스 제어(IAM)** 를 선택한 다음 **추가** > **역할 할당 추가** 를 선택합니다.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="역할 할당을 추가하는 동안 Azure Portal을 보여 주는 스크린샷.":::

1. **역할 할당 추가** 창에서 다음 속성을 설정합니다.
   - 역할: 위에 나열된 자격 증명을 기반으로 하는 Storage Blob 데이터 판독기, Storage Blob 기여자 또는 Storage Blob 소유자입니다.
   - 액세스 권한 할당: **사용자, 그룹 또는 서비스 주체**
   - 구성원 선택: **Customer Insights용 Dynamics 365 AI**(이 절차의 앞부분에서 조회한 [서비스 주체](#create-a-new-service-principal))

1. **검토 + 할당** 을 선택합니다.

변경 사항을 전파하는 데 최대 15분이 소요될 수 있습니다.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Customer Insights에 대한 스토리지 계정 첨부 파일에 Azure 리소스 ID 또는 Azure 구독 세부 정보 입력

Customer Insights의 Data Lake Storage 계정을 [출력 데이터 저장](manage-environments.md) 또는 [데이터 원본으로 사용](connect-dataverse-managed-lake.md)에 연결할 수 있습니다. 이 옵션을 사용하면 리소스 기반 또는 구독 기반 접근 방식 중에서 선택할 수 있습니다. 선택한 접근 방식에 따라 다음 섹션 중 하나의 절차를 따르십시오.

### <a name="resource-based-storage-account-connection"></a>리소스 기반 저장소 계정 연결

1. [Azure 관리자 포털](https://portal.azure.com)로 이동하여 구독에 로그인하고 스토리지 계정을 엽니다.

1. 왼쪽 창에서 **설정** > **엔드포인트** 로 이동합니다.

1. 스토리지 계정 리소스 ID 값을 복사합니다.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="스토리지 계정 리소스 ID 값을 복사합니다.":::

1. Customer Insights에서 스토리지 계정 연결 화면에 표시되는 리소스 필드에 리소스 ID를 삽입합니다.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="스토리지 계정 리소스 ID 정보를 입력합니다.":::   

1. Customer Insights의 나머지 단계를 계속하여 스토리지 계정을 연결합니다.

### <a name="subscription-based-storage-account-connection"></a>구독 기반 저장소 계정 연결

1. [Azure 관리자 포털](https://portal.azure.com)로 이동하여 구독에 로그인하고 스토리지 계정을 엽니다.

1. 왼쪽 창에서 **설정** > **속성** 으로 이동합니다.

1. 스토리지 계정의 **구독**, **리소스 그룹** 및 **이름** 을 검토하여 Customer Insights에서 올바른 값을 선택했는지 확인합니다.

1. Customer Insights에서 스토리지 계정을 연결할 때 해당 필드의 값을 선택합니다.

1. Customer Insights의 나머지 단계를 계속하여 스토리지 계정을 연결합니다.

### <a name="create-a-new-service-principal"></a>새 서비스 주체 만들기

1. 최신 버전의 Graph용 Azure Active Directory PowerShell을 설치하십시오. 자세한 내용은 [Graph용 Azure Active Directory PowerShell 설치](/powershell/azure/active-directory/install-adv2)를 참고하십시오.

   1. PC에서 키보드의 Windows 키를 누르고 **Windows PowerShell** 을 검색하고 **관리자 권한으로 실행** 을 선택합니다.

   1. 열리는 PowerShell 창에 `Install-Module AzureAD`를 입력합니다.

2. Azure AD PowerShell 모듈을 사용하여 Customer Insights에 대한 서비스 주체를 만듭니다.

   1. PowerShell 창에 `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`를 입력합니다. *[내 디렉터리 ID]* 을 서비스 주체를 만들 Azure 구독의 실제 디렉터리 ID로 바꿉니다. 환경 이름 매개 변수 `AzureEnvironmentName`은 선택 사항입니다.
  
   1. `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`를 입력합니다. 이 명령은 선택한 Azure 구독에서 Customer Insights에 대한 서비스 주체를 만듭니다.

[!INCLUDE [footer-include](includes/footer-banner.md)]
