---
title: 통합 고객 프로필 보강
description: 기능을 사용하여 고객 데이터를 보강합니다.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: bc0128c222c032e8cfe35e6f3baa0ea722bce7cb
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673007"
---
# <a name="enrichment-for-customer-profiles-preview"></a>고객 프로필 보강(미리 보기)

Microsoft 및 기타 파트너와 같은 소스의 데이터를 사용하여 고객 데이터를 보강합니다.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="보강 허브 페이지.":::

대상 그룹 인사이트에서 **데이터** > **보강** 으로 이동하여 강화 옵션을 사용합니다.  

기능 보강을 작성하거나 편집하려면 기여자 또는 관리자 권한이 있어야 합니다. 자세한 내용은 [권한](permissions.md)을 참조하십시오.

**검색** 탭에서 지원되는 모든 보강 옵션을 찾을 수 있습니다.

# <a name="individual-consumers-b-to-c"></a>[개별 소비자(B2C)](#tab/b2c)

- Microsoft에서 제공한 [브랜드](enrichment-microsoft.md)
- Microsoft에서 제공한 [관심사](enrichment-microsoft.md)
- Microsoft 제공 [향상된 주소](enrichment-enhanced-addresses.md) 
- [Experian에서 제공하는 인구 통계](enrichment-experian.md)
- SFTP(보안 파일 전송 프로토콜)를 통한 [사용자 지정 데이터](enrichment-SFTP-custom-import.md) 
- Microsoft 제공 [Azure Maps](enrichment-azure-maps.md)

# <a name="business-accounts-b-to-b"></a>[비즈니스 어카운트(B2B)](#tab/b2b)

- Leadspace에서 제공한 [회사 데이터](enrichment-leadspace.md)
- Microsoft 제공 [향상된 주소](enrichment-enhanced-addresses.md) 
- HERE Technologies에서 제공한 [위치 데이터](enrichment-here.md) 
- SFTP(보안 파일 전송 프로토콜)를 통한 [사용자 지정 데이터](enrichment-SFTP-custom-import.md) 
- Microsoft 제공 [Azure Maps](enrichment-azure-maps.md)

---

**내 보강** 탭에서 구성한 보강을 보고 속성을 편집할 수 있습니다.

## <a name="manage-existing-enrichments"></a>기존 보강 관리

**내 보강** 탭으로 이동하여 구성된 모든 보강을 확인하십시오. 각 보강은 보강에 대한 추가 정보를 포함하는 행으로 표시됩니다.

사용 가능한 옵션을 보려면 보강을 선택하십시오. 목록 항목에서 줄임표(...)를 선택하여 옵션을 볼 수도 있습니다. 여러 보강을 구성한 경우 검색 상자를 사용하여 빠르게 찾을 수 있습니다.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="보강 목록에서 보강을 관리하는 옵션.":::

- 고객 프로필의 수가 보강된 강화 세부 사항 **보기**.
- 강화 구성 **편집**.
- **운영** 최신 데이터로 고객 프로필 업데이트 강화
- 예약된 새로 고침마다 자동으로 새로 고쳐지지 않도록 기존 보강을 **비활성화**. 마지막으로 성공한 새로 고침의 데이터는 계속 사용할 수 있습니다. 예약된 새로 고침마다 자동 새로 고침을 다시 시작하도록 비활성 보강을 **활성화**.
- 보강을 **삭제** 합니다.

목록에서 여러 강화를 선택하여 한 번에 실행하거나 비활성화합니다. 보기 및 수정 옵션은 일괄 작업으로 사용할 수 없습니다. 한 번에 하나의 보강에 대해서만 작동합니다.

## <a name="enrichments-and-connections"></a>보강 및 연결

타사 보강은 관리자가 자격 증명으로 설정하고 데이터 전송에 대한 동의를 제공하는 [연결](connections.md)을 사용하여 구성됩니다. 관리자와 기여자는 연결을 사용하여 보강을 구성할 수 있습니다.  

## <a name="multiple-enrichments-of-the-same-type"></a>동일한 유형의 여러 보강

보강할 엔터티는 보강 구성 중에 지정되므로 프로필의 하위 집합만 보강할 수 있습니다. 예를 들어 특정 세그먼트에 대해서만 데이터를 보강합니다. 동일한 유형의 여러 보강을 구성하고 동일한 연결을 재사용할 수 있습니다. 일부 보강에는 만들 수 있는 동일한 유형의 보강 수에 제한이 있습니다. 제한과 현재 사용은 **보강** 페이지에서 확인할 수 있습니다.

## <a name="see-the-progress-of-the-enrichment-process"></a>보강 프로세스의 진행 상황 보기

새로 고치는 동안 또는 새로 고침이 완료된 후 상태 및 잠재적 문제를 포함하여 보강 처리에 대한 세부 정보를 찾을 수 있습니다. 보강을 새로 고치는 데 관련된 프로세스와 프로세스를 실행하는 데 걸린 시간을 이해합니다. 보강 상태는 Experian, Leadspace, HERE Technologies, SFTP Import 및 Azure Maps에 대해 지원됩니다.

보강 상태를 보는 방법

1. **데이터** > **보강** 으로 이동합니다. 
1. **내 보강** 탭에서 보강 상태를 선택하여 측면 창을 엽니다. 
1. **진행 세부 정보** 창에서 **보강** 섹션을 확장합니다. 
1. 진행 상황을 확인하려는 보강 아래에서 **세부 정보 보기** 를 선택합니다. 
1. **작업 세부 정보** 창에서 **세부 정보 표시** 를 선택하여 보강 및 해당 상태 업데이트와 관련된 프로세스를 확인합니다. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
