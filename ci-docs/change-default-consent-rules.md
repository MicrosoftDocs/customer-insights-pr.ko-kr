---
title: 세그먼트에 대한 기본 동의 규칙 관리
description: 동의 관리 기능을 사용하면 재정의가 사용 설정된 경우에 기본 동의 규칙을 사용 중지하거나 변경할 수 있습니다.
ms.date: 12/01/2021
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 764eeca9d99c95a34d9bd4c11d79f8b8e90701e2
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755224"
---
# <a name="disable-or-change-default-consent-rules"></a>기본 동의 규칙 사용 중지 또는 변경

조직에서 Dynamics 365 Customer Insights와 결합된 [동의 관리 기능](consent-management/overview.md)을 사용하는 경우 세그먼트에 대해 [관리자는 동의 규칙](activate-consent.md)을 적용할 수 있습니다. 

세그먼트 영역에서 시행된 동의 규칙을 통해 모든 세그먼트는 동의 확인 및 규칙의 상태를 알려줍니다. 재정의가 허용되면 특정 세그먼트에 대한 기본 동의 규칙이 해제됩니다. 세그먼트의 모든 작성자는 해당 세그먼트의 기본 규칙에 더 많은 동의 규칙을 추가할 수 있습니다. 

## <a name="for-administrators"></a>관리자용

:::image type="content" source="consent-management/media/consent-rules-segment.png" alt-text="동의 규칙 옵션이 있는 세그먼트 빌더.":::

**기본 동의 규칙을 비활성화하는 방법:**

1. **동의 규칙** 알림에서 **세부 정보 보기** 를 선택합니다. 

1. **기본 동의 규칙** 토글을 **끄기** 로 설정합니다.

**더 많은 동의 규칙을 추가하는 방법:**

1. **동의 규칙** 알림에서 **세부 정보 보기** 를 선택합니다. 

1. **동의 규칙 추가** 를 선택하고 **동의 데이터 유형 선택** 드롭다운에서 동의 규칙을 선택합니다.

1. **저장** 을 선택하여 세그먼트에 새 규칙을 적용합니다.

## <a name="for-contributors"></a>Contributor 대상

강제 동의 규칙 없이 세그먼트를 생성하려면 관리자와 협력하여 세그먼트에서 비활성화해야 합니다. 그러나 자신이 소유하고 관리하는 세그먼트에 고유한 동의 규칙을 추가할 수 있습니다.

3단계 프로세스입니다. 
1. Customer Insights에서 [세그먼트를 만들고](segments.md) 저장하십시오. 

1. 관리자와 세그먼트 이름을 공유하고 [세그먼트에 대한 재정의를 활성화](activate-consent.md)해달라고 요청합니다. 

1. 세그먼트를 다시 엽니다. **동의 규칙** 알림에서 **세부 정보 보기** 를 선택하고 적용하려는 동의 규칙을 추가합니다. 그 다음에 **저장** 하고 세그먼트를 **실행** 합니다.



[!INCLUDE [footer-include](includes/footer-banner.md)] 
