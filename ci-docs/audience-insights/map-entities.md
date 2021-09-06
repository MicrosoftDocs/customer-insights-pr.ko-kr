---
title: 데이터 통합 시 엔터티 매핑
description: 데이터를 매핑하여 통합 고객 프로필을 만듭니다.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 570683876b10cb83d8af14552ca9bea9d80613575005d49a9af37cc16b8e75c9
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034414"
---
# <a name="map-entities-and-attributes"></a>엔터티 및 특성 매핑

**매핑** 은 대상 그룹 인사이트의 데이터 통합 프로세스의 첫 번째 단계입니다. 매핑은 다음 세 단계로 구성됩니다.

- *엔터티 선택*: 고객에 대한 보다 완전한 정보가 있는 데이터 집합으로 이어지는 결합 가능한 엔터티를 식별합니다.
- *특성 선택*: 각 엔터티에 대해 *일치* 및 *병합* 단계에서 결합하고 조정할 열을 식별합니다. 이러한 열은 *특성* 이라고 합니다.
- *기본 키 및 의미 유형 선택*: 각 엔티티에 대해 해당 엔티티의 기본 키로 정의 할 특성을 식별하고 각 특성에 대해 해당 속성을 가장 잘 설명하는 의미 유형을 식별합니다.

일반적인 데이터 통합 흐름에 대한 자세한 내용은 [통합](data-unification.md)을 참조하십시오.

## <a name="select-the-first-entities"></a>첫 번째 엔터티 선택

1. 대상 그룹 인사이트에서 **데이터** > **통합** > **매핑** 으로 이동합니다.

2. **엔터티 선택** 을 선택하여 매핑 단계를 시작합니다.

3. 사용할 엔티티와 특성을 선택합니다. *시합* 과 *병합* 단계. 엔터티에서 개별적으로 필요한 특성을 선택하거나 엔터티의 모든 특성을 포함 할 수 있습니다. **모든 필드 포함** 엔터티 수준의 확인란. 데이터 통합 프로세스를 활용하려면 두 개 이상의 엔터티를 선택하는 것이 좋습니다.

   > [!div class="mx-imgBorder"]
   > ![엔터티 추가 예.](media/data-manager-configure-map-add-entities-example.png "엔터티 추가 예")

   이 예에서 우리는 **전자 상거래 연락처** 와 **충성 고객** 엔터티를 추가합니다. 이러한 엔터티를 선택하면 어떤 온라인 비즈니스 고객이 로열티 프로그램 회원인지에 대한 통찰력을 얻을 수 있습니다.
   
   매핑하려는 필수 특성을 선택하기 위해 모든 특성 및 엔터티에서 키워드를 검색 할 수 있습니다.
   
     > [!div class="mx-imgBorder"]
   > ![검색 필드 예.](media/data-manager-configure-map-search-fields-example.png "검색 필드 예")

4. **적용** 을 선택하여 선택 사항을 확인합니다.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>특성에 대한 기본 키 및 의미 유형 선택

엔터티를 선택한 후 **맵** 페이지에는 리뷰를 위해 선택한 엔터티가 나열됩니다. 엔터티의 기본 키를 정의하고 엔터티의 특성에 대한 의미 유형을 식별하십시오.

- **기본 키**: 각 엔터티의 기본 키로 하나의 특성을 선택합니다. 특성이 유효한 기본 키가 되려면 중복 값, 누락 된 값 또는 null 값을 포함하지 않아야 합니다. 문자열, 정수 및 GUID 데이터 형식 특성은 기본 키로 지원되며 선택할 수 있는 필드에 표시됩니다.

