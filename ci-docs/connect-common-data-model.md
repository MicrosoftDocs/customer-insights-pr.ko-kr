---
title: Common Data Model 데이터를 Azure Data Lake 계정에 연결
description: Azure Data Lake Storage를 사용하여 Common Data Model 데이터로 작업합니다.
ms.date: 05/24/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: 2e8564950a3269180a85f80fb736d2dcbd1b03b6
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833369"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Azure Data Lake 계정을 사용하여 Common Data Model 폴더에 연결

이 문서에서는 Azure Data Lake Storage Gen2 계정을 사용하여 Common Data Model 폴더에서 Dynamics 365 Customer Insights로 데이터를 수집하는 방법에 대한 정보를 제공합니다.

## <a name="important-considerations"></a>중요 사항

- Azure Data Lake의 데이터는 Common Data Model 표준을 따라야 합니다. 현재 다른 형식은 지원되지 않습니다.

- 데이터 수집은 Azure Data Lake *Gen2* 스토리지 계정을 독점적으로 지원합니다. Azure Data Lake Gen1 스토리지 계정을 사용하여 데이터를 수집할 수 없습니다.

- Azure Data Lake Storage 계정에는 [계층 구조 네임스페이스가 활성화](/azure/storage/blobs/data-lake-storage-namespace)되어 있어야 합니다.

- Azure 서비스 주체로 인증하려면 테넌트에 구성되어 있는지 확인하세요. 자세한 내용은 [Azure 서비스 주체를 사용하여 Azure Data Lake Storage Gen2 계정에 연결](connect-service-principal.md)을 참조하십시오.

- 연결하고 데이터를 수집하려는 Azure Data Lake는 Dynamics 365 Customer Insights 환경과 동일한 Azure 지역에 있어야 합니다. 다른 Azure 지역의 데이터 레이크에서 Common Data Model 폴더에 대한 연결은 지원되지 않습니다. 환경의 Azure 지역을 알아보려면 Customer Insights에서 **관리자** > **시스템** > **정보** 로 이동하세요.

