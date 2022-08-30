---
title: 데이터 통합을 위한 소스 필드 선택
description: 통합 프로세스의 첫 번째 단계는 엔터티, 속성, 기본 키 및 시맨틱 유형을 선택하여 데이터를 통합 고객 프로필에 매핑하는 것입니다.
recommendations: false
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: bc120aa7a3713e1184ff278edf0942925faafa12
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304573"
---
# <a name="select-source-fields-for-data-unification"></a>데이터 통합을 위한 소스 필드 선택

통합의 첫 번째 단계는 통합하려는 데이터 세트 내의 엔터티와 필드를 선택하는 것입니다. 이름, 주소, 전화번호 및 이메일과 같은 고객 관련 세부 정보가 포함된 엔터티를 선택합니다. 하나 이상의 엔터티를 선택할 수 있습니다.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="select-entities-and-fields"></a>엔터티 및 필드 선택

1. **데이터** > **통합** 으로 이동합니다.

   개별 고객(B-to-C)의 경우 **통합** 랜딩 페이지가 표시되며 첫 번째 단계인 **원본 필드** 에서 **시작** 이 표시됩니다.

   :::image type="content" source="media/m3_unify_land.png" alt-text="개별 고객을 위한 첫 실행 경험을 위한 통합 랜딩 페이지 스크린샷.":::

   비즈니스 거래처(B-to-B)의 경우 **통합** 랜딩 페이지에 **거래처 통합** 이 표시되며 첫 번째 단계인 **원본 필드** 에서 **시작** 이 표시됩니다. **연락처 통합(프리뷰)** 단계는 선택 사항이며 거래처 통합이 완료될 때까지 보류 중입니다.

   :::image type="content" source="media/b2b_unify_land.png" alt-text="비즈니스 거래처의 첫 실행 경험을 위한 통합 랜딩 페이지 스크린샷.":::

1. **시작** 을 선택합니다.

1. **소스 필드** 페이지에서 **엔터티 및 필드 선택** 을 선택합니다. **엔터티 및 필드 선택** 창이 표시됩니다.

1. 엔터티를 하나 이상 선택하세요.

1. 선택한 각 엔터티에 대해 고객 레코드를 일치시키는 데 사용할 필드와 통합 프로필에 포함할 필드를 식별합니다. 이러한 필드를 *특성* 이라고 합니다. 엔터티에서 필요한 특성을 개별적으로 선택하거나 엔터티 수준에서 확인란을 선택하여 엔터티의 모든 특성을 포함할 수 있습니다. 매핑하려는 필수 특성을 선택하기 위해 모든 특성 및 엔터티에서 키워드를 검색 할 수 있습니다.

   :::image type="content" source="media/m3_select_entities.png" alt-text="선택한 엔터티 및 특성의 스크린샷입니다.":::

   이 예에서는 **eCommerceContacts** 와 **loyCustomer** 엔터티를 추가합니다. 이러한 엔터티를 선택하면 어떤 온라인 비즈니스 고객이 로열티 프로그램 회원인지에 대한 통찰력을 얻을 수 있습니다.

1. **적용** 을 선택하여 선택 사항을 확인합니다. 선택한 엔터티 및 특성이 표시됩니다.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>특성에 대한 기본 키 및 의미 유형 선택

   :::image type="content" source="media/m3_select_primary.png" alt-text="아직 기본 키가 선택되지 않은 선택된 엔터티의 스크린샷." lightbox="media/m3_select_primary.png":::

각 엔터티에 대해 다음 단계를 수행합니다.

1. **기본 키** 를 선택합니다. 기본 키는 엔터티에 고유한 특성입니다. 특성이 유효한 기본 키가 되려면 중복 값, 누락 된 값 또는 null 값을 포함하지 않아야 합니다. 문자열, 정수 및 GUID 데이터 유형 특성은 기본 키로 지원됩니다.

1. 시간을 절약하고 정확도를 개선하는 시맨틱의 스마트 예측을 위해 AI 모델을 사용하려면 **지능형 매핑** 이 켜져 있는지 확인하세요. 지능형 매핑은 **유형** 필드에서 AI 기반 시맨틱 권장 사항을 제공합니다.

1. 각 속성에 대해 이름, 도시 또는 이메일 주소와 같이 해당 특성을 가장 잘 설명하는 시맨틱 **유형** 을 선택합니다.

   > [!NOTE]
   > B-to-C에서, 고객 카드에 고객 이름을 채우려면 하나의 필드가 시맨틱 유형 *Person.FullName* 에 매핑되어야 합니다. B-to-B에서 거래처 이름은 *Organization.Name* 에 매핑되어야 합니다. 그렇지 않으면 고객 카드는 이름이 없는 것으로 나타납니다.

   1. 시스템에서 식별한 특성 유형을 재정의하려면 다른 옵션을 선택하십시오. 유형이 존재하지 않는 경우 특성에 대해 **유형** 필드를 선택하고 사용자 지정 시맨틱 유형 이름을 입력하여 사용자 지정 시맨틱 유형을 생성하십시오.

   1. 공개적으로 사용 가능한 프로필 이미지 또는 로고에 대한 URL이 포함된 특성을 추가하려면 URL이 포함된 엔터티 및 필드를 선택합니다. **유형** 필드에 다음을 입력합니다.
      - 사람의 경우: Person.ProfileImage
      - 조직의 경우: Organization.LogoImage

1. 시맨틱 유형이 자동으로 식별되는 특성을 검토합니다. 이러한 특성은 **매핑된 필드 검토** 아래에 나열됩니다. **고객 통합 필드** 단계에서는 동일한 유형의 특성만 결합할 수 있습니다. 시맨틱 유형은 인사이트를 자동으로 제안하는 데 사용됩니다. 선택한 유형이 선택한 모든 엔터티에서 일관된지 확인하십시오.

1. 시맨틱 유형에 자동으로 매핑되지 않는 특성의 경우 시맨틱 유형 필드를 선택하거나 사용자 지정 특성 유형 이름을 입력하거나 매핑되지 않은 상태로 둡니다. 이러한 특성은 **매핑되지 않은 필드의 데이터 정의** 아래에 나열됩니다.

1. 각 엔터티에 대한 단계를 완료한 후 **원본 필드 저장** 을 선택합니다.

1. **다음** 을 선택합니다.

> [!div class="nextstepaction"]
> [다음 단계: 중복 제거](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
