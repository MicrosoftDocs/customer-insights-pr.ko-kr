---
title: 예측 시나리오를 위해 공유된 작업
description: 예측을 관리, 문제 해결 및 구체화하는 방법을 알아봅니다.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8ff8d70ffb8489def072e5d8a6e43d062594141a
ms.sourcegitcommit: 696ad9ab6e10046c00f1ac86a7e8fc37386e6fe7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2022
ms.locfileid: "8555321"
---
# <a name="manage-predictions"></a>예측 관리

이 문서에서는 대부분의 예측 시나리오에서 공유하는 몇 가지 작업에 대해 설명합니다.

## <a name="troubleshoot-a-failed-prediction"></a>실패한 예측 문제 해결

1. **인텔리전스** > **예측** 으로 이동하고 **내 예측** 탭을 선택합니다.

1. 오류 로그를 보려는 예측 옆에 있는 세로 줄임표를 선택합니다.

1. **로그** 를 선택합니다.

1. 모든 오류를 검토합니다. 발생할 수 있는 여러 유형의 오류가 있으며 오류를 일으킨 조건을 설명합니다. 예를 들어 정확하게 예측하기에 데이터가 충분하지 않은 오류는 일반적으로 추가 데이터를 Customer Insights에 로드하여 해결됩니다.

## <a name="input-data-usability-report"></a>입력 데이터 사용성 보고서

입력 데이터 사용성 보고서는 기본 제공 예측이 생성할 수 있는 오류 및 경고에 대한 통합 보기를 제공합니다. 또한 모델 성능을 개선하는 방법에 대한 권장 사항을 제공합니다.

이 보고서는 모델이 학습 프로세스를 완료한 후에 사용할 수 있습니다. 성공적으로 완료되었는지 여부와 관계없이 각 모델에 대해 별도로 생성됩니다.

### <a name="view-the-input-data-usability-report"></a>입력 데이터 사용성 보고서 보기

기본 제공 모델이 학습 단계를 완료한 후 보고서를 확인합니다.
- 모델 이름 옆에 있는 줄임표를 선택하고 **입력 데이터 사용성 보고서** 를 선택합니다.
- 모델 상태를 선택하고 측면 창에서 **입력 데이터 사용성 보고서 보기** 를 선택합니다.
- 목록에서 모델 중 하나를 선택하고 명령 모음에서 **입력 데이터 사용성 보고서** 를 선택합니다.
- 모델 결과 페이지를 열고 명령 모음에서 **입력 데이터 사용성 보고서** 를 선택합니다.

### <a name="information-in-the-input-data-usability-report"></a>입력 데이터 사용성 보고서의 정보

보고서의 다음 열에는 모델의 데이터를 개선하는 데 유용한 정보가 포함되어 있습니다.

:::image type="content" source="media/input-data-usability-report.png" alt-text="오류, 경고 및 권장 사항이 있는 테이블을 보여주는 입력 데이터 사용성 보고서의 예입니다.":::

- **이름:** 오류, 경고 또는 권장 사항을 설명하는 이름입니다.
- **단계:** 모델 단계, 훈련 또는 점수, 참조 정보입니다.
- **상태:** 정보의 심각도(오류, 경고, 권장 사항)입니다.
- **열 이름:** 모델 성능을 개선하기 위해 수정해야 하는 엔터티의 열입니다.
- **엔터티 이름:** 모델 성능을 개선하기 위해 수정해야 하는 엔터티의 이름입니다.
- **세부 정보:** 오류, 경고 또는 권장 사항에 대한 세부 정보입니다.

## <a name="refresh-a-prediction"></a>예측 새로 고침

예측은 설정에서 구성된 대로 [데이터 새로 고침 예약](system.md#schedule-tab)에 자동으로 동일하게 갱신됩니다. 수동으로도 새로 고칠 수 있습니다.

1. **인텔리전스** > **예측** 으로 이동하고 **내 예측** 탭을 선택합니다.

1. 새로 고치려는 예측 옆의 세로 줄임표를 선택합니다.

1. **새로 고침** 을 선택합니다.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="delete-a-prediction"></a>예측 삭제

예측을 삭제하면 출력 엔터티도 제거됩니다.

1. **인텔리전스** > **예측** 으로 이동하고 **내 예측** 탭을 선택합니다.

1. 삭제하려는 예측 옆의 세로 줄임표를 선택합니다.

1. **삭제** 를 선택합니다.
