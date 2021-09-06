---
title: 서비스 주체를 사용하여 Azure Data Lake Storage 계정에 연결
description: Azure 서비스 주체를 사용하여 자체 데이터 레이크에 연결합니다.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 845d1f55eb99f2adf9b437124addec4f6d016fec
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461156"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Azure 서비스 주체를 사용하여 Azure Data Lake Storage 계정에 연결
<!--note from editor: The Cloud Style Guide would have us just use "Azure Data Lake Storage" to mean the current version, unless the old version (Gen1) is mentioned. I've followed this guidance, even though it seems that our docs and Azure docs are all over the map on this.-->
Azure 서비스를 사용하는 자동화 도구에는 항상 제한된 권한이 있어야 합니다. 애플리케이션이 완전한 권한이 있는 사용자로 로그인하는 대신 Azure는 서비스 주체를 제공합니다. 스토리지 계정 키 대신 Azure 서비스 주체를 사용하여 Dynamics 365 Customer Insights을 Azure Data Lake Storage 계정에 연결하는 방법을 알아보려면 계속 읽으십시오. 

서비스 주체를 사용하여 [Common Data Model 폴더를 데이터 원본으로 추가 또는 편집](connect-common-data-model.md) 또는 [환경 생성 또는 업데이트](get-started-paid.md)를 안전하게 수행할 수 있습니다.<!--note from editor: Suggested. Or it could be ", or create a new environment or update an existing one". I think "new" is implied with "create". The comma is necessary.-->

> [!IMPORTANT]
> - 서비스 주체를 사용할 Data Lake Storage 계정에는<!--note from editor: Suggested. Or perhaps it could be "The Data Lake Storage account to which you want to give access to the service principal..."--> [계층적 네임스페이스가 활성화](/azure/storage/blobs/data-lake-storage-namespace)되어 있어야 합니다.
> - 서비스 주체를 만들려면 Azure 구독에 대한 관리자 권한이 필요합니다.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Customer Insights에 대한 Azure 서비스 주체 만들기

대상 그룹 인사이트 또는 참여 인사이트에 대한 새 서비스 주체를 만들기 전에 조직에 이미 있는지 확인하십시오.

### <a name="look-for-an-existing-service-principal"></a>기존 서비스 주체 찾기

