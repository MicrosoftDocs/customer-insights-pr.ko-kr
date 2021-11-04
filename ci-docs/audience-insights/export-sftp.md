---
title: Customer Insights 데이터를 SFTP 호스트로 내보냅니다.
description: 연결을 구성하고 SFTP 위치로 내보내는 방법을 알아봅니다.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a54025588945e4db6ab800dca034520b5f08d49b
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673924"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a>SFTP로 세그먼트 및 다른 데이터 내보내기(프리뷰)

고객 데이터를 SFTP(Secure File Transfer Protocol) 위치로 내보내 타사 애플리케이션에서 사용하십시오.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites-for-connection"></a>연결을 위한 전제 조건

- SFTP 호스트 및 해당 자격 증명의 가용성.

## <a name="known-limitations"></a>알려진 제한 사항

- 내보내기 런타임은 시스템 성능에 따라 다릅니다. 서버의 최소 구성으로 2개의 CPU 코어와 1Gb의 메모리를 권장합니다. 
- 2개의 CPU 코어와 1Gb 메모리의 권장 최소 구성을 사용하면 최대 1억 개의 고객 프로필이 있는 엔터티를 내보내는 데 90분이 걸릴 수 있습니다. 

## <a name="set-up-connection-to-sftp"></a>SFTP 연결 설정

1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 와 **SFTP** 를 선택하여 연결을 구성합니다.

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 이 연결을 사용할 수 있는 사용자를 선택합니다. 아무 조치도 취하지 않으면 기본값은 관리자입니다. 자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.

1. **사용자 이름**, **암호**, **호스트 이름** 및 **내보내기 폴더** 를 제공합니다.

1. **확인** 을 선택해 연결을 테스트합니다.

1. 내보낼 데이터의 상태를 **GZipped** 또는 **압축 해제** 중에서 선택하고 내보낸 파일의 **필드 구분자** 를 선택합니다.

1. **동의** 를 선택해 **데이터 프라이버시 및 규정 준수** 를 확인합니다.

1. 연결을 완료하려면 **저장** 을 선택합니다.

## <a name="configure-an-export"></a>내보내기 구성

이 유형의 연결에 대한 액세스 권한이 있는 경우 이 내보내기를 구성할 수 있습니다. 자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.

1. **데이터** > **내보내기** 로 이동합니다.

1. **대상 추가** 를 선택하여 새 내보내기를 만듭니다.

1. **내보내기 연결** 필드의 SFTP 섹션에서 연결을 선택합니다. 이 섹션 이름이 표시되지 않으면 사용 가능한 이 유형의 연결이 없는 것입니다.

1. 내보내려는 엔터티(예: 세그먼트)를 선택합니다.

   > [!NOTE]
   > 선택한 각 엔터티는 내보낼 때 최대 5개의 출력 파일로 분할됩니다. 

1. **저장** 을 선택합니다.

내보내기를 저장해도 내보내기가 즉시 실행되지는 않습니다.

내보내기는 모든 [예약된 새로 고침](system.md#schedule-tab)에 따라 실행됩니다. [주문형으로 데이터를 내보낼](export-destinations.md#run-exports-on-demand)수도 있습니다. 

## <a name="data-privacy-and-compliance"></a>데이터 프라이버시 및 규정 준수

Dynamics 365 Customer Insights를 사용하여 SFTP를 통해 데이터를 전송하는 경우 Dynamics 365 Customer Insights규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다. Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 내보내기 대상이 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다. 자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.
Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
