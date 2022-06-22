---
title: SFTP 사용자 지정 가져오기로 보강
description: SFTP 사용자 지정 가져오기 보강에 대한 일반 정보입니다.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 657afb6fcb68429680eb677734b4115e69769008
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953727"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>사용자 지정 데이터로 고객 프로필 보강(미리 보기)

SFTP(보안 파일 전송 프로토콜) 사용자 지정 가져오기를 사용하면 데이터 통합 프로세스를 거치지 않아도 되는 데이터를 가져올 수 있습니다. 데이터를 가져오는 유연하고 안전하며 쉬운 방법입니다. SFTP 사용자 지정 가져오기는 보강에 필요한 고객 프로필 데이터를 내보낼 수 있는 [SFTP 내보내기](export-sftp.md)와 함께 사용할 수 있습니다. 그런 다음 데이터를 처리하고 보강할 수 있으며 SFTP 사용자 지정 가져오기를 사용하여 보강된 데이터를 Dynamics 365 Customer Insights로 다시 가져올 수 있습니다.

## <a name="prerequisites"></a>전제 조건

- SFTP 호스트에서 가져올 파일의 파일 이름과 위치(경로)를 알고 있습니다.

- 가져올 데이터에 대한 Common Data Model 스키마를 지정하는 *model.json* 파일을 사용할 수 있습니다. 이 파일은 가져올 파일과 동일한 디렉터리에 있어야 합니다.

- SFTP [연결](connections.md)이 [구성](#configure-the-connection-for-sftp-custom-import)되었습니다.

## <a name="file-schema-example"></a>파일 스키마 예

SFTP 서버에서 가져올 파일이 포함된 디렉터리에는 *model.json* 파일도 포함되어 있어야 합니다. 이 파일은 데이터를 가져오는 데 사용할 스키마를 정의합니다. 스키마는 [Common Data Model](/common-data-model/)을 사용하여 필드 매핑을 지정해야 합니다. model.json 파일의 간단한 예는 다음과 같습니다.

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="configure-the-connection-for-sftp-custom-import"></a>SFTP 사용자 지정 가져오기에 대한 연결 구성

Customer Insights의 [관리자](permissions.md#admin)여야 하며 데이터를 가져올 SFTP 위치에 대한 사용자 자격 증명, URL 및 포트 번호가 있어야 합니다.

1. 강화를 구성할 때 **연결 추가** 를 선택하거나 **관리** > **연결** 로 이동하고 사용자 지정 가져오기 타일에서 **설정** 을 선택합니다.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Custom Import 연결 구성 페이지.":::

1. 연결 이름을 입력합니다.

1. 가져올 데이터가 있는 SFTP 서버의 유효한 사용자 이름, 비밀번호 및 호스트 URL을 입력하십시오.

1. [데이터 개인 정보 보호 및 규정 준수](#data-privacy-and-compliance)를 검토하고 **동의함** 을 선택하여 동의를 제공합니다.

1. **확인** 을 선택하여 구성을 확인한 다음 **저장** 을 선택합니다.

### <a name="data-privacy-and-compliance"></a>데이터 프라이버시 및 규정 준수

Dynamics 365 Customer Insights에서 Custom Import를 사용하여 데이터를 전송하도록 설정하면 개인 데이터와 같이 잠재적으로 민감한 데이터를 포함하여 Dynamics 365 Customer Insights의 규정 준수 경계 외부로 데이터를 전송할 수 있습니다. Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 귀하는 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 데이터가 충족하는지 확인할 책임이 있습니다. 자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.
Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 보강을 언제든지 제거할 수 있습니다.

## <a name="configure-the-import"></a>가져오기 구성

1. **데이터** > **보강** 으로 이동 후, **발견하기** 탭을 선택합니다.

1. **SFTP 사용자 지정 가져오기** 타일에서 **내 데이터 보강** 을 선택합니다.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP 사용자 지정 가져오기 타일":::

1. 개요를 검토한 후 **다음** 을 선택합니다.

1. 연결을 선택합니다. 관리자가 없는 경우 관리자에게 문의하세요.

1. **고객 데이터 세트** 를 선택하고 보강할 프로필 또는 세그먼트를 선택합니다. *고객* 엔터티는 모든 고객 프로필을 강화하는 반면 세그먼트는 해당 세그먼트에 포함된 고객 프로필만 강화합니다.

1. **다음** 을 선택합니다.

1. 가져올 데이터 파일의 **경로** 와 **파일 이름** 을 입력합니다.

1. **다음** 을 선택합니다.

1. 보강에 대한 **이름** 과 **출력 엔터티 이름** 을 제공합니다.

1. 선택 사항을 검토 한 후 **보강 저장** 을 선택합니다.

1. **실행** 을 선택하여 강화 프로세스를 시작하거나 닫기를 선택하여 **강화** 페이지로 돌아갑니다.

## <a name="enrichment-results"></a>보강 결과

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>다음 단계

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
