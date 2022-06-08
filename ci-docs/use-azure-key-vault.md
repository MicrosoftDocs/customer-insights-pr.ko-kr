---
title: 고유한 Azure Key Vault를 가져와 비밀을 관리하세요.
description: 고유한 Azure Key Vault를 사용하도록 Customer Insights를 구성하는 방법을 알아보세요.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: d4f2d5ebc828053c40e22065f4915c4d0f84153f
ms.sourcegitcommit: 6ec4626a185892dfb781d3c7af4384f9c13f3723
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2022
ms.locfileid: "8763587"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>고유한 Azure Key Vault 가져오기(미리 보기)

전용 [Azure Key Vault](/azure/key-vault/general/basic-concepts)를 Customer Insights 환경에 연결하면 조직이 규정 준수 요구 사항을 충족하는 데 도움이 됩니다.
전용 키 자격 증명 모음을 사용하여 조직의 규정 준수 경계에서 비밀을 준비하고 사용할 수 있습니다. Customer Insights는 Azure Key Vault의 비밀을 사용하여 타사 시스템에 대한 [연결을 설정](connections.md)할 수 있습니다.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>키 자격 증명 모음을 Customer Insights 환경에 연결

### <a name="prerequisites"></a>전제 조건

Customer Insights에서 키 자격 증명 모음을 구성하려면 다음 필수 구성 요소가 충족되어야 합니다.

- 활성 Azure 구독이 있어야 합니다.

