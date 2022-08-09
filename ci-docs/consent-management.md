---
title: 고객 동의 사용
description: 동의 데이터를 가져와 Customer Insights에서 고객의 동의 기본 설정을 존중합니다.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 99fe24cb47a8c20f629182d9a1c6adfd36a1eaf7
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188056"
---
# <a name="use-customer-consent"></a>고객 동의 사용

데이터 보호 및 개인 정보 보호 규정은 조직에서 개인 데이터를 사용하는 방식을 관리할 수 있는 권한을 개인에게 제공합니다. 그러한 규정의 예로는 유럽 연합의 일반 데이터 보호 규정 또는 미국의 캘리포니아 소비자 개인 정보 보호법이 있습니다. 이러한 규정은 사람들이 자신의 개인 데이터를 제3자에 의해 수집, 처리 또는 공유하는 것을 거부할 수 있도록 허용합니다.  

고객은 특정 형태의 연락에 대한 동의를 철회하거나 보류할 수 있습니다. 또한 개인 데이터의 수집, 저장, 사용 또는 판매를 거부하도록 요청할 수도 있습니다. 조직이 모든 고객의 동의와 개인 정보 기본 설정을 존중하는 것이 중요합니다.  

Dynamics 365 Customer Insights는 Unified Customer Profiles의 일부로 선호도를 가져오고 저장하여 고객의 요청을 존중할 수 있도록 도와줍니다.

동의 데이터가 고객 프로필과 별도로 저장되는 경우 [동의 데이터를 새 데이터 원본으로 추가](#import-and-unify-consent-data)합니다. 동의 데이터가 포함된 데이터 원본이 데이터 통합 프로세스에 추가됩니다. 동의 데이터와 고객 프로필을 성공적으로 통합하면 동의 정보가 포함된 Unified Customer Profiles가 생성됩니다. 이미 동의 정보가 포함된 고객 프로필의 경우 [동의 데이터 사용](#use-consent-data) 섹션으로 직접 이동합니다.

## <a name="prerequisites"></a>전제 조건

동의 데이터를 다른 고객 프로필과 통합하려면 원본 데이터에서 다음 정보를 사용할 수 있어야 합니다.

- 대체 키 동의 정보를 Customer Insights의 사용자 프로필에 매핑합니다. 예를 들면 이메일 주소나 전화번호입니다.
- 고객의 동의 상태를 결정하기 위한 동의 값입니다.

다음 *선택적* 정보를 추가하는 것을 고려하세요.

- 고객이 변경을 요청하는 경우 동의 상태를 업데이트하기 위한 기본 키입니다.
- 고객 정보를 처리하는 방법이 두 가지 이상인 경우 동의 유형입니다.
- 동의 날짜 또는 동의 시나리오와 관련된 기타 유형의 데이터입니다.

여러 동의 옵션이 있는 단순 동의 데이터베이스의 예제 테이블:

|동의 ID(기본 키)   |이메일(대체 키)  |동의 옵션  |동의 값  |
|---------|---------|---------|---------|
|6    |  holly@contoso.com       |  뉴스레터       |  False       |
|2    |  holly@contoso.com       |  제품 업데이트       |  참       |
|3    |  frank@contoso.com       |  뉴스레터       | 참        |
|4    |  frank@contoso.com       |  제품 업데이트       |  False       |

## <a name="import-and-unify-consent-data"></a>동의 데이터 가져오기 및 통합

다른 데이터 소스를 Customer Insights로 수집하는 것과 동일한 방식으로 동의 데이터를 가져옵니다. 지원되는 데이터 원본 및 가져오는 방법에 대한 자세한 내용은 [데이터 원본 개요](data-sources.md)를 참조하세요.

데이터 원본 통합에 대한 자세한 내용은 [데이터 통합 개요](data-unification.md)를 참조하세요.

## <a name="use-consent-data"></a>동의 데이터 사용

동의 데이터가 Unified Customer Profiles의 일부가 되면 Customer Insights에서 사용할 수 있습니다. 예를 들어 고객의 개인 정보 및 데이터 보호 기본 설정을 준수하도록 하는 규칙이 있는 세그먼트를 만듭니다. 동의 기본 설정을 지원하는 규칙은 프로필 속성을 기반으로 세그먼트에서 사용자를 제외하는 데 사용됩니다. 연락받는 것을 동의하지 않은 고객 프로필을 제외하는 규칙을 세그먼트에 추가합니다.

위의 샘플 테이블을 참조하면 세그먼트에는 다음 규칙이 포함될 수 있습니다. `Consent option=Newsletter & Consent value=True` 이 구성은 연락처 기본 설정을 준수하여 뉴스레터를 보내는 세그먼트를 생성합니다.

세그먼트 작성에 대한 자세한 내용은 [세그먼트 생성](segment-builder.md)을 참조하세요.

세그먼트가 생성되면 많은 [내보내기 옵션](export-destinations.md) 중 하나를 사용하여 다른 애플리케이션에서 세그먼트를 사용할 수 있습니다.

## <a name="ensure-updated-consent-status"></a>업데이트된 동의 상태 유지

고객의 동의 상태를 최신 상태로 유지하는 것이 중요합니다. Customer Insights의 예약된 새로 고침은 항상 데이터 원본의 최신 상태를 가져옵니다. 그런 다음 이 정보는 데이터 통합을 통해 처리되고 업데이트된 고객 프로필이 생성됩니다. 그런 다음 업데이트된 프로필을 사용하여 최신 정보로 작업할 수 있도록 세그먼트를 새로 고칩니다.

즉, Customer Insights로 가져오는 소스 데이터에 항상 최신 정보가 있는지 확인하세요.

자세한 내용은 [수동으로 세그먼트 새로 고침](segments.md#refresh-segments) 또는 [예약된 새로 고침 구성](system.md#schedule-tab)을 참조하세요.

[!INCLUDE [footer-include](includes/footer-banner.md)]
