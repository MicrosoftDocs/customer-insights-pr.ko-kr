---
title: Leadspace를 통한 회사 프로필 보강(프리뷰)
description: Leadspace 타사 보강에 대한 일반 정보입니다.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f45fabc036775e11fc439f69513678d0607729d0
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237958"
---
# <a name="enrich-company-profiles-with-leadspace-preview"></a>Leadspace를 통한 회사 프로필 보강(프리뷰)

Leadspace는 B-to-B 고객 데이터 플랫폼을 제공하는 데이터 과학 회사입니다. 계정을 기반으로 하는 통합 고객 프로필이 있는 환경에서 데이터를 보강할 수 있습니다. 회사 규모, 위치 또는 산업과 같은 특성으로 *고객 프로필* 을 보강합니다. 직함, 가상 사용자 또는 이메일 인증과 같은 특성으로 *연락처 프로필* 을 보강합니다.

## <a name="prerequisites"></a>전제 조건

- 활성 Leadspace 라이선스.
- 계정 기반의 [Unified Customer Profiles](customer-profiles.md)입니다.
- Leadspace [연결](connections.md)은 관리자가 [구성](#configure-the-connection-for-leadspace)합니다. 제품에 대한 자세한 설명은 [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/)에 직접 확인하십시오.

## <a name="configure-the-connection-for-leadspace"></a>Leadspace에 대한 연결 구성

Customer Insights의 [관리자](permissions.md#admin)여야 하며 "영구 키"(**Leadspace 토큰** 이라고 함)가 있어야 합니다.

1. 보강을 구성할 때 **연결 추가** 를 선택하거나 **관리** > **연결** 로 이동하고 Leadspace 타일에서 **설정** 을 선택합니다.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace 연결 구성 페이지.":::

1. 연결 이름과 유효한 Leadspace 토큰을 입력합니다.

1. [데이터 개인 정보 보호 및 규정 준수](connections.md#data-privacy-and-compliance)를 검토하고 **동의함** 을 선택합니다.

1. **확인** 을 선택하여 구성을 확인한 다음 **저장** 을 선택합니다.

## <a name="configure-the-enrichment"></a>보강 구성

1. **데이터** > **보강** 으로 이동 후, **발견하기** 탭을 선택합니다.

1. Leadspace 타일의 **회사 데이터** 에서 **내 데이터 보강** 을 선택합니다.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace 타일의 스크린샷.":::

1. 개요를 검토한 후 **다음** 을 선택합니다.

1. 연결을 선택합니다. 사용 가능한 연결이 없으면 관리자에게 문의하십시오.

1. **다음** 을 선택합니다.

1. **고객 데이터 세트** 를 선택하고 Leadspace의 회사 데이터로 보강할 프로필 또는 세그먼트를 선택합니다. *고객* 엔터티는 모든 고객 프로필을 강화하는 반면 세그먼트는 해당 세그먼트에 포함된 고객 프로필만 강화합니다.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="고객 데이터 집합 선택 시 스크린샷입니다.":::

1. 일치에 사용할 통합 프로필의 필드 유형(기본 및/또는 보조 주소)을 정의합니다. 두 주소에 대해 필드 매핑을 지정하고 두 주소에 대해 개별적으로 프로필을 보강할 수 있습니다. 예를 들어 집 주소와 회사 주소가 있습니다. **다음** 을 선택합니다.

1. Leadspace의 회사 데이터에 필드를 매핑합니다. **회사의 이름** 필드는 필수입니다. 일치 정확도를 높이기 위해 **회사 웹 사이트** 및 **회사 위치** 라는 다른 필드를 최대 2개까지 추가할 수 있습니다.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace 필드 매핑 창.":::

1. 필드 매핑을 완료하려면 **다음** 을 선택합니다.

1. 보강하려는 *연락처 프로필* 이 있는 경우 확인란을 선택합니다. Customer Insights는 필수 필드를 자동으로 매핑합니다.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Leadspace 연락처 레코드 보강.":::

1. **다음** 을 선택합니다.

1. 보강에 대한 **이름** 과 **출력 엔터티 이름** 을 제공합니다.

1. 선택 사항을 검토 한 후 **보강 저장** 을 선택합니다.

1. **실행** 을 선택하여 강화 프로세스를 시작하거나 닫기를 선택하여 **강화** 페이지로 돌아갑니다.

## <a name="view-enrichment-results"></a>강화 결과 보기

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

자세한 내용은 [Leadspace API](https://support.leadspace.com/hc/en-us/sections/201997649-API)를 참조하십시오.

## <a name="next-steps"></a>다음 단계

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
