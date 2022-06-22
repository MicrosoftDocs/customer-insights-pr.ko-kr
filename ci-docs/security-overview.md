---
title: Customer Insights의 보안 설정
description: Dynamics 365 Customer Insights의 보안 설정에 대해 알아봅니다.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947423"
---
# <a name="security-settings-in-customer-insights"></a>Customer Insights의 보안 설정

**보안** 페이지에는 Dynamics 365 Customer Insights를 보다 안전하게 만드는 데 도움이 되는 사용자 권한 및 기능을 구성하는 옵션이 나열되어 있습니다. 관리자만 이 페이지에 액세스할 수 있습니다.

**관리자** > **보안** 으로 이동하여 설정을 구성합니다.

**보안** 페이지에는 다음 탭이 포함됩니다.

- [사용자](#users-tab)
- [API](#apis-tab)
- [프라이빗 링크](#private-links-tab)
- [Key Vault](#key-vault-tab)
- [고객 LockBox를 사용하여 고객 데이터에 안전하게 액세스(프리뷰)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>사용자 탭

Customer Insights에 대한 액세스는 관리자가 애플리케이션에 추가한 조직의 사용자로 제한됩니다. **사용자** 탭을 사용하여 사용자 액세스 및 권한을 관리할 수 있습니다. 자세한 내용은 [사용자 권한](permissions.md)을 참조하십시오.

## <a name="apis-tab"></a>API 탭

[Customer Insights API](apis.md)를 사용하는 환경의 데이터로 키를 보고 관리합니다.

**기본 재생성** 또는 **보조 재생성** 을 선택하여 새 기본 키와 보조 키를 생성할 수 있습니다. 

환경에 대한 API 액세스를 차단하려면 **비활성화** 를 선택합니다. API가 비활성화된 경우 **활성화** 를 선택하여 액세스 권한을 다시 부여할 수 있습니다.

## <a name="private-links-tab"></a>프라이빗 링크 탭

[Azure Private Link](/azure/private-link/private-link-overview)를 사용하면 Customer Insights가 가상 네트워크의 프라이빗 엔드포인트를 통해 Azure Data Lake Storage 계정에 연결할 수 있습니다. 공용 인터넷에 노출되지 않는 저장소 계정의 데이터에 대해 Private Link를 사용하면 제한된 네트워크에 연결할 수 있습니다.

> [!IMPORTANT]
> Private Link 연결을 설정하기 위한 최소 역할 요구 사항:
>
> - Customer Insights: 관리자
> - Azure 기본 제공 역할: [스토리지 계정 기여자](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - 사용자 지정 Azure 역할에 대한 권한: [Microsoft.Storage/storageAccounts/read 및 Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

Customer Insights에서 Private Link를 설정하는 것은 2단계 프로세스입니다. 먼저 Customer Insights의 **관리** > **보안** > **프라이빗 링크** 에서 프라이빗 링크 생성을 시작합니다. **프라이빗 링크 추가** 창에는 볼 수 있는 권한이 있는 테넌트의 스토리지 계정이 나열됩니다. 스토리지 계정을 선택하고 프라이빗 링크를 만드는 데 동의합니다.

다음으로 Data Lake Storage 계정 측에서 프라이빗 링크를 승인해야 합니다. 새 프라이빗 링크를 승인하려면 화면에 표시된 링크를 엽니다.

## <a name="key-vault-tab"></a>Key Vault 탭

**Key Vault** 탭을 사용하면 자신의 [Azure Key Vault](/azure/key-vault/general/basic-concepts)를 환경에 연결하고 관리할 수 있습니다.
전용 키 자격 증명 모음을 사용하여 조직의 규정 준수 경계에서 비밀을 준비하고 사용할 수 있습니다. Customer Insights는 Azure Key Vault의 비밀을 사용하여 타사 시스템에 대한 [연결을 설정](connections.md)할 수 있습니다.

자세한 내용은[ 고유한 Azure 키 자격 증명 모음 가져오기](use-azure-key-vault.md).

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>고객 LockBox를 사용하여 고객 데이터에 안전하게 액세스(프리뷰)

Customer Insights는 Power Platform 고객 Lockbox 기능을 사용하고 있습니다. 고객 Lockbox는 데이터 액세스 요청을 검토 및 승인(또는 거부)하는 인터페이스를 제공합니다. 이러한 요청은 지원 사례를 해결하기 위해 고객 데이터에 대한 데이터 액세스가 필요할 때 발생합니다. 이 기능을 사용하려면 Customer Insights에 테넌트의 Microsoft Dataverse 환경에 대한 기존 연결이 있어야 합니다.

고객 Lockbox에 대한 자세한 내용은 Power Platform 고객 Lockbox [요약](/power-platform/admin/about-lockbox#summary)을 참조하세요. 또한 이 문서에서는 [워크플로](/power-platform/admin/about-lockbox#workflow)와 고객 Lockbox를 활성화하는 데 필요한 [설정](/power-platform/admin/about-lockbox#enable-the-lockbox-policy)에 대해 설명합니다.

> [!IMPORTANT]
> Power Platform 또는 Power Platform의 글로벌 관리자는 Customer Insights에 대해 발행된 고객 Lockbox 요청을 승인할 수 있습니다.

[!INCLUDE [footer-include](includes/footer-banner.md)]
