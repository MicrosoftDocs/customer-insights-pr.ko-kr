---
title: Customer Insights에서 환경 만들기
description: Dynamics 365 Customer Insights에 대한 라이선스 구독으로 환경을 만드는 단계.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 4f26220f6ba7f5b5ae00c11216129f9ad814b77d
ms.sourcegitcommit: 626d485dae1e001e63e4d4bf78f6770766822ba0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/06/2021
ms.locfileid: "7892346"
---
# <a name="create-an-environment-in-audience-insights"></a>대상 그룹 인사이트에서 환경 만들기

이 문서에서는 조직에서 Dynamics 365 Customer Insights 구독을 구입한 후 새 환경을 만드는 방법을 설명합니다. 

조직은 각 Customer Insights 라이선스에 대해 *두 개* 의 환경을 만들 수 있습니다. 조직에서 라이선스를 두 개 이상 구입한 경우 [지원 팀에 문의](https://go.microsoft.com/fwlink/?linkid=2079641)하여 사용 가능한 환경의 수를 늘리세요. 용량 및 추가 용량에 대한 자세한 내용은 [Dynamics 365 라이선스 가이드](https://go.microsoft.com/fwlink/?LinkId=866544)를 다운로드하십시오.

> [!NOTE]
> 서비스를 사용해 보려면 [평가판 환경 설정](../trial-signup.md)을 참조하세요.

## <a name="create-a-new-environment"></a>새 환경 만들기

Customer Insights에 대한 구독 라이선스를 구입한 후 Microsoft 365 테넌트의 전역 관리자는 환경을 만들도록 초대하는 이메일을 받게 됩니다. 시작하려면 [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start)로 이동하십시오. 

안내식 경험은 새로운 환경에 필요한 모든 정보를 수집하는 단계를 안내합니다. 환경을 만들거나 관리하려면 대상 그룹 인사이트에 대한 [관리자 권한](permissions.md)이 필요합니다.

1. 대상 그룹 인사이트에서 환경 선택기를 열고 **+ 새로 만들기** 를 선택합니다.
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="환경 선택기 선택.":::

1. 다음 섹션에 설명된 안내식 경험을 따릅니다.

### <a name="step-1-provide-environment-information"></a>1단계: 환경 정보 제공

**기본 정보** 단계에서 처음부터 환경을 생성할지 아니면 [다른 환경에서 데이터를 복사](manage-environments.md#copy-the-environment-configuration)할지 선택합니다.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="새로운 Customer Insights 환경을 생성하기 위한 대화 상자.":::

다음 정보를 제공합니다.
   - **이름**: 이 환경의 이름입니다. 기존 환경에서 복사한 경우 이 필드가 이미 채워져 있지만 변경할 수 있습니다.
   - **비즈니스 선택**: 새로운 환경의 주요 대상 그룹을 선택합니다. 개별 소비자(B-to-C) 또는 [1비즈니스 계정](work-with-business-accounts.md)(B-to-B)으로 작업할 수 있습니다.
   - **유형**: 프로덕션 환경을 만들지 샌드박스 환경을 만들지 선택합니다. 샌드박스 환경은 예약된 데이터 새로 고침을 허용하지 않으며 사전 구현 및 테스트를 위한 것입니다. 샌드박스 환경은 현재 선택된 프로덕션 환경과 동일한 기본 대상을 사용합니다.
   - **지역**: 서비스가 배포되고 호스팅되는 지역입니다.

### <a name="step-2-configure-data-storage"></a>2단계: 데이터 저장소 구성

**데이터 저장소** 단계에서 대상 그룹 인사이트의 데이터를 저장할 위치를 선택합니다.

두 가지 옵션이 있습니다. **Customer Insights 스토리지**(Customer Insights 팀에서 관리하는 Azure Data Lake) 및 **Azure Data Lake Storage**(사용자의 Azure Data Lake Storage). 기본적으로 Customer Insights 저장소 옵션이 선택되어 있습니다.

:::image type="content" source="media/data-storage-environment.png" alt-text="대상 인사이트 데이터를 저장할 Azure Data Lake Storage를 선택함.":::

Azure Data Lake Storage에 데이터를 저장하면 해당 Azure Storage 계정에 해당하는 지리적 위치로 데이터가 전송되고 저장된다는 데 동의하는 것입니다. 이 위치는 데이터가 저장된 Dynamics 365 Customer Insights의 위치와 다를 수 있습니다. [Microsoft 보안 센터](https://www.microsoft.com/trust-center)에서 자세히 알아보세요.

> [!NOTE]
> Customer Insights는 현재 다음을 지원합니다.
> - Microsoft Dataverse 관리 Data Lake에 저장된 Power BI 데이터 흐름에서 수집된 엔터티입니다.  
> - 환경을 만들 때 선택한 동일한 Azure 지역의 Azure Data Lake Storage 계정입니다.
> - *계층 구조 네임스페이스* 가 사용된 Azure Data Lake Storage 계정입니다.

Azure Data Lake Storage 옵션의 경우 인증을 위해 리소스 기반 옵션과 구독 기반 옵션 중에서 선택할 수 있습니다. 자세한 내용은 [Azure 서비스 주체를 사용하여 Azure Data Lake Storage 계정에 연결](connect-service-principal.md)을 참조하십시오. **컨테이너** 이름은 `customerinsights`이며 변경할 수 없습니다.

데이터 수집과 같은 시스템 프로세스가 완료되면 시스템은 지정한 스토리지 계정에 해당 폴더를 만듭니다. 데이터 파일과 *model.json* 파일이 생성되어 프로세스 이름을 기반으로 폴더에 추가됩니다.

Customer Insights의 여러 환경을 만들고 해당 환경의 출력 엔터티를 스토리지 계정에 저장하도록 선택하면 Customer Insights는 컨테이너에 `ci_environmentID`가 있는 각 환경에 대해 별도의 폴더를 만듭니다.

### <a name="step-3-connect-to-microsoft-dataverse"></a>3단계: Microsoft Dataverse에 연결
   
**Microsoft Dataverse** 단계를 통해 Customer Insights를 Dataverse 환경과 연결할 수 있습니다.

[기본 예측 모델](predictions-overview.md#out-of-box-models)을 사용하려면 Dataverse와 데이터 공유를 구성하세요. 또는 조직에서 관리하는 Microsoft Dataverse 환경 URL을 제공하여 온-프레미스 데이터 원본에서 데이터 수집을 활성화할 수 있습니다. **데이터 공유 활성화** 를 선택하여 Customer Insights 출력 데이터를 Dataverse 관리형 Data Lake와 공유합니다.

> [!IMPORTANT]
> 데이터 공유를 활성화하려면 Customer Insights 및 Dataverse가 동일한 지역에 있어야 합니다.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Microsoft Dataverse와 데이터 공유를 활성화하는 구성 옵션":::

> [!NOTE]
> Customer Insights는 다음 데이터 공유 시나리오를 지원하지 않습니다.
> - 모든 데이터를 자체 Azure Data Lake Storage에 저장하면 Dataverse 관리형 데이터 레이크와 데이터 공유를 활성화할 수 없습니다.
> - Dataverse와 데이터 공유를 사용 설정하면 [엔터티에서 예측되거나 누락된 값 만들기](predictions.md)가 가능하지 않습니다.

### <a name="step-4-finalize-the-settings"></a>4단계: 설정 완료

**검토** 단계에서 지정된 모든 설정을 살펴봅니다. 모든 것이 완료되면 **만들기** 를 선택하여 환경을 설정합니다. 

나중에 대부분의 설정을 변경할 수도 있습니다. 자세한 내용은 [환경 관리](manage-environments.md)를 참조하십시오.

## <a name="work-with-your-new-environment"></a>새로운 환경에서 작업

Customer Insights 구성을 시작하는 데 도움이 되는 다음 문서를 검토하십시오. 

- [더 많은 사용자 추가 및 권한 할당](permissions.md).
- [데이터 원본](data-sources.md)을 수집하고 [데이터 통합 프로세스](data-unification.md)를 통해 실행하여 [통합 고객 프로필](customer-profiles.md)을 가져옵니다.
- [통합된 고객 프로필 보강](enrichment-hub.md) 또는 [예측 모델 실행](predictions-overview.md).
- 고객을 그룹화하는 [세그먼트 만들기](segments.md)를 수행하고 KPI를 검토하기 위한 [측정값](measures.md)을 만듭니다.
- 다른 애플리케이션에서 데이터의 하위 집합을 처리하기 위해 [연결](connections.md) 및 [내보내기를 설정](export-destinations.md)합니다.
