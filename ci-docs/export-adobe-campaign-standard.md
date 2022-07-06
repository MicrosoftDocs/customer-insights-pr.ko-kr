---
title: Adobe Campaign Standard로 Customer Insights 세그먼트 내보내기(프리뷰)
description: Adobe Campaign Standard에서 Customer Insights 세그먼트를 사용하는 방법에 대해 알아보십시오.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 9915591cd969bf825f5d1669de43ed4f9953f898
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081344"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Adobe Campaign Standard로 Customer Insights 세그먼트 내보내기(프리뷰)

Dynamics 365 Customer Insights의 사용자는 관련 대상 그룹을 타겟팅하여 마케팅 캠페인을 보다 효율적으로 만들기 위해 세그먼트를 생성했을 수 있습니다. Adobe Experience Platform 및 Adobe Campaign Standard와 같은 애플리케이션에서 Customer Insights의 세그먼트를 사용하려면 이 문서에 설명된 몇 가지 단계를 따라야 합니다.

:::image type="content" source="media/ACS-flow.png" alt-text="이 문서에 설명된 단계의 프로세스 다이어그램입니다.":::

## <a name="prerequisites"></a>필수 조건

- Dynamics 365 Customer Insights 라이선스
- Adobe Campaign Standard 라이선스
- Azure Blob Storage 계정

## <a name="campaign-overview"></a>캠페인 개요

Adobe Experience Platform에서 Customer Insights의 세그먼트를 사용하는 방법을 더 잘 이해하기 위해 가상의 샘플 캠페인을 살펴보겠습니다.

귀사가 미국 고객에게 월간 구독 기반 서비스를 제공한다고 가정합시다. 다음 8일 이내에 구독을 갱신해야 하지만 아직 갱신하지 않은 고객을 식별하려고 합니다. 이러한 고객을 유지하기 위해 Adobe Campaign Standard를 사용하여 이메일을 통해 프로모션 제안을 보내려고 합니다.

이 예에서는 프로모션 이메일 캠페인을 한 번 실행하려고 합니다. 이 문서에서는 캠페인을 두 번 이상 실행하는 사용 사례를 다루지 않습니다. 그러나 Customer Insights 및 Adobe Campaign Standard는 반복되는 캠페인 시나리오에서도 작동하도록 구성할 수 있습니다.

## <a name="identify-your-target-audience"></a>목표 대상 그룹 식별

이 시나리오에서는 고객의 이메일 주소를 사용할 수 있고 고객의 판촉 기본 설정을 분석하여 해당 세그먼트의 구성원을 식별한다고 가정합니다.

[Customer Insights에서 정의한 세그먼트](segments.md)는 **ChurnProneCustomers** 라고 하며 이러한 고객에게 프로모션 이메일을 보낼 계획입니다.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ChurnProneCustomers 세그먼트가 만들어진 세그먼트 페이지의 스크린샷입니다.":::

보내려는 제안 이메일에는 이름, 성, 및 고객의 구독 종료 날짜가 포함됩니다. 구독이 끝나기 전에 갱신하면 받을 수 있는 할인을 고객에게 알려줍니다.

## <a name="export-your-target-audience"></a>목표 대상 그룹 내보내기

### <a name="configure-a-connection"></a>연결 구성

대상 대상 그룹이 식별되면 Azure Blob Storage 계정으로 내보내기를 구성할 수 있습니다.

1. Customer Insights에서 **관리자** > **연결** 로 이동합니다.

1. **연결 추가** 를 선택하고 **Adobe Campaign** 을 선택하여 연결을 구성하거나 **Adobe Campaign** 타일에서 **설정** 을 선택합니다.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Adobe Campaign Standard용 구성 타일.":::

1. **표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다. 이름 및 연결 유형은 이 연결을 설명합니다. 이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.

1. 이 연결을 사용할 수 있는 사용자를 선택합니다. 아무 조치도 취하지 않으면 기본값은 관리자입니다. 자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.

1. 세그먼트를 내보낼 Azure Blob Storage 계정의 **계정 이름**, **계정 키** 및 **컨테이너** 를 입력합니다.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="스토리지 계정 구성의 스크린샷입니다."::: 

   - Azure Blob Storage 계정 이름 및 계정 키를 찾는 방법에 대한 자세한 내용은 [Azure Portal에서 저장소 계정 설정 관리](/azure/storage/common/storage-account-manage)를 참조하십시오.

   - 컨테이너를 만드는 방법을 배우려면 [컨테이너 만들기](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)를 참조하세요.

1. 연결을 완료하려면 **저장** 을 선택합니다.

### <a name="configure-an-export"></a>내보내기 구성

이 유형의 연결에 대한 액세스 권한이 있는 경우 이 내보내기를 구성할 수 있습니다. 자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.

1. **데이터** > **내보내기** 로 이동합니다.

1. **내보내기 추가** 를 선택하여 새 내보내기를 만듭니다.

