---
title: Customer Insights 데이터를 Microsoft Advertising으로 내보내기
description: 연결을 구성하고 Microsoft Advertising으로 내보내는 방법을 알아봅니다.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124516"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Microsoft Advertising으로 세그먼트 내보내기(프리뷰)

Customer Insights 세그먼트를 Microsoft Advertising으로 내보내 Customer Match 대상 그룹을 만듭니다. 이러한 대상 그룹을 광고 캠페인에 사용하십시오.

## <a name="prerequisites"></a>필수 조건

-   [Microsoft Advertising 계정](https://ads.microsoft.com/) 및 해당 관리자 자격 증명.
-   Customer Match 이용 약관에 동의했습니다. 
-   대상 그룹 인사이트의 [구성된 세그먼트](segments.md).
-   내 보낸 세그먼트의 통합 고객 프로필에는 이메일 주소가 있는 필드가 포함됩니다.

## <a name="known-limitations"></a>알려진 제한 사항

- Microsoft Advertising으로 내보낼 때마다 최대 5십만 개의 프로필을 내보낼 수 있습니다.
- Microsoft Advertising으로 내보내기는 세그먼트로 제한됩니다.
- 최대 5십만 개의 프로필을 Microsoft Advertising으로 내보내는 데 최대 10분이 걸릴 수 있습니다. 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>Microsoft Advertising에 대한 연결 설정

1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 를 선택하고 **Microsoft Advertising** 을 선택하여 연결을 구성합니다.

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 이 연결을 사용할 수 있는 사용자를 선택합니다. 기본값은 관리자입니다. 자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.

1. **동의** 를 선택해 **데이터 프라이버시 및 규정 준수** 를 확인합니다.

1. **연결** 을 선택하여 Microsoft Advertising에 대한 연결을 초기화합니다.

1. **Microsoft Advertising으로 인증** 을 선택하고 Microsoft Advertising에 대한 관리자 자격 증명을 제공합니다.

1. **내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.

1. 연결을 완료하려면 **저장** 을 선택합니다.

## <a name="configure-an-export"></a>내보내기 구성

이 유형의 연결에 대한 액세스 권한이 있는 경우 이 내보내기를 구성할 수 있습니다. 자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.

1. **데이터** > **내보내기** 로 이동합니다.

1. **대상 추가** 를 선택하여 새 내보내기를 만듭니다.

1. **내보내기 연결** 필드의 Microsoft Advertising 섹션에서 연결을 선택합니다. 이 섹션 이름이 표시되지 않으면 사용 가능한 이 유형의 연결이 없는 것입니다.

1. 내보낼 세그먼트를 선택합니다. Microsoft Advertising의 Customer Match 대상 그룹은 내보내기 위해 선택한 세그먼트의 이름으로 자동 생성됩니다. 각 세그먼트는 별도의 Customer Match 대상 그룹을 생성합니다. 

1. **Microsoft Advertising 고객 ID 및 계정 ID** 를 입력합니다. Microsoft Advertising에 로그인하면 URL 매개 변수에서 고객 ID(`cid`) 및 계정 ID(`aid`)를 찾을 수 있습니다.

1. **데이터 매칭** 섹션의 **이메일** 필드에서 고객의 이메일 주소가 있는 통합 고객 프로필의 필드를 선택합니다. Microsoft Advertising으로 세그먼트를 내보내야 합니다.

1. **저장** 을 선택합니다.

내보내기를 저장해도 내보내기가 즉시 실행되지는 않습니다.

내보내기는 모든 [예약된 새로 고침](system.md#schedule-tab)에 따라 실행됩니다. [주문형으로 데이터를 내보낼](export-destinations.md#run-exports-on-demand)수도 있습니다. 


## <a name="data-privacy-and-compliance"></a>데이터 프라이버시 및 규정 준수

Microsoft Advertising으로 데이터를 전송하기 위해 Dynamics 365 Customer Insights를 활성화 할 때 Dynamics 365 Customer Insights의 규정 준수 경계를 벗어나 개인 데이터와 같이 잠재적으로 민감한 데이터를 포함한 데이터의 전송을 허용합니다. Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 귀하는 Microsoft Advertising이 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하는지 확인할 책임이 있습니다. 자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.

Dynamics 365 Customer Insights 관리자는 이 기능의 사용을 중지하도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.
