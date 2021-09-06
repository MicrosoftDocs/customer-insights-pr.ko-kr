---
title: Dynamics 365 Marketing에 Customer Insights 데이터 내보내기
description: 연결을 구성하고 Dynamics 365 Marketing으로 내보내는 방법을 알아봅니다.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b8e63a738abaf4fbb902e3edbf83f5a815978478
ms.sourcegitcommit: 8e89575fe2acb4b289fc157fa7c4c29caf9be967
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2021
ms.locfileid: "7417213"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Dynamics 365 Marketing에 세그먼트 사용(프리뷰)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[세그먼트](segments.md)를 사용하여 캠페인을 생성하고 Dynamics 365 Marketing의 특정 고객 그룹에게 연락합니다. 자세한 내용은 [Dynamics 365 Marketing으로 Dynamics 365 Customer Insights에서 세그먼트 사용](/dynamics365/marketing/customer-insights-segments)을 참조하십시오.

Dataverse 조직에서 실시간 고객 여정 오케스트레이션을 위해 Dynamics 365 Marketing의 새로운 기능을 사용하는 경우 Dynamics 365 Marketing에 대한 표준 내보내기를 만들 필요가 없습니다. 대상 그룹 인사이트의 연락처 및 세그먼트는 Marketing 및 Customer Insights를 연결한 후 Dynamics 365 Marketing에서 직접 사용할 수 있습니다. 기존 내보내기를 삭제하기 전에 [대상 그룹 인사이트와 Dynamics 365 Marketing 고객 여정 오케스트레이션을 연결하는 방법](/dynamics365/marketing/real-time-marketing-ci-profile)에 대한 문서를 검토하십시오.

## <a name="prerequisite-for-a-connection"></a>연결을 위한 전제 조건

- Customer Insights에서 마케팅으로 세그먼트를 내보내려면 먼저 Dynamics 365 Marketing에 연락처 레코드가 있어야 합니다. [Microsoft Dataverse를 사용하는 Dynamics 365 Marketing](connect-power-query.md)에서 연락처를 수집하는 방법에 대해 자세히 알아보십시오.

  > [!NOTE]
  > 대상 그룹 인사이트에서 마케팅으로 세그먼트를 내보내면 마케팅 인스턴스에 새 연락처 레코드가 생성되지 않습니다. 마케팅의 연락처 레코드는 대상 그룹 인사이트에서 수집되고 데이터 원본으로 사용되어야 합니다. 또한 세그먼트를 내보내기 전에 고객 ID를 연락처 ID에 매핑하려면 통합 고객 엔터티에 포함되어야 합니다.

## <a name="set-up-connection-to-marketing"></a>Marketing에 연결을 설정합니다.

1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 와 **Dynamics 365 Marketing** 을 선택하여 연결을 구성합니다.

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 이 연결을 사용할 수 있는 사용자를 선택합니다. 아무 조치도 취하지 않으면 기본값은 관리자입니다. 자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.

1. **서버 주소** 필드에 조직의 Marketing URL을 입력하십시오.

1. **서버 관리자 계정** 섹션에서 **로그인** 을 선택하고 Dynamics 365 Marketing 계정을 선택하십시오.

1. 고객 ID 필드를 Dynamics 365 연락처 ID에 매핑합니다.

1. 연결을 완료하려면 **저장** 을 선택합니다. 

## <a name="configure-an-export"></a>내보내기 구성

이 유형의 연결에 대한 액세스 권한이 있는 경우 이 내보내기를 구성할 수 있습니다. 자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.

1. **데이터** > **내보내기** 로 이동합니다.

1. **대상 추가** 를 선택하여 새 내보내기를 만듭니다.

1. **내보내기 연결** 필드의 Dynamics 365 Marketing 섹션에서 연결을 선택합니다. 이 섹션 이름이 표시되지 않으면 사용 가능한 이 유형의 연결이 없는 것입니다.

1. 하나 이상의 세그먼트를 선택하십시오.

1. **저장** 을 선택합니다.

내보내기를 저장해도 내보내기가 즉시 실행되지는 않습니다.

내보내기는 모든 [예약된 새로 고침](system.md#schedule-tab)에 따라 실행됩니다. [주문형으로 데이터를 내보낼](export-destinations.md#run-exports-on-demand)수도 있습니다. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
