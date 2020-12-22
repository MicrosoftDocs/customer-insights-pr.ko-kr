---
title: Customer Insights 데이터를 SFTP 호스트로 내보냅니다.
description: SFTP 호스트에 대한 연결을 구성하는 방법 알아보기.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643511"
---
# <a name="connector-for-sftp-preview"></a>SFTP용 커넥터(미리 보기)

고객 데이터를 SFTP(보안 파일 전송 프로토콜) 호스트로 내보내 타사 애플리케이션에서 사용합니다.

## <a name="prerequisites"></a>필수 구성 요소

- SFTP 호스트 및 해당 자격 증명의 가용성.

## <a name="connect-to-sftp"></a>SFTP에 연결

1. **관리자** > **내보내기 대상** 으로 이동합니다.

1. **SFTP** 아래에서 **설정** 을 선택합니다.

1. **표시 이름** 필드에서 대상에 인식할 수 있는 이름을 지정합니다.

1. SFTP 계정의 **사용자 이름**, **암호** 및 **호스트 이름** 을 제공합니다. 예: SFTP 서버의 루트 폴더가 /root/folder이고 데이터를 /root/folder/ci_export_destination_folder로 내보내려는 경우 호스트는 sftp://<server_address>/ci_export_destination_folder"여야합니다.

1. **확인** 을 선택해 연결을 테스트합니다.

1. 확인 후 데이터 **압축** 또는 **압축 해제** 하여 내보낼지 여부를 선택하고 내보낸 파일의 **필드 구분 기호** 를 선택하십시오.

1. **동의** 를 선택해 **데이터 프라이버시 및 규정 준수** 를 확인합니다.

1. **다음** 을 선택해 내보내기 구성을 시작합니다.

## <a name="configure-the-connection"></a>연결 구성

1. 내보낼 **고객 특성** 을 선택합니다. 하나 이상의 특성을 내보낼 수 있습니다.

1. **다음** 을 선택합니다.

1. 내보낼 세그먼트를 선택합니다.

1. **저장** 을 선택합니다.

## <a name="export-the-data"></a>데이터 내보내기

[주문 시 데이터를 내보낼](export-destinations.md) 수 있습니다. 내보내기는 [예약된 새로 고침](system.md#schedule-tab)마다 실행됩니다.

## <a name="data-privacy-and-compliance"></a>데이터 프라이버시 및 규정 준수

Dynamics 365 Customer Insights를 사용하여 SFTP를 통해 데이터를 전송하는 경우 Dynamics 365 Customer Insights규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다. Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 내보내기 대상이 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다. 자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.
Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.
