---
title: 서비스 주체를 사용하여 Azure Data Lake Storage Gen2 계정에 연결
description: 대상 그룹 인사이트에 Azure 서비스 주체를 사용하여 대상 그룹 인사이트에 연결할 때 자체 데이터 레이크에 연결합니다.
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644096"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="9358b-103">대상 그룹 인사이트의 Azure 서비스 보안 주체를 사용하여 Azure Data Lake Storage Gen2 계정에 연결</span><span class="sxs-lookup"><span data-stu-id="9358b-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="9358b-104">Azure 서비스를 사용하는 자동화 도구에는 항상 제한된 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="9358b-105">애플리케이션이 완전한 권한이 있는 사용자로 로그인하는 대신 Azure는 서비스 주체를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="9358b-106">스토리지 계정 키 대신 Azure 서비스 주체를 사용하여 Azure Data Lake Storage Gen2 계정과 대상 그룹 인사이트를 연결하는 방법을 알아보려면 계속 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="9358b-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="9358b-107">서비스 주체를 사용하여 [Common Data Model 폴더를 데이터 원본으로 안전하게 추가 또는 편집](connect-common-data-model.md)하거나 [새 환경을 만들거나 기존 환경을 업데이트](manage-environments.md#create-an-environment-in-an-existing-organization)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

<span data-ttu-id="9358b-108">서비스 주체를 만들려면 Azure 구독에 대한 관리자 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-108">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="9358b-109">대상 그룹 인사이트에 대한 Azure 서비스 주체 만들기</span><span class="sxs-lookup"><span data-stu-id="9358b-109">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="9358b-110">대상 그룹 인사이트에 대한 새 서비스 주체를 만들기 전에 조직에 이미 존재하는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="9358b-110">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="9358b-111">기존 서비스 주체 찾기</span><span class="sxs-lookup"><span data-stu-id="9358b-111">Look for an existing service principal</span></span>

