---
title: 신규 및 향후 기능
description: 새로운 기능, 개선 사항 및 버그 수정에 대한 정보입니다.
ms.date: 04/05/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 25c6e2897d836854408871b2c74afa16ecba7435
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647247"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights의 새로운 기능

최신 업데이트를 발표하게 된 것을 기쁘게 생각합니다! 이 문서는 공개 미리 보기 기능, 일반 가용성 향상 및 기능 업데이트를 요약합니다. 장기적인 기능 계획을 보려면 [Dynamics 365 및 Power Platform 릴리스 계획](/dynamics365/release-plans/)을 살펴보십시오.

업데이트는 지역별로 배포합니다. 따라서 특정 지역은 다른 지역보다 먼저 기능을 볼 수 있습니다. 다르게 지정하지 않으면 별도의 조치를 취할 필요가 없으며 가동 중지 시간 없이 자동으로 앱을 업데이트합니다.

> [!TIP]
> 기능 요청 및 제품 제안에 대한 투표를 제출하려면 [Dynamics 365 응용 프로그램 아이디어 포털](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights)로 이동하세요.


## <a name="march-2022-updates"></a>2022년 3월 업데이트

2022년 3월 업데이트에는 새로운 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.

### <a name="liveramp-abilitec-enrichment-preview"></a>LiveRamp AbiliTec 보강(프리뷰)

LiveRamp는 ID 확인 및 고객 데이터 통합을 제공합니다. 고객 데이터의 개인 식별자를 AbiliTec ID 그래프에 매핑하고 AbiliTec ID를 받을 수 있습니다. 그런 다음 이 ID를 사용하여 고객 데이터를 더 잘 통합할 수 있습니다.

자세한 내용은 [LiveRamp의 ID 데이터로 고객 프로필 보강(프리뷰)](enrichment-liveramp.md)을 참조하세요.

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>태그 및 필터를 사용하여 세그먼트 및 측정 구성
조직에서 많은 세그먼트 또는 측정값을 유지 관리하는 경우 올바른 세그먼트 또는 측정값을 찾는 것이 때때로 어려울 수 있습니다. 이 새로운 기능을 사용하면 태그와 열을 사용하여 목록을 구성할 수 있습니다. 데이터를 빠르고 쉽게 찾고 보기를 사용자 지정하는 데 도움이 됩니다.

자세한 내용은 [태그 및 열로 작업](work-with-tags-columns.md)을 참조하세요.

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>자체 스토리지 계정을 사용할 때 Dataverse와 데이터 공유 활성화

환경에서 Azure Data Lake Storage을 사용하여 Customer Insights 데이터를 저장하는 경우 Microsoft Dataverse와 데이터를 공유하려면 몇 가지 추가 구성이 필요합니다.
이전에는 데이터가 관리되는 데이터 레이크에 저장된 경우에만 Dataverse과 데이터 공유를 활성화할 수 있었습니다. 

자세한 내용은 [자체 Azure Data Lake Storage에서 Dataverse와 데이터 공유 활성화(프리뷰)](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)를 참조하세요.

### <a name="new-export-destinations-iterable-and-braze"></a>새로운 내보내기 대상: Iterable 및 Braze

우리는 새로운 연결을 통해 내보내기 대상의 에코시스템을 계속 확장하고 있습니다. 이제 세그먼트를 Iterable 및 Braze로 내보내 활성화 서비스를 사용할 수 있습니다.

자세한 내용은 [Iterable로 세그먼트 내보내기(프리뷰)](export-iterable.md) 및 [Braze로 세그먼트 내보내기(프리뷰)](export-braze.md)를 참조하십시오.

### <a name="improvements-to-marketo-and-google-ads-export"></a>Marketo 및 Google Ads 내보내기 개선

연결된 서비스에서 API를 변경하면 커넥터가 안정적이고 원활하게 실행되도록 업데이트됩니다. Marketo 및 Google Ads 서비스로 내보내기에 대한 몇 가지 업데이트를 출시했습니다.

- Google Ads: Google Ads 내보내기 커넥터의 새 버전을 사용하면 인증 환경이 간소화되어 이제 새 Google Ads 잠재고객을 자동으로 생성할 수 있습니다. 
- Marketo: 새 버전의 Marketo 내보내기 커넥터는 Marketo ID를 지원하므로 데이터 중복을 방지하고 기존 레코드를 업데이트하며 Marketo에서 새 레코드를 생성할 수 있습니다. 


## <a name="february-2022-updates"></a>2022년 2월 업데이트

2022년 2월 업데이트에는 새로운 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.

### <a name="general-availability-for-prediction-models"></a>예측 모델의 일반 공급

**구독 이탈**, **거래 이탈**, **고객평생가치(CLV)** 를 포함한 즉시 사용 가능한 예측 모델이 Customer Insights의 일부로 일반 공급됩니다. 

자세한 내용은 [예측 개요](predictions-overview.md)를 참조하세요.

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>새로운 데이터 원본: Azure Synapse Analytics 통합(프리뷰)

