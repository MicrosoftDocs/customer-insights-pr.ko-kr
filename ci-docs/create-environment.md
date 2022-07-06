---
title: '방법: 새 환경 만들기'
description: Dynamics 365 Customer Insights에서 환경을 만드는 단계입니다.
ms.date: 05/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 62969527ceed906ff06fb9be90b972496323ce0a
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052753"
---
# <a name="how-to-create-a-new-environment"></a>방법: 새 환경 만들기

[Dynamics 365 Customer Insights에 대한 구독 라이선스를 구입](paid-license.md)하면 Microsoft 365 테넌트의 전역 관리자는 환경을 만들도록 초대하는 이메일을 받습니다. 시작하려면 [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start)로 이동하십시오. 이 시나리오에서는 [1단계: 기본 정보 제공](#step-1-provide-basic-information)으로 바로 이동할 수 있습니다.

첫 번째 환경이 생성된 후 Microsoft 365 테넌트의 전역 관리자는 [조직에서 사용자를 관리자로 추가](permissions.md)할 수 있습니다. 앞으로 이러한 관리자는 사용자와 환경을 관리할 수 있습니다. 조직에서 Customer Insights에 대한 라이선스를 두 개 이상 구입한 경우 [지원 팀에 문의](https://go.microsoft.com/fwlink/?linkid=2079641)하여 사용 가능한 환경의 수를 늘리세요. 용량 및 추가 용량에 대한 자세한 내용은 [Dynamics 365 라이선스 가이드](https://go.microsoft.com/fwlink/?LinkId=866544)를 참조하십시오.

> [!TIP]
> 서비스를 사용해 보려면 [평가판 환경 설정](trial-signup.md)을 참조하세요.

## <a name="prerequisites"></a>전제 조건

환경을 만들거나 관리하려면 Customer Insights에 대한 [관리자 권한](permissions.md)이 필요합니다.

## <a name="start-the-environment-creation-process"></a>환경 생성 프로세스 시작

1. 환경 선택기를 열고 **+ 새로 만들기** 를 선택합니다.
  
   :::image type="content" source="media/environment-picker.png" alt-text="환경 선택기 선택.":::

1. 다음 섹션에 설명된 안내 환경에 따라 새 환경에 필요한 모든 정보를 제공하십시오. 이전에 환경을 구성한 경우 [구성 복사](#copy-the-environment-configuration)를 수행할 수도 있습니다.

## <a name="step-1-provide-basic-information"></a>1단계: 기본 정보 제공

**기본 정보** 단계에서 처음부터 환경을 생성할지 아니면 [다른 환경에서 데이터를 복사](#copy-the-environment-configuration)할지 선택합니다.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="새로운 Customer Insights 환경을 생성하기 위한 대화 상자.":::

다음 정보를 제공합니다.

- **이름**: 이 환경의 이름입니다. 기존 환경에서 복사한 경우 이 필드가 이미 채워져 있지만 변경할 수 있습니다.
- **비즈니스 선택**: 새로운 환경의 주요 대상 그룹을 선택합니다. 개별 소비자(B-to-C) 또는 [1비즈니스 계정](work-with-business-accounts.md)(B-to-B)으로 작업할 수 있습니다. 조직에서 소매업체나 커피숍과 같이 주로 개인과 비즈니스를 수행하는 경우 개별 소비자를 선택합니다. 주요 대상 그룹이 자동차 제조업체 또는 제지 회사와 같은 다른 회사인 경우 비즈니스 계정을 선택하십시오.
- **유형**: 프로덕션 환경을 만들지 샌드박스 환경을 만들지 선택합니다. 샌드박스 환경은 예약된 데이터 새로 고침을 허용하지 않으며 사전 구현 및 테스트를 위한 것입니다. 샌드박스 환경은 현재 선택된 프로덕션 환경과 동일한 기본 대상을 사용합니다.
- **지역**: 서비스가 배포되고 호스팅되는 지역입니다. [자신의 Azure Data Lake Storage 계정을 사용](own-data-lake-storage.md)하거나 [기존 Microsoft Dataverse 조직에 연결](customer-insights-dataverse.md)하려면 Customer Insights 환경이 동일한 지역에 있어야 합니다.

## <a name="step-2-configure-data-storage"></a>2단계: 데이터 저장소 구성

**데이터 저장소** 단계에서 Customer Insights 데이터를 저장할 위치를 선택합니다.

다음 두 가지 옵션 중에서 선택할 수 있습니다.

- **Customer Insights 스토리지**: 데이터 스토리지는 Customer Insights 팀에서 관리합니다. 기본 옵션이며 고유한 스토리지 계정에 데이터를 저장하기 위한 특정 요구 사항이 없는 한 이 옵션을 사용하는 것이 좋습니다.
- **Azure Data Lake Storage**: 데이터가 저장되는 위치를 완전히 제어할 수 있도록 데이터를 저장할 고유한 Azure Data Lake Storage 계정을 지정합니다. 자세한 내용은 [내 Azure Data Lake Storage 계정 사용](own-data-lake-storage.md)을 참조하십시오.

:::image type="content" source="media/data-storage-environment.png" alt-text="데이터를 저장할 기본 옵션을 선택합니다.":::

## <a name="step-3-connect-to-microsoft-dataverse"></a>3단계: Microsoft Dataverse에 연결

**Microsoft Dataverse** 단계를 통해 Customer Insights를 Dataverse 환경과 연결할 수 있습니다. Dataverse와 데이터를 공유하여 Dynamics 365 Marketing 또는 Power Apps의 모델 기반 애플리케이션과 같은 Dataverse를 기반으로 하는 비즈니스 애플리케이션과 함께 사용합니다.


고유한 Dataverse 환경이 없는 경우 이 필드를 비워두면 자동으로 생성됩니다.

자세한 내용은 [Microsoft Dataverse의 Customer Insights 데이터 작업](customer-insights-dataverse.md)을 참조하십시오.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="Microsoft Dataverse와의 데이터 공유는 새로운 환경에서 자동으로 활성화됩니다.":::

### <a name="step-4-finalize-the-settings"></a>4단계: 설정 완료

**검토** 단계에서 지정된 모든 설정을 살펴봅니다. 모든 것이 완료되면 **만들기** 를 선택하여 환경을 설정합니다.

나중에 일부 설정을 변경할 수 있습니다. 자세한 내용은 [환경 관리](manage-environments.md)를 참조하십시오.

## <a name="work-with-your-new-environment"></a>새로운 환경에서 작업

Customer Insights 구성을 시작하는 데 도움이 되는 다음 문서를 검토하십시오.

- [더 많은 사용자 추가 및 권한 할당](permissions.md).
- [데이터 원본](data-sources.md)을 수집하고 [데이터 통합 프로세스](data-unification.md)를 통해 실행하여 [통합 고객 프로필](customer-profiles.md)을 가져옵니다.
- [통합된 고객 프로필 보강](enrichment-hub.md) 또는 [예측 모델 실행](predictions-overview.md).
- 고객을 그룹화하는 [세그먼트 만들기](segments.md)를 수행하고 KPI를 검토하기 위한 [측정값](measures.md)을 만듭니다.
- 다른 애플리케이션에서 데이터의 하위 집합을 처리하기 위해 [연결](connections.md) 및 [내보내기를 설정](export-destinations.md)합니다.

## <a name="copy-the-environment-configuration"></a>환경 구성 복사

관리자는 새 환경을 만들 때 기존 환경에서 구성을 복사하도록 선택할 수 있습니다.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="환경 설정의 설정 옵션 스크린샷.":::

조직에서 데이터를 복사할 수 있는 사용 가능한 모든 환경 목록이 표시됩니다.

다음 구성 설정이 복사됩니다.

- Power Query를 통해 가져온 데이터 원본
- 데이터 통합 구성
- 세그먼트
- 측정값
- 관계
- 작업
- 검색 및 필터 인덱스
- 내보내기
- 일정 새로 고침
- 보강
- 예측 모델
- 역할 할당

## <a name="set-up-a-copied-environment"></a>복사한 환경 설정

환경 구성을 복사할 때 자격 증명을 확인하기 위해 몇 가지 추가 단계를 거쳐야 합니다.

- 고객 프로필. 먼저 데이터 원본을 인증 및 수집하고 데이터 통합을 실행하여 고객 프로필을 다시 만듭니다.
- 데이터 원본 자격 증명. 데이터 원본을 수동으로 인증하고 새로 고치려면 모든 데이터 원본에 대한 자격 증명을 제공해야 합니다.
- Common Data Model 폴더 및 Dataverse의 데이터 원본. 원본 환경에서와 동일한 이름으로 이러한 데이터 원본을 수동으로 생성해야 합니다.
- 내보내기 및 보강에 사용되는 연결 암호입니다. 연결을 다시 인증한 다음 보강 및 내보내기를 다시 활성화해야 합니다.

복사된 환경이 생성되면 확인 메시지가 표시됩니다. **데이터 원본으로 이동** 을 선택하여 데이터 원본 목록을 볼 수 있습니다.

모든 데이터 원본에 **자격 증명 필요** 상태가 표시됩니다. 데이터 원본을 편집하고 자격 증명 정보를 입력하여 새로 고치십시오.

:::image type="content" source="media/data-sources-copied.png" alt-text="복사되어 인증이 필요한 데이터 소스 목록.":::

데이터 원본을 새로 고친 후 **데이터** > **통합** 으로 이동합니다. 원본 환경에서 설정을 확인할 수 있습니다. 필요에 따라 편집하거나 **실행** 을 선택하여 데이터 통합 프로세스를 시작하고 통합 고객 엔터티를 만듭니다.

데이터 통합이 완료되면 **측정** 및 **세그먼트** 로 이동하여 이들도 새로 고칩니다.

내보내기 및 보강을 다시 활성화하기 전에 **관리자** > **연결** 로 이동하여 새 환경에서 연결을 다시 인증하십시오.

[!INCLUDE [footer-include](includes/footer-banner.md)]