- 온라인 서비스에 저장된 데이터는 Dynamics 365 Customer Insights에서 데이터가 처리되거나 저장되는 위치와 다른 위치에 저장될 수 있습니다. 온라인 서비스에서 데이터를 가져오거나 이에 연결하면 해당 데이터가 Dynamics 365 Customer Insights에 전송되거나 저장될 수 있음에 동의하는 것입니다. [Microsoft 보안 센터에서 자세히 알아보십시오.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-model-folder"></a>Common Data Model 폴더에 연결

1. **데이터** > **데이터 원본** 으로 이동.

1. **데이터 원본 추가** 를 선택합니다.

1. **Azure Data Lake Storage** 를 선택하고 데이터 원본의 **이름** 을 입력하고 **다음** 을 선택합니다.

   - 메시지가 표시되면 해당 산업과 관련된 샘플 데이터 세트 중 하나를 선택한 후 **다음** 을 선택합니다.

1. 인증을 위해 리소스 기반 옵션과 구독 기반 옵션 중에서 사용하여 선택할 수 있습니다. 자세한 내용은 [Azure 서비스 주체를 사용하여 Azure Data Lake Storage Gen2 계정에 연결](connect-service-principal.md)을 참조하십시오. **서버 주소** 를 입력하고 **로그인** 을 선택한 후 **다음** 을 선택합니다.
   > [!div class="mx-imgBorder"]
   > ![Azure Data Lake에 대한 새 연결 세부 정보를 입력하는 대화 상자.](media/enter-new-storage-details.png)
   > [!NOTE]
   > 스토리지 계정의 컨테이너에 대해 다음 역할 중 하나가 필요하고 데이터 원본를 생성해야 합니다.
   >
   >  - Storage Blob Data Reader는 스토리지 계정에서 데이터를 읽고 Customer Insights로 수집하는 데 충분합니다. 
   >  - Customer Insights에서 매니페스트 파일을 직접 편집하려면 Storage Blob 데이터 기여자 또는 담당자가 필요합니다.

1. **Common Data Model 폴더 선택** 대화상자에서 데이터를 가져올 model.json 또는 manifest.json 파일을 선택하고 **다음** 을 선택합니다.
   > [!NOTE]
   > 환경의 다른 데이터 원본과 연결된 model.json 또는 manifest.json 파일은 목록에 표시되지 않습니다.

1. 선택한 model.json 또는 manifest.json 파일에서 사용 가능한 엔터티 목록이 표시됩니다. 사용 가능한 엔터티 목록을 검토한 후 엔터티를 선택한 다음 **저장** 을 선택합니다. 선택한 모든 항목이 새 데이터 원본에서 수집됩니다.
   > [!div class="mx-imgBorder"]
   > ![model.json 파일의 엔터티 목록을 표시하는 대화 상자.](media/review-entities.png)

1. 데이터 프로파일링을 사용할 수 있도록 설정할 데이터 엔터티를 표시한 후 **저장** 을 선택합니다. 데이터 프로파일링을 통해 분석 및 기타 기능을 사용할 수 있습니다. 엔터티에서 모든 특성을 선택하는 전체 엔터티를 선택하거나 선택한 특정 특성을 선택할 수 있습니다. 기본적으로 데이터 프로파일링에 대해 활성화된 엔터티가 없습니다.
   > [!div class="mx-imgBorder"]
   > ![데이터 프로파일링을 보여주는 대화 상자.](media/dataprofiling-entities.png)

1. 선택 사항을 저장하면 **데이터 원본** 페이지가 열립니다. 이제 Common Data Model 폴더 연결이 데이터 원본으로 표시됩니다.

> [!NOTE]
> model.json 파일 또는 manifest.json은 동일한 환경에서 하나의 데이터 원본에만 연결할 수 있습니다. 그러나 여러 환경의 데이터 원본에 동일한 model.json 또는 manifest.json 파일을 사용할 수 있습니다.

## <a name="edit-a-common-data-model-folder-data-source"></a>Common Data Model 폴더 데이터 원본 편집

Common Data Model 폴더가 포함된 스토리지 계정의 액세스 키를 업데이트할 수 있습니다. model.json 또는 manifest.json 파일을 변경할 수도 있습니다. 저장소 계정과 다른 컨테이너에 연결하거나 계정 이름을 변경하려면 [새로운 데이터 원본 연결을 만듭니다](#connect-to-a-common-data-model-folder).

1. **데이터** > **데이터 원본** 으로 이동.

2. 업데이트하려는 데이터 원본 옆에 있는 세로 줄임표(&vellip;)를 선택합니다.

3. 목록에서 **편집** 옵션을 선택합니다.

4. 선택적으로 **액세스 키** 를 업데이트하고 **다음** 을 선택합니다.

   ![기존 데이터 원본에 대한 액세스 키를 편집하고 업데이트하는 대화 상자.](media/edit-access-key.png)

5. 선택적으로 계정 키 기반 연결에서 리소스 기반 또는 구독 기반 연결로 업데이트할 수 있습니다. 자세한 내용은 [Azure 서비스 주체를 사용하여 Azure Data Lake Storage Gen2 계정에 연결](connect-service-principal.md)을 참조하십시오. 연결을 업데이트할 때 **컨테이너** 정보를 변경할 수 없습니다.
   > [!div class="mx-imgBorder"]

   > ![Azure Data Lake에 대한 연결 세부 정보를 기존 스토리지 계정에 입력하는 대화 상자.](media/enter-existing-storage-details.png)

6. 선택적으로, 컨테이너와 다른 엔터티 집합이 있는 다른 model.json 또는 manifest.json 파일을 선택합니다.

7. 선택적으로 수집할 추가 엔터티를 선택할 수 있습니다. 종속성이 없는 경우 이미 선택된 엔터티를 제거할 수도 있습니다.

   > [!IMPORTANT]
   > 기존 model.json 또는 manifest.json 파일과 엔티티 집합에 대한 종속성이 있는 경우 오류 메시지가 표시되고 다른 model.json 또는 manifest.json 파일을 선택할 수 없습니다. model.json 또는 manifest.json 파일을 변경하기 전에 이러한 종속성을 제거하거나 종속성 제거를 방지하기 위해 사용할 model.json 또는 manifest.json 파일로 새 데이터 원본를 만드십시오.

8. 선택적으로 추가 특성 또는 엔터티를 선택하여 데이터 프로파일링을 사용 설정하거나 이미 선택한 항목을 사용 중지할 수 있습니다.

[!INCLUDE [footer-include](includes/footer-banner.md)]