---
title: Dynamics 365 Customer Insights 시작
description: Customer Insights의 개요는 리소스를 빠르게 시작하는 데 도움이 됩니다.
ms.reviewer: v-wendysmith
ms.author: mhart
author: m-hartmann
ms.date: 04/12/2022
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 1c925110f40319df77940d1c32f24a99504d6ec6
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011987"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights 시작

Customer Insights는 고객에 대한 더 깊은 이해를 구축하는 데 도움이 될 수 있습니다. 다양한 트랜잭션, 행동 및 관찰 소스의 데이터를 연결하여 360도 고객 보기를 만듭니다. 이러한 인사이트를 사용하여 고객 중심 경험과 프로세스를 추진하십시오. 고객 데이터를 통합하고 이해하며 지능형 인사이트 및 행동에 이를 활용할 수 있습니다.

## <a name="step-1-create-an-environment"></a>1단계: 환경 만들기

먼저, 작업할 수 있는 환경을 만드십시오. 조직에서 이미 라이선스를 구입한 경우 [환경 만들기](create-environment.md)를 참조하세요. Customer Insights 평가판을 시작하려면 [평가판 환경 설정](trial-signup.md)을 참조하십시오.

## <a name="step-2-explore-customer-insights"></a>2단계: Customer Insights 살펴보기

Customer Insights에 처음 로그인하면 설정을 구성하고 제품을 탐색하십시오.

1. Microsoft Azure Active Directory(AAD) 사용자 계정을 사용하여 [Customer Insights에 로그인](https://home.ci.ai.dynamics.com)합니다.

1. 환경을 변경하여 데모 데이터를 확인하고 [Customer Insights를 탐색](home.md)하십시오.

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>3단계: 데이터 수집, 통합 및 관계 설정

통합 프로필은 인사이트를 얻고 데이터에 대한 작업을 수행하기 위한 기반입니다. 다양한 소스에서 데이터를 가져와 데이터 통합 프로세스를 실행하여 통합 프로필을 결합합니다. 수집된 엔터티 간에 관계를 지정하고 보강 기능을 사용하여 프로필에 정보를 추가합니다.

1. 여러 옵션에서 데이터 원본을 만들어 데이터를 수집합니다. [Azure Data Lake Storage(Common Data Model 포함)](connect-common-data-model.md), [Azure Synapse Analytics](connect-synapse.md), [Microsoft Dataverse](connect-dataverse-managed-lake.md) 또는 [Power Query 커넥터](connect-power-query.md) 중에서 선택합니다.

1. [원본 필드](map-entities.md)를 식별하고, [중복](remove-duplicates.md), [일치 조건](match-entities.md), [필드 통합](merge-entities.md)을 제거하여 [데이터 통합 프로세스](data-unification.md)를 실행합니다.

1. [시스템이 생성하는 엔터티](entities.md)에 익숙해지고 [수집된 엔터티 간의 관계](relationships.md)를 만듭니다.

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>4단계: 예측, 활동 및 측정으로 통합 프로필 향상

통합 프로필을 설정하면 데이터를 향상하고 제공하는 정보를 더욱 늘릴 수 있습니다.

1. 확장되는 강화 공급자 라이브러리에서 선택하여 [고객 데이터를 강화](enrichment-hub.md)합니다.

1. [즉시 사용 가능한 모델](predictions-overview.md)을 사용하여 이탈 가능성 또는 예상 수익을 예측합니다.

1. 수집된 데이터를 기반으로 [활동을 구성](activities.md)하고 시간순으로 고객과의 상호 작용을 시각화합니다.

1. [측정을 구축](measures.md)하여 비즈니스 목표와 KPI를 측정합니다.

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>5단계: 다양한 내보내기 옵션을 통해 세그먼트 생성 및 데이터 활성화

이제 데이터가 완성되었고 고객에 대한 광범위한 정보가 포함되었으므로 해당 데이터에 대해 조치를 취할 방법을 찾으십시오.

1. 고객 기반의 하위 집합인 [세그먼트를 만들어](segments.md) 작업이 대상 고객과 관련이 있는지 확인하십시오.

1. 고객 데이터를 사용할 수 있는 [내보내기 옵션](export-destinations.md)의 확장 카탈로그를 찾아보십시오. 예를 들어, 데이터를 사용하여 프로모션을 관리하고 디지털 마케팅을 활용할 수 있습니다.

1. 예를 들어 [고객 카드 추가 기능](customer-card-add-in.md)이 있는 다른 Dynamics 365 앱에 대한 통합 옵션을 검토하십시오.  


[!INCLUDE [footer-include](includes/footer-banner.md)]
