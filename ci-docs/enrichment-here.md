---
title: HERE Technologies로 고객 프로필 보강(프리뷰)
description: HERE Technologies 타사 보강에 대한 일반 정보입니다.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 26de9fce863c9832b70adf3ce39cb2ae0ce43d0e
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196264"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>HERE Technologies로 고객 프로필 보강(프리뷰)

HERE Technologies는 위치 중심 데이터 및 서비스를 제공하는 위치 플랫폼 회사입니다. HERE Technologies의 데이터 강화 서비스는 고객에 대한 위치 정보의 정확성을 향상시킵니다. 주소 정규화, 위도 및 경도 추출 등을 제공합니다.

## <a name="prerequisites"></a>전제 조건

- 활성 HERE Technologies 구독. 구독하려면 [여기에서 가입](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic)하거나 직접 [HERE Technologies에 문의](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you)하세요. [HERE Technologies Location 보강에 대해 자세히 알아보세요.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- HERE [연결](connections.md)은 관리자가 [구성](#configure-the-connection-for-here-technologies)합니다.

## <a name="configure-the-connection-for-here-technologies"></a>HERE Technologies에 대한 연결 구성

Customer Insights의 [관리자](permissions.md#admin)여야 하며 활성 HERE Technologies API 키가 있어야 합니다.

1. 강화를 구성할 때 **연결 추가** 를 선택하거나 **관리** > **연결** 로 이동하고 HERE 기술 타일에서 **설정** 을 선택합니다.

1. 연결 이름과 유효한 HERE Technologies API 키를 입력합니다.

1. [데이터 개인 정보 보호 및 규정 준수](#data-privacy-and-compliance)를 검토하고 **동의함** 을 선택하여 동의를 제공합니다.

1. **확인** 을 선택하여 구성을 확인한 다음 **저장** 을 선택합니다.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="HERE technologies 연결 구성 페이지.":::

### <a name="data-privacy-and-compliance"></a>데이터 프라이버시 및 규정 준수

Dynamics 365 Customer Insights를 사용하여 HERE Technologies로 데이터를 전송하는 경우 Dynamics 365 Customer Insights 규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다. Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 HERE Technologies가 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다. 자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.
Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 보강을 언제든지 제거할 수 있습니다.

## <a name="configure-the-enrichment"></a>보강 구성

1. **데이터** > **보강** 으로 이동 후, **발견하기** 탭을 선택합니다.

1. HERE Technologies 타일의 **위치** 에서 **내 데이터 보강** 을 선택합니다.

   :::image type="content" source="media/HERE-tile.png" alt-text="HERE Technologies 타일.":::

1. 개요를 검토한 후 **다음** 을 선택합니다.

1. 연결을 선택합니다. 사용 가능한 연결이 없으면 관리자에게 문의하십시오.

1. **다음** 을 선택합니다.

1. **고객 데이터 세트** 를 선택하고 HERE Technologies의 데이터로 보강할 프로필 또는 세그먼트를 선택합니다. *고객* 엔터티는 모든 고객 프로필을 강화하는 반면 세그먼트는 해당 세그먼트에 포함된 고객 프로필만 강화합니다.

1. 일치에 사용할 통합 프로필의 필드 유형(기본 및/또는 보조 주소)을 정의합니다. 두 주소에 대해 필드 매핑을 지정하고 두 주소에 대해 개별적으로 프로필을 보강할 수 있습니다. 예를 들어 집 주소와 회사 주소가 있습니다. **다음** 을 선택합니다.

1. HERE Technologies의 데이터에 필드를 매핑합니다. **상세 주소 1** 및 **우편 번호** 필드는 선택한 기본 또는 보조 주소의 필수 항목입니다. 더 높은 일치 정확도를 위해 더 많은 필드를 추가하세요.

1. 필드 매핑을 완료하려면 **다음** 을 선택합니다.

1. 보강에 대한 **이름** 과 **출력 엔터티 이름** 을 제공합니다.

1. 선택 사항을 검토 한 후 **보강 저장** 을 선택합니다.

1. **실행** 을 선택하여 강화 프로세스를 시작하거나 닫기를 선택하여 **강화** 페이지로 돌아갑니다.

## <a name="view-enrichment-results"></a>강화 결과 보기

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**필드로 보강된 고객 수** 는 각 보강된 필드의 적용 범위에 대한 드릴다운을 제공합니다.

## <a name="next-steps"></a>다음 단계

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
