---
title: 환경 만들기 및 관리
description: 서비스에 등록하는 방법과 환경을 관리하는 방법을 알아봅니다.
ms.date: 06/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 904ce68336cba4b7a4d5a37692b72d091400559d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304888"
---
# <a name="manage-environments"></a><span data-ttu-id="3af92-103">환경 관리</span><span class="sxs-lookup"><span data-stu-id="3af92-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="3af92-104">이 문서에서는 새 조직을 만드는 방법과 환경을 프로비저닝하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="3af92-105">조직 가입 및 만들기</span><span class="sxs-lookup"><span data-stu-id="3af92-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="3af92-106">[Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) 웹 사이트로 이동</span><span class="sxs-lookup"><span data-stu-id="3af92-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="3af92-107">**시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="3af92-108">원하는 가입 시나리오를 선택하고 해당 링크를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="3af92-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="3af92-109">이용 약관에 동의하고 **계속** 을 선택하여 조직 생성을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="3af92-110">새로운 환경이 생성되면 다음으로 리디렉션됩니다.[Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="3af92-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="3af92-111">데모 환경을 사용하여 앱을 탐색하거나 다음 섹션의 단계에 따라 새 환경을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="3af92-112">환경 설정을 지정한 후 **만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="3af92-113">환경이 성공적으로 생성된 후 로그인됩니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="3af92-114">기존 조직에서 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="3af92-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="3af92-115">다음과 같은 두 가지 방법으로 새 환경을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="3af92-116">완전히 새로운 구성을 지정하거나 기존 환경에서 일부 구성 설정을 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

> [!NOTE]
> <span data-ttu-id="3af92-117">조직은 각 Customer Insights 라이선스에 대해 *두 개* 의 환경을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-117">Organizations can create *two* environments for every Customer Insights license.</span></span> <span data-ttu-id="3af92-118">조직에서 라이선스를 두 개 이상 구매하는 경우 [지원팀에 문의](https://go.microsoft.com/fwlink/?linkid=2079641)하여 사용 가능한 환경의 수를 늘리세요.</span><span class="sxs-lookup"><span data-stu-id="3af92-118">If your organization purchases more than once license, please [contact our support team](https://go.microsoft.com/fwlink/?linkid=2079641) to increase the number of available environments.</span></span> <span data-ttu-id="3af92-119">용량 및 추가 용량에 대한 자세한 내용은 [Dynamics 365 라이선스 가이드](https://go.microsoft.com/fwlink/?LinkId=866544)를 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="3af92-119">For more information about capacity and add-on capacity, download [Dynamics 365 licensing guide](https://go.microsoft.com/fwlink/?LinkId=866544).</span></span>

<span data-ttu-id="3af92-120">환경을 만들려면:</span><span class="sxs-lookup"><span data-stu-id="3af92-120">To create an environment:</span></span>

