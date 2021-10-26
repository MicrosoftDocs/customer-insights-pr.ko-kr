---
title: 역할 및 권한
description: 작업 영역 구성원에 대해 사용 가능한 역할 및 권한에 대한 개요입니다.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 68e28caf1c14c23acd506da5f7b441f1e3b72e8b
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645545"
---
# <a name="roles-and-permissions"></a>역할 및 권한

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

작업 영역은 이벤트와 보고서를 저장하고 관리하는 위치입니다. 자세한 내용은 [작업 영역 만들기 및 구성원 추가](create-workspace.md)를 참조하세요. 

작업 영역에는 다음 역할 및 권한이 포함될 수 있습니다.

- *구성원* 역할은 작업 영역에 액세스할 수 있는 사용자입니다. 작업 영역에 구성원을 할당하고 역할과 권한을 정의할 수 있습니다. 
- *관리자* 역할은 작업 영역 및 환경을 관리하여 다른 사용자에 대한 참여 인사이트를 구성합니다. 
- *기여자* 역할은 참여 인사이트를 구성할 필요는 없지만 자체 보고서, 유입 경로 또는 세그먼트를 만들려는 분석가를 대상으로 합니다.

## <a name="permissions"></a>사용 권한
  
다음 테이블에는 각 역할에 대한 권한이 나와 있습니다. 

| 권한 | 환경 관리자 | 작업 영역 관리자 | 환경 기여자 | 작업 영역 기여자 | 
|--|--|--|--|--|
| 환경 만들기(생성자가 자동으로 환경 관리자가 됨) | X* | X* | X* | X* |  
| 환경 구성(환경 구성원, 환경 삭제) | X |  |  |  |  
| 작업 영역 만들기 | X |  |  |  |  
| 작업 영역 구성(작업 영역 구성원, 작업 영역 삭제) | X | X |  |  |  
| 이벤트 및 개선된 이벤트 구성 | X | X | |  |  
| 작업 영역 이벤트 및 개선된 이벤트보기 | X | X | |  |  
| 작업 영역 리소스(보고서, 세그먼트 및 메트릭) 보기| X | X | X | X |  
| 사용자 지정 보고서 및 유입 경로 만들기 | X | X | X | X |  
| 기준 메트릭 및 차원 만들기| X | X |  |  |  
| 세그먼트 만들기| X | X | X | X |  

*미리보기에서만 평가판 환경을 만들 수 있습니다. 

## <a name="add-members"></a>구성원 추가

작업 영역 및 환경에서 구성원을 추가 및 제거할 수 있습니다. 자세한 정보는 [환경 및 작업 영역](manage-environments-workspaces.md)을 참조하세요.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
