---
title: Azure Synapse 데이터 원본 연결(프리뷰)
description: Azure Synapse의 데이터베이스를 Dynamics 365 Customer Insights의 데이터 원본으로 사용합니다.
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 675fd03c44a7a7a492b111895d79c2e77f93a5b5
ms.sourcegitcommit: 4ba74816ebfa46412c64c40a61e1f31c4ccc40f2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9738164"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Azure Synapse Analytics 데이터 원본 연결(프리뷰)

Azure Synapse Analytics는 데이터 웨어하우스 및 빅 데이터 시스템 전반에 걸쳐 인사이트를 확보하는 시간을 단축하는 엔터프라이즈 분석 서비스입니다. Azure Synapse Analytics는 엔터프라이즈 데이터 웨어하우징에 사용되는 최고의 SQL 기술, 빅 데이터에 사용되는 Spark 기술, 로그 및 시계열 분석을 위한 Data Explorer, 데이터 통합 및 ETL/ELT 및 Power BI, Cosmos DB, AzureML과 같은 다른 Azure 서비스와의 긴밀한 통합을 위한 파이프라인을 결합합니다.

자세한 내용은 [Azure Synapse 개요](/azure/synapse-analytics/overview-what-is)를 참조하십시오.

## <a name="prerequisites"></a>전제 조건

> [!NOTE]
> [방화벽이 사용 설정된](/azure/synapse-analytics/security/synapse-workspace-ip-firewall) Synapse Workspace가 현재 지원되지 않습니다.
> [!IMPORTANT]
> 설명된 대로 모든 **역할 할당** 을 설정해야 합니다.  

**Customer Insights에서**:

* Customer Insights의 **관리자** 역할이 있습니다. [Customer Insights의 사용자 권한](permissions.md#add-users)에 대해 자세히 알아보세요.

**Azure에서**:

- 활성 Azure 구독.

- 새 Azure Data Lake Storage Gen2 계정을 사용하는 경우 'Dynamics 365 AI for Customer Insights'에 해당하는 *Customer Insights의 서비스 주체* 에게 **스토리지 Blob 데이터 기여자** 권한이 있어야 합니다. [Customer Insights를 위해 서비스 주체를 사용하여 Azure Data Lake Storage에 연결하는 방법](connect-service-principal.md)에 대해 자세히 알아보세요. Data Lake Storage Gen2에는 [계층적 네임스페이스](/azure/storage/blobs/data-lake-storage-namespace)가 활성화되어 **있어야** 합니다.

- Azure Synapse workspace가 있는 리소스 그룹에서 'Dynamics 365 AI for Customer Insights'에 해당하는 *서비스 주체* 및 *Customer Insights의 사용자* 에게 적어도 **독자** 권한 이상이 할당되어야 합니다. 자세한 내용은 [Azure Portal을 사용하여 Azure 역할 할당](/azure/role-based-access-control/role-assignments-portal)을 참조하십시오.

- *사용자* 는 데이터가 있고 Azure Synapse 작업 영역에 연결된 Azure Data Lake Storage Gen2 계정에 대한 **스토리지 Blob 데이터 기여자** 권한이 필요합니다. [Azure Portal을 사용하여 Blob 및 큐 데이터에 대한 액세스를 위한 Azure 역할 할당](/azure/storage/common/storage-auth-aad-rbac-portal) 및 [스토리지 Blob 데이터 기여자 권한](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)에 대해 자세히 알아봅니다.

- *[Azure Synapse 작업 영역 관리 ID](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* 는 데이터가 있고 Azure Synapse 작업 영역에 연결된 Azure Data Lake Storage Gen2 계정에 대한 **스토리지 Blob 데이터 기여자** 권한이 필요합니다. [Azure Portal을 사용하여 Blob 및 큐 데이터에 대한 액세스를 위한 Azure 역할 할당](/azure/storage/common/storage-auth-aad-rbac-portal) 및 [스토리지 Blob 데이터 기여자 권한](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)에 대해 자세히 알아보기.

- Azure Synapse workspace에서 'Dynamics 365 AI for Customer Insights'에 해당하는 *Customer Insights의 서비스 주체* 에는 **시냅스 관리자** 역할이 할당되어야 합니다. **사용자** 는 작업 영역에 할당된 최소한 **시냅스 기여자** 역할이 필요합니다. 자세한 내용은 [Synapse 작업 영역에 대한 액세스 제어를 설정하는 방법](/azure/synapse-analytics/security/how-to-set-up-access-control)을 참조하십시오.

- Customer Insights 환경에서 데이터를 [자체 Azure Data Lake Storage](own-data-lake-storage.md)에 저장하는 경우 연결을 Azure Synapse Analytics에 설정하는 사용자에게는 Data Lake Storage 계정에서 기본 **독자** 이상의 역할이 필요합니다. 자세한 내용은 [Azure Portal을 사용하여 Azure 역할 할당](/azure/role-based-access-control/role-assignments-portal)을 참조하십시오.

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Azure Synapse Analytics의 데이터 레이크 데이터베이스에 연결

1. **데이터** > **데이터 원본** 으로 이동.

1. **데이터 원본 추가** 를 선택합니다.

1. **Azure Synapse Analytics(프리뷰)** 방법을 선택합니다.

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Synapse Analytics 데이터에 연결하는 대화 상자":::
  
1. 데이터 소스의 **이름** 과 **설명**(선택 사항)을 입력합니다.

1. Azure Synapse Analytics에 대한 [사용 가능한 연결](connections.md)을 선택하거나 [새 연결을 생성](export-azure-synapse-analytics.md#set-up-connection-to-azure-synapse)합니다.

1. 선택한 Azure Synapse Analytics 연결에 연결된 작업 영역에서 **데이터베이스** 를 선택하고 **다음** 을 선택합니다. 현재 *레이크 데이터베이스* 데이터베이스 유형만 지원합니다.

1. 연결된 데이터베이스에서 수집할 엔터티를 선택하고 **다음** 을 선택합니다.

1. 선택적으로 데이터 프로파일링을 허용할 데이터 엔터티를 선택합니다.

1. **저장** 을 선택하여 선택 사항을 적용하고 Azure Synapse Analytics의 레이크 데이터베이스 테이블에 연결된 새로 만든 데이터 원본의 데이터 수집을 시작합니다. **데이터 원본** 페이지가 열리고 **새로 고침 중** 상태의 새 데이터 원본이 표시됩니다.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

데이터를 로드하는 데 시간이 걸릴 수 있습니다. 새로 고침이 완료되면, 수집된 데이터를 [**엔터티**](entities.md) 페이지에서 검토할 수 있습니다.

[!INCLUDE [footer-include](includes/footer-banner.md)]
