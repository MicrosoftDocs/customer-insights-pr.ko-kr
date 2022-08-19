---
title: 데이터 보강(프리뷰) 개요
description: Microsoft 및 기타 타사 서비스의 기능을 사용하여 고객 데이터를 강화하세요.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 0c2a900190b4ab6e93098d05a2fd66bcd2b847fd
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245887"
---
# <a name="data-enrichment-preview-overview"></a>데이터 보강(프리뷰) 개요

Microsoft 및 기타 파트너와 같은 소스의 데이터를 사용하여 고객 데이터를 보강합니다. 타사 보강은 관리자가 자격 증명으로 설정하고 데이터 전송에 대한 동의를 제공하는 [연결](connections.md)을 사용하여 구성됩니다. 관리자와 기여자는 연결을 사용하여 보강을 구성할 수 있습니다.  

## <a name="multiple-enrichments-of-the-same-type"></a>동일한 유형의 여러 보강

보강할 엔터티는 보강 구성 중에 지정되므로 프로필의 하위 집합만 보강할 수 있습니다. 예를 들어 특정 세그먼트에 대해서만 데이터를 보강합니다. 동일한 유형의 여러 보강을 구성하고 동일한 연결을 재사용할 수 있습니다. 일부 보강에는 만들 수 있는 동일한 유형의 보강 수에 제한이 있습니다. **보강** 페이지의 **발견** 탭에서 각 타일에 대한 제한 및 현재 사용을 볼 수 있습니다.

## <a name="enrich-data-sources-before-unification"></a>통합 전 데이터 원본 보강

데이터 통합 전에 고객 데이터를 보강하여 데이터 일치의 품질을 높일 수 있습니다. 자세한 내용은 [데이터 원본 보강](data-sources-enrichment.md)을 참조하세요.

## <a name="create-an-enrichment"></a>보강 만들기

보강을 만들거나 편집하려면 기여자 또는 관리자 [권한](permissions.md)이 있어야 합니다.

**데이터** > **보강** 으로 이동합니다. **검색** 탭에는 지원되는 모든 보강 옵션이 표시됩니다.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="보강 허브 페이지.":::

# <a name="individual-consumers-b-to-c"></a>[개별 소비자(B2C)](#tab/b2c)

- LiveRamp AbiliTec 제공 [AbiliTec ID](enrichment-liveramp.md)
- Microsoft에서 제공한 [브랜드](enrichment-microsoft.md)
- [Experian에서 제공하는 인구 통계](enrichment-experian.md)
- Microsoft 제공 [향상된 주소](enrichment-enhanced-addresses.md)
- Microsoft에서 제공한 [관심사](enrichment-microsoft.md)
- Microsoft Azure 지도에서 제공하는 [위치 데이터](enrichment-azure-maps.md)
- HERE Technologies에서 제공한 [위치 데이터](enrichment-here.md)
- SFTP(보안 파일 전송 프로토콜)를 통한 [SFTP 사용자 지정 데이터](enrichment-SFTP-custom-import.md)

# <a name="business-accounts-b-to-b"></a>[비즈니스 어카운트(B2B)](#tab/b2b)

- Microsoft에서 제공한 [계정 참여 데이터](enrichment-office.md)
- Dun & Bradstreet 제공 [회사 데이터](enrichment-dnb.md)
- Leadspace에서 제공한 [회사 데이터](enrichment-leadspace.md)
- Microsoft 제공 [향상된 주소](enrichment-enhanced-addresses.md)
- Microsoft에서 제공한 [개선된 회사 데이터](enrichment-enhanced-company-data.md)
- Microsoft Azure 지도에서 제공하는 [위치 데이터](enrichment-azure-maps.md)
- HERE Technologies에서 제공한 [위치 데이터](enrichment-here.md)
- SFTP(보안 파일 전송 프로토콜)를 통한 [SFTP 사용자 지정 데이터](enrichment-SFTP-custom-import.md)

---

## <a name="manage-existing-enrichments"></a>기존 보강 관리

