---
title: 신규 및 향후 기능
description: '새로운 기능, 개선 사항 및 버그 수정에 대한 정보입니다.'
ms.date: 01/27/2022
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
---

# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights 대상 그룹 인사이트의 새로운 기능



최신 업데이트를 발표하게 된 것을 기쁘게 생각합니다! 이 문서는 공개 미리 보기 기능, 일반 가용성 향상 및 기능 업데이트를 요약합니다. 장기적인 기능 계획을 보려면 [Dynamics 365 및 Power Platform 릴리스 계획](/dynamics365/release-plans/)을 살펴보십시오.

업데이트는 지역별로 배포합니다. 따라서 특정 지역은 다른 지역보다 먼저 기능을 볼 수 있습니다. 다르게 지정하지 않으면 별도의 조치를 취할 필요가 없으며 가동 중지 시간 없이 자동으로 앱을 업데이트합니다.

> [!TIP]
> 기능 요청 및 제품 제안에 대한 투표를 제출하려면 [Dynamics 365 응용 프로그램 아이디어 포털](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights)로 이동하세요.


## <a name="december-2021-updates"></a>2021년 12월 업데이트

2021년 12월 업데이트에는 새로운 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.

### <a name="forward-customer-insights-logs-to-azure-monitor"></a>Azure Monitor에 Customer Insights 로그 전달

Customer Insights는 Azure Monitor와 직접 통합을 제공합니다. 이 기능에는 감사 이벤트 및 운영 이벤트가 포함됩니다. Azure Monitor 리소스 로그를 사용하면 로그를 모니터링하고 Azure Storage,  Azure Log Analytics에 보내거나 Azure Event Hubs에 스트리밍할 수 있습니다.

자세한 내용은 [Azure Monitor(프리뷰)로 Dynamics 365 Customer Insights에 로그 전달](diagnostics.md)을 참조하세요.

### <a name="enrich-customer-profiles-with-engagement-data"></a>참여 데이터로 고객 프로필 보강

Microsoft Office 365의 데이터를 사용하여 Office 365 앱을 통해 참여에 대한 인사이트로 고객 계정 프로필을 보강합니다. 참여 데이터는 계정 수준에서 집계되는 이메일 및 회의 활동으로 구성됩니다. 예를 들어 비즈니스 계정의 이메일 수 또는 계정과의 회의 수입니다. 개별 사용자에 대한 데이터는 공유되지 않습니다. 이 보강은 영국, 유럽, 북미에서 사용할 수 있습니다.

자세한 내용은 [참여 데이터로 고객 프로필 보강(프리뷰)](enrichment-office.md)을 참조하세요

### <a name="advanced-data-unification-features"></a>고급 데이터 통합 기능

#### <a name="enable-conflict-resolution-policies-at-the-individual-attribute-level"></a>개별 특성 수준에서 충돌 해결 정책 사용

엔터티 내에서 고객 레코드의 중복을 제거할 때 전체 레코드를 승자로 선택하지 않아도 될 수 있습니다. 이제 모든 속성에 대한 규칙을 기반으로 다양한 레코드의 최상의 필드를 병합할 수 있습니다. 예를 들어 가장 최근의 이메일과 다른 기록에서 가장 완전한 주소를 유지하도록 선택할 수 있습니다. 

이제 단일 엔터티 내에서 레코드를 중복 제거하고 병합하면서 개별 특성에 대해 별도의 병합 규칙을 정의할 수 있습니다. 이전에는 단일 병합 규칙(최신성 데이터 완전성을 기반으로 레코드 유지)만 선택할 수 있었고 해당 규칙은 레코드 수준에서 모든 특성에 적용되었습니다. 보관하려는 데이터 중 일부가 레코드 A에 있고 다른 좋은 데이터가 레코드 B에 있는 경우에는 이상적이지 않습니다.

