---
title: 엔터티 및 엔터티 경로 간 관계
description: 여러 데이터 원본의 항목 간에 관계를 만들고 관리합니다.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 1853fcd8db2918a0b4a19fa0934e2f0ddbcf6d093c85fdf2068a13f954035dec
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035239"
---
# <a name="relationships-between-entities"></a>엔터티 간 관계

관계는 엔터티를 연결하고 엔터티가 공통 식별자인 외래 키를 공유할 때 데이터 그래프를 정의합니다. 이 외래 키는 한 엔터티에서 다른 엔터티로 참조될 수 있습니다. 연결된 엔터티를 사용하면 여러 데이터 원본을 기반으로 세그먼트 및 측정값을 정의할 수 있습니다.

관계에는 세 가지 유형이 있습니다. 
- 데이터 통합 프로세스의 일부로 시스템에서 만들어진 편집 불가능한 시스템 관계
- 데이터 원본 수집에서 자동으로 만들어진 편집 불가능한 상속된 관계 
- 사용자가 만들고 구성한 편집 가능한 사용자 지정 관계

## <a name="non-editable-system-relationships"></a>편집 불가능한 시스템 관계

데이터 통합 과정에서 시스템 관계는 지능형 매칭을 기반으로 자동으로 만들어집니다. 이러한 관계 고객 프로필 레코드를 해당 레코드와 연관시키는 데 도움이 됩니다. 다음 다이어그램은 세 가지 시스템 기반 관계의 생성을 보여줍니다. 고객 엔터티는 다른 엔터티와 매칭되어 통합 *고객* 엔터티를 생성합니다.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="3개의 1-n 관계가 있는 고객 엔터티에 대한 관계 경로의 다이어그램.":::

- ***CustomerToContact* 관계** 는 *고객* 엔터티와 *연락처* 엔터티 간에 만들어졌습니다. *고객* 엔터티는 *연락처* 엔터티 키 필드 **contactID** 와 관련되는 키 필드 **Contact_contactID** 를 가져옵니다.
- ***CustomerToAccount* 관계** 는 *고객* 엔터티와 *거래처* 엔터티 간에 만들어졌습니다. *고객* 엔터티는 *거래처* 엔터티 키 필드 **accountID** 와 관련되는 키 필드 **Account_accountID** 를 가져옵니다.
- ***CustomerToWebAccount* 관계** 는 *고객* 엔터티와 *WebAccount* 엔터티 간에 만들어졌습니다. *고객* 엔터티는 *WebAccount* 엔터티 키 필드 **webaccountID** 와 관련되는 키 필드 **WebAccount_webaccountID** 를 가져옵니다.

## <a name="non-editable-inherited-relationships"></a>편집 불가능한 상속된 관계

데이터 수집 프로세스 중에 시스템은 기존 관계의 데이터 원본을 확인합니다. 관계가 없는 경우 시스템이 자동으로 생성합니다. 이러한 관계는 다운스트림 프로세스에서도 사용됩니다.

## <a name="create-a-custom-relationship"></a>사용자 지정 관계 만들기

관계는 외래 키를 포함하는 *소스 엔터티* 와 소스 엔터티의 외래 키가 가리키는 *대상 엔터티* 로 구성됩니다. 

1. 대상 그룹 인사이트에서 **데이터** > **데이터 원본** 으로 이동합니다.

2. **새 관계** 를 선택합니다.

3. **새 관계** 창에 다음 정보를 제공합니다.

   :::image type="content" source="media/relationship-add.png" alt-text="빈 입력 필드가 있는 새 관계 측면 창.":::

   - **관계 이름**: 관계의 목적을 나타내는 이름입니다. 예: CustomerToSupportCase.
   - **설명**: 관계에 대한 설명입니다.
   - **소스 엔터티**: 관계에서 소스로 사용되는 엔터티입니다. 예: SupportCase.
   - **대상 엔터티**: 관계에서 대상으로 사용되는 엔터티입니다. 예: 고객.
   - **소스 카디널리티** : 소스 엔터티의 카디널리티를 지정합니다. 카디널리티는 집합에서 가능한 요소 수를 설명합니다. 항상 대상 카디널리티와 관련됩니다. **하나** 와 **다수** 중에서 선택할 수 있습니다. 다대일 및 일대일 관계만 지원됩니다.  
     - 다대일: 여러 소스 레코드가 하나의 대상 레코드와 관련될 수 있습니다. 예: 단일 고객의 여러 지원 서비스 케이스.
     - 일대일: 단일 소스 레코드가 하나의 대상 레코드와 관련됩니다. 예: 단일 고객에 대한 하나의 로열티 ID.

     > [!NOTE]
     > 다대다 관계는 두 개의 다대일 관계와 소스 엔터티 및 대상 엔터티를 연결하는 연결 엔터티를 사용하여 생성할 수 있습니다.

   - **카디널리티**: 대상 엔터티 레코드의 카디널리티를 선택합니다. 
   - **소스 키 필드**: 소스 엔터티의 외래 키 필드입니다. 예: SupportCase는 CaseID를 외래 키 필드로 사용할 수 있습니다.
   - **대상 키 필드**:대상 엔터티의 키 필드입니다. 예시 고객은 **CustomerID** 키 필드를 사용할 수 있습니다.

