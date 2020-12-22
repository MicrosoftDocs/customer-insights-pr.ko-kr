---
title: 환경 만들기 및 관리
description: 서비스에 등록하는 방법과 환경을 관리하는 방법을 알아봅니다.
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644141"
---
# <a name="manage-environments"></a><span data-ttu-id="bbc0a-103">환경 관리</span><span class="sxs-lookup"><span data-stu-id="bbc0a-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="bbc0a-104">이 문서에서는 새 조직을 만드는 방법과 환경을 프로비저닝하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="bbc0a-105">조직 가입 및 만들기</span><span class="sxs-lookup"><span data-stu-id="bbc0a-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="bbc0a-106">[Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) 웹 사이트로 이동</span><span class="sxs-lookup"><span data-stu-id="bbc0a-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="bbc0a-107">**시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="bbc0a-108">원하는 가입 시나리오를 선택하고 해당 링크를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="bbc0a-109">이용 약관에 동의하고 **계속** 을 선택하여 조직 생성을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="bbc0a-110">새로운 환경이 생성되면 다음으로 리디렉션됩니다.[Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="bbc0a-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="bbc0a-111">데모 환경을 사용하여 앱을 탐색하거나 다음 섹션의 단계에 따라 새 환경을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="bbc0a-112">환경 설정을 지정한 후 **만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="bbc0a-113">환경이 성공적으로 생성된 후 로그인됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="bbc0a-114">기존 조직에서 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="bbc0a-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="bbc0a-115">다음과 같은 두 가지 방법으로 새 환경을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="bbc0a-116">완전히 새로운 구성을 지정하거나 기존 환경에서 일부 구성 설정을 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="bbc0a-117">환경을 만들려면:</span><span class="sxs-lookup"><span data-stu-id="bbc0a-117">To create an environment:</span></span>

1. <span data-ttu-id="bbc0a-118">앱 헤더의 **설정** 기호를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-118">Select the **Settings** symbol in the header of the app.</span></span>

