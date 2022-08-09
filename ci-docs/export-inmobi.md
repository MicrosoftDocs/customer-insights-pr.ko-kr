---
title: InMobi로 Customer Insights 데이터 내보내기
description: 연결을 구성하고 InMobi로 내보내는 방법을 알아보세요.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195896"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>InMobi로 Customer Insights 데이터 내보내기(프리뷰)

Customer Insights 인스턴스에서 [InMobi](https://www.inmobi.com/)로 세그먼트 목록 또는 기타 데이터를 내보냅니다.

## <a name="prerequisites"></a>전제 조건

- [InMobi 계정](https://www.inmobi.com/)과 관리자 자격 증명입니다.
- [Azure Blob Storage 계정](/azure/storage/blobs/create-data-lake-storage-account) 이름과 계정 키입니다. 이름 및 키를 찾는 방법에 대한 자세한 내용은 [Azure Portal에서 스토리지 계정 설정 관리](/azure/storage/common/storage-account-manage)를 참조하세요.
- InMobi 데이터를 내보내는 [Azure Blob Storage 컨테이너](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)입니다.
- InMobi는 Blob Storage에 대한 직접 연결을 생성하고 데이터를 InMobi로 자동 가져오기를 구성합니다. 프로세스를 시작하려면 InMobi 담당자에게 문의하세요.

## <a name="known-limitations"></a>알려진 제한 사항

- Azure Blob Storage의 경우 [표준 성능과 프리미엄 성능 계층](/azure/storage/blobs/storage-blob-performance-tiers) 중에서 선택합니다. 프리미엄 성능 계층을 선택하는 경우 [프리미엄 블록 Blob을 계정 유형으로](/azure/storage/common/storage-account-overview#types-of-storage-accounts) 선택합니다.

## <a name="set-up-connection-to-azure-blob-storage"></a>Azure Blob Storage에 대한 연결 설정

[Azure Blob Storage에 대한 연결을 설정](export-azure-blob-storage.md)합니다.

## <a name="configure-an-export"></a>내보내기 구성

[내보내기를 구성](export-azure-blob-storage.md#configure-an-export)합니다.

[!INCLUDE [footer-include](includes/footer-banner.md)]