1. [Azure 관리 포털](https://portal.azure.com)로 이동하고 조직에 로그인합니다.

2. **Azure 서비스** 에서 **Azure Active Directory** 를 선택합니다.

3. **관리** 에서 **엔터프라이즈 애플리케이션** 를 선택합니다.

4. Microsoft 검색<!--note from editor: Via Microsoft Writing Style Guide.--> 애플리케이션 ID:
   - 대상 그룹 인사이트: `Dynamics 365 AI for Customer Insights`라는 이름의 `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff`
   - 참여 인사이트: `Dynamics 365 AI for Customer Insights engagement insights`라는 이름의 `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd`

5. 일치하는 레코드를 찾으면 서비스 주체가 이미 존재한다는 의미입니다. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="기존 서비스 주체를 보여주는 스크린샷.":::
   
6. 결과가 반환되지 않으면 새 서비스 주체를 만듭니다.

>[!NOTE]
>Dynamics 365 Customer Insights의 모든 기능을 활용하려면 두 앱을 서비스 주체에 추가하는 것이 좋습니다.<!--note from editor: Using the note format is suggested, just so this doesn't get lost by being tucked up in the step.-->

### <a name="create-a-new-service-principal"></a>새 서비스 주체 만들기
<!--note from editor: Some general formatting notes: The MWSG wants bold for text the user enters (in addition to UI strings and the settings users select), but there's plenty of precedent for using code format for entering text in PowerShell so I didn't change that. Note that italic should be used for placeholders, but not much else.-->
1. 최신 버전의 Graph용 Azure Active Directory PowerShell을 설치하십시오. 자세한 내용은 [Graph용 Azure Active Directory PowerShell 설치](/powershell/azure/active-directory/install-adv2)를 참고하십시오.

   1. PC에서 키보드의 Windows 키를 선택하고 **Windows PowerShell** 을 검색하고 **관리자 권한으로 실행** 을 선택합니다.<!--note from editor: Or should this be something like "search for **Windows PowerShell** and, if asked, select **Run as administrator**."?-->
   
   1. 열리는 PowerShell 창에 `Install-Module AzureAD`를 입력합니다.

2. Azure AD PowerShell 모듈을 사용하여 Customer Insights에 대한 서비스 주체를 만듭니다.

   1. PowerShell 창에 `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`를 입력합니다. *"[테넌트 ID]"* 를<!--note from editor: Edit okay? Or should the quotation marks stay in the command line, in which case it would be "Replace *[your tenant ID]* --> 서비스 주체를 만들려는 테넌트의 실제 ID로 바꿉니다. 환경 이름 매개 변수 `AzureEnvironmentName`은 선택 사항입니다.
  
   1. `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`를 입력합니다. 이 명령은 선택한 테넌트에 대한 대상 그룹 인사이트를 위한 서비스 주체를 만듭니다. 

   1. `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`를 입력합니다. 이 명령은 선택한 테넌트에 대한 참여 인사이트를 위한<!--note from editor: Edit okay?--> 서비스 주체를 만듭니다.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>서비스 주체에게 스토리지 계정에 액세스할 수 있는 권한 부여

Azure Portal로 이동하여 대상 그룹 인사이트에서 사용하려는 스토리지 계정의 서비스 주체에 권한을 부여합니다.

1. [Azure 관리 포털](https://portal.azure.com)로 이동하고 조직에 로그인합니다.

1. 대상 그룹 인사이트에 대한 서비스 주체가 액세스할 스토리지 계정을 엽니다.

1. 왼쪽 창에서 **액세스 제어(IAM)** 를 선택한 다음 **추가** > **역할 할당 추가** 를 선택합니다.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="역할 할당을 추가하는 동안 Azure Portal을 보여 주는 스크린샷.":::

1. **역할 할당 추가** 창에서 다음 속성을 설정합니다.
   - 역할: **Storage Blob 데이터 기여자**
   - 액세스 권한 할당: **사용자, 그룹 또는 서비스 주체**
   - 선택: **Customer Insights용 Dynamics 365 AI** 및 **Customer Insights용 Dynamics 365 AI 참여 인사이트**(이 절차 이전에 생성한 두 개의 [서비스 주체](#create-a-new-service-principal))

1.  **저장** 을 선택합니다.

변경 사항을 전파하는 데 최대 15분이 소요될 수 있습니다.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>대상 그룹 인사이트에 대한 스토리지 계정 첨부 파일에 Azure 리소스 ID 또는 Azure 구독 세부 정보를 입력합니다.

가능:<!--note from editor: Edit suggested only if this section is optional.--> 대상 그룹 인사이트의 Data Lake Storage 계정을 [출력 데이터 저장](manage-environments.md) 또는 [데이터 원본으로 사용](connect-common-data-service-lake.md)에 연결할 수 있습니다. 이 옵션을 사용하면 리소스 기반 또는 구독 기반 접근 방식 중에서 선택할 수 있습니다. 선택한 접근 방식에 따라 다음 섹션 중 하나의 절차를 따르십시오.<!--note from editor: Suggested.-->

### <a name="resource-based-storage-account-connection"></a>리소스 기반 저장소 계정 연결

1. [Azure 관리자 포털](https://portal.azure.com)로 이동하여 구독에 로그인하고 스토리지 계정을 엽니다.

1. 왼쪽 창에서 **설정** > **속성** 으로 이동합니다.

1. 스토리지 계정 리소스 ID 값을 복사합니다.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="스토리지 계정 리소스 ID 값을 복사합니다.":::

1. 대상 그룹 인사이트에서 스토리지 계정 연결 화면에 표시되는 리소스 필드에 리소스 ID를 삽입합니다.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="스토리지 계정 리소스 ID 정보를 입력합니다.":::   

1. 대상 그룹 인사이트의 나머지 단계를 계속하여 스토리지 계정을 연결합니다.

### <a name="subscription-based-storage-account-connection"></a>구독 기반 저장소 계정 연결

1. [Azure 관리자 포털](https://portal.azure.com)로 이동하여 구독에 로그인하고 스토리지 계정을 엽니다.

1. 왼쪽 창에서 **설정** > **속성** 으로 이동합니다.

1. **구독**, **리소스 그룹** 및 스토리지 계정의 **이름** 을 검토하여 대상 그룹 인사이트에서 올바른 값을 선택했는지 확인합니다.

1. 대상 그룹 인사이트에서 스토리지 계정을 연결할 때 해당 필드의 값을 선택합니다.

1. 대상 그룹 인사이트의 나머지 단계를 계속하여 스토리지 계정을 연결합니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]