1. **내보내기 연결** 필드에서 Adobe Campaign 섹션에서 연결을 선택합니다. 이 섹션 이름이 표시되지 않으면 이 유형의 연결을 사용할 수 없습니다.

1. 내보낼 세그먼트를 선택하십시오. 이 예에서는 **ChurnProneCustomers** 입니다.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="ChurnProneCustomers 세그먼트가 선택된 세그먼트 선택 사용자 인터페이스의 스크린샷입니다.":::

1. **다음** 을 선택합니다.

1. 이제 Customer Insights 세그먼트의 **원본** 필드를 Adobe Campaign Standard 프로필 스키마의 **대상** 필드 이름에 매핑합니다.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Adobe Campaign Standard 커넥터에 대한 필드 매핑.":::

   더 많은 특성을 추가하려면 **특성 추가** 를 선택합니다. 대상 이름은 원본 필드 이름과 다를 수 있으므로 두 시스템에서 필드의 이름이 동일하지 않은 경우 Customer Insights의 세그먼트 출력을 Adobe Campaign Standard에 계속 매핑할 수 있습니다.

   > [!NOTE]
   > 이메일 주소는 ID 필드로 사용되지만 고객 프로필의 다른 식별자를 사용하여 데이터를 Adobe Campaign Standard에 매핑할 수 있습니다.

1. **저장** 을 선택합니다.

내보내기 대상을 저장한 후 **데이터** > **내보내기** 에서 확인합니다.

이제 [필요에 따라 세그먼트 내보내기](export-destinations.md#run-exports-on-demand)를 할 수 있습니다. 내보내기는 [예약된 새로 고침](system.md)마다 실행됩니다.

> [!NOTE]
> 내보낸 세그먼트의 레코드 수가 Adobe Campaign Standard 라이선스의 허용 한도 내에 있는지 확인하십시오.

내보낸 데이터는 위에서 구성한 Azure Blob Storage 컨테이너에 저장됩니다. 컨테이너에 다음 폴더 경로가 자동으로 만들어집니다.

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

예: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Adobe Campaign Standard 구성

내보낸 세그먼트에는 이전 단계에서 내보내기 대상을 정의하는 동안 선택한 열이 포함됩니다. 이 데이터는 [Adobe Campaign Standard에서 프로필 만들기](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles)에 사용할 수 있습니다.

Adobe Campaign Standard에서 세그먼트를 사용하려면 두 개의 추가 필드를 포함하도록 Adobe Campaign Standard의 프로필 스키마를 확장해야 합니다. Adobe Campaign Standard의 새 필드를 사용하여 [프로필 리소스를 확장](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing)하는 방법을 알아봅니다.

이 예에서 이러한 필드는 *세그먼트 이름 및 세그먼트 날짜(선택 사항)* 입니다.

이 필드를 사용하여 이 캠페인에 대해 타겟팅하려는 Adobe Campaign Standard의 프로필을 식별합니다.

Adobe Campaign Standard에 가져올 레코드 외에 다른 레코드가 없는 경우 이 단계를 건너뛸 수 있습니다.

## <a name="import-data-into-adobe-campaign-standard"></a>Adobe Campaign Standard로 데이터 가져오기

이제 모든 것이 준비되었으므로 프로필을 만들기 위해 Customer Insights에서 Adobe Campaign Standard로 준비된 대상 그룹 데이터를 가져와야 합니다. 워크플로를 사용하여 [Adobe Campaign Standard에서 프로필을 가져오는 방법](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences)에 대해 알아봅니다.

아래 이미지의 가져오기 워크플로는 8시간마다 실행되고 내보낸 Customer Insights 세그먼트(Azure Blob Storage의 .csv 파일)를 찾도록 구성되었습니다. 워크플로는 지정된 열 순서로 .csv 파일 콘텐츠를 추출합니다. 이 워크플로는 기본 오류 처리를 수행하고 Adobe Campaign Standard에서 데이터를 하이드레이팅하기 전에 각 레코드에 이메일 주소가 있는지 확인하도록 구축되었습니다. 또한 워크플로는 Adobe Campaign Standard 프로필 데이터로 업데이트하기 전에 파일 이름에서 세그먼트 이름을 추출합니다.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Adobe Campaign Standard 사용자 인터페이스의 가져오기 워크플로 스크린샷.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Adobe Campaign Standard에서 대상 그룹 검색

데이터를 Adobe Campaign Standard로 가져오면 *세그먼트 이름* 및 *세그먼트 날짜* 를 기반으로 [워크플로 만들기](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) 및 [쿼리](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data)하여 샘플 캠페인에 대해 식별된 프로필을 선택할 수 있습니다.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Adobe Campaign Standard를 사용하여 이메일 작성 및 보내기

이메일 콘텐츠를 만든 다음 내 이메일을 [테스트 및 전송](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages)합니다.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard의 갱신 제안이 포함된 샘플 이메일.":::
