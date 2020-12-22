---
title: 엔터티 및 데이터 집합
description: 엔터티 페이지에서 데이터를 봅니다.
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e3f41c0424b2cd756d72ae6af9d5225ebba92628
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406274"
---
# <a name="entities-in-audience-insights"></a>대상 그룹 인사이트의 엔터티

[데이터 원본을 구성](data-sources.md)한 후 **엔터티** 로 이동하여 수집된 데이터의 품질을 평가합니다. 엔터티는 데이터 집합으로 간주합니다. Dynamics 365 Customer Insights의 다양한 기능은 이러한 엔터티를 중심으로 구축됩니다. 이를 면밀히 검토하면 해당 기능의 출력을 검증하는 데 도움이 됩니다.

**엔터티** 페이지는 엔터티를 나열하고 여러 열을 포함합니다.

- **이름**: 데이터 엔터티의 이름입니다. 엔터티 이름 옆에 경고 기호가 표시되면 해당 엔터티의 데이터가 성공적으로 로드되지 않았음을 의미합니다.
- **원본**: 엔터티를 수집한 데이터 소스 유형
- **만든 사람**: 엔터티를 만든 사람의 이름
- **만든 날짜**: 엔터티 작성 날짜 및 시간
- **업데이트한 사람**: 엔터티를 업데이트한 사람의 이름
- **마지막 업데이트 날짜**: 엔터티의 마지막 업데이트 날짜 및 시간
- **마지막 새로 고침**: 마지막으로 데이터를 새로 고친 날짜 및 시간

## <a name="exploring-a-specific-entitys-data"></a>특정 엔터티의 데이터 탐색

엔터티를 선택하여 해당 엔터티에 포함된 다른 필드와 레코드를 탐색합니다.

> [!div class="mx-imgBorder"]
> ![엔터티 선택](media/data-manager-entities-data.png "엔터티 선택")

- **데이터** 탭은 기본적으로 선택되며 엔터티의 개별 레코드에 대한 세부 사항을 나열하는 테이블을 표시합니다.

> [!div class="mx-imgBorder"]
> ![필드 테이블](media/data-manager-entities-fields.PNG "필드 테이블")

- **필드** 탭에는 필드 이름, 데이터 유형 및 유형과 같은 선택된 엔터티에 대한 세부 정보를 검토하는 테이블이 표시됩니다. **유형** 열에는 Common Data Model 관련 유형이 표시되며 시스템에 의해 자동 식별되거나 사용자에 의해 [수동으로 매핑](map-entities.md)됩니다. 필드와 같이 특성의 데이터 형식과 다를 수 있는 의미 유형입니다. 예를 들어 아래의 *전자 메일* 에는 *텍스트* 라는 데이터 형식이 있지만 (의미론적) Common Data Model 유형은 *전자 메일* 또는 *EmailAddress* 일 수 있습니다.

> [!NOTE]
> 두 테이블 모두 엔터티 데이터의 샘플만 표시합니다. 전체 데이터 집합을 보려면 **데이터 원본** 페이지에서 엔터티를 선택하고 **편집** 을 선택한 다음 [데이터 원본](data-sources.md)에 설명된 대로 파워 쿼리 편집기를 사용하여 이 엔터티의 데이터를 봅니다.

엔터티에서 수집된 데이터에 대해 자세히 알아보려면 **요약** 열은 데이터에 적용할 수 있는 null, 누락된 값, 고유 값, 개수 및 분포와 같은 데이터의 중요한 특성을 제공합니다.

데이터 요약을 보려면 차트 아이콘을 선택합니다.

> [!div class="mx-imgBorder"]
> ![요약 기호](media/data-manager-entities-summary.png "데이터 요약 테이블")

### <a name="next-step"></a>다음 단계

수집된 데이터를 *매핑*, *일치* 및 *병합* 하는 방법은 [통합](data-unification.md) 항목을 참조하십시오.
