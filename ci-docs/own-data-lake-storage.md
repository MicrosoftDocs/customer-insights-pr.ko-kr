---
title: 자신의 Azure Data Lake Storage Gen2 계정 사용
author: mukeshpo
description: 자신의 Azure Data Lake Storage 계정을 사용하여 Customer Insights 데이터를 저장하기 위한 요구 사항에 대해 알아봅니다.
ms.author: mukeshpo
ms.date: 08/15/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 5e4b9348f06d4e5e10b4499ad86b38c9d52da1f5
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304389"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>자신의 Azure Data Lake Storage Gen2 계정 사용

Dynamics 365 Customer Insights는 모든 데이터를 [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction)에 저장할 수 있는 옵션을 제공합니다. Data Lake Storage에 데이터를 저장하면 해당 Azure Storage 계정에 해당하는 지리적 위치로 데이터가 전송되고 저장된다는 데 동의하는 것입니다. 자세한 정보는 [Microsoft 보안 센터](https://www.microsoft.com/trust-center)를 참조하십시오.

Customer Insights의 관리자는 프로세스 중에 [환경 생성](create-environment.md) 및 [데이터 저장 옵션 지정](create-environment.md#step-2-configure-data-storage)을 수행할 수 있습니다.

## <a name="prerequisites"></a>전제 조건

- Azure Data Lake Storage 계정은 Customer Insights 환경을 만들 때 선택한 것과 동일한 Azure 지역에 있어야 합니다. 환경의 지역을 알아보려면 Customer Insights에서 **관리자** > **시스템** > **정보** 로 이동하세요.
- Data Lake Storage 계정은 Gen2여야 합니다. Azure Data Lake Gen1 스토리지 계정은 지원되지 않습니다.
- Azure Data Lake Storage 계정에는 [계층 구조 네임스페이스가 활성화](/azure/storage/blobs/data-lake-storage-namespace)되어 있어야 합니다.
- `customerinsights`이라는 컨테이너가 스토리지 계정에 있어야 합니다. Customer Insights에서 자체 Data Lake Storage를 사용하기 전에 생성하십시오.
- Customer Insights 환경을 설정하는 관리자는 스토리지 계정 또는 `customerinsights` 컨테이너에 대한 Storage Blob 데이터 기여자 또는 Storage Blob 데이터 소유자 역할이 필요합니다. 스토리지 계정에 권한을 할당하는 방법에 대한 자세한 내용은 [스토리지 계정 만들기](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal)를 참조하십시오.

## <a name="connect-customer-insights-with-your-storage-account"></a>스토리지 계정과 Customer Insights 연결

새 환경을 만들 때 Data Lake Storage 계정이 존재하고 모든 필수 구성 요소가 충족되는지 확인합니다.

1. 환경 생성 중 **데이터 스토리지** 단계에서 **출력 데이터 저장** 을 **Azure Data Lake Storage Gen2** 로 설정합니다.
1. **스토리지 연결** 방법을 선택합니다. 인증을 위해 리소스 기반 옵션과 구독 기반 옵션 중에서 선택할 수 있습니다. 자세한 내용은 [Azure 서비스 주체를 사용하여 Azure Data Lake Storage 계정에 연결](connect-service-principal.md)을 참조하십시오.
   - **Azure 구독** 의 경우 `customerinsights` 컨테이너가 포함된 **구독**, **리소스 그룹** 및 **스토리지 계정** 을 선택합니다.
   - **계정 키** 의 경우 Data Lake Storage 계정에 대해 **계정 이름** 및 **계정 키** 를 제공합니다. 이 인증 방법을 사용하면 조직에서 키를 교체할 경우 알림을 받게 됩니다. 회전할 때 새 키로 [환경 구성을 업데이트](manage-environments.md#edit-an-existing-environment)해야 합니다.
1. Azure Private Link를 사용하여 스토리지 계정에 연결하고 [Private Link에 대한 연결을 생성](security-overview.md#set-up-an-azure-private-link)할지 여부를 선택합니다.

데이터 수집과 같은 시스템 프로세스가 완료되면 시스템은 스토리지 계정에 해당 폴더를 만듭니다. 데이터 파일과 model.json 파일이 생성되어 프로세스 이름을 기반으로 폴더에 추가됩니다.

Customer Insights의 여러 환경을 만들고 해당 환경의 출력 엔터티를 스토리지 계정에 저장하도록 선택하면 Customer Insights는 컨테이너에 `ci_environmentID`가 있는 각 환경에 대해 별도의 폴더를 만듭니다.
