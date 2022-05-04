---
title: Dynamics 365 Marketing에서 통합 프로필 사용
description: 통합 프로필 및 세그먼트를 Dynamics 365 Marketing과 통합하는 방법을 알아보십시오.
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 45c59465771e4ad25ed36d5da1568e67b94cf994
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653747"
---
# <a name="work-with-unified-customer-profiles-in-dynamics-365-marketing"></a>Dynamics 365 Marketing의 통합 고객 프로필 작업

[Dynamics 365 Marketing](/dynamics365/marketing/overview)은 고객 경험을 향상시켜 모든 접점에서 개인화된 여정을 조율하여 관계 강화하고 충성도를 높일 수 있습니다. Dynamics 365 Marketing 앱은 Dynamics 365 Sales, Dynamics 365 Customer Insights, Microsoft Teams 및 기타 제품과 원활하게 작동하며 데이터 및 AI의 힘을 사용하여 더 빠르고 더 나은 결정을 내릴 수 있습니다.

Customer Insights 데이터를 Marketing과 연결하여 다음을 수행할 수 있습니다.

- 통합 고객 프로필 및 세그먼트를 타겟팅합니다. 이를 통해 고객 데이터의 위치에 관계없이 모든 고객의 참여를 유도할 수 있습니다.
- 이메일, SMS 및 푸시 알림의 기본 동적 콘텐츠(예: 개인 설정된 토큰)를 통해 로열티 상태, 구독 갱신 날짜, 상위 거래처 또는 통합 Customer Insights 프로필에서 캡처한 기타 모든 측정값을 확인할 수 있습니다.
- Marketing의 데이터를 Customer Insights로 로드하고 다른 소스의 고객 데이터와 결합합니다.
- Customer Insights 데이터 정리, 보강 및 유사 일치 도구를 적용합니다.


## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>실시간 마케팅에서 풍부한 고객 프로필 사용

실시간 마케팅을 통해 고객 행동을 기반으로 고객 여정을 시작하는 [사용자 지정 트리거](/dynamics365/marketing/real-time-marketing-custom-triggers)를 만들할 수 있습니다. 데이터가 더 개인화될수록 여정은 더 관련성 있고 개인화될 것입니다. 이것이 Marketing과 Customer Insights를 결합을 강력하게 만드는 이유입니다. 모든 소스의 [데이터를 통합](data-unification.md)한 다음 이를 사용하여 고도로 개인화된 고객 여정을 촉진할 수 있습니다.

자세히 알아보기: [실시간 마케팅에서 Customer Insights 프로필 및 세그먼트 사용](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>아웃바운드 고객 여정에 통합 세그먼트 사용

Customer Insights를 사용하면 다양한 소스의 데이터를 구체화하고 집계된 고객 세그먼트로 결합할 수 있습니다. [Customer Insights를 아웃바운드 마케팅과 연결](export-dynamics365-marketing.md)하면 이러한 세그먼트가 자동으로 *표시되고* 고객 여정 디자이너에서 자동으로 새로 고쳐집니다.

자세히 알아보기: [Dynamics 365 Marketing을 통해 Dynamics 365 Customer Insights의 세그먼트 사용](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>자체 Azure Data Lake Storage에서 데이터 가져오기

Marketing을 통해 Customer Insights 데이터를 사용하려는 경우 클라우드 스토리지로 제한되지 않습니다. 자체 Azure Data Lake Storage 설정이 이미 있는 경우 Customer Insights에 연결한 다음 클라우드 기반 설정에서와 마찬가지로 Marketing 앱과 데이터를 공유할 수 있습니다.

자세히 알아보기: [자체 Azure Data Lake Storage에서 Dataverse와 데이터 공유 활성화](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)