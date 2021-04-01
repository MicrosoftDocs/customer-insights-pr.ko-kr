---
title: 환경 만들기 및 관리
description: 서비스에 등록하는 방법과 환경을 관리하는 방법을 알아봅니다.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 1c2dfdd2889b5cb6c5285b4d7cc7f52a3d6de4d1
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598301"
---
# <a name="manage-environments"></a><span data-ttu-id="be745-103">환경 관리</span><span class="sxs-lookup"><span data-stu-id="be745-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="be745-104">이 문서에서는 새 조직을 만드는 방법과 환경을 프로비저닝하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="be745-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="be745-105">조직 가입 및 만들기</span><span class="sxs-lookup"><span data-stu-id="be745-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="be745-106">[Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) 웹 사이트로 이동</span><span class="sxs-lookup"><span data-stu-id="be745-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="be745-107">**시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be745-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="be745-108">원하는 가입 시나리오를 선택하고 해당 링크를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="be745-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="be745-109">이용 약관에 동의하고 **계속** 을 선택하여 조직 생성을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="be745-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="be745-110">새로운 환경이 생성되면 다음으로 리디렉션됩니다.[Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="be745-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="be745-111">데모 환경을 사용하여 앱을 탐색하거나 다음 섹션의 단계에 따라 새 환경을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="be745-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="be745-112">환경 설정을 지정한 후 **만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be745-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="be745-113">환경이 성공적으로 생성된 후 로그인됩니다.</span><span class="sxs-lookup"><span data-stu-id="be745-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="be745-114">기존 조직에서 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="be745-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="be745-115">다음과 같은 두 가지 방법으로 새 환경을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be745-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="be745-116">완전히 새로운 구성을 지정하거나 기존 환경에서 일부 구성 설정을 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be745-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="be745-117">환경을 만들려면:</span><span class="sxs-lookup"><span data-stu-id="be745-117">To create an environment:</span></span>

