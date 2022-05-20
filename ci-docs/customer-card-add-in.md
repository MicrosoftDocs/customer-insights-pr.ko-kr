---
title: Dynamics 365 앱용 고객 카드 추가 앱(비디오 포함)
description: 이 추가 기능을 사용하여 Dynamics 365 앱의 Customer Insights에서 고객 프로필 데이터를 표시합니다.
ms.date: 02/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-search-filter
- ci-customer-card
- customerInsights
ms.openlocfilehash: 8508880bb3274bb491a314a043a5222d4d381073
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755644"
---
# <a name="customer-card-add-in-preview"></a>고객 카드 추가 기능(미리 보기)

Dynamics 365 앱에서 직접 고객에 대한 모든 측면 보기를 확인하세요. 지원되는 Dynamics 365 앱에 설치된 고객 카드 추가 기능을 사용하여 고객 프로필 필드, 인사이트 및 활동 타임라인을 표시하도록 선택할 수 있습니다. 추가 기능은 연결된 Dynamics 365 앱의 데이터에 영향을 주지 않고 Customer Insights에서 데이터를 검색합니다.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>필수 조건

- 추가 기능은 Sales 또는 Customer Service, 버전 9.0 이상과 같은 Dynamics 365 모델 기반 앱에서만 작동합니다.
- Dynamics 365 데이터를 Customer Insights 고객 프로필에 매핑하려면 [Microsoft Dataverse 커넥터를 사용하여 Dynamics 365 앱에서 수집](connect-power-query.md)하는 것이 좋습니다. 다른 방법으로 Dynamics 365 연락처(또는 계정)를 수집하려면, `contactid`(또는 `accountid`) 필드가 [데이터 통합 프로세스 구상 단계에 있는 해당 데이터 소스의 기본 키로 설정되었는지 확인해야 합니다](map-entities.md#select-primary-key-and-semantic-type-for-attributes).
- 고객 카드 추가 기능의 모든 Dynamics 365 사용자는 데이터를 보려면 Customer Insights에서 [사용자로 추가](permissions.md)해야 합니다.
- 데이터 조회가 작동하려면 Customer Insights의 [구성된 검색 및 필터 기능](search-filter-index.md)이 필요합니다.
- 각 추가 기능 컨트롤은 Customer Insights의 특정 데이터에 의존합니다. 일부 데이터 및 컨트롤은 특정 유형의 환경에서만 사용할 수 있습니다. 추가 기능 구성은 선택한 환경 유형으로 인해 제어를 사용할 수 없는 경우 알려줍니다. [환경 사용 사례](work-with-business-accounts.md)에 대해 자세히 알아보세요.
  - **측정 제어**: 고객 특성 유형의 [구성된 측정값](measures.md)이 필요합니다.
  - **지능형 제어**: [예측 또는 맞춤 모델](predictions-overview.md)을 사용하여 생성된 데이터가 필요합니다.
  - **고객 세부 정보 제어**: 프로필의 모든 필드는 통합 고객 프로필에서 사용할 수 있습니다.
  - **보강 제어**: 활성 [보강](enrichment-hub.md)이 고객 프로필에 적용되어야 합니다. 카드 추가 기능은 다음 강화를 지원합니다. Microsfot에서 제공한 [브랜드](enrichment-microsoft.md), Microsfot에서 제공한 [관심사](enrichment-microsoft.md), Microsfot에서 제공한 [사무실 참여 데이터](enrichment-office.md).
  - **연락처 제어**: 유형 연락처의 의미 체계 엔티티 정의가 필요합니다.
  - **시간 표시줄 제어**: [구성된 활동](activities.md)이 필요합니다.

## <a name="install-the-customer-card-add-in"></a>고객 카드 추가 기능 설치

고객 카드 추가 기능은 Dynamics 365의 Customer Engagement 앱을 위한 솔루션입니다. 솔루션을 설치하려면 AppSource로 이동하고 **Dynamics 고객 카드** 를 검색합니다. [AppSource에서 고객 카드 추가 기능](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview)을 선택하고 **지금 가져 오기** 를 선택합니다.

솔루션을 설치하려면 Dynamics 365 앱에 대한 관리자 자격 증명으로 로그인해야 할 수 있습니다. 솔루션을 환경에 설치하는 데 시간이 걸릴 수 있습니다.

## <a name="configure-the-customer-card-add-in"></a>고객 카드 추가 기능 구성

1. 관리자로서 Dynamics 365에서 **설정** 섹션으로 이동하고 **솔루션** 을 선택합니다.

1. **Dynamics 365 Customer Insights 고객 카드 추가 기능(미리 보기)** 솔루션에 대한 **표시 이름** 링크를 선택합니다.

   > [!div class="mx-imgBorder"]
   > ![표시 이름 선택.](media/select-display-name.png "표시 이름을 선택합니다.")

1. **로그인** 을 선택하고 Customer Insights를 구성하는 데 사용하는 관리자 계정의 자격 증명을 입력합니다.

   > [!NOTE]
   > **로그인** 단추를 선택할 때 브라우저 팝업 차단 기능이 인증 창을 차단하지 않는지 확인하십시오.

1. 데이터를 가져오려는 Customer Insights 환경을 선택합니다.

1. Dynamics 365 앱의 레코드에 대한 필드 매핑을 정의합니다. Customer Insights의 데이터에 따라 다음 옵션을 매핑하도록 선택할 수 있습니다.
   - 연락처와 매핑하려면 연락처 엔터티의 ID와 일치하는 고객 엔터티의 필드를 선택합니다.
   - 계정과 매핑하려면 연락처 엔터티의 ID와 일치하는 계정 엔터티의 필드를 선택합니다.

   > [!div class="mx-imgBorder"]
   > ![연락처 ID 필드.](media/contact-id-field.png "연락처 ID 필드입니다.")

1. **구성 저장** 을 선택하여 설정을 저장합니다.

1. 그런 다음 사용자가 고객 카드를 사용자 지정하고 볼 수 있도록 Dynamics 365에서 보안 역할을 할당해야 합니다. Dynamics 365에서 **설정** > **보안** > **사용자** 로 이동합니다. 사용자 역할을 편집할 사용자를 선택하고 **역할 관리** 를 선택합니다.

1. 전체 조직에 대해 카드에 표시되는 콘텐츠를 사용자 지정할 사용자에게 **Customer Insights 카드 사용자 지정자** 역할을 할당합니다.

## <a name="add-customer-card-controls-to-forms"></a>양식에 고객 카드 제어 추가

시나리오에 따라 **연락처** 양식 또는 **계정** 양식에 컨트롤을 추가하도록 선택할 수 있습니다. Customer Insights 환경이 비즈니스 계정용인 경우 계정 양식에 컨트롤을 추가하는 것이 좋습니다. 이 경우 아래 단계에서 "연락처"를 "계정"으로 바꿉니다.

1. 연락처 양식에 고객 카드 컨트롤을 추가하려면 Dynamics 365에서에서 **설정** > **사용자 지정** 으로 이동합니다.

1. **시스템 사용자 지정** 을 선택합니다.

1. **연락처** 엔터티를 찾아 확장한 다음 **양식** 을 선택합니다.

1. 고객 카드 컨트롤을 추가할 연락처 양식을 선택합니다.

    > [!div class="mx-imgBorder"]
    > ![연락처 양식 선택.](media/contact-active-forms.png "연락처 양식을 선택합니다.")

1. 양식 편집기에서 컨트롤을 추가하려면 **필드 탐색기** 에서 컨트롤을 배치할 위치로 필드를 드래그합니다.

1. 방금 추가한 양식에서 필드를 선택한 다음 **속성 변경** 을 선택합니다.

1. **컨트롤** 탭으로 이동하여 **컨트롤 추가** 를 선택합니다. 사용 가능한 사용자 지정 컨트롤 중 하나를 선택하고 **추가** 를 선택합니다.

1. **필드 속성** 대화 상자에서 **양식에 레이블 표시** 확인란의 선택을 취소합니다.

1. 컨트롤에 대해 **웹** 옵션을 선택합니다. 보강 컨트롤의 경우 **enrichmentType** 필드를 구성하여 표시하고자 하는 강화 유형을 선택합니다. 각 보강 유형에 대해 별도의 보강 컨트롤을 추가합니다.

1. **저장** 과 **게시** 를 선택하여 업데이트된 연락처 양식을 게시합니다.

1. 게시된 연락처 양식으로 이동합니다. 새로 추가된 컨트롤이 표시됩니다. 처음 사용할 때 로그인해야 할 수도 있습니다.

1. 사용자 지정 컨트롤에 표시할 내용을 사용자 지정하려면 오른쪽 상단에서 편집 단추를 선택합니다.

## <a name="upgrade-customer-card-add-in"></a>고객 카드 추가 기능 업그레이드

고객 카드 추가 기능은 자동으로 업그레이드되지 않습니다. 최신 버전으로 업그레이드하려면 추가 기능이 설치된 Dynamics 365 앱에서 다음 단계를 따르세요.

1. Dynamics 365 앱에서 **설정** > **사용자 지정** 으로 이동하고 **솔루션** 을 선택합니다.

1. 추가 기능 테이블에서 **CustomerInsightsCustomerCard** 를 찾아 행을 선택합니다.

1. 작업 표시줄에서 **솔루션 업그레이드 적용** 을 선택합니다.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Dynamics 365 앱의 사용자 지정 영역에서 솔루션 업그레이드.":::

1. 업그레이드 프로세스를 시작하면 업그레이드가 완료될 때까지 로딩 표시기가 나타납니다. 최신 버전이 없으면 업그레이드 시 오류 메시지가 표시됩니다.

## <a name="troubleshooting"></a>문제 해결

### <a name="controls-from-customer-card-add-in-dont-find-data"></a>고객 카드 추가 기능의 컨트롤에서 데이터를 찾을 수 없음

**문제점:**

올바르게 구성된 ID 필드가 있더라도 컨트롤은 고객에 대한 데이터를 찾을 수 없습니다.  

**해결 방법:**

1. 다음 지침에 따라 카드 추가 기능을 구성했는지 확인합니다. [고객 카드 추가 기능 구성](#configure-the-customer-card-add-in)

1. 데이터 수집 구성을 검토합니다. 연락처 ID GUID가 포함된 Dynamics 365 시스템의 데이터 원본을 편집합니다. Power Query 편집기에 연락처 ID GUID가 대문자로 표시된 경우 다음 단계를 시도합니다.
    1. 데이터 원본를 편집하여 Power Query 편집자에서 데이터 원본을 엽니다.
    1. 연락처 ID 열을 선택합니다.
    1. 헤더 표시줄에서 **변환** 을 선택하여 사용 가능한 작업을 확인합니다.
    1. **소문자** 를 선택합니다. 테이블의 GUID가 이제 소문자인지 확인합니다.
    1. 데이터 원본을 저장합니다.
    1. 데이터 수집, 통합 및 다운스트림 프로세스를 실행하여 변경 사항을 GUID에 전파합니다.

시스템이 전체 새로 고침을 완료한 후 Customer Card Add-in 컨트롤에 예상 데이터가 표시되어야 합니다.

[!INCLUDE [footer-include](includes/footer-banner.md)]