- Customer Insights의 [관리자](permissions.md#admin) 역할이 있습니다. [Customer Insights의 사용자 권한](permissions.md#assign-roles-and-permissions)에 대해 자세히 알아보세요.

- 키 자격 증명 모음 또는 키 자격 증명 모음이 속한 리소스 그룹에 대한 [기여자](/azure/role-based-access-control/built-in-roles#contributor) 및 [사용자 액세스 관리자](/azure/role-based-access-control/built-in-roles#user-access-administrator) 역할이 있습니다. 자세한 내용은 [Azure Portal을 사용하여 Azure 역할 할당 추가 또는 제거](/azure/role-based-access-control/role-assignments-portal)로 이동하세요. 키 자격 증명 모음에 대한 사용자 액세스 관리자 역할이 없는 경우 Dynamics 365 Customer Insights에 대한 Azure 서비스 주체에 대한 역할 기반 액세스 제어 권한을 별도로 설정해야 합니다. 연결해야 하는 키 자격 증명 모음에 대해 [Azure 서비스 주체](connect-service-principal.md)를 사용하는 단계를 따릅니다.

- 키 자격 증명 모음에는 Key Vault 방화벽이 **사용 중지** 되어 있어야 합니다.

- 키 자격 증명 모음은 Customer Insights 환경과 동일한 [Azure 위치](https://azure.microsoft.com/global-infrastructure/geographies/#overview)에 있습니다. Customer Insights의 환경 지역은 **관리자** > **시스템** > **정보** > **지역** 아래에 나열됩니다.

### <a name="link-a-key-vault-to-the-environment"></a>환경에 키 자격 증명 모음 연결

1. **관리자** > **보안** 으로 이동한 다음 **Key Vault** 탭을 선택합니다.
1. **Key Vault** 타일에서 **설정** 을 선택합니다.
1. **구독** 을 선택합니다.
1. **Key Vault** 드롭다운 목록에서 키 자격 증명 모음을 선택합니다. 너무 많은 키 자격 증명 모음이 표시되는 경우 리소스 그룹을 선택하여 검색 결과를 제한합니다.
1. **데이터 프라이버시 및 규정 준수** 선언문에 동의합니다.
1. **저장** 을 선택합니다.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Customer Insights에서 연결된 주요 자격 증명 모음을 설정하는 단계.":::

이제 **Key Vault** 타일에 연결된 키 자격 증명 모음 이름, 리소스 그룹 및 구독이 표시됩니다. 연결 설정에서 사용할 준비가 되었습니다.
Customer Insights에 부여되는 키 자격 증명 모음에 대한 자세한 내용은 이 문서 뒷부분의 [키 자격 증명 모음에 부여된 권한](#permissions-granted-on-the-key-vault)을 참조하세요.

## <a name="use-the-key-vault-in-the-connection-setup"></a>연결 설정에서 키 자격 증명 모음 사용

타사 시스템에 대한 [연결을 설정](connections.md)할 때 연결된 Key Vault의 비밀을 사용하여 연결을 구성할 수 있습니다.

1. **관리자** > **연결** 로 이동합니다.
1. **연결 추가** 를 선택합니다.
1. 지원되는 연결 유형의 경우 키 자격 증명 모음을 연결한 경우 **Key Vault 사용** 토글을 사용할 수 있습니다.
1. 비밀을 수동으로 입력하는 대신 키 자격 증명 모음의 비밀 값을 가리키는 비밀 이름을 선택할 수 있습니다.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Key Vault 비밀을 사용하는 SFTP 연결이 있는 연결 창.":::

## <a name="supported-connection-types"></a>지원되는 연결 유형

다음 [내보내기](export-destinations.md) 연결이 지원됩니다.

* [ActiveCampaign](export-active-campaign.md)
* [AutoPilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google 광고](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [SendGrid](export-sendgrid.md)
* [SendInBlue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault"></a>키 자격 증명 모음에 부여된 권한

[Key Vault 액세스 정책](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) 또는 [Azure 역할 기반 액세스 제어](/azure/key-vault/general/rbac-guide?tabs=azure-cli)가 사용된 경우 연결된 키 자격 증명 모음에 대한 Customer Insights에 다음 권한이 부여됩니다.

### <a name="key-vault-access-policy"></a>Key Vault 액세스 정책

| 종류        | 사용 권한          |
| ----------- | -------------------- |
| 열쇠         | [키 가져오기](/rest/api/keyvault/keys/get-keys/get-keys), [키 가져오기](/rest/api/keyvault/keys/get-key/get-key)                                 |
| 암호      | [비밀 가져오기](/rest/api/keyvault/secrets/get-secrets/get-secrets), [비밀 가져오기](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| 인증서 | [인증서 가져오기](/rest/api/keyvault/certificates/get-certificates/get-certificates), [인증서 가져오기](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

앞의 값은 실행 중에 나열하고 읽을 최소값입니다.

### <a name="azure-role-based-access-control"></a>Azure 역할 기반 액세스 제어

Key Vault Reader 및 Key Vault 비밀 사용자 역할이 Customer Insights에 추가됩니다. 이러한 역할에 대한 자세한 내용은 [Key Vault 데이터 평면 작업을 위한 Azure 기본 제공 역할](/azure/key-vault/general/rbac-guide?tabs=azure-cli)로 이동하세요.

## <a name="recommendations"></a>추천

- Customer Insights에 필요한 비밀만 포함하는 별도의 또는 전용 키 자격 증명 모음를 사용합니다. [별도의 키 자격 증명 모음이 권장](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults)되는 이유에 대해 자세히 알아보세요.

- 액세스, 백업, 감사 및 복구 옵션을 제어하기 위해 [Key Vault를 사용하는 모범 사례](/azure/key-vault/general/best-practices#turn-on-logging)를 따르세요.

## <a name="frequently-asked-questions"></a>자주 묻는 질문

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Customer Insights가 비밀을 쓰거나 키 자격 증명 모음에 비밀을 덮어쓸 수 있습니까?

번호 이 문서 앞부분의 [부여된 권한](#permissions-granted-on-the-key-vault) 섹션에 설명된 읽기 및 나열 권한만 Customer Insights에 부여됩니다. 시스템은 키 자격 증명 모음에서 비밀을 추가, 삭제 또는 덮어쓸 수 없습니다. 이는 연결에서 Key Vault를 사용할 때 자격 증명을 입력할 수 없는 이유이기도 합니다.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Key Vault 비밀 사용에서 기본 인증으로 연결을 변경할 수 있습니까?

번호 연결된 키 자격 증명 모음의 비밀을 사용하여 구성한 후에는 기본 연결로 다시 변경할 수 없습니다. 별도의 연결을 만들고 더 이상 필요하지 않은 경우 이전 연결을 삭제합니다.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Customer Insights에 대한 키 자격 증명 모음에 대한 액세스 권한을 취소하려면 어떻게 해야 하나요?

[Key Vault 액세스 정책](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) 또는 [Azure 역할 기반 액세스 제어](/azure/key-vault/general/rbac-guide?tabs=azure-cli)가 사용되는지 여부에 따라 이름이 `Dynamics 365 AI for Customer Insights`인 서비스 주체 `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff`에 대한 권한을 제거해야 합니다. Key Vault를 사용하는 모든 연결이 작동을 멈춥니다.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>연결에 사용되는 비밀이 키 자격 증명 모음에서 제거되었습니다. 무엇을 도와드릴까요?

Key Vault에서 구성된 비밀에 더 이상 액세스할 수 없는 경우 Customer Insights에 알림이 표시됩니다. 실수로 제거된 비밀을 복원하려면 키 자격 증명 모음에서 [일시 삭제](/azure/key-vault/general/soft-delete-overview)를 사용하도록 설정합니다.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>연결이 작동하지 않지만 내 비밀은 키 자격 증명 모음에 있습니다. 원인은 무엇입니까?

키 자격 증명 모음에 액세스할 수 없는 경우 Customer Insights에 알림이 표시됩니다. 원인은 다음과 같을 수 있습니다.

- Customer Insights 서비스 주체에 대한 권한이 제거되었습니다. 수동으로 복원해야 합니다.

- 키 자격 증명 모음의 방화벽이 사용됩니다. Customer Insights에 대해 키 자격 증명 모음에 다시 액세스할 수 있도록 하려면 방화벽을 사용하지 않도록 설정해야 합니다.
