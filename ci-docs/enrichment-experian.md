---
title: Experian 인구 통계로 고객 프로필을 보강하십시오.(프리뷰)
description: Experian 제3자 보강에 대한 일반 정보.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: a30e98b06ed07590ab95cae1d8db8023e49ff7f9
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053029"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Experian 인구 통계로 고객 프로필을 보강하십시오.(프리뷰)

Experian은 소비자 및 기업 신용보고 및 마케팅 서비스 분야의 글로벌 리더입니다. Experian의 데이터 보강 서비스를 사용하면 가구 규모, 소득 등과 같은 인구 통계학적 데이터로 고객 프로필을 보강하여 고객에 대한 더 깊은 이해를 구축할 수 있습니다.

## <a name="supported-countriesregions"></a>지원되는 국가/지역

현재 미국에서만 고객 프로필 보강을 지원합니다.

## <a name="prerequisites"></a>전제 조건

- 활성 Experian 구독입니다. 구독하려면 [Experian에 직접 연락](https://www.experian.com/marketing-services/contact)하세요. [Experian 데이터 보강에 대해 자세히 알아보기](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Experian [연결](connections.md)은 관리자가 [구성](#configure-the-connection-for-experian)합니다.

- Experian에서 생성한 SSH 사용 보안 전송(ST) 계정의 Experian 사용자 ID, 당사자 ID 및 모델 번호.

## <a name="configure-the-connection-for-experian"></a>Experian 연결 구성

Customer Insights의 [관리자](permissions.md#admin)여야 하며 Experian 사용자 ID, 당사자 ID 및 모델 번호가 있어야 합니다.

1. 강화를 구성할 때 **연결 추가** 를 선택하거나 **관리** > **연결** 로 이동하고 Experian 타일에서 **설정** 을 선택합니다.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian연결 구성 창.":::

1. 연결 이름과 Experian Secure Transport 계정의 유효한 사용자 ID, 당사자 ID 및 모델 번호를 입력합니다.

1. [데이터 개인 정보 보호 및 규정 준수](#data-privacy-and-compliance)를 검토하고 **동의함** 을 선택하여 동의를 제공합니다.

1. **확인** 을 선택하여 구성을 확인한 다음 **저장** 을 선택합니다.

### <a name="data-privacy-and-compliance"></a>데이터 프라이버시 및 규정 준수

Experian에 데이터를 전송하기 위해 Dynamics 365 Customer Insights를 활성화할 때 개인 데이터와 같이 잠재적으로 민감한 데이터를 비롯하여 Dynamics 365 Customer Insights의 준수 경계를 벗어난 데이터 전송을 허용합니다. Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 귀하는 Experian이 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 해야 합니다. 자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요. Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 보강을 언제든지 제거할 수 있습니다.

## <a name="configure-the-enrichment"></a>보강 구성

1. **데이터** > **보강** 으로 이동 후, **발견하기** 탭을 선택합니다.

1. Experian 타일의 **인구통계** 에서 **내 데이터 보강** 을 선택합니다.

   :::image type="content" source="media/experian-tile.png" alt-text="강화 개요 페이지의 Experian 타일입니다.":::

1. 개요를 검토한 후 **다음** 을 선택합니다.

1. 연결을 선택합니다. 관리자가 없는 경우 관리자에게 문의하세요.

1. **다음** 을 선택합니다.

1. **고객 데이터 세트** 를 선택하고 Experian에서 인구 통계 데이터로 보강하려는 프로필 또는 세그먼트를 선택합니다. *고객* 엔터티는 모든 고객 프로필을 강화하는 반면 세그먼트는 해당 세그먼트에 포함된 고객 프로필만 강화합니다.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="고객 데이터 집합 선택 시 스크린샷입니다.":::

1. Experian의 인구 통계 데이터를 일치시키는 데 사용할 통합 프로필의 필드 유형을 정의합니다. **이름과 주소**, **전화** 또는 **이메일** 중 하나 이상이 필요합니다. 더 높은 일치 정확도를 위해 기타 필드를 추가하세요. **다음** 을 선택합니다.

1. Experian의 인구통계학적 데이터에 필드를 매핑합니다.

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
