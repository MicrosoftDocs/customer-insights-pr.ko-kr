---
title: 의미 체계 매핑(미리 보기)
description: 의미 체계 매핑 개요 및 사용 방법.
ms.date: 12/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: a60855f6d5616ca9b958752836d1071ae3433db0
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647056"
---
# <a name="semantic-mappings-preview"></a>의미 체계 매핑(미리 보기)

의미 체계 매핑을 사용하면 비활동 데이터를 미리 정의된 스키마에 매핑할 수 있습니다. 이러한 스키마는 Customer Insights가 데이터 속성을 더 잘 이해하는 데 도움이 됩니다. 시맨틱 매핑과 제공된 데이터는 Customer Insights에서 새로운 인사이트와 기능을 가능하게 합니다. 활동 데이터를 스키마에 매핑하려면 [활동 문서](activities.md)를 검토합니다.

**의미 체계 매핑은 현재 비즈니스 계정을 기반으로 하는 환경에 대해 사용** 되어 있습니다. *ContactProfile* 은 현재 Customer Insights에서 사용할 수 있는 유일한 유형의 의미 체계 매핑입니다.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>ContactProfile 의미 체계 엔티티 매핑 정의

1. **데이터** > **의미 체계 매핑(프리뷰)** 로 이동합니다.

1. **의미 체계 매핑 추가** 를 선택하여 안내 환경을 시작합니다.

1. **엔터티 데이터** 단계에서 다음 필드의 값을 설정합니다.

   - **의미 체계 엔터티 매핑 이름**: 의미 체계 엔터티 매핑의 이름을 제공합니다.
   - **소스 엔티티** : 연락처 데이터가 포함된 엔터티를 선택합니다.
   - **기본 키**: 연락처 레코드를 고유하게 식별하는 필드를 선택합니다. 중복 값, 빈 값 또는 누락된 값을 포함해서는 안됩니다.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="이름, 소스 엔터티 및 기본 키로 의미 엔터티 매핑 설정.":::

1. **다음** 을 선택하여 작업을 계속할 수 있습니다.

