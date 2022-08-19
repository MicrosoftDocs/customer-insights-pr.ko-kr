---
title: 연결(프리뷰) 개요
description: Customer Insights에서 다른 서비스에 대한 연결.
ms.date: 08/04/2022
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 8580dc7d90c75f66f73efc15f8e38f5e10fbb8a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245519"
---
# <a name="connections-preview-overview"></a>연결(프리뷰) 개요

연결은 Customer Insights와의 데이터 공유를 가능하게 하는 핵심입니다. 각 연결은 특정 서비스와 데이터 공유를 설정합니다. 연결을 사용하여 [타사 보강을 구성](enrichment-hub.md)하고 [내보내기를 구성](export-destinations.md)합니다. 동일한 연결을 여러 번 사용할 수 있습니다. 예를 들어 Dynamics 365 Marketing에 대한 하나의 연결은 여러 내보내기에 대해 작동하고 하나의 Leadspace 연결은 여러 보강에 사용할 수 있습니다.

## <a name="export-connections"></a>내보내기 연결

관리자만 새 연결을 구성할 수 있지만 [기여자에게 액세스 권한을 부여](#allow-contributors-to-use-a-connection-for-exports)하여 기존 연결을 사용할 수 있습니다. 관리자는 데이터가 이동할 수 있는 위치를 제어하고 기여자는 필요에 맞는 페이로드와 빈도를 정의합니다.

## <a name="enrichment-connections"></a>보강 연결

관리자만 새 연결을 구성할 수 있지만 생성된 연결은 관리자와 기여자 모두가 상시 사용할 수 있습니다. 관리자는 자격 증명을 관리하고 데이터 전송에 동의합니다. 그런 다음 관리자와 기여자 모두가 연결을 보강하는 데 사용할 수 있습니다.

## <a name="add-a-new-connection"></a>새 연결 추가

### <a name="prerequisites"></a>전제 조건

- [관리자 권한](permissions.md)
- 동일 조직에서 기타 Microsoft 서비스(해당하는 경우)

1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 를 선택하고 생성하려는 연결 유형을 선택합니다. 아니면 **검색** 탭으로 이동하여 연결 타일에서 **설정** 을 선택합니다.

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 필수 세부 정보를 입력합니다. 정확한 필드는 연결하려는 서비스에 따라 다릅니다. 특정 연결 유형에 대한 세부 사항은 대상 서비스에 대한 문서에서 참조하세요.

1. [자체 Key Vault를 사용](use-azure-key-vault.md)하여 비밀을 저장하는 경우 **Key Vault 사용** 을 활성화하고 목록에서 비밀을 선택합니다.

1. 데이터 개인 정보 보호 및 규정 준수를 검토하고 **동의함** 을 선택합니다.

1. **저장** 을 선택하여 연결을 생성합니다.

### <a name="data-privacy-and-compliance"></a>데이터 프라이버시 및 규정 준수

제3자 또는 다른 Microsoft 제품에 데이터를 전송하기 위해 Dynamics 365 Customer Insights를 활성화 할 때 Dynamics 365 Customer Insights의 규정 준수 범위 이외의 개인 데이터 등 잠재적으로 민감한 데이터를 비롯한 데이터의 전송을 허용합니다. Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만, 보유하고 있는 제3자의 모든 개인 정보 보호 또는 보안 의무를 충족하는 데에 대한 책임은 귀하에게 있음을 알려드립니다. 자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.

Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 연결 상태를 언제든지 제거할 수 있습니다.

## <a name="allow-contributors-to-use-a-connection-for-exports"></a>기여자가 내보내기에 연결을 사용하도록 허용

내보내기 연결을 설정하거나 편집할 때 이 특정 연결을 사용하여 [내보내기](export-destinations.md)를 정의할 수 있는 사용자를 선택합니다. 기본적으로 관리자 역할을 가진 사용자는 연결을 사용할 수 있습니다. **이 연결을 사용할 수 있는 사람 선택** 설정을 변경하면 기여자 역할을 가진 사용자가 이 연결을 사용할 수 있습니다.

- 기여자는 연결을 보거나 편집할 수 없습니다. 내보내기를 생성할 때 표시 이름 및 해당 유형만 볼 수 있습니다.
- 연결을 공유하면 기여자가 연결을 사용할 수 있습니다. 기여자는 내보내기를 설정할 때 공유 연결을 볼 수 있습니다. 이 특정 연결을 사용하는 모든 내보내기를 관리할 수 있습니다.
- 기여자가 이미 정의한 내보내기를 유지하면서 이 설정을 변경할 수 있습니다.

## <a name="manage-existing-connections"></a>기존 연결 관리

1. **관리자** > **연결** 로 이동합니다.

1. **보강** 또는 **내보내기** 탭을 선택하여 보강 또는 내보내기 연결 목록, 연결 유형, 생성 시기 및 액세스 권한이 있는 사람을 조회합니다. 모든 열을 기준으로 연결 목록을 정렬할 수 있습니다.

1. 사용 가능한 작업을 보려면 연결을 선택합니다.

   - 연결을 **수정** 합니다.
   - 연결을 [**제거**](#remove-a-connection)합니다.

### <a name="remove-a-connection"></a>연결 제거

제거하려는 연결이 보강 또는 내보내기에 사용되는 경우 먼저 연결을 분리하거나 제거합니다. 제거 대화 상자는 관련 보강 또는 내보내기로 안내합니다.

> [!TIP]
> 비활성화한 보강 및 분리된 내보내기가 비활성화됩니다. [보강](enrichment-hub.md) 또는 [내보내기](export-destinations.md) 페이지에서 다른 연결을 추가하여 다시 활성화합니다.

1. **관리자** > **연결** 로 이동합니다.

1. **보강** 또는 **내보내기** 탭을 선택합니다.

1. 제거할 연결을 선택합니다.

1. 드롭다운 메뉴에서 **제거** 를 선택합니다. 확인 대화 상자가 나타납니다.

   1. 이 연결을 사용하는 보강 또는 내보내기가 있는 경우 단추를 선택하여 연결을 사용하는 항목을 확인하십시오.
      - **내보내기:** 내보내기 **제거** 또는 **연결 분리** 중에서 선택합니다. 연결을 끊으면 내보내기 구성이 유지되지만 다른 연결이 추가될 때까지 실행되지 않습니다.
      - **보강:** **삭제** 또는 보강 **비활성화** 중에서 선택합니다.
   1. 연결에 더 이상 종속성이 없으면 **관리자** > **연결** 로 돌아가 연결을 다시 제거하십시오.

1. **제거** 를 선택하여 삭제를 확인합니다.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>자체 Key Vault에서 관리하는 비밀을 통해 연결 설정

일부 연결에는 API 키 또는 비밀과 같은 암호가 필요합니다. 일부 연결은 자체 Key Vault에 저장된 비밀을 지원합니다. 지원되는 연결 및 [Customer Insights를 위해 자체 Key Vault](use-azure-key-vault.md)를 설정하는 방법에 대해 자세히 알아보세요.

[!INCLUDE [footer-include](includes/footer-banner.md)]
