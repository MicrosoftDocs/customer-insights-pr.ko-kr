---
title: 고객 프로필용 검색 및 필터 색인 관리
description: 통합 고객 프로필에 대한 정보를 신속하게 찾고 지정된 속성을 필터링합니다.
ms.date: 07/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: dfbfcbff3ffb3e4483252377e591229631d38556
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2022
ms.locfileid: "9187917"
---
# <a name="manage-the-search--filter-index-for-customer-profiles"></a>고객 프로필용 검색 및 필터 색인 관리

고객 데이터를 통합한 결과는 전체 고객 기반에 대한 통일된 보기를 제공하는 *고객* 엔터티입니다. 사용자가 빠르게 [특정 고객 또는 고객 그룹에 대한 정보를 찾을 수 있도록](customer-profiles.md) 관리자는 **고객** 페이지에서 **검색** 및 **필터** 기능을 구성할 수 있습니다.

   :::image type="content" source="media/search-filter.png" alt-text="검색 필터":::

## <a name="define-searchable-attributes-and-indexed-fields"></a>검색 가능한 특성 및 색인된 필드 정의

검색 가능한 특성을 관리자로 처음 정의하는 경우 먼저 색인된 필드를 정의합니다. **고객** 페이지에서 사용자가 고객을 검색하고 필터링할 수 있는 모든 특성을 선택하는 것이 좋습니다. 데이터 통합 프로세스 중에 작성된 *고객* 엔터티에 존재하는 특성만 지정할 수 있습니다.

1. **고객** 페이지로 이동하여 **검색 및 필터 색인** 을 선택합니다.

1. **+ 추가** 를 선택합니다.

1. 색인된 필드로 추가할 목록에서 특성을 선택하고 **적용** 을 클릭합니다.

1. 더 많은 특성을 추가하려면 **추가** 를 선택합니다. 선택된 특성을 제거하려면 특성을 선택하고 **삭제** 를 선택합니다.

   :::image type="content" source="media/search-filter-index.png" alt-text="검색 및 필터 색인 페이지.":::

1. 검색 및 필터 설정을 적용할 준비가 되면 **실행** 을 선택합니다. 변경 사항이 처리된 후 [고객 페이지의 고객 카드](customer-profiles.md)에서 내용을 확인할 수 있습니다.

## <a name="define-filtering-options-for-a-given-attribute"></a>주어진 특성에 대한 필터링 옵션 정의

**고객** 페이지에서 고객을 필터링하는 데 사용되는 필드를 설정합니다.

1. **고객** 페이지로 이동하여 **검색 및 필터 색인** 을 선택합니다.

1. 특성을 선택하고 **필터를 추가** 합니다. 구성될 결과 개수와 결과 순서를 정의합니다. 특성의 데이터 형식에 따라 다음 창 중 하나가 나타납니다.

   - 문자열 유형 특성: **문자열 필터** 창 및 구성할 주문 정책에 원하는 결과 개수를 지정합니다.

   - 숫자 유형 특성: **숫자 필터** 창 및 구성할 주문 정책에 포함되는 간격을 지정합니다.

   - 날짜 유형 특성: **날짜 필터** 창 및 구성할 주문 정책에 포함되는 간격을 지정합니다.

1. **확인** 을 선택합니다. 필터링 기준을 적용할 모든 속성에서 이 과정을 반복합니다.

1. 검색 및 필터 설정을 적용할 준비가 되면 **실행** 을 선택합니다. 변경 사항이 처리된 후 [고객 페이지의 고객 카드](customer-profiles.md)에서 내용을 확인할 수 있습니다.

## <a name="view-indexed-customer-fields"></a>색인된 고객 필드 보기

**검색 및 필터 색인** 페이지에는 다음 정보가 표시됩니다.

- **이름**: *고객* 엔터티에 나타나는 특성 이름을 나타냅니다.
- **데이터 형식**: 데이터 형식이 문자열, 숫자 또는 날짜인지를 지정합니다.
- **검색에 포함**: **검색** 을 사용하여 **고객** 페이지에서 이 특성을 고객 검색에 사용할 수 있는지 여부를 지정합니다.
- **필터 추가**: **고객** 페이지에서 이 특성을 필터링에 사용하는 방법을 정의하기 위한 컨트롤입니다.

## <a name="next-steps"></a>다음 단계

[통합 프로필 페이지](customer-profiles.md)를 검토하여 프로필을 검색하거나 인덱싱된 필드를 사용하여 모든 통합 프로필의 하위 집합을 확인하십시오.

[!INCLUDE [footer-include](includes/footer-banner.md)]
