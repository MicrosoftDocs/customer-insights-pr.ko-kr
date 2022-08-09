---
title: GDPR에 따른 데이터 주체 권한(DSR) 요청 | Microsoft Docs
description: Dynamics 365 Customer Insights에 대한 데이터 주체 요청에 응답합니다.
ms.date: 05/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6c6ce49c18de3a09d28138316d893e6842919042
ms.sourcegitcommit: ff0f4b5664d995870c91adb87c7d3780a582efca
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/13/2022
ms.locfileid: "9146703"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>GDPR에 따른 데이터 주체 권한(DSR) 요청

유럽 연합의 GDPR(일반 데이터 보호 규정)은 2018년 5월 25일부터 시행되었습니다. 개인에게 데이터와 관련하여 상당한 권리를 부여합니다. GDPR은 개인의 개인 정보 보호 권리를 보호하고 가능하게 하는 것입니다. [Microsoft 보안 센터](https://www.microsoft.com/trust-center)에서 보안 및 규정 준수에 대한 Microsoft의 노력에 대해 자세히 알아볼 수 있습니다.

우리는 고객이 GDPR 요구 사항을 충족할 수 있도록 최선을 다하고 있습니다. 여기에는 사용자 ID, 전화번호 및 이메일 주소와 같은 개인 정보가 포함된 데이터를 삭제하고 내보낼 수 있는 권한이 포함됩니다. 관리자는 개인 데이터를 삭제하거나 내보내는 사용자 요청을 구현할 수 있습니다.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights에 대한 GDPR 데이터 주체 삭제 요청에 응답

조직의 고객 데이터에서 개인 데이터를 "제거할 수 있는 권한"은 일반 데이터 보호 규정(GDPR)에서 핵심적인 보호입니다. 개인 데이터 제거에는 감사 로그 정보를 제외한 모든 개인 데이터 및 시스템 생성 로그 제거가 포함됩니다.

#### <a name="manage-data-subject-delete-requests"></a>데이터 주체 삭제 요청 관리

Customer Insights는 특정 고객 또는 사용자의 개인 데이터를 삭제하기 위해 다음과 같은 제품 내 경험을 제공합니다.

- **고객 데이터에 대한 삭제 요청 관리**: Customer Insights의 고객 데이터는 Customer Insights 외부의 원래 데이터 원본에서 수집됩니다. GDPR 삭제 요청을 기본 데이터 원본에서 먼저 수행합니다.
- **Customer Insights 사용자 데이터에 대한 삭제 요청 관리**: 사용자 데이터는 Customer Insights에서 생성됩니다. 모든 GDPR 삭제 요청은 Customer Insights에서 수행해야 합니다.

##### <a name="manage-requests-to-delete-customer-data"></a>고객 데이터 삭제 요청 관리

Customer Insights 관리자는 다음 단계에 따라 데이터 원본에서 삭제된 고객 데이터를 제거할 수 있습니다. 다음에 나열된 단계를 진행하기 전에 데이터 원본에서 삭제 요청이 수행되었는지 확인하세요. 

1. Dynamics 365 Customer Insights에 로그인합니다.
1. **데이터** > **데이터 원본** 으로 이동
1. 삭제된 고객 데이터가 포함된 목록의 각 데이터 원본의 경우:
   1. 세로 줄임표(&vellip;)를 선택한 다음 **새로 고침** 을 선택합니다.
   1. **상태** 아래에서 데이터 원본의 상태를 확인합니다. 확인 표시는 새로 고침이 완료되었음을 나타냅니다. 경고 삼각형은 문제가 있음을 의미합니다. 경고 삼각형이 표시되면 D365CI@microsoft.com에 문의하십시오.
1. 데이터 원본 새로 고침을 완료한 다음 다운스트림 새로 고침도 실행합니다. 특히 Customer Insights의 전체 새로 고침 반복 작업이 예약되지 않은 경우입니다. 

> [!IMPORTANT]
> 정적 세그먼트는 삭제 요청 후 전체 새로 고침 또는 실행 중인 다운스트림 새로 고침에 포함되지 않습니다. 고객 데이터가 정적 세그먼트에서도 제거되도록 하려면 새로 고침 한 원본 데이터로 정적 세그먼트를 다시 생성하세요.

> [!div class="mx-imgBorder"]
> ![고객 데이터에 대한 GDPR 삭제 요청 처리.](media/gdpr-data-sources.png "고객 데이터에 대한 GDPR 삭제 요청 처리")

##### <a name="manage-delete-requests-for-user-data"></a>사용자 데이터에 대한 삭제 요청 관리

Customer Insights 관리자는 다음 단계에 따라 Customer Insights 사용자 데이터를 삭제할 수 있습니다.

1. Dynamics 365 Customer Insights에 로그인합니다.
2. **관리자** > **보안** > **권한** 으로 이동합니다.
3. 삭제하려는 사용자의 확인란을 선택합니다.
4. **제거** 를 선택합니다.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>GDPR 데이터 주체 내보내기 요청에 응답

일반 데이터 보호 규정(GDPR)을 준수하는 과정에서 귀하와 파트너 관계를 맺겠다는 약속의 일환으로, 당사는 귀하가 데이터 주체의 요청에 응답하는 데 도움이 되는 문서를 개발했습니다.

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

### <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights에서 데이터 삭제 처리

1. 데이터 파티션 및 데이터 스냅샷이 30일 이상 비활성 상태인 경우 데이터 파티션 및 데이터 스냅샷에 대한 데이터가 삭제됩니다. 즉, 데이터 원본의 새로 고침을 통해 새 데이터 파티션 및 스냅샷으로 교체되었음을 의미합니다.
2. 모든 데이터와 스냅샷이 삭제되지는 않습니다. 가장 최근의 데이터 파티션과 데이터 스냅샷은 Customer Insights에서 사용되므로 기본적으로 활성 상태입니다. 가장 최근 데이터의 경우 데이터 원본이 지난 30일 이내에 새로 고침 되지 않았는지 여부는 중요하지 않습니다.

[!INCLUDE [footer-include](includes/footer-banner.md)]
