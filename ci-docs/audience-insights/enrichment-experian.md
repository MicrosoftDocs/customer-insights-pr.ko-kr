---
title: 타사 보강 Experian으로 보강
description: Experian 타사 보강에 대한 일반 정보입니다.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668820"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>자세한 내용은 Experian의 인구 통계로 고객 프로필 보강을 참고하세요 (미리보기)

Experian은 소비자 및 기업 신용보고 및 마케팅 서비스 분야의 글로벌 리더입니다. Experian의 데이터 보강 서비스를 사용하면 가구 규모, 소득 등과 같은 인구 통계 데이터로 고객 프로필을 강화하여 고객에 대한 더 깊은 이해를 구축할 수 있습니다.

## <a name="prerequisites"></a>필수 구성 요소

Experian 구성을 위해 다음 전제 조건이 충족되어야 합니다.

- Experian 구독이 활성화 상태입니다. 구독을 받으려면 직접 [Experian에 문의](https://www.experian.com/marketing-services/contact)합니다. [Experian데이터 보강에 대한 자세한 정보](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).
- Experian에서 생성한 SSH 사용 보안 전송 (ST) 계정의 사용자 ID, 당사자 ID 및 모델 번호가 있습니다.
- 대상 그룹 인사이트의 [관리자](permissions.md#administrator) 권한이 있어야 합니다.

## <a name="configuration"></a>구성

1. **데이터** > **보강** 으로 이동 후, **발견하기** 탭을 선택합니다.

1. Experian 타일에서 **내 데이터 강화** 를 선택합니다.

   > [!div class="mx-imgBorder"]
   > ![Experian 타일](media/experian-tile.png "Experian 타일")

1. **시작하기** 를 선택하고 Experian Secure Transport 계정의 사용자 ID, 당사자 ID 및 모델 번호를 입력하십시오. **동의함** 확인란을 선택하여 **데이터 개인 정보 및 규정 준수** 에 대한 동의를 검토하고 제공합니다. **적용** 을 선택하고 모든 입력을 확인하십시오.

## <a name="map-your-fields"></a>필드 매핑

1. **데이터 추가** 를 선택하고 신원 확인을 위해 Experian에 전송할 **이름과 주소**, **이메일** 또는 **전화** 중에 키 식별자를 선택하십시오.

   > [!TIP]
   > Experian에 전송된 키 식별자 속성이 많을수록 일치율이 높아질 수 있습니다.

1. **다음** 을 선택하고 선택한 키 식별자 필드에 대해 통합 고객 엔터티의 해당 속성을 매핑합니다.

1. **속성 추가** 를 선택해 Experian에 보내려는 추가 속성을 매핑합니다.

1.  **저장** 필드를 선택하여 매핑을 완료합니다.

   > [!div class="mx-imgBorder"]
   > ![Experian 필드 매핑](media/experian-field-mapping.png "Experian 필드 매핑")

## <a name="enrichment-results"></a>보강 결과

강화 프로세스를 시작하려면 명령 모음에서.**실행** 을 선택하십시오. [예약된 새로 고침](system.md#schedule-tab)으로 시스템이 자동으로 보강을 실행하도록 할 수도 있습니다. 처리 시간은 고객 데이터의 크기와 Experian에서 계정에 대해 설정한 보강 프로세스에 따라 다릅니다.

보강 프로세스가 완료되면 **내 보강** 아래에서 새로 보강 된 고객 프로필 데이터를 검토 할 수 있습니다. 또한 마지막 업데이트 시간과 강화 된 프로필 수를 확인할 수 있습니다.

**보강된 데이터 보기** 를 선택하여 각 보강된 프로필의 상세 보기에 액세스할 수 있습니다 .

## <a name="next-steps"></a>다음 단계

보강된 고객 데이터를 바탕으로 구축합니다. [세그먼트](segments.md)를 만들고, [측정](measures.md)하고, 또한 [데이터를 내보내](export-destinations.md) 고객에게 맞춤형 경험을 제공합니다.

## <a name="data-privacy-and-compliance"></a>데이터 프라이버시 및 규정 준수

Dynamics 365 Customer Insights를 사용하여 Experian으로 데이터를 전송하는 경우 Dynamics 365 Customer Insights규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다. Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 Experian이 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다. 자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.
Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 보강을 언제든지 제거할 수 있습니다.
