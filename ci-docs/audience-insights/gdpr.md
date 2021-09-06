---
title: GDPR에 따른 데이터 주체 권한(DSR) 요청 | Microsoft Docs
description: Dynamics 365 Customer Insights 대상 그룹 통계 기능에 대한 데이터 주체 요청에 응답합니다.
ms.date: 05/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 891794321f20954533ec0374b397eaf6b30445c2b0c95f601009912b3c3950a7
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034507"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>GDPR에 따른 데이터 주체 권한(DSR) 요청

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Dynamics 365 Customer Insights 대상 그룹 인사이트 기능에 대한 GDPR 데이터 주체 삭제 요청에 응답

조직의 고객 데이터에서 개인 데이터를 "제거할 수 있는 권한"은 일반 데이터 보호 규정(GDPR)에서 핵심적인 보호입니다. 개인 데이터 제거에는 감사 로그 정보를 제외한 모든 개인 데이터 및 시스템 생성 로그 제거가 포함됩니다.

### <a name="manage-data-subject-delete-requests"></a>데이터 주체 삭제 요청 관리

대상 그룹 인사이트는 특정 고객 또는 Customer Insights 사용자의 개인 데이터를 삭제하기 위해 다음과 같은 제품 내 환경을 제공합니다.

- **고객 데이터에 대한 삭제 요청 관리**: Customer Insights의 고객 데이터는 Customer Insights 외부의 원래 데이터 원본에서 수집됩니다. 모든 GDPR 삭제 요청은 원래 데이터 원본에서 수행해야 합니다.
- **Customer Insights 사용자 데이터에 대한 삭제 요청 관리**: 사용자 데이터는 Customer Insights에서 생성됩니다. 모든 GDPR 삭제 요청은 Customer Insights에서 수행해야 합니다.

#### <a name="manage-delete-requests-for-customer-data"></a>고객 데이터에 대한 삭제 요청 관리

Customer Insights 관리자는 다음 단계에 따라 데이터 원본에서 삭제된 고객 데이터를 제거할 수 있습니다.

1. Dynamics 365 Customer Insights에 로그인합니다.
2. 대상 그룹 인사이트에서 **데이터** > **데이터 원본** 으로 이동합니다.
3. 삭제된 고객 데이터가 포함된 목록의 각 데이터 원본의 경우:
   1. (...)을 선택하고 **새로 고침** 을 선택합니다.
   2. **상태** 아래에서 데이터 원본의 상태를 확인합니다. 확인 표시는 새로 고침이 완료되었음을 나타냅니다. 경고 삼각형은 문제가 있음을 의미합니다. 경고 삼각형이 표시되면 D365CI@microsoft.com에 문의하십시오.

> [!div class="mx-imgBorder"]
> ![고객 데이터에 대한 GDPR 삭제 요청 처리.](media/gdpr-data-sources.png "고객 데이터에 대한 GDPR 삭제 요청 처리")

#### <a name="manage-delete-requests-for-user-data"></a>사용자 데이터에 대한 삭제 요청 관리

Customer Insights 관리자는 다음 단계에 따라 Customer Insights 사용자 데이터를 삭제할 수 있습니다.

1. Dynamics 365 Customer Insights에 로그인합니다.
2. 대상 그룹 인사이트에서 **관리** > **권한** 으로 이동합니다.
3. 삭제하려는 사용자의 확인란을 선택합니다.
4. **제거** 를 선택합니다.

> [!div class="mx-imgBorder"]
> ![사용자 데이터에 대한 GDPR 삭제 요청 처리.](media/gdpr-permissions.png "사용자 데이터에 대한 GDPR 삭제 요청 처리")

## <a name="responding-to-gdpr-data-subject-export-requests"></a>GDPR 데이터 주체 내보내기 요청에 응답

일반 데이터 보호 규정(GDPR)을 향한 여정에서 귀하와 파트너 관계를 맺겠다는 약속의 일환으로, 준비에 도움이 되는 문서를 개발했습니다. 이 문서에서는 대상 그룹 인사이트를 사용할 때 GDPR 규정 준수를 지원하기 위해 오늘 수행할 수 있는 단계를 설명합니다.

### <a name="manage-export-and-view-requests"></a>내보내기 및 보기 요청 관리

데이터 이식성의 권리는 데이터 주체가 다른 데이터 컨트롤러로 전송될 수 있는 전자 형식(“구조화되고, 일반적으로 사용되며, 기계 판독 가능하며, 상호 운용 가능한 형식”으로 정의됨)으로 개인 데이터의 복사본을 요청할 수 있도록 합니다.

#### <a name="export-customer-data-tenant-admin"></a>고객 데이터 내보내기(테넌트 관리자)

테넌트 관리자는 다음 단계에 따라 데이터를 내보낼 수 있습니다.

1. 요청에 고객의 전자 메일 주소를 지정하여 D365CI@microsoft.com으로 전자 메일을 보냅니다. Customer Insights 팀은 등록된 테넌트 관리자 이메일 주소로 이메일을 보내 데이터 내보내기 확인을 요청합니다.
2. 요청한 고객의 데이터를 내보내려면 확인을 승인합니다.
3. 테넌트 관리자 전자 메일 주소를 통해 내보낸 데이터를 받습니다.

#### <a name="export-user-data-tenant-admin"></a>사용자 데이터 내보내기(테넌트 관리자)

1. 요청에 사용자의 전자 메일 주소를 지정하여 D365CI@microsoft.com으로 전자 메일을 보냅니다. Customer Insights 팀은 등록된 테넌트 관리자 이메일 주소로 이메일을 보내 데이터 내보내기 확인을 요청합니다.
2. 요청한 사용자의 데이터를 내보내려면 확인을 승인합니다.
3. 테넌트 관리자 전자 메일 주소를 통해 내보낸 데이터를 받습니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]