---
title: Dynamics 365 Marketing으로 세그먼트 내보내기(프리뷰)
description: 연결을 구성하고 Dynamics 365 Marketing으로 내보내는 방법을 알아봅니다.
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
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196632"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Dynamics 365 Marketing으로 세그먼트 내보내기(프리뷰)

[세그먼트](segments.md)를 사용하여 캠페인을 생성하고 [Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)의 특정 고객 그룹에게 연락합니다.

Dataverse 조직에서 실시간 고객 여정 오케스트레이션을 위해 Dynamics 365 Marketing의 새로운 기능을 사용하는 경우 Dynamics 365 Marketing에 대한 표준 내보내기를 만들 필요가 없습니다. Customer Insights의 연락처 및 세그먼트는 Marketing 및 Customer Insights를 연결한 후 Dynamics 365 Marketing에서 직접 사용할 수 있습니다. 기존 내보내기를 삭제하기 전에 [Customer Insights와 Dynamics 365 Marketing 고객 여정 오케스트레이션을 연결하는 방법](/dynamics365/marketing/real-time-marketing-ci-profile) 문서를 검토하십시오.

## <a name="prerequisite"></a>전제 조건

Customer Insights에서 마케팅으로 세그먼트를 내보내려면 먼저 Dynamics 365 Marketing에 연락처 레코드가 있어야 합니다. [Microsoft Dataverse를 사용하는 Dynamics 365 Marketing](connect-dataverse-managed-lake.md)에서 연락처를 수집하는 방법에 대해 자세히 알아보십시오.

> [!NOTE]
> Customer Insights에서 Marketing으로 세그먼트를 내보내면 Marketing 인스턴스에 새 연락처 레코드가 생성되지 않습니다. Marketing의 연락처 레코드는 Customer Insights에서 수집되고 데이터 원본으로 사용해야 합니다. 또한 세그먼트를 내보내기 전에 고객 ID를 연락처 ID에 매핑하려면 통합 고객 엔터티에 포함되어야 합니다.

## <a name="set-up-connection-to-marketing"></a>Marketing에 연결을 설정합니다.

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 를 선택하고 **Dynamics 365 Marketing** 을 선택합니다.

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 이 연결을 사용할 수 있는 사용자를 선택합니다. 기본적으로 관리자만 해당합니다. 자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.

1. **서버 주소** 필드에 조직의 Marketing URL을 입력하십시오.

1. **서버 관리자 계정** 섹션에서 **로그인** 을 선택하고 Dynamics 365 Marketing 계정을 선택하십시오.

1. Customer 엔터티의 연락처 ID 필드를 Dynamics 365 연락처 ID에 매핑합니다.

1. [데이터 개인 정보 보호 및 규정 준수](connections.md#data-privacy-and-compliance)를 검토하고 **동의함** 을 선택합니다.

1. 연결을 완료하려면 **저장** 을 선택합니다.

## <a name="configure-an-export"></a>내보내기 구성

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **데이터** > **내보내기** 로 이동합니다.

1. **내보내기 추가** 를 선택합니다.

1. **내보내기 연결** 필드의 Dynamics 365 Marketing 섹션에서 연결을 선택합니다. 사용 가능한 연결이 없으면 관리자에게 문의하십시오.

1. 내보낼 엔터티의 이름을 입력합니다.

1. Dynamics 365 연락처 ID와 일치하는 Customer 엔터티의 연락처 ID 필드를 선택합니다.

1. 내보낼 세그먼트를 선택합니다.

1. **저장** 을 선택합니다.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
