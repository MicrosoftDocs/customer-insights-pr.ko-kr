---
title: LinkedIn Ads로 세그먼트 내보내기(프리뷰)
description: 연결을 구성하고 LinkedIn Ads로 내보내는 방법을 알아봅니다.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4c3928e05db0ebda262b4ad3e928ce85f70035b9
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304711"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>LinkedIn Ads로 세그먼트 내보내기(프리뷰)

통합 고객 프로필의 세그먼트를 LinkedIn Ads로 내보내어 Matched Audiences를 만듭니다. 회사 타겟팅 및 연락처 타겟팅에 Matched Audiences를 사용합니다.

## <a name="prerequisites"></a>전제 조건

- [LinkedIn Campaign Manager 계정](https://business.linkedin.com/marketing-solutions/ads) 및 해당 관리자 자격 증명입니다.
- [LinkedIn Campaign Manager 계정 ID](https://www.linkedin.com/help/lms/answer/a424270)입니다.
- Customer Insights에 [세그먼트를 구성했습니다](segments.md).
- 내보낸 세그먼트에는 LinkedIn에서 [연락처 타겟팅](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) 또는 [회사 타겟팅](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting)을 선택하는지에 따라 하나 이상의 특정 필드가 필요합니다. 가능한 필드는 [내보내기 구성](#configure-an-export) 시 **데이터 일치** 단계에 나열됩니다.

## <a name="known-limitations"></a>알려진 제한 사항

- 최대 10만 개의 고객 프로필을 LinkedIn Ads로 내보낼 때마다 최대 10분이 소요될 수 있습니다.
- 세그먼트만 해당됩니다. 세그먼트에는 300개 이상의 고유 프로필이 포함되어야 합니다.

## <a name="set-up-connection-to-linkedin-ads"></a>LinkedIn Ads에 대한 연결 설정

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 를 선택하고 **LinkedIn Ads** 를 선택합니다.

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 이 연결을 사용할 수 있는 사용자를 선택합니다. 기본적으로 관리자만 해당합니다. 자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.

1. LinkedIn Campaign Manager 계정 ID를 입력합니다.

1. [데이터 개인 정보 보호 및 규정 준수](connections.md#data-privacy-and-compliance)를 검토하고 **동의함** 을 선택합니다.

1. **연결** 을 선택하여 해당 연결을 초기화합니다.

1. **LinkedIn** 으로 인증을 선택하고 LinkedIn Campaign Manager에 대한 관리자 자격 증명을 제공합니다.

1. **내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.

1. 연결을 완료하려면 **저장** 을 선택합니다.

## <a name="configure-an-export"></a>내보내기 구성

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **데이터** > **내보내기** 로 이동합니다.

1. **내보내기 추가** 를 선택합니다.

1. **내보내기 연결** 필드의 LinkedIn Ads 섹션에서 연결을 선택합니다. 사용 가능한 연결이 없으면 관리자에게 문의하십시오.

1. 내보낼 엔터티의 이름을 입력합니다.

1. LinkedIn에서 [연락처 타겟팅](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) 또는 [회사 타겟팅](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting)을 수행하기 위해 데이터를 내보낼지 여부를 선택합니다.

1. **데이터 일치** 섹션에서 연락처 타겟팅의 경우 고객의 이메일 주소, Apple Ad ID, Google Ad ID, Google 사용자 ID 또는 성과 이름을 나타내는 필드를 하나 이상 선택합니다. 회사 타겟팅을 선택하는 경우 회사 이름, 이메일 도메인, LinkedIn 페이지 URL, 주식 종목 또는 웹 사이트를 나타내는 필드를 하나 이상 선택합니다.

1. 필요에 따라 필드를 추가하여 내보내기를 추가로 정의할 수 있습니다. **특성 추가** 를 선택하여 이러한 필드를 매핑합니다.

1. 내보낼 세그먼트를 선택합니다. 내보내기 위해 선택한 세그먼트의 이름으로 LinkedIn Campaign Manager의 Matched Audiences가 자동으로 생성됩니다. 각 세그먼트는 별도의 Matched Audience를 생성합니다.

1. **저장** 을 선택합니다.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
