---
title: 고객 프로필 검색 및 필터링
description: 통합 고객 프로필에 대한 정보를 신속하게 찾고 지정된 속성을 필터링합니다.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: e53d87c4f633cba09fecbc1c219f0ac2ec6bb5598a7902cbcf7398d26d6d7c6b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7029407"
---
# <a name="customer-profiles-search--filter-index"></a>고객 프로필: 색인 검색 및 필터링

고객 데이터를 통합한 결과는 전체 고객 기반에 대한 통일된 보기를 제공하는 고객 프로필 엔터티입니다. [특정 고객 또는 고객 그룹에 대한 정보를 빠르게 찾을 수 있도록](customer-profiles.md) **고객** 페이지에서 **검색** 및 **필터** 기능을 구성할 수 있습니다. 관리자가 **검색 및 필터 색인** 페이지에서 특성을 편집하여 사용자가 검색 및 필터링할 수 있는 특성을 편집하는 방법을 계속 읽으십시오.

> [!div class="mx-imgBorder"]
> ![검색 필터.](media/search-filter.png "검색 필터")

## <a name="add-fields-and-specify-attributes"></a>필드 추가 및 특성 지정

검색 가능한 특성을 관리자로 처음 정의하는 경우 먼저 색인화된 필드를 정의해야 합니다. **고객** 페이지에서 사용자가 고객을 검색하고 필터링할 수 있는 모든 특성을 선택하는 것이 좋습니다. 데이터 통합 프로세스 중에 작성한 고객 프로필 엔터티에 존재하는 특성만 지정할 수 있습니다.

1. **고객** 페이지를 열고 **검색 및 필터 색인** 을 선택합니다.

2. 색인화된 필드를 지정하려면 **+ 추가** 를 선택합니다.

3. 색인 필드로 추가할 목록에서 특성을 선택합니다. **추가** 를 선택하면 언제든지 더 많은 특성을 추가할 수 있습니다. 또한 **제거** 기호를 선택하여 선택한 특성을 제거할 수 있습니다.

## <a name="explore-the-indexed-customer-fields-table"></a>색인화된 고객 필드 테이블 탐색

다음 정보가 표에 나와 있습니다.

- **이름**: 고객 프로필 엔터티에 나타나는 특성 이름을 나타냅니다.
- **데이터 형식**: 데이터 형식이 문자열, 숫자 또는 날짜인지를 지정합니다.
- **검색에 포함**: **검색** 을 사용하여 **고객** 페이지에서 이 특성을 고객 검색에 사용할 수 있는지 여부를 지정합니다.
- **필터 추가**: **고객** 페이지에서 이 특성을 필터링에 사용하는 방법을 정의하기 위한 컨트롤입니다.

## <a name="editing-filtering-options-for-a-given-attribute"></a>주어진 특성에 대한 필터링 옵션 편집

**고객** 페이지의 **필터** 메뉴에는 다양한 수의 특성 수준이 포함될 수 있습니다(예: 고객별로 필터링하기 위한 다른 연령 그룹).

1. **검색 및 필터 색인** 페이지에서 주어진 특성에 대해 **필터 추가** 를 선택합니다. 결과 수와 결과 순서를 정의할 수 있습니다. 특성의 데이터 형식에 따라 다음 창 중 하나가 나타납니다.

- 문자열 유형 특성: **문자열 필터 옵션** 창 및 구성할 주문 정책에 원하는 결과 수를 지정합니다.

- 숫자 유형 특성: **숫자 필터 옵션** 창 및 구성할 주문 정책에 포함되는 간격을 지정합니다.

- 날짜 유형 특성: **날짜 필터 옵션** 창 및 구성할 주문 정책에 포함되는 간격을 지정합니다.

2. **저장** 을 선택하여 변경 내용을 적용합니다.

3. 설정을 적용할 준비가 되면 **실행** 을 선택합니다.

## <a name="next-steps"></a>다음 단계

[통합 프로필 페이지](customer-profiles.md)를 검토하여 프로필을 검색하거나 인덱싱된 필드를 사용하여 모든 통합 프로필의 하위 집합을 확인하십시오.


[!INCLUDE[footer-include](../includes/footer-banner.md)]