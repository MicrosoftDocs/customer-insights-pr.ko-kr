---
title: 예측 시나리오를 위해 공유된 작업
description: 예측을 관리, 문제 해결 및 구체화하는 방법을 알아봅니다.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095728"
---
# <a name="manage-predictions"></a><span data-ttu-id="08373-103">예측 관리</span><span class="sxs-lookup"><span data-stu-id="08373-103">Manage predictions</span></span>

<span data-ttu-id="08373-104">이 문서에서는 대부분의 예측 시나리오에서 공유하는 몇 가지 작업에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="08373-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="08373-105">실패한 예측 문제 해결</span><span class="sxs-lookup"><span data-stu-id="08373-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="08373-106">**인텔리전스** > **예측** 으로 이동하고 **내 예측** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="08373-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="08373-107">오류 로그를 보려는 예측 옆에 있는 세로 줄임표를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="08373-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="08373-108">**로그** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="08373-108">Select **Logs**.</span></span>

1. <span data-ttu-id="08373-109">모든 오류를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="08373-109">Review all the errors.</span></span> <span data-ttu-id="08373-110">발생할 수 있는 여러 유형의 오류가 있으며 오류를 일으킨 조건을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="08373-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="08373-111">예를 들어 정확하게 예측하기에 데이터가 충분하지 않은 오류는 일반적으로 추가 데이터를 Customer Insights에 로드하여 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="08373-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="08373-112">입력 데이터 사용성 보고서</span><span class="sxs-lookup"><span data-stu-id="08373-112">Input data usability report</span></span>

<span data-ttu-id="08373-113">입력 데이터 사용성 보고서는 기본 제공 예측이 생성할 수 있는 오류 및 경고에 대한 통합 보기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="08373-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="08373-114">또한 모델 성능을 개선하는 방법에 대한 권장 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="08373-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="08373-115">이 보고서는 모델이 학습 프로세스를 완료한 후에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08373-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="08373-116">성공적으로 완료되었는지 여부와 관계없이 각 모델에 대해 별도로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="08373-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

> [!NOTE]
> <span data-ttu-id="08373-117">현재 이 기능은 트랜잭션 이탈 모델에서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="08373-117">Currently, this feature only works for the Transaction Churn model.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="08373-118">입력 데이터 사용성 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="08373-118">View the input data usability report</span></span>

<span data-ttu-id="08373-119">기본 제공 모델이 학습 단계를 완료한 후 보고서를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="08373-119">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="08373-120">모델 이름 옆에 있는 줄임표를 선택하고 **입력 데이터 사용성 보고서** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="08373-120">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="08373-121">모델 상태를 선택하고 측면 창에서 **입력 데이터 사용성 보고서 보기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="08373-121">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="08373-122">목록에서 모델 중 하나를 선택하고 명령 모음에서 **입력 데이터 사용성 보고서** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="08373-122">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="08373-123">모델 결과 페이지를 열고 명령 모음에서 **입력 데이터 사용성 보고서** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="08373-123">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="08373-124">입력 데이터 사용성 보고서의 정보</span><span class="sxs-lookup"><span data-stu-id="08373-124">Information in the input data usability report</span></span>

<span data-ttu-id="08373-125">보고서의 다음 열에는 모델의 데이터를 개선하는 데 유용한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08373-125">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="오류, 경고 및 권장 사항이 있는 테이블을 보여주는 입력 데이터 사용성 보고서의 예입니다.":::

- <span data-ttu-id="08373-127">이름: 오류, 경고 또는 권장 사항을 설명하는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="08373-127">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="08373-128">단계: 모델 단계, 훈련 또는 점수, 참조 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="08373-128">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="08373-129">상태: 정보의 심각도(오류, 경고, 권장 사항)입니다.</span><span class="sxs-lookup"><span data-stu-id="08373-129">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="08373-130">열 이름: 모델 성능을 개선하기 위해 수정해야 하는 엔터티의 열입니다.</span><span class="sxs-lookup"><span data-stu-id="08373-130">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="08373-131">엔터티 이름: 모델 성능을 개선하기 위해 수정해야 하는 엔터티의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="08373-131">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="08373-132">세부 정보: 오류, 경고 또는 권장 사항에 대한 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="08373-132">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="08373-133">예측 새로 고침</span><span class="sxs-lookup"><span data-stu-id="08373-133">Refresh a prediction</span></span>

<span data-ttu-id="08373-134">예측은 설정에서 구성된 대로 [데이터 새로 고침 예약](system.md#schedule-tab)에 자동으로 동일하게 갱신됩니다.</span><span class="sxs-lookup"><span data-stu-id="08373-134">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="08373-135">수동으로도 새로 고칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08373-135">You can refresh them manually too.</span></span>

1. <span data-ttu-id="08373-136">**인텔리전스** > **예측** 으로 이동하고 **내 예측** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="08373-136">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="08373-137">새로 고치려는 예측 옆의 세로 줄임표를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="08373-137">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="08373-138">**새로 고침** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="08373-138">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="08373-139">예측 삭제</span><span class="sxs-lookup"><span data-stu-id="08373-139">Delete a prediction</span></span>

<span data-ttu-id="08373-140">예측을 삭제하면 출력 엔터티도 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="08373-140">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="08373-141">**인텔리전스** > **예측** 으로 이동하고 **내 예측** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="08373-141">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="08373-142">삭제하려는 예측 옆의 세로 줄임표를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="08373-142">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="08373-143">**삭제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="08373-143">Select **Delete**.</span></span>
