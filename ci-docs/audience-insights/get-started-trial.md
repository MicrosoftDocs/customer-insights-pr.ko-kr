---
title: Customer Insights 평가판 생성 및 구성
description: Dynamics 365 Customer Insights에 대한 평가판 구독을 받고 구성하는 단계입니다.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 3a235e924395a606b9332de3d205289288a597a9
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558831"
---
# <a name="set-up-a-trial-environment"></a>평가판 환경 설정 

Dynamics 365 Customer Insights 평가판을 통해 주요 기능을 검토하고 다양한 기능에 대해 자세히 알아볼 수 있습니다. 평가판 구독은 만료 후 삭제됩니다. 평가판 환경은 평가판 환경의 관리자가 되는 개별 사용자가 만듭니다. 더 많은 사용자를 평가판에 초대하고 다양한 기능을 구성할 수 있습니다.

## <a name="create-a-trial-environment"></a>평가판 환경 만들기

[평가판 등록 페이지 ](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights)에서 평가판에 가입할 수 있습니다. 

1. **무료 평가판 등록** 옵션을 선택하고 **지금 등록하기** 를 선택하세요.

1. 직장 또는 학교 이메일 주소를 제공하고 추가 세부 정보 입력 후 **시작** 을 선택하십시오.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="평가판 인스턴스에 등록하는 대화 상자":::

1. 사용 약관을 검토하고 **계속** 을 선택하여 확인합니다.

1. 새 환경을 위한 **이름** 을 제공합니다. 

1. 환경 **유형** 을 **평가판** 으로 설정합니다.

