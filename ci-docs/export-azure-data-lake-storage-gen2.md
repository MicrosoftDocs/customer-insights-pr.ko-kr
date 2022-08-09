---
title: Azure Data Lake Storage Gen2로 데이터 내보내기(프리뷰)
description: Azure Data Lake Storage Gen2로 연결을 구성하는 방법을 알아보세요.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196448"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Azure Data Lake Storage Gen2로 데이터 내보내기(프리뷰)

Data Lake Storage Gen2에 Customer Insights 데이터를 저장하거나 다른 애플리케이션으로 데이터를 전송하는 데 사용합니다.

## <a name="prerequisites"></a>전제 조건

- [Azure Data Lake Gen2에서 사용할 스토리지 계정](/azure/storage/blobs/create-data-lake-storage-account)입니다. 스토리지 계정 이름 및 키를 찾는 방법에 대한 자세한 내용은 [Azure Portal에서 스토리지 계정 설정 관리](/azure/storage/common/storage-account-manage)를 참조하세요.
- [Azure Blob Storage 컨테이너](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)입니다.

## <a name="known-limitations"></a>알려진 제한 사항

- Azure Data Lake Storage Gen2의 경우 [표준 성능과 프리미엄 성능 계층](/azure/storage/blobs/create-data-lake-storage-account) 중에서 선택할 수 있습니다. 프리미엄 성능 계층을 선택하는 경우 [프리미엄 블록 Blob을 계정 유형으로](/azure/storage/common/storage-account-overview#types-of-storage-accounts) 선택합니다.

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Azure Data Lake Storage Gen2에 대한 연결 설정

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 를 선택하고 **Azure Data Lake Gen2** 를 선택합니다.

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 이 연결을 사용할 수 있는 사용자를 선택합니다. 기본적으로 관리자만 해당합니다. 자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.

1. Azure Data Lake Storage Gen2에 대한 **계정 이름**, **계정 키** 및 **컨테이너** 를 입력합니다.

1. [데이터 개인 정보 보호 및 규정 준수](connections.md#data-privacy-and-compliance)를 검토하고 **동의함** 을 선택합니다.

1. 연결을 완료하려면 **저장** 을 선택합니다.

## <a name="configure-an-export"></a>내보내기 구성

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **데이터** > **내보내기** 로 이동합니다.

1. **내보내기 추가** 를 선택합니다.

1. **내보내기 연결** 필드의 Azure Data Lake 섹션에서 연결을 선택합니다. 사용 가능한 연결이 없으면 관리자에게 문의하십시오.

1. 내보낼 엔터티의 이름을 입력합니다.

1. Azure Data Lake Storage Gen2 스토리지의 폴더 이름을 입력합니다.

1. 이 대상으로 내보내려는 각 엔터티 옆의 상자를 선택하십시오.

1. **저장** 을 선택합니다.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

내보낸 데이터는 구성한 Azure Data Lake 2세대 스토리지 컨테이너에 저장됩니다.

> [!TIP]
> 많은 양의 데이터가 포함된 엔터티를 내보내면 각 내보내기에 대해 동일한 폴더에 여러 CSV 파일이 생성될 수 있습니다. 내보내기를 완료하는 데 걸리는 시간을 최소화하기 위해 성능상의 이유로 내보내기 분할이 발생합니다.

[!INCLUDE [footer-include](includes/footer-banner.md)]
