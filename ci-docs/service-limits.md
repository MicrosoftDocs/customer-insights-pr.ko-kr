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
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350415"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Customer Insights 기능의 서비스 제한

이 문서에서는 서비스의 신뢰성과 안정성을 보장하기 위해 고안된 Customer Insights 서비스의 기본 제한 사항에 대해 설명합니다. [아이디어 포럼](https://go.microsoft.com/fwlink/?linkid=2074172)에서 변경 요청을 할 수 있습니다. 

## <a name="audience-insights"></a>대상 그룹 인사이트

| 지역  | 제한  | 노트 |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| 세그먼트, 측정값 및 예측 | 300  | 결합된 [세그먼트](audience-insights/segments.md), [측정값](audience-insights/measures.md) 및 [예측](audience-insights/predictions.md)의 총 수는 300을 초과할 수 없습니다.  |
| 관계 | 엔티티 경로의 관계에 대한 20가지 수준의 깊이. | 빌더 인터페이스를 사용하여 [세그먼트](audience-insights/segments.md) 또는 [측정](audience-insights/measures.md)를 생성할 때 엔터티 경로는 시작 엔터티와 대상 엔터티 간에 최대 20개의 관계 홉을 가질 수 있습니다.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
