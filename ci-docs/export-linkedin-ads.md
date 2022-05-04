---
title: Customer Insights 데이터를 LinkedIn Ads로 내보내기
description: 연결을 구성하고 LinkedIn Ads로 내보내는 방법을 알아봅니다.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bf1d12ffbd7a4cfd7d268fea8a1f90cc37589e00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647447"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>LinkedIn Ads로 세그먼트 내보내기(프리뷰)

통합 고객 프로필의 세그먼트를 LinkedIn Ads로 내보내어 Matched Audiences를 만듭니다. 회사 타겟팅 및 연락처 타겟팅에 Matched Audiences를 사용합니다.

## <a name="prerequisites"></a>필수 조건

-   [LinkedIn Campaign Manager 계정](https://business.linkedin.com/marketing-solutions/ads) 및 해당 관리자 자격 증명이 있습니다.
-   Customer Insights에 [세그먼트를 구성](segments.md)했습니다.
-   내 보낸 세그먼트의 고객 프로필에는 이메일 주소가 있는 필드가 포함됩니다.

## <a name="known-limitations"></a>알려진 제한 사항

- Customer Insights의 세그먼트에는 최소 300개의 고유 프로필이 포함되어야 합니다. 
- LinkedIn Ads로 내보낼 때마다 고객 프로필을 최대 10만 개까지 내보낼 수 있습니다.
- LinkedIn Ads로 내보내기는 세그먼트로 제한됩니다.
- 최대 10만 개의 고객 프로필을 LinkedIn Ads로 내보내려면 최대 10분이 소요될 수 있습니다. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>LinkedIn Ads에 대한 연결 설정하기

1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 와 **LinkedIn Ads** 를 선택하여 연결을 구성합니다.

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 이 연결을 사용할 수 있는 사용자를 선택합니다. 아무 작업도 하지 않으면 기본값은 관리자입니다. 자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.

1. [LinkedIn Campaign Manager 계정 ID](https://www.linkedin.com/help/lms/answer/a424270)를 제공합니다.

1. **동의** 를 선택해 **데이터 프라이버시 및 규정 준수** 를 확인합니다.

1. **연결** 을 선택하여 Campaign Monitor에 대한 연결을 초기화합니다.

1. **LinkedIn** 으로 인증을 선택하고 LinkedIn Campaign Manager에 대한 관리자 자격 증명을 제공합니다.

1. **내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.

1. 연결을 완료하려면 **저장** 을 선택합니다.

## <a name="configure-an-export"></a>내보내기 구성

이 유형의 연결에 대한 액세스 권한이 있는 경우 내보내기를 구성할 수 있습니다. 자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.

1. **데이터** > **내보내기** 로 이동합니다.

1. **대상 추가** 를 선택하여 새 내보내기를 만듭니다.

1. **내보내기 연결** 필드의 LinkedIn Ads 섹션에서 연결을 선택합니다. 이 섹션 이름이 표시되지 않으면 사용 가능한 이 유형의 연결이 없는 것입니다.

1. LinkedIn에서 [연락처 타겟팅](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) 또는 [회사 타겟팅](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting)을 수행하기 위해 데이터를 내보낼지 여부를 선택합니다. 

1. **데이터 일치** 섹션에서 연락처 타겟팅의 경우 고객의 이메일 주소, Apple Ad ID, Google Ad ID, Google 사용자 ID 또는 성과 이름을 나타내는 필드를 하나 이상 선택합니다. 회사 타겟팅을 선택하는 경우 회사 이름, 이메일 도메인, LinkedIn 페이지 URL, 주식 종목 또는 웹 사이트를 나타내는 필드를 하나 이상 선택합니다. 추가 필드를 선택하여 내보내기를 추가로 정의할 수 있습니다. 

1. 내보낼 세그먼트를 선택합니다. 내보내기 위해 선택한 세그먼트의 이름으로 LinkedIn Campaign Manager의 Matched Audiences가 자동으로 생성됩니다. 각 세그먼트는 별도의 Matched Audience를 생성합니다. 

1. **저장** 을 선택합니다.

내보내기를 저장해도 내보내기가 즉시 실행되지는 않습니다.

내보내기는 모든 [예약된 새로 고침](system.md#schedule-tab)에 따라 실행됩니다. [주문형으로 데이터를 내보낼](export-destinations.md#run-exports-on-demand)수도 있습니다. 


## <a name="data-privacy-and-compliance"></a>데이터 프라이버시 및 규정 준수

LinkedIn Ads로 데이터를 전송하기 위해 Dynamics 365 Customer Insights를 활성화 할 때 Dynamics 365 Customer Insights의 규정 준수 경계를 벗어나 개인 데이터와 같이 잠재적으로 민감한 데이터를 포함한 데이터의 전송을 허용합니다. Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 귀하는 LinkedIn Ads가 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하는지 확인할 책임이 있습니다. 자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.

Dynamics 365 Customer Insights 관리자는 이 기능의 사용을 중지하도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.
