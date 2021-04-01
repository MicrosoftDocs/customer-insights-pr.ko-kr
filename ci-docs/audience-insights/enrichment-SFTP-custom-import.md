---
title: SFTP 사용자 지정 가져오기로 보강
description: SFTP 사용자 지정 가져오기 보강에 대한 일반 정보입니다.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d9e095ef793cbd25415864f76a541dce68fafe47
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595863"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="75392-103">사용자 지정 데이터로 고객 프로필 보강(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="75392-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="75392-104">SFTP(보안 파일 전송 프로토콜) 사용자 지정 가져오기를 사용하면 데이터 통합 프로세스를 거치지 않아도 되는 데이터를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75392-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="75392-105">데이터를 가져오는 유연하고 안전하며 쉬운 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="75392-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="75392-106">SFTP 사용자 지정 가져오기는 보강에 필요한 고객 프로필 데이터를 내보낼 수 있는 [SFTP 내보내기](export-sftp.md)와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75392-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="75392-107">그런 다음 데이터를 처리하고 보강할 수 있으며 SFTP 사용자 지정 가져오기를 사용하여 보강된 데이터를 다시 Dynamics 365 Customer Insights의 대상 그룹 인사이트 기능으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75392-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="75392-108">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="75392-108">Prerequisites</span></span>

<span data-ttu-id="75392-109">SFTP 사용자 지정 가져오기를 구성하려면 다음 전제 조건이 충족되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75392-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="75392-110">가져올 데이터가 있는 SFTP 위치에 대한 사용자 자격 증명(사용자 이름 및 암호)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75392-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="75392-111">STFP 호스트에 대한 URL 및 포트 번호(일반적으로 22)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75392-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="75392-112">SFTP 호스트에서 가져올 파일의 파일 이름과 위치가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75392-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="75392-113">가져올 데이터의 스키마를 지정하는 *model.json* 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75392-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="75392-114">이 파일은 가져올 파일과 동일한 디렉터리에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75392-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="75392-115">[관리자](permissions.md#administrator) 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75392-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="75392-116">구성</span><span class="sxs-lookup"><span data-stu-id="75392-116">Configuration</span></span>

1. <span data-ttu-id="75392-117">**데이터** > **보강** 으로 이동 후, **발견하기** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="75392-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="75392-118">**SFTP 사용자 지정 가져오기 타일** 에서 **내 데이터 보강을 선택** 합니다.</span><span class="sxs-lookup"><span data-stu-id="75392-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="75392-119">![사용자 지정 가져오기 타일](media/SFTP_Custom_Import_tile.png "사용자 지정 가져오기 타일")</span><span class="sxs-lookup"><span data-stu-id="75392-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="75392-120">**시작** 을 선택하고 SFTP 서버의 자격 증명과 주소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="75392-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="75392-121">예를 들어 sftp://mysftpserver.com:22입니다.</span><span class="sxs-lookup"><span data-stu-id="75392-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="75392-122">루트 폴더에 없는 경우 데이터가 포함된 파일의 이름과 SFTP 서버에 있는 파일 경로를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="75392-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="75392-123">**사용자 지정 가져오기에 연결** 을 선택하여 모든 입력을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="75392-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="75392-124">![SFTP 사용자 지정 가져오기 구성 플라이아웃](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP 사용자 지정 가져오기 구성 플라이아웃")</span><span class="sxs-lookup"><span data-stu-id="75392-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="75392-125">필드 매핑 정의</span><span class="sxs-lookup"><span data-stu-id="75392-125">Defining field mappings</span></span> 

<span data-ttu-id="75392-126">SFTP 서버에서 가져올 파일이 포함된 디렉터리에는 *model.json* 파일도 포함되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75392-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="75392-127">이 파일은 데이터를 가져오는 데 사용할 스키마를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="75392-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="75392-128">스키마에서 [Common Data Model](/common-data-model/)을 사용하여 필드 매핑을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75392-128">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="75392-129">model.json 파일의 간단한 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="75392-129">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="75392-130">보강 결과</span><span class="sxs-lookup"><span data-stu-id="75392-130">Enrichment results</span></span>

<span data-ttu-id="75392-131">강화 프로세스를 시작하려면 명령 모음에서.**실행** 을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="75392-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="75392-132">[예약된 새로 고침](system.md#schedule-tab)으로 시스템이 자동으로 보강을 실행하도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75392-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="75392-133">처리 시간은 가져올 데이터의 크기와 SFTP 서버에 대한 연결에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="75392-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="75392-134">보강 프로세스가 완료된 후 **내 보강** 에서 새로 가져온 사용자 지정 보강 데이터를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75392-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="75392-135">또한 마지막 업데이트 시간과 강화 된 프로필 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75392-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="75392-136">**보강된 데이터 보기** 를 선택하여 각 보강된 프로필의 상세 보기에 액세스할 수 있습니다 .</span><span class="sxs-lookup"><span data-stu-id="75392-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="75392-137">다음 단계</span><span class="sxs-lookup"><span data-stu-id="75392-137">Next steps</span></span>

<span data-ttu-id="75392-138">보강된 고객 데이터를 바탕으로 구축합니다.</span><span class="sxs-lookup"><span data-stu-id="75392-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="75392-139">[세그먼트](segments.md), [측정값](measures.md)을 만들고 [데이터를 내보내](export-destinations.md) 고객에게 개인화된 경험을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="75392-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]