---
title: 기계 학습 기반 제안된 세그먼트
description: 기계 학습을 통해 고객 특성을 기반으로 새롭고 흥미로운 세그먼트를 찾을 수 있습니다.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: bbc22adcd7b6e756fa6128abd855795de7480f2d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597105"
---
# <a name="suggested-segments-preview"></a><span data-ttu-id="3f4d6-103">제안된 세그먼트(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="3f4d6-103">Suggested segments (preview)</span></span>

<span data-ttu-id="3f4d6-104">AI 모델의 도움을 받아 흥미로운 고객 세그먼트를 발견하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-104">Discover interesting segments of your customers with the help of an AI model.</span></span> <span data-ttu-id="3f4d6-105">이 기계 학습 기반 기능은 측정값 또는 고객 특성을 기반으로 세그먼트를 제안합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-105">This machine learning powered feature suggests segments based on measures or customer attributes.</span></span> <span data-ttu-id="3f4d6-106">KPI를 개선하거나 다른 특성의 컨텍스트에서 특성의 영향을 더 잘 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-106">It can help improve your KPIs or better understand the influence of attributes in context of other attributes.</span></span> 

> [!NOTE]
> <span data-ttu-id="3f4d6-107">제안된 세그먼트 기능은 자동화된 방법을 사용하여 데이터를 평가하고 해당 데이터를 기반으로 예측을 수행하므로 해당 용어를 일반 데이터 보호 규정(이후 "GDPR")에서 정의한 바에 따라 프로파일링 방법으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-107">The suggested segments feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="3f4d6-108">데이터 처리를 위해 이 기능을 사용하는 경우 GDPR 또는 기타 법률 또는 규정이 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-108">Your use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="3f4d6-109">귀하는 이 기능을 포함한 Dynamics 365 Customer Insights 사용이 개인 정보 보호, 개인 데이터, 생체 인식 데이터, 데이터 보호 및 통신 기밀과 관련된 법률을 포함하여 모든 관련 법률 및 규정을 준수하는지 확인할 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including this feature, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="측면 창에 제안의 세부 정보를 표시하는 Customer Insights의 제안된 세그먼트 페이지입니다.":::

## <a name="suggested-segments-to-improve-your-kpis"></a><span data-ttu-id="3f4d6-111">KPI를 개선하기 위해 제안된 세그먼트</span><span class="sxs-lookup"><span data-stu-id="3f4d6-111">Suggested segments to improve your KPIs</span></span>

<span data-ttu-id="3f4d6-112">대상 그룹 insights 사용자로서 핵심 성과 지표(KPI)를 추적하는 데 도움이 되는 일련의 [생성된 측정값](measures.md)을 가지고 있을 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-112">As a user of audience insights, you likely have a series of [measures created](measures.md) that help track your Key Performance Indicators (KPIs).</span></span> <span data-ttu-id="3f4d6-113">세그먼트를 만들고 고도로 타겟팅된 캠페인을 실행하기 위해 특정 특성이 이 KPI에 어떤 영향을 미치는지 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-113">It's important to understand how certain attributes influence this KPI to create segments and run a highly targeted campaign.</span></span>   
<span data-ttu-id="3f4d6-114">예를 들어 사용자가 *TotalSpendPerCustomer* 라는 측정값을 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-114">For example, you track a measure called *TotalSpendPerCustomer*.</span></span> <span data-ttu-id="3f4d6-115">기업으로서 여러분은 이 숫자가 증가하는 것을 보고 싶어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-115">As a business, you’d like to see this number grow.</span></span> <span data-ttu-id="3f4d6-116">측정값을 기본 특성으로 선택하면 영향을 평가할 특성을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-116">Choosing a measure as primary attribute, lets you select the attributes that you want to assess for influence.</span></span> <span data-ttu-id="3f4d6-117">*회원 등급*, *가입 기간* 및 *직업* 을 생각해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-117">Let's say *membership tier*, *membership period*, and *occupation*.</span></span> <span data-ttu-id="3f4d6-118">그런 다음 Customer Insights는 해당 측정값에 가장 큰 영향을 주는 사람을 알려주는 세그먼트를 제안할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-118">Customer Insights can then suggest a segment that tells you who are the biggest influence of that measure.</span></span> <span data-ttu-id="3f4d6-119">예를 들어 *골드* 회원이며 *최소 5년* 동안 사용자의 비즈니스를 이용한 *회계사* 가 *TotalSpendPerCustomer* 에 가장 큰 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-119">For example, *Accountants* who are *Gold* members, and who have been with your business for *at least five years* are the biggest influencer of *TotalSpendPerCustomer*.</span></span> <span data-ttu-id="3f4d6-120">모든 제안에 대한 예상 세그먼트 크기를 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-120">You’ll get an estimated segment size for every suggestion.</span></span> <span data-ttu-id="3f4d6-121">이 정보를 사용하여 대상 고객을 위한 캠페인을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-121">You can use this information to create campaigns for the targeted audiences.</span></span>

