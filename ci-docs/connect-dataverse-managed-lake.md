---
title: Microsoft Dataverse 관리형 데이터 레이크의 데이터에 연결
description: Microsoft Dataverse 관리 데이터 레이크에서 데이터 가져오기
ms.date: 08/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 0d9612525344c8ac99b6e3edfe33a426dc0a474b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609803"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Microsoft Dataverse 관리형 데이터 레이크의 데이터에 연결

Microsoft Dataverse 사용자는 Microsoft Dataverse 관리 레이크에서 분석 개체에 빠르게 연결할 수 있습니다. 환경의 데이터 원본 하나만 동일한 Dataverse 관리 레이크를 동시에 사용할 수 있습니다.

> [!NOTE]
> Dataverse 조직의 관리자여야만 계속 진행하고 관리형 레이크에서 사용 가능한 엔터티 목록을 볼 수 있습니다.

## <a name="prerequisites"></a>전제 조건

- Azure Data Lake Storage와 같은 온라인 서비스에 저장된 데이터는 Dynamics 365 Customer Insights에서 데이터가 처리 또는 저장된 위치와 다른 곳에 저장될 수 있습니다. 온라인 서비스에서 데이터를 가져오거나 이에 연결하면 해당 데이터가 Dynamics 365 Customer Insights에 전송되거나 저장될 수 있음에 동의하는 것입니다. [Microsoft 보안 센터에서 자세히 알아보십시오.](https://www.microsoft.com/trust-center)

- [변경 추적](/power-platform/admin/enable-change-tracking-control-data-synchronization)이 활성화된 Dataverse 엔터티만 표시됩니다. 이러한 엔터티는 Dataverse 관리형 데이터 레이크로 내보내고 Customer Insights에서 사용할 수 있습니다. 기본 Dataverse 테이블에는 기본적으로 변경 내용 추적이 활성화되어 있습니다. 사용자 지정 테이블에 대해 변경 내용 추적을 켜야 합니다. Dataverse 테이블이 변경 추적을 위해 활성화되어 있는지 확인하려면 [Power Apps](https://make.powerapps.com) > **데이터** > **테이블** 로 이동합니다. 관심 있는 테이블을 찾아 선택합니다. **설정** > **고급 옵션** 으로 이동하여 **변경 사항 추적** 설정을 검토합니다.

## <a name="connect-to-a-dataverse-managed-lake"></a>Dataverse 관리 레이크에 연결

1. **데이터** > **데이터 원본** 으로 이동.

1. **데이터 원본 추가** 를 선택합니다.

1. **Microsoft Dataverse** 를 선택합니다.

1. 데이터 소스의 **이름** 과 **설명**(선택 사항)을 입력합니다.

1. Dataverse 조직의 **서버 주소** 를 제공하고 **로그인** 을 선택합니다.

1. 사용 가능한 목록에서 Customer Insights에 엔터티로 수집할 테이블을 선택합니다.

   > [!NOTE]
   > 일부 테이블이 이미 선택된 경우 다른 Dynamics 365 응용 프로그램(예: Dynamics 365 Sales Insights 또는 Customer Service Insights)에서 사용할 수 있습니다. 선택 사항은 변경할 수 없습니다. 이 테이블은 데이터 원본이 생성되면 엔터티로 사용할 수 있습니다.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dataverse 환경의 엔터티 목록을 보여주는 대화 상자.":::

1. Dataverse에서 선택한 테이블의 동기화를 시작하려면 선택 항목을 저장하십시오. 새로 추가된 연결은 **데이터 원본** 페이지에서 찾을 수 있습니다. 새로 고침을 위해 대기하고 선택한 모든 테이블이 동기화될 때까지 엔터티 수를 0으로 표시합니다.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

데이터를 로드하는 데 시간이 걸릴 수 있습니다. 새로 고침이 완료되면, 수집된 데이터를 [**엔터티**](entities.md) 페이지에서 검토할 수 있습니다.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Dataverse 관리 레이크 데이터 원본 편집

데이터 원본을 생성한 후에만 엔터티 선택을 편집할 수 있습니다. 예를 들어, 만약 추가 엔티티가 Dataverse에 추가 되었고 당신 또한 그 것들을 가져오고 싶습니다.
다른 Dataverse 데이터 레이크에 연결하려면, [새로운 데이터 원본 생성](#connect-to-a-dataverse-managed-lake)을 수행합니다.

1. **데이터** > **데이터 원본** 으로 이동.

1. 업데이트하려는 데이터 원본 옆에 있는 **편집** 을 선택합니다.

1. 사용 가능한 엔터티 목록에서 추가 엔터티를 선택합니다.

1. **저장** 을 클릭하여 변경 사항을 적용하고 **데이터 원본** 페이지로 돌아갑니다.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupted-data"></a>수집 오류 또는 데이터 손상의 일반적인 이유

수집된 데이터에 대해 다음 검사를 실행하여 손상된 레코드를 노출합니다.

- 필드 값이 해당 열의 데이터 유형과 일치하지 않습니다.
- 필드에 열이 예상 스키마와 일치하지 않게 하는 문자가 포함되어 있습니다. 예: 잘못된 형식의 따옴표, 이스케이프 처리되지 않은 따옴표 또는 복귀 개행 문자.
- datetime/date/datetimeoffset 열이 있으면 표준 ISO 형식을 따르지 않는 경우 해당 형식을 모델에 지정해야 합니다.

### <a name="schema-or-data-type-mismatch"></a>스키마 또는 데이터 형식 불일치

데이터가 스키마를 따르지 않으면 레코드가 손상된 것으로 분류됩니다. 원본 데이터 또는 스키마를 수정하고 데이터를 다시 수집하십시오.

### <a name="datetime-fields-in-the-wrong-format"></a>잘못된 형식의 날짜/시간 필드

엔터티의 날짜/시간 필드가 ISO 또는 en-US 형식이 아닙니다. Customer Insights의 기본 날짜/시간 형식은 en-US 형식입니다. 엔터티의 모든 날짜/시간 필드는 동일한 형식이어야 합니다. Customer Insights는 모델 또는 manifest.json의 원본 또는 엔터티 수준에서 주석 또는 특성이 만들어지면 다른 형식을 지원합니다. 예:

**Model.json**

   ```json
      "annotations": [
        {
          "name": "ci:CustomTimestampFormat",
          "value": "yyyy-MM-dd'T'HH:mm:ss:SSS"
        },
        {
          "name": "ci:CustomDateFormat",
          "value": "yyyy-MM-dd"
        }
      ]   
   ```

  manifest.json에서 날짜/시간 형식은 엔터티 수준 또는 특성 수준에서 지정할 수 있습니다. 엔터티 수준에서 *.manifest.cdm.json의 엔터티의 "exhibitsTraits"를 사용하여 날짜/시간 형식을 정의합니다. 특성 수준에서 entityname.cdm.json의 속성에 "appliedTraits"를 사용합니다.

**엔터티 수준의 Manifest.json**

```json
"exhibitsTraits": [
    {
        "traitReference": "is.formatted.dateTime",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd'T'HH:mm:ss"
            }
        ]
    },
    {
        "traitReference": "is.formatted.date",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd"
            }
        ]
    }
]
```

**특성 수준의 Entity.json**

```json
   {
      "name": "PurchasedOn",
      "appliedTraits": [
        {
          "traitReference": "is.formatted.date",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-dd"
            }
          ]
        },
        {
          "traitReference": "is.formatted.dateTime",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-ddTHH:mm:ss"
            }
          ]
        }
      ],
      "attributeContext": "POSPurchases/attributeContext/POSPurchases/PurchasedOn",
      "dataFormat": "DateTime"
    }
```

[!INCLUDE [footer-include](includes/footer-banner.md)]