- **특성 의미 유형**: 이메일 주소 또는 이름과 같은 특성 범주입니다. 스마트 예측 의미 체계에 AI 모델을 사용하고 시간을 절약하고 정확도를 높이려면 **지능형 매핑** 을 **사용 설정** 하세요. 지능형 매핑은 **유형** 필드에서 AI 기반 의미론 권장 사항을 강조합니다. **사용 중지** 로 설정하면 정기적인 매핑 권장 사항을 볼 수 있습니다. 사용 가능한 옵션 목록에서 의미 유형을 선택하고 제안 된 선택을 재정의 할 수 있습니다.

> [!div class="mx-imgBorder"]
> ![특성 유형 및 의미 예측.](media/data-manager-configure-map-add-attributes-semantic-prediction.png "특성 유형 및 의미 예측")

사용자 지정 의미 유형을 추가할 수도 있습니다. 해당 특성의 유형 필드를 선택하고 사용자 지정 의미 유형 이름을 입력합니다. 이 방법으로 시스템이 자동 식별한 특성 유형을 변경할 수도 있습니다.

의미 유형이 자동으로 식별되는 모든 특성은 **매핑된 필드 검토** 부분. 이러한 특성과 의미 유형은 데이터 통합의 통합 단계에서 엔터티를 결합하는데 사용되므로 리뷰합니다.

의미 체계 유형에 자동으로 매핑되지 않는 특성은 **매핑되지 않은 필드의 데이터 정의** 섹션. 매핑되지 않은 특성에 대한 의미 유형 필드를 선택하거나 사용자 정의 특성 유형 이름을 입력합니다.

> [!div class="mx-imgBorder"]
> ![기본 키 및 특성 유형.](media/data-manager-configure-map-add-attributes.png "기본 키 및 특성 유형")

> [!NOTE]
> 고객 카드에 고객 이름을 채우려면 하나의 필드가 Person.FullName 의미 유형에 매핑되어야 합니다. 그렇지 않으면 고객 카드는 이름이 없는 것으로 나타납니다. 

## <a name="add-and-remove-attributes-and-entities"></a>특성 및 엔터티 추가 및 제거

1. **통합** > **맵** 에서 **필드 편집** 을 선택합니다.

2. **필드 편집** 창에서 특성 및 엔터티를 추가하거나 제거합니다. 검색 또는 스크롤을 사용하여 관심있는 특성 및 엔터티를 찾아 선택하십시오. 이미 일치된 특성이나 엔터티는 제거할 수 없습니다.

   > [!div class="mx-imgBorder"]
   > ![특성 추가 또는 제거.](media/configure-data-map-edit.png "특성 추가 또는 제거")

3. **적용** 을 선택합니다.

## <a name="add-images-to-profiles"></a>프로필에 이미지 추가

엔터티에 공개적으로 사용 가능한 프로필 이미지 또는 로고에 대한 URL이 포함되어 있으면 이를 통합 고객 프로필에 추가할 수 있습니다.

엔터티를 선택하고 프로필 이미지의 URL이 포함된 필드를 찾습니다. **유형** 입력 필드에 다음 값을 수동으로 입력합니다. 
- 사람의 경우: Person.ProfileImage
- 조직의 경우: Organization.LogoImage

통합 단계를 계속하고 이미지 URL이 포함된 특성이 [통합 ](merge-entities.md)단계.

## <a name="set-attributes-for-organizations"></a>조직의 특성 설정

조직(미리 보기)의 경우 특성 유형은 "Organization.Name"에 매핑되어야 합니다.
> [!div class="mx-imgBorder"]
> ![기본 키 및 특성 유형 B2B](media/configure-data-map-edit-b2b.png "기본 키 및 특성 유형 B2B")

## <a name="next-step"></a>다음 단계

데이터 통합 프로세스의 일부로 **일치** 페이지로 이동합니다. 이 단계에 대해 배우려면 [**일치**](match-entities.md)를 방문하십시오.

> [!TIP]
> 다음 비디오를 확인하십시오. [시작하기: 통합 고객 프로필 만들기](https://youtu.be/oBfGEhucAxs).


[!INCLUDE[footer-include](../includes/footer-banner.md)]