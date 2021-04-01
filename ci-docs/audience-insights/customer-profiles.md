---
title: 고객 프로필 보기
description: 통합된 고객 데이터를 조합하여 볼 수 있습니다.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: d6a9e7872a488b6d68afce35b547f93cc4a7c652
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596875"
---
# <a name="customer-profiles"></a>고객 프로필

**고객** 페이지에는 [모든 데이터 원본](data-sources.md)에서 수집된 프로필 데이터를 기반으로 고객의 결합된 보기를 보여줍니다. [통합된 고객 엔터티를 만든](data-unification.md) 후 고객 프로필을 사용할 수 있습니다. 데이터 통합 프로세스를 완료하여 고객에 대한 풍부한 보기를 확보해야 합니다. 또한 이 페이지에서 고객을 검색할 수도 있습니다.

고객은 개인 또는 조직(미리 보기)일 수 있습니다. 각 고객 또는 조직 프로필은 타일로 표시됩니다. 타일을 선택하여 특정 고객 또는 조직에 대한 추가 정보를 확인합니다. 추가 레코드를 보려면 페이지 하단의 페이지 매기기 컨트롤을 사용합니다.

> [!div class="mx-imgBorder"] 
> ![B2C 고객 프로필](media/profiles-customers.png "B2C 고객 프로필")

조직(미리 보기)
> [!div class="mx-imgBorder"] 
> ![B2B 고객 프로필](media/profile-customers-b2b.png "B2B 고객 프로필")

> [!NOTE]
> 탐색에서 **고객** 을 선택할 때 타일이 표시되지 않으면 관리자는 **검색 및 필터 색인** 에서 [검색 가능한 속성을 하나 이상 정의](search-filter-index.md)해야 합니다.

## <a name="search-for-customers"></a>고객 검색

검색 상자에 이름이나 다른 특성을 입력하여 고객을 검색합니다. 검색은 데이터 통합 프로세스 중에 만든 고객 프로필 엔터티 내에서만 작동합니다.

관리자는 **검색 및 필터 색인** 페이지를 사용하여 검색 가능한 특성을 구성할 수 있습니다. 자세한 내용은 [검색 및 필터 색인 관리](search-filter-index.md)를 참조하십시오.

## <a name="filter-customers"></a>고객 필터링

고객 프로필 엔터티 필드별로 고객을 필터링할 수 있습니다. 검색과 마찬가지로 관리자는 먼저 **검색 및 필터 색인** 페이지를 사용하여 필드를 필터링 가능한 필드로 정의해야 합니다.

1. **고객** 페이지에서 **필터** 를 선택합니다.

2. 고객을 필터링할 특성 옆에 있는 확인란을 선택합니다.

   > [!div class="mx-imgBorder"] 
   > ![고객 프로필](media/profiles-customers3.png "고객 프로필")

3. **고객** 페이지에서 **필터 지우기** 를 선택하여 필터를 제거합니다.

##  <a name="customer-details-page"></a>고객 정보 페이지

고객 타일 중 하나를 선택하여 **고객 정보 페이지** 를 엽니다. 이 보기에는 선택된 고객의 통합된 정보가 포함됩니다.

고객 정보에는 다음이 포함됩니다.

-   **고객 프로필 타일**: 이 타일에는 통합된 고객 프로필 엔터티의 다양한 값이 표시됩니다. 이러한 세부 정보에는 이메일 주소, 이름, 도시 등이 포함될 수 있습니다. 

-   **잠재적 관심사, 잠재적 브랜드:** 자사 보강을 구성했는지 표시합니다. 이 고객과 유사한 프로필을 가진 고객이 가질 수 있는 브랜드에 대한 잠재적인 관심사 및 친밀도를 나타냅니다. 자세한 내용은 [브랜드 및 관심 선호도로 고객 프로필 강화](enrichment-microsoft-graph.md)를 참조하세요.

-   **측정값:** 특정 유형의 측정값(고객 특성 측정값)을 하나 이상 구성했는지 표시합니다. 여기에는 개별 고객 수준에서 고객에 대한 계산된 KPI가 포함됩니다. 자세한 내용은 [측정값 정의 및 관리](measures.md)를 참조하세요.

-   **활동 시간 표시줄:** 활동을 구성했는지 표시합니다. 시간 표시줄 보기에는 가장 최근 활동부터 시작하여 이 고객의 시간순으로 정렬된 활동이 포함됩니다. 자세한 내용은 [고객 활동](activities.md)을 참조하세요.

**고객으로 돌아가기** 를 선택하여 고객 검색 페이지로 돌아갑니다.

## <a name="next-steps"></a>다음 단계

[더 많은 데이터 원본 추가](data-sources.md) 또는 [고객 분류 작성](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]