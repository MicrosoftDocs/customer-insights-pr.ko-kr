---
title: 통합 고객 프로필 보강
description: 기능을 사용하여 고객 데이터를 보강합니다.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 6b73aa93ec1a98f2b8d20d02e88bc6304f887078
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269476"
---
# <a name="enrichment-for-customer-profiles-preview"></a>고객 프로필 보강(미리 보기)

Microsoft 및 기타 파트너와 같은 소스의 데이터를 사용하여 고객 데이터를 보강합니다.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="보강 허브 페이지":::

대상 그룹 인사이트에서 **데이터** > **보강** 으로 이동하여 강화 옵션을 사용합니다.    
기능 보강을 작성하거나 편집하려면 기여자 또는 관리자 권한이 있어야 합니다. 자세한 내용은 [권한](permissions.md)을 참조하십시오.

**검색** 탭에서 다음과 같은 기능이 보강됩니다.

- Microsoft Graph에서 제공하는 [브랜드](enrichment-microsoft-graph.md)
- Microsoft Graph에서 제공하는 [관심사](enrichment-microsoft-graph.md).
- Leadspace에서 제공한 [회사 데이터](enrichment-leadspace.md)
- Experian에서 제공한 [인구 통계 자료](enrichment-experian.md)
- HERE Technologies에서 제공한 [위치 데이터](enrichment-here.md)
- SFTP(보안 파일 전송 프로토콜)를 통한 [사용자 지정 데이터](enrichment-SFTP-custom-import.md)

**내 보강** 탭에서 구성한 보강을 보고 속성을 편집할 수 있습니다.

## <a name="manage-existing-enrichments"></a>기존 보강 관리

구성된 모든 보강을 보려면 **내 보강** 으로 이동합니다. 각 보강은 보강에 대한 추가 정보를 포함하는 행으로 표시됩니다.

사용 가능한 옵션을 보려면 보강을 선택하십시오. 또는 목록 항목에서 줄임표(...)를 선택하여 옵션을 볼 수 있습니다.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="보강 목록에서 보강을 관리하는 옵션":::

- 고객 프로필의 수가 보강된 강화 세부 사항 **보기**.
- 강화 구성 **편집**.
- **운영** 최신 데이터로 고객 프로필 업데이트 강화
- 예약된 새로 고침마다 자동으로 새로 고쳐지지 않도록 기존 보강을 **비활성화**. 마지막으로 성공한 새로 고침의 데이터는 계속 사용할 수 있습니다. 예약된 새로 고침마다 자동 새로 고침을 다시 시작하도록 비활성 보강을 **활성화**.
- 보강을 **삭제** 합니다.

목록에서 여러 가지 보강을 선택하여 한 번에 실행하거나 비활성화할 수 있습니다. 보기 및 편집 옵션은 일괄 작업으로 사용할 수 없으며 한 번에 하나의 보강에 대해서만 작동합니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]