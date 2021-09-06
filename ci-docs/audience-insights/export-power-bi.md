---
title: Power BI 커넥터
description: Power BI에서 Dynamics 365 Customer Insights 커넥터 사용 방법 알아보기.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: a0ca431dbea839fe271cf3a512cd3a5dde6d920d396056e91b33bcf7ed84272a
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035515"
---
# <a name="connector-for-power-bi-preview"></a>Power BI용 커넥터(미리 보기)

Power BI Desktop을 사용하여 데이터에 대한 시각화를 만듭니다. 통일된 고객 데이터로 추가 인사이트를 생성하고 보고서를 작성합니다.

## <a name="prerequisites"></a>필요한 항목

- 통합 고객 프로필이 있습니다.
- [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/)의 최신 버전은 컴퓨터에 설치됩니다. [Power BI Desktop에 대해 자세히 알아보기](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Power BI용 커넥터 구성

1. Power BI Desktop에서 **파일** > **데이터 가져오기** 를 선택합니다.

1. **더 보기** 를 선택하고 **Dynamics 365 Customer Insights** 를 검색합니다.

1. **연결** 을 선택합니다.

1. Customer Insights에 사용하는 것과 동일한 조직 계정으로 **로그인** 하고 **연결** 을 선택합니다.
   > [!NOTE]
   > 이 단계에서 지정하는 계정은 Customer Insights에서 데이터를 가져오는 데 사용되며 Power BI과 같은 로그인 계정을 사용할 필요는 없습니다. 데이터 가져오기에 사용되는 계정을 재설정하려면 Power BI를 열고 **파일** > **옵션** > **설정** > **데이터 원본 설정** 으로 이동합니다. 데이터 소스 목록에서, **Dynamics 365 Customer Insights 로그인** 선택 후, **권한 지우기** 를 선택하십시오.  

1. **탐색기** 대화 상자에서. 액세스할 수 있는 모든 환경 목록이 표시됩니다. 환경을 확장하고 폴더(엔터티, 측정값, 세그먼트, 보강)를 엽니다. 예를 들어, 가져올 수 있는 모든 엔터티를 보려면 **엔터티** 폴더를 여세요.

   ![Power BI 커넥터 탐색기.](media/power-bi-navigator.png "Power BI 커넥터 탐색기")

1. 포함하고 **로드** 할 엔터티 옆의 확인란을 선택합니다. 여러 환경에서 여러 엔터티를 선택할 수 있습니다.

1. 엔터티가 로드되는 동안 로드 대화 상자가 나타납니다. 선택한 엔터티가 모두 로드되면 Power BI 데이터를 시각화하는 기능을 사용할 수 있습니다.

## <a name="large-data-sets"></a>대규모 데이터 세트

Power BI용 Customer Insights 커넥터는 최대 1백만 개의 고객 프로필을 포함하는 데이터 세트에서 작동하도록 설계되었습니다. 더 큰 데이터 세트를 가져 올 수는 있으나 시간이 오래 걸립니다. 또한 Power BI 한계상의 이유로 프로세스가 시간 제한에 걸릴 수 있습니다. 자세한 내용은 [Power BI : 대용량 데이터 세트에 대한 권장사항](/power-bi/admin/service-premium-what-is#large-datasets)을 참조하세요. 

### <a name="work-with-a-subset-of-data"></a>데이터 하위 집합으로 작업

데이터의 하위 집합으로 작업하는 것을 고려하십시오. 예를 들어 모든 고객 레코드를 Power BI로 내보내는 대신 [세그먼트](segments.md)를 만들 수 있습니다.

## <a name="troubleshooting"></a>문제 해결

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Power BI에 Customer Insights 환경이 표시되지 않음

대상 그룹 인사이트에서 동일한 두 엔터티 사이에 정의된 둘 이상의 [관계](relationships.md)를 가진 환경은 Power BI 커넥터에서 사용할 수 없습니다.

중복된 관계를 식별하고 제거할 수 있습니다.

1. 대상 그룹 인사이트의 Power BI에서 누락된 환경의 **데이터** > **관계** 로 이동합니다.
2. 중복된 관계 식별:
   - 동일한 두 엔터티 간에 정의된 관계가 두 개 이상 있는지 확인합니다.
   - 통합 프로세스에 모두 포함된 두 엔티티 간에 생성된 관계가 있는지 확인합니다. 통합 프로세스에 포함된 모든 엔티티 간에 정의된 암시적 관계가 있습니다.
3. 식별된 중복 관계를 제거하십시오.

중복된 관계를 제거한 후 Power BI 커넥터를 다시 구성해보십시오. 이제 환경을 사용할 수 있어야 합니다.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Power BI Desktop에서 엔터티를 로드할 때 날짜 필드 오류

MM/DD/YYYY와 같은 날짜 형식의 필드가 포함된 엔터티를 로드할 때 일치하지 않는 로케일 형식으로 인해 오류가 발생할 수 있습니다. 이 불일치는 대상 그룹 인사이트의 날짜 필드가 미국 형식으로 저장되기 때문에 Power BI Desktop 파일이 영어(미국)가 아닌 다른 로케일로 설정된 경우 발생합니다.

Power BI Desktop 파일에는 데이터를 검색할 때 적용되는 단일 로케일 설정이 있습니다. 이 날짜 필드를 올바르게 해석하려면 .BPI 파일의 로케일을 영어(미국)로 설정하십시오. [Power BI Desktop 파일의 로케일을 변경하는 방법 알아보기](/power-bi/fundamentals/supported-languages-countries-regions.md#choose-the-locale-for-importing-data-into-power-bi-desktop).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
