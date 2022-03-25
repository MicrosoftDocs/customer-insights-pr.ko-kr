---
title: 제3자 보강을 통한 보강 Experian
description: Experian 제3자 보강에 대한 일반 정보.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: efa26fa82a950063e074a4ab930ed95383c55334
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376700"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Experian 인구 통계로 고객 프로필을 보강하십시오.(프리뷰)

Experian은 소비자 및 기업 신용보고 및 마케팅 서비스 분야의 글로벌 리더입니다. Experian의 데이터 보강 서비스를 사용하면 가구 규모, 소득 등과 같은 인구 통계학적 데이터로 고객 프로필을 보강하여 고객에 대한 더 깊은 이해를 구축할 수 있습니다.

## <a name="prerequisites"></a>필수 조건

Experian을 구성하려면 다음 전제 조건이 충족되어야 합니다.

- 활성 Experian 구독이 있어야 합니다. 구독하려면 [Experian에 직접 연락](https://www.experian.com/marketing-services/contact)하세요. [Experian 데이터 보강에 대해 자세히 알아보기](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- 관리자가 Experian 연결을 이미 *구성했거나* 귀하가 [관리자](permissions.md#admin) 권한을 가지고 있음. 또한 Experian에서 생성된 SSH 사용 보안 전송(ST) 계정에 대한 사용자 ID, 당사자 ID 및 모델 번호가 필요합니다.

## <a name="supported-countriesregions"></a>지원되는 국가/지역

현재 미국에서만 고객 프로필 보강을 지원합니다.

## <a name="configure-the-enrichment"></a>보강 구성

1. **데이터** > **보강** 으로 이동 후, **발견하기** 탭을 선택합니다.

1. Experian 타일에서 **내 데이터 보강** 을 선택하세요.

   > [!div class="mx-imgBorder"]
   > ![Experian 타일.](media/experian-tile.png "Experian tile")
   > 

1. 드롭다운 목록에서 [연결](connections.md)을 선택하십시오. 사용 가능한 연결이 없으면 관리자에게 문의하십시오. 관리자인 경우 **연결 추가** 를 선택하고 드롭다운 목록에서 Experian을 선택하여 연결을 만들 수 있습니다. 

1. **Experian 연결** 을 선택하여 연결 선택을 확인합니다.

1.  **다음** 을 선택하고 Experian 인구 통계 데이터로 보강할 **고객 데이터 집합** 을 선택합니다. **고객** 엔터티를 선택하여 모든 고객 프로필을 보강하거나 세그먼트 엔터티를 선택하여 해당 세그먼트에 포함된 고객 프로필만 보강할 수 있습니다.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="고객 데이터 집합 선택 시 스크린샷입니다.":::

1. **다음** 을 선택하고 통합 프로필에서 Experian의 인구 통계 데이터와 일치하는 것을 찾는 데 사용해야 하는 필드 유형을 정의합니다. **이름과 주소**, **전화** 또는 **이메일** 중 하나 이상이 필요합니다. 더 높은 일치 정확도를 위해 최대 2개의 다른 필드를 추가할 수 있습니다. 이 선택은 다음 단계에서 액세스할 수 있는 매핑 필드에 영향을 줍니다.

    > [!TIP]
    > Experian에 더 많은 키 식별자 특성을 전송하면 더 높은 일치율을 얻을 수 있습니다.

1. 필드 매핑을 시작하려면 **다음** 을 선택합니다.

1. 통합 프로필에서 Experian의 인구 통계 데이터와 일치하는 것을 찾는 데 사용해야 하는 필드 유형을 정의합니다. 표시된 필드는 필수입니다.

1. 보강 이름과 출력 엔터티 이름을 제공합니다.

1. 선택 사항을 검토 한 후 **보강 저장** 을 선택합니다.

## <a name="configure-the-connection-for-experian"></a>Experian 연결 구성 

연결을 구성하려면 관리자여야 합니다. 보강을 구성할 때 **연결 추가** 를 *선택하거나* **관리자** > **연결** 로 이동하여 Experian 타일에서 **설정** 을 선택합니다.

1. **시작** 을 선택합니다.

1. **표시 이름** 상자에 연결 이름을 입력합니다.

1. Experian 보안 전송 계정에 대한 유효한 사용자 ID, 당사자 ID 및 모델 번호를 입력하십시오.

1. **데이터 개인 정보 보호 및 규정 준수** 를 검토하고 **동의함** 을 선택하여 동의를 제공합니다.

1. **확인** 을 선택하여 구성을 확인합니다.

1. 확인을 완료한 후 **저장** 을 선택합니다.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian연결 구성 창.":::

## <a name="enrichment-results"></a>보강 결과

강화 프로세스를 시작하려면 명령 모음에서.**실행** 을 선택하십시오. [예약된 새로 고침](system.md#schedule-tab)으로 시스템이 자동으로 보강을 실행하도록 할 수도 있습니다. 처리 시간은 고객 데이터의 크기와 Experian에서 계정에 대해 설정한 보강 프로세스에 따라 다릅니다.

보강 프로세스가 완료되면 **내 보강** 아래에서 새로 보강 된 고객 프로필 데이터를 검토 할 수 있습니다. 또한 마지막 업데이트 시간과 강화 된 프로필 수를 확인할 수 있습니다.

**보강된 데이터 보기** 를 선택하여 각 보강된 프로필의 상세 보기에 액세스할 수 있습니다 .

## <a name="next-steps"></a>다음 단계

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>데이터 프라이버시 및 규정 준수

Experian에 데이터를 전송하기 위해 Dynamics 365 Customer Insights를 활성화할 때 개인 데이터와 같이 잠재적으로 민감한 데이터를 비롯하여 Dynamics 365 Customer Insights의 준수 경계를 벗어난 데이터 전송을 허용합니다. Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 귀하는 Experian이 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 해야 합니다. 자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.
Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 보강을 언제든지 제거할 수 있습니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
