---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755552"
---
데이터를 수집한 후 데이터 통합 프로세스를 시작하여 통합된 고객 프로필을 만듭니다. 자세한 내용은 [데이터 통합](../data-unification.md)을 참조하십시오.

### <a name="select-source-fields"></a>원본 필드 선택

1. 데이터를 수집한 후 전자상거래 및 충성도 데이터의 연락처를 공통 데이터 유형에 매핑합니다. **데이터** > **통합** 으로 이동합니다.

1. 고객 프로필을 나타내는 엔터티(**eCommerceContacts** 및 **loyCustomers**)를 선택합니다.

   ![전자상거래와 충성도 데이터 원본을 통합합니다.](../media/unify-ecommerce-loyalty.png)

1. **eCommerceContacts** 의 기본 키로 **ContactId** 를 선택하고 **loyCustomers** 의 기본 키로 **LoyaltyID** 를 선택합니다.

1. **다음** 을 선택합니다. 중복 레코드를 건너뛰고 **다음** 을 ​​선택합니다.

### <a name="match-conditions"></a>일치 조건

1. **eCommerceContacts : eCommerce** 를 기본 엔터티로 선택하고 모든 레코드를 포함합니다.

1. **loyCustomers : LoyaltyScheme** 을 선택하고 모든 레코드를 포함합니다.

1. 규칙 추가:
   - eCommerceContacts 및 loyCustomers 모두에 대해 **성과 이름** 을 선택합니다.
   - **정규화** 에 대해 **유형(전화, 이름, 주소, ...)** 를 선택합니다.
   - **정밀도 수준**: **기본** 및 **값**: **높음** 을 설정합니다.
   - 이름으로 **성과 이름, 이메일** 을 입력합니다.

1. 이메일 주소에 대한 두 번째 조건 추가:
   - eCommerceContacts 및 loyCustomers 모두에 대해 **이메일** 을 선택합니다.
   - 정규화를 비워 둡니다.
   - **정밀도 수준**: **기본** 및 **값**: **높음** 을 설정합니다.

   ![이름 및 이메일에 대한 일치 규칙을 통합합니다.](../media/unify-match-rule.png)

1. **완료** 를 선택합니다.

1. **다음** 을 선택합니다.

### <a name="unify-fields"></a>필드 통합

1. **loyCustomers** 엔터티의 **ContactId** 이름을 **ContactIdLOYALTY** 로 변경하여 수집된 다른 ID와 구분합니다.

1. 검토하려면 **다음** 을 선택하고 **고객 프로필 만들기** 를 선택합니다.