4. **저장** 을 선택하여 사용자 지정 관계를 만듭니다.

## <a name="view-relationships"></a>관계 보기

관계 페이지에는 만들어진 모든 관계가 나열됩니다. 각 행은 관계를 나타내며 소스 엔터티, 대상 엔터티 및 카디널리티에 대한 세부 정보도 포함합니다. 

:::image type="content" source="media/relationships-list.png" alt-text="관계 페이지의 작업 표시줄에 있는 관계 및 옵션 목록입니다.":::

이 페이지는 기존 및 신규 관계에 대한 옵션 집합을 제공합니다. 
- **새 관계:** [사용자 지정 관계 만들기](#create-a-custom-relationship).
- **시각화 도우미**: [관계 시각화 도우미 탐색](#explore-the-relationship-visualizer)을 통해 기존 관계 및 해당 카디널리티의 네트워크 다이어그램을 확인합니다.
- **필터링 기준**: 목록에 표시할 관계 유형을 선택합니다.
- **관계 검색**: 관계의 속성에 대한 텍스트 기반 검색을 사용합니다.

### <a name="explore-the-relationship-visualizer"></a>관계 시각화 도우미 탐색

관계 시각화 도우미는 연결된 엔터티와 해당 카디널리티 간의 기존 관계에 대한 네트워크 다이어그램을 보여줍니다. 또한 관계 경로를 시각화합니다.

보기를 사용자 지정하려면 상자를 캔버스에서 끌어 상자의 위치를 변경하면 됩니다.

:::image type="content" source="media/relationship-visualizer.png" alt-text="관련 엔터티 간의 연결이 있는 관계 시각화 도우미 네트워크 다이어그램의 스크린샷입니다.":::

사용 가능한 옵션: 
- **이미지로 내보내기**: 현재 보기를 이미지 파일로 저장합니다.
- **가로/세로 레이아웃으로 변경** : 엔터티 및 관계의 정렬 방식을 변경합니다.
- **편집**: 편집 창에서 사용자 지정 관계의 속성을 업데이트하고 변경 사항을 저장합니다.

### <a name="relationship-path"></a>관계 경로

관계 경로는 소스 엔터티와 대상 엔터티 간에 관계로 연결된 엔터티를 설명합니다. 통합 프로필 엔터티 이외의 다른 엔터티를 포함하는 세그먼트 또는 측정값을 생성할 때 사용되며 통합 프로필 엔터티에 도달하기 위한 여러 옵션이 있습니다.

관계 경로는 시스템에 관계가 통합 프로필 엔터티에 액세스하도록 알려줍니다. 다른 관계 경로는 다른 결과를 산출할 수 있습니다.

예를 들어 *eCommerce_eCommercePurchases* 엔터티는 통합 프로필 *고객* 엔터티에 대해 다음과 같은 관계를 갖습니다.

- eCommerce_eCommercePurchases > 고객
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > 고객
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > 고객 

관계 경로는 측정값 또는 세그먼트에 대한 규칙을 생성할 때 사용할 수 있는 엔터티를 결정합니다. 가장 긴 관계 경로가 있는 옵션을 선택하면 일치하는 레코드가 모든 엔터티의 일부가 되어야 하기 때문에 더 적은 결과를 얻을 수 있습니다. 이 예에서 고객은 판매 시점(POS_posPurchases)에서 전자 상거래(eCommerce_eCommercePurchases)를 통해 상품을 구매하고 로열티 프로그램(loyaltyScheme_loyCustomers)에 참여해야 합니다. 첫 번째 옵션을 선택하면 고객이 하나의 추가 엔터티에만 있으면 되므로 더 많은 결과를 얻을 수 있습니다.

## <a name="manage-existing-relationships"></a>기존 관계 관리 

관계 페이지에서 각 관계는 행으로 표시됩니다. 

관계를 선택하고 다음 옵션 중 하나를 선택합니다. 
 
- **편집**: 편집 창에서 사용자 지정 관계의 속성을 업데이트하고 변경 사항을 저장합니다.
- **삭제**: 사용자 지정 관계를 삭제합니다.
- **보기**: 시스템 생성 및 상속된 관계 보기. 

## <a name="next-step"></a>다음 단계

시스템 및 사용자 지정 관계는 더 이상 격리되지 않는 여러 데이터 소스를 기반으로 [세그먼트 만들기](segments.md) 및 [측정값](measures.md)에 사용됩니다.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
