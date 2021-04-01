---
title: Customer Insights 데이터를 SFTP 호스트로 내보냅니다.
description: SFTP 호스트에 대한 연결을 구성하는 방법 알아보기.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598393"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="c4adc-103">SFTP용 커넥터(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="c4adc-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="c4adc-104">고객 데이터를 SFTP(보안 파일 전송 프로토콜) 호스트로 내보내 타사 애플리케이션에서 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c4adc-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c4adc-105">필요한 항목</span><span class="sxs-lookup"><span data-stu-id="c4adc-105">Prerequisites</span></span>

- <span data-ttu-id="c4adc-106">SFTP 호스트 및 해당 자격 증명의 가용성.</span><span class="sxs-lookup"><span data-stu-id="c4adc-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="c4adc-107">SFTP에 연결</span><span class="sxs-lookup"><span data-stu-id="c4adc-107">Connect to SFTP</span></span>

1. <span data-ttu-id="c4adc-108">**관리자** > **내보내기 대상** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c4adc-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c4adc-109">**SFTP** 아래에서 **설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c4adc-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="c4adc-110">**표시 이름** 필드에서 대상에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c4adc-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="c4adc-111">**사용자 이름**, **암호**, **호스트 이름** 및 **내보내기 폴더** 를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c4adc-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="c4adc-112">**확인** 을 선택해 연결을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="c4adc-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="c4adc-113">성공적으로 확인한 후 데이터를 **압축** 또는 **압축 해제** 하여 내보낼지 선택하고 내보낸 파일에 대한 **필드 구분자** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c4adc-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="c4adc-114">**동의** 를 선택해 **데이터 프라이버시 및 규정 준수** 를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c4adc-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c4adc-115">**다음** 을 선택해 내보내기 구성을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c4adc-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="c4adc-116">내보내기 구성</span><span class="sxs-lookup"><span data-stu-id="c4adc-116">Configure the export</span></span>

1. <span data-ttu-id="c4adc-117">내보내려는 엔터티(예: 세그먼트)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c4adc-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c4adc-118">선택한 각 엔터티는 내보낼 때 최대 5개의 출력 파일이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4adc-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="c4adc-119">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c4adc-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c4adc-120">데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="c4adc-120">Export the data</span></span>

<span data-ttu-id="c4adc-121">[주문 시 데이터를 내보낼](export-destinations.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4adc-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="c4adc-122">내보내기는 [예약된 새로 고침](system.md#schedule-tab)마다 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4adc-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c4adc-123">알려진 제한 사항</span><span class="sxs-lookup"><span data-stu-id="c4adc-123">Known limitations</span></span>

- <span data-ttu-id="c4adc-124">내보내기 런타임은 시스템 성능에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="c4adc-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="c4adc-125">서버의 최소 구성으로 2개의 CPU 코어와 1Gb의 메모리를 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="c4adc-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="c4adc-126">2개의 CPU 코어와 1Gb 메모리의 권장 최소 구성을 사용하면 최대 1억 개의 고객 프로필이 있는 엔터티를 내보내는 데 90분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4adc-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c4adc-127">데이터 프라이버시 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="c4adc-127">Data privacy and compliance</span></span>

<span data-ttu-id="c4adc-128">Dynamics 365 Customer Insights를 사용하여 SFTP를 통해 데이터를 전송하는 경우 Dynamics 365 Customer Insights규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4adc-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c4adc-129">Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 내보내기 대상이 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4adc-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c4adc-130">자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c4adc-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c4adc-131">Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4adc-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]