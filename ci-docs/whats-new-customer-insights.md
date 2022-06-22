---
title: 신규 및 업데이트된 기능
description: 새로운 기능, 개선 사항 및 버그 수정에 대한 정보입니다.
ms.date: 06/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: d06f8be114f558d7adadf2913107c5fd69686875
ms.sourcegitcommit: 9dd767051014e06d8d9f2f616e248573f24df4cb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8843355"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights의 새로운 기능

최신 업데이트를 발표하게 된 것을 기쁘게 생각합니다! 이 문서는 공개 미리 보기 기능, 일반 가용성 향상 및 기능 업데이트를 요약합니다. 장기적인 기능 계획을 보려면 [Dynamics 365 및 Power Platform 릴리스 계획](/dynamics365/release-plans/)을 살펴보십시오.

업데이트는 지역별로 배포합니다. 따라서 특정 지역은 다른 지역보다 먼저 기능을 볼 수 있습니다. 다르게 지정하지 않으면 별도의 조치를 취할 필요가 없으며 가동 중지 시간 없이 자동으로 앱을 업데이트합니다.

> [!TIP]
> 기능 요청 및 제품 제안에 대한 투표를 제출하려면 [Dynamics 365 응용 프로그램 아이디어 포털](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights)로 이동하세요.

## <a name="may-2022-updates"></a>2022년 5월 업데이트

2022년 5월 업데이트에는 새로운 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.

### <a name="updated-data-unification-experience"></a>업데이트된 데이터 통합 환경

 데이터 통합을 사용하면 한 때 서로 다른 데이터 원본을 해당 데이터에 대한 통합 보기를 제공하는 단일 마스터 데이터 세트로 통합할 수 있습니다. 데이터는 단일 엔터티 또는 여러 엔터티에서 통합될 수 있습니다. 먼저 [엔터티 및 원본 필드를 선택하고](map-entities.md), [중복 레코드를 제거하고](remove-duplicates.md), [일치 조건](match-entities.md)에 대한 규칙을 지정하고, [Unified Customer Profiles에 포함할 필드](merge-entities.md)를 정의합니다.

자세한 내용은 [데이터 통합 개요](data-unification.md)를 참조하세요.

### <a name="refreshed-home-page-in-customer-insights"></a>Customer Insights의 새로 고쳐진 홈페이지

**홈** 은 주요 기능에 대한 구성 프로세스를 안내하고 세그먼트, 측정값 및 보강 데이터에 대한 개요를 제공합니다. 보다 관련성 높은 정보를 한눈에 제공할 수 있도록 환경을 새로 고쳤습니다.

자세한 내용은 [Customer Insights 탐색](home.md)을 참조하세요.

### <a name="track-usage-of-a-segment"></a>세그먼트 사용량 추적

이제 Customer Insights와 연결된 Dataverse 조직을 기반으로 하는 앱의 [세그먼트 사용량을 추적](segments.md#track-usage-of-a-segment)할 수 있습니다. [Dynamics 365 Marketing의 고객 여정에 사용된 Customer Insights 세그먼트](/dynamics365/marketing/real-time-marketing-ci-profile)의 경우 시스템에서 해당 세그먼트의 사용에 대해 알려줍니다.

### <a name="export-to-criteo"></a>Criteo로 내보내기

Criteo는 사용자가 디지털 광고를 관리할 수 있도록 도와주는 온라인 플랫폼입니다. 이제 Criteo로 Unified Customer Profiles의 세그먼트를 내보내 캠페인을 생성하고, 이메일 마케팅을 제공하고, 특정 고객 그룹을 사용할 수 있습니다.

자세한 내용은 [Criteo로 세그먼트 내보내기(프리뷰)](export-criteo.md)를 참조하세요.

### <a name="refined-documentation-structure-for-environment-creation"></a>환경 생성을 위한 세련된 문서 구조

Customer Insights에서 환경 생성 및 관리와 관련된 도움말 문서를 새롭게 다듬었습니다. 이제 문서가 목차의 환경 노드 아래에 그룹화됩니다. 재구성된 문서는 환경을 설정하고 보다 명확한 구조를 갖는 다양한 방법에 대한 추가 지침을 제공합니다. 공유할 피드백이 있는 경우 도움말 문서 끝에 있는 컨트롤을 통해 알려주세요.

자세한 내용은 [방법: 새 환경 만들기](create-environment.md)를 참조하세요.

## <a name="april-2022-updates"></a>2022년 4월 업데이트

2022년 4월 업데이트에는 새로운 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.

### <a name="dun--bradstreet-enrichment-preview"></a>Dun & Bradstreet 보강(프리뷰)

Dun & Bradstreet는 비즈니스를 위한 상업 데이터, 분석 및 인사이트를 제공합니다. 통합된 고객 프로필을 보유한 고객이 회사의 데이터를 보강할 수 있습니다. 보강에는 DUNS 번호, 회사 규모, 위치, 산업 등과 같은 특성이 포함됩니다.

자세한 내용은 [Dun & Bradstreet를 통한 회사 프로필 보강(프리뷰)](enrichment-dnb.md).

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>새 측정값 생성 시 측정값 유형 정의

이제 개별 프로필에 대한 측정값과 전체 비즈니스에 대한 측정값을 구분할 수 있습니다. 비즈니스 측정값은 Customer Insights의 홈 페이지에 표시되지만 고객 측정값은 자세한 고객 보기에 노출됩니다.

자세한 내용은 [측정값 빌더를 사용하여 처음부터 측정값 만들기](measure-builder.md)를 참조하세요.

### <a name="consolidation-of-customer-insights-documentation"></a>Customer Insights 설명서 통합

설명서 문서를 다시 방문하여 참여 인사이트 및 대상 그룹 인사이트 기능에 대한 언급을 제거했습니다. 앞으로 애플리케이션의 핵심 기능에 대해 쓸 때 제품 이름 Customer Insights를 일관되게 참조할 것입니다. 이 변경으로 인해 기본 설명서 저장소의 목차, URL 구조 및 파일 경로가 크게 재구성되었습니다. 모든 책갈피 또는 기존 링크는 계속 작동하며 업데이트된 URL로 리디렉션됩니다.

변경 사항을 어떻게 인식하는지 알려주거나 예상대로 작동하지 않는 것을 발견하려면 [이 페이지에 대한 피드백 제출](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**)을 통해 알려주십시오.

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

자세한 내용은 [자체 Azure Data Lake Storage에서 Dataverse와 데이터 공유 활성화(프리뷰)](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)를 참조하세요.

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