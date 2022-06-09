---
title: Braze로 Customer Insights 데이터 내보내기
description: 연결을 구성하고 Braze로 내보내는 방법을 알아보세요.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bfc9b34506dc3385b5edf12b31e74d05f2d20655
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646675"
---
# <a name="export-segment-lists-to-braze-preview"></a>Braze로 세그먼트 목록 내보내기(프리뷰)

Unified customer profile의 세그먼트를 Braze로 내보내고 마케팅 활동에 사용합니다.

## <a name="prerequisites"></a>전제 조건

-   [Braze 계정](https://www.braze.com/) 및 해당 관리자 자격 증명이 있습니다.
-   Customer Insights에 [세그먼트를 구성](segments.md)했습니다.
-   내보낸 세그먼트의 Unified customer profile에는 이메일 주소와 Braze 고객 ID를 나타내는 필드가 있습니다. 

## <a name="known-limitations"></a>알려진 제한 사항

- Braze로 내보내기는 세그먼트로 제한됩니다.
- 최대 100만 개의 고객 프로필을 Braze로 내보내려면 최대 40분이 소요될 수 있습니다. 
- Braze로 내보낼 수 있는 고객 프로필의 수는 Braze와의 계약에 따라 달라지고 제한됩니다.

## <a name="set-up-connection-to-braze"></a>Braze에 연결 설정

1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 를 선택하고 **Braze** 를 선택하여 연결을 구성합니다.

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 이 연결을 사용할 수 있는 사용자를 선택합니다. 아무 조치도 취하지 않으면 기본값은 관리자입니다. 자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.

1. 계속 로그인하려면 [Braze API 키](https://www.braze.com/docs/api/basics/)를 제공하세요. 

1. **동의** 를 선택해 **데이터 프라이버시 및 규정 준수** 를 확인합니다.

1. **연결** 을 선택하여 Braze와의 연결을 초기화합니다.

1. **내보내기 사용자로 사용자 본인 추가** 를 선택하고 Customer Insights 자격 증명을 제공합니다.

1. 연결을 완료하려면 **저장** 을 선택합니다.

## <a name="configure-an-export"></a>내보내기 구성

이 유형의 연결에 대한 액세스 권한이 있는 경우 이 내보내기를 구성할 수 있습니다. 자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.

1. **데이터** > **내보내기** 로 이동합니다.

1. **대상 추가** 를 선택하여 새 내보내기를 만듭니다.

1. **내보내기 연결** 필드의 Braze 섹션에서 연결을 선택합니다. 이 섹션 이름이 표시되지 않으면 사용 가능한 이 유형의 연결이 없는 것입니다.  

3. **데이터 일치** 섹션의 **이메일** 필드에서 고객의 이메일 주소를 나타내는 필드를 선택하고 "고객 ID" 필드에서 고객의 Braze ID를 나타내는 필드를 선택합니다. Braze로 세그먼트를 내보내는 데 필요합니다. Braze의 세그먼트는 Dynamics 365 Customer Insights에서와 동일한 세그먼트 이름으로 생성됩니다. 데이터 일치를 위해 추가 선택적 필드를 선택할 수 있습니다. 

1. **저장** 을 선택합니다.

내보내기를 저장해도 내보내기가 즉시 실행되지는 않습니다.

내보내기는 모든 [예약된 새로 고침](system.md#schedule-tab)에 따라 실행됩니다. [주문형으로 데이터를 내보낼](export-destinations.md#run-exports-on-demand)수도 있습니다. 


## <a name="data-privacy-and-compliance"></a>데이터 프라이버시 및 규정 준수

Dynamics 365 Customer Insights에서 Braze로 데이터를 전송하도록 설정하면 개인 데이터와 같이 잠재적으로 민감한 데이터를 포함하여 Dynamics 365 Customer Insights의 규정 준수 경계 외부로 데이터를 전송할 수 있습니다. Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 귀하는 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 Braze가 충족하는지 확인할 책임이 있습니다. 자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.

Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.