---
title: Dynamics 365 Sales로 세그먼트 내보내기(프리뷰)
description: 연결을 구성하고 Dynamics 365 Sales로 내보내는 방법을 알아봅니다.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: c3497f4625cada49ae33c6987e58994a15536f9b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195989"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Dynamics 365 Sales로 세그먼트 내보내기(프리뷰)

고객 데이터를 사용하여 마케팅 목록을 만들고, 워크플로에 대한 후속작업을 수행하고, Dynamics 365 Sales로 홍보 행사를 보냅니다.

## <a name="prerequisites"></a>전제 조건

Customer Insights에서 영업으로 세그먼트를 내보내려면 먼저 Dynamics 365 Sales에 연락처 레코드가 있어야 합니다. [Microsoft Dataverse를 사용하여 Dynamics 365 Sales](connect-dataverse-managed-lake.md)에서 연락처를 수집하는 방법에 대해 자세히 알아보세요.

   > [!NOTE]
   > Customer Insights에서 영업으로 세그먼트를 내보내면 영업 인스턴스에 새 연락처 레코드가 생성되지 않습니다. 영업의 연락처 레코드는 Customer Insights에서 수집되고 데이터 원본으로 사용해야 합니다. 또한 세그먼트를 내보내기 전에 고객 ID를 연락처 ID에 매핑하려면 통합 고객 엔터티에 포함되어야 합니다.

## <a name="known-limitations"></a>알려진 제한 사항

10만으로 제한된 세그먼트를 Dynamics 365 Sales로 내보낼 때마다 완료까지 최대 3시간이 소요될 수 있습니다.

## <a name="set-up-connection-to-sales"></a>Sales에 대한 연결 설정

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 를 선택하고 **Dynamics 365 Sales** 를 선택합니다.

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 이 연결을 사용할 수 있는 사용자를 선택합니다. 기본적으로 관리자만 해당합니다. 자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.

1. **서버 주소** 필드에 조직의 Sales URL을 입력하십시오.

1. **서버 관리자 계정** 섹션에서 **로그인** 을 선택하고 Dynamics 365 Sales 계정을 선택하십시오.

1. 고객 ID 필드를 Dynamics 365 연락처 ID에 매핑합니다.

1. [데이터 개인 정보 보호 및 규정 준수](connections.md#data-privacy-and-compliance)를 검토하고 **동의함** 을 선택합니다.

1. 연결을 완료하려면 **저장** 을 선택합니다.

## <a name="configure-an-export"></a>내보내기 구성

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **데이터** > **내보내기** 로 이동합니다.

1. **내보내기 추가** 를 선택합니다.

1. **내보내기 연결** 필드의 Dynamics 365 Sales 섹션에서 연결을 선택합니다. 사용 가능한 연결이 없으면 관리자에게 문의하십시오.

1. 내보낼 엔터티의 이름을 입력합니다.

1. Dynamics 365 연락처 ID와 일치하는 Customer 엔터티의 연락처 ID 필드를 선택합니다.

1. 내보낼 세그먼트를 선택합니다.

1. **저장** 을 선택합니다.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
