---
title: 기본 프로필 보고서 사용
description: 성별, 연령 및 출신 국가 또는 지역별로 그룹화된 기본 프로필 보고서를 만드는 방법.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bf2ec67c9fb99918b87841d3c0b131934e31b58b
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486128"
---
# <a name="out-of-box-profile-reports"></a>기본 프로필 보고서

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

보고서는 사용자의 행동 방식을 이해하는 데 도움이 되는 데이터 시각화 모음입니다. Customer Insights 대상 그룹 인사이트에 연결하면 참여 인사이트에서 통합 고객 프로필에 대한 정보가 포함된 보고서를 표시할 수 있습니다. 이 보고서에는 성별, 연령 및 지리적 위치별로 그룹화된 프로필 수가 포함됩니다.

## <a name="prerequisites"></a>필수 조건

대상 인사이트 환경은 고객이 관리하는 Azure Data Lake Storage 계정에 데이터를 저장해야 합니다.

대상 그룹 인사이트 기능의 평가판 버전을 사용하거나 Customer Insights 관리되는 데이터 레이크의 환경을 사용하는 경우 [당사에 문의](https://go.microsoft.com/fwlink/?linkid=2145734)하여 지원을 받으세요.  


## <a name="enable-the-customer-profile-report"></a>고객 프로필 보고서 사용

환경 관리자는 [참여 인사이트와 대상 그룹 인사이트를 연결](integrate-audience-insights-engagement-insights.md)해야 합니다.

연결 세부 정보를 지정한 후 관리자는 조직의 다른 사용자에게 보고서를 볼 수 있는 액세스 권한을 부여할 수 있습니다. 연결을 설정하는 환경 관리자는 자동으로 보고서에 액세스할 수 있습니다. 

연결을 완료하면 왼쪽 탐색 창에서 **프로필** 기능을 사용할 수 있습니다. 

- **검색** > **프로필** 로 이동하여 보고서를 확인합니다.

**프로필** 보고서에는 연결된 고객 프로필의 성별, 나이 및 지리적 위치에 대한 시각화가 포함됩니다.

:::image type="content" source="media/customer-profiles.png" alt-text="고객 프로필 보고서.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]