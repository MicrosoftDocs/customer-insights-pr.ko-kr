---
title: Customer Insights 데이터를 SFTP 호스트로 내보냅니다.
description: SFTP 호스트에 대한 연결을 구성하는 방법 알아보기.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643511"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="e2607-103">SFTP용 커넥터(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="e2607-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="e2607-104">고객 데이터를 SFTP(보안 파일 전송 프로토콜) 호스트로 내보내 타사 애플리케이션에서 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e2607-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e2607-105">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="e2607-105">Prerequisites</span></span>

- <span data-ttu-id="e2607-106">SFTP 호스트 및 해당 자격 증명의 가용성.</span><span class="sxs-lookup"><span data-stu-id="e2607-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="e2607-107">SFTP에 연결</span><span class="sxs-lookup"><span data-stu-id="e2607-107">Connect to SFTP</span></span>

1. <span data-ttu-id="e2607-108">**관리자** > **내보내기 대상** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e2607-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e2607-109">**SFTP** 아래에서 **설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2607-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="e2607-110">**표시 이름** 필드에서 대상에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2607-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="e2607-111">SFTP 계정의 **사용자 이름**, **암호** 및 **호스트 이름** 을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e2607-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="e2607-112">예: SFTP 서버의 루트 폴더가 /root/folder이고 데이터를 /root/folder/ci_export_destination_folder로 내보내려는 경우 호스트는 sftp://<server_address>/ci_export_destination_folder"여야합니다.</span><span class="sxs-lookup"><span data-stu-id="e2607-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="e2607-113">**확인** 을 선택해 연결을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="e2607-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="e2607-114">확인 후 데이터 **압축** 또는 **압축 해제** 하여 내보낼지 여부를 선택하고 내보낸 파일의 **필드 구분 기호** 를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="e2607-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="e2607-115">**동의** 를 선택해 **데이터 프라이버시 및 규정 준수** 를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e2607-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e2607-116">**다음** 을 선택해 내보내기 구성을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="e2607-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="e2607-117">연결 구성</span><span class="sxs-lookup"><span data-stu-id="e2607-117">Configure the connection</span></span>

1. <span data-ttu-id="e2607-118">내보낼 **고객 특성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2607-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="e2607-119">하나 이상의 특성을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2607-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="e2607-120">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2607-120">Select **Next**.</span></span>

1. <span data-ttu-id="e2607-121">내보낼 세그먼트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2607-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="e2607-122">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2607-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="e2607-123">데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="e2607-123">Export the data</span></span>

<span data-ttu-id="e2607-124">[주문 시 데이터를 내보낼](export-destinations.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2607-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="e2607-125">내보내기는 [예약된 새로 고침](system.md#schedule-tab)마다 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2607-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e2607-126">데이터 프라이버시 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="e2607-126">Data privacy and compliance</span></span>

<span data-ttu-id="e2607-127">Dynamics 365 Customer Insights를 사용하여 SFTP를 통해 데이터를 전송하는 경우 Dynamics 365 Customer Insights규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2607-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e2607-128">Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 내보내기 대상이 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2607-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e2607-129">자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2607-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e2607-130">Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2607-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
