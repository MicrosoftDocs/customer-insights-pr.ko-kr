---
title: Dynamics 365 Customer Insights의 서비스 한도
description: 한도 및 제한 사항을 이해합니다.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eb25e050b8aa768e6e1d8d4c5adce6095cccc346
ms.sourcegitcommit: 31a9b531dacd3a6465b3030c704ff5c085b7e122
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2021
ms.locfileid: "7791989"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Customer Insights 기능의 서비스 제한

이 문서에서는 서비스의 신뢰성과 안정성을 보장하기 위해 고안된 Customer Insights 서비스의 기본 제한 사항에 대해 설명합니다. [아이디어 포럼](https://go.microsoft.com/fwlink/?linkid=2074172)에서 변경 요청을 할 수 있습니다. 

## <a name="audience-insights"></a>대상 그룹 인사이트

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Dynamics 365 Customer Insights 대상 그룹 인사이트 기능의 서비스 한도

| 지역  | 제한  | 노트 |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| 세그먼트, 측정값 및 예측 | 300  | 결합된 [세그먼트](audience-insights/segments.md), [측정값](audience-insights/measures.md) 및 [예측](audience-insights/predictions.md)의 총 수는 300을 초과할 수 없습니다.  |
| 관계 | 엔티티 경로의 관계에 대한 20가지 수준의 깊이. | 빌더 인터페이스를 사용하여 [세그먼트](audience-insights/segments.md) 또는 [측정](audience-insights/measures.md)를 생성할 때 엔터티 경로는 시작 엔터티와 대상 엔터티 간에 최대 20개의 관계 홉을 가질 수 있습니다.  |


## <a name="engagement-insights"></a>참여 인사이트

### <a name="workspace-and-event-quotas"></a>작업 영역 및 이벤트 할당량

참여 인사이트는 초당 수백만 개의 이벤트를 지원할 수 있는 확장성이 뛰어난 애플리케이션입니다. 공개 프리뷰 중에 이벤트에는 볼륨 임계값이 있습니다. 조직의 작업 영역 수에도 제한이 있습니다.

### <a name="engagement-insights-limits"></a>참여 인사이트 한도

- 작업 영역당 최대 이벤트 볼륨 = 초당 이벤트 100개

- 조직당 최대 작업 영역 수 = 100개

이벤트가 임계값을 초과하면 해당 이벤트를 기반으로 하는 보고서의 데이터가 손실될 수 있습니다. 한도를 초과하기 전에 [지원팀에 문의](https://go.microsoft.com/fwlink/?linkid=2145734)하여 볼륨 증가를 요청할 수 있습니다. 볼륨 증가에 대한 필요성을 확인하고 요청을 지원하기 위해 협력할 것입니다.


[!INCLUDE[footer-include](includes/footer-banner.md)]
