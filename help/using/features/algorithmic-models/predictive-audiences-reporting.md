---
description: Predictive Audiences을 사용하면 데이터 과학을 사용하여 알 수 없는 대상을 실시간으로 개별 성향으로 분류할 수 있습니다.
seo-description: Predictive Audiences을 사용하면 데이터 과학을 사용하여 알 수 없는 대상을 실시간으로 개별 성향으로 분류할 수 있습니다.
seo-title: Predictive Audiences 보고
solution: Audience Manager
title: Predictive Audiences 보고
feature: 알고리즘 모델
exl-id: 43a4272c-d9be-47f6-9b81-15472b0366ab
translation-type: tm+mt
source-git-commit: 03f039a1317576c7979a5cb4c3cffc543e3bd656
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 6%

---

# Predictive Audiences 보고

[!UICONTROL Predictive Audiences] 모델을 저장한 후 Audience Manager에서 교육을 시작합니다. 몇 시간 내에 계산된 모델은 [데이터 수집 서버](https://docs.adobe.com/content/help/en/audience-manager/user-guide/reference/system-components/components-data-collection.html#dcs-pcs)에서 대상을 분석하기 시작합니다. 다음 날 보고를 사용할 수 있습니다.

[!UICONTROL Predictive Audiences] 분류 결과를 보려면 **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**&#x200B;로 이동한 다음 목록에서 모델을 클릭합니다.

왼쪽의 필터링 옵션을 사용하여 모델 이름을 검색하거나 모델 유형에 따라 결과를 필터링합니다.

![predictive-audiences-filter](assets/predictive-audiences-filter-models.png)

모델 테이블에는 다음 정보가 표시됩니다.

* **[!UICONTROL ID]**:모델 ID는 Audience Manager 계정의 각 모델을 고유하게 식별합니다.
* **[!UICONTROL Name]**:모델 생성 단계에서 제공한 이름;
* **[!UICONTROL Description]**:모델 생성 단계에서 제공한 설명;
* **[!UICONTROL Model Type]**:각 모델의 유형([!UICONTROL Look-Alike Modeling] 또는  [!UICONTROL Predictive Audiences]);
* **[!UICONTROL Status]**:각 모델의 상태:
   * **[!UICONTROL Pending]**:모델을 초기화 중이며 결과를 곧 생성할 것입니다.
   * **[!UICONTROL Active]**:모델이 성공적으로 실행되고 결과를 생성합니다.
   * **[!UICONTROL Warning]**:데이터가 부족하여(즉, 기준선 수가 적거나 사용자 프로필이 풍부하지 않음) 모델을 생성하지 못했습니다.
   * **[!UICONTROL Error]**:모델을 실행하지 못했습니다. Adobe 담당자에게 문의하십시오.

## 모델 개요 보고서{#model-report}

모델을 선택하면 해당 보고 페이지가 로드됩니다. 페이지 맨 위에는 1일의 실시간 실현을 기반으로 모델이 대상 고객을 분류한 상위 5개의 가장 큰 예측 세그먼트가 표시됩니다. **[!UICONTROL Other]** 카테고리에는 상위 5개의 가장 큰 예측 세그먼트에 포함되지 않은 나머지 개인 정보가 포함됩니다.

Audience Manager은 [!UICONTROL Predictive Audiences]에 대한 색상 코딩된 도넛형 차트와 타임라인 그래프를 모두 표시합니다.

페이지 맨 위에 있는 개인 탭을 클릭하면 차트와 그래프에서 해당 탭을 추가하거나 제거합니다.

도넛형 차트는 대상 고객의 성향 기반 분류를 보여주며 그래프는 지난 6일 동안 예측 세그먼트의 실시간 인구 트렌드를 보여줍니다.

모델 상태가 [!UICONTROL Pending], [!UICONTROL Warning] 또는 [!UICONTROL Error]이면 그래프 대신 모델 상태가 표시됩니다.

![smart-persona-report](assets/predictive-audiences-report.png)

보고서 표는 각 [!UICONTROL Predictive Audiences] 세그먼트에 대한 다음 정보를 보여줍니다.

1. **[!UICONTROL SEGMENT ID]**:각 페르소나와 연관된 자동 생성된 세그먼트의 세그먼트 ID.
1. **[!UICONTROL NAME]**:페르소나 이름;
1. **[!UICONTROL STATUS]**:세그먼트의  [!UICONTROL Predictive Audiences] 상태:
   * **[!UICONTROL Succeeded]**:사용자가 이 세그먼트로 분류됩니다.
   * **[!UICONTROL Pending]**:세그먼트가 아직 초기화되고 있습니다.
   * **[!UICONTROL Insufficient Training Data]**:데이터가 부족하여 사용자가 이 세그먼트로 분류되지 않습니다. 전체 기준 모집단 수가 너무 낮아 데이터를 충분히 제공하지 않습니다.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]**:지난 24시간 동안 각 가상 사용자에 대한 세그먼트 재지정 수입니다.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]**:전체 모델 인구 중 지난 24시간 동안 각 사용자에 대한 세그먼트 할당량의 비율입니다.

## 영향력 있는 트레이트{#influential-traits}

[!UICONTROL Influential Traits] 방문자의  [!UICONTROL Predictive Audiences] 페르소나 분류를 결정하기 위한 가장 강력한 예측자가 알고리즘으로 검색된 특성입니다.

해당 기호는 트레이트가 있는지(+) 또는 감소하는지(-)가 선택된 가상 사용자에 속하는 사용자의 가능성을 증가하는지 여부를 나타냅니다.

모든 성향에 대해 영향력있는 트레이트를 보려면 [!UICONTROL View All Influential Traits]을 클릭합니다.

[!UICONTROL Influential Traits] 창에는 선택한 모델의 각 사용자에 대한 다음 정보가 표시됩니다.

![영향력 있는 특성](assets/predictive-audiences-influential-traits.png)

1. **[!UICONTROL TRAIT ID]**:선택한 페르소나에 대한 각 영향력 있는 트레이트의 특성 ID
1. **[!UICONTROL NAME]**:선택한 페르소나에 대한 각 영향력 있는 트레이트의 이름;
1. **[!UICONTROL DESCRIPTION]**:선택한 사람에 대한 각 영향력 있는 트레이트에 대한 설명
1. **[!UICONTROL WEIGHT]**:선택된 사람에 대한 각각의 영향력 있는 트레이트의 무게. [!UICONTROL Influential Traits] 기본적으로 가중치별로 정렬되어 내림차순으로 정렬됩니다.  가중치의 값은 예측 능력을 나타냅니다. 기호는 트레이트가 있는지(+) 또는 감소했는지(-) 중에 페르소나에 속할 가능성이 있는지 여부를 나타냅니다.
1. **[!UICONTROL 30 DAY REAL TIME POPULATION]**:지난 30일 동안 선택한 페르소나에 대한 영향력 있는 각 트레이트에 대한 고유한 트레이트 실현의 수입니다.
