---
title: SFTP 호스트로 데이터 내보내기(프리뷰)(비디오 포함)
description: 연결을 구성하고 SFTP 위치로 내보내는 방법을 알아봅니다.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207237"
---
# <a name="export-data-to-sftp-hosts-preview"></a>SFTP 호스트로 데이터 내보내기(프리뷰)

고객 데이터를 SFTP(Secure File Transfer Protocol) 위치로 내보내 타사 애플리케이션에서 사용하십시오.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>전제 조건

- SFTP 호스트 및 해당 자격 증명의 가용성.

## <a name="known-limitations"></a>알려진 제한 사항

- 방화벽 뒤에 있는 SFTP 대상은 현재 지원되지 않습니다.
- 내보내기 런타임은 시스템 성능에 따라 다릅니다. 서버의 최소 구성으로 2개의 CPU 코어와 1Gb의 메모리를 권장합니다.
- 2개의 CPU 코어와 1GB 메모리의 권장 최소 구성을 사용하면 최대 1억 개의 고객 프로필을 내보내는 데 90분이 걸릴 수 있습니다.
- 인증을 위해 SSH 키를 사용하는 경우 [개인 키 생성](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example)을 PEM 또는 SSH.COM 형식으로 진행하는지 확인하세요. Putty를 사용하는 경우 내보내기를 통해 개인 키를 오픈 SSH로 변환합니다. 다음 개인 키 형식이 지원됩니다.
  - OpenSSL PEM 및 SSH.COM 형식의 RSA
  - OpenSSL PEM 및 SSH.COM 형식의 DSA
  - OpenSSL PEM 형식의 ECDSA 256/384/521
  - OpenSSH 키 형식의 ED25519 및 RSA

## <a name="set-up-connection-to-sftp"></a>SFTP 연결 설정

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 를 선택하고 **SFTP** 를 선택합니다.

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 이 연결을 사용할 수 있는 사용자를 선택합니다. 기본적으로 관리자만 해당합니다. 자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.

1. SSH 또는 연결에 필요한 사용자 이름/비밀번호를 통해 인증할지 여부를 선택하고 필요한 세부 정보를 제공합니다. 인증을 위해 SSH 키를 사용하는 경우 [개인 키 생성](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example)을 PEM 또는 SSH.COM 형식으로 진행하는지 확인하세요. Putty를 사용하는 경우 내보내기를 통해 개인 키를 오픈 SSH로 변환합니다. 다음 개인 키 형식이 지원됩니다.
   - OpenSSL PEM 및 SSH.COM 형식의 RSA
   - OpenSSL PEM 및 SSH.COM 형식의 DSA
   - OpenSSL PEM 형식의 ECDSA 256/384/521
   - OpenSSH 키 형식의 ED25519 및 RSA

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

> [!TIP]
> 많은 양의 데이터가 포함된 엔터티를 내보내면 각 내보내기에 대해 동일한 폴더에 여러 CSV 파일이 생성될 수 있습니다. 내보내기를 완료하는 데 걸리는 시간을 최소화하기 위해 성능상의 이유로 내보내기 분할이 발생합니다.

[!INCLUDE [footer-include](includes/footer-banner.md)]
