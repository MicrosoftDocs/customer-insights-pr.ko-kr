---
title: 방법 - 환경 관리
description: 기존 Customer Insights 환경을 관리자로 관리하는 방법을 알아봅니다.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 62a5856edac5e66e5e42c93313d78fa6826469b3
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833500"
---
# <a name="how-to-manage-environments"></a>방법: 환경 관리

관리자는 환경을 [만들고](create-environment.md) 관리합니다. 기존 환경에서 일부 설정을 변경할 수 있습니다. 비즈니스, 유형, 지역, 스토리지 옵션 및 Dataverse 설정은 환경 생성 후 고정됩니다. 이러한 설정을 변경하려면 환경을 재설정하거나 새 환경을 만드십시오.

## <a name="edit-an-existing-environment"></a>기존 환경 편집

기존 환경의 세부 사항 중 일부를 편집할 수 있습니다.

1. 앱 헤더의 **환경** 선택기를 선택합니다.

1. **편집** 아이콘을 선택합니다.

   :::image type="content" source="media/edit-environment.png" alt-text="환경 설정을 편집하는 아이콘.":::

1. **환경 편집** 상자에서 환경 설정을 업데이트할 수 있습니다.

새로운 환경을 시작하려면 [새 환경 만들기](create-environment.md)를 참조하십시오.

## <a name="change-the-owner-of-an-environment"></a>환경 담당자 변경

여러 사용자가 관리자 권한을 가질 수 있지만 한 명의 사용자만 환경의 담당자가 됩니다. 기본적으로 처음에 환경을 만드는 사람이 관리자입니다. 환경의 관리자는 관리자 권한이 있는 다른 사용자에게 소유권을 할당할 수 있습니다.

1. 앱 헤더의 **환경** 선택기를 선택합니다.

1. **편집** 아이콘을 선택합니다.

1. **환경 편집** 상자에서 **기본 정보** 단계로 이동합니다.

1. **환경 담당자 변경** 필드에서 환경의 새 담당자를 선택합니다.  

1. **검토 및 완료** 를 선택한 다음 **업데이트** 를 선택하여 변경 사항을 적용합니다.

## <a name="claim-ownership-of-an-environment"></a>환경 소유권 주장

담당자의 사용자 계정이 삭제되거나 일시 중지되면 환경에 담당자가 없게 됩니다. 모든 관리 사용자는 소유권을 주장하고 새 담당자가 될 수 있습니다. 해당 사용자는 계속해서 환경을 소유하거나 [소유권을 다른 관리자에게로 변경할 수 있습니다](#change-the-owner-of-an-environment).

소유권을 주장하려면 원래 담당자가 조직을 떠날 때 Customer Insights의 모든 페이지 상단에 표시되는 **소유권 확보** 단추를 선택합니다.

## <a name="reset-an-existing-environment-preview"></a>기존 환경 재설정(프리뷰)

환경 담당자는 모든 구성을 삭제하고 수집된 데이터를 제거하려는 경우 환경을 빈 상태로 재설정할 수 있습니다.

1. 앱 헤더의 **환경** 선택기를 선택합니다.

1. 재설정하려는 환경을 선택하고 세로 줄임표(&vellip;)를 선택합니다.

1. **재설정** 옵션을 선택합니다.

   :::image type="content" source="media/reset-environment.png" alt-text="환경을 재설정하도록 제어합니다.":::

1. 전체 환경, 데이터 원본을 제외한 모든 항목 또는 Unified customer profile 상단에 구성된 모든 항목을 재설정할지 여부를 선택합니다.

1. 확인하려면 환경 이름을 입력하고 **재설정** 을 선택합니다.

## <a name="delete-an-existing-environment"></a>기존 환경 삭제

환경 담당자는 관리하는 환경을 삭제할 수 있습니다.

1. 앱 헤더의 **환경** 선택기를 선택합니다.

1. 재설정하려는 환경을 선택하고 세로 줄임표(&vellip;)를 선택합니다. 

1. **삭제** 옵션을 선택합니다.

   :::image type="content" source="media/delete-environment.png" alt-text="환경 삭제 제어":::

1. 삭제를 확인하려면 환경 이름을 입력하고 **삭제** 를 선택합니다.

> [!IMPORTANT]
> 환경을 삭제해도 Dataverse 환경에 대한 연결은 제거되지 않습니다. 앞으로 동일한 Dataverse 환경을 새로운 Customer Insights 환경에 연결할 계획이라면 해당 연결을 제거해야 합니다. [Dataverse 환경에 대한 기존 연결 제거](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment) 방법을 알아보십시오.

[!INCLUDE [footer-include](includes/footer-banner.md)]
