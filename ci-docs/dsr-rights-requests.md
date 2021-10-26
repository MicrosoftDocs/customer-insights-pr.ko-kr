---
title: GDPR에 따른 데이터 주체 권한(DSR) 요청 | Microsoft Docs
description: Dynamics 365 Customer Insights 대상 그룹 통계 기능에 대한 데이터 주체 요청에 응답합니다.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6faaeb6a1ee34c3e5c8e7d465b37cee589bc920c
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483684"
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

## <a name="engagement-insights"></a>참여 인사이트

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>최종 사용자 식별 정보가 포함된 이벤트 데이터 삭제 및 내보내기

다음 섹션에서는 개인 데이터를 포함할 수 있는 이벤트 데이터를 삭제하고 내보내는 방법에 대해 설명합니다.

데이터를 삭제하거나 내보내려면:

1. 개인 정보 데이터가 포함된 이벤트 속성의 태그를 지정합니다.
2. 특정 값(예: 지정된 사용자 ID)과 관련된 데이터를 삭제하거나 내보냅니다.

#### <a name="tag-and-update-event-properties"></a>이벤트 속성에 태그 지정 및 업데이트

개인 데이터는 이벤트 속성 수준에서 태그가 지정됩니다. 먼저 삭제 또는 내보낼 속성에 태그를 지정합니다.

이벤트 속성에 개인 정보를 포함하는 태그를 지정하려면 다음 단계를 따르세요.

1. 이벤트가 포함된 작업 영역을 엽니다.

1. **데이터** > **이벤트** 로 이동하여 선택한 작업 영역의 이벤트 목록을 확인합니다.
  
1. 태그를 지정할 이벤트를 선택합니다.

1. **속성 편집** 을 선택하여 선택한 이벤트의 모든 속성을 나열하는 창을 엽니다.
     
1. **...** 를 선택한 다음 **편집** 을 선택하여 **속성 업데이트** 대화 상자를 엽니다.

   ![이벤트 편집.](engagement-insights/media/edit-event.png "이벤트 편집")

1. **속성 업데이트** 창에서 오른쪽 위 모서리에 있는 **...** 를 선택한 다음 **EUII 포함** 상자를 선택합니다. **업데이트** 를 선택하여 변경 내용을 저장합니다.

   ![변경 내용을 저장합니다.](engagement-insights/media/update-property.png "변경 내용 저장")

   > [!NOTE]
   > 이벤트 스키마가 변경되거나 새 이벤트를 생성할 때마다 관련 이벤트 속성을 평가하고 필요한 경우 개인 데이터를 포함하는 것으로 태그를 지정하거나 태그를 해제하는 것이 좋습니다.

#### <a name="delete-or-export-tagged-event-data"></a>태그가 지정된 이벤트 데이터 삭제 또는 내보내기

모든 이벤트 속성이 이전 단계에서 설명한 대로 적절하게 태그 지정된 경우 환경 관리자는 태그 지정된 이벤트 데이터에 대해 삭제 요청을 발행할 수 있습니다.

EUII 삭제 또는 내보내기 요청을 관리하려면

1. **관리** > **환경** > **설정** 으로 이동합니다.

1. **EUII(최종 사용자 식별 정보) 관리** 섹션에서 **EUII 관리** 를 선택합니다

##### <a name="deletion"></a>삭제 항목

삭제를 위해 **EUII(최종 사용자 식별 정보) 삭제** 섹션에 쉼표로 구분된 사용자 ID 목록을 입력할 수 있습니다. 이 ID는 정확한 문자열 일치를 통해 현재 환경에 있는 모든 프로젝트의 태그가 지정된 모든 이벤트 속성과 비교됩니다. 

속성 값이 제공된 ID 중 하나와 일치하면 연결된 이벤트가 영구적으로 삭제됩니다. 이 작업은 되돌릴 수 없으므로 **삭제** 를 선택한 후 삭제 항목을 확인해야 합니다.

##### <a name="export"></a>Export

내보내기 프로세스는 **EUII(최종 사용자 식별 정보) 내보내기** 섹션에서 이벤트 속성 값을 정의할 때 삭제 프로세스와 동일합니다. 또한 내보내기 대상을 지정하려면 **Azure Blob Storage URL** 을 제공해야 합니다. Azure Blob URL에는 [SAS(공유 액세스 서명)](/azure/storage/common/storage-sas-overview)가 포함되어야 합니다.

**내보내기** 를 선택하면 일치하는 태그 속성이 포함된 현재 팀의 모든 이벤트가 CSV 형식으로 내보내기 대상으로 내보내집니다.

### <a name="good-practices"></a>우수 사례

* 개인 데이터가 포함된 이벤트를 보내지 않도록 합니다.
* EUII 데이터가 포함된 이벤트를 보내야 하는 경우 EUII 데이터가 포함된 이벤트 및 이벤트 속성의 수를 제한하세요. 하나의 이벤트로 제한하는 것이 좋습니다.
* 전송된 개인 데이터에 액세스할 수 있는 사람은 가능한 한 적어야 합니다.
* 개인 데이터가 포함된 이벤트의 경우 특정 사용자에게 쉽게 연결할 수 있는 고유 식별자(예: 사용자 ID)를 생성하도록 하나의 속성을 설정해야 합니다. 이렇게 하면 데이터를 쉽게 분리하고 올바른 데이터를 내보내거나 삭제할 수 있습니다.
* 이벤트당 하나의 속성에만 개인 데이터가 포함된 것으로 태그를 지정하세요. 고유 식별자만 포함하는 것이 가장 좋습니다.
* 자세한 값(예: 전체 요청 본문)을 포함하는 속성에 태그를 지정하지 마세요. 참여 인사이트 기능은 삭제하거나 내보낼 이벤트를 결정할 때 정확한 문자열 일치를 사용합니다.

[!INCLUDE[footer-include](includes/footer-banner.md)]