---
title: Customer Insights의 세그먼트
description: 세그먼트 및 세그먼트 생성 및 관리 방법에 대한 개요입니다.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: d616ec8273115203dddb59334a348c66e72fa678
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800750"
---
# <a name="segments-overview"></a>세그먼트 개요

세그먼트를 사용하면 인구 통계, 트랜잭션 또는 행동 특성을 기반으로 고객을 그룹화할 수 있습니다. 세그먼트를 사용하여 판촉 캠페인, 판매 활동 및 고객 지원 조치를 대상으로 비즈니스 목표를 달성할 수 있습니다.

세그먼트 정의의 필터와 일치하는 고객 프로필을 세그먼트의 *구성원* 이라고 합니다. 약간의 [서비스 제한](/dynamics365/customer-insights/service-limits)이 적용됩니다.

## <a name="create-a-new-segment"></a>새 세그먼트 만들기

새 세그먼트를 만드는 방법에는 여러 가지가 있습니다. 

# <a name="individual-consumers-b-to-c"></a>[개별 소비자(B2C)](#tab/b2c)

- 세그먼트 빌더가 있는 복잡한 세그먼트: [직접 빌드](segment-builder.md#create-a-new-segment) 
- 연산자가 하나인 간단한 세그먼트: [빠른 세그먼트](segment-builder.md#quick-segments) 
- 유사한 고객을 찾는 AI 기반 방법: [유사 고객](find-similar-customer-segments.md) 
- 측정값 또는 속성을 기반으로 한 AI 기반 제안: [측정값 향상을 위한 제안 세그먼트](suggested-segments.md) 
- 활동에 따른 제안: [고객 활동에 기반한 제안 세그먼트](suggested-segments-activity.md) 

# <a name="business-accounts-b-to-b"></a>[비즈니스 어카운트(B2B)](#tab/b2b)

- 세그먼트 빌더가 있는 복잡한 세그먼트: [직접 빌드](segment-builder.md#create-a-new-segment)

---

## <a name="manage-existing-segments"></a>기존 세그먼트 관리

**세그먼트** 페이지로 이동하여 저장된 모든 세그먼트를 보고 관리합니다.

각 세그먼트는 세그먼트에 대한 추가 정보가 포함된 행으로 표시됩니다.

:::image type="content" source="media/segments-selected-segment.png" alt-text="옵션 드롭다운 목록 및 사용 가능한 옵션이 있는 선택된 세그먼트." lightbox="media/segments-selected-segment.png":::

세그먼트를 선택하면 다음 작업을 수행할 수 있습니다.

- **보기**: 구성원 수 추세를 포함한 세그먼트 세부 사항 및 세그먼트 구성원의 미리보기를 봅니다.
- **다운로드**: 구성원 목록을 .CSV 파일로 다운로드합니다.
- **편집**: 속성을 변경할 세그먼트를 편집합니다.
- 세그먼트의 **중복 항목을 만듭니다**. 속성을 즉시 편집하거나 복제본을 저장하도록 선택할 수 있습니다.
- **새로 고침**: 최신 데이터를 포함하도록 세그먼트를 새로 고칩니다.
- **활성화** 또는 **비활성화**: 세그먼트를 활성화하거나 비활성화합니다. 비활성 세그먼트의 경우 세그먼트 정의가 존재하지만 아직 고객이 포함되어 있지 않습니다. 활성 세그먼트는 세그먼트 정의와 일치하는 고객을 찾습니다. [예약된 새로 고침](system.md#schedule-tab)이 구성되었고 비활성 세그먼트에 **상태** 가 **건너뜀** 으로 나열되어 있으면 새로 고침이 시도되지 않았음을 나타냅니다. 비활성 세그먼트가 활성화되면 새로 고쳐지고 예약된 새로 고침에 포함됩니다.
  또는 **활성화/비활성화** 드롭다운의 **나중에 예약** 기능을 사용하여 특정 세그먼트의 활성화 및 비활성화에 대한 미래 날짜 및 시간을 지정할 수 있습니다.
- 세그먼트에서 **[유사한 고객 찾기](find-similar-customer-segments.md)** 를 수행합니다.
- **이름 바꾸기**: 세그먼트 이름을 바꿉니다.
- **태그**: 세그먼트에 대한 [태그를 관리](work-with-tags-columns.md#manage-tags)합니다.
- **다운로드**: 구성원 목록을 .CSV 파일로 다운로드합니다.
- **내보내기 관리** 내보내기 관련 세그먼트를 보고 관리합니다. [내보내기에 대해 자세히 알아보기.](export-destinations.md)
- **삭제**: 세그먼트를 삭제합니다.
- **열**: 표시되는 [열을 사용자 지정](work-with-tags-columns.md#customize-columns)합니다.
- **필터**: [태그를 필터링](work-with-tags-columns.md#filter-on-tags)합니다.
- **이름 검색**: 세그먼트 이름으로 검색합니다.

## <a name="refresh-segments"></a>세그먼트 새로 고침

**세그먼트** 페이지에서 **모두 새로 고침** 을 선택하여 모든 세그먼트를 한 번에 새로 고치거나 세그먼트를 선택할 때 하나 이상의 세그먼트를 새로 고치고 옵션에서 **새로 고침** 을 선택할 수 있습니다. 또는 **관리자** > **시스템** > **일정** 에서 반복 새로 고침을 구성할 수 있습니다. 반복 새로 고침이 구성된 경우 다음 규칙이 적용됩니다.

- **동적** 또는 **확장** 유형의 모든 세그먼트는 설정된 케이던스에서 자동으로 새로 고쳐집니다. 새로 고침이 완료되면 **상태** 가 세그먼트 새로 고침에 문제가 있었는지 나타냅니다. **마지막 새로 고침** 은 마지막으로 성공한 새로 고침의 타임스탬프를 보여줍니다. 오류가 발생하면 오류를 선택하여 발생한 상황에 대한 세부 정보를 확인합니다.
- 유형이 **정적** 인 세그먼트는 자동으로 새로 고침되지 *않습니다*. **마지막 새로 고침** 은 정적 세그먼트가 수동으로 실행되거나 새로 고쳐진 마지막 시간의 타임스탬프를 보여줍니다.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>세그먼트 내보내기

세그먼트 페이지 또는 [내보내기 페이지](export-destinations.md)에서 세그먼트를 내보낼 수 있습니다. 

1. **세그먼트** 페이지로 이동합니다.

1. 내보낼 세그먼트의 세로 줄임표(&vellip;)를 선택합니다.

1. 작업 드롭다운 목록에서 **내보내기 관리** 를 선택합니다.

1. **세그먼트에 대한 내보내기(미리 보기)** 페이지가 열립니다. 현재 세그먼트를 포함하는지 여부에 따라 그룹화된 구성된 모든 내보내기를 볼 수 있습니다.

   1. 선택한 세그먼트를 내보내기에 추가하려면 해당 내보내기를 **편집** 하여 해당 세그먼트를 선택한 다음 저장합니다. 개별 고객을 위한 환경에서는 대신 목록에서 내보내기를 선택하고 **세그먼트 추가** 를 선택하여 동일한 결과를 얻을 수 있습니다.

   1. 선택한 세그먼트로 새 내보내기를 만들려면 **내보내기 추가** 를 선택합니다. 내보내기 만들기에 대한 자세한 내용은 [새 내보내기 설정](export-destinations.md#set-up-a-new-export)을 참조하십시오.

1. 세그먼트의 기본 페이지로 돌아가려면 **뒤로** 를 선택합니다.

## <a name="track-usage-of-a-segment"></a>세그먼트 사용량 추적

Customer Insights와 연결된 동일한 Microsoft Dataverse 조직을 기반으로 하는 앱에서 세그먼트를 사용하는 경우 세그먼트 사용량을 추적할 수 있습니다. [Dynamics 365 Marketing의 고객 여정에 사용된 Customer Insights 세그먼트](/dynamics365/marketing/real-time-marketing-ci-profile)의 경우 시스템에서 해당 세그먼트의 사용에 대해 알려줍니다.

Customer Insights 환경 내에서 또는 Marketing의 고객 여정에서 사용 중인 세그먼트를 편집할 때 [세그먼트 빌더](segment-builder.md)의 배너가 종속성에 대해 알려줍니다. 배너에서 직접 또는 세그먼트 빌더에서 **사용량** 을 선택하여 종속성 세부 정보를 검사할 수 있습니다.

**세그먼트 사용량** 창은 Dataverse 기반 앱에서 이 세그먼트의 사용량에 대한 세부 정보를 보여줍니다. 고객 여정에 사용되는 세그먼트의 경우 이 세그먼트가 사용되는 Marketing에서 여정을 검사할 수 있는 링크를 찾을 수 있습니다. Marketing 앱에 액세스할 수 있는 권한이 있는 경우 해당 앱에서 자세한 내용에 액세스할 수 있습니다.

:::image type="content" source="media/segment-usage-pane.png" alt-text="세그먼트 빌더의 세그먼트 사용량에 대한 세부 정보가 있는 측면 창.":::

추적된 세그먼트를 삭제하려고 하면 시스템에서 추적된 세그먼트의 사용량에 대해 알려줍니다. 삭제하려는 세그먼트가 Marketing의 고객 여정에서 사용되는 경우 해당 여정은 해당 세그먼트의 모든 사용자에 대해 중지됩니다. 여정이 마케팅 캠페인의 일부인 경우 삭제는 해당 캠페인 자체에 영향을 미칩니다. 그러나 경고에도 불구하고 세그먼트를 삭제할 수 있습니다.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Dataverse 애플리케이션에서 세그먼트를 사용할 때 세그먼트 삭제를 확인하는 대화 상자.":::

### <a name="supported-apps"></a>지원되는 앱

사용량은 현재 다음 Dataverse 기반 앱에서 추적됩니다.

- [Dynamics 365 Marketing의 고객 여정](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="view-processing-history-and-segment-members"></a>처리 기록 및 세그먼트 구성원 보기

세그먼트 세부정보를 검토하여 세그먼트에 대한 통합 데이터를 볼 수 있습니다.

**세그먼트** 페이지에서 검토할 세그먼트를 선택합니다.

페이지의 상단 부분에는 구성원 수의 변화를 시각화하는 추세 그래프가 포함되어 있습니다. 데이터 포인트 위로 마우스를 가져가면 특정 날짜의 구성원 수를 확인할 수 있습니다.

시각화의 시간 프레임 업데이트할 수 있습니다.

> [!div class="mx-imgBorder"]
> ![세그먼트 시간 범위.](media/segment-time-range.png "세그먼트 시간 범위")

아래 부분에는 세그먼트 구성원 목록이 포함되어 있습니다.

> [!NOTE]
> 이 목록에 나타나는 필드는 세그먼트 엔터티의 특성을 기반으로 합니다.
>
>이 목록은 일치하는 세그먼트 구성원의 미리 보기이며 세그먼트의 처음 100개 레코드를 표시하므로 신속하게 평가하고 필요한 경우 정의를 검토할 수 있습니다. 일치하는 모든 레코드를 보려면 [세그먼트 내보내기](export-destinations.md)를 수행해야 합니다.

[!INCLUDE [footer-include](includes/footer-banner.md)]
