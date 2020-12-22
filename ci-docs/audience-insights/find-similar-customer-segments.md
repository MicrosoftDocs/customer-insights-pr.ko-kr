---
title: AI로 유사 고객 찾기
description: 인공 지능으로 유사한 고객 세그먼트를 찾으십시오.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 8cdec4edd599b0249fcf144b5e5c0124504e1e14
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406295"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="a8ee4-103">유사한 고객(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="a8ee4-103">Similar Customers (preview)</span></span>

<span data-ttu-id="a8ee4-104">이 기능을 사용하면 인공 지능을 사용하여 고객 기반에서 유사한 고객을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="a8ee4-105">이 기능을 사용하려면 하나 이상의 세그먼트를 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="a8ee4-106">기존 세그먼트의 기준을 확장하면 해당 세그먼트와 유사한 고객을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="a8ee4-107">*유사한 고객 찾기* 는 자동화된 수단을 사용하여 데이터를 평가하고 해당 데이터를 기반으로 예측을 수행하므로 일반 데이터 보호 규정("GDPR")에 의해 정의된 대로 프로파일링 방법으로 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="a8ee4-108">고객이 데이터를 처리하기 위해 이 기능을 사용하는 경우 GDPR 또는 기타 법률 또는 규정이 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="a8ee4-109">귀하는 예측을 포함한 Dynamics 365 Customer Insights 사용이 개인 정보 보호, 개인 데이터, 생체 인식 데이터, 데이터 보호 및 통신 기밀과 관련된 법률을 포함하여 모든 관련 법률 및 규정을 준수하는지 확인할 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="a8ee4-110">유사한 고객 찾기</span><span class="sxs-lookup"><span data-stu-id="a8ee4-110">Finding similar customers</span></span>

1. <span data-ttu-id="a8ee4-111">대상 그룹 인사이트에서 **세그먼트** 로 이동하여 새 세그먼트의 기반이 될 세그먼트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="a8ee4-112">그것이 *원본 세그먼트* 입니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="a8ee4-113">작업 표시줄에서 **유사한 고객 찾기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="a8ee4-114">새 세그먼트의 제안된 이름을 검토하고 필요한 경우 변경하십시오.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="a8ee4-115">새 세그먼트를 정의하는 필드를 검토하십시오.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="a8ee4-116">이 필드는 시스템이 원본 세그먼트와 유사한 고객을 찾으려고 하는 기초를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="a8ee4-117">시스템은 기본적으로 권장 필드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="a8ee4-118">모델 성능을 크게 저하시킬 수 있는 필드는 자동으로 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="a8ee4-119">StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType과 같은 데이터 유형이 있는 필드</span><span class="sxs-lookup"><span data-stu-id="a8ee4-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="a8ee4-120">카디널리티(필드의 요소 수)가 2보다 작거나 30보다 큰 필드</span><span class="sxs-lookup"><span data-stu-id="a8ee4-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="a8ee4-121">**모든 고객** 또는 새 세그먼트에서 **기존 특정 세그먼트** 의 고객만 포함하려면 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="a8ee4-122">**원본 세그먼트에서 모든 사람 제외** 확인란을 선택해 원본 세그먼트에서 고객을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="a8ee4-123">기본적으로 시스템은 출력에 대상 그룹 크기의 20%만 포함하도록 제안합니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="a8ee4-124">필요에 따라 이 임계값을 편집하십시오.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-124">Edit this threshold as needed.</span></span> <span data-ttu-id="a8ee4-125">임계값을 높이면 정밀도가 떨어집니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="a8ee4-126">페이지 하단에서 **실행** 을 선택해 데이터 집합을 분석하는 이진 분류 작업(기계 학습의 방법)을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="a8ee4-127">유사한 세그먼트 보기</span><span class="sxs-lookup"><span data-stu-id="a8ee4-127">View the similar segment</span></span>

<span data-ttu-id="a8ee4-128">유사한 세그먼트를 처리한 후 새로운 세그먼트가 **세그먼트** 페이지에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a8ee4-129">![유사한 고객 세그먼트](media/expanded-segment.png "유사한 고객 세그먼트")</span><span class="sxs-lookup"><span data-stu-id="a8ee4-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="a8ee4-130">작업 표시줄에서 **보기** 를 선택해 세그먼트 세부 정보를 여십시오.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="a8ee4-131">이 보기에는 [유사성 점수](#about-similarity-scores)의 결과 분포에 대한 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="a8ee4-132">또한 유사성 점수 값은 **세그먼트 구성원 미리 보기** 에서 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="a8ee4-133">유사한 세그먼트의 출력 사용</span><span class="sxs-lookup"><span data-stu-id="a8ee4-133">Use the output of a similar segment</span></span>

<span data-ttu-id="a8ee4-134">다른 세그먼트와 마찬가지로 [유사한 세그먼트의 출력으로 작업](segments.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="a8ee4-135">예를 들어, 세그먼트를 내보내거나 측정값을 작성하십시오.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="a8ee4-136">유사한 세그먼트 새로 고침 및 편집</span><span class="sxs-lookup"><span data-stu-id="a8ee4-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="a8ee4-137">유사한 세그먼트를 새로 고치려면 **세그먼트** 페이지를 선택하고 작업 표시줄에서 **새로 고침** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="a8ee4-138">유사한 세그먼트를 수정하면 데이터가 다시 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="a8ee4-139">이전에 생성된 세그먼트는 새로 고친 데이터로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="a8ee4-140">유사한 세그먼트를 편집하려면 **세그먼트** 페이지를 선택하고 작업 표시줄에서 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="a8ee4-141">변경 사항을 적용하고 **실행** 을 선택해 처리를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="a8ee4-142">유사한 세그먼트 삭제</span><span class="sxs-lookup"><span data-stu-id="a8ee4-142">Delete a similar segment</span></span>

<span data-ttu-id="a8ee4-143">**세그먼트** 페이지에서 세그먼트를 선택하고 작업 표시줄에서 **삭제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="a8ee4-144">그런 다음 삭제를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="a8ee4-145">유사성 점수 정보</span><span class="sxs-lookup"><span data-stu-id="a8ee4-145">About similarity scores</span></span>

<span data-ttu-id="a8ee4-146">이진 분류 기계 학습 모델은 유사한 세그먼트의 고객에게 점수를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="a8ee4-147">점수는 원본세그먼트의 고객과의 유사성을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="a8ee4-148">0.55 미만의 유사성 점수는 시스템이 원본 세그먼트의 고객과 *비슷하지 않다* 고 분류한 고객입니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="a8ee4-149">0.55 – 0.7 사이의 유사성 점수는 *다소 유사* 로 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="a8ee4-150">0.7 – 0.85 사이의 유사성 점수는 *유사* 로 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="a8ee4-151">0.85 – 1 사이의 유사성 점수는 시스템이 *매우 유사* 로 분류한 고객입니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="a8ee4-152">유사성 점수가 0.4 미만인 고객은 모델 출력에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="a8ee4-153">시스템은 이를 원본 세그먼트와 비슷한 것으로 간주하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8ee4-153">The system doesn't consider them similar enough to the source segment.</span></span>
