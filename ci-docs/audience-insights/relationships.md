---
title: 엔터티 및 엔터티 경로 간 관계
description: 여러 데이터 원본의 항목 간에 관계를 만들고 관리합니다.
ms.date: 04/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c25bfcb8e2a8223498dd1a5e8cfb3712a40ab85e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595220"
---
# <a name="relationships-between-entities"></a>엔터티 간 관계

관계 엔터티가 한 엔터티에서 다른 엔터티로 참조할 수 있는 공통 식별자(외래 키)를 공유할 때 엔터티를 연결하고 데이터 그래프를 생성하는 데 도움이 됩니다. 연결된 엔터티를 사용하면 여러 데이터 원본을 기반으로 세그먼트 및 측정값을 정의할 수 있습니다.

관계에는 다음과 같은 두 가지 유형이 있습니다. 편집할 수 없는 시스템 관계 - 자동으로 생성되며 사용자가 만들고 구성한 사용자 지정 관계입니다.

일치 및 병합 프로세스 동안 시스템 관계 지능형 일치를 기반으로 배경에서 생성됩니다. 이러한 관계 고객 프로필 레코드를 다른 해당 엔터티의 레코드와 연관시키는 데 도움이 됩니다. 다음 다이어그램에서는 고객 엔터티가 추가 엔터티와 일치하여 최종 고객 프로필 엔터티를 생성할 때 세 가지 시스템 관계를 만드는 방법을 보여줍니다.

> [!div class="mx-imgBorder"]
> ![관계 만들기](media/relationships-entities-merge.png "관계 만들기")

- ***CustomerToContact* 관계** 는 고객 엔터티와 연락처 엔터티 간에 만들어졌습니다. 고객 엔터티는 연락처 엔터티 키 필드 **contactId** 와 관련되는 키 필드 **Contact_contactId** 를 가져옵니다.
- ***CustomerToAccount* 관계** 는 고객 엔터티와 거래처 엔터티 간에 만들어졌습니다. 고객 엔터티는 거래처 엔터티 키 필드 **accountId** 와 관련되는 키 필드 **Account_accountId** 를 가져옵니다.
- ***CustomerToWebAccount* 관계** 는 고객 엔터티와 WebAccount 엔터티 간에 만들어졌습니다. 고객 엔터티는 WebAccount 엔터티 키 필드 **webaccountId** 와 관련되는 키 필드 **WebAccount_webaccountId** 를 가져옵니다.

## <a name="create-a-relationship"></a>관계 만들기

**관계** 페이지에서 사용자 지정 관계를 정의합니다. 각 관계는 소스 엔터티(외래 키를 보유하는 엔터티)와 대상 엔터티(원본 엔터티의 외래 키가 가리키는 엔터티)로 구성됩니다.

1. 대상 그룹 인사이트에서 **데이터** > **데이터 원본** 으로 이동합니다.

2. **새 관계** 를 선택합니다.

3. **관계 추가** 창에 다음 정보를 제공합니다.

   > [!div class="mx-imgBorder"]
   > ![관계 세부 정보 입력](media/relationships-add.png "관계 세부 정보 입력")

   - **관계 이름**: 관계의 목적을 반영하는 이름입니다(예: **AccountWebLogs).**
   - **설명**: 관계에 대한 설명입니다.
   - **원본 엔터티**: 관계에서 원본으로 사용되는 엔터티(예: WebLog)를 선택합니다.
   - **카디널리티**: 원본 엔터티 레코드의 카디널리티를 선택합니다. 예를 들어 "다수"는 여러 웹블로그 레코드가 하나의 WebAccount와 관련이 있음을 의미합니다.
   - **원본 키 필드**: 원본 엔터티의 외래 키 필드를 나타냅니다. 예를 들어 WebLog에는 **accountId** 외래 키 필드가 있습니다.
   - **대상 엔터티**: 관계에서 대상으로 사용되는 엔터티(예: WebAccount)를 선택합니다.
   - **카디널리티**: 대상 엔터티 레코드의 카디널리티를 선택합니다. 예를 들어 "하나"는 여러 웹블로그 레코드가 하나의 WebAccount와 관련이 있음을 의미합니다.
   - **대상 키 필드**: 이 필드는 대상 엔터티의 키 필드를 나타냅니다. 예를 들어 WebAccount에는 **accountId** 키 필드가 있습니다.

> [!NOTE]
> 다대일 및 일대일 관계만 지원됩니다. 다대일 관계는 두 개의 다대일 관계 및 링크 엔터티(원본 엔터티와 대상 엔터티를 연결하는 데 사용되는 엔터티)를 사용하여 다대다 관계를 만들 수 있습니다.

## <a name="delete-a-relationship"></a>관계 삭제

1. 대상 그룹 인사이트에서 **데이터** > **데이터 원본** 으로 이동합니다.

2. 삭제하려는 관계의 확인란을 선택합니다.

3. **관계** 표 상단에서 **삭제** 를 선택합니다.

4. 삭제를 확정합니다.

## <a name="next-step"></a>다음 단계

시스템 및 사용자 지정 관계는 더 이상 격리되지 않은 여러 데이터 원본을 기반으로 세그먼트를 만드는 데 사용됩니다. 자세한 내용은 [세그먼트](segments.md)를 참조하십시오.


[!INCLUDE[footer-include](../includes/footer-banner.md)]