1. <span data-ttu-id="3af92-121">앱 헤더의 **환경** 선택기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-121">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="3af92-122">**새로 만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-122">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3af92-123">![환경 설정.](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="3af92-123">![Environment settings.](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="3af92-124">**환경 만들기** 대화 상자에서 **새로운 환경** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-124">In the **Create an environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="3af92-125">[현재 환경에서 데이터 복사](#considerations-for-copy-configuration-preview)하고 싶다면 **기존 환경에서 복사** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-125">If you want to [copy data from the current environment](#considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="3af92-126">조직에서 데이터를 복사할 수 있는 사용 가능한 모든 환경 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-126">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="3af92-127">다음 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-127">Provide the following details:</span></span>
   - <span data-ttu-id="3af92-128">**이름**: 이 환경의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-128">**Name**: The name for this environment.</span></span> <span data-ttu-id="3af92-129">기존 환경에서 복사한 경우 이 필드가 이미 채워져 있지만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-129">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="3af92-130">**유형**: 프로덕션 환경을 만들지 샌드박스 환경을 만들지 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-130">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>
   - <span data-ttu-id="3af92-131">**지역**: 서비스가 배포되고 호스팅되는 지역입니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-131">**Region**: The region into which the service is deployed and hosted.</span></span>
   
1. <span data-ttu-id="3af92-132">필요에 따라 **고급 설정** 을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-132">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="3af92-133">**모든 데이터 저장**: Customer Insights에서 생성된 출력 데이터를 저장할 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-133">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="3af92-134">두 가지 옵션이 있습니다. **Customer Insights 스토리지**(Customer Insights 팀에서 관리하는 Azure Data Lake) 및 **Azure Data Lake Storage**(사용자의 Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="3af92-134">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="3af92-135">기본적으로 Customer Insights 저장소 옵션이 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-135">By default, the Customer Insights storage option is selected.</span></span>

     > [!NOTE]
     > <span data-ttu-id="3af92-136">Azure Data Lake Storage에 데이터를 저장하면 데이터가 Dynamics 365 Customer Insights에서 데이터가 저장되는 위치와 다를 수 있으므로 해당 Azure Storage 계정의 적절한 지역에 데이터를 전송하고 저장한다는 데 동의하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-136">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="3af92-137">Microsoft 보안 센터에서 자세히 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="3af92-137">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
     >
     > <span data-ttu-id="3af92-138">현재 수집된 엔터티는 항상 Customer Insights 관리형 Data Lake에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-138">Currently, ingested entities are always stored in the Customer Insights Managed Data Lake.</span></span> 
     > 
     > <span data-ttu-id="3af92-139">환경을 만들 때 선택한 동일한 Azure 지역의 Azure Data Lake Storage 계정만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-139">We support only Azure Data Lake Storage accounts from the same Azure region you selected when creating the environment.</span></span> 
     > 
     > <span data-ttu-id="3af92-140">계층 구조 네임스페이스가 사용 설정된 Azure Data Lake Storage 계정만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-140">We support only Azure Data Lake Storage accounts that have hierarchical namespace enabled.</span></span>


   - <span data-ttu-id="3af92-141">Azure Data Lake Storage 옵션의 경우 인증을 위해 리소스 기반 옵션과 구독 기반 옵션 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-141">For the Azure Data Lake Storage option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="3af92-142">자세한 내용은 [Azure 서비스 보안 주체를 사용하여 대상 그룹 인사이트를 Azure Data Lake Storage Gen2 계정에 연결](connect-service-principal.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3af92-142">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="3af92-143">**컨테이너** 이름은 변경할 수 없으며 `customerinsights`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-143">The **Container** name can't be changed and will be `customerinsights`.</span></span>
   
   - <span data-ttu-id="3af92-144">[예측](predictions.md)을 사용하려면 Microsoft Dataverse로 데이터 공유를 구성하거나 온-프레미스 데이터 소스에서 데이터 수집을 사용 설정하고 **Microsoft Dataverse와 데이터 공유 구성 및 추가 기능 사용 설정** 아래에 Microsoft Dataverse 환경 URL을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-144">If you want to use [predictions](predictions.md), configure data sharing with Microsoft Dataverse, or enable data ingestion from on-premises data sources, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="3af92-145">**데이터 공유 활성화** 를 선택하여 Customer Insights 출력 데이터를 Microsoft Dataverse 관리형 Data Lake와 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-145">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="3af92-146">모든 데이터를 자체 Azure Data Lake Storage에 저장하는 경우 Microsoft Dataverse 관리형 Data Lake와의 데이터 공유는 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-146">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="3af92-147">Microsoft Dataverse 관리형 Data Lake와의 데이터 공유를 활성화한 경우 [엔터티에서 누락된 값의 예측](predictions.md)은 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-147">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="3af92-148">![Microsoft Dataverse와 데이터 공유를 활성화하는 구성 옵션](media/datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="3af92-148">![Configuration options to enable data sharing with Microsoft Dataverse.](media/datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="3af92-149">데이터 수집 또는 세그먼트 생성과 같은 프로세스를 실행하면 위에서 지정한 스토리지 계정에 해당 폴더가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-149">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="3af92-150">데이터 파일 및 model.json 파일이 생성되고 프로세스 이름을 기반으로 폴더에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-150">Data files and model.json files will be created and added to folders based on the process name.</span></span>

   <span data-ttu-id="3af92-151">Customer Insights의 여러 환경을 만들고 해당 환경의 출력 엔터티를 스토리지 계정에 저장하도록 선택하면 컨테이너에 ci_<environmentid>가 있는 각 환경에 대해 별도의 폴더가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-151">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="considerations-for-copy-configuration-preview"></a><span data-ttu-id="3af92-152">복사 구성 고려 사항(프리뷰)</span><span class="sxs-lookup"><span data-stu-id="3af92-152">Considerations for copy configuration (preview)</span></span>

<span data-ttu-id="3af92-153">다음 구성 설정이 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-153">The following configuration settings are copied:</span></span>

- <span data-ttu-id="3af92-154">기능 구성</span><span class="sxs-lookup"><span data-stu-id="3af92-154">Feature configurations</span></span>
- <span data-ttu-id="3af92-155">수집한/가져온 데이터 원본</span><span class="sxs-lookup"><span data-stu-id="3af92-155">Ingested/imported data sources</span></span>
- <span data-ttu-id="3af92-156">데이터 통합(맵, 일치, 병합) 구성</span><span class="sxs-lookup"><span data-stu-id="3af92-156">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="3af92-157">세그먼트</span><span class="sxs-lookup"><span data-stu-id="3af92-157">Segments</span></span>
- <span data-ttu-id="3af92-158">측정값</span><span class="sxs-lookup"><span data-stu-id="3af92-158">Measures</span></span>
- <span data-ttu-id="3af92-159">관계</span><span class="sxs-lookup"><span data-stu-id="3af92-159">Relationships</span></span>
- <span data-ttu-id="3af92-160">활동 </span><span class="sxs-lookup"><span data-stu-id="3af92-160">Activities</span></span>
- <span data-ttu-id="3af92-161">검색 및 필터 인덱스</span><span class="sxs-lookup"><span data-stu-id="3af92-161">Search & filter Index</span></span>
- <span data-ttu-id="3af92-162">내보내기 대상</span><span class="sxs-lookup"><span data-stu-id="3af92-162">Export destinations</span></span>
- <span data-ttu-id="3af92-163">예약된 새로 고침</span><span class="sxs-lookup"><span data-stu-id="3af92-163">Scheduled refresh</span></span>
- <span data-ttu-id="3af92-164">보강</span><span class="sxs-lookup"><span data-stu-id="3af92-164">Enrichments</span></span>
- <span data-ttu-id="3af92-165">모델 관리</span><span class="sxs-lookup"><span data-stu-id="3af92-165">Model management</span></span>
- <span data-ttu-id="3af92-166">역할 할당</span><span class="sxs-lookup"><span data-stu-id="3af92-166">Role assignments</span></span>

<span data-ttu-id="3af92-167">다음 설정이 복사되지 *않습니다*.</span><span class="sxs-lookup"><span data-stu-id="3af92-167">The following settings are *not* copied:</span></span>

- <span data-ttu-id="3af92-168">고객 프로필.</span><span class="sxs-lookup"><span data-stu-id="3af92-168">Customer profiles.</span></span>
- <span data-ttu-id="3af92-169">데이터 원본 자격 증명.</span><span class="sxs-lookup"><span data-stu-id="3af92-169">Data source credentials.</span></span> <span data-ttu-id="3af92-170">모든 데이터 원본에 대한 자격 증명을 제공하고 데이터 원본을 수동으로 새로 고쳐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-170">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="3af92-171">Common Data Model 폴더의 데이터 원본 및 Dataverse 관리형 Data Lake.</span><span class="sxs-lookup"><span data-stu-id="3af92-171">Data sources from Common Data Model folder and Dataverse managed Data Lake.</span></span> <span data-ttu-id="3af92-172">원본 환경에서와 동일한 이름으로 해당 데이터 원본을 수동으로 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-172">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="3af92-173">환경을 복사하면 새 환경이 생성되었다는 확인 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-173">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="3af92-174">**데이터 원본으로 이동** 을 선택하여 데이터 원본 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-174">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="3af92-175">모든 데이터 원본에 **자격 증명 필요** 상태가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-175">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="3af92-176">데이터 원본을 편집하고 자격 증명 정보를 입력하여 새로 고치십시오.</span><span class="sxs-lookup"><span data-stu-id="3af92-176">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3af92-177">![데이터 원본 복사됨.](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="3af92-177">![Data sources copied.](media/data-sources-copied.png)</span></span>

<span data-ttu-id="3af92-178">데이터 원본을 새로 고친 후 **데이터** > **통합** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-178">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="3af92-179">원본 환경에서 설정을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-179">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="3af92-180">필요에 따라 편집하거나 **실행** 을 선택하여 데이터 통합 프로세스를 시작하고 통합 고객 엔터티를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-180">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="3af92-181">데이터 통합이 완료되면 **측정** 및 **세그먼트** 로 이동하여 이들도 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-181">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="3af92-182">기존 환경 편집</span><span class="sxs-lookup"><span data-stu-id="3af92-182">Edit an existing environment</span></span>

<span data-ttu-id="3af92-183">기존 환경의 세부 사항 중 일부를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-183">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="3af92-184">앱 헤더의 **환경** 선택기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-184">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="3af92-185">**편집** 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-185">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="3af92-186">**환경 편집** 상자에서 환경의 **표시 이름** 을 업데이트할 수 있지만 **지역** 또는 **유형** 은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-186">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="3af92-187">Azure Data Lake Storage에 데이터를 저장하도록 환경이 구성된 경우 **계정 키** 를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-187">If an environment is configured to store data in Azure Data Lake Storage, you can update the **Account key**.</span></span> <span data-ttu-id="3af92-188">그러나 **계정 이름** 또는 **컨테이너** 이름은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-188">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="3af92-189">선택적으로 계정 키 기반 연결에서 리소스 기반 또는 구독 기반 연결로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-189">Optionally, you can update from an account key-based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="3af92-190">한 번 업그레이드하면 업데이트 후 계정 키로 되돌릴 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-190">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="3af92-191">자세한 내용은 [Azure 서비스 보안 주체를 사용하여 대상 그룹 인사이트를 Azure Data Lake Storage Gen2 계정에 연결](connect-service-principal.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3af92-191">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="3af92-192">연결을 업데이트할 때 **컨테이너** 정보를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-192">You can't change **Container** information when updating the connection.</span></span>

6. <span data-ttu-id="3af92-193">선택적으로 **Microsoft Dataverse와 데이터 공유 구성 및 추가 기능 사용 설정** 아래에서 Microsoft Dataverse 환경 URL을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-193">Optionally, you can provide a Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="3af92-194">이러한 기능에는 Microsoft Dataverse, 온-프레미스 데이터 소스를 기반으로 한 데이터 수집 또는 사용 [예측](predictions.md)을 기반으로 한 애플리케이션 및 솔루션과의 데이터 공유가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-194">These capabilities include data sharing with applications and solutions based on Microsoft Dataverse, data ingestion from on-premises data sources, or the use [predictions](predictions.md).</span></span> <span data-ttu-id="3af92-195">**데이터 공유 활성화** 를 선택하여 Customer Insights 출력 데이터를 Microsoft Dataverse 관리형 Data Lake와 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-195">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data lake.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="3af92-196">모든 데이터를 자체 Azure Data Lake Storage에 저장하는 경우 Microsoft Dataverse 관리형 Data Lake와의 데이터 공유는 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-196">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
   > - <span data-ttu-id="3af92-197">[엔터티에서 누락된 값의 예측](predictions.md)은 Microsoft Dataverse 관리형 Data Lake와의 데이터 공유를 활성화할 때 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-197">[Prediction of missing values in an entity](predictions.md) is currently not supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

   <span data-ttu-id="3af92-198">Microsoft Dataverse와의 데이터 공유를 활성화하면 데이터 원본 및 기타 프로세스의 전체 새로 고침이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-198">After enabling data sharing with Microsoft Dataverse, a full refresh of your data sources and other processes starts.</span></span> <span data-ttu-id="3af92-199">프로세스가 현재 실행 중인 경우 Microsoft Dataverse와의 데이터 공유를 활성화하는 옵션이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-199">If processes are currently running, you don't see the option to enable data sharing with Microsoft Dataverse.</span></span> <span data-ttu-id="3af92-200">해당 프로세스가 완료될 때까지 기다리거나 취소하여 데이터 공유를 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-200">Wait for those processes to complete or cancel them to enable data sharing.</span></span> 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Microsoft Dataverse와 데이터 공유를 활성화하는 구성 옵션":::
   
   <span data-ttu-id="3af92-202">데이터 수집 또는 세그먼트 생성과 같은 프로세스를 실행하면 위에서 지정한 스토리지 계정에 해당 폴더가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-202">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="3af92-203">실행하는 프로세스에 따라 데이터 파일 및 model.json 파일이 생성되고 각 하위 폴더에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-203">Data files and model.json files will be created and added to the respective subfolders, depending on the process you run.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="3af92-204">기존 환경 초기화</span><span class="sxs-lookup"><span data-stu-id="3af92-204">Reset an existing environment</span></span>

<span data-ttu-id="3af92-205">모든 구성을 삭제하고 수집된 데이터를 제거하려는 경우 관리자로서 환경을 빈 상태로 재설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-205">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="3af92-206">앱 헤더의 **환경** 선택기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-206">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="3af92-207">재설정하려는 환경을 선택하고 줄임표(**...**)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-207">Select the environment you want to reset and select the ellipsis (**...**).</span></span> 

3. <span data-ttu-id="3af92-208">**재설정** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-208">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="3af92-209">삭제를 확인하려면 환경 이름을 입력하고 **초기화** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-209">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment"></a><span data-ttu-id="3af92-210">기존 환경 삭제</span><span class="sxs-lookup"><span data-stu-id="3af92-210">Delete an existing environment</span></span>

<span data-ttu-id="3af92-211">관리자는 관리하는 환경을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-211">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="3af92-212">앱 헤더의 **환경** 선택기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-212">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="3af92-213">재설정하려는 환경을 선택하고 줄임표(**...**)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-213">Select the environment you want to reset and select the ellipsis (**...**).</span></span> 

3. <span data-ttu-id="3af92-214">**삭제** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-214">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="3af92-215">삭제를 확인하려면 환경 이름을 입력하고 **삭제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3af92-215">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
