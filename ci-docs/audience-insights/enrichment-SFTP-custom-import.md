---
title: SFTP 사용자 지정 가져오기로 보강
description: SFTP 사용자 지정 가져오기 보강에 대한 일반 정보입니다.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f25dcc08d96d36507e47af0d7b184003ae095819
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269614"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>사용자 지정 데이터로 고객 프로필 보강(미리 보기)

SFTP(보안 파일 전송 프로토콜) 사용자 지정 가져오기를 사용하면 데이터 통합 프로세스를 거치지 않아도 되는 데이터를 가져올 수 있습니다. 데이터를 가져오는 유연하고 안전하며 쉬운 방법입니다. SFTP 사용자 지정 가져오기는 보강에 필요한 고객 프로필 데이터를 내보낼 수 있는 [SFTP 내보내기](export-sftp.md)와 함께 사용할 수 있습니다. 그런 다음 데이터를 처리하고 보강할 수 있으며 SFTP 사용자 지정 가져오기를 사용하여 보강된 데이터를 다시 Dynamics 365 Customer Insights의 대상 그룹 인사이트 기능으로 가져올 수 있습니다.

## <a name="prerequisites"></a>필수 구성 요소

SFTP 사용자 지정 가져오기를 구성하려면 다음 전제 조건이 충족되어야 합니다.

- 가져올 데이터가 있는 SFTP 위치에 대한 사용자 자격 증명(사용자 이름 및 암호)이 있습니다.
- STFP 호스트에 대한 URL 및 포트 번호(일반적으로 22)가 있습니다.
- SFTP 호스트에서 가져올 파일의 파일 이름과 위치가 있습니다.
- 가져올 데이터의 스키마를 지정하는 *model.json* 파일이 있습니다. 이 파일은 가져올 파일과 동일한 디렉터리에 있어야 합니다.
- [관리자](permissions.md#administrator) 권한이 있어야 합니다.

## <a name="configuration"></a>구성

1. **데이터** > **보강** 으로 이동 후, **발견하기** 탭을 선택합니다.

1. **SFTP 사용자 지정 가져오기 타일** 에서 **내 데이터 보강을 선택** 합니다.

   > [!div class="mx-imgBorder"]
   > ![사용자 지정 가져오기 타일](media/SFTP_Custom_Import_tile.png "사용자 지정 가져오기 타일")

1. **시작** 을 선택하고 SFTP 서버의 자격 증명과 주소를 제공합니다. 예를 들어 sftp://mysftpserver.com:22입니다.

1. 루트 폴더에 없는 경우 데이터가 포함된 파일의 이름과 SFTP 서버에 있는 파일 경로를 입력합니다.

1. **사용자 지정 가져오기에 연결** 을 선택하여 모든 입력을 확인합니다.

   > [!div class="mx-imgBorder"]
   > ![SFTP 사용자 지정 가져오기 구성 플라이아웃](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP 사용자 지정 가져오기 구성 플라이아웃")

## <a name="defining-field-mappings"></a>필드 매핑 정의 

SFTP 서버에서 가져올 파일이 포함된 디렉터리에는 *model.json* 파일도 포함되어 있어야 합니다. 이 파일은 데이터를 가져오는 데 사용할 스키마를 정의합니다. 스키마에서 [Common Data Model](https://docs.microsoft.com/common-data-model/)을 사용하여 필드 매핑을 지정해야 합니다. model.json 파일의 간단한 예는 다음과 같습니다.

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

보강된 고객 데이터를 바탕으로 구축합니다. [세그먼트](segments.md), [측정값](measures.md)을 만들고 [데이터를 내보내](export-destinations.md) 고객에게 개인화된 경험을 제공합니다.




[!INCLUDE[footer-include](../includes/footer-banner.md)]