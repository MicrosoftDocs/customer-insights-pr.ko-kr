---
title: 엔터티 및 데이터 집합
description: 엔터티 페이지에서 데이터를 봅니다.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: 1e1abdf49a3c1fe6f9fdd2cf5353a7723454f47b
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355306"
---
# <a name="entities-in-audience-insights"></a>대상 그룹 인사이트의 엔터티

[데이터 원본을 구성](data-sources.md)한 후 **엔터티** 로 이동하여 수집된 데이터의 품질을 평가합니다. 엔터티는 데이터 집합으로 간주합니다. Dynamics 365 Customer Insights의 다양한 기능은 이러한 엔터티를 중심으로 구축됩니다. 이를 면밀히 검토하면 해당 기능의 출력을 검증하는 데 도움이 됩니다.

**엔터티** 페이지에는 엔터티가 나열되어 있고 다음 열을 포함합니다.

- **이름**: 데이터 엔터티의 이름입니다. 엔터티 이름 옆에 경고 기호가 표시되면 해당 엔터티의 데이터가 성공적으로 로드되지 않았음을 의미합니다.
- **원본**: 엔터티를 수집한 데이터 원본의 유형
- **업데이트됨**: 엔터티가 마지막으로 업데이트된 시간
- **상태**: 엔터티의 마지막 업데이트에 대한 세부 정보

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>특정 엔터티의 데이터 탐색

1. 대상 그룹 인사이트에서 **데이터** > **엔터티** 로 이동합니다.
1. **엔터티** 페이지에서 엔터티를 선택하여 세부 정보 페이지를 엽니다.  
1. 해당 엔터티에 포함된 다른 필드와 레코드를 탐색합니다.

- **특성** 탭은 기본적으로 선택되며 필드 이름, 데이터 유형 및 유형과 같은 선택한 엔터티에 대한 세부 사항을 검토하는 테이블을 표시합니다. **유형** 열에는 Common Data Model 관련 유형이 표시되며 시스템에 의해 자동 식별되거나 사용자에 의해 [수동으로 매핑](map-entities.md)됩니다. 이러한 유형은 특성의 데이터 유형과 다를 수 있는 시맨틱 유형입니다. 예를 들어 아래의 *이메일* 필드에는 *텍스트* 데이터 유형이 있지만 (의미론적) Common Data Model 유형은 *이메일* 또는 *이메일 주소* 일 수 있습니다.

> [!div class="mx-imgBorder"]
> ![필드 테이블.](media/data-manager-entities-fields.PNG "필드 테이블")

> [!NOTE]
> 이 페이지에는 엔터티 데이터의 샘플만 표시됩니다. 전체 데이터 집합을 보려면 **데이터 원본** 페이지에서 엔터티를 선택하고 **편집** 을 선택한 다음 [데이터 원본](data-sources.md)에 설명된 대로 Power Query 편집기를 사용하여 이 엔터티의 데이터를 봅니다.

엔터티에서 수집된 데이터에 대해 자세히 알아보려면 **요약** 열은 데이터에 적용할 수 있는 null, 누락된 값, 고유 값, 개수 및 분포와 같은 데이터의 중요한 특성을 제공합니다. 데이터 요약을 보려면 차트 아이콘을 선택합니다.

> [!div class="mx-imgBorder"]
> ![요약 기호.](media/data-manager-entities-summary.png "데이터 요약 테이블")

- **데이터** 탭에는 엔터티의 개별 레코드에 대한 세부 정보가 나열된 테이블이 표시됩니다. 나열된 세부 정보는 엔터티의 데이터 유형에 따라 다릅니다.

> [!div class="mx-imgBorder"]
> ![엔터티를 선택합니다.](media/data-manager-entities-data.png "엔터티 선택")

- **보고서** 탭(일부 엔터티에 사용 가능)을 사용하면 보고서를 생성하여 데이터를 시각화할 수 있으며 다음 열이 포함됩니다.

  - **보고서 이름**: 보고서의 이름입니다.
  - **만든 사람**: 엔터티를 만든 사람의 이름
  - **생성 일시**: 엔터티 생성 날짜 및 시간
  - **수정한 사람**: 엔터티를 수정한 사람의 이름
  - **수정 일시**: 엔터티 수정 날짜 및 시간 

## <a name="entity-specific-information"></a>엔터티별 정보

다음 섹션에서는 일부 시스템 생성 엔터티에 대한 정보를 제공합니다.

### <a name="corrupted-data-sources"></a>손상된 데이터 원본

수집된 데이터 원본의 필드에 손상된 데이터가 포함될 수 있습니다. 손상된 필드가 있는 레코드는 시스템 생성 엔터티에 노출됩니다. 손상된 레코드에 대해 알면 소스 시스템에서 검토하고 업데이트할 데이터를 식별하는 데 도움이 됩니다. 다음 번에 데이터 원본을 새로 고친 후 수정된 레코드는 Customer Insights에 수집되고 다운스트림 프로세스로 전달됩니다. 

예를 들어, '생일' 열에는 '날짜'로 설정된 데이터 유형이 있습니다. 고객 레코드에 생일이 '01/01/19777'로 입력되어 있습니다. 시스템은 이 레코드를 손상된 것으로 표시합니다. 이제 누군가가 소스 시스템의 생일을 '1977'로 변경할 수 있습니다. 데이터 원본의 자동 새로 고침 후 필드는 이제 유효한 형식을 가지며 레코드는 손상된 엔터티에서 제거됩니다. 

**데이터** > **엔터티** 로 이동하여 **시스템** 섹션에서 손상된 엔터티를 찾습니다. 손상된 엔터티의 명명 스키마: 'DataSourceName_EntityName_corrupt'. 손상된 엔터티를 선택하여 모든 손상된 필드와 개별 레코드 수준에서 이유를 식별합니다.
> [!div class="mx-imgBorder"]
> ![손상된 이유.](media/corruption-reason.png "손상된 이유")

Customer Insights는 여전히 손상된 레코드를 처리합니다. 그러나 통합 데이터로 작업할 때 문제가 발생할 수 있습니다.

수집된 데이터에 대해 다음 검사를 실행하여 손상된 레코드를 노출합니다. 

- 필드 값이 해당 열의 데이터 유형과 일치하지 않습니다.
- 필드에 열이 예상 스키마와 일치하지 않게 하는 문자가 포함되어 있습니다. 예: 잘못된 형식의 따옴표, 이스케이프 처리되지 않은 따옴표 또는 복귀 개행 문자.
- datetime/date/datetimeoffset 열이 있으면 표준 ISO 형식을 따르지 않는 경우 해당 형식을 모델에 지정해야 합니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
