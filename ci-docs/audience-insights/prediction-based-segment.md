---
title: 예측 출력을 기반으로 한 세그먼트
description: 예측 모델의 출력 엔터티를 기반으로 세그먼트를 만듭니다.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741437"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="ac182-103">예측 모델을 기반으로 세그먼트 만들기(프리뷰)</span><span class="sxs-lookup"><span data-stu-id="ac182-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="ac182-104">예측 결과는 때때로 고객의 하위 집합에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac182-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="ac182-105">예측 모델의 결과에서 세그먼트를 만들어 추천 맞춤 설정을 높입니다.</span><span class="sxs-lookup"><span data-stu-id="ac182-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="ac182-106">예를 들어 특정 유형의 서비스를 선호하는 고객에게 특정 권장 사항을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac182-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="ac182-107">필요한 항목</span><span class="sxs-lookup"><span data-stu-id="ac182-107">Prerequisites</span></span>

- <span data-ttu-id="ac182-108">Customer Insights에 최소한 [기여자 권한](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="ac182-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="ac182-109">Customer Insights에 구성된 제품 추천, 트랜잭션 이탈, 구독 이탈 또는 고객 평생 가치 모델.</span><span class="sxs-lookup"><span data-stu-id="ac182-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="ac182-110">다양한 모델을 설정하기 위한 요구 사항을 검토하십시오.</span><span class="sxs-lookup"><span data-stu-id="ac182-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="ac182-111">제품 추천 모델</span><span class="sxs-lookup"><span data-stu-id="ac182-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="ac182-112">구독 이탈 모델(프리뷰)</span><span class="sxs-lookup"><span data-stu-id="ac182-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="ac182-113">트랜잭션 이탈 모델</span><span class="sxs-lookup"><span data-stu-id="ac182-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="ac182-114">고객 평생 가치 모델</span><span class="sxs-lookup"><span data-stu-id="ac182-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="ac182-115">예측을 기반으로 고객 세그먼트 생성</span><span class="sxs-lookup"><span data-stu-id="ac182-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="ac182-116">**인텔리전스** > **예측** 으로 이동하고 **내 예측** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ac182-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="ac182-117">검토할 모델 옆에 있는 수직 줄임표를 선택하고 **보기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ac182-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="ac182-118">결과 페이지에서 **세그먼트 생성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ac182-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="ac182-119">결과 페이지에 대한 자세한 내용은 모델에 대한 문서를 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="ac182-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="세그먼트 만들기 작업이 강조 표시된 예측 결과 페이지의 스크린 샷":::

1. <span data-ttu-id="ac182-121">선택한 모델의 출력 엔터티를 기반으로 새 세그먼트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ac182-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="ac182-122">자세한 내용은 [세그먼트 만들기 및 관리](segments.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ac182-122">For more information, see [Create and manage segments](segments.md).</span></span>