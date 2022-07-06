---
title: Salesforce Marketing Cloud로 데이터 내보내기(프리뷰)
description: 연결을 구성하고 Salesforce Marketing Cloud로 내보내는 방법을 알아봅니다.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c3a6a40d9b9f08c8ebca8cb4a9196a1a79f03afa
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081463"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Salesforce Marketing Cloud로 데이터 내보내기(프리뷰)

SFTP(Secure File Transfer Protocol) 위치를 통해 내보냄으로써 Salesforce Marketing Cloud에서 고객 데이터를 사용하십시오.

## <a name="prerequisites-for-connection"></a>연결을 위한 전제 조건

- SFTP 호스트 및 해당 관리자 자격 증명의 가용성. [Salesforce Marketing Cloud에 대한 SFTP 위치를 설정하는 방법](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Salesforce Marketing Cloud에 대한 연결 설정

1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 를 선택하고 **Salesforce Marketing Cloud** 를 선택하여 연결을 구성합니다.

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 이 연결을 사용할 수 있는 사용자를 선택합니다. 아무 조치도 취하지 않으면 기본값은 관리자입니다. 자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.

1. **사용자 이름**, **암호**, **호스트 이름** 및 **내보내기 폴더** 를 제공합니다.

1. **확인** 을 선택해 연결을 테스트합니다.

1. **동의** 를 선택해 **데이터 프라이버시 및 규정 준수** 를 확인합니다.

1. 연결을 완료하려면 **저장** 을 선택합니다.

## <a name="configure-an-export"></a>내보내기 구성

이 유형의 연결에 대한 액세스 권한이 있는 경우 이 내보내기를 구성할 수 있습니다. 자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.

1. **데이터** > **내보내기** 로 이동합니다.

1. **대상 추가** 를 선택하여 새 내보내기를 만듭니다.

1. **내보내기 연결** 필드의 SFTP 섹션에서 연결을 선택합니다. 이 섹션 이름이 표시되지 않으면 사용 가능한 이 유형의 연결이 없는 것입니다.

1. 내보낼 데이터의 상태를 **GZipped** 또는 **압축 해제** 중에서 선택하고 내보낸 파일의 **필드 구분자** 를 선택합니다.

1. 내보내려는 엔터티(예: 세그먼트)를 선택합니다.

   > [!NOTE]
   > 선택한 각 엔터티는 내보낼 때 최대 5개의 출력 파일로 분할됩니다. 

1. **저장** 을 선택합니다.

내보내기를 저장해도 내보내기가 즉시 실행되지는 않습니다.

내보내기는 모든 [예약된 새로 고침](system.md#schedule-tab)에 따라 실행됩니다. [주문형으로 데이터를 내보낼](export-destinations.md#run-exports-on-demand)수도 있습니다. 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>SFTP 위치에서 Salesforce Marketing Cloud로 Customer Insights 데이터 가져오기

1. [Salesforce Marketing Cloud에서 데이터 확장](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5)을 만들어 SFTP 위치에서 Customer Insights 데이터 파일을 가져옵니다.

2. [SFTP 위치에서](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) Salesforce Marketing Cloud 데이터 확장에 데이터를 가져옵니다. 

3. 데이터를 데이터 확장으로 가져오도록 자동화를 설정하십시오. [파일 드롭 자동화 및 예약된 자동화](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5)에 대해 자세히 알아보세요.

   [파일 드롭 자동화](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) 또는 [예약된 자동화](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5)를 정의합니다. 

다음은 [SFTP를 통한 자동화](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5)의 예입니다.

## <a name="data-privacy-and-compliance"></a>데이터 프라이버시 및 규정 준수

Dynamics 365 Customer Insights를 사용하여 SFTP를 통해 데이터를 전송하는 경우 Dynamics 365 Customer Insights규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다. Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 내보내기 대상이 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다. 자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.
Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.

[!INCLUDE [footer-include](includes/footer-banner.md)]
