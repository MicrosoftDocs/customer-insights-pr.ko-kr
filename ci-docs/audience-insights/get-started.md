---
title: Dynamics 365 Customer Insights에서 대상 그룹 인사이트 기능 시작
description: 대상 그룹 인사이트 개요는 리소스를 빠르게 시작하는 데 도움이 됩니다.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: aaaf1848df175469d8af07754ac153b777781ffb
ms.sourcegitcommit: 971716c761871cee390519cacef617dac21ecd60
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466585"
---
# <a name="get-started-with-dynamics-365-customer-insights-audience-insights-capability"></a>Dynamics 365 Customer Insights 대상 그룹 인사이트 기능 시작하기

대상 그룹 인사이트는 고객을 더 깊이 이해하는 데 도움이 됩니다. 다양한 트랜잭션, 행동 및 관찰 소스의 데이터를 연결하여 360도 고객 보기를 만듭니다. 이러한 인사이트를 사용하여 고객 중심 경험과 프로세스를 추진하십시오. 고객 데이터를 통합하고 이해하며 지능형 인사이트 및 행동에 이를 활용할 수 있습니다.

## <a name="step-1-create-an-environment"></a>1단계: 환경 만들기

시작하려면 먼저 작업할 환경을 만들어야 합니다. 조직에서 이미 라이선스를 구입한 경우 [유료 구독 시작하기](get-started-paid.md)를 참조하십시오. 대상 그룹 인사이트에 대한 평가판을 시작하려면 [평가판 환경 설정](get-started-trial.md)을 참조하십시오. 

## <a name="step-2-explore-audience-insights"></a>2단계: 대상 그룹 인사이트 살펴보기

대상 그룹 인사이트에 처음 로그인하면 설정을 구성하고 제품을 탐색할 수 있습니다.

1. Microsoft Azure Active Directory(AAD) 사용자 계정을 사용하여 [대상 그룹 인사이트에 로그인](https://home.ci.ai.dynamics.com)합니다.

1. [환경을 변경](manage-environments.md#switch-environments)하여 데모 데이터를 보고 [대상 그룹 인사이트를 탐색](home.md)하십시오.

##  <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>3단계: 데이터 수집, 통합 및 관계 설정

통합 프로필은 인사이트를 얻고 데이터에 대한 작업을 수행하기 위한 기반입니다. 다양한 소스에서 데이터를 가져와 데이터 통합 프로세스를 실행하여 통합 프로필을 결합합니다. 수집된 엔터티 사이에 관계를 지정하고 보강 기능을 사용하여 프로필에 정보를 추가합니다. 

1. 여러 옵션에서 데이터 원본을 만들어 데이터를 수집합니다. [파워 쿼리 커넥터](connect-power-query.md), [Common Data Model 폴더](connect-common-data-model.md) 또는 [Microsoft Dataverse](connect-common-data-service-lake.md) 중에서 선택합니다. 

1. [매핑](map-entities.md), [일치](match-entities.md) 및 [병합](merge-entities.md) 단계를 통해 [데이터 통합 프로세스](data-unification.md)를 실행합니다.

1. [시스템이 생성하는 엔터티](entities.md)에 익숙해지고 [수집된 엔터티 간의 관계](relationships.md)를 만듭니다.
    
## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>4단계: 예측, 활동 및 측정으로 통합 프로필 향상

통합 프로필을 설정하면 데이터를 향상하고 제공하는 정보를 더욱 늘릴 수 있습니다.

1. 확장되는 강화 공급자 라이브러리에서 선택하여 [고객 데이터를 강화](enrichment-hub.md)합니다.

1. [즉시 사용 가능한 모델](predictions-overview.md)을 사용하여 이탈 가능성 또는 예상 수익을 예측합니다.

1. 수집된 데이터를 기반으로 [활동을 구성](activities.md)하고 시간순으로 고객과의 상호 작용을 시각화합니다. 

1. [측정을 구축](measures.md)하여 비즈니스 목표와 KPI를 측정합니다.
 
## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>5단계: 다양한 내보내기 옵션을 통해 세그먼트 생성 및 데이터 활성화

이제 데이터가 완성되었고 고객에 대한 광범위한 정보가 포함되었으므로 해당 데이터에 대해 작업을 수행할 방법을 찾아야 합니다. 

1. 고객 기반의 하위 집합인 [세그먼트를 만들어](segments.md) 작업이 대상 고객과 관련이 있는지 확인하십시오.

1. 고객 데이터를 사용할 수 있는 [내보내기 옵션](export-destinations.md)의 확장 카탈로그를 찾아보십시오. 예를 들어, 데이터를 사용하여 프로모션을 관리하고 디지털 마케팅을 활용할 수 있습니다.

1. 예를 들어 [참여 인사이트에 직접 연결](../engagement-insights/integrate-audience-insights-engagement-insights.md) 또는 [고객 카드 추가 기능](customer-card-add-in.md)이 있는 다른 Dynamics 365 앱과의 통합 옵션을 검토합니다.  


[!INCLUDE[footer-include](../includes/footer-banner.md)]
