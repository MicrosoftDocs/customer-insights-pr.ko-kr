---
title: 내보내기 대상
description: 데이터를 내보내고 내보내기 대상을 관리합니다.
ms.date: 07/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5557442983f8c48cd46387009e0060beb6e764bb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596093"
---
# <a name="export-destinations-preview-overview"></a>내보내기 대상(미리 보기) 개요

**내보내기 대상** 페이지에는 데이터를 내보내도록 설정한 모든 위치가 표시됩니다. 내보낼 새 대상을 추가할 수도 있습니다. 또한 현재 사용 가능한 내보내기 옵션을 보여줍니다. 빠른 개요, 설명 및 각 확장성 옵션으로 수행 할 수 있는 작업을 알아보십시오. 비즈니스와 관련된 지원되는 앱으로 통합 프로필, 측정 값 및 세그먼트를 내보냅니다.

**관리자** > **내보내기 대상** 으로 이동하여 다음과 같은 확장성 옵션을 찾으십시오.

- [Adobe Campaign Standard](export-adobe-campaign-standard.md)
- [Adobe 환경 플랫폼](export-adobe-experience-platform.md)
- [AdRoll](export-adroll.md)
- [AutoPilot](export-autopilot.md)
- [Azure Blob Storage](export-azure-blob-storage.md)
- [Azure Data Lake Storage Gen2](export-azure-data-lake-storage-gen2.md)
- [Microsoft Teams용 봇](export-teams-bot.md)
- [Customer Insights API](apis.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Customer Service(고객 카드 추가 기능)](customer-card-add-in.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 영업 허브(고객 카드 추가 기능)](customer-card-add-in.md)
- [Facebook 광고 관리자](export-facebook.md)
- [Google 광고](export-google-ads.md)
- [LiveRamp&reg;](export-liveramp.md)
- [Mailchimp](export-mailchimp.md)
- [Marketo](export-marketo.md)
- [Power Automate](export-power-automate.md)
- [Power Apps](export-power-apps.md)
- [Power BI](export-power-bi.md)
- [SendGrid](export-sendgrid.md)
- [SFTP](export-sftp.md)

## <a name="add-a-new-export-destination"></a>새 내보내기 대상 추가

내보내기 대상을 추가하려면 [관리자 권한](permissions.md)이 있어야 합니다. Microsoft 서비스로 내보내는 경우 두 서비스가 모두 같은 조직에 있다고 가정합니다.

1. **관리자** > **내보내기 대상** 으로 이동합니다.

1. **내 내보내기 대상** 탭으로 전환합니다.

1. **내보내기 추가** 로 이동하여 새 내보내기 대상을 만듭니다.

1. **대상 추가** 창에서 드롭다운에서 내보내기 대상의 **유형** 을 선택합니다.

1. 필요한 세부 사항을 제공하고 **다음** 을 선택해 내보내기 대상을 만듭니다.

**검색** 탭의 타일에서 **설정** 을 선택할 수도 있습니다.

## <a name="view-export-destinations"></a>내보내기 대상 보기

내보내기 대상을 만든 후에는 **내 내보내기 대상** 탭의 테이블에서 찾을 수 있습니다. 이 테이블에는 세 개의 열이 있습니다.

- **표시 이름**: 대상을 만들 때 입력한 이름입니다.
- **유형**: 대상을 만들 때 설정한 내보내기 대상 유형입니다.
- **만든 날짜**: 대상을 만든 날짜입니다.

## <a name="edit-an-export-destination"></a>내보내기 대상 편집

1. 편집할 내보내기 대상의 세로 줄임표를 선택하십시오.

   > [!div class="mx-imgBorder"]
   > ![세로 줄임표](media/export-destinations-page-ellipsis.png "세로 줄임표")

1. 드롭다운 메뉴에서 **편집** 을 선택합니다.

1. 업데이트가 필요한 값을 변경하고 **저장** 을 선택합니다.

## <a name="export-data-on-demand"></a>주문 시 데이터 내보내기

내보내기 대상에 대한 커넥터를 구성한 후에는 내보내기가 [예정된 새로 고침](system.md#schedule-tab)으로 실행됩니다.

예약된 새로 고침을 기다리지 않고 데이터를 내보내려면 **관리자** > **내보내기 대상** 에서 **내 내보내기 목적** 탭으로 이동합니다.

> [!div class="mx-imgBorder"]
> ![세로 줄임표](media/export-destinations-page-ellipsis.png "세로 줄임표")

- 목록 위의 **내보내기** 를 선택해 모든 내보내기 대상으로 동시에 내보내기를 실행합니다.
- 목록 항목 뒤의 줄임표(...)를 선택한 다음 **내보내기** 옵션을 선택해 단일 내보내기 대상에 대해 내보내기를 실행합니다.

## <a name="remove-an-export-destination"></a>내보내기 대상 제거

내보내기 대상을 제거하려면 기본 **내보내기 대상** 페이지에서 시작하십시오.

1. 제거할 내보내기 대상의 세로 줄임표를 선택하십시오.

   > [!div class="mx-imgBorder"]
   > ![세로 줄임표](media/export-destinations-page-ellipsis.png "세로 줄임표")

2. 드롭다운 메뉴에서 **제거** 를 선택합니다.

3. 확인 화면에서 **제거** 를 선택하여 제거를 확인합니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]