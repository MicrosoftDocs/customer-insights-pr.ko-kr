---
title: Microsoft Office 365의 데이터로 고객 프로필 보강
description: Microsoft Office의 독점 데이터를 사용하여 참여 데이터로 고객 프로필을 보강합니다.
ms.date: 12/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 782042ff643bd0cc70ac53e5680bfd0c68944d84
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646981"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>참여 데이터로 고객 프로필 보강(프리뷰)

Microsoft Office 365의 데이터를 사용하여 Office 365 앱을 통해 참여에 대한 인사이트로 고객 계정 프로필을 보강합니다. 참여 데이터는 계정 수준에서 집계되는 이메일 및 회의 활동으로 구성됩니다. 예를 들어 비즈니스 계정의 이메일 수 또는 계정과의 회의 수입니다. 개별 사용자에 대한 데이터는 제공되지 않습니다. 

이 보강은 영국, 유럽, 북미에서 사용할 수 있습니다.

## <a name="prerequisites"></a>필수 항목

보강을 구성하려면 다음 전제 조건이 충족되어야 합니다.

- 활성 Office 365 클라우드 라이선스가 있어야 합니다.
- [비즈니스 계정](work-with-business-accounts.md)을 기반으로 [통합된 고객 프로필](customer-profiles.md)이 있습니다.
- Customer Insights 환경에는 [첨부된 Microsoft Dataverse 조직](create-environment.md#step-3-connect-to-microsoft-dataverse)이 있어야 합니다.
- [관리자](permissions.md#admin) 권한이 있어야 합니다.
- Office 365 테넌트 관리자로부터 Dynamics 365 애플리케이션 내에서 **조직에 대한 인사이트** 를 제공하기 위해 Office 365 데이터를 사용하는 데 동의를 받았거나 받을 수 있어야 합니다.

## <a name="configure-the-enrichment"></a>보강 구성

1. **데이터** > **보강** 으로 이동합니다.

1. **발견** 탭으로 이동하여 **계정 참여** 타일에서 **내 데이터 보강** 을 선택합니다.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="계정 참여 타일":::
   
1. **개요** 단계에서 **다음** 을 선택하고 Office 데이터를 집계할 조직의 이메일 주소를 입력합니다. 나열된 이메일 주소의 데이터만 관련 통신을 위해 처리됩니다. 모범 사례는 이메일 그룹을 사용하는 것입니다. 예를 들면, Office 365에서 쉽게 관리할 수 있도록 *미국 영업팀* 을 사용합니다. 그룹의 이메일 주소 수가 확인되어 표시됩니다. 이메일 주소의 총 개수는 2개 이상이어야 하며 2,500개를 초과할 수 없습니다.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="계정 참여 이메일 주소.":::

1. 동의서를 검토하고 **동의함** 확인란을 선택한 후 **다음** 을 선택합니다.

1. 고객 데이터 세트를 선택하고 **다음** 을 선택합니다.

1. 연락처 이메일 주소 필드를 매핑하고 **다음** 을 선택합니다.

1. 보강 구성을 검토하고 보강 이름을 지정한 다음 **보강 저장** 을 선택하여 보강을 저장합니다.

## <a name="office-365-tenant-administrator-consent"></a>Office 365 테넌트 관리자 동의

보강을 활성화하려면 Office 365 테넌트 관리자의 동의가 필요합니다. 보강이 저장되면 Office 365 테넌트 관리자에게 이메일이 전송되어 Dynamics 365 애플리케이션이 기업의 Office 365 데이터를 사용하여 **조직에 대한 인사이트** 를 제공한다는 내용을 검토하고 동의하도록 요청합니다. Office 365 테넌트 관리자는 Office 365 관리 콘솔에서 **조직에 대한 인사이트** 를 선택하여 직접 동의할 수도 있습니다.

## <a name="running-the-enrichment-for-the-first-time"></a>처음으로 보강 실행

보강이 처음 시작되면 Office 365 테넌트 관리자가 동의한 후에 Office 365에서 데이터 다운로드가 시작됩니다. 이 프로세스에는 다소 시간이 걸릴 수 있습니다. 첫 번째 보강 실행은 6시간 지연될 예정입니다. 보강이 완료된 후 계정 참여 개요 페이지에서 데이터가 포함된 일 수를 확인할 수 있습니다. 데이터 볼륨이 큰 경우 며칠 후에 다시 보강을 실행합니다. 1년이라는 전체 기간 동안 데이터가 완전함을 보장합니다.

프로세스를 시작하려면 계정 참여 구성 페이지에서 **실행** 을 선택하세요. 또한 [예약된 새로 고침](system.md#schedule-tab)의 일부로 시스템에서 자동으로 보강 기능을 실행하도록 할 수 있습니다. 기본적으로 보강은 일주일에 한 번 실행됩니다.

Office 데이터의 크기에 따라 보강 실행을 완료하는 데 몇 시간이 걸릴 수 있습니다.

보강을 실행하면 Microsoft는 Office 365 규정 준수 경계에서 데이터를 처리하여 집계된 통찰력을 생성하며 이것이 Customer Insights 환경에 추가됩니다. Customer Insights 사용자는 개별 수준의 데이터(예: 이메일 또는 일정 초대의 본문)를 사용할 수 없습니다. 

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>보강 결과

보강 프로세스를 실행한 후 **내 보강** 으로 이동하여 보강 결과를 검토합니다. 강화된 고객의 총 수와 강화 결과의 개요를 확인할 수 있습니다. 여기에는 처리된 이메일 및 회의 수, 데이터가 집계된 일수 등이 포함됩니다.

시간 경과에 따라 보강된 고객 수와 보강된 데이터의 미리 보기가 포함된 차트도 찾을 수 있습니다.  

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="보강 프로세스를 실행한 후 결과 미리 보기.":::

모든 데이터는 계정 수준까지 집계됩니다. 시스템은 모든 계정에 대해 0에서 100 사이의 참여 점수를 계산합니다. 참여 점수는 다른 계정과 관련하여 이메일 및 회의 전반의 계정 참여에 대한 종합 측정값을 제공합니다. 다음 목록에는 계정 참여 보강이 제공하는 집계 데이터가 포함되어 있습니다.



| 데이터                                                                              | 열 이름                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| 참여 점수                                                                  |  EngagementScore                         |
| 계정에 보낼 이메일 수                                                       |  NoOfEmails_ToAccount                    |
| 계정에서 보낼 이메일 수                                                     |  NoOfEmails_FromAccount                  | 
| 계정에서 시작된 모임 수입니다.                                           |  NoOfMeetings_FromAccount                | 
| 조직에서 시작된 모임 수입니다.                                 |  NoOfMeetings_ToAccount                  | 
| 계정이 있는 회의에 있는 조직의 사람 수                  |  NoOfContactsInvolved_Meetings           | 
| 계정이 있는 이메일 대화에 있는 조직의 사람 수       |  NoOfContactsInvolved_Emails             | 
| 조직과 회의에 참여하는 계정의 사람 수                  |  NoOfAccountContactsInvolved_Meetings    | 
| 조긱과의 이메일 대화에 있는 계정의 사람 수       |  NoOfAccountContactsInvolved_Emails      | 
| 참여 시작 날짜(데이터의 첫 번째 이메일 또는 회의)                        |  EngagementStartDate                     | 
| 마지막 이메일 이후 일 수                                                             |  DaysSinceLastEmail                      | 
| 마지막 모임 이후 일 수                                                           |  DaysSinceLastMeeting                    | 
| 평균 회의 시간                                                      |  AverageDuration_Of_Meetings             | 
| 계정의 평균 이메일 회신 기간                                    |  AverageDuration_Of_AccountEmailReplies  | 
| 집계 시작 날짜                                                            |  AggregationStartDate                    | 
| 집계 수준(연, 월, 주)                                          |  AggregationLevel                        | 


프리뷰 섹션에서 **더 보기** 를 선택하여 보강된 데이터를 검토합니다. *사무실* 엔터티가 열립니다. **데이터** > **엔터티** 의 **보강** 그룹에서 나열된 엔터티를 찾을 수도 있습니다. 또한 보강 구성 중에 선택한 이메일 주소에 대한 Active Directory ID가 포함된 *Office_UserEntity* 도 찾을 수 있습니다. 

## <a name="see-enrichment-data-on-the-customer-card"></a>고객 카드의 보강 데이터 보기

계정 참여는 개별 고객 카드에서도 볼 수 있습니다. **고객** 으로 이동하여 고객 프로필을 선택하십시오. 고객 카드에서 계정의 참여 점수, 총 이메일 수, 작년에 집계된 총 회의 수를 확인할 수 있습니다. 이메일 및 회의 기록을 보여주는 차트도 있습니다.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="보강된 데이터가 포함된 고객 카드.":::

## <a name="create-segments-and-measures-based-on-the-enriched-data"></a>풍부한 데이터를 기반으로 세그먼트 및 측정값 생성

강화된 데이터를 사용하여 아래에 자세히 설명된 대로 세그먼트 및 측정값을 생성할 수 있습니다. 예를 들어 *마지막 이메일 이후 일수* 와 *마지막 회의 이후 일수* 값이 60을 초과하는 모든 고객이 포함된 세그먼트 해당 세그먼트에는 재활성화를 시도할 수 있는 오래된 계정이 포함되어 있습니다. 

## <a name="next-steps"></a>다음 단계

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