**데이터** > **보강** 으로 이동합니다. **내 보강** 탭에서 구성된 보강, 해당 상태, 보강 고객 수 및 데이터를 마지막으로 새로 고친 시간을 확인합니다. 열을 기준으로 보강 목록을 정렬하거나 검색 상자를 사용하여 관리하려는 보강을 찾을 수 있습니다.

사용 가능한 작업을 보려면 보강을 선택합니다.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="보강 목록에서 보강을 관리하는 옵션.":::

- 고객 프로필의 수가 보강된 강화 세부 사항 **보기**.
- 강화 구성 **편집**.
- 보강을 [**실행**](#run-or-refresh-enrichments)하여 최신 데이터로 고객 프로필을 업데이트합니다. 목록에서 선택하여 한 번에 여러 보강을 실행합니다.
- 보강을 **활성화** 또는 **비활성화** 합니다. 비활성 보강은 [예약된 새로 고침](schedule-refresh.md) 중에 새로 고쳐지지 않습니다.
- 보강을 **삭제** 합니다.

보강에서 [세그먼트](segments.md) 또는 [측정값](measures.md)을 생성할 수도 있습니다.

## <a name="run-or-refresh-enrichments"></a>보강 실행 또는 새로 고침

보강을 실행하면 자동 일정에 따라 새로 고치거나 요청 시 수동으로 새로 고칠 수 있습니다.

1. 하나 이상의 보강을 수동으로 새로 고치려면 선택하고 **실행** 을 선택합니다. [자동 새로 고침을 예약](schedule-refresh.md)하려면 **관리** > **시스템** > **예약** 으로 이동합니다. 처리 시간은 고객 데이터의 크기에 따라 다릅니다.

1. 선택적으로 [보강 프로세스의 진행 상황을 확인합니다](#see-the-progress-of-the-enrichment-process).

1. 보강 프로세스가 완료되면 **내 보강** 으로 이동하여 새로 보강된 고객 프로필 데이터, 마지막 업데이트 시간 및 보강된 프로필 수를 검토합니다.

1. [보강 결과](#view-enrichment-results)를 보려면 보강을 선택하세요.

### <a name="see-the-progress-of-the-enrichment-process"></a>보강 프로세스의 진행 상황 보기

새로 고치는 동안 또는 새로 고침이 완료된 후 상태 및 잠재적 문제를 포함하여 보강 처리에 대한 세부 정보를 찾을 수 있습니다. 보강을 새로 고치는 데 관련된 프로세스와 프로세스를 실행하는 데 걸린 시간을 이해합니다. 보강 상태는 Experian, Leadspace, HERE Technologies, SFTP Import 및 Azure Maps에 대해 지원됩니다.

1. **데이터** > **보강** 으로 이동합니다.
1. **내 보강** 탭에서 보강 상태를 선택하여 측면 창을 엽니다.
1. **진행 세부 정보** 창에서 **보강** 섹션을 확장합니다.
1. 진행 상황을 확인하려는 보강 아래에서 **세부 정보 보기** 를 선택합니다.
1. **작업 세부 정보** 창에서 **세부 정보 표시** 를 선택하여 보강 및 해당 상태 업데이트와 관련된 프로세스를 확인합니다.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="view-enrichment-results"></a>강화 결과 보기

보강 실행을 완료한 후 보강 결과를 검토합니다.

1. **데이터** > **보강** 으로 이동합니다.
1. **내 보강** 탭에서 보려는 보강을 선택합니다.

모든 보강은 보강 프로필 수 및 시간 경과에 따른 보강 프로필 수와 같은 기본 정보를 표시합니다. **보강된 고객 프리뷰** 타일은 생성된 보강 엔터티의 샘플을 보여줍니다. 자세히 알아보려면 **더 보기** 를 선택하고 **데이터** 탭을 선택합니다.

:::image type="content" source="media/enrichments-results.png" alt-text="보강 결과 페이지.":::

사용 가능한 경우 **필드로 보강된 고객 수** 는 각 보강된 필드의 적용 범위에 대한 드릴다운을 제공합니다.

일부 보강은 또한 보강 유형과 관련된 정보를 표시합니다. 자세한 내용은 관련 설명서를 참조하세요.

[!INCLUDE [footer-include](includes/footer-banner.md)]