## <a name="understand-what-influences-a-customer-attribute"></a><span data-ttu-id="3f4d6-122">고객 특성에 영향을 미치는 요소 이해</span><span class="sxs-lookup"><span data-stu-id="3f4d6-122">Understand what influences a customer attribute</span></span>

<span data-ttu-id="3f4d6-123">측정값 대신 고객 특성을 기본 특성으로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-123">You can choose a customer attribute instead of a measure as the primary attribute.</span></span> <span data-ttu-id="3f4d6-124">영향을 미치는 특성 선택에 따라 AI 모델은 선택한 특성이 기본 특성에 어떻게 영향을 미치는지 보여주는 일련의 제안을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-124">Based on your choice of influencing attributes, the AI model creates a series of suggestions that show how the selected attributes influence the primary attribute.</span></span>   
<span data-ttu-id="3f4d6-125">예를 들어 기본 특성으로 *리워드 회원(예/아니오)* 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-125">For example, you choose *Rewards Member (Yes/No)* as the primary attribute.</span></span> <span data-ttu-id="3f4d6-126">*재직 기간*, *직업* 및 *지원 티켓 수* 는 다른 영향을 미치는 특성으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-126">*Tenure*, *Occupation*, and *Number of Support Tickets* are set as other influencing attributes.</span></span> <span data-ttu-id="3f4d6-127">AI 모델은 대부분 2년 이상의 재직 기간을 가진 IT 전문가가 보상 회원임을 나타내는 세그먼트를 제안할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-127">The AI model could suggest segments indicating mostly IT professionals with tenure over two years are rewards members.</span></span> <span data-ttu-id="3f4d6-128">또 다른 제안은 재직 기간이 1년 이상이고 지원 티켓이 3개 미만인 회계사가 보상 회원이라는 점을 강조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-128">Another suggestion could highlight that accountants with tenure over one year and fewer than three support tickets are rewards members.</span></span> 

## <a name="artificial-intelligence-usage"></a><span data-ttu-id="3f4d6-129">인공 지능 사용</span><span class="sxs-lookup"><span data-stu-id="3f4d6-129">Artificial intelligence usage</span></span>

<span data-ttu-id="3f4d6-130">의사 결정 트리 알고리즘은 기본 특성과 영향을 주는 특성을 사용하여 흥미로운 세그먼트를 제안합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-130">Using the primary attribute and influencing attributes, a decision tree algorithm suggests interesting segments.</span></span> <span data-ttu-id="3f4d6-131">제안은 AI 알고리즘에서 선택한 규칙 또는 패턴을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-131">The suggestions are based on rules or patterns that were picked up by the AI algorithm.</span></span> <span data-ttu-id="3f4d6-132">평균 인구와 크게 다른 세그먼트만 제안으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-132">Only segments that significantly differ from the average population are shown as suggestions.</span></span> <span data-ttu-id="3f4d6-133">평균 모집단과의 비교는 선택한 측정값 또는 기본 특성을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-133">The comparison to the average population is based on the selected measure or primary attribute.</span></span>

