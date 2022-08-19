---
title: LiveRamp의 ID 데이터로 고객 프로필 보강(프리뷰)
description: LiveRamp 데이터로 고객 프로필을 보강합니다.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0aa6dc144602741b87843a5373779855ee3e334c
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237820"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>LiveRamp의 ID 데이터로 고객 프로필 보강(프리뷰)

LiveRamp는 결정적 오프라인 ID 확인 및 고객 데이터 통합을 제공합니다. 고객 데이터의 개인 식별자를 AbiliTec ID 그래프에 매핑하고 AbiliTec ID를 받을 수 있습니다. 그런 다음 이 ID를 사용하여 고객 데이터를 더 잘 통합할 수 있습니다.

## <a name="supported-countriesregions"></a>지원되는 국가/지역

LiveRamp 데이터로 고객 프로필 보강은 현재 미국에서만 지원됩니다.

## <a name="prerequisites"></a>전제 조건

- 활성 LiveRamp 구독입니다. 구독하려면 LiveRamp 계정 팀이나 [dynamics@liveramp.com](mailto:dynamics@liveramp.com)에 자세한 내용을 문의하세요.

- API에 액세스하기 위한 클라이언트 ID 및 암호가 있는 활성 AbiliTec 구독입니다. 자세한 내용은 [AbiliTec API 개발자 허브](https://developers.liveramp.com/abilitec-api/)를 참조하세요.

- LiveRamp [연결](connections.md)은 관리자가 [구성](#configure-the-connection-for-liveramp)합니다.

## <a name="configure-the-connection-for-liveramp"></a>LiveRamp에 대한 연결 구성

Customer Insights의 [관리자](permissions.md#admin)여야 하며 활성 LiveRamp 클라이언트 ID 및 암호가 있어야 합니다.

1. 보강을 구성할 때 **연결 추가** 를 선택하거나 **관리** > **연결** 로 이동하여 LiveRamp 타일에서 **설정** 을 선택합니다.

   :::image type="content" source="media/liveramp-connection.png" alt-text="LiveRamp AbiliTec 서비스에 대한 연결을 설정하는 구성 창입니다.":::

1. 연결 이름과 유효한 LiveRamp 클라이언트 ID 및 암호를 입력합니다.

1. [데이터 개인 정보 보호 및 규정 준수](connections.md#data-privacy-and-compliance)를 검토하고 **동의함** 을 선택합니다.

1. **확인** 을 선택하여 구성을 확인한 다음 **저장** 을 선택합니다.

## <a name="configure-the-enrichment"></a>보강 구성

1. **데이터** > **보강** 으로 이동 후, **발견하기** 탭을 선택합니다.

1. LiveRamp 타일의 **ID** 에서 **내 데이터 보강** 을 선택합니다.

   :::image type="content" source="media/liveramp-tile.png" alt-text="보강 개요 페이지의 ID 타일입니다. ":::

1. 개요를 검토한 후 **다음** 을 선택합니다.

1. 연결을 선택합니다. 사용 가능한 연결이 없으면 관리자에게 문의하십시오.

1. **다음** 을 선택합니다.

1. **고객 데이터 세트** 를 선택하고 LiveRamp의 ID 데이터로 보강할 프로필 또는 세그먼트를 선택합니다. *고객* 엔터티는 모든 고객 프로필을 강화하는 반면 세그먼트는 해당 세그먼트에 포함된 고객 프로필만 강화합니다.

1. LiveRamp의 ID 데이터를 일치시키는 데 사용할 통합 프로필의 필드 유형을 정의합니다. **이름 및 주소**, **이메일** 또는 **전화** 필드 중 하나 이상이 필수입니다. 더 높은 일치 정확도를 위해 기타 필드를 추가하세요. **다음** 을 선택합니다.

1. LiveRamp의 ID 데이터에 필드를 매핑합니다.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="LiveRamp 보강을 위한 데이터 매핑 옵션입니다.":::

1. 필드 매핑을 완료하려면 **다음** 을 선택합니다.

1. 보강에 대한 **이름** 과 **출력 엔터티 이름** 을 제공합니다.

1. 선택 사항을 검토 한 후 **보강 저장** 을 선택합니다.

1. **실행** 을 선택하여 강화 프로세스를 시작하거나 닫기를 선택하여 **강화** 페이지로 돌아갑니다.

## <a name="view-enrichment-results"></a>강화 결과 보기

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**필드로 보강된 고객 수** 는 각 보강된 필드의 적용 범위에 대한 드릴다운을 제공합니다.

## <a name="next-steps"></a>다음 단계

보강된 고객 데이터를 바탕으로 구축합니다. AbiliTec ID를 사용하여 고객 프로필을 개인 기반 보기로 통합합니다.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
