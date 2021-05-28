---
title: 신규 및 향후 기능
description: 새로운 기능, 개선 사항 및 버그 수정에 대한 정보입니다.
ms.date: 05/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: c66b37d6e4d6ed830238566fbc09934832892b34
ms.sourcegitcommit: 3f9981df97fa7b1f432a446d3f11936ea4cfbde5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "5988928"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights 대상 그룹 인사이트의 새로운 기능

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

최신 업데이트를 발표하게 된 것을 기쁘게 생각합니다! 이 문서는 공개 미리 보기 기능, 일반 가용성 향상 및 기능 업데이트를 요약합니다. 장기적인 기능 계획을 보려면 [Dynamics 365 및 Power Platform 릴리스 계획](/dynamics365/release-plans/)을 살펴보십시오.

업데이트는 지역별로 배포합니다. 따라서 특정 지역은 다른 지역보다 먼저 기능을 볼 수 있습니다. 다르게 지정하지 않으면 별도의 조치를 취할 필요가 없으며 가동 중지 시간 없이 자동으로 앱을 업데이트합니다.

> [!TIP]
> 기능 요청 및 제품 제안에 대한 투표를 제출하려면 [Dynamics 365 응용 프로그램 아이디어 포털](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights)로 이동하십시오.

## <a name="april-2021-updates"></a>2021년 4월 업데이트

2021년 4월 업데이트에는 여러 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.

### <a name="data-unification"></a>데이터 통합
 
- **데이터 통합을 위해 향상된 병합 환경**    
  
   이제 데이터 통합 프로세스의 병합 구성의 사용자 환경이 향상되었습니다. 변경 사항에는 병합된 필드의 직관적인 순서와 결합 및 단일 필드에 대한 자세한 통계가 포함됩니다.

- **엔터티 재정렬 및 모든 소스 레코드를 고객 엔터티로 구성**  
      
   이제 데이터 통합 프로세스의 기존 통합 계획에서 엔터티를 재정렬하고 제거할 수 있습니다. 비즈니스 요구에 따라 일치 프로세스에서 엔터티를 유연하게 재정렬할 수 있습니다. 또한 일치하지 않는 모든 레코드를 최종 *고객* 엔터티에 포함하여 고객 프로필 데이터 집합 정의를 정의할 수 있습니다.

### <a name="enrichments"></a>보강

 - **새로운 보강: 향상된 주소**    
  
   고객 데이터의 주소를 향상시키기 위해 새로운 보강 기능을 도입하게 되어 기쁘게 생각합니다. 데이터의 주소는 구조화되지 않았거나 불완전하거나 부정확할 수 있습니다. 이 기능은 Microsoft의 모델을 사용하여 주소를 정규화하고 Common Data Model 형식으로 보강하여 더 나은 정확성과 인사이트를 제공합니다.
 
   자세한 내용은 [향상된 주소로 고객 프로필 보강](enrichment-enhanced-addresses.md)을 참조하십시오.

- **보강을 위한 안내형 구성 환경**    
  
   간단한 안내형 환경을 사용하여 보강을 위한 구성 경험을 다시 검토했습니다. 이제 보강을 만들고 편집하기 위한 명확한 단계별 프로세스가 있습니다.
 
   또한 여러 보강에서 동일한 연결을 사용할 수 있도록 타사 보강에 대한 연결 구성을 분리했습니다. 관리자만 새 연결을 구성할 수 있지만 생성된 연결은 관리자와 기여자 모두가 사용할 수 있습니다.    

   자세한 내용은 [연결 개요](connections.md)를 참조하십시오.

- **동일한 유형의 여러 보강**    
  
   이제 사용자가 동일한 보강 유형의 여러 보강을 만들고 관리할 수 있습니다. 예를 들어 이제 두 개의 개별 주소 보강을 만들어 두 개의 서로 다른 고객 세그먼트를 보강할 수 있습니다. 동일한 유형의 보강을 만들 수 있는 수에 제한이 적용되며 보강 유형에 따라 다릅니다.
  
   자세한 내용은 [고객 프로필 보강](enrichment-hub.md)을 참조하세요.

## <a name="march-2021-updates"></a>2021년 3월 업데이트

2021년 3월 업데이트에는 여러 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.

### <a name="activities"></a>활동 

- **활동 마법사 및 의미 유형**

   활동 매핑 생성을 안내하고 단순화하기 위해 활동 매핑 경험을 개선하고 업데이트했습니다. 이 새로운 경험에서 사용자는 프로세스의 각 단계를 완료하는 데 도움이되는 안내식 경험을 얻게 됩니다. 활동 매핑 단계에서 사용자는 다양한 활동 유형 중에서 선택하는 것 외에도 *구독* 및/또는 *SalesOrderLine* 를 위한 데이터를 산업 표준 스키마에 의미론적으로 매핑할 수 있으며 이는 다운스트림 소비에 사용될 수 있습니다.   

   자세한 내용은 [고객 활동](activities.md)을 참조하세요.

### <a name="data-ingestion"></a>데이터 수집

