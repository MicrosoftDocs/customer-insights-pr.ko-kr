---
title: Dun & Bradstreet를 통한 회사 프로필 보강
description: Dun & Bradstreet 타사 보강에 대한 일반 정보입니다.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b1038970b6aee3bbdd7f79cc457f79aaf1c38222
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953899"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Dun & Bradstreet를 통한 회사 프로필 보강(프리뷰)

Dun & Bradstreet는 비즈니스를 위한 상업 데이터, 분석 및 인사이트를 제공합니다. 통합된 고객 프로필을 보유한 고객이 회사의 데이터를 보강할 수 있습니다. 보강에는 DUNS 번호, 회사 규모, 위치, 산업 등과 같은 특성이 포함됩니다.

## <a name="prerequisites"></a>전제 조건

- 활성 [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) 라이선스입니다.
- 기업을 위한 [Unified customer profiles](customer-profiles.md)입니다.
- Dun & Bradstreet [프로젝트](#set-up-your-dun--bradstreet-project)가 설정되었습니다.
- Dun & Bradstreet [연결](connections.md)은 관리자가 [구성](#configure-a-connection-for-dun--bradstreet)합니다.

## <a name="set-up-your-dun--bradstreet-project"></a>Dun & Bradstreet 프로젝트 설정

Dun & Bradstreet 라이선스 사용자는 [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights)에서 프로젝트를 설정할 수 있습니다.

1. [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights)에 로그인합니다. 자격 증명을 검색하려면 [비밀번호를 복원](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights)합니다.

1. Customer Insights 필드를 해당 Dun & Bradstreet 필드에 매핑하는 데 사용할 [csv 템플릿 파일](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv)을 다운로드합니다.

1. Dun & Bradstreet 프로젝트 생성 경험의 **데이터 업로드** 단계에서 파일을 업로드합니다.

1. 새로 생성된 Dun & Bradstreet 프로젝트에서 관련 **소스** 아래의 가로 점을 선택하여 사용 가능한 옵션을 확인합니다.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Dun & Bradstreet 프로젝트의 점 스크린샷.":::

1. **S3 세부 정보 가져오기** 를 선택합니다. 이 정보를 안전한 장소에 보관하십시오. Customer Insights에서 [보강을 위한 연결 설정](#configure-a-connection-for-dun--bradstreet)에 필요합니다.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Dun & Bradstreet 프로젝트의 s3 정보 선택 스크린샷.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Dun & Bradstreet에 대한 연결 구성

Customer Insights의 [관리자](permissions.md#admin)여야 하며 Dun & Bradstreet Connect의 자격 증명이 있어야 합니다.

1. 강화를 구성할 때 **연결 추가** 를 선택하거나 **관리** > **연결** 로 이동하고 Dun & Bradstreet 타일에서 **설정** 을 선택합니다.

1. 연결 이름을 입력합니다.

1. 유효한 Dun & Bradstreet 자격 증명 및 Dun & Bradstreet 프로젝트 세부 정보 *지역, 드롭 폴더 경로 및 드롭 폴더 이름* 을 입력하십시오. Dun & Bradstreet 프로젝트에서 [이 정보를 가져옵니다](#set-up-your-dun--bradstreet-project).

1. [데이터 개인 정보 보호 및 규정 준수](#data-privacy-and-compliance)를 검토하고 **동의함** 을 선택하여 동의를 제공합니다.

1. **확인** 을 선택하여 구성을 확인한 다음 **저장** 을 선택합니다.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Dun & Bradstreet 연결 구성 페이지.":::

### <a name="data-privacy-and-compliance"></a>데이터 프라이버시 및 규정 준수

Dynamics 365 Customer Insights에서 Dun & Bradstreet로 데이터를 전송하도록 설정하면 개인 데이터와 같이 잠재적으로 민감한 데이터를 포함하여 Dynamics 365 Customer Insights의 규정 준수 경계 외부로 데이터를 전송할 수 있습니다. Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 귀하는 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 Dun & Bradstreet가 충족하는지 확인할 책임이 있습니다. 자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.
Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 보강을 언제든지 제거할 수 있습니다.

## <a name="supported-countries-or-regions"></a>지원되는 국가 또는 지역

현재 지원되는 국가/지역 옵션: 캐나다(영어) 또는 미국(영어).

## <a name="configure-the-enrichment"></a>보강 구성

1. **데이터** > **보강** 으로 이동 후, **발견하기** 탭을 선택합니다.

1. Dun & Bradstreet의 **회사 데이터** 타일에서 **내 데이터 보강** 을 선택합니다.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Dun & Bradstreet 타일의 스크린샷.":::

1. 개요를 검토한 후 **다음** 을 선택합니다.

1. 연결을 선택하고 확인합니다. 관리자가 없는 경우 관리자에게 문의하세요.

1. **다음** 을 선택합니다.

1. **고객 데이터 세트** 를 선택하고 Dun & Bradstreet의 회사 데이터로 보강할 프로필 또는 세그먼트를 선택합니다. *고객* 엔터티는 모든 고객 프로필을 강화하는 반면 세그먼트는 해당 세그먼트에 포함된 고객 프로필만 강화합니다.

1. Dun & Bradstreet의 회사 데이터를 일치시키는 데 사용할 통합 프로필의 필드 유형을 정의합니다. **이름과 주소**, **전화** 또는 **이메일** 중 하나 이상이 필요합니다.

1. **다음** 선택

1. Dun & Bradstreet의 회사 데이터에 필드를 매핑합니다. **DUNS 번호** 또는 **회사명** 및 **국가** 필드는 필수 항목입니다.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Dun & Bradstreet 필드 매핑 창.":::

1. 필드 매핑을 완료하려면 **다음** 을 선택합니다.

1. 보강에 대한 **이름** 과 **출력 엔터티 이름** 을 제공합니다.

1. 선택 사항을 검토 한 후 **보강 저장** 을 선택합니다.

1. **실행** 을 선택하여 강화 프로세스를 시작하거나 닫기를 선택하여 **강화** 페이지로 돌아갑니다.

## <a name="enrichment-results"></a>보강 결과

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>다음 단계

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