1. <span data-ttu-id="be745-118">앱 헤더의 **환경** 선택기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be745-118">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="be745-119">**새로 만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be745-119">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="be745-120">![환경 설정](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="be745-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="be745-121">**새로운 환경 조성** 대화 상자에서 **새로운 환경** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be745-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="be745-122">[현재 환경에서 데이터 복사](#additional-considerations-for-copy-configuration-preview)하고 싶다면 **기존 환경에서 복사** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be745-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="be745-123">조직에서 데이터를 복사할 수 있는 사용 가능한 모든 환경 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="be745-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="be745-124">다음 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="be745-124">Provide the following details:</span></span>
   - <span data-ttu-id="be745-125">**이름**: 이 환경의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="be745-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="be745-126">기존 환경에서 복사한 경우 이 필드가 이미 채워져 있지만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be745-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="be745-127">**지역**: 서비스가 배포되고 호스팅되는 지역입니다.</span><span class="sxs-lookup"><span data-stu-id="be745-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="be745-128">**유형**: 프로덕션 환경을 만들지 샌드박스 환경을 만들지 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be745-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="be745-129">필요에 따라 **고급 설정** 을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be745-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="be745-130">**모든 데이터 저장**: Customer Insights에서 생성된 출력 데이터를 저장할 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="be745-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="be745-131">**Customer Insights 저장소**(Customer Insights 팀에서 관리하는 Azure Data Lake) 및 **Azure Data Lake Storage Gen2**(자신의 Azure Data Lake Storage)의 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be745-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="be745-132">기본적으로 Customer Insights 저장소 옵션이 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be745-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="be745-133">Azure Data Lake Storage에 데이터를 저장하면 데이터가 Dynamics 365 Customer Insights에서 데이터가 저장되는 위치와 다를 수 있으므로 해당 Azure Storage 계정의 적절한 지역에 데이터를 전송하고 저장한다는 데 동의하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="be745-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="be745-134">Microsoft 보안 센터에서 자세히 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="be745-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="be745-135">현재 수집된 엔터티는 항상 Customer Insights 관리형 데이터 레이크에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="be745-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="be745-136">환경을 만들 때 선택한 동일한 Azure 지역의 Azure Data Lake Gen2 스토리지 계정만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="be745-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="be745-137">Azure Data Lake Gen2 계층 구조 네임스페이스(HNS)를 지원하는 저장소 계정만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="be745-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="be745-138">Azure Data Lake Storage Gen2 옵션의 경우 인증을 위해 리소스 기반 옵션과 구독 기반 옵션 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be745-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="be745-139">자세한 내용은 [Azure 서비스 보안 주체를 사용하여 대상 그룹 인사이트를 Azure Data Lake Storage Gen2 계정에 연결](connect-service-principal.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be745-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="be745-140">**컨테이너** 이름은 변경할 수 없으며 "customerinsights"가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be745-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="be745-141">[예측](predictions.md)을 사용하거나 Microsoft Dataverse를 기반으로 하는 응용 프로그램 및 솔루션과의 데이터 공유를 구성하려면 **Microsoft Dataverse와 데이터 공유 구성 및 추가 기능 사용** 에 Microsoft Dataverse 환경 URL을 제공하십시오.</span><span class="sxs-lookup"><span data-stu-id="be745-141">If you want to use [predictions](predictions.md) or configure data sharing with applications and solutions based on Microsoft Dataverse, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="be745-142">**데이터 공유 활성화** 를 선택하여 Customer Insights 출력 데이터를 Microsoft Dataverse 관리형 Data Lake와 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="be745-142">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="be745-143">모든 데이터를 자체 Azure Data Lake Storage에 저장하는 경우 Microsoft Dataverse 관리형 Data Lake와의 데이터 공유는 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be745-143">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="be745-144">Microsoft Dataverse 관리형 Data Lake와의 데이터 공유를 활성화한 경우 [엔터티에서 누락된 값의 예측](predictions.md)은 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be745-144">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="be745-145">![Microsoft Dataverse와 데이터 공유를 활성화하는 구성 옵션](media/Datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="be745-145">![Configuration options to enable data sharing with Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="be745-146">데이터 수집 또는 세그먼트 생성과 같은 프로세스를 실행하면 위에서 지정한 스토리지 계정에 해당 폴더가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="be745-146">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="be745-147">데이터 파일과 model.json 파일이 생성되며 실행하는 프로세스에 따라 해당 하위 폴더에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="be745-147">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="be745-148">Customer Insights의 여러 환경을 만들고 해당 환경의 출력 엔터티를 스토리지 계정에 저장하도록 선택하면 컨테이너에 ci_<environmentid>가 있는 각 환경에 대해 별도의 폴더가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="be745-148">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="be745-149">복사 구성에 대한 추가 고려 사항 (미리보기)</span><span class="sxs-lookup"><span data-stu-id="be745-149">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="be745-150">다음 구성 설정이 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="be745-150">The following configuration settings are copied:</span></span>

- <span data-ttu-id="be745-151">기능 구성</span><span class="sxs-lookup"><span data-stu-id="be745-151">Feature configurations</span></span>
- <span data-ttu-id="be745-152">수집한/가져온 데이터 원본</span><span class="sxs-lookup"><span data-stu-id="be745-152">Ingested/imported data sources</span></span>
- <span data-ttu-id="be745-153">데이터 통합(맵, 일치, 병합) 구성</span><span class="sxs-lookup"><span data-stu-id="be745-153">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="be745-154">세그먼트</span><span class="sxs-lookup"><span data-stu-id="be745-154">Segments</span></span>
- <span data-ttu-id="be745-155">측정값</span><span class="sxs-lookup"><span data-stu-id="be745-155">Measures</span></span>
- <span data-ttu-id="be745-156">관계</span><span class="sxs-lookup"><span data-stu-id="be745-156">Relationships</span></span>
- <span data-ttu-id="be745-157">활동 </span><span class="sxs-lookup"><span data-stu-id="be745-157">Activities</span></span>
- <span data-ttu-id="be745-158">검색 및 필터 인덱스</span><span class="sxs-lookup"><span data-stu-id="be745-158">Search & filter Index</span></span>
- <span data-ttu-id="be745-159">내보내기 대상</span><span class="sxs-lookup"><span data-stu-id="be745-159">Export destinations</span></span>
- <span data-ttu-id="be745-160">예약된 새로 고침</span><span class="sxs-lookup"><span data-stu-id="be745-160">Scheduled refresh</span></span>
- <span data-ttu-id="be745-161">보강</span><span class="sxs-lookup"><span data-stu-id="be745-161">Enrichments</span></span>
- <span data-ttu-id="be745-162">모델 관리</span><span class="sxs-lookup"><span data-stu-id="be745-162">Model management</span></span>
- <span data-ttu-id="be745-163">역할 할당</span><span class="sxs-lookup"><span data-stu-id="be745-163">Role assignments</span></span>

<span data-ttu-id="be745-164">다음 설정이 복사되지 *않습니다*.</span><span class="sxs-lookup"><span data-stu-id="be745-164">The following settings are *not* copied:</span></span>

- <span data-ttu-id="be745-165">고객 프로필.</span><span class="sxs-lookup"><span data-stu-id="be745-165">Customer profiles.</span></span>
- <span data-ttu-id="be745-166">데이터 원본 자격 증명.</span><span class="sxs-lookup"><span data-stu-id="be745-166">Data source credentials.</span></span> <span data-ttu-id="be745-167">모든 데이터 원본에 대한 자격 증명을 제공하고 데이터 원본을 수동으로 새로 고쳐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be745-167">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="be745-168">Common Data Model 폴더 및 Common Data Service 관리 레이크의 데이터 원본.</span><span class="sxs-lookup"><span data-stu-id="be745-168">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="be745-169">원본 환경에서와 동일한 이름으로 해당 데이터 원본을 수동으로 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be745-169">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="be745-170">환경을 복사하면 새 환경이 생성되었다는 확인 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="be745-170">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="be745-171">**데이터 원본으로 이동** 을 선택하여 데이터 원본 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be745-171">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="be745-172">모든 데이터 원본에 **자격 증명 필요** 상태가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="be745-172">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="be745-173">데이터 원본을 편집하고 자격 증명 정보를 입력하여 새로 고치십시오.</span><span class="sxs-lookup"><span data-stu-id="be745-173">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="be745-174">![데이터 원본 복사됨](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="be745-174">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="be745-175">데이터 원본을 새로 고친 후 **데이터** > **통합** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="be745-175">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="be745-176">원본 환경에서 설정을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be745-176">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="be745-177">필요에 따라 편집하거나 **실행** 을 선택하여 데이터 통합 프로세스를 시작하고 통합 고객 엔터티를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="be745-177">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="be745-178">데이터 통합이 완료되면 **측정** 및 **세그먼트** 로 이동하여 이들도 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="be745-178">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="be745-179">기존 환경 편집</span><span class="sxs-lookup"><span data-stu-id="be745-179">Edit an existing environment</span></span>

<span data-ttu-id="be745-180">기존 환경의 세부 사항 중 일부를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be745-180">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="be745-181">앱 헤더의 **환경** 선택기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be745-181">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="be745-182">**편집** 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be745-182">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="be745-183">**환경 편집** 상자에서 환경의 **표시 이름** 을 업데이트할 수 있지만 **지역** 또는 **유형** 은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="be745-183">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="be745-184">환경이 데이터를 Azure Data Lake Storage Gen2에 저장하도록 구성된 경우 **계정 키** 를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be745-184">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="be745-185">그러나 **계정 이름** 또는 **컨테이너** 이름은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="be745-185">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="be745-186">선택적으로 계정 키 기반 연결에서 리소스 기반 또는 구독 기반 연결로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be745-186">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="be745-187">한 번 업그레이드하면 업데이트 후 계정 키로 되돌릴 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="be745-187">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="be745-188">자세한 내용은 [Azure 서비스 보안 주체를 사용하여 대상 그룹 인사이트를 Azure Data Lake Storage Gen2 계정에 연결](connect-service-principal.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be745-188">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="be745-189">연결을 업데이트할 때 **컨테이너** 정보를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="be745-189">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="be745-190">기존 환경 초기화</span><span class="sxs-lookup"><span data-stu-id="be745-190">Reset an existing environment</span></span>

<span data-ttu-id="be745-191">모든 구성을 삭제하고 수집된 데이터를 제거하려는 경우 관리자로서 환경을 빈 상태로 재설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be745-191">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="be745-192">앱 헤더의 **환경** 선택기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be745-192">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="be745-193">재설정하려는 환경을 선택하고 줄임표 **...** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be745-193">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="be745-194">**재설정** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be745-194">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="be745-195">삭제를 확인하려면 환경 이름을 입력하고 **초기화** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be745-195">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="be745-196">기존 환경 삭제(관리자만 사용 가능)</span><span class="sxs-lookup"><span data-stu-id="be745-196">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="be745-197">관리자는 관리하는 환경을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be745-197">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="be745-198">앱 헤더의 **환경** 선택기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be745-198">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="be745-199">재설정하려는 환경을 선택하고 줄임표 **...** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be745-199">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="be745-200">**삭제** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be745-200">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="be745-201">삭제를 확인하려면 환경 이름을 입력하고 **삭제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be745-201">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]