---
title: Azure Blob Storage로 Customer Insights 데이터 내보내기
description: Azure Blob Storage에 대한 연결을 구성하는 방법을 알아보십시오.
ms.date: 09/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0986ee5caf5fa079994ca584fb2c4d9294ddb80b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596185"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Azure Blob Storage용 커넥터(미리 보기)

Customer Insights 데이터를 Azure Blob Storage에 저장하거나 사용자의 데이터를 다른 애플리케이션으로 전송하는 데 사용합니다.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Azure Blob Storage용 커넥터 구성

1. 대상 그룹 인사이트에서 **데이터** > **내보내기 대상** 으로 이동합니다.

1. **Azure Blob Storage** 아래에서 **설정** 을 선택합니다.

1. Azure Blob Storage 계정의 **계정 이름**, **계정 키**, **컨테이너** 를 입력합니다.
    - Azure Blob Storage 계정 이름 및 계정 키를 찾는 방법에 대한 자세한 내용은 [Azure Portal에서 저장소 계정 설정 관리](/azure/storage/common/storage-account-manage)를 참조하십시오.
    - 컨테이너를 만드는 방법을 배우려면 [컨테이너 만들기](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)를 참조하세요.

1. **표시 이름** 필드에서 대상에 인식할 수 있는 이름을 지정합니다.

1. **다음** 을 선택합니다.

1. 이 대상으로 내보내려는 각 엔터티 옆의 상자를 선택하십시오.

1. **저장** 을 선택합니다.

내보낸 데이터는 구성한 Azure Blob Storage 컨테이너에 저장됩니다. 컨테이너에 다음 폴더 경로가 자동으로 생성됩니다.

- 원본 엔터티 및 시스템에서 생성된 엔터티의 경우:`%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - 예: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- 내보낸 엔티티의 model.json은 %ExportDestinationName% 수준에 있음
  - 예: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>데이터 내보내기

[주문 시 데이터를 내보낼](export-destinations.md#export-data-on-demand) 수 있습니다. 내보내기는 [예약된 새로 고침](system.md#schedule-tab)마다 실행됩니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]