- **Power Platform 데이터 흐름 및 게이트웨이를 사용하여 온-프레미스 데이터 소스에 연결** Customer Insights의 게이트웨이와 Power Platform 또는 Dataverse 연결된 환경을 사용하는 Power Platform 데이터 흐름 및 온-프레미스 연결 프리뷰를 발표하게 되어 기쁘게 생각합니다. 연결된 Dataverse 환경이 있는 Customer Insights 환경에서 생성된 모든 새 데이터 소스는 환경은 기본적으로 온-프레미스 데이터 연결과 풍부한 커넥터 및 변환 기능을 제공하는 Power Platform 데이터 흐름으로 설정됩니다.

### <a name="extensibility"></a>확장성

- **연결 및 내보내기로 구성된 내보내기** **내보내기 대상** 페이지에서 **연결** 로 이름을 바꾸고 **내보내기** 를 위한 별도의 페이지를 추가했습니다. 이 업데이트의 일부로 기존 내보내기를 연결 쌍과 해당 연결을 사용하는 내보내기 쌍으로 전환합니다. 관리자는 이제 **연결** 페이지에서 외부로 나가는 데이터를 보다 명확하게 확인할 수 있습니다. 모든 사용자 역할은 **수출** 페이지에 액세스 권한이 있지만 관리자만 기여자가 공유 연결을 사용하여 특정 내보내기를 편집할 수 있도록 선택할 수 있습니다.     
  자세한 내용은 [연결 개요](connections.md) 및 [수출 개요](export-destinations.md)를 확인하세요.

- **Campaign Monitor로 세그먼트 내보내기** Campaign Monitor를 포함하도록 내보내기 대상을 확장했습니다. 이제 Customer Insights에서 Campaign Monitor 목록으로 세그먼트를 내보내고 이를 마케팅 캠페인의 기준으로 사용할 수 있습니다.    
   자세한 내용은 [Campaign Monitor로 내보내기](export-campaign-monitor.md)를 참조하십시오.

- **Constant Contact로 세그먼트 내보내기** Constant Contact를 포함하도록 내보내기 대상을 확장했습니다. 이제 Customer Insights에서 Constant Contact 목록으로 세그먼트를 내보내고 이를 마케팅 캠페인의 기준으로 사용할 수 있습니다.   
   자세한 내용은 [Constant Contact로 내보내기](export-constant-contact.md)를 참조하십시오.

- **RollWorks로 세그먼트 내보내기** RollWorks를 포함하도록 내보내기 대상을 확장했습니다. 이제 Customer Insights에서 RollWorks 대상으로 세그먼트를 내보내고 이를 B2B 광고의 기준으로 사용할 수 있습니다.    
   자세한 내용은 [RollWorks로 데이터 내보내기](export-rollworks.md)를 참조하십시오.

- **Snapchat으로 세그먼트 내보내기** Snapchat을 포함하도록 내보내기 대상을 확장했습니다. 이제 Customer Insights에서 Snapchat 대상으로 세그먼트를 내보내고 이를 광고의 기준으로 사용할 수 있습니다.     
   자세한 내용은 [Snapchat으로 데이터 내보내기](export-snapchat.md)를 참조하십시오.

### <a name="predictions"></a>예측

