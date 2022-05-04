---
title: Customer Insights 데이터를 Azure Synapse Analytics로 내보내기
description: Azure Synapse Analytics에 대한 연결을 구성하는 방법을 알아보세요.
ms.date: 04/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e77227e1e353c02cfb13e26a8ecbe0768ba6c0fa
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646684"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Azure Synapse Analytics(프리뷰)로 데이터 내보내기

Azure Synapse은 데이터 웨어하우스 및 빅 데이터 시스템 전체에서 인사이트를 얻는 시간을 가속화하는 분석 서비스입니다. [Azure Synapse](/azure/synapse-analytics/overview-what-is)에서 Customer Insights 데이터를 수집하고 사용할 수 있습니다.

## <a name="prerequisites"></a>필수 조건

Customer Insights에서 Azure Synapse로의 연결을 구성하려면 다음 필수 조건을 충족해야 합니다.

> [!NOTE]
> 설명된 대로 모든 **역할 할당** 을 설정해야 합니다.  

## <a name="prerequisites-in-customer-insights"></a>Customer Insights의 필수 조건

* Azure Active Directory(AD) 사용자 계정에는 Customer Insights에 **관리자** 역할이 있습니다. [사용자 권한 설정](permissions.md#assign-roles-and-permissions)에 대해 자세히 알아보세요.

Azure에서: 

- 활성 Azure 구독.

- 새 Azure Data Lake Storage Gen2 계정을 사용하는 경우 *Customer Insights의 서비스 주체* 에는 **스토리지 Blob 데이터 Contributor** 권한이 필요합니다. [대상 그룹 인사이트에 대한 Azure 서비스 주체를 사용하여 Azure Data Lake Storage Gen2 계정에 연결](connect-service-principal.md)에 대해 자세히 알아봅니다. Data Lake Storage Gen2에는 [계층적 네임스페이스](/azure/storage/blobs/data-lake-storage-namespace)가 활성화되어 **있어야** 합니다.

- Azure Synapse workspace가 있는 리소스 그룹에서 *서비스 주체* 및 *Customer Insights에서 관리자 권한이 있는 Azure AD 사용자* 에 최소 **Reader** 권한을 할당해야 합니다. 자세한 내용은 [Azure Portal을 사용하여 Azure 역할 할당](/azure/role-based-access-control/role-assignments-portal)을 참조하십시오.

- *Customer Insights에서 관리자 권한이 있는 Azure AD 사용자* 는 데이터가 있고 Azure Synapse workspace에 연결된 Azure Data Lake Storage Gen2 계정에 대한 **스토리지 Blob 데이터 Contributor** 권한이 필요합니다. [Azure Portal을 사용하여 Blob 및 큐 데이터에 대한 액세스를 위한 Azure 역할 할당](/azure/storage/common/storage-auth-aad-rbac-portal) 및 [스토리지 Blob 데이터 기여자 권한](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)에 대해 자세히 알아봅니다.

- *[Azure Synapse 작업 영역 관리 ID](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* 는 데이터가 있고 Azure Synapse 작업 영역에 연결된 Azure Data Lake Storage Gen2 계정에 대한 **스토리지 Blob 데이터 기여자** 권한이 필요합니다. [Azure Portal을 사용하여 Blob 및 큐 데이터에 대한 액세스를 위한 Azure 역할 할당](/azure/storage/common/storage-auth-aad-rbac-portal) 및 [스토리지 Blob 데이터 기여자 권한](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor)에 대해 자세히 알아보기.

- Azure Synapse workspace에서 *Customer Insights의 서비스 주체* 에는 **시냅스 관리자** 역할이 할당되어야 합니다. 자세한 내용은 [Synapse 작업 영역에 대한 액세스 제어를 설정하는 방법](/azure/synapse-analytics/security/how-to-set-up-access-control)을 참조하십시오.

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>연결을 설정하고 Azure Synapse로 내보내기

### <a name="configure-a-connection"></a>연결 구성

연결을 만들려면 Customer Insights에 있는 서비스 주체와 사용자 계정에 Synapse Analytics 작업 영역이 있는 *리소스 그룹* 에 대한 **읽기** 권한이 필요합니다. 또한, 서비스 주체와 Synapse Analytics 작업 영역의 사용자는 **Synapse 관리자** 권한이 필요합니다. 

1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 를 선택하고 **Azure Synapse Analytics** 를 선택하거나 **Azure Synapse Analytics** 타일에서 **설정** 을 선택하여 연결을 구성합니다.

1. 표시 이름 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 이 연결을 사용할 수 있는 사용자를 선택합니다. 아무 조치도 취하지 않으면 기본값은 관리자입니다. 자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.

1. Customer Insights 데이터를 사용할 구독을 선택하거나 검색합니다. 구독을 선택하자마자 **작업 영역**, **스토리지 계정** 및 **컨테이너** 를 선택할 수도 있습니다.

1. **저장** 을 ​​선택하여 연결을 저장합니다.

### <a name="configure-an-export"></a>내보내기 구성

이 유형의 연결에 대한 액세스 권한이 있는 경우 이 내보내기를 구성할 수 있습니다. 공유된 연결로 내보내기를 구성하려면 Customer Insights에서 최소한 **기여자** 권한이 있어야 합니다. 자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하십시오.

1. **데이터** > **내보내기** 로 이동합니다.

1. **내보내기 추가** 를 선택하여 새 내보내기를 만듭니다.

1. **내보내기 연결** 필드의 **Azure Synapse Analytics** 섹션에서 연결을 선택합니다. 이 섹션 이름이 표시되지 않으면 사용 가능한 이 유형의 [연결](connections.md)이 없는 것입니다.

1. 내보내기에 대해 알아볼 수 있는 **표시 이름** 과 **데이터베이스 이름** 을 제공합니다.

1. Azure Synapse Analytics에 내보낼 엔터티를 선택합니다.
   > [!NOTE]
   > [Common Data Model 폴더](connect-common-data-model.md) 기반의 데이터 원본은 지원하지 않습니다.

2. **저장** 을 선택합니다.

내보내기를 저장해도 내보내기가 즉시 실행되지는 않습니다.

내보내기는 모든 [예약된 새로 고침](system.md#schedule-tab)에 따라 실행됩니다. [주문형으로 데이터를 내보낼](export-destinations.md#run-exports-on-demand)수도 있습니다.

Synapse Analytics로 내보낸 데이터를 쿼리하려면 내보내기 작업 공간에 있는 해당 저장소에 대한 **Storage Blob Data Reader** 액세스 권한이 있어야 합니다. 

### <a name="update-an-export"></a>내보내기 업데이트

1. **데이터** > **내보내기** 로 이동합니다.

1. 업데이트하려는 내보내기에 대한 **편집** 을 선택합니다.

   - 선택 항목에서 엔터티를 **추가** 또는 **제거** 합니다. 선택 항목에서 엔터티가 제거되면 Synapse 분석 데이터베이스에서 삭제되지 않습니다. 그러나 향후 데이터 새로 고침은 해당 데이터베이스에서 제거된 항목을 업데이트하지 않습니다.

   - **데이터베이스 이름 변경** 은 새로운 Synapse 분석 데이터베이스를 생성합니다. 이전에 구성된 이름의 데이터베이스는 향후 새로 고침에서 업데이트를 수신하지 않습니다.
