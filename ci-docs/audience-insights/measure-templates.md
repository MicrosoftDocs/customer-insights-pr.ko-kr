---
title: 템플릿에서 측정값 생성
description: 일반적인 사용 사례에 대한 템플릿을 사용하여 측정값을 정의합니다.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 0fe846691825b93732cbbe6d1c942a79e4a3934f
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359910"
---
# <a name="use-a-template-to-build-a-measure"></a>템플릿을 사용하여 측정값 빌드

일반적으로 사용되는 [측정값](measures.md)의 미리 정의된 템플릿을 사용하여 생성할 수 있습니다. 템플릿에 대한 자세한 설명과 안내식 경험은 효율적인 측정값 생성에 도움이 됩니다. 템플릿은 *통합 활동* 엔터티의 매핑된 데이터를 기반으로 합니다. 따라서 템플릿에서 측정값을 만들기 전에 [고객 활동](activities.md)을 구성했는지 확인하십시오.

사용자 지정 측정값을 만들려면 [측정값 빌더를 사용하여 처음부터 측정값 만들기](measure-builder.md)를 참조하세요.

# <a name="individual-consumers-b-to-c"></a>[개별 소비자(B2C)](#tab/b2c)

사용할 수 있는 측정값 템플릿: 
- 평균 거래 금액(ATV)
- 총 거래 금액
- 평균 일일 수익
- 평균 연간 수익
- 거래 횟수
- 획득한 로열티 포인트
- 사용한 로열티 포인트
- 잔여 로열티 포인트
- 활성 고객 수명
- 로열티 멤버십 기간
- 마지막 구매 후 경과 시간

## <a name="build-a-new-measure-using-a-template"></a>템플릿을 사용하여 새 측정값 작성

1. **측정값** 으로 이동합니다.

1. **신규** 를 선택하고 **템플릿 선택** 을 선택합니다.

   :::image type="content" source="media/measure-use-template.png" alt-text="템플릿이 강조 표시된 새 측정 값을 만들 때 드롭다운 메뉴의 스크린샷입니다.":::

1. 필요에 맞는 템플릿을 찾아 **템플릿 선택** 을 선택하십시오.

1. 필요한 데이터를 검토하고 모든 데이터가 제자리에 있다면 **시작** 을 선택합니다.

1. **이름 편집** 창에서 측정 및 출력 엔터티의 이름을 설정합니다. 

1. **완료** 를 선택합니다.

1. **기간 설정** 섹션에서 사용할 데이터의 시간 프레임을 정의합니다. 새 측정값이 전체 데이터 집합을 포함하도록 하려면 **항상** 을 선택하고 측정값이 특정 기간에 집중하도록 하려면 **특정 기간** 을 선택합니다.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="템플릿에서 측정값을 구성할 때 기간 섹션을 보여주는 스크린 샷입니다.":::

1. 다음 섹션에서 **데이터 추가** 를 선택하여 활동을 선택하고 *통합 활동* 엔터티의 해당 데이터를 매핑합니다.

    1. 1/2단계: **활동 유형** 에서 사용할 엔터티의 유형을 선택합니다. **활동** 에서 매핑할 엔터티를 선택합니다.
    1. 2/2단계: *통합 활동* 엔터티에서 공식에 필요한 구성 요소에 대한 특성을 선택합니다. 예를 들어 평균 트랜잭션 값의 경우 트랜잭션 값을 나타내는 특성입니다. **활동 타임 스탬프** 의 경우 통합 활동 엔터티에서 활동의 날짜 및 시간을 나타내는 특성을 선택하십시오.
   
1. 데이터 매핑이 성공하면 상태가 **완료** 로 표시되며 매핑된 활동 및 특성의 이름을 볼 수 있습니다.

1. 이제 **실행** 을 선택하여 측정 결과를 계산합니다. 나중에 수정하려면 **임시보관함에 저장** 을 선택합니다.

# <a name="business-accounts-b-to-b"></a>[비즈니스 어카운트(B2B)](#tab/b2b)

이 기능은 개별 고객이 기본 대상인 대상 그룹 환경에서 생성된 측정값에만 사용할 수 있습니다.

---