1. <span data-ttu-id="9358b-112">[Azure 관리 포털](https://portal.azure.com)로 이동하고 조직에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-112">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="9358b-113">Azure 서비스에서 **Azure Active Directory** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-113">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="9358b-114">**관리** 에서 **엔터프라이즈 애플리케이션** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-114">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="9358b-115">대상 그룹 인사이트 자사 애플리케이션 ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` 또는 이름 `Dynamics 365 AI for Customer Insights`를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-115">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="9358b-116">일치하는 레코드를 찾으면 대상 그룹 인사이트에 대한 서비스 주체가 존재함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-116">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="9358b-117">아무것도 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-117">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="기존 서비스 주체를 보여주는 스크린샷.":::
   
6. <span data-ttu-id="9358b-119">결과가 반환되지 않으면 새 서비스 주체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-119">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="9358b-120">새 서비스 주체 만들기</span><span class="sxs-lookup"><span data-stu-id="9358b-120">Create a new service principal</span></span>

1. <span data-ttu-id="9358b-121">최신 버전의 **그래프용 Azure Active Directory PowerShell** 을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-121">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="9358b-122">자세한 내용은 [그래프용 Azure Active Directory PowerShell 설치](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9358b-122">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="9358b-123">PC에서 키보드의 Windows 키를 선택하고 **Windows PowerShell** 과 **관리자 권한으로 실행** 를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-123">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="9358b-124">열리는 PowerShell 창에 `Install-Module AzureAD`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-124">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="9358b-125">Azure AD PowerShell 모듈을 사용하여 대상 그룹 인사이트에 대한 서비스 주체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-125">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="9358b-126">PowerShell 창에 `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-126">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="9358b-127">"본인의 테넌트 ID"를 서비스 주체를 만들 테넌트의 실제 ID로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-127">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="9358b-128">환경 이름 매개 변수 `AzureEnvironmentName`은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-128">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="9358b-129">`New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-129">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="9358b-130">이 명령은 선택한 테넌트에 대한 대상 그룹 인사이트를 위한 서비스 주체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-130">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="9358b-131">서비스 주체에게 스토리지 계정에 액세스할 수 있는 권한 부여</span><span class="sxs-lookup"><span data-stu-id="9358b-131">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="9358b-132">Azure Portal로 이동하여 대상 그룹 인사이트에서 사용하려는 스토리지 계정의 서비스 주체에 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-132">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="9358b-133">[Azure 관리 포털](https://portal.azure.com)로 이동하고 조직에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-133">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="9358b-134">대상 그룹 인사이트에 대한 서비스 주체가 액세스할 스토리지 계정을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-134">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="9358b-135">탐색 창에서 **액세스 제어(IAM)** 를 선택하고 **추가** > **역할 할당** 추가를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-135">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="역할 할당을 추가하는 동안 Azure Portal을 보여주는 스크린샷.":::
   
1. <span data-ttu-id="9358b-137">**역할 할당 추가** 창에서 다음 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-137">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="9358b-138">역할: *Storage Blob 데이터 기여자*</span><span class="sxs-lookup"><span data-stu-id="9358b-138">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="9358b-139">액세스 권한 할당: *사용자, 그룹 또는 서비스 주체*</span><span class="sxs-lookup"><span data-stu-id="9358b-139">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="9358b-140">선택: *Dynamics 365 AI for Customer Insights*([사용자가 만든 서비스 주체](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="9358b-140">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="9358b-141">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-141">Select **Save**.</span></span>

<span data-ttu-id="9358b-142">변경 사항을 전파하는 데 최대 15분이 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-142">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="9358b-143">대상 그룹 인사이트에 대한 스토리지 계정 첨부 파일에 Azure 리소스 ID 또는 Azure 구독 세부 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-143">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="9358b-144">대상 그룹 인사이트에 Azure Data Lake 스토리지 계정을 연결하여 [출력 데이터를 저장](manage-environments.md)하거나 [데이터 원본으로 사용](connect-common-data-service-lake.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-144">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="9358b-145">Azure Data Lake 옵션을 선택하면 리소스 기반 또는 구독 기반 접근 방식 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-145">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="9358b-146">선택한 접근 방식에 대한 필수 정보를 제공하려면 아래 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-146">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resounce-based-storage-account-connection"></a><span data-ttu-id="9358b-147">리소스 기반 저장소 계정 연결</span><span class="sxs-lookup"><span data-stu-id="9358b-147">Resounce-based storage account connection</span></span>

1. <span data-ttu-id="9358b-148">[Azure 관리 포털](https://portal.azure.com)로 이동하여 구독에 로그인하고 스토리지 계정을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-148">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="9358b-149">탐색 창에서 이동 **설정** > **속성** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-149">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="9358b-150">스토리지 계정 리소스 ID 값을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-150">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="스토리지 계정 리소스 ID 값을 복사합니다.":::

1. <span data-ttu-id="9358b-152">대상 그룹 인사이트에서 스토리지 계정 연결 화면에 표시된 리소스 필드에 리소스 ID를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-152">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="스토리지 계정 리소스 ID 정보를 입력합니다.":::   
   
1. <span data-ttu-id="9358b-154">대상 그룹 인사이트의 나머지 단계를 계속하여 스토리지 계정을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-154">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="9358b-155">구독 기반 저장소 계정 연결</span><span class="sxs-lookup"><span data-stu-id="9358b-155">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="9358b-156">[Azure 관리 포털](https://portal.azure.com)로 이동하여 구독에 로그인하고 스토리지 계정을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-156">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="9358b-157">탐색 창에서 이동 **설정** > **속성** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-157">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="9358b-158">**구독**, **리소스 그룹** 및 스토리지 계정의 **이름** 을 검토하여 대상 그룹 인사이트에서 올바른 값을 선택했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-158">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="9358b-159">대상 그룹 인사이트에서 스토리지 계정을 연결할 때 값 또는 해당 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-159">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="스토리지 계정 리소스 ID 정보를 입력합니다.":::
   
1. <span data-ttu-id="9358b-161">대상 그룹 인사이트의 나머지 단계를 계속하여 스토리지 계정을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="9358b-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>
