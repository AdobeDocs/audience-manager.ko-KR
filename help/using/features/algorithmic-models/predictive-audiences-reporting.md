---
description: Predictive Audiences을 사용하면 데이터 과학을 사용하여 알 수 없는 대상을 실시간으로 개별 성향으로 분류할 수 있습니다.
seo-description: Predictive Audiences을 사용하면 데이터 과학을 사용하여 알 수 없는 대상을 실시간으로 개별 성향으로 분류할 수 있습니다.
seo-title: Predictive Audiences 보고
solution: Audience Manager
title: Predictive Audiences 보고
feature: 알고리즘 모델
exl-id: 43a4272c-d9be-47f6-9b81-15472b0366ab
source-git-commit: 03f039a1317576c7979a5cb4c3cffc543e3bd656
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 6%

---

# Predictive Audiences 보고

[!UICONTROL Predictive Audiences] 모델을 저장한 후 Audience Manager이 교육을 시작합니다. 두 시간 내에 계산된 모델은 [데이터 수집 서버](https://docs.adobe.com/content/help/en/audience-manager/user-guide/reference/system-components/components-data-collection.html#dcs-pcs)에서 대상 분석을 시작합니다. 보고 기능은 다음 날 사용할 수 있습니다.

[!UICONTROL Predictive Audiences] 분류 결과를 보려면 **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** 로 이동한 다음 목록에서 모델을 클릭합니다.

왼쪽에 있는 필터링 옵션을 사용하여 모델 이름을 검색하거나 모델 유형에 따라 결과를 필터링합니다.

![predictive-audiences-filter](assets/predictive-audiences-filter-models.png)

모델 테이블에는 다음 정보가 표시됩니다.

* **[!UICONTROL ID]**:모델 ID는 Audience Manager 계정에서 각 모델을 고유하게 식별합니다.
* **[!UICONTROL Name]**:모델 생성 단계에서 제공한 이름
* **[!UICONTROL Description]**:모델 생성 단계에서 제공한 설명
* **[!UICONTROL Model Type]**:각 모델의 유형([!UICONTROL Look-Alike Modeling]  또는  [!UICONTROL Predictive Audiences]);
* **[!UICONTROL Status]**:각 모델의 상태:
   * **[!UICONTROL Pending]**:모델을 초기화하고 있으며 결과를 곧 생성합니다.
   * **[!UICONTROL Active]**:모델이 성공적으로 실행되고 결과를 생성합니다.
   * **[!UICONTROL Warning]**:데이터가 부족하여 모델이 결과를 생성하지 못했습니다(즉, 기준선 모집단이 적으면 사용자 프로필이 풍부하지 않음).
   * **[!UICONTROL Error]**:모델을 실행하지 못했습니다. Adobe 담당자에게 문의해야 합니다.

## 모델 개요 보고서{#model-report}

모델을 선택하면 해당 보고 페이지가 로드됩니다. 페이지 맨 위에서 모델이 타겟 대상을 분류한 1일의 실시간 실현을 기반으로 하여 상위 5개의 가장 큰 예측 세그먼트를 볼 수 있습니다. **[!UICONTROL Other]** 카테고리에는 상위 5개의 가장 큰 예측 세그먼트에 포함되지 않은 나머지 가상 사용자가 포함됩니다.

Audience Manager은 색상 코딩된 도넛 차트와 [!UICONTROL Predictive Audiences]에 대한 타임라인 그래프를 모두 표시합니다.

페이지 상단에 있는 개인화 탭을 클릭하면 차트와 그래프에서 해당 탭을 추가하거나 제거합니다.

도넛 차트는 타겟 대상의 성향 기반 분류를 보여주는 반면 그래프는 지난 6일 동안의 예측 세그먼트의 1일 실시간 인구 트렌드를 보여줍니다.

모델 상태가 [!UICONTROL Pending], [!UICONTROL Warning] 또는 [!UICONTROL Error]이면 그래프 대신 모델 상태가 표시됩니다.

![smart-persona-report](assets/predictive-audiences-report.png)

보고서 테이블에는 각 [!UICONTROL Predictive Audiences] 세그먼트에 대한 다음 정보가 표시됩니다.

1. **[!UICONTROL SEGMENT ID]**:각 성향에 연결된 자동 생성된 세그먼트의 세그먼트 ID입니다.
1. **[!UICONTROL NAME]**:페르소나 이름
1. **[!UICONTROL STATUS]**:세그먼트의  [!UICONTROL Predictive Audiences] 상태:
   * **[!UICONTROL Succeeded]**:사용자는 이 세그먼트로 분류됩니다.
   * **[!UICONTROL Pending]**:세그먼트가 아직 초기화되어 있습니다.
   * **[!UICONTROL Insufficient Training Data]**:데이터가 부족하여 사용자가 이 세그먼트로 분류되지 않습니다. 총 기준 모집단이 너무 작으며 학습할 충분한 데이터를 제공하지 않습니다.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]**:지난 24시간 동안 각 성향에 대한 세그먼트 실현 수입니다.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]**:총 모델 인구 중 지난 24시간 동안 각 성향에 대한 세그먼트 실현 비율입니다.

## 영향력 있는 트레이트{#influential-traits}

[!UICONTROL Influential Traits] 알고리즘이  [!UICONTROL Predictive Audiences] 방문자의 성향 분류를 결정하기 위한 가장 강력한 예측자가 되는 트레이트입니다.

해당 기호는 트레이트의 존재 여부가 선택한 성향에 속하는 사용자의 가능성이(+) 또는 감소하는지(-)를 나타냅니다.

모든 성향에 대해 영향을 주는 트레이트를 보려면 [!UICONTROL View All Influential Traits] 을 클릭하십시오.

[!UICONTROL Influential Traits] 창에는 선택한 모델의 각 사용자에 대한 다음 정보가 표시됩니다.

![영향력 있는 트레이트](assets/predictive-audiences-influential-traits.png)

1. **[!UICONTROL TRAIT ID]**:선택한 성향에 대한 각 영향력 있는 트레이트의 트레이트 ID입니다.
1. **[!UICONTROL NAME]**:선택한 사용자에 대한 각 영향력 있는 트레이트의 이름
1. **[!UICONTROL DESCRIPTION]**:선택한 사용자에 대한 각 영향력 있는 트레이트에 대한 설명
1. **[!UICONTROL WEIGHT]**:선택한 사용자에 대한 각 영향력 있는 트레이트의 가중치입니다. [!UICONTROL Influential Traits] 기본적으로 가중치를 기준으로 내림차순으로 정렬됩니다.  가중치 값은 예측 능력을 나타냅니다. 기호는 트레이트의 존재 여부가 성향에 속할 가능성이(+) 또는 감소하는지(-)를 나타냅니다.
1. **[!UICONTROL 30 DAY REAL TIME POPULATION]**:지난 30일 동안 선택한 성향에 대한 각 영향력 있는 트레이트의 고유 트레이트 실현 수입니다.
