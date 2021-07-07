---
title: SFTP 사용자 지정 가져오기로 보강
description: SFTP 사용자 지정 가져오기 보강에 대한 일반 정보입니다.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f92b36ac5364ea8586f9cbba7ba03178641555c0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304658"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="f2413-103">사용자 지정 데이터로 고객 프로필 보강(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="f2413-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="f2413-104">SFTP(보안 파일 전송 프로토콜) 사용자 지정 가져오기를 사용하면 데이터 통합 프로세스를 거치지 않아도 되는 데이터를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2413-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="f2413-105">데이터를 가져오는 유연하고 안전하며 쉬운 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="f2413-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="f2413-106">SFTP 사용자 지정 가져오기는 보강에 필요한 고객 프로필 데이터를 내보낼 수 있는 [SFTP 내보내기](export-sftp.md)와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2413-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="f2413-107">그런 다음 데이터를 처리하고 보강할 수 있으며 SFTP 사용자 지정 가져오기를 사용하여 보강된 데이터를 다시 Dynamics 365 Customer Insights의 대상 그룹 인사이트 기능으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2413-107">The data can then be processed and enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f2413-108">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="f2413-108">Prerequisites</span></span>

<span data-ttu-id="f2413-109">SFTP 사용자 지정 가져오기를 구성하려면 다음 전제 조건이 충족되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2413-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="f2413-110">SFTP 호스트에서 가져올 파일의 이름과 위치(경로)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2413-110">You have the file name and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="f2413-111">가져올 데이터의 [Common Data Model 스키마](/common-data-model/)를 지정하는 *model.json* 파일이 있음.</span><span class="sxs-lookup"><span data-stu-id="f2413-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="f2413-112">이 파일은 가져올 파일과 동일한 디렉터리에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2413-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="f2413-113">관리자가 SFTP 연결을 이미 구성 *했거나* 귀하가 [관리자](permissions.md#administrator) 권한을 가지고 있음.</span><span class="sxs-lookup"><span data-stu-id="f2413-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="f2413-114">데이터를 가져올 SFTP 위치에 대한 사용자 자격 증명, URL 및 포트 번호.</span><span class="sxs-lookup"><span data-stu-id="f2413-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="f2413-115">가져오기 구성</span><span class="sxs-lookup"><span data-stu-id="f2413-115">Configure the import</span></span>

1. <span data-ttu-id="f2413-116">**데이터** > **보강** 으로 이동 후, **발견하기** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f2413-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="f2413-117">**SFTP 사용자 지정 가져오기 타일** 에서 **내 데이터 보강** 을 선택하고 **시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f2413-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP 사용자 지정 가져오기 타일":::

1. <span data-ttu-id="f2413-119">드롭다운 목록에서 [연결](connections.md)을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="f2413-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="f2413-120">사용 가능한 연결이 없으면 관리자에게 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="f2413-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="f2413-121">관리자인 경우 **연결 추가** 를 선택하고 드롭다운 목록에서 **SFTP 사용자 지정 가져오기** 를 선택하여 연결을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2413-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the dropdown list.</span></span>

1. <span data-ttu-id="f2413-122">**사용자 지정 가져오기 연결** 을 선택하여 선택한 연결을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f2413-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="f2413-123">**다음** 을 선택한 후 가져올 데이터 파일의 **경로** 및 **파일 이름** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f2413-123">Select **Next** and enter the **Path** and **Filename** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="데이터 위치 입력 시 스크린 샷.":::

1. <span data-ttu-id="f2413-125">**다음** 을 선택하고 보강 이름과 출력 엔터티 이름을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f2413-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="f2413-126">선택 사항을 검토 한 후 **보강 저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f2413-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="f2413-127">SFTP 사용자 지정 가져오기에 대한 연결 구성</span><span class="sxs-lookup"><span data-stu-id="f2413-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="f2413-128">연결을 구성하려면 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2413-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="f2413-129">보강을 구성할 때 **연결 추가** 를 선택 *하거나* **관리자** > **연결** 로 이동하여 사용자 지정 가져오기 타일에서 **설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f2413-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="f2413-130">**표시 이름** 상자에 연결 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f2413-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="f2413-131">가져올 데이터가 있는 SFTP 서버의 유효한 사용자 이름, 비밀번호 및 호스트 URL을 입력하십시오.</span><span class="sxs-lookup"><span data-stu-id="f2413-131">Enter a valid username, password, and host URL for the SFTP server that the data to be imported resides on.</span></span>

1. <span data-ttu-id="f2413-132">**동의함** 확인란을 선택하여 **데이터 개인 정보 및 규정 준수** 에 대한 동의를 검토하고 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f2413-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="f2413-133">**확인** 을 선택하여 구성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f2413-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="f2413-134">확인이 완료되면 **저장** 을 선택하여 연결을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2413-134">Once the verification has completed, the connection can be saved by selecting **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f2413-135">![Experian 연결 구성 페이지](media/enrichment-SFTP-connection.png "Experian 연결 구성 페이지")</span><span class="sxs-lookup"><span data-stu-id="f2413-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="f2413-136">필드 매핑 정의</span><span class="sxs-lookup"><span data-stu-id="f2413-136">Defining field mappings</span></span> 

<span data-ttu-id="f2413-137">SFTP 서버에서 가져올 파일이 포함된 디렉터리에는 *model.json* 파일도 포함되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2413-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="f2413-138">이 파일은 데이터를 가져오는 데 사용할 스키마를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f2413-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="f2413-139">스키마는 [Common Data Model](/common-data-model/)을 사용하여 필드 매핑을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2413-139">The schema has to use [Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="f2413-140">model.json 파일의 간단한 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f2413-140">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="f2413-141">보강 결과</span><span class="sxs-lookup"><span data-stu-id="f2413-141">Enrichment results</span></span>

<span data-ttu-id="f2413-142">강화 프로세스를 시작하려면 명령 모음에서.**실행** 을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="f2413-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="f2413-143">[예약된 새로 고침](system.md#schedule-tab)으로 시스템이 자동으로 보강을 실행하도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2413-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f2413-144">처리 시간은 가져올 데이터의 크기와 SFTP 서버에 대한 연결에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="f2413-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="f2413-145">보강 프로세스가 완료된 후 **내 보강** 에서 새로 가져온 사용자 지정 보강 데이터를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2413-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="f2413-146">또한 마지막 업데이트 시간과 강화 된 프로필 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2413-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="f2413-147">**보강된 데이터 보기** 를 선택하여 각 보강된 프로필의 상세 보기에 액세스할 수 있습니다 .</span><span class="sxs-lookup"><span data-stu-id="f2413-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f2413-148">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f2413-148">Next steps</span></span>

<span data-ttu-id="f2413-149">보강된 고객 데이터를 바탕으로 구축합니다.</span><span class="sxs-lookup"><span data-stu-id="f2413-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="f2413-150">[세그먼트](segments.md) 및 [측정값](measures.md)을 만들고 [데이터 내보내기](export-destinations.md) 를 통해 고객에게 개인화된 경험을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f2413-150">Create [segments](segments.md) and [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
