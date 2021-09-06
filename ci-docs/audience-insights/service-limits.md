---
title: 서비스 한도
description: 한도 및 제한 사항을 이해합니다.
ms.date: 07/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2966f2ede1ddbe0245471771365cbf5b593be608764aa10ed28d962c52bb8067
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034872"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Dynamics 365 Customer Insights 대상 그룹 인사이트 기능의 서비스 한도

이 문서에서는 서비스의 신뢰성과 안정성을 보장하기 위해 고안된 Customer Insights 서비스의 기본 제한 사항에 대해 설명합니다. [아이디어 포럼](https://go.microsoft.com/fwlink/?linkid=2074172)에서 변경 요청을 할 수 있습니다. 
 
| 영역  | 제한  | 참고 |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| 세그먼트 및 측정값 | 100개의 세그먼트 또는 측정값입니다. | 활성 [세그먼트](segments.md)와 [측정값](measures.md)은 합쳐서 총 개수가 100개를 초과할 수 없습니다.  |
| 관계 | 엔티티 경로의 관계에 대한 20가지 수준의 깊이. | 빌더 인터페이스를 사용하여 [세그먼트](segments.md) 또는 [측정](measures.md)를 생성할 때 엔터티 경로는 시작 엔터티와 대상 엔터티 간에 최대 20개의 관계 홉을 가질 수 있습니다.  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]