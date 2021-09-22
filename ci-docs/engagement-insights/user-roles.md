---
title: 역할 및 권한
description: 작업 영역 구성원에 대해 사용 가능한 역할 및 권한에 대한 개요입니다.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 07/06/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6d7f4db4a130fc15a69b380c892538db5492d96d8e13f3c070c6a6b9bd098371
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036701"
---
# <a name="roles-and-permissions"></a>역할 및 권한

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

작업 영역은 이벤트와 보고서를 저장하고 관리하는 방법입니다. 구성원은 작업 영역에 액세스할 수 있는 사용자입니다. 작업 영역에 구성원을 할당하고 역할과 권한을 정의할 수 있습니다. 관리자 역할은 작업 영역 및 환경을 관리하여 다른 사용자에 대한 참여 인사이트를 구성합니다. 기여자 역할은 참여 인사이트를 구성할 필요는 없지만 자체 보고서, 유입 경로 또는 세그먼트를 생성하려는 분석가를 대상으로 합니다.

## <a name="permissions"></a>사용 권한
  
다음 차트는 각 역할에 대한 권한을 식별합니다. 

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
