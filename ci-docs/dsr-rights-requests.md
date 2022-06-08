---
title: GDPR에 따른 데이터 주체 권한(DSR) 요청 | Microsoft Docs
description: Dynamics 365 Customer Insights에 대한 데이터 주체 요청에 응답합니다.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: af2583295627f98e980adbca4f216b9c34c3cad8
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808569"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>GDPR에 따른 데이터 주체 권한(DSR) 요청

유럽 연합의 GDPR(일반 데이터 보호 규정)은 2018년 5월 25일부터 시행되었습니다. 개인에게 데이터와 관련하여 상당한 권리를 부여합니다. GDPR은 개인의 개인 정보 보호 권리를 보호하고 가능하게 하는 것입니다. [Microsoft 보안 센터](https://www.microsoft.com/trust-center)에서 보안 및 규정 준수에 대한 Microsoft의 노력에 대해 자세히 알아볼 수 있습니다.

우리는 고객이 GDPR 요구 사항을 충족할 수 있도록 최선을 다하고 있습니다. 여기에는 사용자 ID, 전화번호 및 이메일 주소와 같은 개인 정보가 포함된 데이터를 삭제하고 내보낼 수 있는 권한이 포함됩니다. 관리자는 개인 데이터를 삭제하거나 내보내는 사용자 요청을 구현할 수 있습니다.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights에 대한 GDPR 데이터 주체 삭제 요청에 응답

조직의 고객 데이터에서 개인 데이터를 "제거할 수 있는 권한"은 일반 데이터 보호 규정(GDPR)에서 핵심적인 보호입니다. 개인 데이터 제거에는 감사 로그 정보를 제외한 모든 개인 데이터 및 시스템 생성 로그 제거가 포함됩니다.

#### <a name="manage-data-subject-delete-requests"></a>데이터 주체 삭제 요청 관리

Customer Insights는 특정 고객 또는 사용자의 개인 데이터를 삭제하기 위해 다음과 같은 제품 내 경험을 제공합니다.

- **고객 데이터에 대한 삭제 요청 관리**: Customer Insights의 고객 데이터는 Customer Insights 외부의 원래 데이터 원본에서 수집됩니다. 모든 GDPR 삭제 요청은 원래 데이터 원본에서 수행해야 합니다.
- **Customer Insights 사용자 데이터에 대한 삭제 요청 관리**: 사용자 데이터는 Customer Insights에서 생성됩니다. 모든 GDPR 삭제 요청은 Customer Insights에서 수행해야 합니다.

##### <a name="manage-requests-to-delete-customer-data"></a>고객 데이터 삭제 요청 관리

Customer Insights 관리자는 다음 단계에 따라 데이터 원본에서 삭제된 고객 데이터를 제거할 수 있습니다.

1. Dynamics 365 Customer Insights에 로그인합니다.
2. **데이터** > **데이터 원본** 으로 이동
3. 삭제된 고객 데이터가 포함된 목록의 각 데이터 원본의 경우:
   1. 세로 줄임표(&vellip;)를 선택한 다음 **새로 고침** 을 선택합니다.
   2. **상태** 아래에서 데이터 원본의 상태를 확인합니다. 확인 표시는 새로 고침이 완료되었음을 나타냅니다. 경고 삼각형은 문제가 있음을 의미합니다. 경고 삼각형이 표시되면 D365CI@microsoft.com에 문의하십시오.

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

## <a name="consent-management-preview"></a>동의 관리(프리뷰)

동의 관리 기능은 사용자 데이터를 직접 수집하지 않습니다. 다른 애플리케이션에서 사용자가 제공한 동의 데이터만 가져와서 처리합니다.

특정 사용자에 대한 동의 데이터를 제거하려면 동의 관리 기능에 수집된 데이터 소스에서 제거하십시오. 데이터 원본를 새로 고침하면 제거된 데이터가 동의 센터에서도 삭제됩니다. 동의 엔터티를 사용하는 애플리케이션은 [새로 고침](system.md#refresh-processes)한 이후 소스에서 제거된 데이터도 삭제합니다. 다른 모든 프로세스 및 애플리케이션에서 사용자 데이터를 제거하라는 데이터 주체 요청에 응답한 후 데이터 원본을 빠르게 새로 고치는 것이 좋습니다.

[!INCLUDE [footer-include](includes/footer-banner.md)]