1. **산업 데모 선택** 필드에서 산업별 데이터 집합을 옵션으로 선택할 수 있습니다. 또한 나중에 [산업 데모로 변경](#use-industry-specific-demo-data-sets-in-audience-insights) 하고 기본 데이터 집합으로 시작할 수 있습니다.

1. 당신의 환경 **지역** 을 선택하세요.

1. 선택적으로, Dynamics 365 조직의 관리자인 경우: **고급 설정** 을 선택하고 조직의 URL을 제공하여 고객 이탈 예측과 같은 예측 기능을 사용합니다. 

1. **만들기** 를 선택합니다. 

환경 설정이 완료되는 데 몇 분이 소요됩니다. 완료되면 위 단계에서 선택한 데모 환경 또는 산업 데모로 리디렉션됩니다. 이제 읽기 전용 데모 데이터로 앱을 탐색할 수 있습니다. 자신의 데이터를 환경에 추가하려면 [자체 환경에서 시나리오별 데모 데이터 생성](#create-scenario-specific-demo-data-in-your-own-environment)을 참조하십시오.

:::image type="content" source="media/trial-environment.png" alt-text="새로 생성된 평가판 환경의 스크린샷.":::

## <a name="use-industry-specific-demo-data-sets-in-audience-insights"></a>대상 그룹 인사이트에서 산업별 데모 데이터 집합 사용

실제 데이터 소스를 연결하는 것은 Customer Insights의 기능을 사용하는 데 있어 중요한 단계 중 하나입니다. 자신의 데이터를 방해하지 않고 기능을 사용해 보려면 산업별 데모 데이터를 선택적으로 사용할 수 있습니다. 다음 산업에 사용할 수 있는 몇 가지 데모 데이터 집합이 있습니다. 

-   자동차
-   은행업
-   소비자 상품
-   정부 기관용
-   의료
-   접객
-   보험
-   제조
-   전문 서비스
-   소매

### <a name="see-industry-specific-demo-data-in-trials"></a>평가판에서 산업별 데모 데이터 보기

특정 산업 또는 시나리오에 맞게 조정된 읽기 전용 버전의 Customer Insights의 경우 데모 환경에서 시작하십시오. 
 
1.  대상 그룹 인사이트의 환경 선택기에서 **데모** 환경을 선택합니다.

2.  **홈** 의 업계 데모 선택 드롭다운 메뉴에서 옵션을 선택합니다.

:::image type="content" source="media/trial-select-industry-demo.png" alt-text="평가판 환경을 위한 산업을 선택하십시오.":::

### <a name="create-scenario-specific-demo-data-in-your-own-environment"></a>자체 환경에서 시나리오별 데모 데이터 생성

관리자는 앱 헤더에서 환경 선택기를 선택하여 새 환경을 만듭니다. 새 환경에서는 고유한 데이터 소스를 구성하고 요구 사항에 따라 앱을 설정할 수 있습니다. 

1.  대상 그룹 인사이트에서 **데이터** > **데이터 원본** 으로 이동합니다.

2.  자신의 데이터 원본을 가져오려면 [데이터 수집 가이드](data-sources.md)로 이동합니다.     
   데이터 수집을 시도할 수 있는 샘플 데이터 작업을 선호하는 경우 사용자 환경에서 업계 데모 데이터를 수집할 수 있습니다. **데이터허브에서 가져오기** 옵션을 선택하고 아래 단계를 수행합니다.

3.  귀하의 시나리오에 맞는 산업 카드를 선택하십시오. 

4.  데이터 원본의 제안된 이름을 검토하고 선택적으로 업데이트합니다. 

5.  **다음** 을 선택하여 샘플 데이터를 수집합니다. 

이제 수집된 데이터를 사용하여 시나리오에 맞게 Customer Insights를 조정할 수 있습니다. 수집된 데모 데이터와 관련된 환경을 보려면 환경 선택기에서 **<Industry> 데모** 옵션을 선택하세요.

## <a name="limitations-in-trials"></a>평가판의 제한 사항

- 평가판은 기본적으로 30일 동안 활성화됩니다. 그러나 23일 후에 평가판에 로그인하면 연장할 수 있습니다.
- 평가판 중에는 자체 Azure Data Lake Storage 계정을 사용하여 출력 데이터를 저장할 수 없습니다. 그러나 Data Lake Storage 계정에서 데이터를 수집할 수 있습니다.
- Customer Insights 평가판을 시작할 때 자동으로 프로비저닝되는 Dataverse 환경에 최대 3GB의 데이터를 저장할 수 있습니다.

## <a name="copy-data-from-a-trial-to-a-paid-subscription"></a>평가판에서 유료 구독으로 데이터 복사

일반적으로 Customer Insights의 유료 버전으로 업그레이드할 때 자신의 데이터로 새로 시작하는 것이 좋습니다. 

선택적으로 Customer Insights를 구매하는 경우 평가판 환경에서 데이터를 복사할 수 있습니다. 평가판 환경에서 유료 환경으로 설정을 마이그레이션하려면 Customer Insights 평가판의 관리자이자 Microsoft 365 테넌트의 전역 관리자이거나 조직의 Dynamics 365 관리자여야 합니다. 

Customer Insights의 유료 인스턴스에 처음 로그인하면 새 환경을 생성하라는 메시지가 표시됩니다. 이 프로세스에서 기존 환경에서 구성을 복사하고 대부분의 설정을 마이그레이션하도록 선택할 수 있습니다. 위에서 언급한 권한이 있는 경우 평가판 환경이 이 목록에 표시됩니다. 자세한 내용은 [환경 구성 복사](manage-environments.md#copy-the-environment-configuration)를 참조하십시오.

## <a name="next-steps"></a>다음 단계

Customer Insights 구성을 시작하는 데 도움이 되는 다음 문서를 검토하십시오. 

- [더 많은 사용자 추가 및 권한 할당](permissions.md).
- [데이터 원본](data-sources.md)을 수집하고 [데이터 통합 프로세스](data-unification.md)를 통해 실행하여 [통합 고객 프로필](customer-profiles.md)을 가져옵니다.
- [통합된 고객 프로필 보강](enrichment-hub.md) 또는 [예측 모델 실행](predictions-overview.md).
- [세그먼트](segments.md)를 만들어 고객을 그룹화하고 [측정](measures.md) 검토 KPI를 만듭니다.
- [연결](connections.md) 및 [내보내기](export-destinations.md)를 설정하여 다른 응용 프로그램에서 데이터의 하위 집합을 처리합니다.