### <a name="responsible-ai"></a><span data-ttu-id="3f4d6-134">책임감 있는 AI</span><span class="sxs-lookup"><span data-stu-id="3f4d6-134">Responsible AI</span></span>

<span data-ttu-id="3f4d6-135">제안된 세그먼트를 사용하면 특성을 선택하여 새 세그먼트를 만들고 선택한 데이터를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-135">Suggested segments lets you select attributes to create new segments and process the data you select.</span></span> <span data-ttu-id="3f4d6-136">인종, 성적 취향 또는 성별과 같은 민감한 특성을 포함한 특성을 선택하는 경우 해당 데이터를 처리할 수 있는지와 처리해야 하는지를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-136">When choosing attributes, including sensitive attributes like race, sexual orientation, or gender, you must ensure that you can and should process that data.</span></span> <span data-ttu-id="3f4d6-137">귀하의 조직에 적용되는 모든 법률을 준수하고 조직의 원칙과 개인 정보 보호 정책을 준수할 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-137">You are responsible to comply with any laws applicable to your organization and adhere to your organization’s principles and privacy policies.</span></span>

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a><span data-ttu-id="3f4d6-138">범주 및 숫자 값이 있는 기본 특성에 대한 다른 결과</span><span class="sxs-lookup"><span data-stu-id="3f4d6-138">Different results for primary attributes with categorical and numeric values</span></span>

<span data-ttu-id="3f4d6-139">숫자 특성 또는 범주 특성을 기본 특성으로 선택하면 세그먼트 제안이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-139">Segment suggestions are different if you choose a numeric attribute or a categorical attribute as the primary attribute.</span></span> <span data-ttu-id="3f4d6-140">범주형 특성의 값에는 둘 이상의 범주 또는 유형이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-140">Values in a categorical attribute contain two or more categories or types.</span></span> <span data-ttu-id="3f4d6-141">숫자 특성은 정량적 데이터를 포함하며 이와 관련된 측정 감각을 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-141">A numeric attribute contains quantitative data and has a sense of measurement associated with it.</span></span>

<span data-ttu-id="3f4d6-142">*연간 소득* 또는 *가입 기간* 과 같은 숫자 특성을 기본 특성으로 사용하여 시스템은 모든 고객과 비교할 때 숫자 특성의 평균값이 높거나 낮은 세그먼트를 제안합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-142">With a numeric attribute like *annual income* or *membership period* as the primary attribute, the system suggests segments that have a higher or lower average value of the numeric attribute when compared to all customers.</span></span>

<span data-ttu-id="3f4d6-143">기본 특성으로서 *고객 만족도* 와 같은 범주형 특성은 동일한 범주에 속한 모든 고객의 비율과 비교할 때 특정 범부에 속하는 고객 비율이 더 높거나 낮은 제안된 세그먼트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-143">A categorical attribute like *customer satisfaction* as the primary attribute results in suggested segments that have a higher or lower percentage of customers belonging to a particular category when compared to the percentage of all customers belonging to that same category.</span></span> <span data-ttu-id="3f4d6-144">예를 들어 *고객 만족도* 를 기본 특성으로 선택하면 이는 세 가지 범주(*낮음*, *중간* 및 *높음*)로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-144">For example, *customer satisfaction* is chosen as the primary attribute and it consists of three categories (*Low*, *Medium* and *High*).</span></span> <span data-ttu-id="3f4d6-145">각 범주의 경우 동일한 범주에 있는 모든 고객의 비율에 비해 해당 범주에 속하는 고객의 비율이 상당히 높거나 낮은 세그먼트가 제안됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-145">For each category, segments will be suggested that have a significantly higher or lower percentage of customers belonging to that category as compared to the proportion of all customers in same category.</span></span> <span data-ttu-id="3f4d6-146">모든 고객의 22%가 *높음* 만족도를 갖는 경우, 22%에 비해 *높은* 만족도를 가진 고객 비율이 상당히 높거나 낮은 세그먼트만 해당 범주에 대해 제안됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-146">If 22% of all customers have a *High* satisfaction, then, only segments that have a significantly higher or lower proportion of customers with a *High* satisfaction as compared to 22% will be suggested for that category.</span></span> <span data-ttu-id="3f4d6-147">마찬가지로 통계적으로 유의한 경우 각각의 다른 범주(*낮음* 및 *중간*)에 대해 세그먼트가 제안됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-147">Similarly, segments will be suggested for each of the other categories (*Low* and *Medium*) if they are statistically significant.</span></span>