1. <span data-ttu-id="bbc0a-119">**새 환경** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-119">Select **New environment**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bbc0a-120">![환경 설정](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="bbc0a-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="bbc0a-121">**새로운 환경 조성** 대화 상자에서 **새로운 환경** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="bbc0a-122">[현재 환경에서 데이터 복사](#additional-considerations-for-copy-configuration-preview)하고 싶다면 **기존 환경에서 복사** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="bbc0a-123">조직에서 데이터를 복사할 수 있는 사용 가능한 모든 환경 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="bbc0a-124">다음 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-124">Provide the following details:</span></span>
   - <span data-ttu-id="bbc0a-125">**이름**: 이 환경의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="bbc0a-126">기존 환경에서 복사한 경우 이 필드가 이미 채워져 있지만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="bbc0a-127">**지역**: 서비스가 배포되고 호스팅되는 지역입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="bbc0a-128">**유형**: 프로덕션 환경을 만들지 샌드박스 환경을 만들지 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="bbc0a-129">필요에 따라 **고급 설정** 을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="bbc0a-130">**모든 데이터 저장**: Customer Insights에서 생성된 출력 데이터를 저장할 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="bbc0a-131">**Customer Insights 저장소**(Customer Insights 팀에서 관리하는 Azure Data Lake) 및 **Azure Data Lake Storage Gen2**(자신의 Azure Data Lake Storage)의 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="bbc0a-132">기본적으로 Customer Insights 저장소 옵션이 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="bbc0a-133">Azure Data Lake Storage에 데이터를 저장하면 데이터가 Dynamics 365 Customer Insights에서 데이터가 저장되는 위치와 다를 수 있으므로 해당 Azure Storage 계정의 적절한 지역에 데이터를 전송하고 저장한다는 데 동의하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="bbc0a-134">Microsoft 보안 센터에서 자세히 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="bbc0a-135">현재 수집된 엔터티는 항상 Customer Insights 관리형 데이터 레이크에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="bbc0a-136">환경을 만들 때 선택한 동일한 Azure 지역의 Azure Data Lake Gen2 스토리지 계정만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="bbc0a-137">Azure Data Lake Gen2 계층 구조 네임스페이스(HNS)를 지원하는 저장소 계정만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="bbc0a-138">Azure Data Lake Storage Gen2 옵션의 경우 인증을 위해 리소스 기반 옵션과 구독 기반 옵션 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="bbc0a-139">자세한 내용은 [Azure 서비스 보안 주체를 사용하여 대상 그룹 인사이트를 Azure Data Lake Storage Gen2 계정에 연결](connect-service-principal.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="bbc0a-140">**컨테이너** 이름은 변경할 수 없으며 "customerinsights"가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="bbc0a-141">[예측](predictions.md)을 사용하려면 **예측 사용** 아래의 **서버 주소** 필드에 Common Data Service 인스턴스 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-141">If you want to use [predictions](predictions.md), enter the Common Data Service instance URL in the **Server address** field under **Use predictions**.</span></span>

   <span data-ttu-id="bbc0a-142">데이터 수집 또는 세그먼트 생성과 같은 프로세스를 실행하면 위에서 지정한 스토리지 계정에 해당 폴더가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-142">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="bbc0a-143">데이터 파일과 model.json 파일이 생성되며 실행하는 프로세스에 따라 해당 하위 폴더에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-143">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="bbc0a-144">Customer Insights의 여러 환경을 만들고 해당 환경의 출력 엔터티를 스토리지 계정에 저장하도록 선택하면 컨테이너에 ci_<environmentid>가 있는 각 환경에 대해 별도의 폴더가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-144">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="bbc0a-145">복사 구성에 대한 추가 고려 사항 (미리보기)</span><span class="sxs-lookup"><span data-stu-id="bbc0a-145">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="bbc0a-146">다음 구성 설정이 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-146">The following configuration settings are copied:</span></span>

- <span data-ttu-id="bbc0a-147">기능 구성</span><span class="sxs-lookup"><span data-stu-id="bbc0a-147">Feature configurations</span></span>
- <span data-ttu-id="bbc0a-148">통합/가져온 데이터 원본</span><span class="sxs-lookup"><span data-stu-id="bbc0a-148">Inegsted/imported data sources</span></span>
- <span data-ttu-id="bbc0a-149">데이터 통합(맵, 일치, 병합) 구성</span><span class="sxs-lookup"><span data-stu-id="bbc0a-149">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="bbc0a-150">세그먼트</span><span class="sxs-lookup"><span data-stu-id="bbc0a-150">Segments</span></span>
- <span data-ttu-id="bbc0a-151">측정값</span><span class="sxs-lookup"><span data-stu-id="bbc0a-151">Measures</span></span>
- <span data-ttu-id="bbc0a-152">관계</span><span class="sxs-lookup"><span data-stu-id="bbc0a-152">Relationships</span></span>
- <span data-ttu-id="bbc0a-153">활동 </span><span class="sxs-lookup"><span data-stu-id="bbc0a-153">Activities</span></span>
- <span data-ttu-id="bbc0a-154">검색 및 필터 인덱스</span><span class="sxs-lookup"><span data-stu-id="bbc0a-154">Search & filter Index</span></span>
- <span data-ttu-id="bbc0a-155">내보내기 대상</span><span class="sxs-lookup"><span data-stu-id="bbc0a-155">Export destinations</span></span>
- <span data-ttu-id="bbc0a-156">예약된 새로 고침</span><span class="sxs-lookup"><span data-stu-id="bbc0a-156">Scheduled refresh</span></span>
- <span data-ttu-id="bbc0a-157">보강</span><span class="sxs-lookup"><span data-stu-id="bbc0a-157">Enrichments</span></span>
- <span data-ttu-id="bbc0a-158">모델 관리</span><span class="sxs-lookup"><span data-stu-id="bbc0a-158">Model management</span></span>
- <span data-ttu-id="bbc0a-159">역할 할당</span><span class="sxs-lookup"><span data-stu-id="bbc0a-159">Role assignments</span></span>

<span data-ttu-id="bbc0a-160">다음 설정이 복사되지 *않습니다*.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-160">The following settings are *not* copied:</span></span>

- <span data-ttu-id="bbc0a-161">고객 프로필.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-161">Customer profiles.</span></span>
- <span data-ttu-id="bbc0a-162">데이터 원본 자격 증명.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-162">Data source credentials.</span></span> <span data-ttu-id="bbc0a-163">모든 데이터 원본에 대한 자격 증명을 제공하고 데이터 원본을 수동으로 새로 고쳐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-163">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="bbc0a-164">Common Data Model 폴더 및 Common Data Service 관리 레이크의 데이터 원본.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-164">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="bbc0a-165">원본 환경에서와 동일한 이름으로 해당 데이터 원본을 수동으로 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-165">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="bbc0a-166">환경을 복사하면 새 환경이 생성되었다는 확인 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-166">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="bbc0a-167">**데이터 원본으로 이동** 을 선택하여 데이터 원본 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-167">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="bbc0a-168">모든 데이터 원본에 **자격 증명 필요** 상태가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-168">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="bbc0a-169">데이터 원본을 편집하고 자격 증명 정보를 입력하여 새로 고치십시오.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-169">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bbc0a-170">![데이터 원본 복사됨](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="bbc0a-170">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="bbc0a-171">데이터 원본을 새로 고친 후 **데이터** > **통합** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-171">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="bbc0a-172">원본 환경에서 설정을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-172">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="bbc0a-173">필요에 따라 편집하거나 **실행** 을 선택하여 데이터 통합 프로세스를 시작하고 통합 고객 엔터티를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-173">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="bbc0a-174">데이터 통합이 완료되면 **측정** 및 **세그먼트** 로 이동하여 이들도 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-174">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="bbc0a-175">기존 환경 편집</span><span class="sxs-lookup"><span data-stu-id="bbc0a-175">Edit an existing environment</span></span>

<span data-ttu-id="bbc0a-176">기존 환경의 세부 사항 중 일부를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-176">You can edit some of the details of existing environments.</span></span>

1. <span data-ttu-id="bbc0a-177">**관리** > **시스템** > **정보** 로 이동</span><span class="sxs-lookup"><span data-stu-id="bbc0a-177">Go to **Admin** > **System** > **About**.</span></span>

2. <span data-ttu-id="bbc0a-178">**편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-178">Select **Edit**.</span></span>

3. <span data-ttu-id="bbc0a-179">환경의 **표시 이름** 을 업데이트할 수 있지만 **지역** 또는 **유형** 은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-179">You can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="bbc0a-180">환경이 데이터를 Azure Data Lake Storage Gen2에 저장하도록 구성된 경우 **계정 키** 를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-180">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="bbc0a-181">그러나 **계정 이름** 또는 **컨테이너** 이름은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-181">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="bbc0a-182">선택적으로 계정 키 기반 연결에서 리소스 기반 또는 구독 기반 연결로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-182">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="bbc0a-183">한 번 업그레이드하면 업데이트 후 계정 키로 되돌릴 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-183">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="bbc0a-184">자세한 내용은 [Azure 서비스 보안 주체를 사용하여 대상 그룹 인사이트를 Azure Data Lake Storage Gen2 계정에 연결](connect-service-principal.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-184">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="bbc0a-185">연결을 업데이트할 때 **컨테이너** 정보를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-185">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="bbc0a-186">기존 환경 초기화</span><span class="sxs-lookup"><span data-stu-id="bbc0a-186">Reset an existing environment</span></span>

<span data-ttu-id="bbc0a-187">모든 구성을 삭제하고 수집된 데이터를 제거하려는 경우 환경을 빈 상태로 재설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-187">You can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="bbc0a-188">**관리** > **시스템** > **정보** 로 이동</span><span class="sxs-lookup"><span data-stu-id="bbc0a-188">Go to **Admin** > **System** > **About**.</span></span>

2.  <span data-ttu-id="bbc0a-189">**초기화** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-189">Select **Reset**.</span></span> 

3.  <span data-ttu-id="bbc0a-190">삭제를 확인하려면 환경 이름을 입력하고 **초기화** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-190">To confirm the deletion, enter the environment name and select **Reset**.</span></span>


## <a name="delete-an-existing-environment"></a><span data-ttu-id="bbc0a-191">기존 환경 삭제</span><span class="sxs-lookup"><span data-stu-id="bbc0a-191">Delete an existing environment</span></span>

1. <span data-ttu-id="bbc0a-192">**관리** > **시스템** > **정보** 로 이동</span><span class="sxs-lookup"><span data-stu-id="bbc0a-192">Go to **Admin** > **System** > **About**.</span></span>

1. <span data-ttu-id="bbc0a-193">**삭제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-193">Select **Delete**.</span></span>

1. <span data-ttu-id="bbc0a-194">삭제를 확인하려면 환경 이름을 입력하고 **삭제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bbc0a-194">To confirm the deletion, enter the environment name and select **Delete**.</span></span>
