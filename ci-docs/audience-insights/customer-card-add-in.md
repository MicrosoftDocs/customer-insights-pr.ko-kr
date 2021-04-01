---
title: 고객 카드 추가 기능 설치 및 구성
description: Dynamics 365 Customer Insights용 고객 카드 추가 기능을 설치하고 구성합니다.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f3c4a01f9ce7749eeee72f7901620dae7cb9b8d3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597335"
---
# <a name="customer-card-add-in-preview"></a>고객 카드 추가 기능(미리 보기)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Dynamics 365 앱에서 직접 고객에 대한 모든 측면 보기를 확인하세요. 고객 카드 추가 기능으로 인구 통계, 인사이트 및 활동 일정을 봅니다.

## <a name="prerequisites"></a>필수 구성 요소

- 통합 인터페이스가 활성화된 영업 허브 또는 고객 서비스 허브와 같은 Dynamics 365 앱, 버전 9.0 이상.
- [Common Data Service를 사용하여 Dynamics 365 앱에서 수집](connect-power-query.md)된 고객 프로필입니다.
- 고객 카드 추가 기능의 사용자는 대상 그룹 인사이트에서 [사용자로 추가](permissions.md)되어야 합니다.
- [구성된 검색 및 필터 기능](search-filter-index.md)입니다.
- 인구 통계 제어: 통합 고객 프로필에서 인구 통계 필드(예: 연령 또는 성별)를 사용할 수 있습니다.
- 보강 제어: 활성 [보강](enrichment-hub.md)이 고객 프로필에 적용되어야 합니다.
- 인텔리전스 제어: Azure Machine Learning([예측](predictions.md) 또는 [사용자 지정 모델](custom-models.md))을 사용하여 생성된 데이터 필요
- 측정값 제어: [구성된 측정값](measures.md)이 필요합니다.
- 시간 표시줄 제어: [구성된 활동](activities.md)이 필요합니다.

## <a name="install-the-customer-card-add-in"></a>고객 카드 추가 기능 설치

고객 카드 추가 기능은 Dynamics 365의 Customer Engagement 앱을 위한 솔루션입니다. 솔루션을 설치하려면 AppSource로 이동하고 **Dynamics 고객 카드** 를 검색합니다. [AppSource에서 고객 카드 추가 기능](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview)을 선택하고 **지금 가져 오기** 를 선택합니다.

솔루션을 설치하려면 Dynamics 365 앱에 대한 관리자 자격 증명으로 로그인해야 할 수 있습니다.

솔루션을 환경에 설치하는 데 시간이 걸릴 수 있습니다.

## <a name="configure-the-customer-card-add-in"></a>고객 카드 추가 기능 구성

1. 관리자로서 Dynamics 365에서 **설정** 섹션으로 이동하고 **솔루션** 을 선택합니다.

1. **Dynamics 365 Customer Insights 고객 카드 추가 기능(미리 보기)** 솔루션에 대한 **표시 이름** 링크를 선택합니다.

   > [!div class="mx-imgBorder"]
   > ![표시 이름 선택](media/select-display-name.png "표시 이름 선택")

1. **로그인** 을 선택하고 Customer Insights를 구성하는 데 사용하는 관리자 계정의 자격 증명을 입력합니다.

   > [!NOTE]
   > **로그인** 단추를 선택할 때 브라우저 팝업 차단 기능이 인증 창을 차단하지 않는지 확인하십시오.

1. 데이터를 가져오려는 환경을 선택합니다.

1. Dynamics 365 앱에서 레코드에 대한 필드 매핑을 정의합니다.
   - 연락처와 매핑하려면 연락처 엔터티의 ID와 일치하는 고객 엔터티의 필드를 선택합니다.
   - 계정과 매핑하려면 연락처 엔터티의 ID와 일치하는 계정 엔터티의 필드를 선택합니다.

   > [!div class="mx-imgBorder"]
   > ![연락처 ID 필드](media/contact-id-field.png "연락처 ID 필드")

1. **구성 저장** 을 선택하여 설정을 저장합니다.

1. 그런 다음 사용자가 고객 카드를 사용자 지정하고 볼 수 있도록 Dynamics 365에서 보안 역할을 할당해야 합니다. Dynamics 365에서 **설정** > **보안** > **사용자** 로 이동합니다. 사용자 역할을 편집할 사용자를 선택하고 **역할 관리** 를 선택합니다.

1. 전체 조직에 대해 카드에 표시되는 콘텐츠를 사용자 지정할 사용자에게 **Customer Insights 카드 사용자 지정자** 역할을 할당합니다.

## <a name="add-customer-card-controls-to-forms"></a>양식에 고객 카드 제어 추가
  
1. 연락처 양식에 고객 카드 컨트롤을 추가하려면 Dynamics 365에서에서 **설정** > **사용자 지정** 으로 이동합니다.

1. **시스템 사용자 지정** 을 선택합니다.

1. **연락처** 엔터티를 찾아 확장한 다음 **양식** 을 선택합니다.

1. 고객 카드 컨트롤을 추가할 연락처 양식을 선택합니다.

    > [!div class="mx-imgBorder"]
    > ![연락처 양식 선택](media/contact-active-forms.png "연락처 양식 선택")

1. 양식 편집기에서 컨트롤을 추가하려면 **필드 탐색기** 에서 컨트롤을 배치할 위치로 필드를 드래그합니다.

1. 방금 추가한 양식에서 필드를 선택한 다음 **속성 변경** 을 선택합니다.

1. **컨트롤** 탭으로 이동하여 **컨트롤 추가** 를 선택합니다. 사용 가능한 사용자 지정 컨트롤 중 하나를 선택하고 **추가** 를 선택합니다.

1. **필드 속성** 대화 상자에서 **양식에 레이블 표시** 확인란의 선택을 취소합니다.

1. 컨트롤에 대해 **웹** 옵션을 선택합니다. 보강 컨트롤의 경우 **enrichmentType** 필드를 구성하여 표시하고자 하는 강화 유형을 선택합니다. 각 보강 유형에 대해 별도의 보강 컨트롤을 추가합니다.

1. **저장** 과 **게시** 를 선택하여 업데이트된 연락처 양식을 게시합니다.

1. 게시된 연락처 양식으로 이동합니다. 새로 추가된 컨트롤이 표시됩니다. 처음 사용할 때 로그인해야 할 수도 있습니다.

1. 사용자 지정 컨트롤에 표시할 내용을 사용자 지정하려면 오른쪽 상단에서 편집 단추를 선택합니다.

## <a name="upgrade-customer-card-add-in"></a>고객 카드 추가 기능 업그레이드
고객 카드 추가 기능은 자동으로 업그레이드되지 않습니다. 최신 버전으로 업그레이드하려면 추가 기능이 설치된 Dynamics 365 앱에서 이 절차를 따르십시오.

1. Dynamics 365 앱에서 **설정** > **사용자 지정** 으로 이동하고 **솔루션** 을 선택합니다.

1. 추가 기능 테이블에서 **CustomerInsightsCustomerCard** 를 찾아 행을 선택합니다.

1. 작업 표시줄에서 **솔루션 업그레이드 적용** 을 선택합니다.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Dynamics 365 앱의 사용자 지정 영역에서 솔루션 업그레이드":::

1. 업그레이드 프로세스를 시작하면 업그레이드가 완료될 때까지 로딩 표시기가 나타납니다. 최신 버전이 없으면 업그레이드 시 오류 메시지가 표시됩니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]