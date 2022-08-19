---
title: 보안 설정 구성
description: Dynamics 365 Customer Insights의 보안 설정에 대해 알아봅니다.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ea21163d7dd05370de28ca8340ae9583846adb26
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246070"
---
# <a name="configure-security-settings"></a>보안 설정 구성

API 키를 관리하고, 고객 데이터에 액세스하며, Azure 프라이빗 링크를 설정하세요.

## <a name="manage-api-keys"></a>API 키 관리

[Customer Insights API](apis.md)를 사용하는 환경의 데이터로 키를 조회하고 관리합니다.

1. **시스템** > **보안** 으로 이동하여 **API** 탭을 선택합니다.

1. 환경에 대한 API 액세스 권한이 설정되지 않은 경우 **사용 설정** 을 선택합니다. 또는 환경에 대한 API 액세스를 차단하려면 **비활성화** 를 선택하고 확인합니다.

1. 기본 및 보조 API 키를 관리합니다.

   1. 기본 또는 보조 API 키를 표시하려면 **보기** 기호를 선택합니다.

   1. 기본 또는 보조 API 키를 복사하려면 **복사** 기호를 선택합니다.

   1. **기본 재생성** 또는 **보조 재생성** 을 선택하여 새 기본 키와 보조 API 키를 생성할 수 있습니다.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>고객 LockBox를 사용하여 고객 데이터에 안전하게 액세스(프리뷰)

Customer Insights에서는 Power Platform 고객 Lockbox 기능을 사용합니다. 고객 Lockbox는 데이터 액세스 요청을 검토 및 승인(또는 거부)하는 인터페이스를 제공합니다. 이러한 요청은 지원 사례를 해결하기 위해 고객 데이터에 대한 데이터 액세스가 필요할 때 발생합니다. 이 기능을 사용하려면 Customer Insights에 테넌트의 Microsoft Dataverse 환경에 대한 기존 연결이 있어야 합니다.

고객 Lockbox에 대한 자세한 내용은 Power Platform 고객 Lockbox [요약](/power-platform/admin/about-lockbox#summary)을 참조하세요. 또한 이 문서에서는 [워크플로](/power-platform/admin/about-lockbox#workflow)와 고객 Lockbox를 활성화하는 데 필요한 [설정](/power-platform/admin/about-lockbox#enable-the-lockbox-policy)에 대해 설명합니다.

> [!IMPORTANT]
> Power Platform 또는 Power Platform의 글로벌 관리자는 Customer Insights에 대해 발행된 고객 Lockbox 요청을 승인할 수 있습니다.

## <a name="set-up-an-azure-private-link"></a>Azure 프라이빗 링크 설정

[Azure Private Link](/azure/private-link/private-link-overview)를 사용하면 Customer Insights가 가상 네트워크의 프라이빗 엔드포인트를 통해 Azure Data Lake Storage 계정에 연결할 수 있습니다. 공용 인터넷에 노출되지 않는 저장소 계정의 데이터에 대해 Private Link를 사용하면 제한된 네트워크에 연결할 수 있습니다.

> [!IMPORTANT]
> Private Link 연결을 설정하기 위한 최소 역할 요구 사항:
>
> - Customer Insights: 관리자
> - Azure 기본 제공 역할: [스토리지 계정 기여자](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - 사용자 지정 Azure 역할에 대한 권한: [Microsoft.Storage/storageAccounts/read 및 Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. Customer Insights에서 **관리자** > **보안** 으로 이동하여 **프라이빗 링크** 탭을 선택합니다.

1. **프라이빗 링크 추가** 를 선택합니다.

   **프라이빗 링크 추가** 창에는 볼 수 있는 권한이 있는 테넌트의 스토리지 계정이 나열됩니다.

1. 구독, 리소스 그룹 및 스토리지 계정을 선택합니다.

1. [데이터 개인 정보 보호 및 규정 준수](connections.md#data-privacy-and-compliance)를 검토하고 **동의함** 을 선택합니다.

1. **저장** 을 선택합니다.

1. Data Lake Storage 계정으로 이동하여 화면에 나타나는 링크를 엽니다.

1. 프라이빗 링크를 승인합니다.


[!INCLUDE [footer-include](includes/footer-banner.md)]
