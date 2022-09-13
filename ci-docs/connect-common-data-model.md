---
title: Azure Data Lake 계정을 사용하여 Common Data Model 폴더에 연결
description: Azure Data Lake Storage를 사용하여 Common Data Model 데이터로 작업합니다.
ms.date: 07/27/2022
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: d79b2d34e425e123224209814fef6e367c77c813
ms.sourcegitcommit: d7054a900f8c316804b6751e855e0fba4364914b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/02/2022
ms.locfileid: "9396093"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Azure Data Lake Storage에서 데이터에 연결

Azure Data Lake Storage Gen2 계정을 사용하여 Dynamics 365 Customer Insights로 데이터를 수집합니다. 데이터 수집은 전체 또는 증분일 수 있습니다.

## <a name="prerequisites"></a>전제 조건

- 데이터 수집은 Azure Data Lake Storage *Gen2* 계정만 지원합니다. Data Lake Storage Gen1 계정을 사용하여 데이터를 수집할 수 없습니다.

- Azure Data Lake Storage 계정에는 [계층 구조 네임스페이스가 활성화](/azure/storage/blobs/data-lake-storage-namespace)되어 있어야 합니다. 데이터는 루트 폴더를 정의하고 각 엔터티에 대한 하위 폴더가 있는 계층적 폴더 형식으로 저장해야 합니다. 하위 폴더에는 전체 데이터 또는 증분 데이터 폴더가 있을 수 있습니다.

- Azure 서비스 주체로 인증하려면 테넌트에 구성되어 있는지 확인하세요. 자세한 내용은 [Azure 서비스 주체를 사용하여 Azure Data Lake Storage Gen2 계정에 연결](connect-service-principal.md)을 참조하십시오.

- 연결하고 데이터를 수집하려는 Azure Data Lake Storage는 Dynamics 365 Customer Insights 환경과 동일한 Azure 지역에 있어야 합니다. 다른 Azure 지역의 데이터 레이크에서 Common Data Model 폴더에 대한 연결은 지원되지 않습니다. 환경의 Azure 지역을 알아보려면 Customer Insights에서 **관리자** > **시스템** > **정보** 로 이동하세요.

