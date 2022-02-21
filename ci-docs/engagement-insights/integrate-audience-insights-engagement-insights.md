---
title: 대상 그룹 인사이트와 참여 인사이트 사이에 링크 만들기
description: 대상 그룹 인사이트와 참여 인사이트 사이에 활성 링크를 만들어 양방향 데이터 공유를 가능하게 합니다.
ms.date: 09/08/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6aadd6b5018f63362f86c0e3e3ce085e94c47391
ms.sourcegitcommit: 5dd32dc2b18027cf2aa954356dded4bc6aab9801
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2022
ms.locfileid: "8116022"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>대상 그룹 인사이트와 참여 인사이트 사이에 링크 만들기

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

참여 인사이트와 대상 그룹 인사이트의 통합을 통해 두 기능의 환경을 연결하고 데이터를 양방향으로 공유할 수 있습니다.

참여 인사이트에서 더 많은 분석 옵션을 보려면 대상 그룹 인사이트의 통합 프로필 및 세그먼트를 사용하십시오. 참여 인사이트에서 비즈니스 가치가 높은 이벤트를 내보냅니다. 이 이벤트를 사용하여 대상 그룹 인사이트의 통합 프로필에 데이터를 추가합니다.

## <a name="prerequisites"></a>필수 조건

- 대상 그룹 인사이트 프로필은 자체 Azure Data Lake Storage 계정 또는 [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro)&ndash;관리형 데이터 레이크에 저장해야 합니다. 
- 대상 그룹 인사이트 환경에는 연결된 Dataverse 환경이 있어야 합니다. 또한 해당 환경에서 데이터 저장을 위해 Dataverse을 사용하는 경우 대상 그룹 인사이트에서 **데이터 공유 활성화** 옵션을 선택해야 합니다. 자세한 내용은 [대상 그룹 인사이트에서 환경 만들기 및 구성](../audience-insights/create-environment.md)을 참조하세요.
- 참여 인사이트와 대상 그룹 인사이트 환경 모두에 관리자 권한이 필요합니다.
- 연결된 환경은 동일한 지리적 지역에 있어야 합니다.

> [!NOTE]
> - 대상 그룹 인사이트 구독이 내부적으로 관리형 데이터 레이크의 대상 그룹 인사이트를 사용하는 평가판인 경우 [pirequest@microsoft.com](mailto:pirequest@microsoft.com)에 문의하여 도움을 받으십시오. 
> - 대상 그룹 인사이트 환경에서 자체 Azure Data Lake Storage을 사용하여 데이터를 저장하는 경우 스토리지 계정에 참여 인사이트 Azure 서비스 주체를 추가해야 합니다. 자세한 내용은 [대상 그룹 인사이트를 위해 Azure 서비스 주체를 사용하여 Azure Data Lake Storage 계정에 연결](../audience-insights/connect-service-principal.md)을 참고하십시오. 


## <a name="create-an-environment-link"></a>환경 링크 만들기

참여 인사이트에서 **관리자** > **환경** 설정을 업데이트하여 환경 링크를 만들 수 있습니다.

**대상 그룹 인사이트와 참여 인사이트 사이에 활성화 링크를 구축하는 방법**

1. **환경 관리자** 페이지에서 **링크 환경** 탭을 선택합니다.

    :::image type="content" source="media/integrate1.png" alt-text="환경 설정.":::

1. 화면 왼쪽 상단 코너 또는 하단에서 **환경 설정** 을 선택합니다.

     :::image type="content" source="media/integrate2.png" alt-text="대상 그룹 인사이트 환경 선택.":::

1. 대상 그룹 인사이트 환경을 선택한 다음 ***다음** 을 ​​선택하여 완료합니다. 이제 연결된 환경에 대한 옵션 기능을 선택할 수 있습니다.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>대상 그룹 통찰 통합 프로필 특성 및 세그먼트 활성화

환경을 연결한 후 연결된 환경에 대한 옵션 기능을 선택할 수 있습니다. 이러한 기능을 사용하면 고객 데이터에 대한 대화형 분석을 위해 대상 그룹 인사이트에서 통합된 프로필 속성 및 세그먼트를 사용할 수 있습니다.

> [!IMPORTANT]
> 대상 그룹 인사이트 세그먼트가 참여 인사이트에 표시되려면 먼저 [병합 및 다운스트림 프로세스를 실행](../audience-insights/merge-entities.md)해야 합니다. 다운스트림 프로세스는 참여 인사이트와 공유할 대상 그룹 인사이트 세그먼트를 준비하는 고유한 테이블을 생성하기 때문에 중요합니다. (시스템 새로 고침이 예약된 경우 다운스트림 프로세스가 자동으로 포함됩니다.)

**참여 인사이트에서 웹 데이터를 분석하는 방법**

1. **환경 관리자** 페이지에서 **참여 인사이트와 대상 그룹 인사이트의 데이터 공유** 토글을 켜고 **다음** 을 선택합니다.

    :::image type="content" source="media/integrate4.png" alt-text="기능 선택.":::

1. 참여 인사이트의 차원이 될 통합 프로필의 특성을 선택합니다. (모든 특성이 유용한 차원은 아닙니다. 예를 들어 웹사이트 이벤트 분석을 위한 특성으로 **이름** 또는 **성** 이 필요하지 않을 수 있습니다.)

    :::image type="content" source="media/integrate5.png" alt-text="차원 큐레이트.":::

   >[!NOTE]
   > 식별자를 나타내는 모든 대상 그룹 인사이트 프로필 특성(예: **ID** 및 **대체 ID**)은 사용 가능한 속성에서 필터링되어 참여 인사이트의 차원이 됩니다.

1. 특성 선택이 완료되면 **다음** 을 선택합니다.
1. 참여 인사이트에서 대상 그룹 인사이트 프로필 차원 및 세그먼트를 볼 수 있는 사용자를 추가합니다.

    :::image type="content" source="media/integrate6.png" alt-text="고객 데이터에 대한 액세스 관리.":::

   > [!IMPORTANT]
   > 이 단계에서 사용자를 명시적으로 추가하지 않으면 참여 인사이트에서 데이터가 사용자에게 숨겨집니다.
   > 대상 그룹 인사이트 세그먼트가 참여 인사이트에 표시되려면 먼저 [병합 및 다운스트림 프로세스를 실행](../audience-insights/merge-entities.md)해야 합니다. 다운스트림 프로세스는 참여 인사이트와 공유할 대상 그룹 인사이트 세그먼트를 준비하는 고유한 테이블을 생성하기 때문에 중요합니다. (시스템 새로 고침이 예약된 경우 다운스트림 프로세스가 자동으로 포함됩니다.)

1. 선택한 사항을 검토한 다음 **마침** 을 선택하십시오.

    :::image type="content" source="media/integrate7.png" alt-text="고객 데이터 설정 검토.":::

## <a name="export-refined-events-to-audience-insights"></a>정리된 이벤트를 대상 그룹 인사이트로 내보내기

환경 간 링크를 생성한 후 참여 인사이트에서 대상 그룹 인사이트로 정리된 이벤트를 내보내고 새로운 데이터 원본으로 수집할 수 있습니다. 

자세한 내용은 [참여 인사이트의 웹 데이터를 대상 그룹 인사이트와 통합](../audience-insights/integrate-engagement-insights.md)을 참고하십시오.

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