1. **관계** 단계에서 연락처 데이터를 해당 계정 데이터에 연결하도록 세부 정보를 구성합니다. 이 단계는 엔터티 간의 연결을 시각화합니다.  

   구현할 수 있는 관계 경로에는 **직접 관계** 와 **간접 관계** 의 두 가지 유형이 있습니다. 자세한 내용은 [직접 및 간접 관계 경로](relationships.md#relationship-paths)에서 확인하세요.

   1. **관계 추가** 를 선택하여 관계를 구성합니다.
   1. 연락처 엔터티를 다른 엔터티에 연결하는 원본 엔터티에서 특성을 선택합니다.
   1. 연락처 엔터티를 연결할 엔터티를 선택합니다. **계정 엔터티** 또는 **중간 엔터티** 섹션에서 엔터티를 선택할 수 있습니다. 중간 엔터티를 선택하는 경우 대상 계정 엔터티에 연결할 두 번째 관계를 정의해야 합니다.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="계정 엔터티 또는 중간 엔터티 선택.":::

   1. **관계 이름** 을 제공합니다. 엔터티 간의 관계가 이미 존재하는 경우 관계 이름은 읽기 전용입니다. 관계가 없으면 제공한 이름으로 새 관계가 생성됩니다.
   1. **적용** 을 선택하여 관계 구성을 완료합니다.

   > [!NOTE]
   > 연락처 엔터티와 중간 엔터티가 있는 다른 계정 엔터티 간에 더 많은 관계를 구성할 수 있습니다.
   >  :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="다양한 관계의 시각화는 연락처 엔터티를 계정 엔터티에 연결.":::

1. 관계 구성이 완료되면 **다음** 을 선택합니다.

1. **의미 체계 유형 설정** 단계에서 **의미 체계 유형** 을 선택합니다. 현재 *ContactProfile* 이라는 하나의 **의미 체계** 유형이 있습니다.

1. 표시된 필드의 *ContactProfile* **의미 체계 유형** 에 데이터를 매핑합니다.
   - 필수 필드: 연락처 ID
   - 선택 필드: 이름, 성, 생년월일, 성별, 기본 이메일 및 기본 전화

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="연락처 데이터 특성을 제공된 필수 및 선택 필드에 매핑.":::

1. **다음** 을 선택하여 작업을 계속할 수 있습니다.

1. **검토** 단계에서 의미 체계 매핑의 구성을 살펴봅니다. 변경하려면 해당 섹션에 대해 **편집** 을 선택합니다.

1. **저장** 을 선택하여 새 **의미 체계 매핑** 을 저장합니다.

1. 저장 후 의미 체계 매핑 **실행** 을 선택하거나 **닫기** 를 선택하여 의미 매핑을 처리하지 않고 저장할 수 있습니다.

1. 의미 체계 매핑을 나중에 실행하려면 의미 체계 매핑을 선택하고 **새로 고침** 을 선택합니다.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>기존 의미 체계 매핑 관리

**데이터** > **의미 체계 매핑(미리 보기)** 에서 저장된 모든 의미 체계 매핑을 보고 관리할 수 있습니다. 각 의미 체계 매핑은 별도의 행으로 표시됩니다. 소스 엔터티, 의미 체계 유형, 매핑 유형 및 해당 상태에 대한 세부 정보를 찾을 수 있습니다.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="의미 체계 매핑을 관리하는 옵션.":::

- **편집**: 검토 단계에서 의미 체계 매핑 설정의 구성을 엽니다. 현재 구성을 변경할 수 있습니다. **저장** 및 **실행** 을 선택하여 변경 사항을 처리합니다.

- **새로 고침**: 구성의 일부인 엔터티의 최신 데이터로 선택한 의미 체계 매핑을 새로 고칩니다. 주어진 의미 체계 매핑을 새로 고치면 동일한 유형의 모든 의미 체계 매핑이 새로 고쳐집니다.

- **이름 바꾸기**: 선택한 의미 체계 매핑에 대해 다른 이름을 입력할 수 있는 대화 상자를 엽니다. **저장** 을 선택하여 변경 내용을 적용합니다.

- **삭제** : 선택한 의미 체계 매핑의 삭제를 확인하는 대화 상자를 엽니다. 의미 체계 매핑 및 삭제 아이콘을 선택하여 한 번에 둘 이상의 의미 체계 매핑을 삭제할 수도 있습니다. **삭제** 를 선택하여 확인합니다.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>ContactProfile 시맨틱 엔터티 매핑을 사용하여 연락처 수준 활동 생성

*ContactProfile* 시맨틱 엔터티 매핑을 생성한 후 연락처의 활동을 캡처할 수 있습니다. 이를 통해 계정의 활동 타임라인에서 각 활동을 담당한 담당자를 확인할 수 있습니다. 대부분의 단계는 일반적인 활동 매핑 구성을 따릅니다.

   > [!NOTE]
   > 연락처 수준 활동이 작동하려면 활동 데이터 내의 각 레코드에 대해 **AccountID** 와 **ContactID** 속성이 모두 있어야 합니다.

1. [*ContactProfile* 시맨틱 엔터티 매핑 정의](#define-a-contactprofile-semantic-entity-mapping) 그리고 시맨틱 매핑을 실행합니다.

1. **데이터** > **활동** 으로 이동합니다.

1. 새 활동을 만들려면 **활동 추가** 를 선택합니다.

1. 활동의 이름을 지정하고 소스 활동 엔터티를 선택한 다음 활동 엔터티의 기본 키를 선택합니다.

1. **관계** 단계에서 연락처 데이터를 중간 엔터티로 사용하여 활동 소스 데이터와 계정 간의 간접 관계를 만듭니다. 자세한 내용은 [직접 및 간접 관계 경로](relationships.md#relationship-paths)에서 확인하세요.
   - *구매* 활동에 대한 예시 관계:
      - **ContactID** 속성에서 **구매 원본 활동 데이터** > **연락처 데이터**
      - **AccountID** 속성에서 **연락처 데이터** > **계정 데이터**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="예시 관계 설정":::

1. 관계를 설정한 후 **다음** 을 선택하고 활동 매핑 구성을 완료합니다. 활동 생성에 대한 자세한 단계는 [활동 정의](activities.md)를 참조하세요.

1. 활동 매핑을 실행합니다.

1. 이제 연락처 수준 활동이 고객 타임라인에 표시됩니다.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="연락처 활동 구성 후 최종 결과":::

### <a name="contact-level-activity-timeline-filtering"></a>연락처 수준 활동 타임라인 필터링

연락처 수준 활동 매핑을 구성하고 실행하면 고객의 활동 타임라인이 업데이트됩니다. 여기에는 *ContactProfile* 구성에 따라 작업한 활동에 대해 귀하의 ID 또는 이름이 포함됩니다. 타임라인에서 연락처별로 활동을 필터링하여 관심 있는 특정 연락처를 볼 수 있습니다. 또한 **연락처에 매핑되지 않은 활동** 을 선택하여 특정 연락처에 할당되지 않은 모든 활동을 볼 수 있습니다.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="연락처 수준 활동에 사용할 수 있는 필터링 옵션.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
