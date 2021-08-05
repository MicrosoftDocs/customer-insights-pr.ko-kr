---
title: Customer Insights 유료 라이선스 생성 및 구성
description: Dynamics 365 Customer Insights에 대한 라이선스 구독을 받고 구성하는 단계입니다.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: f8cf1be97ee8af46145a450009fd278b1821f8fe
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650488"
---
# <a name="get-started-with-a-paid-subscription"></a>유료 구독 시작하기

이 문서에서는 조직에서 Dynamics 365 Customer Insights 구독을 구입한 후 새 환경을 만드는 방법을 설명합니다. Customer Insights 구매를 원할 경우 [Dynamics 365 Customer Insights 웹사이트](https://dynamics.microsoft.com/ai/customer-insights/)에 연락처가 나와 있습니다. 

서비스 및 기능을 사용해 보려면 [평가판 환경 설정](get-started-trial.md)을 참조하십시오.

## <a name="create-an-environment-in-an-existing-organization"></a>기존 조직에서 환경 만들기

Customer Insights에 대한 구독 라이선스를 구입한 후 Microsoft 365 테넌트의 전역 관리자는 환경을 만들도록 초대하는 이메일을 받게 됩니다. 시작하려면 [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start)로 이동하십시오. 

Customer Insights는 사용자별로 라이선스가 부여되지 않으므로 라이선스 영역에 표시되지 않습니다. Microsoft 365 관리 센터에서 라이선스를 찾고 있다면 **내 제품** 으로 이동하십시오. 

> [!NOTE]
> 조직은 각 Customer Insights 라이선스에 대해 *두 개* 의 환경을 만들 수 있습니다. 조직에서 라이선스를 두 개 이상 구매하는 경우 [지원팀에 문의](https://go.microsoft.com/fwlink/?linkid=2079641)하여 사용 가능한 환경의 수를 늘리세요. 용량 및 추가 용량에 대한 자세한 내용은 [Dynamics 365 라이선스 가이드](https://go.microsoft.com/fwlink/?LinkId=866544)를 다운로드하십시오.

환경을 만들려면:

1. **환경 만들기** 대화 상자에서 **새로운 환경** 을 선택합니다.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="새로운 Customer Insights 환경을 생성하기 위한 대화 상자.":::

   환경 설정을 처음부터 시작하는 것이 좋습니다. 그러나 관리자 또는 평가판 환경의 구성원인 경우 **기존 환경에서 복사** 를 선택하여 [다른 환경에서 데이터를 복사](manage-environments.md#copy-the-environment-configuration)할 수 있습니다. 조직에서 데이터를 복사할 수 있는 사용 가능한 모든 환경 목록이 표시됩니다.

1. 다음 정보를 제공합니다.
   - **이름**: 이 환경의 이름입니다. 기존 환경에서 복사한 경우 이 필드가 이미 채워져 있지만 변경할 수 있습니다.
   - **지역**: 서비스가 배포되고 호스팅되는 지역입니다.
   - **유형**: 프로덕션 환경을 만들지 샌드박스 환경을 만들지 선택합니다. 샌드박스 환경은 예약된 데이터 새로 고침을 허용하지 않으며 사전 구현 및 테스트를 위한 것입니다.
   
1. 필요에 따라 **고급 설정** 을 선택할 수 있습니다.

   - **모든 데이터 저장**: Customer Insights에서 생성된 출력 데이터를 저장할 위치를 지정합니다. 두 가지 옵션이 있습니다. **Customer Insights 스토리지**(Customer Insights 팀에서 관리하는 Azure Data Lake) 및 **Azure Data Lake Storage**(사용자의 Azure Data Lake Storage). 기본적으로 Customer Insights 저장소 옵션이 선택되어 있습니다.

     > [!NOTE]
     > Azure Data Lake Storage에 데이터를 저장하면 데이터가 Dynamics 365 Customer Insights에서 데이터가 저장되는 위치와 다를 수 있으므로 해당 Azure Storage 계정의 적절한 지역에 데이터를 전송하고 저장한다는 데 동의하는 것입니다. [Microsoft 보안 센터에서 자세히 알아보십시오.](https://www.microsoft.com/trust-center)
     >
     > 현재 Power BI 데이터 흐름에서 수집된 엔터티는 Microsoft Dataverse 관리형 Data Lake에 저장됩니다. 
     > 
     > 환경을 만들 때 선택한 동일한 Azure 지역의 Azure Data Lake Storage 계정만 지원합니다. 
     > 
     > 계층 구조 네임스페이스가 사용 설정된 Azure Data Lake Storage 계정만 지원합니다.


   - Azure Data Lake Storage 옵션의 경우 인증을 위해 리소스 기반 옵션과 구독 기반 옵션 중에서 선택할 수 있습니다. 자세한 내용은 [Azure 서비스 보안 주체를 사용하여 대상 그룹 인사이트를 Azure Data Lake Storage Gen2 계정에 연결](connect-service-principal.md)을 참조하세요. **컨테이너** 이름은 변경할 수 없으며 `customerinsights`가 됩니다.
   
   - [기본 제공 모델](predictions-overview.md#out-of-box-models)을 사용하려면, Microsoft Dataverse와 데이터 공유를 구성하거나 온-프레미스 데이터 원본에서 데이터 수집 활성화, **Microsoft Dataverse에서 데이터 공유 구성 및 추가 기능 활성화** 에서 Microsoft Dataverse 환경 URL을 제공합니다. **데이터 공유 활성화** 를 선택하여 Customer Insights 출력 데이터를 Microsoft Dataverse 관리형 Data Lake와 공유합니다.

     > [!NOTE]
     > - 모든 데이터를 자체 Azure Data Lake Storage에 저장하는 경우 Microsoft Dataverse 관리형 Data Lake와의 데이터 공유는 현재 지원되지 않습니다.
     > - [엔터티에서 누락된 값의 예측](predictions.md)은 Microsoft Dataverse 관리형 Data Lake와의 데이터 공유를 활성화할 때 현재 지원되지 않습니다.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Microsoft Dataverse와 데이터 공유를 활성화하는 구성 옵션":::

   데이터 수집과 같은 시스템 프로세스가 완료되면 지정한 스토리지 계정에 해당 폴더가 생성됩니다. 데이터 파일과 model.json 파일이 생성되어 프로세스 이름을 기반으로 폴더에 추가됩니다.

   Customer Insights의 여러 환경을 만들고 해당 환경의 출력 엔터티를 스토리지 계정에 저장하도록 선택하면 컨테이너에 ci_<environmentid>가 있는 각 환경에 대해 별도의 폴더가 생성됩니다.

1. **만들기** 를 선택하여 환경을 설정합니다. 

## <a name="configure-an-environment"></a>환경 구성

Customer Insights 구성을 시작하는 데 도움이 되는 다음 문서를 검토하십시오. 

- [더 많은 사용자 추가 및 권한 할당](permissions.md).
- [데이터 원본](data-sources.md)을 수집하고 [데이터 통합 프로세스](data-unification.md)를 통해 실행하여 [통합 고객 프로필](customer-profiles.md)을 가져옵니다.
- [통합된 고객 프로필 보강](enrichment-hub.md) 또는 [예측 모델 실행](predictions-overview.md).
- [세그먼트](segments.md)를 만들어 고객을 그룹화하고 [측정](measures.md) 검토 KPI를 만듭니다.
- [연결](connections.md) 및 [내보내기](export-destinations.md)를 설정하여 다른 응용 프로그램에서 데이터의 하위 집합을 처리합니다.
