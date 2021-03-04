---
title: 대상 그룹 인사이트의 홈 페이지
description: 홈 페이지에서 앱 탐색을 시작합니다.
ms.date: 01/07/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7cc767f5d80b213a4c1bb5b2e8062bd44c15279b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477049"
---
# <a name="create-a-new-environment"></a>새 환경 만들기

## <a name="create-a-trial-environment"></a>평가판 환경 만들기

[평가판 등록 페이지 ](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights)에서 평가판에 가입할 수 있습니다. 

> [!NOTE]
> 평가판은 30일 후에 만료됩니다.

1. **무료 평가판 등록** 옵션을 선택하고 **지금 등록하기** 를 선택하세요.

1. 직장 또는 학교 이메일 주소를 제공하고, **다음** 을 선택해 자신에 대한 자세한 설명을 부탁드립니다.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="평가판 인스턴스에 등록하는 대화 상자":::

1. 새 환경을 위한 **이름** 을 제공합니다. 

1. 평가판 유형을 선택합니다.

1. 당신의 환경 **지역** 을 선택하세요.

1. 선택 사항으로, Dynamics 365 조직의 관리자의 경우: **고급 설정** 을 선택하고 고객 이탈과 같은 예측 기능을 사용하려면 조직의 URL을 제공하세요.

1. **만들기** 를 선택합니다. 

환경이 생성 된 후, 가상 데이터로 앱을 탐색 할 수있는 환경인 **데모** 를 확인하실 수 있습니다. 업계에 맞게 샘플 데이터를 변경할 수 있습니다. 헤더에서 **설정** 아이콘을 선택하고 **데모 설정** 을 선택하세요. 또한 시각적 테마를 변경할 수 있습니다. 

당신 [환경으로 전환](#switch-environments) 사용자 자신의 데이터로 작업하기 위해 등록 프로세스 중에 만들었습니다.

## <a name="create-a-new-production-or-sandbox-environment"></a>새 프로덕션 또는 샌드박스 환경을 생성합니다.

사용자 환경의 앱 헤더에서 **환경** 선택기를 선택하고 **새로 만들기** 를 선택합니다.

[평가판 환경 조성 ](#create-a-trial-environment)을 위해 다음 단계를 따르십시오. 기본적으로 데이터는 Customer Insights에서 관리하는 데이터 레이크에 저장됩니다. 자체 Azure Data Lake에 데이터를 저장하기 위해 **고급 설정** 을 선택할 때 추가 옵션이 제공됩니다.  계정 이름 및 계정 키를 제공하여 Azure Data Lake에 대한 연결을 설정합니다. 

> [!IMPORTANT]
> 데이터를 Azure Data Lake Storage에 저장하면 데이터가 해당 Azure 스토리지 계정에 적합한 지리적 위치에 전송되고 저장된다는 데 동의하게 됩니다. 이 지리적 위치는 Dynamics 365 Customer Insights에 데이터가 저장된 위치와 다를 수 있습니다. [Microsoft 보안 센터에서 자세히 알아보십시오.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>홈 페이지 탐색

다음 URL [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/)에서 [Dynamics 365 Customer Insights에서 대상 그룹 인사이트에 액세스](https://home.ci.ai.dynamics.com/) 할 수 있습니다.
**홈** 페이지에는 [매핑](map-entities.md), [일치](match-entities.md) 및 [병합](merge-entities.md) 단계를 완료 한 후 세그먼트, 측정값 및 보강 데이터(구성된 경우)의 개요가 표시됩니다.

> [!div class="mx-imgBorder"] 
> ![홈 페이지에 대한 통찰력](media/home-page-insights.png "홈 페이지에 대한 통찰력")

아래에 **최근 세그먼트**, 정의한 인구 통계, 행동 또는 거래 특성을 기반으로 고객 그룹이 표시됩니다. [세그먼트 생성](segments.md)을 사용하면 고객 기반을 그룹화하고 비즈니스 활동을 더 정확하게 타겟팅할 수 있습니다.

**최근 측정값** 은 사용자가 정의한 [핵심 성과 지표(KPI)](measures.md)가 있는 타일을 표시합니다. 예를 들면 고객이 이탈할 평균 가능성 또는 고객당 평균 온라인 지출입니다.

그만큼 **최근 강화** 섹션에는 최근 완료된 보강 실행의 결과가 나열됩니다. [보강](enrichment-hub.md)은 고객 기반에 대한 정보를 추가합니다. 예를 들어, 그들이 선호하는 관심사와 브랜드를 해석함으로써.

## <a name="switch-environments"></a>환경 전환

페이지 오른쪽 상단의 **환경** 컨트롤을 선택하여 환경을 변경합니다.

> [!div class="mx-imgBorder"] 
> ![환경 전환](media/home-page-environment-switcher.png "환경 전환")

관리자는 [여러 환경](manage-environments.md)을 만들고 관리할 수 있습니다. 예를 들어 조직이 국제적으로 운영되고 데이터와 통찰력을 다른 방식으로 분리해야 하는 경우 둘 이상의 환경을 유지하는 것이 유용할 수 있습니다.

## <a name="next-step"></a>다음 단계

홈페이지에서 자신의 통찰력을 보려면 먼저 고객 프로파일 구축을 위해 [데이터 원본 추가](data-sources.md)및 데이터 [통합](data-unification.md)을 수행해야 합니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]