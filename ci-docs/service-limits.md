---
title: Customer Insights의 서비스 제한
description: Customer Insights SaaS 서비스의 제한 사항을 이해합니다.
ms.date: 05/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6d1b761a5c9f67bfdc7c5b152132c618db3ea36a
ms.sourcegitcommit: 78ef22cd39a1ebd7525f96829cd79d95f34438b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/07/2022
ms.locfileid: "8940676"
---
# <a name="service-limits-in-customer-insights"></a>Customer Insights의 서비스 제한

이 문서에서는 서비스의 신뢰성과 안정성을 보장하기 위해 고안된 Customer Insights 서비스의 기본 제한 사항에 대해 설명합니다. [아이디어 포럼](https://go.microsoft.com/fwlink/?linkid=2074172)에서 변경 요청을 할 수 있습니다.

## <a name="customer-insights"></a>Customer Insights

| 지역  | 제한  | 노트 |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| 세그먼트, 측정값 및 예측 | 300  | 결합된 [세그먼트](segments.md), [측정값](measures.md) 및 [예측](predictions.md)의 총 수는 300을 초과할 수 없습니다.  |
| 관계 | 엔티티 경로의 관계에 대한 20가지 수준의 깊이. | 빌더 인터페이스를 사용하여 [세그먼트](segments.md) 또는 [측정](measures.md)를 생성할 때 엔터티 경로는 시작 엔터티와 대상 엔터티 간에 최대 20개의 관계 홉을 가질 수 있습니다.  |

## <a name="fair-scheduling-of-jobs"></a>공정한 작업 일정

Customer Insights는 공유 Azure 리소스를 사용하는 SaaS 서비스입니다. 고객은 강도가 다양하고 일정이 다른 워크로드를 사용하는 경향이 있습니다. 기본 리소스에 대한 공정한 액세스를 보장하기 위해 시스템 프로세스가 공정한 순서로 실행되도록 합니다. 시스템 프로세스의 예로는 데이터 통합, 세그먼트 업데이트 또는 측정값 계산과 관련된 작업이 있습니다. 공정한 일정은 요청된 작업이 급증하는 경우 리소스를 대기열에 넣지 않도록 보호합니다. 동시에 Customer Insights는 대기열에 있는 모든 작업이 병렬로 처리되는 것을 보장하지 않습니다.

[!INCLUDE [footer-include](includes/footer-banner.md)]