자세한 내용은 [일치 항목에 대한 중복 제거 정의](match-entities.md#define-deduplication-on-a-match-entity)를 참조하세요.

#### <a name="custom-rules-for-matching"></a>일치를 위한 맞춤 규칙

레코드를 일치시키지 않기 위해 일반 규칙에 대한 예외를 지정해야 하는 경우가 있습니다. 이는 여러 개인이 충분한 정보를 공유하여 시스템이 그들을 한 개인으로 일치시킬 때 발생할 수 있습니다. 예를 들어 같은 도시에 거주하며 같은 성를 쓰고 생년월일이 같은 쌍둥이가 있습니다.

예외는 잘못된 데이터 통합이 통합 규칙에서 해결될 수 있도록 합니다. 규칙에 여러 예외를 추가할 수 있습니다.

자세한 내용은 [규칙에 예외 추가](match-entities.md#add-exceptions-to-a-rule)를 참조하세요.

#### <a name="provide-additional-conflict-resolution-policies-and-enable-grouping-of-attributes"></a>추가 충돌 해결 정책 제공 및 특성 그룹화 가능

이 기능을 사용하면 필드 그룹을 단일 단위로 취급할 수 있습니다. 예를 들어, 레코드에 Address1, Address2, City, State 및 Zip 필드가 포함되어 있는 경우입니다. 데이터를 더 완전하게 만들기 위해 다른 레코드의 Address2에 병합하고 싶지 않을 수 있습니다.

이제 관련 필드 그룹을 결합하고 단일 병합 정책을 그룹에 적용할 수 있습니다. 

자세한 내용은 [필드 그룹 결합](merge-entities.md#combine-a-group-of-fields)을 참조하세요.


## <a name="november-2021-updates"></a>2021년 11월 업데이트

2021년 11월 업데이트에는 새로운 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.

### <a name="segment-membership-now-available-in-dataverse"></a>이제 Dataverse에서 세그먼트 멤버십을 사용할 수 있습니다

이제 고객 프로필 및 인사이트와 함께 Dataverse에서 고객 프로필에 대한 세그먼트 멤버십 정보를 사용할 수 있습니다. Dynamics 365 작업 앱 및 모델 기반 앱은 이 데이터를 사용하여 지정된 고객에 대한 세그먼트 멤버십 세부 정보를 조회할 수 있습니다.

### <a name="activities-support-contact-level-details-for-business-accounts"></a>활동은 비즈니스 계정에 대한 연락처 수준 세부 정보를 지원합니다.

이제 비즈니스 계정 활동 타임라인에서 연락처에 대한 활동을 구성, 표시 및 필터링하여 특정 활동에 참여한 계정 연락처를 더 잘 이해할 수 있습니다.

## <a name="october-2021-updates"></a>2021년 10월 업데이트

2021년 10월 업데이트에는 새로운 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.

### <a name="b-to-b"></a>B-to-B

2021년 10월부터 Customer Insights에서 비즈니스 계정 및 관련 연락처로 작업할 수 있습니다. 이전에는 앱이 대부분 개인 소비자를 대상으로 했습니다. 새로운 환경 유형 위에 B-to-B 시나리오를 지원하도록 여러 기능 영역이 업데이트되었습니다. 지원되는 B-to-B 기능에 대한 개요는 [대상 그룹 인사이트에서 비즈니스 계정으로 작업](work-with-business-accounts.md)을 참조하십시오.

다음 섹션에서는 비즈니스 계정 및 개별 소비자를 지원하도록 조정된 몇 가지 주요 영역을 강조합니다.

#### <a name="export-segments-based-on-business-accounts"></a>비즈니스 계정을 기반으로 세그먼트 내보내기

대상 그룹 인사이트의 모든 세그먼트 내보내기는 비즈니스 계정의 컨텍스트에서 사용할 수 있습니다. 대부분의 세그먼트 내보내기는 비즈니스 계정에 유효한 기본 세그먼트의 추가 구성 및 [연락처 정보 프로젝팅](segment-builder.md#create-a-new-segment)이 필요합니다. 자세한 내용은 [세그먼트 내보내기](export-destinations.md#export-segments)를 참조하십시오.

#### <a name="use-the-linkedin-ads-export-with-business-accounts"></a>비즈니스 계정으로 LinkedIn 광고 내보내기 사용

LinkedIn 광고 내보내기는 이제 비즈니스 계정의 컨텍스트에서 연락처 및 회사 타겟팅에 사용할 수 있습니다. LinkedIn 내보내기의 주요 포커스로 회사 타겟팅을 선택하면 연락처 정보를 프로젝팅할 필요 없이 비즈니스 계정에 구축된 세그먼트를 내보낼 수 있습니다. 자세한 내용은 [ LinkedIn 광고 내보내기](export-linkedin-ads.md) 및 [연락처 타겟팅](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting)과 [회사 타겟팅](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting)의 차이점에 대한 문서를 참조하십시오. 

#### <a name="create-measures-based-on-business-accounts-and-their-hierarchy"></a>비즈니스 계정 및 해당 계층 구조를 기반으로 측정값 만들기

측정값 빌더를 사용하면 비즈니스 계정에 대한 측정값을 생성하고 선택적으로 계층 구조 정보를 사용할 수 있습니다. 계층 구조 정보는 계정 및 모든 관련 하위 계정에서 측정값 계산을 롤업하는 데 사용됩니다. 예를 들어 계층 구조로 식별되는 각 비즈니스 계정 그룹에 대한 총 수익과 같은 측정값을 생성할 수 있습니다. 자세한 내용은 [측정값 정의 및 관리](measures.md)를 참조하세요.

#### <a name="create-segments-based-on-business-accounts-and-their-hierarchy"></a>비즈니스 계정 및 해당 계층 구조를 기반으로 세그먼트 만들기

세그먼트 빌더를 사용하면 세그먼트의 각 계정에 대한 연락처 정보를 선택적으로 포함하는 비즈니스 계정 세그먼트를 만들 수 있습니다. 계정 계층 구조가 설정되어 있으면 세그먼트 생성에서 계정 계층 구조 정보를 사용할 수 있습니다. 자세한 내용은 [새 세그먼트 만들기](segment-builder.md#create-a-new-segment)를 참조하세요.

#### <a name="retain-your-business-accounts-with-deep-insights-to-their-churn-tendency"></a>고객 이탈 경향에 대한 깊은 인사이트를 통해 비즈니스 계정 유지

고객 이탈 예측 모델은 이제 비즈니스 계정도 지원합니다. 계정뿐만 아니라 계정과 고객이 구매하는 제품 또는 서비스 범주의 조합에 대한 이탈 위험을 평가할 수 있습니다. 이 추가 사항은 계정이 일반적으로 귀하의 구매를 중단할 가능성이 더 높은지 또는 특정 범주의 상품 또는 서비스에 대한 구매를 중단할 가능성이 더 높은지 이해하는 데 도움이 됩니다. 이 AI 모델을 사용하는 데 도움이 되도록 계정이 이탈할 가능성이 있는 이유도 나열됩니다. 자세한 내용은 [트랜잭션 이탈 예측(프리뷰)](predict-transactional-churn.md)을 참조하십시오.

#### <a name="see-contacts-of-a-business-account-in-customer-view"></a>고객 보기에서 비즈니스 계정 연락처 보기

비즈니스 계정이 관련 계정에 매핑된 경우 Customer Insights 앱은 이러한 관련 연락처를 고객 세부 정보 보기의 일부로 표시합니다. 자세한 내용은 [고객 프로필](customer-profiles.md)을 참조하십시오.


## <a name="september-2021-updates"></a>2021년 9월 업데이트

2021년 9월 업데이트에는 새로운 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.

### <a name="activities"></a>활동 

- **활동 타임라인 개선** 고객 프로필의 활동 타임라인에 대한 필터를 확장했습니다. 또한 새 필터 팬을 사용하여 활동 유형 및 날짜별로 필터링할 수 있습니다. 날짜는 다른 조건을 사용하여 필터링할 수 있습니다. 자세한 내용은 [고객 프로필에서 활동 타임라인 보기](activities.md#view-activity-timelines-on-customer-profiles)를 참조하세요.

### <a name="relationships"></a>관계

- **다중 홉 관계 지원** 활동을 구성하고 엔터티 간의 관계를 정의할 때 다중 홉 관계를 사용합니다. 다중 홉 관계는 중간 엔터티를 사용하여 두 엔터티를 연결합니다. 활동을 구성할 때 다중 홉 관계를 사용하여 활동 엔터티를 중간 엔터티에 연결한 다음 고객 엔터티에 연결할 수 있습니다. 다중 홉 관계와 다중 경로 관계를 결합할 수 있습니다. 자세한 내용은 [다중 홉 관계](relationships.md#multi-hop-relationship)를 참조하세요.

- **다중 경로 관계 지원** 활동을 구성하고 엔터티 간의 관계를 정의할 때 다중 경로 관계를 사용합니다. 다중 경로 관계는 소스 엔터티를 둘 이상의 엔터티에 연결합니다. 활동을 구성할 때 다중 경로 관계를 사용하여 활동 엔터티를 둘 이상의 고객 엔터티에 연결할 수 있습니다. 다중 경로 관계와 다중 홉 관계를 결합할 수 있습니다. 자세한 내용은 [다중 경로 관계](relationships.md#multi-path-relationship)를 참조하세요.

## <a name="august-2021-updates"></a>2021년 8월 업데이트

2021년 7월과 8월 업데이트에는 새로운 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.

### <a name="extensibility"></a>확장성

- **Klaviyo로 세그먼트 내보내기** [Klaviyo를 포함하도록 내보내기 대상을 확장](export-klaviyo.md)했습니다. 이제 세그먼트를 내보내 캠페인을 만들고 이메일 마케팅을 수행하고 Klaviyo로 특정 고객 그룹을 사용할 수 있습니다. 


## <a name="june-2021-updates"></a>2021년 6월 업데이트

2021년 6월 업데이트에는 여러 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.

### <a name="data-ingestion"></a>데이터 수집

- **데이터 통합 진행 상황 업데이트 개선** 이제 [데이터 통합 프로세스](data-unification.md) 단계에서 보다 세분화되고 개선된 동적 상태 업데이트를 볼 수 있습니다. 이 기능을 사용하면 자세한 진행 상황을 추적하여 프로세스 흐름을 이해하고 주의가 필요한 단계가 있는 경우 조치를 취할 수 있습니다.

### <a name="extensibility"></a>확장성

- **Salesforce Marketing Cloud로 세그먼트 및 기타 데이터 내보내기** [Salesforce Marketing Cloud](export-salesforce.md)를 포함하도록 내보내기 대상을 확장했습니다. 이제 브랜드 SFTP 내보내기를 통해 세그먼트 및 기타 유형의 데이터를 Salesforce Marketing Cloud로 내보낼 수 있습니다. Salesforce에서 데이터 가져오기를 완전히 자동화하고 보다 효과적인 마케팅 캠페인을 만드는 데 사용할 수 있습니다.  
 
- **ActiveCampaign으로 세그먼트 내보내기** [활성 캠페인](export-active-campaign.md)을 포함하도록 내보내기 대상을 확장했습니다. 이제 세그먼트를 내보내 캠페인을 생성하고, 이메일 마케팅을 실행하고, ActiveCampaign에서 특정 고객 그룹과 작업할 수 있습니다.
 
- **Sendinblue로 세그먼트 내보내기** [Sendinblue](export-sendinblue.md)를 포함하도록 내보내기 대상을 확장했습니다. 이제 세그먼트를 내보내 캠페인을 생성하고, 이메일 마케팅을 실행하고, Sendinblue에서 특정 고객 그룹과 작업할 수 있습니다.
 
### <a name="ux-updates"></a>UX 업데이트 

- **신규 및 향상된 고객 페이지 및 프로필 세부 정보 페이지** 향상된 사용자 환경과 더 나은 성능을 위해 고객 페이지와 프로필 세부 정보 페이지를 다시 디자인했습니다. 이러한 변경을 통해 고객을 보고, 정렬하고, 검색하고, 필터링할 수 있습니다. 이제 필터가 URL에 표시되어 검색 결과를 다른 사용자와 원활하게 공유할 수 있습니다. 검색 결과를 세그먼트로 저장할 수도 있습니다.    
  고객 프로필의 세부 정보 페이지는 이제 가독성 향상을 위해 인구 통계 데이터, ID 및 기타 프로필 특성과 같은 다양한 하위 섹션의 데이터를 그룹화합니다. 프로필 세부 정보 페이지의 다른 섹션은 이제 더 대화형이 되었습니다. 예를 들어, 이제 활동 섹션에서 필터링 및 정렬이 가능합니다.


## <a name="may-2021-updates"></a>2021년 5월 업데이트

2021년 5월 업데이트에는 여러 기능, 성능 업그레이드 및 버그 수정이 포함됩니다.

### <a name="data-ingestion"></a>데이터 수집

- **Azure Data Lake Storage에서 데이터를 연결할 때 메타데이터 또는 엔터티 정의 보기 또는 수정** 이제 Azure Data Lake Storage의 Common Data Model 폴더에서 데이터를 연결할 때 대상 그룹 인사이트에서 메타데이터 또는 엔터티 정의를 보고 편집할 수 있습니다. 이 기능은 실시간 피드백, 모델 검증 및 오류 검사를 제공합니다. 이를 통해 model.json과 manifest.json을 완벽하게 편집할 수 있습니다.

### <a name="extensibility"></a>확장성

- **향상된 세그먼트 내보내기, 사용자 지정 일정 및 복제** 이제 목록에서 [특정 세그먼트에 대한 모든 내보내기 보기](export-destinations.md#view-exports-and-export-details)를 수행할 수 있습니다. 이 새로운 보기는 특정 세그먼트가 사용되는 방식을 관리하고 기존을 조정하거나 새 내보내기를 만드는 데 도움이 됩니다.    
  개별 내보내기 또는 한 번에 여러 내보내기에 대한 [사용자 지정 새로 고침 일정을 정의](export-destinations.md#schedule-and-run-exports)할 수 있습니다. 지금까지 모든 내보내기는 시스템을 새로 고칠 때마다 실행되었습니다.    
  처음부터 새 내보내기를 만드는 대신 기존 내보내기를 기반으로 시작하여 시간을 절약할 수 있습니다.

- **Microsoft Advertising으로 세그먼트 내보내기** Microsoft Advertising을 포함하도록 내보내기 대상을 확장했습니다. 통합 고객 프로필 데이터로 Microsoft Advertising에 Customer Match 대상 그룹을 만들고, 광고 캠페인에 이러한 대상 그룹을 사용합니다. 자세한 내용은 [Microsoft Advertising으로 세그먼트 내보내기](export-microsoft-advertising.md)를 참조하십시오.

- **LinkedIn Ads로 세그먼트 내보내기** LinkedIn Ads를 포함하도록 내보내기 대상을 확장했으며 통합 고객 프로필 데이터를 내보내 LinkedIn을 통해 연락처 타겟팅 및 회사 타겟팅을 잠금 해제할 수 있습니다. 자세한 내용은 [LinkedIn Ads로 세그먼트 내보내기](export-linkedin-ads.md)를 참조하십시오.


- **Omnisend로 세그먼트 내보내기** Omnisend를 포함하도록 내보내기 대상을 확장했습니다. 대상 그룹 인사이트에서 만든 세그먼트를 사용하여 캠페인을 생성하고 이메일 마케팅을 제공하며 Omnisend의 특정 고객 그룹을 활용합니다. 자세한 내용은 [Omnisend로 세그먼트 내보내기](export-omnisend.md)를 참조하십시오.

### <a name="predictions"></a>예측

- **입력 데이터 사용성 보고서** 입력 데이터 사용성 보고서는 기본 제공 예측이 생성할 수 있는 오류 및 경고에 대한 통합 보기를 제공합니다. 또한 모델 성능을 개선하는 방법에 대한 권장 사항을 제공합니다.    
  이 보고서는 모델이 학습 프로세스를 완료한 후에 사용할 수 있습니다. 성공적으로 완료되었는지 여부와 관계없이 각 모델에 대해 별도로 생성됩니다.
  현재 이 기능은 트랜잭션 이탈 모델에서만 사용할 수 있습니다. 자세한 내용은 [입력 데이터 사용성 보고서](manage-predictions.md#input-data-usability-report)를 참조하십시오.

### <a name="relationships"></a>관계

- **관계 시각화 도우미** 관계 시각화 도우미 보기를 사용하면 엔터티와 해당 카디널리티 간의 기존 관계를 모두 볼 수 있습니다. 관계는 이제 사용자 생성, 시스템 및 상속된 관계 그룹으로 구성됩니다. 보기를 이미지로 내보낼 수도 있습니다. 자세한 내용은 [관계 보기](relationships.md#view-relationships)를 참조하십시오. 

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

- **RollWorks로 세그먼트 내보내기** RollWorks를 포함하도록 내보내기 대상을 확장했습니다. 이제 Customer Insights에서 RollWorks 대상그룹으로 세그먼트를 내보내고 이를 B-to-B 광고의 기준으로 사용할 수 있습니다.    
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

  관리자는 동일한 조직의 새 환경에 환경 구성을 복사할 수 있습니다. 이 기능은 Microsoft Dataverse 관리형 Data Lake 또는 Common Data Model 폴더를 기반으로 하는 데이터 원본이 사용되는 경우 복사 환경 기능을 확장합니다.

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