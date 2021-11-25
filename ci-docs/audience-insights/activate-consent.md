---
title: 세그먼트에 대한 동의 규칙 활성화
description: 다음 단계에 따라 대상 그룹 인사이트에서 동의 데이터를 연결하고 동의 확인을 활성화합니다. 관리자는 동의 확인을 사용 중지할 수도 있습니다.
ms.date: 11/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 45899738d39bd5caa433e123f9fe59020e831998
ms.sourcegitcommit: 79b09498d1328e5551fb8684c44af1fb149f9881
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2021
ms.locfileid: "7790784"
---
# <a name="activate-consent-rules"></a>동의 규칙 활성화

[동의 센터(미리 보기)](../consent-management/overview.md)는 다양한 소스의 동의 데이터를 결합시키는 데 도움이 됩니다. 통합된 *동의* 엔터티를 사용하여 기본 동의 확인을 적용합니다. 동의 센터에서 동의 데이터를 가져오고 데이터에 대한 규칙을 구성하면 *동의* 엔터티가 대상 그룹 인사이트에 자동으로 동기화됩니다.

## <a name="enable-consent-checks"></a>동의 확인 사용

동의 센터(프리뷰)로 가져온 동의 데이터와 규칙이 설정되면 동의 확인을 사용할 수 있습니다. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="활성화된 동의 데이터가 있는 대상 그룹 인사이트 설정의 동의 탭.":::

1. 대상 그룹 인사이트에서 **데이터** > **시스템** 으로 이동합니다.

1. **동의(프리뷰)** 탭을 선택합니다.

1. **동의 확인 사용** 섹션에서 사용하려는 영역의 토글을 **켜기** 로 설정합니다.

1. 특정 세그먼트에 적용되는 기본 동의 확인을 제거하려면 **기본 동의 규칙의 재정의 허용** 확인란을 선택합니다. 

1. 드롭다운 메뉴에서 재정의를 허용할 위치를 선택합니다.     

1. **고객 프로필에 동의 연결** 섹션에서 동의 데이터를 고객 데이터에 연결하기 위한 식별자로 사용되는 속성을 선택합니다. 전화번호나 이메일 주소일 가능성이 큽니다. 

1. **저장** 을 선택하여 설정을 적용합니다.

## <a name="disable-consent-checks"></a>동의 확인 사용 중지

대상 그룹 인사이트에서 동의 데이터 사용을 중지하려면 관리자가 그에 따라 시스템 설정을 업데이트해야 합니다.

1. 대상 그룹 인사이트에서 **데이터** > **시스템** 으로 이동합니다.

1. **동의(프리뷰)** 탭을 선택합니다.

1. **동의 확인 사용** 섹션에서 토글을 **끄기** 로 설정합니다.
