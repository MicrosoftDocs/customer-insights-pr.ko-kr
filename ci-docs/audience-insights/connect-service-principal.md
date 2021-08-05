---
title: 서비스 주체를 사용하여 Azure Data Lake Storage Gen2 계정에 연결
description: 대상 그룹 인사이트에 Azure 서비스 주체를 사용하여 대상 그룹 인사이트에 연결할 때 자체 데이터 레이크에 연결합니다.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: cc94ad49f12067d513db4663bff60620d6501eb0
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692121"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>대상 그룹 인사이트의 Azure 서비스 보안 주체를 사용하여 Azure Data Lake Storage Gen2 계정에 연결

Azure 서비스를 사용하는 자동화 도구에는 항상 제한된 권한이 있어야 합니다. 애플리케이션이 완전한 권한이 있는 사용자로 로그인하는 대신 Azure는 서비스 주체를 제공합니다. 스토리지 계정 키 대신 Azure 서비스 주체를 사용하여 Azure Data Lake Storage Gen2 계정과 대상 그룹 인사이트를 연결하는 방법을 알아보려면 계속 읽어보세요. 

서비스 주체를 사용하여 [Common Data Model 폴더를 데이터 원본으로 안전하게 추가 또는 편집](connect-common-data-model.md)하거나 [새 환경을 만들거나 기존 환경을 업데이트](get-started-paid.md)할 수 있습니다.

> [!IMPORTANT]
> - 서비스 주체를 사용하려는 Azure Data Lake Gen2 스토리지 계정에는 [계층적 네임 스페이스(HNS)가 활성화](/azure/storage/blobs/data-lake-storage-namespace)되어 있어야 합니다.
> - 서비스 주체를 만들려면 Azure 구독에 대한 관리자 권한이 필요합니다.

## <a name="create-azure-service-principal-for-audience-insights"></a>대상 그룹 인사이트에 대한 Azure 서비스 주체 만들기

대상 그룹 인사이트에 대한 새 서비스 주체를 만들기 전에 조직에 이미 존재하는지 확인하세요.

### <a name="look-for-an-existing-service-principal"></a>기존 서비스 주체 찾기

1. [Azure 관리 포털](https://portal.azure.com)로 이동하고 조직에 로그인합니다.

2. Azure 서비스에서 **Azure Active Directory** 를 선택합니다.

3. **관리** 에서 **엔터프라이즈 애플리케이션** 를 선택합니다.

4. 대상 그룹 인사이트 자사 애플리케이션 ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` 또는 이름 `Dynamics 365 AI for Customer Insights`를 검색합니다.

5. 일치하는 레코드를 찾으면 대상 그룹 인사이트에 대한 서비스 주체가 존재함을 의미합니다. 아무것도 만들 필요가 없습니다.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="기존 서비스 주체를 보여주는 스크린샷.":::
   
6. 결과가 반환되지 않으면 새 서비스 주체를 만듭니다.

### <a name="create-a-new-service-principal"></a>새 서비스 주체 만들기

1. 최신 버전의 **그래프용 Azure Active Directory PowerShell** 을 설치합니다. 자세한 내용은 [그래프용 Azure Active Directory PowerShell 설치](/powershell/azure/active-directory/install-adv2)를 참조하세요.
   - PC에서 키보드의 Windows 키를 선택하고 **Windows PowerShell** 과 **관리자 권한으로 실행** 를 검색합니다.
   
   - 열리는 PowerShell 창에 `Install-Module AzureAD`를 입력합니다.

2. Azure AD PowerShell 모듈을 사용하여 대상 그룹 인사이트에 대한 서비스 주체를 만듭니다.
   - PowerShell 창에 `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`를 입력합니다. "본인의 테넌트 ID"를 서비스 주체를 만들 테넌트의 실제 ID로 바꿉니다. 환경 이름 매개 변수 `AzureEnvironmentName`은 선택 사항입니다.
  
   - `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`를 입력합니다. 이 명령은 선택한 테넌트에 대한 대상 그룹 인사이트를 위한 서비스 주체를 만듭니다.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>서비스 주체에게 스토리지 계정에 액세스할 수 있는 권한 부여

Azure Portal로 이동하여 대상 그룹 인사이트에서 사용하려는 스토리지 계정의 서비스 주체에 권한을 부여합니다.

1. [Azure 관리 포털](https://portal.azure.com)로 이동하고 조직에 로그인합니다.

1. 대상 그룹 인사이트에 대한 서비스 주체가 액세스할 스토리지 계정을 엽니다.

1. 탐색 창에서 **액세스 제어(IAM)** 를 선택하고 **추가** > **역할 할당** 추가를 선택합니다.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="역할 할당을 추가하는 동안 Azure Portal을 보여주는 스크린샷.":::
   
1. **역할 할당 추가** 창에서 다음 속성을 설정합니다.
   - 역할: *Storage Blob 데이터 기여자*
   - 액세스 권한 할당: *사용자, 그룹 또는 서비스 주체*
   - 선택: *Dynamics 365 AI for Customer Insights*([사용자가 만든 서비스 주체](#create-a-new-service-principal))

1.  **저장** 을 선택합니다.

변경 사항을 전파하는 데 최대 15분이 소요될 수 있습니다.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>대상 그룹 인사이트에 대한 스토리지 계정 첨부 파일에 Azure 리소스 ID 또는 Azure 구독 세부 정보를 입력합니다.

대상 그룹 인사이트에 Azure Data Lake 스토리지 계정을 연결하여 [출력 데이터를 저장](manage-environments.md)하거나 [데이터 원본으로 사용](connect-dataverse-managed-lake.md)합니다. Azure Data Lake 옵션을 선택하면 리소스 기반 또는 구독 기반 접근 방식 중에서 선택할 수 있습니다.

선택한 접근 방식에 대한 필수 정보를 제공하려면 아래 단계를 따릅니다.

### <a name="resource-based-storage-account-connection"></a>리소스 기반 저장소 계정 연결

1. [Azure 관리 포털](https://portal.azure.com)로 이동하여 구독에 로그인하고 스토리지 계정을 엽니다.

1. 탐색 창에서 이동 **설정** > **속성** 으로 이동합니다.

1. 스토리지 계정 리소스 ID 값을 복사합니다.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="스토리지 계정 리소스 ID 값을 복사합니다.":::

1. 대상 그룹 인사이트에서 스토리지 계정 연결 화면에 표시된 리소스 필드에 리소스 ID를 삽입합니다.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="스토리지 계정 리소스 ID 정보를 입력합니다.":::   
   
1. 대상 그룹 인사이트의 나머지 단계를 계속하여 스토리지 계정을 연결합니다.

### <a name="subscription-based-storage-account-connection"></a>구독 기반 저장소 계정 연결

1. [Azure 관리 포털](https://portal.azure.com)로 이동하여 구독에 로그인하고 스토리지 계정을 엽니다.

1. 탐색 창에서 이동 **설정** > **속성** 으로 이동합니다.

1. **구독**, **리소스 그룹** 및 스토리지 계정의 **이름** 을 검토하여 대상 그룹 인사이트에서 올바른 값을 선택했는지 확인합니다.

1. 대상 그룹 인사이트에서 스토리지 계정을 연결할 때 값 또는 해당 필드를 선택합니다.
   
1. 대상 그룹 인사이트의 나머지 단계를 계속하여 스토리지 계정을 연결합니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]