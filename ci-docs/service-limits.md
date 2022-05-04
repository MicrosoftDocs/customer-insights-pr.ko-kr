---
title: Dynamics 365 Customer Insights의 서비스 한도
description: 한도 및 제한 사항을 이해합니다.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641770"
---
# <a name="service-limits-in-customer-insights"></a>Customer Insights의 서비스 제한

이 문서에서는 서비스의 신뢰성과 안정성을 보장하기 위해 고안된 Customer Insights 서비스의 기본 제한 사항에 대해 설명합니다. [아이디어 포럼](https://go.microsoft.com/fwlink/?linkid=2074172)에서 변경 요청을 할 수 있습니다. 

## <a name="customer-insights"></a>Customer Insights

| 지역  | 제한  | 노트 |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| 세그먼트, 측정값 및 예측 | 300  | 결합된 [세그먼트](segments.md), [측정값](measures.md) 및 [예측](predictions.md)의 총 수는 300을 초과할 수 없습니다.  |
| 관계 | 엔티티 경로의 관계에 대한 20가지 수준의 깊이. | 빌더 인터페이스를 사용하여 [세그먼트](segments.md) 또는 [측정](measures.md)를 생성할 때 엔터티 경로는 시작 엔터티와 대상 엔터티 간에 최대 20개의 관계 홉을 가질 수 있습니다.  |


[!INCLUDE [footer-include](includes/footer-banner.md)]
