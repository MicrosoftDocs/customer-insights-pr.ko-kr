---
title: GDPR에 따른 데이터 주체 권한(DSR) 요청 | Microsoft Docs
description: Dynamics 365 Customer Insights 대상 그룹 통계 기능에 대한 데이터 주체 요청에 응답합니다.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350277"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>GDPR에 따른 데이터 주체 권한(DSR) 요청

유럽 연합의 GDPR(일반 데이터 보호 규정)은 2018년 5월 25일부터 시행되었습니다. 개인에게 데이터와 관련하여 상당한 권리를 부여합니다. GDPR은 개인의 개인 정보 보호 권리를 보호하고 가능하게 하는 것입니다. [Microsoft 보안 센터](https://www.microsoft.com/trust-center)에서 보안 및 규정 준수에 대한 Microsoft의 노력에 대해 자세히 알아볼 수 있습니다.

우리는 고객이 GDPR 요구 사항을 충족할 수 있도록 최선을 다하고 있습니다. 여기에는 사용자 ID, 전화번호 및 이메일 주소와 같은 개인 정보가 포함된 데이터를 삭제하고 내보낼 수 있는 권한이 포함됩니다. 관리자는 개인 데이터를 삭제하거나 내보내는 사용자 요청을 구현할 수 있습니다.

## <a name="audience-insights"></a>대상 그룹 인사이트

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Dynamics 365 Customer Insights 대상 그룹 인사이트 기능에 대한 GDPR 데이터 주체 삭제 요청에 응답

조직의 고객 데이터에서 개인 데이터를 "제거할 수 있는 권한"은 일반 데이터 보호 규정(GDPR)에서 핵심적인 보호입니다. 개인 데이터 제거에는 감사 로그 정보를 제외한 모든 개인 데이터 및 시스템 생성 로그 제거가 포함됩니다.

#### <a name="manage-data-subject-delete-requests"></a>데이터 주체 삭제 요청 관리

대상 그룹 인사이트는 특정 고객 또는 Customer Insights 사용자의 개인 데이터를 삭제하기 위해 다음과 같은 제품 내 환경을 제공합니다.

- **고객 데이터에 대한 삭제 요청 관리**: Customer Insights의 고객 데이터는 Customer Insights 외부의 원래 데이터 원본에서 수집됩니다. 모든 GDPR 삭제 요청은 원래 데이터 원본에서 수행해야 합니다.
- **Customer Insights 사용자 데이터에 대한 삭제 요청 관리**: 사용자 데이터는 Customer Insights에서 생성됩니다. 모든 GDPR 삭제 요청은 Customer Insights에서 수행해야 합니다.

##### <a name="manage-requests-to-delete-customer-data"></a>고객 데이터 삭제 요청 관리

Customer Insights 관리자는 다음 단계에 따라 데이터 원본에서 삭제된 고객 데이터를 제거할 수 있습니다.

1. Dynamics 365 Customer Insights에 로그인합니다.
2. 대상 그룹 인사이트에서 **데이터** > **데이터 원본** 으로 이동합니다.
3. 삭제된 고객 데이터가 포함된 목록의 각 데이터 원본의 경우:
   1. (...)을 선택하고 **새로 고침** 을 선택합니다.
   2. **상태** 아래에서 데이터 원본의 상태를 확인합니다. 확인 표시는 새로 고침이 완료되었음을 나타냅니다. 경고 삼각형은 문제가 있음을 의미합니다. 경고 삼각형이 표시되면 D365CI@microsoft.com에 문의하십시오.

> [!div class="mx-imgBorder"]
> ![고객 데이터에 대한 GDPR 삭제 요청 처리.](audience-insights/media/gdpr-data-sources.png "고객 데이터에 대한 GDPR 삭제 요청 처리")

##### <a name="manage-delete-requests-for-user-data"></a>사용자 데이터에 대한 삭제 요청 관리

Customer Insights 관리자는 다음 단계에 따라 Customer Insights 사용자 데이터를 삭제할 수 있습니다.

1. Dynamics 365 Customer Insights에 로그인합니다.
2. 대상 그룹 인사이트에서 **관리** > **권한** 으로 이동합니다.
3. 삭제하려는 사용자의 확인란을 선택합니다.
4. **제거** 를 선택합니다.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>GDPR 데이터 주체 내보내기 요청에 응답

일반 데이터 보호 규정(GDPR)을 향한 여정에서 귀하와 파트너 관계를 맺겠다는 약속의 일환으로, 준비에 도움이 되는 문서를 개발했습니다. 이 문서에서는 대상 그룹 인사이트를 사용할 때 GDPR 규정 준수를 지원하기 위해 오늘 수행할 수 있는 단계를 설명합니다.

#### <a name="manage-export-and-view-requests"></a>내보내기 및 보기 요청 관리

데이터 이식성의 권리는 데이터 주체가 다른 데이터 컨트롤러로 전송될 수 있는 전자 형식(“구조화되고, 일반적으로 사용되며, 기계 판독 가능하며, 상호 운용 가능한 형식”으로 정의됨)으로 개인 데이터의 복사본을 요청할 수 있도록 합니다.

##### <a name="export-customer-data-tenant-admin"></a>고객 데이터 내보내기(테넌트 관리자)

테넌트 관리자는 다음 단계에 따라 데이터를 내보낼 수 있습니다.

1. 요청에 고객의 전자 메일 주소를 지정하여 D365CI@microsoft.com으로 전자 메일을 보냅니다. Customer Insights 팀은 등록된 테넌트 관리자 이메일 주소로 이메일을 보내 데이터 내보내기 확인을 요청합니다.
2. 요청한 고객의 데이터를 내보내려면 확인을 승인합니다.
3. 테넌트 관리자 전자 메일 주소를 통해 내보낸 데이터를 받습니다.

##### <a name="export-user-data-tenant-admin"></a>사용자 데이터 내보내기(테넌트 관리자)

1. 요청에 사용자의 전자 메일 주소를 지정하여 D365CI@microsoft.com으로 전자 메일을 보냅니다. Customer Insights 팀은 등록된 테넌트 관리자 이메일 주소로 이메일을 보내 데이터 내보내기 확인을 요청합니다.
2. 요청한 사용자의 데이터를 내보내려면 확인을 승인합니다.
3. 테넌트 관리자 전자 메일 주소를 통해 내보낸 데이터를 받습니다.

## <a name="consent-management-preview"></a>동의 관리(프리뷰)

동의 관리 기능은 사용자 데이터를 직접 수집하지 않습니다. 다른 애플리케이션에서 사용자가 제공한 동의 데이터만 가져와서 처리합니다.

특정 사용자에 대한 동의 데이터를 제거하려면 동의 관리 기능에 수집된 데이터 소스에서 제거하십시오. 데이터 원본를 새로 고침하면 제거된 데이터가 동의 센터에서도 삭제됩니다. 동의 엔터티를 사용하는 애플리케이션은 [새로 고침](audience-insights/system.md#refresh-processes)한 이후 소스에서 제거된 데이터도 삭제합니다. 다른 모든 프로세스 및 애플리케이션에서 사용자 데이터를 제거하라는 데이터 주체 요청에 응답한 후 데이터 원본을 빠르게 새로 고치는 것이 좋습니다.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]