---
title: Dynamics 365 Sales에 Customer Insights 데이터 내보내기
description: 연결을 구성하고 Dynamics 365 Sales로 내보내는 방법을 알아봅니다.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: cf680c21c55c71d99728be79fe68111dc89a79ec
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355025"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a>Dynamics 365 Sales에 세그먼트 사용(프리뷰)



고객 데이터를 사용하여 마케팅 목록을 만들고, 워크플로에 대한 후속작업을 수행하고, Dynamics 365 Sales로 홍보 행사를 보냅니다.

## <a name="known-limitations"></a>알려진 제한 사항

- Dynamics 365 Sales로 내보내기는 세그먼트당 100,000명의 구성원으로 제한됩니다.
- Dynamics 365 Sales로 세그먼트 내보내기를 완료하는 데 최대 3시간이 걸릴 수 있습니다. 

## <a name="prerequisite-for-connection"></a>연결을 위한 전제 조건

1. Customer Insights에서 영업으로 세그먼트를 내보내려면 먼저 Dynamics 365 Sales에 연락처 레코드가 있어야 합니다. [Microsoft Dataverse를 사용하는 Dynamics 365 Sales](connect-power-query.md)에서 연락처를 수집하는 방법에 대해 자세히 알아보십시오.

   > [!NOTE]
   > 대상 그룹 인사이트에서 영업으로 세그먼트를 내보내면 영업 인스턴스에 새 연락처 레코드가 생성되지 않습니다. 영업의 연락처 레코드는 대상 그룹 인사이트에서 수집되고 데이터 원본으로 사용되어야 합니다. 또한 세그먼트를 내보내기 전에 고객 ID를 연락처 ID에 매핑하려면 통합 고객 엔터티에 포함되어야 합니다.

## <a name="set-up-the-connection-to-sales"></a>Sales에 연결을 설정합니다.

1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 와 **Dynamics 365 Sales** 를 선택하여 연결을 구성합니다.

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 이 연결을 사용할 수 있는 사용자를 선택합니다. 아무 조치도 취하지 않으면 기본값은 관리자입니다. 자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.

1. **서버 주소** 필드에 조직의 Sales URL을 입력하십시오.

1. **서버 관리자 계정** 섹션에서 **로그인** 을 선택하고 Dynamics 365 Sales 계정을 선택하십시오.

1. 고객 ID 필드를 Dynamics 365 연락처 ID에 매핑합니다.

1. 연결을 완료하려면 **저장** 을 선택합니다. 

## <a name="configure-an-export"></a>내보내기 구성

이 유형의 연결에 대한 액세스 권한이 있는 경우 이 내보내기를 구성할 수 있습니다. 자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.

1. **데이터** > **내보내기** 로 이동합니다.

1. **대상 추가** 를 선택하여 새 내보내기를 만듭니다.

1. **내보내기 연결** 필드의 Dynamics 365 Sales 섹션에서 연결을 선택합니다. 이 섹션 이름이 표시되지 않으면 사용 가능한 이 유형의 연결이 없는 것입니다.

1. 하나 이상의 세그먼트를 선택하십시오.

1. **저장** 을 선택합니다.

내보내기를 저장해도 내보내기가 즉시 실행되지는 않습니다.

내보내기는 모든 [예약된 새로 고침](system.md#schedule-tab)에 따라 실행됩니다. [주문형으로 데이터를 내보낼](export-destinations.md#run-exports-on-demand)수도 있습니다. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
