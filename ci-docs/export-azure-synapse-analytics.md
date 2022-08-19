---
title: Azure Synapse Analytics로 데이터 내보내기(프리뷰)
description: Azure Synapse Analytics에 대한 연결을 구성하는 방법을 알아보세요.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 0e953cfff12df433d033717d58b28c2834468916
ms.sourcegitcommit: 086f75136132d561cd78a4c2cb1e1933e2301f32
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/11/2022
ms.locfileid: "9259852"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Azure Synapse Analytics로 데이터 내보내기(프리뷰)

Azure Synapse은 데이터 웨어하우스 및 빅 데이터 시스템 전체에서 인사이트를 얻는 시간을 가속화하는 분석 서비스입니다. [Azure Synapse](/azure/synapse-analytics/overview-what-is)에서 Customer Insights 데이터를 수집하고 사용할 수 있습니다.

## <a name="prerequisites"></a>전제 조건

> [!NOTE]
> 설명된 대로 모든 **역할 할당** 을 설정해야 합니다.

- Customer Insights의 Azure Active Directory(AD) 사용자 계정은 [관리자 역할](permissions.md#add-users) 권한이 있어야 합니다.

Azure에서:

- 활성 Azure 구독.

- 새 Azure Data Lake Storage Gen2 계정을 사용하는 경우 [Customer Insights의 서비스 주체](connect-service-principal.md)에는 **Storage Blob 데이터 기여자** 권한이 있어야 합니다. Data Lake Storage Gen2에는 [계층적 네임스페이스](/azure/storage/blobs/data-lake-storage-namespace)가 활성화되어 **있어야** 합니다.

- Azure Synapse workspace가 있는 리소스 그룹에서 *서비스 주체* 및 *Customer Insights에서 관리자 권한이 있는 Azure AD 사용자* 에 **Reader** 이상의 [권한](/azure/role-based-access-control/role-assignments-portal)을 할당해야 합니다.

- *Customer Insights에서 관리자 권한이 있는 Azure AD 사용자* 에게는 데이터가 있고 Azure Synapse workspace에 연결된 Azure Data Lake Storage Gen2 계정에 대한 **Storage Blob 데이터 기여자** 권한이 있어야 합니다. [Azure Portal을 사용하여 Blob 및 큐 데이터에 대한 액세스를 위한 Azure 역할 할당](/azure/storage/common/storage-auth-aad-rbac-portal) 및 [스토리지 Blob 데이터 기여자 권한](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)에 대해 자세히 알아봅니다.

- *[Azure Synapse workspace 관리 ID](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* 에는 데이터가 있고 Azure Synapse workspace에 연결된 Azure Data Lake Storage Gen2 계정에 대한 **Storage Blob 데이터 기여자** 권한이 있어야 합니다. [Azure Portal을 사용하여 Blob 및 큐 데이터에 대한 액세스를 위한 Azure 역할 할당](/azure/storage/common/storage-auth-aad-rbac-portal) 및 [스토리지 Blob 데이터 기여자 권한](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)에 대해 자세히 알아보기.

- Azure Synapse workspace에서 *Customer Insights의 서비스 주체* 에는 **시냅스 관리자** [역할이 할당](/azure/synapse-analytics/security/how-to-set-up-access-control)되어야 합니다.

- Customer Insights 환경에서 데이터를 [자체 Azure Data Lake Storage](own-data-lake-storage.md)에 저장하는 경우 연결을 Azure Synapse Analytics에 설정하는 사용자에게는 Data Lake Storage 계정에서 기본 **독자** 이상의 역할이 필요합니다. 자세한 내용은 [Azure Portal을 사용하여 Azure 역할 할당](/azure/role-based-access-control/role-assignments-portal)을 참조하십시오.

## <a name="set-up-connection-to-azure-synapse"></a>Azure Synapse에 대한 연결 설정

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 를 선택하고 **Azure Synapse Analytics** 를 선택합니다.

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 이 연결을 사용할 수 있는 사용자를 선택합니다. 기본적으로 관리자만 해당합니다. 자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.

1. Customer Insights 데이터를 사용할 구독을 선택하거나 검색합니다. 구독을 선택하자마자 **작업 영역**, **스토리지 계정** 및 **컨테이너** 를 선택할 수도 있습니다.

1. [데이터 개인 정보 보호 및 규정 준수](connections.md#data-privacy-and-compliance)를 검토하고 **동의함** 을 선택합니다.

1. 연결을 완료하려면 **저장** 을 선택합니다.

## <a name="configure-an-export"></a>내보내기 구성

[!INCLUDE [export-permission-include](includes/export-permission.md)] 공유된 연결로 내보내기를 구성하려면 Customer Insights에서 **기여자** 이상의 권한이 있어야 합니다.

1. **데이터** > **내보내기** 로 이동합니다.

1. **내보내기 추가** 를 선택합니다.

1. **내보내기 연결** 필드의 Azure Synapse Analytics 섹션에서 연결을 선택합니다. 사용 가능한 연결이 없으면 관리자에게 문의하십시오.

1. 내보내기에 대해 알아볼 수 있는 **표시 이름** 과 **데이터베이스 이름** 을 제공합니다. 내보내기는 연결에 정의된 작업 영역에 새 [Azure Synapse 레이크 데이터베이스](/azure/synapse-analytics/database-designer/concepts-lake-database)를 생성합니다.

1. Azure Synapse Analytics에 내보낼 엔터티를 선택합니다.
   > [!NOTE]
   > [Common Data Model 폴더](connect-common-data-model.md) 기반의 데이터 원본은 지원하지 않습니다.

1. **저장** 을 선택합니다.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Synapse Analytics로 내보낸 데이터를 쿼리하려면 내보내기 작업 공간에 있는 해당 저장소에 대한 **Storage Blob Data Reader** 액세스 권한이 있어야 합니다.

## <a name="update-an-export"></a>내보내기 업데이트

1. **데이터** > **내보내기** 로 이동합니다.

1. 업데이트하려는 내보내기에 대한 **편집** 을 선택합니다.

   - 선택 항목에서 엔터티를 **추가** 또는 **제거** 합니다. 선택 항목에서 엔터티가 제거되면 Synapse 분석 데이터베이스에서 삭제되지 않습니다. 그러나 향후 데이터 새로 고침은 해당 데이터베이스에서 제거된 항목을 업데이트하지 않습니다.

   - **데이터베이스 이름 변경** 은 새로운 Synapse 분석 데이터베이스를 생성합니다. 이전에 구성된 이름의 데이터베이스는 향후 새로 고침에서 업데이트를 수신하지 않습니다.

[!INCLUDE [footer-include](includes/footer-banner.md)]
