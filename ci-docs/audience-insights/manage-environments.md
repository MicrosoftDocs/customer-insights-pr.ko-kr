---
title: 환경 만들기 및 관리
description: 서비스에 등록하는 방법과 환경을 관리하는 방법을 알아봅니다.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 744f0bcbf5d2700363180f44e38d6dee9bf5df63
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270120"
---
# <a name="manage-environments"></a>환경 관리

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

이 문서에서는 새 조직을 만드는 방법과 환경을 프로비저닝하는 방법을 설명합니다.

## <a name="sign-up-and-create-an-organization"></a>조직 가입 및 만들기

1. [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) 웹 사이트로 이동

2. **시작** 을 선택합니다.

3. 원하는 가입 시나리오를 선택하고 해당 링크를 선택하십시오.

4. 이용 약관에 동의하고 **계속** 을 선택하여 조직 생성을 시작합니다.

5. 새로운 환경이 생성되면 다음으로 리디렉션됩니다.[Customer Insights](https://home.ci.ai.dynamics.com).

6. 데모 환경을 사용하여 앱을 탐색하거나 다음 섹션의 단계에 따라 새 환경을 만듭니다.

7. 환경 설정을 지정한 후 **만들기** 를 선택합니다.

8. 환경이 성공적으로 생성된 후 로그인됩니다.

## <a name="create-an-environment-in-an-existing-organization"></a>기존 조직에서 환경 만들기

다음과 같은 두 가지 방법으로 새 환경을 만들 수 있습니다. 완전히 새로운 구성을 지정하거나 기존 환경에서 일부 구성 설정을 복사할 수 있습니다.

환경을 만들려면:

1. 앱 헤더의 **환경** 선택기를 선택합니다.

1. **새로 만들기** 를 선택합니다.

   > [!div class="mx-imgBorder"]
   > ![환경 설정](media/environment-settings-dialog.png)

1. **새로운 환경 조성** 대화 상자에서 **새로운 환경** 을 선택합니다.

   [현재 환경에서 데이터 복사](#additional-considerations-for-copy-configuration-preview)하고 싶다면 **기존 환경에서 복사** 를 선택합니다. 조직에서 데이터를 복사할 수 있는 사용 가능한 모든 환경 목록이 표시됩니다.

1. 다음 정보를 제공합니다.
   - **이름**: 이 환경의 이름입니다. 기존 환경에서 복사한 경우 이 필드가 이미 채워져 있지만 변경할 수 있습니다.
   - **지역**: 서비스가 배포되고 호스팅되는 지역입니다.
   - **유형**: 프로덕션 환경을 만들지 샌드박스 환경을 만들지 선택합니다.

2. 필요에 따라 **고급 설정** 을 선택할 수 있습니다.

   - **모든 데이터 저장**: Customer Insights에서 생성된 출력 데이터를 저장할 위치를 지정합니다. **Customer Insights 저장소**(Customer Insights 팀에서 관리하는 Azure Data Lake) 및 **Azure Data Lake Storage Gen2**(자신의 Azure Data Lake Storage)의 두 가지 옵션이 있습니다. 기본적으로 Customer Insights 저장소 옵션이 선택되어 있습니다.

   > [!NOTE]
   > Azure Data Lake Storage에 데이터를 저장하면 데이터가 Dynamics 365 Customer Insights에서 데이터가 저장되는 위치와 다를 수 있으므로 해당 Azure Storage 계정의 적절한 지역에 데이터를 전송하고 저장한다는 데 동의하는 것입니다. [Microsoft 보안 센터에서 자세히 알아보십시오.](https://www.microsoft.com/trust-center)
   >
   > 현재 수집된 엔터티는 항상 Customer Insights 관리형 데이터 레이크에 저장됩니다.
   > 환경을 만들 때 선택한 동일한 Azure 지역의 Azure Data Lake Gen2 스토리지 계정만 지원합니다.
   > Azure Data Lake Gen2 계층 구조 네임스페이스(HNS)를 지원하는 저장소 계정만 지원합니다.

   - Azure Data Lake Storage Gen2 옵션의 경우 인증을 위해 리소스 기반 옵션과 구독 기반 옵션 중에서 선택할 수 있습니다. 자세한 내용은 [Azure 서비스 보안 주체를 사용하여 대상 그룹 인사이트를 Azure Data Lake Storage Gen2 계정에 연결](connect-service-principal.md)을 참조하세요. **컨테이너** 이름은 변경할 수 없으며 "customerinsights"가 됩니다.
   
   - [예측](predictions.md)을 사용하거나 Microsoft Dataverse를 기반으로 하는 응용 프로그램 및 솔루션과의 데이터 공유를 구성하려면 **Microsoft Dataverse와 데이터 공유 구성 및 추가 기능 사용** 에 Microsoft Dataverse 환경 URL을 제공하십시오. **데이터 공유 활성화** 를 선택하여 Customer Insights 출력 데이터를 Microsoft Dataverse 관리형 Data Lake와 공유합니다.

     > [!NOTE]
     > - 모든 데이터를 자체 Azure Data Lake Storage에 저장하는 경우 Microsoft Dataverse 관리형 Data Lake와의 데이터 공유는 현재 지원되지 않습니다.
     > - Microsoft Dataverse 관리형 Data Lake와의 데이터 공유를 활성화한 경우 [엔터티에서 누락된 값의 예측](predictions.md)은 현재 지원되지 않습니다.

     > [!div class="mx-imgBorder"]
     > ![Microsoft Dataverse와 데이터 공유를 활성화하는 구성 옵션](media/Datasharing-with-DataverseMDL.png)

   데이터 수집 또는 세그먼트 생성과 같은 프로세스를 실행하면 위에서 지정한 스토리지 계정에 해당 폴더가 생성됩니다. 데이터 파일과 model.json 파일이 생성되며 실행하는 프로세스에 따라 해당 하위 폴더에 추가됩니다.

   Customer Insights의 여러 환경을 만들고 해당 환경의 출력 엔터티를 스토리지 계정에 저장하도록 선택하면 컨테이너에 ci_<environmentid>가 있는 각 환경에 대해 별도의 폴더가 생성됩니다.

### <a name="additional-considerations-for-copy-configuration-preview"></a>복사 구성에 대한 추가 고려 사항 (미리보기)

다음 구성 설정이 복사됩니다.

- 기능 구성
- 수집한/가져온 데이터 원본
- 데이터 통합(맵, 일치, 병합) 구성
- 세그먼트
- 측정값
- 관계
- 활동 
- 검색 및 필터 인덱스
- 내보내기 대상
- 예약된 새로 고침
- 보강
- 모델 관리
- 역할 할당

다음 설정이 복사되지 *않습니다*.

- 고객 프로필.
- 데이터 원본 자격 증명. 모든 데이터 원본에 대한 자격 증명을 제공하고 데이터 원본을 수동으로 새로 고쳐야 합니다.
- Common Data Model 폴더 및 Common Data Service 관리 레이크의 데이터 원본. 원본 환경에서와 동일한 이름으로 해당 데이터 원본을 수동으로 생성해야 합니다.

환경을 복사하면 새 환경이 생성되었다는 확인 메시지가 표시됩니다. **데이터 원본으로 이동** 을 선택하여 데이터 원본 목록을 볼 수 있습니다.

모든 데이터 원본에 **자격 증명 필요** 상태가 표시됩니다. 데이터 원본을 편집하고 자격 증명 정보를 입력하여 새로 고치십시오.

> [!div class="mx-imgBorder"]
> ![데이터 원본 복사됨](media/data-sources-copied.png)

데이터 원본을 새로 고친 후 **데이터** > **통합** 으로 이동합니다. 원본 환경에서 설정을 확인할 수 있습니다. 필요에 따라 편집하거나 **실행** 을 선택하여 데이터 통합 프로세스를 시작하고 통합 고객 엔터티를 만듭니다.

데이터 통합이 완료되면 **측정** 및 **세그먼트** 로 이동하여 이들도 새로 고칩니다.

## <a name="edit-an-existing-environment"></a>기존 환경 편집

기존 환경의 세부 사항 중 일부를 편집할 수 있습니다.

1.  앱 헤더의 **환경** 선택기를 선택합니다.

2.  **편집** 아이콘을 선택합니다.

3. **환경 편집** 상자에서 환경의 **표시 이름** 을 업데이트할 수 있지만 **지역** 또는 **유형** 은 변경할 수 없습니다.

4. 환경이 데이터를 Azure Data Lake Storage Gen2에 저장하도록 구성된 경우 **계정 키** 를 업데이트할 수 있습니다. 그러나 **계정 이름** 또는 **컨테이너** 이름은 변경할 수 없습니다.

5. 선택적으로 계정 키 기반 연결에서 리소스 기반 또는 구독 기반 연결로 업데이트할 수 있습니다. 한 번 업그레이드하면 업데이트 후 계정 키로 되돌릴 수 없습니다. 자세한 내용은 [Azure 서비스 보안 주체를 사용하여 대상 그룹 인사이트를 Azure Data Lake Storage Gen2 계정에 연결](connect-service-principal.md)을 참조하세요. 연결을 업데이트할 때 **컨테이너** 정보를 변경할 수 없습니다.

## <a name="reset-an-existing-environment"></a>기존 환경 초기화

모든 구성을 삭제하고 수집된 데이터를 제거하려는 경우 관리자로서 환경을 빈 상태로 재설정할 수 있습니다.

1.  앱 헤더의 **환경** 선택기를 선택합니다. 

2.  재설정하려는 환경을 선택하고 줄임표 **...** 를 선택합니다. 

3. **재설정** 옵션을 선택합니다. 

4.  삭제를 확인하려면 환경 이름을 입력하고 **초기화** 를 선택합니다.

## <a name="delete-an-existing-environment-available-only-for-admins"></a>기존 환경 삭제(관리자만 사용 가능)

관리자는 관리하는 환경을 삭제할 수 있습니다.

1.  앱 헤더의 **환경** 선택기를 선택합니다.

2.  재설정하려는 환경을 선택하고 줄임표 **...** 를 선택합니다. 

3. **삭제** 옵션을 선택합니다. 

4.  삭제를 확인하려면 환경 이름을 입력하고 **삭제** 를 선택합니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]