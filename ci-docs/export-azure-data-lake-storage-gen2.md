---
title: Azure Data Lake Storage Gen2로 Customer Insights 데이터 내보내기
description: Azure Data Lake Storage Gen2로 연결을 구성하는 방법을 알아보세요.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 8b14992f8312d333d8a12501e8a28496c8434779
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646774"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>세그먼트 목록 및 기타 데이터를 Azure Data Lake Storage Gen2로 내보내기(미리 보기)

Data Lake Storage Gen2에 Customer Insights 데이터를 저장하거나 다른 애플리케이션으로 데이터를 전송하는 데 사용합니다.

## <a name="known-limitations"></a>알려진 제한 사항

1. Azure Data Lake Storage Gen2의 경우 데이터 레이크에 대한 스토리지 계정을 만들 때 [표준 성능과 프리미엄 성능 계층](/azure/storage/blobs/create-data-lake-storage-account) 중에서 선택할 수 있습니다. 프리미엄 성능 계층을 선택하는 경우 프리미엄 블록 Blob을 계정 유형으로 선택합니다. 


## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>Azure Data Lake Storage Gen2에 대한 연결 설정 


1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 와 **Azure Data Lake 2세대** 를 선택하여 연결을 구성합니다.

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 이 연결을 사용할 수 있는 사용자를 선택합니다. 아무 조치도 취하지 않으면 기본값은 관리자입니다. 자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.

1. Azure Data Lake Storage Gen2에 대한 **계정 이름**, **계정 키** 및 **컨테이너** 를 입력합니다.
    - Azure Data Lake Storage Gen2와 함께 사용할 스토리지 계정을 만드는 방법을 알아 보려면 [스토리지 계정 만들기](/azure/storage/blobs/create-data-lake-storage-account)를 참조하십시오. 
    - Azure Data Lake 2세대 스토리지 계정 이름 및 계정 키를 찾는 방법에 대한 자세한 내용은 [Azure Portal에서 스토리지 계정 설정 관리](/azure/storage/common/storage-account-manage)를 참조하세요.

1. 연결을 완료하려면 **저장** 을 선택합니다. 

## <a name="configure-an-export"></a>내보내기 구성

이 유형의 연결에 대한 액세스 권한이 있는 경우 이 내보내기를 구성할 수 있습니다. 자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.

1. **데이터** > **내보내기** 로 이동합니다.

1. **내보내기 추가** 를 선택하여 새 내보내기를 만듭니다.

1. **내보내기 연결 필드** 의 **Azure Data Lake** 섹션에서 연결을 선택합니다. 이 섹션 이름이 표시되지 않으면 사용 가능한 이 유형의 연결이 없는 것입니다.

1. 이 대상으로 내보내려는 각 엔터티 옆의 상자를 선택하십시오.

1. **저장** 을 선택합니다.

내보내기를 저장해도 내보내기가 즉시 실행되지는 않습니다.

내보내기는 모든 [예약된 새로 고침](system.md#schedule-tab)에 따라 실행됩니다. [주문형으로 데이터를 내보낼](export-destinations.md#run-exports-on-demand)수도 있습니다. 

내보낸 데이터는 구성한 Azure Data Lake 2세대 스토리지 컨테이너에 저장됩니다. 

[!INCLUDE [footer-include](includes/footer-banner.md)]