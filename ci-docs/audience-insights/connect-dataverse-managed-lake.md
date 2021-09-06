---
title: Microsoft Dataverse에서 테이블에 연결
description: Microsoft Dataverse 관리 데이터 레이크에서 데이터 가져오기
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: ffeccffd0e353cb5490b537552d585c184ad672f9c806e673bd04743214ad068
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033088"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Microsoft Dataverse 관리형 데이터 레이크의 데이터에 연결

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

이 문서에서는 Dataverse 사용자가 Dataverse 관리형 레이크에서 분석 엔터티에 빠르게 연결할 수 있는 방법에 대한 정보를 제공합니다. Dataverse 조직의 관리자만 관리 레이크 엔터티 목록을 볼 수 있습니다.

## <a name="important-considerations"></a>중요 사항

Azure Data Lake Storage와 같은 온라인 서비스에 저장된 데이터는 Dynamics 365 Customer Insights에서 데이터가 처리 또는 저장된 위치와 다른 곳에 저장될 수 있습니다.온라인 서비스에서 데이터를 가져오거나 이에 연결하면 해당 데이터가 Dynamics 365 Customer Insights에 전송되거나 저장될 수 있음에 동의하는 것입니다. [Microsoft 보안 센터에서 자세히 알아보십시오.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-dataverse-managed-lake"></a>Dataverse 관리 레이크에 연결

1. 대상 그룹 인사이트에서 **데이터** > **데이터 원본** 으로 이동합니다.

2. **데이터 원본 추가** 를 선택합니다.

3. **Microsoft Dataverse 관리 레이크에 연결** 을 선택하고 **다음** 을 선택합니다.

4. 데이터 원본의 **이름** 을 입력하고 **다음** 을 선택합니다. 이름 지침: 
   - 문자로 시작합니다.
   - 문자와 숫자만 사용하십시오. 특수 문자와 공백은 사용할 수 없습니다.
   - 3~64자 사이에서 사용하십시오.

5. Dataverse 조직의 **서버 주소** 를 제공하고 **로그인** 을 선택합니다.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="사용자가 Dataverse 환경 URL을 입력할 수 있는 데이터 수집 단계의 화면.":::

6. 사용 가능한 목록에서 대상 그룹 통찰력에 대한 엔터티로 수집하려는 테이블을 선택합니다.    

   > [!NOTE]
   > 일부 테이블이 이미 선택된 경우 다른 Dynamics 365 응용 프로그램(예: Dynamics 365 Sales Insights 또는 Customer Service Insights)에서 사용할 수 있습니다. 선택 사항은 변경할 수 없습니다. 이 테이블은 데이터 원본이 생성되면 엔터티로 사용할 수 있습니다.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dataverse 환경의 엔터티 목록을 보여주는 대화 상자.":::

7. Dataverse에서 선택한 테이블의 동기화를 시작하려면 선택 항목을 저장하십시오. 새로 추가된 연결은 **데이터 원본** 페이지에서 찾을 수 있습니다. 새로 고침을 위해 대기하고 선택한 모든 테이블이 동기화될 때까지 엔터티 수를 0으로 표시합니다.

환경의 데이터 원본 하나만 동일한 Dataverse 관리 레이크를 동시에 사용할 수 있습니다.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Dataverse 관리 레이크 데이터 원본 편집

데이터 원본을 생성한 후에만 엔터티 선택을 편집할 수 있습니다. 예를 들어, 만약 추가 엔티티가 Dataverse에 추가 되었고 당신 또한 그 것들을 가져오고 싶습니다.    
다른 Dataverse 데이터 레이크에 연결하려면, [새로운 데이터 원본 생성](#connect-to-a-dataverse-managed-lake)을 수행합니다.

1. 대상 그룹 인사이트에서 **데이터** > **데이터 원본** 으로 이동합니다.

2. 업데이트하려는 데이터 원본 옆에 있는 줄임표를 선택하십시오.

3. 목록에서 **편집** 옵션을 선택합니다.

4. 사용 가능한 엔터티 목록에서 추가 엔터티를 선택하고 **저장** 을 선택합니다.

[!INCLUDE[footer-include](../includes/footer-banner.md)]