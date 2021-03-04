---
title: Customer Insights 데이터를 SFTP 호스트로 내보냅니다.
description: SFTP 호스트에 대한 연결을 구성하는 방법 알아보기.
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268006"
---
# <a name="connector-for-sftp-preview"></a>SFTP용 커넥터(미리 보기)

고객 데이터를 SFTP(보안 파일 전송 프로토콜) 호스트로 내보내 타사 애플리케이션에서 사용합니다.

## <a name="prerequisites"></a>필요한 항목

- SFTP 호스트 및 해당 자격 증명의 가용성.

## <a name="connect-to-sftp"></a>SFTP에 연결

1. **관리자** > **내보내기 대상** 으로 이동합니다.

1. **SFTP** 아래에서 **설정** 을 선택합니다.

1. **표시 이름** 필드에서 대상에 인식할 수 있는 이름을 지정합니다.

1. **사용자 이름**, **암호**, **호스트 이름** 및 **내보내기 폴더** 를 제공합니다.

1. **확인** 을 선택해 연결을 테스트합니다.

1. 성공적으로 확인한 후 데이터를 **압축** 또는 **압축 해제** 하여 내보낼지 선택하고 내보낸 파일에 대한 **필드 구분자** 를 선택합니다.

1. **동의** 를 선택해 **데이터 프라이버시 및 규정 준수** 를 확인합니다.

1. **다음** 을 선택해 내보내기 구성을 시작합니다.

## <a name="configure-the-export"></a>내보내기 구성

1. 내보내려는 엔터티(예: 세그먼트)를 선택합니다.

   > [!NOTE]
   > 선택한 각 엔터티는 내보낼 때 최대 5개의 출력 파일이 됩니다. 

1. **저장** 을 선택합니다.

## <a name="export-the-data"></a>데이터 내보내기

[주문 시 데이터를 내보낼](export-destinations.md) 수 있습니다. 내보내기는 [예약된 새로 고침](system.md#schedule-tab)마다 실행됩니다.

## <a name="known-limitations"></a>알려진 제한 사항

- 내보내기 런타임은 시스템 성능에 따라 다릅니다. 서버의 최소 구성으로 2개의 CPU 코어와 1Gb의 메모리를 권장합니다. 
- 2개의 CPU 코어와 1Gb 메모리의 권장 최소 구성을 사용하면 최대 1억 개의 고객 프로필이 있는 엔터티를 내보내는 데 90분이 걸릴 수 있습니다. 

## <a name="data-privacy-and-compliance"></a>데이터 프라이버시 및 규정 준수

Dynamics 365 Customer Insights를 사용하여 SFTP를 통해 데이터를 전송하는 경우 Dynamics 365 Customer Insights규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다. Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 내보내기 대상이 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다. 자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.
Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]