- 온라인 서비스에 저장된 데이터는 Dynamics 365 Customer Insights에서 데이터가 처리되거나 저장되는 위치와 다른 위치에 저장될 수 있습니다. 온라인 서비스에서 데이터를 가져오거나 이에 연결하면 해당 데이터가 Dynamics 365 Customer Insights에 전송되거나 저장될 수 있음에 동의하는 것입니다. [Microsoft 보안 센터에서 자세히 알아보십시오.](https://www.microsoft.com/trust-center)

- Customer Insights 서비스 주체는 스토리지 계정에 액세스하려면 다음 역할 중 하나에 있어야 합니다. 자세한 내용은 [서비스 주체에 스토리지 계정에 액세스할 수 있는 권한 부여](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account)를 참조하세요.
  - 스토리지 Blob 데이터 Reader
  - 스토리지 Blob 데이터 담당자
  - Storage Blob 데이터 Contributor

- 데이터 원본 연결을 설정하는 사용자에게는 스토리지 계정에 대한 최소한의 Storage Blob Data Contributor 권한이 필요합니다.

- Data Lake Storage의 데이터는 데이터 저장을 위한 Common Data Model 표준을 따라야 하며 데이터 파일(*.csv 또는 *.parquet)의 스키마를 나타내는 공통 데이터 모델 매니페스트가 있어야 합니다. 매니페스트는 엔터티 열 및 데이터 형식, 데이터 파일 위치 및 파일 형식과 같은 엔터티의 세부 정보를 제공해야 합니다. 자세한 내용은 [Common Data Model 매니페스트](/common-data-model/sdk/manifest)를 참조하세요. 매니페스트가 없는 경우 Storage Blob 데이터 소유자 또는 Storage Blob 데이터 기여자 액세스 권한이 있는 관리자는 데이터를 수집할 때 스키마를 정의할 수 있습니다.

## <a name="connect-to-azure-data-lake-storage"></a>Azure Data Lake Storage에 연결

1. **데이터** > **데이터 원본** 으로 이동.

1. **데이터 원본 추가** 를 선택합니다.

1. **Azure Data Lake Storage** 를 선택합니다.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Azure Data Lake에 대한 연결 세부 정보를 입력하는 대화 상자입니다." lightbox="media/data_sources_ADLS.png":::

1. 데이터 소스의 **이름** 과 **설명**(선택 사항)을 입력합니다. 이름은 데이터 원본을 고유하게 식별하며 다운스트림 프로세스에서 참조되며 변경할 수 없습니다.

1. **다음을 사용하여 스토리지 연결** 에 대해 다음 옵션 중 하나를 선택합니다. 자세한 내용은 [Azure 서비스 주체를 사용하여 Azure Data Lake Storage Gen2 계정에 Customer Insights 연결](connect-service-principal.md)을 참조하세요.

   - **Azure 리소스**: **리소스 ID** 를 입력합니다. 선택적으로 Azure Private Link를 통해 스토리지 계정에서 데이터를 수집하려는 경우 **프라이빗 링크 사용** 을 선택합니다. 자세한 내용은 [프라이빗 링크](security-overview.md#set-up-an-azure-private-link)를 참조하세요.
   - **Azure 구독**: **구독** 을 선택한 다음 **리소스 그룹** 및 **스토리지 계정** 을 선택합니다. 선택적으로 Azure Private Link를 통해 스토리지 계정에서 데이터를 수집하려는 경우 **프라이빗 링크 사용** 을 선택합니다. 자세한 내용은 [프라이빗 링크](security-overview.md#set-up-an-azure-private-link)를 참조하세요.
  
   > [!NOTE]
   > 데이터 원본을 만들려면 컨테이너 또는 스토리지 계정에 대해 다음 역할 중 하나가 필요합니다.
   >
   >  - Storage Blob Data Reader는 스토리지 계정에서 데이터를 읽고 Customer Insights로 수집하는 데 충분합니다.
   >  - Customer Insights에서 매니페스트 파일을 직접 편집하려면 Storage Blob 데이터 기여자 또는 담당자가 필요합니다.  
  
1. 데이터를 가져올 데이터 및 스키마(model.json 또는 manifest.json 파일)가 포함된 **컨테이너** 의 이름을 선택하고 **다음** 을 선택합니다.
   > [!NOTE]
   > 환경의 다른 데이터 원본과 연결된 model.json 또는 manifest.json 파일은 목록에 표시되지 않습니다. 그러나 여러 환경의 데이터 원본에 동일한 model.json 또는 manifest.json 파일을 사용할 수 있습니다.

1. 새 스키마를 생성하려면 [새 스키마 파일 생성](#create-a-new-schema-file)으로 이동합니다.

1. 기존 스키마를 사용하려면 model.json 또는 manifest.cdm.json 파일이 포함된 폴더로 이동합니다. 디렉터리 내에서 검색하여 파일을 찾을 수 있습니다.

1. json 파일을 선택하고 **다음** 을 선택합니다. 사용 가능한 엔터티 목록이 표시됩니다.

   :::image type="content" source="media/review-entities.png" alt-text="선택할 엔터티 목록의 대화 상자":::

1. 포함할 엔터티를 선택합니다.

   :::image type="content" source="media/ADLS_required.png" alt-text="기본 키에 필수를 표시하는 대화 상자":::

   > [!TIP]
   > JSON 편집 인터페이스에서 엔터티를 편집하려면 해당 엔터티를 선택하고 나서 **스키마 파일 편집** 을 선택합니다. 변경하고 **저장** 을 선택합니다.

1. 증분 수집이 필요한 선택한 엔터티의 경우 **증분 새로 고침** 아래에 **필수** 가 표시됩니다. 이러한 각 엔터티에 대해서는 [Azure Data Lake 데이터 원본에 대한 증분 새로 고침 구성](incremental-refresh-data-sources.md)을 참조하세요.

1. 기본 키가 정의되지 않은 선택된 엔터티의 경우 **기본 키** 아래에 **필수** 가 표시됩니다. 이러한 각 엔터티에 대해 다음을 수행합니다.
   1. **필수** 를 선택합니다. **엔티티 편집** 패널이 표시됩니다.
   1. **기본 키** 를 선택합니다. 기본 키는 엔터티에 고유한 특성입니다. 특성이 유효한 기본 키가 되려면 중복 값, 누락 된 값 또는 null 값을 포함하지 않아야 합니다. 문자열, 정수 및 GUID 데이터 유형 특성은 기본 키로 지원됩니다.
   1. 선택적으로 파티션 패턴을 변경합니다.
   1. **닫기** 를 선택하여 패널을 저장하고 닫습니다.

1. 포함된 각 엔터티의 **특성** 수를 선택합니다. **특성 관리** 페이지가 표시됩니다.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="데이터 프로파일링을 선택하는 대화 상자입니다.":::

   1. 새 특성을 생성하거나 기존 특성을 편집 또는 삭제합니다. 이름, 데이터 형식을 변경하거나 의미 유형을 추가할 수 있습니다.
   1. 분석 및 기타 기능을 활성화하려면 전체 엔터티 또는 특정 특성에 대한 **데이터 프로파일링** 을 선택합니다. 기본적으로 데이터 프로파일링에 대해 활성화된 엔터티가 없습니다.
   1. **완료** 를 선택합니다.

1. **저장** 을 선택합니다. **데이터 원본** 페이지가 열리고 **새로 고침 중** 상태의 새 데이터 원본이 표시됩니다.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

데이터를 로드하는 데 시간이 걸릴 수 있습니다. 새로 고침이 완료되면, 수집된 데이터를 [**엔터티**](entities.md) 페이지에서 검토할 수 있습니다.

### <a name="create-a-new-schema-file"></a>새 스키마 파일 만들기

1. **새 스키마 파일** 을 선택합니다.

1. 파일의 이름을 입력하고 **저장** 을 선택합니다.

1. **새 엔터티** 를 선택합니다. **새 엔티티** 패널이 표시됩니다.

1. 엔터티 이름을 입력하고 **데이터 파일 위치** 를 선택합니다.
   - **여러 .csv 또는 .parquet 파일**: 루트 폴더를 찾아 패턴 유형을 선택하고 표현식을 입력합니다.
   - **단일 .csv 또는 .parquet 파일**: .csv 또는 .parquet 파일을 찾아 선택합니다.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="데이터 파일 위치가 강조 표시된 새 엔터티를 만드는 대화 상자입니다.":::

1. **저장** 을 선택합니다.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="특성을 정의하거나 자동 생성하는 대화 상자입니다.":::

1. **특성 정의** 를 선택하여 특성을 수동으로 추가하거나 **자동 생성** 을 선택합니다. 특성을 정의하려면 이름을 입력하고 데이터 형식 및 선택적 의미 유형을 선택합니다. 자동 생성 특성의 경우:

   1. 특성이 자동 생성된 후 **특성 검토** 를 선택합니다. **특성 관리** 페이지가 표시됩니다.

   1. 데이터 형식이 각 특성에 대해 올바른지 확인합니다.

   1. 분석 및 기타 기능을 활성화하려면 전체 엔터티 또는 특정 특성에 대한 **데이터 프로파일링** 을 선택합니다. 기본적으로 데이터 프로파일링에 대해 활성화된 엔터티가 없습니다.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="데이터 프로파일링을 선택하는 대화 상자입니다.":::

   1. **완료** 를 선택합니다. **엔터티 선택** 페이지가 표시됩니다.

1. 해당되는 경우 엔터티 및 특성을 계속 추가합니다.

1. 모든 엔터티가 추가된 후 **포함** 을 선택하여 데이터 원본 수집에 엔터티를 포함합니다.

   :::image type="content" source="media/ADLS_required.png" alt-text="기본 키에 필수를 표시하는 대화 상자":::

1. 증분 수집이 필요한 선택한 엔터티의 경우 **증분 새로 고침** 아래에 **필수** 가 표시됩니다. 이러한 각 엔터티에 대해서는 [Azure Data Lake 데이터 원본에 대한 증분 새로 고침 구성](incremental-refresh-data-sources.md)을 참조하세요.

1. 기본 키가 정의되지 않은 선택된 엔터티의 경우 **기본 키** 아래에 **필수** 가 표시됩니다. 이러한 각 엔터티에 대해 다음을 수행합니다.
   1. **필수** 를 선택합니다. **엔티티 편집** 패널이 표시됩니다.
   1. **기본 키** 를 선택합니다. 기본 키는 엔터티에 고유한 특성입니다. 특성이 유효한 기본 키가 되려면 중복 값, 누락 된 값 또는 null 값을 포함하지 않아야 합니다. 문자열, 정수 및 GUID 데이터 유형 특성은 기본 키로 지원됩니다.
   1. 선택적으로 파티션 패턴을 변경합니다.
   1. **닫기** 를 선택하여 패널을 저장하고 닫습니다.

1. **저장** 을 선택합니다. **데이터 원본** 페이지가 열리고 **새로 고침 중** 상태의 새 데이터 원본이 표시됩니다.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

데이터를 로드하는 데 시간이 걸릴 수 있습니다. 새로 고침이 완료되면, 수집된 데이터를 [**엔터티**](entities.md) 페이지에서 검토할 수 있습니다.

## <a name="edit-an-azure-data-lake-storage-data-source"></a>Azure Data Lake Storage 데이터 원본 편집

*다음을 사용하여 스토리지 계정에 연결* 옵션을 업데이트할 수 있습니다. 자세한 내용은 [Azure 서비스 주체를 사용하여 Azure Data Lake Storage Gen2 계정에 Customer Insights 연결](connect-service-principal.md)을 참조하세요. 저장소 계정과 다른 컨테이너에 연결하거나 계정 이름을 변경하려면 [새로운 데이터 원본 연결을 만듭니다](#connect-to-azure-data-lake-storage).

1. **데이터** > **데이터 원본** 으로 이동.

1. 업데이트하려는 데이터 원본 옆에 있는 **편집** 을 선택합니다.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Azure Data Lake 데이터 원본을 편집하는 대화 상자입니다.":::

1. 다음 정보를 변경합니다.

   - **설명**
   - **다음을 사용하여 스토리지 연결** 및 연결 정보입니다. 연결을 업데이트할 때 **컨테이너** 정보를 변경할 수 없습니다.
      > [!NOTE]
      > 스토리지 계정 또는 컨테이너에 다음 역할 중 하나를 할당해야 합니다.
        > - 스토리지 Blob 데이터 Reader
        > - 스토리지 Blob 데이터 담당자
        > - Storage Blob 데이터 Contributor

   - Azure Private Link를 통해 스토리지 계정에서 데이터를 수집하려는 경우 **프라이빗 링크를 사용하도록 설정** 합니다. 자세한 내용은 [프라이빗 링크](security-overview.md#set-up-an-azure-private-link)를 참조하세요.

1. **다음** 을 선택합니다.
1. 다음 중 하나를 변경합니다.
   - 컨테이너와 다른 엔터티 집합이 있는 다른 model.json 또는 manifest.json 파일로 이동합니다.
   - 수집할 엔터티를 추가하려면 **새 엔터티** 를 선택합니다.
   - 종속성이 없는 경우 이미 선택한 엔터티를 제거하려면 엔터티를 선택하고 **삭제** 를 선택합니다.
      > [!IMPORTANT]
      > 기존 model.json 또는 manifest.json 파일과 엔티티 집합에 대한 종속성이 있는 경우 오류 메시지가 표시되고 다른 model.json 또는 manifest.json 파일을 선택할 수 없습니다. model.json 또는 manifest.json 파일을 변경하기 전에 이러한 종속성을 제거하거나 종속성 제거를 방지하기 위해 사용할 model.json 또는 manifest.json 파일로 새 데이터 원본를 만드십시오.
   - 데이터 파일 위치 또는 기본 키를 변경하려면 **편집** 을 선택합니다.
   - 증분 수집 데이터를 변경하려면 [Azure Data Lake 데이터 원본에 대한 증분 새로 고침 구성](incremental-refresh-data-sources.md)을 참조하세요.
   - .json 파일의 엔터티 이름과 일치하도록 엔터티 이름만 변경하세요.

     > [!NOTE]
     > 수집 후에는 항상 Customer Insights의 엔터티 이름을 model.json 또는 manifest.json 파일의 엔터티 이름과 동일하게 유지하세요. Customer Insights는 시스템을 새로 고칠 때마다 model.json 또는 manifest.json을 사용하여 모든 엔터티 이름의 유효성을 검사합니다. Customer Insights 내부 또는 외부에서 엔터티 이름이 변경되면 Customer Insights에서 .json 파일의 새 엔터티 이름을 찾을 수 없기 때문에 오류가 발생합니다. 수집된 엔터티 이름이 실수로 변경된 경우 .json 파일의 이름과 일치하도록 Customer Insights의 엔터티 이름을 수정하세요.

1. **특성** 을 선택하여 특성을 추가 또는 변경하거나 데이터 프로파일링을 활성화합니다. 그런 다음 **완료** 를 선택합니다.

1. **저장** 을 클릭하여 변경 사항을 적용하고 **데이터 원본** 페이지로 돌아갑니다.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
