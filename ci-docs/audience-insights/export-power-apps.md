---
title: Power Apps 커넥터
description: Power Apps 및 Power Automate와 연결합니다.
ms.date: 01/19/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a8bbb9a09218d54228589d43c21c8894680b56e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268924"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps 커넥터(미리 보기)

통합된 고객 프로필을 Power Apps를 사용하여 개인화된 앱으로 가져오기.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Power Apps 및 Dynamics 365 Customer Insights 연결

Customer Insights는 [Power Apps에서 사용 가능한 많은 데이터 소스](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources) 중 하나입니다.

[앱에 데이터 연결을 추가](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection)하는 방법을 알아보려면 Power Apps 설명서를 참조하십시오. 또한 [Power Apps가 위임을 사용하여 캔버스 앱에서 대규모 데이터 집합을 처리하는 방법](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview)을 검토하는 것이 좋습니다.

## <a name="available-entities"></a>사용 가능한 엔터티

Customer Insights를 데이터 연결로 추가한 후 Power Apps에서 다음 엔터티를 선택할 수 있습니다.

- 고객: [통합 고객 프로필](customer-profiles.md)의 데이터를 사용합니다.
- UnifiedActivity: 앱에 [활동 타임라인](activities.md)을 표시합니다.

## <a name="limitations"></a>제한 사항

### <a name="retrievable-entities"></a>검색 가능한 엔터티

Power Apps 커넥터에서 **고객**, **통합 활동**, **세그먼트** 엔터티만 검색할 수 있습니다. 다른 엔터티는 기본 커넥터가 Power Automate 내의 트리거를 통해 지원하기 때문에 표시됩니다.  

### <a name="delegation"></a>위임

고객 엔터티 및 통합 활동 엔터티에 대한 위임 작업. 

- **고객** 엔터티에 대한 위임: 이 엔터티에 대한 위임을 사용하려면 필드가 [검색 및 필터 색인](search-filter-index.md)에 인덱싱되어야 합니다.  

- **통합 활동** 위임:이 엔티티에 대한 위임은 **ActivityId** 와 **고객 ID** 필드에서만 작동합니다.  

- 위임에 대한 자세한 내용은 [Power Apps 위임 가능한 기능 및 작업](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps)을 참조하세요. 

## <a name="example-gallery-control"></a>갤러리 컨트롤 예

예를 들어, 고객 프로필을 [갤러리 컨트롤](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery)에 추가합니다.

1. 빌드 중인 앱에 **갤러리** 컨트롤을 추가합니다.

> [!div class="mx-imgBorder"]
> ![갤러리 요소 추가](media/connector-powerapps9.png "갤러리 요소 추가")

1. **고객** 을 항목의 데이터 원본을 선택합니다.

    > [!div class="mx-imgBorder"]
    > ![데이터 원본 선택](media/choose-datasource-powerapps.png "데이터 원본 선택")

1. 오른쪽의 데이터 패널을 변경하여 갤러리에 표시할 고객 엔터티 필드를 선택할 수 있습니다.

1. 갤러리에서 선택한 고객의 필드를 표시하려면 레이블: **{Name_of_the_gallery}.Selected.{property_name}** 의 텍스트 속성을 입력합니다.

    예: Gallery1.Selected.address1_city

1. 고객의 통합 타임라인을 표시하려면 갤러리 요소를 추가하고 항목 속성: **Filter('UnifiedActivity', CustomerId = {Customer_Id})** 을 추가합니다.

    예: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]