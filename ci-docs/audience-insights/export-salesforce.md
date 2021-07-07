---
title: Salesforce Marketing Cloud로 Customer Insights 데이터 내보내기
description: 연결을 구성하고 Salesforce Marketing Cloud로 내보내는 방법을 알아봅니다.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314639"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="dd54c-103">Salesforce Marketing Cloud로 세그먼트 및 기타 데이터 내보내기(프리뷰)</span><span class="sxs-lookup"><span data-stu-id="dd54c-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="dd54c-104">SFTP(Secure File Transfer Protocol) 위치를 통해 내보냄으로써 Salesforce Marketing Cloud에서 고객 데이터를 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="dd54c-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="dd54c-105">연결을 위한 전제 조건</span><span class="sxs-lookup"><span data-stu-id="dd54c-105">Prerequisites for connection</span></span>

- <span data-ttu-id="dd54c-106">SFTP 호스트 및 해당 관리자 자격 증명의 가용성.</span><span class="sxs-lookup"><span data-stu-id="dd54c-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="dd54c-107">Salesforce Marketing Cloud에 대한 SFTP 위치를 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="dd54c-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="dd54c-108">알려진 제한 사항</span><span class="sxs-lookup"><span data-stu-id="dd54c-108">Known limitations</span></span>

- <span data-ttu-id="dd54c-109">내보내기 런타임은 시스템 성능에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="dd54c-110">서버의 최소 구성으로 2개의 CPU 코어와 1Gb의 메모리를 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="dd54c-111">권장되는 최소 구성을 사용하는 경우 최대 1억 개의 고객 프로필이 있는 항목을 내보내는 데 90분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="dd54c-112">Salesforce Marketing Cloud에 대한 연결 설정</span><span class="sxs-lookup"><span data-stu-id="dd54c-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="dd54c-113">**관리자** > **연결** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="dd54c-114">**연결 추가** 를 선택하고 **Salesforce Marketing Cloud** 를 선택하여 연결을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="dd54c-115">**표시 이름** 필드에서 연결에 인식할 수 있는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="dd54c-116">이름 및 연결 유형은 이 연결을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="dd54c-117">이 연결의 목적과 대상을 설명하는 이름을 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="dd54c-118">이 연결을 사용할 수 있는 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-118">Choose who can use this connection.</span></span> <span data-ttu-id="dd54c-119">아무 조치도 취하지 않으면 기본값은 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="dd54c-120">자세한 내용은 [기여자가 내보내기에 연결을 사용하도록 허용](connections.md#allow-contributors-to-use-a-connection-for-exports)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="dd54c-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="dd54c-121">**사용자 이름**, **암호**, **호스트 이름** 및 **내보내기 폴더** 를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="dd54c-122">**확인** 을 선택해 연결을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="dd54c-123">**동의** 를 선택해 **데이터 프라이버시 및 규정 준수** 를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="dd54c-124">연결을 완료하려면 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="dd54c-125">내보내기 구성</span><span class="sxs-lookup"><span data-stu-id="dd54c-125">Configure an export</span></span>

<span data-ttu-id="dd54c-126">이 유형의 연결에 대한 액세스 권한이 있는 경우 이 내보내기를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="dd54c-127">자세한 내용은 [내보내기를 구성하는 데 필요한 권한](export-destinations.md#set-up-a-new-export)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dd54c-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="dd54c-128">**데이터** > **내보내기** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="dd54c-129">**대상 추가** 를 선택하여 새 내보내기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="dd54c-130">**내보내기 연결** 필드의 SFTP 섹션에서 연결을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="dd54c-131">이 섹션 이름이 표시되지 않으면 사용 가능한 이 유형의 연결이 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="dd54c-132">내보낼 데이터의 상태를 **GZipped** 또는 **압축 해제** 중에서 선택하고 내보낸 파일의 **필드 구분자** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="dd54c-133">내보내려는 엔터티(예: 세그먼트)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="dd54c-134">선택한 각 엔터티는 내보낼 때 최대 5개의 출력 파일로 분할됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="dd54c-135">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-135">Select **Save**.</span></span>

<span data-ttu-id="dd54c-136">내보내기를 저장해도 내보내기가 즉시 실행되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="dd54c-137">내보내기는 모든 [예약된 새로 고침](system.md#schedule-tab)에 따라 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="dd54c-138">[주문형으로 데이터를 내보낼](export-destinations.md#run-exports-on-demand)수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="dd54c-139">SFTP 위치에서 Salesforce Marketing Cloud로 Customer Insights 데이터 가져오기</span><span class="sxs-lookup"><span data-stu-id="dd54c-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="dd54c-140">[Salesforce Marketing Cloud에서 데이터 확장](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5)을 만들어 SFTP 위치에서 Customer Insights 데이터 파일을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="dd54c-141">[SFTP 위치에서](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) Salesforce Marketing Cloud 데이터 확장에 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="dd54c-142">데이터를 데이터 확장으로 가져오도록 자동화를 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="dd54c-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="dd54c-143">[파일 드롭 자동화 및 예약된 자동화](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="dd54c-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="dd54c-144">[파일 드롭 자동화](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) 또는 [예약된 자동화](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5)를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="dd54c-145">다음은 [SFTP를 통한 자동화](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5)의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="dd54c-146">데이터 프라이버시 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="dd54c-146">Data privacy and compliance</span></span>

<span data-ttu-id="dd54c-147">Dynamics 365 Customer Insights를 사용하여 SFTP를 통해 데이터를 전송하는 경우 Dynamics 365 Customer Insights규정 준수 경계 외부로 개인 데이터와 같이 잠재적으로 민감한 데이터 등의 데이터를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="dd54c-148">Microsoft는 귀하의 지시에 따라 이러한 데이터를 전송하지만 내보내기 대상이 귀하가 가질 수 있는 모든 개인 정보 보호 또는 보안 의무를 충족하도록 할 책임은 귀하에게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="dd54c-149">자세한 내용은 [Microsoft 개인정보처리방침](https://go.microsoft.com/fwlink/?linkid=396732)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dd54c-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="dd54c-150">Dynamics 365 Customer Insights 관리자는 이 기능을 더 이상 사용하지 않도록 이 내보내기 대상을 언제든지 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd54c-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
