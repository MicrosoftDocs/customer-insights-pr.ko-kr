---
title: Common Data Service 관리 레이크의 엔터티에 연결
description: Common Data Service 관리 데이터 레이크에서 데이터 가져오기
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: b1cfab40c1edb32f4a7f359e1195cfb1e879a0d5
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596967"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Common Data Service 관리형 데이터 레이크의 데이터에 연결

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

이 문서는 기존 Dynamics 365 고객이 Common Data Service 관리 레이크의 분석 엔터티에 빠르게 연결할 수 있는 방법에 대한 정보를 제공합니다. Common Data Service 조직의 관리자만 관리 레이크 엔터티 목록을 볼 수 있습니다.

## <a name="important-considerations"></a>중요 사항

Azure Data Lake Storage와 같은 온라인 서비스에 저장된 데이터는 Dynamics 365 Customer Insights에서 데이터가 처리 또는 저장된 위치와 다른 곳에 저장될 수 있습니다.온라인 서비스에서 데이터를 가져오거나 이에 연결하면 해당 데이터가 Dynamics 365 Customer Insights에 전송되거나 저장될 수 있음에 동의하는 것입니다. [Microsoft 보안 센터에서 자세히 알아보십시오.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Common Data Service 관리 레이크에 연결

1. 대상 그룹 인사이트에서 **데이터** > **데이터 원본** 으로 이동합니다.

2. **데이터 원본 추가** 를 선택합니다.

3. **Common Data Service에 연결** 을 선택하고 **다음** 을 선택합니다.

4. 데이터 원본의 **이름** 을 입력하고 **다음** 을 선택합니다. 이름 지침: 
   - 문자로 시작합니다.
   - 문자와 숫자만 사용하십시오. 특수 문자와 공백은 사용할 수 없습니다.
   - 3~64자 사이에서 사용하십시오.

5. Common Data Service 조직의 **서버 주소** 를 제공하고 **로그인** 을 선택합니다.

   > [!div class="mx-imgBorder"]
   > ![Common Data Service 서버 주소를 입력할 대화 상자](media/enter-CDS-org-details.png)

6. 사용 가능한 목록에서 수집할 엔터티를 선택합니다.    

   > [!NOTE]
   > 일부 엔터티가 이미 선택된 경우 다른 Dynamics 365 응용 프로그램(예: Dynamics 365 Sales Insights 또는 Customer Service Insights)에서 사용할 수 있습니다. 선택 사항은 변경할 수 없습니다. 이러한 엔티티는 데이터 원본이 생성되어야 사용할 수 있습니다.

   > [!div class="mx-imgBorder"]
   > ![Common Data Service 조직의 엔터티 목록을 표시하는 대화 상자](media/select-analytical-entities.png)

7. 선택한 내용을 저장하여 선택한 엔터티를 Common Data Service 관리형 레이크와 동기화합니다. 새로 추가된 연결은 **데이터 원본** 페이지에서 찾을 수 있습니다. 새로 고치기 위해 대기하고 모든 엔터티가 동기화 될 때까지 엔터티 수를 0으로 표시합니다.

환경의 데이터 원본 하나만 동일한 Common Data Service 관리 레이크를 동시에 사용할 수 있습니다.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Common Data Service 관리 레이크 데이터 원본 편집

데이터 원본을 생성한 후에만 엔터티 선택을 편집할 수 있습니다. 예를 들어, 만약 추가 엔티티가 Common Data Service에 추가 되었고 당신 또한 그 것들을 가져오고 싶습니다.    
다른 Common Data Service에 연결하려면 [새 데이터 원본을 만듭니다](#connect-to-a-common-data-service-managed-lake).

1. 대상 그룹 인사이트에서 **데이터** > **데이터 원본** 으로 이동합니다.

2. 업데이트하려는 데이터 원본 옆에 있는 줄임표를 선택하십시오.

3. 목록에서 **편집** 옵션을 선택합니다.

4. 사용 가능한 엔터티 목록에서 추가 엔터티를 선택하고 **저장** 을 선택합니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]