> [!NOTE]
> <span data-ttu-id="3f4d6-148">현재는 최대 10개의 범주가 있는 기본 범주 특성만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-148">Currently, we only support primary categorical attributes that have up to 10 categories.</span></span> <span data-ttu-id="3f4d6-149">10개 이상의 범주가 있는 기본 특성을 기반으로 하는 세그먼트 제안을 보려면 일부 범주를 그룹화하여 범주 수를 10개 이하로 줄이는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-149">If you want to see segment suggestions based on a primary attribute with more than 10 categories, we recommend to group some of the categories to reduce the number of categories to 10 or fewer.</span></span> <span data-ttu-id="3f4d6-150">이 제한은 기본 특성에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-150">This limitation only applies to primary attributes.</span></span> <span data-ttu-id="3f4d6-151">영향을 미치는 범주 특성의 경우, 현재 최대 100개의 범주를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-151">For influencing categorical attributes, we currently support a maximum of 100 categories.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="3f4d6-152">제안된 세그먼트 생성</span><span class="sxs-lookup"><span data-stu-id="3f4d6-152">Generate suggested segments</span></span>

1. <span data-ttu-id="3f4d6-153">**세그먼트** 로 이동</span><span class="sxs-lookup"><span data-stu-id="3f4d6-153">Go to **Segments**.</span></span>

1. <span data-ttu-id="3f4d6-154">**제안(미리 보기)** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-154">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="3f4d6-155">**새로운 제안 받기** 를 선택하여 가이드 환경을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-155">Select **Get new suggestions** to start the guided experience.</span></span>

1. <span data-ttu-id="3f4d6-156">측정값 또는 고객 특성을 기본 특성으로 선택하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-156">Choose a measure or a customer attribute as the primary attribute and select **Next**.</span></span>

   :::image type="content" source="media/suggested-segments-primary-attribute.png" alt-text="제안된 세그먼트에서 제안을 위한 기본 특성 선택.":::

1. <span data-ttu-id="3f4d6-158">영향을 미치는 특성을 선택하고 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-158">Select the influencing attributes and select **Save**.</span></span>
   
   > [!TIP]
   > <span data-ttu-id="3f4d6-159">영향을 미치는 특성을 여러 개 선택하면 기본 특성에 미치는 영향을 평가할 가능성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-159">Selecting multiple influencing attributes improves the chances of evaluating how they influence the primary attribute.</span></span> <span data-ttu-id="3f4d6-160">기본 특성에 영향을 미치지 않는 특성은 포함하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-160">Don't include attributes that have no influence the primary attribute.</span></span> <span data-ttu-id="3f4d6-161">예를 들어 모든 고객이 특정 국가 출신인 경우 *국가* 특성은 결과에 영향을 미치지 않으므로 포함하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-161">For example, if all your customers are from a specific country, don't include the *country* attribute because it won't have any impact on the output.</span></span>

1. <span data-ttu-id="3f4d6-162">고객 프로필 및 선택한 특성의 수에 따라 선택한 특성을 처리하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-162">Depending on the number of customer profiles and selected attributes, it can take a few minutes to process the selected attributes.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="3f4d6-163">제안된 세그먼트의 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="3f4d6-163">View details of a suggested segment</span></span>

