---
title: Dun & Bradstreet를 통한 회사 프로필 보강
description: Dun & Bradstreet 타사 보강에 대한 일반 정보입니다.
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c738c2657d4cda213342629156ddc8104366bd8a
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755408"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Dun & Bradstreet를 통한 회사 프로필 보강(프리뷰)

Dun & Bradstreet는 비즈니스를 위한 상업 데이터, 분석 및 인사이트를 제공합니다. 통합된 고객 프로필을 보유한 고객이 회사의 데이터를 보강할 수 있습니다. 보강에는 DUNS 번호, 회사 규모, 위치, 산업 등과 같은 특성이 포함됩니다.

## <a name="prerequisites"></a>전제 조건

Dun & Bradstreet 보강을 구성하려면 다음 전제 조건이 충족되어야 합니다.

- 활성 [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) 라이선스가 있어야 합니다.
- 회사의 [통합 고객 프로필](customer-profiles.md)을 갖고 있습니다.
- Dun & Bradstreet [연결](connections.md)은 관리자가 구성합니다. [관리자](permissions.md#admin) 권한과 Dun & Bradstreet Connect의 자격 증명이 있는 경우 생성할 수 있습니다.

## <a name="setting-up-your-dun--bradstreet-project"></a>Dun & Bradstreet 프로젝트 설정

Dun & Bradstreet 라이선스 사용자는 [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights)에서 프로젝트를 설정할 수 있습니다.


1. [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights)에 로그인합니다. 자격 증명을 검색하려면 [비밀번호를 복원](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights)합니다.

1. Customer Insights 필드를 해당 Dun & Bradstreet 필드에 매핑하는 데 사용할 [csv 템플릿 파일](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv)을 다운로드합니다.

1. Dun & Bradstreet 프로젝트 생성 경험의 **데이터 업로드** 단계에서 파일을 업로드합니다.

1. 새로 생성된 Dun & Bradstreet 프로젝트에서 관련 **소스** 아래의 가로 점을 선택하여 사용 가능한 옵션을 확인합니다.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Dun & Bradstreet 프로젝트의 점 스크린샷.":::

1. **S3 세부 정보 가져오기** 를 선택합니다. 이 정보를 안전한 장소에 보관하십시오. Customer Insights에서 [보강을 위한 연결 설정](#configure-a-connection-for-dun--bradstreet)에 필요합니다.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Dun & Bradstreet 프로젝트의 s3 정보 선택 스크린샷.":::

## <a name="configure-the-enrichment"></a>보강 구성

1. **데이터** > **보강** 으로 이동합니다.

1. Dun & Bradstreet 타일에서 **내 데이터 보강** 을 선택하고 **시작** 을 선택합니다.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Dun & Bradstreet 타일의 스크린샷.":::

1. 드롭다운 목록에서 [연결](connections.md)을 선택하십시오. 사용 가능한 연결이 없으면 관리자에게 문의하십시오. 관리자인 경우 연결을 만들 수 있습니다. **연결 추가** 를 선택하고 **Dun & Bradstreet** 를 선택합니다.

1. **Dun & Bradstreet에 연결** 을 선택하여 연결을 확인합니다.

1. **다음** 을 선택하고 Dun & Bradstreet의 회사 데이터로 보강하려는 **고객 데이터 세트** 를 선택합니다. **고객 엔터티** 를 선택하여 모든 고객 프로필을 보강하거나 세그먼트 엔터티를 선택하여 해당 세그먼트에 포함된 통합 고객 프로필만 보강할 수 있습니다.

1. **다음** 을 ​​선택하고 Dun & Bradstreet에서 일치하는 회사 데이터를 찾는 데 사용되는 통합 프로필의 필드를 정의합니다. **DUNS 번호** 또는 **회사명** 및 **국가** 필드는 필수 항목입니다. 국가 필드는 [두세 글자 국가 코드](https://www.iso.org/iso-3166-country-codes.html), 영어 국가명, 모국어 국가명, 국제전화 국가코드를 지원합니다. 몇 가지 일반적인 국가 변형은 다음과 같습니다.

- US: United States of America, United States, USA, America.
- CA: Canada.
- GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain.
- AU: Australia, Commonwealth of Australia.
- FR: France, French Republic.
- DE: Germany, German, Deutschland, Allemagne, Federal Republic of Germany, Republic of Germany.

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Dun & Bradstreet 필드 매핑 창.":::

1. 필드 매핑을 완료하려면 **다음** 을 선택합니다.

1. 보강에 대한 이름을 제공하고 선택 사항을 검토한 후 **보강 저장** 을 선택합니다.

## <a name="configure-a-connection-for-dun--bradstreet"></a>Dun & Bradstreet에 대한 연결 구성

연결을 구성하려면 관리자여야 합니다. 보강을 구성할 때 **연결 추가** 를 선택 *또는* **관리자** > **연결** 로 이동하고 Dun & Bradstreet 타일에서 **설정** 을 선택합니다.

1. **시작** 을 선택합니다.

1. **표시 이름** 상자에 연결 이름을 입력합니다.

1. 유효한 Dun & Bradstreet 자격 증명 및 Dun & Bradstreet 프로젝트 세부 정보 *지역, 드롭 폴더 경로 및 드롭 폴더 이름* 을 입력하십시오. Dun & Bradstreet 프로젝트에서 [이 정보를 가져옵니다](#setting-up-your-dun--bradstreet-project).

1. **데이터 개인 정보 보호 및 규정 준수** 를 검토하고 **동의함** 을 선택하여 동의를 제공합니다.

1. **확인** 을 선택하여 구성을 확인합니다.

1. 확인을 완료한 후 **저장** 을 선택합니다.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Dun & Bradstreet 연결 구성 페이지.":::

## <a name="enrichment-results"></a>보강 결과

보강을 새로 고친 후 [내 보강](enrichment-hub.md) 아래에서 새로 보강된 회사 데이터를 검토할 수 있습니다. 마지막 업데이트 시간과 보강된 프로필 수를 찾을 수 있습니다.

**보강된 데이터 보기** 를 선택하여 각 보강된 프로필의 상세 보기에 액세스할 수 있습니다 .

## <a name="next-steps"></a>다음 단계

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>데이터 프라이버시 및 규정 준수

Dynamics 365 Customer Insights에서 Dun & Bradstreet로 데이터를 전송하도록 설정하면 개인 데이터와 같이 잠재적으로 민감한 데이터를 포함하여 Dynamics 365 Customer Insights의 규정 준수 경계 외부로 데이터를 전송할 수 있습니다. Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 귀하는 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 Dun & Bradstreet가 충족하는지 확인할 책임이 있습니다. 자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.
Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 보강을 언제든지 제거할 수 있습니다.

[!INCLUDE[footer-include](includes/footer-banner.md)]
