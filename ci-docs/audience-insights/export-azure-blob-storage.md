---
title: Azure Blob Storage로 Customer Insights 데이터 내보내기
description: 연결을 구성하고 Azure Blob Storage로 내보내는 방법을 알아봅니다.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5ea8e58822e1bb901552ff1de960d5340d340003
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231259"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>세그먼트 목록 및 기타 데이터를 Azure Blob Storage로 내보내기(프리뷰)

Blob Storage에 Customer Insights 데이터를 저장하거나 다른 애플리케이션으로 데이터를 전송하는 데 사용합니다.

## <a name="known-limitations"></a>알려진 제한 사항

1. Azure Blob Storage의 경우 [표준 성능과 프리미엄 성능 계층](/azure/storage/blobs/storage-blob-performance-tiers) 중에서 선택할 수 있습니다. 프리미엄 성능 계층을 선택하는 경우 [프리미엄 블록 Blob을 계정 유형으로](/azure/storage/common/storage-account-overview#types-of-storage-accounts) 선택합니다.

## <a name="set-up-the-connection-to-blob-storage"></a>Blob Storage에 대한 연결 설정

1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 와 **Azure Blob Storage** 를 선택하여 연결을 구성합니다.

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 이 연결을 사용할 수 있는 사용자를 선택합니다. 아무 조치도 취하지 않으면 기본값은 관리자입니다. 자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.

1. Blob Storage 계정의 **계정 이름**, **계정 키** 및 **컨테이너** 를 입력합니다.
    - Blob Storage 계정 이름 및 계정 키를 찾는 방법에 대한 자세한 내용은 [Azure Portal에서 스토리지 계정 설정 관리](/azure/storage/common/storage-account-manage)를 참조하세요.
    - 컨테이너를 만드는 방법을 배우려면 [컨테이너 만들기](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)를 참조하세요.

1. 연결을 완료하려면 **저장** 을 선택합니다. 

## <a name="configure-an-export"></a>내보내기 구성

이 유형의 연결에 대한 액세스 권한이 있는 경우 이 내보내기를 구성할 수 있습니다. 자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.

> [!IMPORTANT]
> Azure Blob Storage 계정에 대한 일시 삭제 설정을 켠 경우 내보내기가 실패합니다. 데이터를 Blob으로 내보내려면 일시 삭제를 끕니다. 자세한 내용은 [Blob 일시 삭제 사용](/azure/storage/blobs/soft-delete-blob-enable.md)을 참조하십시오

1. **데이터** > **내보내기** 로 이동합니다.

1. **대상 추가** 를 선택하여 새 내보내기를 만듭니다.

1. **내보내기 연결** 필드의 Azure Blob Storage 섹션에서 연결을 선택합니다. 이 섹션 이름이 표시되지 않으면 이 유형의 연결을 사용할 수 없습니다.

1. 이 대상으로 내보내려는 각 엔터티 옆의 상자를 선택하십시오.

1. **저장** 을 선택합니다.

내보내기를 저장해도 내보내기가 즉시 실행되지는 않습니다.

내보내기는 모든 [예약된 새로 고침](system.md#schedule-tab)에 따라 실행됩니다.     

[주문형으로 데이터를 내보낼](export-destinations.md#run-exports-on-demand)수도 있습니다. 

내보낸 데이터는 구성한 Blob Storage 컨테이너에 저장됩니다. 컨테이너에 다음 폴더 경로가 자동으로 생성됩니다.

- 원본 엔터티 및 시스템에서 생성된 엔터티의 경우:  
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - 예: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
 
- 내보낸 엔터티의 model.json은 %ExportDestinationName% 수준에 있습니다.  
  - 예: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE[footer-include](../includes/footer-banner.md)]
