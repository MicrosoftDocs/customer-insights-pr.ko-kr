---
title: 주요 대상 그룹으로 비즈니스 계정 시작
description: Dynamics 365 Customer Insights의 주요 대상 고객인 비즈니스 계정에 대해 알아보세요.
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: 88882dc727c37262c9f204fbc8049abe17bd21a3
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353551"
---
# <a name="work-with-business-accounts-in-audience-insights"></a>대상 그룹 인사이트에서 비즈니스 계정 작업

Dynamics 365 Customer Insights의 대상 그룹 인사이트 기능을 사용하면 B-to-C(개별 고객) 및 B-to-B(비즈니스 계정)과 같은 다양한 주요 대상 그룹에 대해 환경을 구성할 수 있습니다. B-to-C 시나리오에서 데이터는 개인을 중심으로 합니다. B-to-B의 경우 주요 대상 그룹은 계정(조직 또는 회사)과 연락처입니다. 이 문서는 비즈니스 계정 환경을 시작하는 데 도움이 됩니다. 환경 초점에 따라 대상 그룹 인사이트의 기능 영역에 대한 차이점을 나열합니다. 차이점에 대한 자세한 내용은 기능 영역의 문서를 검토하세요. 

## <a name="create-an-environment-for-business-accounts"></a>비즈니스 계정을 위한 환경 만들기

관리자는 [기존 조직에 환경을 만들 수 있습니다](create-environment.md). 새 환경을 만드는 과정의 한 단계에서는 관리자에게 환경의 주요 대상 그룹을 묻습니다. 라이선스 구매 후 대상 그룹 인사이트의 초기 설정인 경우 가이드 경험이 첫 번째 환경 생성에 도움이 됩니다.

그런 다음 지원되는 모든 소스의 데이터 소스로 비즈니스 계정 및 관련 연락처에 대한 [데이터를 수집](data-sources.md)할 수 있습니다.

데이터를 통합한 후 관계 구성의 일부로 [계정 계층을 지정](relationships.md#set-up-account-hierarchies)합니다. 연락처 및 계정 엔터티를 연결하도록 [의미 체계 매핑을 구성](semantic-mappings.md)할 수도 있습니다. 

## <a name="switch-between-primary-target-audience"></a>기본 대상 그룹 간 전환

조직에서 개별 고객 및 비즈니스 계정에 대한 환경을 유지 관리하는 경우 왼쪽 창의 전환기를 사용하여 기본 대상 그룹를 선택할 수 있습니다.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="개인 고객과 비즈니스 계정 간의 기본 대상 그룹를 변경하는 스위처.":::

## <a name="supported-feature-areas"></a>지원되는 기능 영역

- [활동](activities.md): 활동을 생성하고 타임라인에 표시하기 위한 계정 및 관련 연락처 지원.
- [관계](relationships.md): 활동 마법사는 계정 보기에서 연락처의 모든 활동을 표시할 수 있도록 엔터티 간의 관계를 만드는 데 도움이 됩니다. 연락처를 드릴업하여 연락처 보기를 볼 수 있으며 계정 활동 집계에 계층을 사용할 수 있습니다.
- [측정값](measures.md): 하나의 계산으로 측정값 작성기에서 생성된 측정값을 지원합니다. 선택적 설정은 측정값을 생성할 때 하위 계정에 대한 롤업을 허용합니다.
- [세그먼트](segments.md): 세그먼트 빌더를 사용하여 처음부터 생성된 세그먼트를 지원합니다. 새 연산자를 사용하면 세그먼트를 작성할 때 계정 계층을 통합할 수 있습니다.
- [데이터 수집](data-sources.md): 이 영역의 모든 기능은 비즈니스 계정과 개인 고객에 대해 동일합니다.
- [데이터 통합](data-unification.md): 이 영역의 모든 기능은 비즈니스 계정 및 개인 고객에 대해 동일합니다.
- [보강](enrichment-hub.md): 일부 보강 유형은 개별 고객 시나리오에만 사용할 수 있고 다른 유형은 비즈니스 계정에만 사용할 수 있습니다.
- [예측 및 기본 제공 모델](predictions-overview.md): 트랜잭션 이탈 예측에는 비즈니스 계정에 대한 추가 단계가 포함됩니다. 다른 예측은 개별 고객에게만 제공됩니다.
- [활성화 및 내보내기](export-destinations.md): 비즈니스 계정 및 개인 고객에 대해 내보내기가 가능합니다. 일부 내보내기의 경우 기본 세그먼트에 예상되는 추가 구성 및 연락처 정보가 비즈니스 계정에 유효해야 합니다.
- [시스템 설정](system.md) 및 [사용자 관리](permissions.md): 이 영역의 모든 기능은 비즈니스 계정 및 개인 고객에 대해 동일합니다.

