---
title: Salesforce Marketing Cloud로 데이터 내보내기(프리뷰)
description: 연결을 구성하고 Salesforce Marketing Cloud로 내보내는 방법을 알아봅니다.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197046"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Salesforce Marketing Cloud로 데이터 내보내기(프리뷰)

SFTP(Secure File Transfer Protocol) 위치를 통해 내보냄으로써 Salesforce Marketing Cloud에서 고객 데이터를 사용하십시오.

## <a name="prerequisites"></a>전제 조건

- [Salesforce Marketing Cloud용 SFTP 호스트](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 및 해당 관리자 자격 증명입니다.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Salesforce Marketing Cloud에 대한 연결 설정

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 를 선택하고 **Salesforce Marketing Cloud** 를 선택합니다.

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 이 연결을 사용할 수 있는 사용자를 선택합니다. 기본적으로 관리자만 해당합니다. 자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.

1. **사용자 이름**, **암호**, **호스트 이름** 및 **내보내기 폴더** 를 제공합니다.

1. **확인** 을 선택해 연결을 테스트합니다.

1. [데이터 개인 정보 보호 및 규정 준수](connections.md#data-privacy-and-compliance)를 검토하고 **동의함** 을 선택합니다.

1. 연결을 완료하려면 **저장** 을 선택합니다.

## <a name="configure-an-export"></a>내보내기 구성

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **데이터** > **내보내기** 로 이동합니다.

1. **내보내기 추가** 를 선택합니다.

1. **내보내기 연결** 필드의 SFTP 섹션에서 연결을 선택합니다. 사용 가능한 연결이 없으면 관리자에게 문의하십시오.

1. 내보낼 엔터티의 이름을 입력합니다.

1. 내보낼 데이터의 상태를 **GZipped** 또는 **압축 해제** 중에서 선택하고 내보낸 파일의 **필드 구분자** 를 선택합니다.

1. 내보내려는 엔터티(예: 세그먼트)를 선택합니다.

   > [!NOTE]
   > 선택한 각 엔터티는 내보낼 때 최대 5개의 출력 파일로 분할됩니다.

1. **저장** 을 선택합니다.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>SFTP 위치에서 Salesforce Marketing Cloud로 Customer Insights 데이터 가져오기

1. [Salesforce Marketing Cloud에서 데이터 확장](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5)을 만들어 SFTP 위치에서 Customer Insights 데이터 파일을 가져옵니다.

2. [SFTP 위치에서](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) Salesforce Marketing Cloud 데이터 확장에 데이터를 가져옵니다.

3. 데이터를 데이터 확장으로 가져오도록 자동화를 설정하십시오. [파일 드롭 자동화 및 예약된 자동화](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5)에 대해 자세히 알아보세요.

   [파일 드롭 자동화](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) 또는 [예약된 자동화](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5)를 정의합니다.

다음은 [SFTP를 통한 자동화](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5)의 예입니다.

[!INCLUDE [footer-include](includes/footer-banner.md)]