Azure Synapse Analytics는 데이터 웨어하우스 및 빅 데이터 시스템 전반에 걸쳐 인사이트를 확보하는 시간을 단축하는 엔터프라이즈 분석 서비스입니다.

이미 Azure Synapse Analytics를 사용하는 조직은 해당 데이터를 Customer Insights에 수집할 수 있습니다. 

자세한 내용은 [Azure Synapse 데이터 원본 연결(프리뷰)](connect-synapse.md)을 참조하세요.

### <a name="liveramp-enrichment-preview"></a>LiveRamp 보강(프리뷰)

LiveRamp는 ID 확인 및 고객 데이터 통합을 제공합니다. 고객 데이터의 개인 식별자를 AbiliTec ID 그래프에 매핑하고 AbiliTec ID를 받을 수 있습니다. 그런 다음 이 ID를 사용하여 고객 데이터를 더 잘 통합할 수 있습니다.

자세한 내용은 [LiveRamp의 ID 데이터로 고객 프로필 보강(프리뷰)](enrichment-liveramp.md)을 참조하세요.

### <a name="enrichment-for-data-sources-preview"></a>데이터 원본 보강(프리뷰)

Microsoft 및 기타 파트너와 같은 소스의 데이터를 사용하여 데이터 통합 전에 고객 데이터를 강화하십시오. 데이터 원본 보강은 데이터를 통합할 경우 더 나은 결과를 얻을 수 있는 더 높은 데이터 완전성과 품질을 확보하는 데 도움이 됩니다.

자세한 내용은 [데이터 원본 보강(프리뷰)](data-sources-enrichment.md)을 참조하세요.

### <a name="change-owner-of-environment"></a>환경 담당자 변경

여러 사용자가 Customer Insights에서 관리자 권한을 가질 수 있지만 한 명의 사용자만 환경 담당자입니다. 개선된 환경을 통해 환경 담당자를 변경하고 이전 담당자가 조직을 떠난 경우 소유권을 주장할 수 있습니다. 

자세한 내용은 [환경 담당자 변경](manage-environments.md#change-the-owner-of-an-environment)을 참조하세요.

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>데이터 준비 프로세스는 손상된 레코드의 손상 이유를 나열합니다.

이제 데이터 준비에 손상된 데이터가 있는 모든 필드에 대한 손상 이유가 표시됩니다. 정보는 쉽게 식별할 수 있도록 개별 기록 수준으로 제공됩니다. 

자세한 정보는 [손상된 데이터 원본](entities.md#corrupted-data-sources)을 참조하세요.

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>참여 인사이트 기능의 보고 기능에 대한 프리뷰 종료

Dynamics 365 Customer Insights 참여 인사이트 기능 프리뷰가 2022년 2월 15일에 종료됩니다.  
이 변경 사항은 Customer Insights 평가판 경험에 더 이상 유입 경로 생성 기능이나 기타 보고 기능이 포함되지 않음을 의미합니다.

Microsoft CDP(고객 데이터 플랫폼)인 [Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/)의 다른 많은 기능을 탐색하고 평가해 보시기 바랍니다.    
 
전환 기간 동안 기존 프리뷰 참가자는 다음과 같은 일부 미리 보기 기능에 계속 액세스할 수 있습니다.

- 웹 사이트 또는 모바일 앱을 계측하기 위한 코드 가져오기 
- 이벤트 및 이벤트 속성 보기 
- 수집 및 정제된 이벤트로 통합 프로필을 향상하여 고객 데이터의 가치를 최대한 활용
  
전환 기간 동안 캡처된 이벤트는 연결된 Data Lake로 계속 스트리밍됩니다. 이 기능이 꺼지면 데이터 공유가 중지되고 연결된 스토리지로 새 이벤트가 전송되지 않습니다.
기능 프리뷰 종료에 대한 질문이 있는 경우 Microsoft 계정 팀에 직접 문의하십시오. 계정 팀에서 향후 출시에 대한 최신 정보를 제공합니다. 

## <a name="january-2022-updates"></a>2022년 1월 업데이트

2022년 1월 업데이트에는 새로운 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>고객 피드백의 감정 분석

Customer Insights는 고객 감정을 종합하고 특정 비즈니스 측면을 목표 개선을 위한 기회로 식별하는 새로운 AI 기반 기능을 제공합니다. 고객의 서면 피드백을 분석하여 저렴한 비용으로 정확한 인사이트를 얻을 수 있습니다. 각 고객 ID에 대해 두 가지 파생된 통찰력을 생성하는 자연어 처리(NLP) 모델로 구동되는 감정 분석. 감정 점수(-5 ~ 5) 및 적용 가능한 비즈니스 측면 목록. 

자세한 내용은 [고객 피드백의 감정 분석(프리뷰)](sentiment-analysis.md)을 참조하세요.


[!INCLUDE [footer-include](includes/footer-banner.md)]