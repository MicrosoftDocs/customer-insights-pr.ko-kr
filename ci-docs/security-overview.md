---
title: Dynamics 365 Customer Insights의 보안 설정
description: Dynamics 365 Customer Insights의 보안 설정에 대해 알아봅니다.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653738"
---
# <a name="security-overview-page"></a>보안 개요 페이지

**보안** 페이지에는 Dynamics 365 Customer Insights를 보다 안전하게 만드는 데 도움이 되는 사용자 권한 및 기능을 구성하는 옵션이 나열되어 있습니다. 관리자만 이 페이지에 액세스할 수 있습니다. 

**관리자** > **보안** 으로 이동하여 설정을 구성합니다.

**보안** 페이지에는 다음 탭이 포함됩니다.
- [사용자](#users-tab)
- [API](#apis-tab)
- [Key Vault](#key-vault-tab)

## <a name="users-tab"></a>사용자 탭

Customer Insights에 대한 액세스는 관리자가 애플리케이션에 추가한 조직의 사용자로 제한됩니다. **사용자** 탭을 사용하여 사용자 액세스 및 권한을 관리할 수 있습니다. 자세한 내용은 [사용자 권한](permissions.md)을 참조하십시오.

## <a name="apis-tab"></a>API 탭

[Customer Insights API](apis.md)를 사용하는 환경의 데이터로 키를 보고 관리합니다.

**기본 재생성** 또는 **보조 재생성** 을 선택하여 새 기본 키와 보조 키를 생성할 수 있습니다. 

환경에 대한 API 액세스를 차단하려면 **비활성화** 를 선택합니다. API가 비활성화된 경우 **활성화** 를 선택하여 액세스 권한을 다시 부여할 수 있습니다.

## <a name="key-vault-tab"></a>Key Vault 탭

**Key Vault** 탭을 사용하면 자신의 [Azure Key Vault](/azure/key-vault/general/basic-concepts)를 환경에 연결하고 관리할 수 있습니다.
전용 키 자격 증명 모음을 사용하여 조직의 규정 준수 경계에서 비밀을 준비하고 사용할 수 있습니다. Customer Insights는 Azure Key Vault의 비밀을 사용하여 타사 시스템에 대한 [연결을 설정](connections.md)할 수 있습니다.

자세한 내용은[ 고유한 Azure 키 자격 증명 모음 가져오기](use-azure-key-vault.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
