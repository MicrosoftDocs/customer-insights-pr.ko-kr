---
title: SFTP 사용자 지정 가져오기로 보강
description: SFTP 사용자 지정 가져오기 보강에 대한 일반 정보입니다.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f52d24cbe793bee7948ad2af31059cd3edf40f94
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646542"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>사용자 지정 데이터로 고객 프로필 보강(미리 보기)

SFTP(보안 파일 전송 프로토콜) 사용자 지정 가져오기를 사용하면 데이터 통합 프로세스를 거치지 않아도 되는 데이터를 가져올 수 있습니다. 데이터를 가져오는 유연하고 안전하며 쉬운 방법입니다. SFTP 사용자 지정 가져오기는 보강에 필요한 고객 프로필 데이터를 내보낼 수 있는 [SFTP 내보내기](export-sftp.md)와 함께 사용할 수 있습니다. 그런 다음 데이터를 처리하고 보강할 수 있으며 SFTP 사용자 지정 가져오기를 사용하여 보강된 데이터를 Dynamics 365 Customer Insights로 다시 가져올 수 있습니다.

## <a name="prerequisites"></a>전제 조건

SFTP 사용자 지정 가져오기를 구성하려면 다음 전제 조건이 충족되어야 합니다.

- SFTP 호스트에서 가져올 파일의 이름과 위치(경로)가 있습니다.
- 가져올 데이터의 [Common Data Model 스키마](/common-data-model/)를 지정하는 *model.json* 파일이 있음. 이 파일은 가져올 파일과 동일한 디렉터리에 있어야 합니다.
- 관리자가 SFTP 연결을 이미 구성 *했거나* 귀하가 [관리자](permissions.md#admin) 권한을 가지고 있음. 데이터를 가져올 SFTP 위치에 대한 사용자 자격 증명, URL 및 포트 번호.


## <a name="configure-the-import"></a>가져오기 구성

1. **데이터** > **보강** 으로 이동 후, **발견하기** 탭을 선택합니다.

1. **SFTP 사용자 지정 가져오기 타일** 에서 **내 데이터 보강** 을 선택하고 **시작** 을 선택합니다.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP 사용자 지정 가져오기 타일":::

1. 드롭다운 목록에서 [연결](connections.md)을 선택하십시오. 사용 가능한 연결이 없으면 관리자에게 문의하십시오. 관리자인 경우 **연결 추가** 를 선택하고 드롭다운 목록에서 **SFTP 사용자 지정 가져오기** 를 선택하여 연결을 만들 수 있습니다.

1. **사용자 지정 가져오기 연결** 을 선택하여 선택한 연결을 확인합니다.

1.  **다음** 을 선택한 후 가져올 데이터 파일의 **경로** 및 **파일 이름** 을 입력합니다.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="데이터 위치 입력 시 스크린 샷.":::

1. **다음** 을 선택하고 고객 데이터 세트를 선택합니다. 모든 고객 프로필 또는 세그먼트일 수 있습니다.

1. **다음** 을 선택하고 보강 이름과 출력 엔터티 이름을 제공합니다. 

1. 선택 사항을 검토 한 후 **보강 저장** 을 선택합니다.

## <a name="configure-the-connection-for-sftp-custom-import"></a>SFTP 사용자 지정 가져오기에 대한 연결 구성 

연결을 구성하려면 관리자여야 합니다. 보강을 구성할 때 **연결 추가** 를 선택 *하거나* **관리자** > **연결** 로 이동하여 사용자 지정 가져오기 타일에서 **설정** 을 선택합니다.

1. **표시 이름** 상자에 연결 이름을 입력합니다.

1. 가져올 데이터가 있는 SFTP 서버의 유효한 사용자 이름, 비밀번호 및 호스트 URL을 입력하십시오.

1. **동의함** 확인란을 선택하여 **데이터 개인 정보 및 규정 준수** 에 대한 동의를 검토하고 제공합니다.

1. **확인** 을 선택하여 구성을 확인합니다.

1. 확인이 완료되면 **저장** 을 선택하여 연결을 저장할 수 있습니다.

   > [!div class="mx-imgBorder"]
   > ![Experian 연결 구성 페이지.](media/enrichment-SFTP-connection.png "Experian 연결 구성 페이지")


## <a name="defining-field-mappings"></a>필드 매핑 정의 

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
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
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

## <a name="enrichment-results"></a>보강 결과

강화 프로세스를 시작하려면 명령 모음에서.**실행** 을 선택하십시오. [예약된 새로 고침](system.md#schedule-tab)으로 시스템이 자동으로 보강을 실행하도록 할 수도 있습니다. 처리 시간은 가져올 데이터의 크기와 SFTP 서버에 대한 연결에 따라 다릅니다.

보강 프로세스가 완료된 후 **내 보강** 에서 새로 가져온 사용자 지정 보강 데이터를 검토할 수 있습니다. 또한 마지막 업데이트 시간과 강화 된 프로필 수를 확인할 수 있습니다.

**보강된 데이터 보기** 를 선택하여 각 보강된 프로필의 상세 보기에 액세스할 수 있습니다 .

## <a name="next-steps"></a>다음 단계

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
