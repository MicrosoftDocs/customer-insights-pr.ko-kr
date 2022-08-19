---
title: Azure Maps의 위치 데이터로 고객 프로필 보강(프리뷰)
description: Azure Maps 자사 보강에 대한 일반 정보.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f14b4fc20a9a1d8842f42f9e0e656b3d8dcddcf4
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2022
ms.locfileid: "9238050"
---
# <a name="enrich-customer-profiles-with-location-data-from-azure-maps-preview"></a>Azure Maps의 위치 데이터로 고객 프로필 보강(프리뷰)

Azure Maps는 기본 제공 위치 인텔리전스를 통해 지리 공간 데이터를 기반으로 경험을 제공하는 위치 중심 데이터 및 서비스를 제공합니다. Azure Maps 데이터 보강 서비스는 고객에 대한 위치 정보의 정밀도를 향상시킵니다. Dynamics 365 Customer Insights에 주소 정규화, 위도 및 경도 추출과 같은 기능을 제공합니다.

## <a name="prerequisites"></a>전제 조건

- 활성 Azure Maps 구독입니다. 구독하려면 [가입하거나 무료 평가판을 받으세요](https://azure.microsoft.com/services/azure-maps/).

- Azure Maps [연결](connections.md)은 관리자가 [구성](#configure-the-connection-for-azure-maps)합니다.

## <a name="configure-the-connection-for-azure-maps"></a>Azure Maps에 대한 연결 구성

Customer Insights의 [관리자](permissions.md#admin)여야 하며 활성 Azure Maps API 키가 있어야 합니다.

1. 보강을 구성할 때 **연결 추가** 를 선택하거나 **관리자** > **연결** 로 이동하여 Azure Maps 타일에서 **설정** 을 선택합니다.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Azure Maps 연결 구성 페이지.":::

1. 연결 이름과 유효한 Azure Maps API 키를 입력합니다.

1. [데이터 개인 정보 보호 및 규정 준수](connections.md#data-privacy-and-compliance)를 검토하고 **동의함** 을 선택합니다.

1. **확인** 을 선택하여 구성을 확인한 다음 **저장** 을 선택합니다.

## <a name="configure-the-enrichment"></a>보강 구성

1. **데이터** > **보강** 으로 이동 후, **발견하기** 탭을 선택합니다.

1. Microsoft Azure Maps 타일의 **위치** 에서 **내 데이터 보강** 을 선택합니다.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Azure Maps 타일.":::

1. 개요를 검토한 후 **다음** 을 선택합니다.

1. 연결을 선택합니다. 사용 가능한 연결이 없으면 관리자에게 문의하십시오.

1. **다음** 을 선택합니다.

1. **고객 데이터 세트** 를 선택하고 Microsoft의 데이터로 보강할 프로필 또는 세그먼트를 선택합니다. *고객* 엔터티는 모든 고객 프로필을 강화하는 반면 세그먼트는 해당 세그먼트에 포함된 고객 프로필만 강화합니다.

1. 일치에 사용할 통합 프로필의 필드 유형(기본 및/또는 보조 주소)을 정의합니다. 두 주소에 대해 필드 매핑을 지정하고 두 주소에 대해 개별적으로 프로필을 보강할 수 있습니다. 예를 들어 집 주소와 회사 주소가 있습니다. **다음** 을 선택합니다.

1. Azure Maps에서 위치 데이터에 필드를 매핑합니다. **상세 주소 1** 및 **우편 번호** 필드는 선택한 기본 또는 보조 주소의 필수 항목입니다. 더 높은 일치 정확도를 위해 더 많은 필드를 추가하세요.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Azure Maps 특성 매핑.":::

1. 필드 매핑을 완료하려면 **다음** 을 선택합니다.

1. 최대의 유연성을 제공하여 고급 사용 사례를 처리할 수 있는 **고급 설정** 을 검토하세요. 그러나 다음 기본값은 일반적으로 변경할 필요가 없습니다.

   - **주소 유형**: 불완전한 경우에도 최상의 주소 일치가 반환됩니다. 완전한 주소만 얻으려면&mdash;예를 들어 집 번호가 포함된 주소&mdash;**포인트 주소** 를 제외한 모든 확인란을 선택 취소합니다.
   - **언어**: 주소는 주소 영역을 기반으로 하는 언어로 반환됩니다. 표준화된 주소 언어를 적용하려면 드롭다운 메뉴에서 언어를 선택합니다. 예를 들어 **영어** 를 선택하면 **København, Danmark** 대신 **Copenhagen, Denmark** 가 반환됩니다.
   - **최대 결과 수**: 주소당 결과 수입니다.

1. **다음** 을 선택합니다.

1. 보강에 대한 **이름** 과 **출력 엔터티 이름** 을 제공합니다.

1. 선택 사항을 검토 한 후 **보강 저장** 을 선택합니다.

1. **실행** 을 선택하여 강화 프로세스를 시작하거나 닫기를 선택하여 **강화** 페이지로 돌아갑니다.

## <a name="view-enrichment-results"></a>강화 결과 보기

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**필드로 보강된 고객 수** 는 각 보강된 필드의 적용 범위에 대한 드릴다운을 제공합니다.

## <a name="next-steps"></a>다음 단계

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