<span data-ttu-id="3f4d6-164">AI 모델이 제안을 생성하면 **세그먼트** > **제안(미리 보기)** 에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-164">Once the AI model has generated the suggestions, you'll find them listed on **Segments** > **Suggestions (preview)**.</span></span>
 
<span data-ttu-id="3f4d6-165">제안된 세그먼트를 선택하여 평균값과 세그먼트 구성원 수의 비교를 포함하여 해당 제안의 세부 정보를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-165">Select a suggested segment to review the details of that suggestion including a comparison of the average value and the number of segment members.</span></span> <span data-ttu-id="3f4d6-166">AI 모델이 선택한 세그먼트를 제안하기 위해 학습한 특성 값 또는 규칙을 검토할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-166">You can also review the attribute values or rules that the AI model learned to suggest the selected segment.</span></span>

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="3f4d6-167">제안을 세그먼트로 저장</span><span class="sxs-lookup"><span data-stu-id="3f4d6-167">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="3f4d6-168">**세그먼트** > **제안(미리 보기)** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-168">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="3f4d6-169">저장할 세그먼트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-169">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="3f4d6-170">측면 창에서 **세그먼트로 저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-170">In the side pane, select **Save as segment**.</span></span> 

1. <span data-ttu-id="3f4d6-171">세그먼트를 저장하면 **모든 세그먼트** 탭의 세그먼트 목록에 표시됩니다. 이제 [다른 세그먼트와 마찬가지로 새로 고침, 편집 또는 삭제](segments.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-171">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed, edited, or deleted like any other segment](segments.md).</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="3f4d6-172">제안 모음 새로 고침 또는 편집</span><span class="sxs-lookup"><span data-stu-id="3f4d6-172">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="3f4d6-173">**세그먼트** > **제안(미리 보기)** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-173">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="3f4d6-174">**제안 새로 고침** 을 선택하여 구성된 특성을 유지하면서 제안을 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-174">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="3f4d6-175">또는 **특성 편집** 을 선택하여 구성된 특성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-175">Or select **Edit attributes** to modify the configured attributes.</span></span> <span data-ttu-id="3f4d6-176">시스템은 AI 모델을 다시 실행하여 최신 데이터를 기반으로 세그먼트 제안을 생성하고 현재 제안을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-176">The system will rerun the AI model, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

## <a name="limitations"></a><span data-ttu-id="3f4d6-177">제한 사항</span><span class="sxs-lookup"><span data-stu-id="3f4d6-177">Limitations</span></span>

1. <span data-ttu-id="3f4d6-178">예상 세그먼트 크기 불일치: 빈 값이 포함된 기본 특성을 선택하면 세그먼트 제안에서 예상 세그먼트 크기에 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-178">Estimated segment size mismatch: If you choose a primary attribute that contains empty values, it can affect the estimated segment size in the segment suggestions.</span></span> <span data-ttu-id="3f4d6-179">이러한 세그먼트를 저장할 때 실제 세그먼트 크기는 원래 예상치와 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-179">When saving such segment, the actual segment size can be different to the original estimation.</span></span>
 
2. <span data-ttu-id="3f4d6-180">부울 유형의 기본 특성이 작동하지 않음 : 현재는 문자열 및 숫자 유형의 데이터만 기본 특성으로 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-180">Boolean type primary attributes don't work: Currently, we only support string and numeric types of data as the primary attribute.</span></span>

3. <span data-ttu-id="3f4d6-181">제안된 세그먼트가 확실히 구별되지 않음: 선택한 특성과 해당 특성의 값 분포가 결과에 영향을 미친다는 점을 기억하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-181">Suggested segments aren't distinct enough: Keep in mind that the selected attributes and the distribution of values of those attributes influences the results.</span></span> <span data-ttu-id="3f4d6-182">영향을 미치는 특성 또는 기본 특성을 변경하여 다른 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4d6-182">You can change your influencing attributes or even your primary attribute to get different results.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]