- **예측 제품 추천에 제품 필터 사용** 제품 추천 모델에 제품 필터를 사용하는 기능을 추가했습니다. 이제 제품의 하위 집합만 사용하는 예측을 만들 수 있습니다.    
   자세한 내용은 [제품 필터 구성](predict-product-recommendation.md#configure-product-filters)을 참조하십시오.

- **모델 예측에서 세그먼트 만들기** 예측 모델의 결과를 사용하여 세그먼트를 만드는 빠른 방법을 추가했습니다. 모델 결과 페이지에서 **세그먼트 만들기** 옵션을 선택하여 쉽게 새 세그먼트를 만들 수 있습니다.    
  자세한 내용은 [예측 모델을 기반으로 세그먼트 만들기](prediction-based-segment.md)를 참조하세요.

- **제품 추천에 대한 설명** 제품 권장 사항을 생성하기 위해 AI 모델에서 학습한 주요 요소와 이러한 요소가 제품 권장 사항에 기여하는 정도를 설명하는 정보를 추가했습니다. 이 정보는 모델 결과 화면에 추가됩니다.    
   자세한 내용은 [예측 상태 및 결과를 검토](predict-product-recommendation.md#review-a-prediction-status-and-results)를 참조하세요.

## <a name="february-2021-updates"></a>2021년 2월 업데이트

2021년 2월 업데이트에는 여러 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.

#### <a name="extensibility"></a>확장성

- **AdRoll로 세그먼트 내보내기**

  AdRoll을 포함하도록 내보내기 대상을 확장했습니다. 이제 Customer Insights에서 AdRoll 대상 그룹으로 세그먼트를 내보내고 이를 광고의 기준으로 사용할 수 있습니다. 자세한 내용은 [AdRoll용 커네터](export-adroll.md)를 참조하십시오.

#### <a name="segments"></a>세그먼트
 
- **중복 항목 만들기**
  
  기존 세그먼트를 기반으로 새 세그먼트를 만들려면 이제 세그먼트를 복제하고 복제된 세그먼트를 편집하여 더 구체화할 수 있습니다. 

- **세그먼트에 추가 속성 추가**

  이제 이러한 속성이 고객 프로필의 일부가 아닌 경우에도 세그먼트 출력에 특성을 포함할 수 있습니다. 예를 들어, 고객 엔터티와M:1 관계가 있는 구독 엔터티의 일부인 경우에도 세그먼트에 구독 ID를 포함합니다. 특성이 고객 엔터티와 관련된 엔터티에 속하는 한 이제 이러한 특성을 포함할 수 있습니다.  

#### <a name="predictions"></a>예측

- **예측 제품 추천 만들기**

  고객이 구매에 관심을 갖는 것이 무엇인지 이해하는 것은 개인 설정 및 참여를 통해 비즈니스 수익을 개선하고 고객 충성도를 구축하는 데 필요한 첫 번째 단계 중 하나입니다. 고객의 관심사에 맞지 않는 제품에 대한 추천을 제공하면 고객과 비즈니스 사이에 단절감이 생길 수 있으며 궁극적으로 고객의 전반적인 잠재적 수익과 경험을 제한할 수 있습니다. 

  자체 데이터를 사용하여 이제 고객이 미래에 구매할 가능성이 있는 제품에 대한 예측을 생성할 수 있습니다. 자세한 내용은 [제품 추천 예측](predict-product-recommendation.md)을 참조하십시오.

#### <a name="system-administration"></a>시스템 관리

- **복사 환경은 더 많은 유형의 데이터 원본을 지원함**

  관리자는 동일한 조직의 새 환경에 환경 구성을 복사할 수 있습니다. 이 기능은 데이터 원본을 기반으로 하는 Common Data Service 데이터 레이크 또는 Common Data Model 폴더가 사용되는 사례에 대해 복사 환경 기능을 확장합니다.

## <a name="january-2021-updates"></a>2021년 1월 업데이트

2021년 1월 업데이트에는 여러 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.

#### <a name="extensibility"></a>확장성

- **SFTP 내보내기를 위한 확장된 기능 및 향상된 성능** 이제 Customer Insights의 모든 출력 엔터티를 SFTP 호스트로 내보낼 수 있습니다. 이전에는 내보내기가 세그먼트 엔터티로 제한되어 있었습니다. 또한 SFTP 내보내기의 성능은 SFTP 호스트의 성능에 따라 더 짧은 시간에 더 많은 데이터 볼륨을 허용합니다.    
  자세한 내용은 [SFTP용 커넥터(미리 보기)](export-sftp.md)를 참조하십시오.  

#### <a name="segments"></a>세그먼트

- **메트릭을 개선하기 위한 기계 학습 기반 제안된 세그먼트** 세그먼트를 발견하고 만드는 새로운 방법이 있습니다. 시스템은 AI 모델을 사용하여 이미 추적 중인 KPI(측정값)를 개선하는 데 도움이 될 수 있는 세그먼트를 제안합니다. 측정값 또는 다른 기본 특성에서 선택한 특성의 영향 정도를 보여줍니다. 이 정보는 기회를 제공하는 잠재적인 세그먼트를 찾는 데 도움이 됩니다.    
  자세한 내용은 [제안된 세그먼트(미리 보기)](suggested-segments.md)를 참조하십시오.

#### <a name="data-unification"></a>데이터 통합

- **향상된 일치 환경** 데이터 통합 영역에서 일치 환경이 업데이트되었습니다. 일치 작동 방식을 자세히 설명하는 자세한 통계를 포함한 일치 규칙을 구성하고 볼 수 있습니다. 구성, 드래그 앤 드롭 일치 규칙 등을 유지하면서 일치 규칙이 더 이상 활동하지 않도록 비활성화하는 옵션이 있습니다.
  자세한 내용은 [엔터티 일치](match-entities.md)를 참조하십시오.

- **일치 프로세스의 중복 제거 출력을 엔티티로 사용할 수 있음** 일치 프로세스의 중복 제거 프로세스 출력은 이제 추가 분석을 위해 별도의 엔터티에 기록됩니다. 이 엔터티는 중복 제거 프로세스에 사용되는 필드와 승자 레코드 및 승자 레코드와 병합되는 해당 대체 레코드로 구성됩니다.
  자세한 내용은 [엔터티로서 중복 제거 출력](match-entities.md#deduplication-output-as-an-entity)을 참조하세요.

#### <a name="system-administration"></a>시스템 관리

- **Microsoft Dataverse에 원활한 데이터 공유** 이제 Microsoft Dataverse 관리형 Data Lake를 사용하여 Microsoft Dataverse 응용 프로그램과 Customer Insights 결과를 공유할 수 있습니다. Dataverse 환경을 Customer Insights와 연결하면 데이터 공유를 활성화할 수 있는 옵션이 제공됩니다.
  자세한 내용은 [환경 관리](manage-environments.md)를 참조하십시오.




[!INCLUDE[footer-include](../includes/footer-banner.md)]