---
title: Dynamics 365 Sales에 Customer Insights 데이터 내보내기
description: Dynamics 365 Sales에 대한 연결을 구성하는 방법에 대해 알아봅니다.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643826"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Dynamics 365 Sales용 커넥터(미리 보기)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

고객 데이터를 사용하여 마케팅 목록을 만들고, 워크플로에 대한 후속작업을 수행하고, Dynamics 365 Sales로 홍보 행사를 보냅니다.

## <a name="prerequisite"></a>필수 구성 요소

[Common Data Service를 사용하여 수집된 Dynamics 365 Sales](connect-power-query.md)의 연락처 레코드입니다.

## <a name="configure-the-connector-for-sales"></a>Sales용 커넥터 구성

1. 대상 그룹 인사이트에서 **데이터** > **내보내기 대상** 으로 이동합니다.

1. **Dynamics 365 Sales** 아래에서 **설정** 을 선택합니다.

1. **표시 이름** 필드에서 내보내기 대상에 인식할 수 있는 이름을 지정합니다.

1. **서버 주소** 필드에 조직의 Sales URL을 입력하십시오.

1. **서버 관리자 계정** 섹션에서 **로그인** 을 선택하고 Dynamics 365 Sales 계정을 선택하십시오.

1. 고객 ID 필드를 Dynamics 365 연락처 ID에 매핑합니다.

1. **다음** 을 선택합니다.

1. 하나 이상의 세그먼트를 선택하십시오.

1. **저장** 을 선택합니다.

## <a name="export-the-data"></a>데이터 내보내기

[주문 시 데이터를 내보낼](export-destinations.md) 수 있습니다. 내보내기는 [예약된 새로 고침](system.md#schedule-tab)마다 실행됩니다.
