---
description: Predictive Audiences을 사용하면 데이터 과학을 사용하여 알 수 없는 대상을 실시간으로 개별 성향으로 분류할 수 있습니다.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences Reporting
solution: Audience Manager
title: Predictive Audiences 보고
feature: Algorithmic Models
exl-id: 43a4272c-d9be-47f6-9b81-15472b0366ab
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 3%

---

# Predictive Audiences 보고

저장 후 [!UICONTROL Predictive Audiences] 모델, Audience Manager이 교육을 시작합니다. 몇 시간 이내에 계산된 모델은 의 대상자 분석을 시작합니다. [데이터 수집 서버](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/system-components/components-data-collection.html#dcs-pcs). 보고는 다음 날에 사용할 수 있습니다.

결과를 확인하려면 [!UICONTROL Predictive Audiences] 분류, 이동 **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**&#x200B;을 클릭하고 목록에서 모델을 클릭합니다.

왼쪽의 필터링 옵션을 사용하여 모델 이름을 검색하거나 모델 유형을 기반으로 결과를 필터링합니다.

![predictive-audiences-filter](assets/predictive-audiences-filter-models.png)

모델 테이블에는 다음 정보가 표시됩니다.

* **[!UICONTROL ID]**: 모델 ID는 Audience Manager 계정에서 각 모델을 고유하게 식별합니다.
* **[!UICONTROL Name]**: 모델 생성 단계에서 제공한 이름;
* **[!UICONTROL Description]**: 모델 생성 단계에서 제공한 설명입니다.
* **[!UICONTROL Model Type]**: 각 모델의 유형([!UICONTROL Look-Alike Modeling] 또는 [!UICONTROL Predictive Audiences]);
* **[!UICONTROL Status]**: 각 모델의 상태:
   * **[!UICONTROL Pending]**: 모델을 초기화하고 있으며 곧 결과를 생성합니다.
   * **[!UICONTROL Active]**: 모델이 성공적으로 실행되고 결과가 나옵니다.
   * **[!UICONTROL Warning]**: 데이터 부족으로 인해 모델이 결과를 내놓지 못했습니다(즉, 기준선 인구가 적고 사용자 프로필이 풍부하지 않음).
   * **[!UICONTROL Error]**: 모델을 실행하지 못했습니다. Adobe 담당자에게 문의하십시오.

## 모델 개요 보고서{#model-report}

모델을 선택하면 해당 보고 페이지가 로드됩니다. 페이지 상단에서 모델이 타겟 대상자를 분류한 기준 1일 실시간 실현을 기반으로 하는 상위 5개의 가장 큰 예측 세그먼트를 볼 수 있습니다. 다음 **[!UICONTROL Other]** 카테고리는 상위 5개의 가장 큰 예측 세그먼트에 포함되지 않은 나머지 가상 사용자를 포함합니다.

Audience Manager에 색상 코드 도넛 차트와 타임라인 그래프가 모두 표시됩니다. [!UICONTROL Predictive Audiences].

페이지 상단에 있는 가상 사용자 탭을 클릭하면 차트 및 그래프에서 가상 사용자가 추가되거나 제거됩니다.

도넛 차트는 타겟 대상의 성향 기반 분류를 보여 주는 반면 그래프는 지난 6일 동안의 예측 세그먼트의 1일 실시간 모집단 트렌드를 보여 줍니다.

모델 상태가 인 경우 [!UICONTROL Pending], [!UICONTROL Warning], 또는 [!UICONTROL Error]를 지정하면 그래프 대신 모델 상태가 표시됩니다.

![smart-persona-report](assets/predictive-audiences-report.png)

보고서 테이블에는 각각에 대한 다음 정보가 표시됩니다 [!UICONTROL Predictive Audiences] 세그먼트.

1. **[!UICONTROL SEGMENT ID]**: 각 담당자와 연결된 자동 생성된 세그먼트의 세그먼트 ID
1. **[!UICONTROL NAME]**: 성향 이름;
1. **[!UICONTROL STATUS]**: 의 상태 [!UICONTROL Predictive Audiences] 세그먼트:
   * **[!UICONTROL Succeeded]**: 사용자가 이 세그먼트로 분류됨;
   * **[!UICONTROL Pending]**: 세그먼트가 아직 초기화 중입니다.
   * **[!UICONTROL Insufficient Training Data]**: 데이터가 충분하지 않아 사용자가 이 세그먼트로 분류되지 않습니다. 총 기준 모집단이 너무 낮아서 학습할 데이터를 충분히 제공하지 않습니다.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]**: 지난 24시간 동안 각 성향에 대한 세그먼트 실현 수입니다.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]**: 지난 24시간 동안 총 모델 모집단 중 각 성향에 대한 세그먼트 실현의 백분율입니다.

## 영향력 있는 트레이트{#influential-traits}

[!UICONTROL Influential Traits] 는 다음과 같은 트레이트입니다. [!UICONTROL Predictive Audiences] 방문자의 성향 분류를 결정하는 가장 강력한 예측 변수로 발견된 알고리즘입니다.

이 기호는 트레이트가 있는지(+) 또는 사용자가 선택한 성향에 속할 가능성이 증가하는지(-) 여부를 나타냅니다.

모든 성향에 대해 영향력 있는 트레이트를 보려면 [!UICONTROL View All Influential Traits].

다음 [!UICONTROL Influential Traits] 창에는 선택한 모델의 각 담당자에 대한 다음 정보가 표시됩니다.

![영향력 있는 트레이트](assets/predictive-audiences-influential-traits.png)

1. **[!UICONTROL TRAIT ID]**: 선택한 담당자에 대해 영향을 주는 각 트레이트의 트레이트 ID;
1. **[!UICONTROL NAME]**: 선택한 담당자에 대해 영향을 주는 각 트레이트의 이름
1. **[!UICONTROL DESCRIPTION]**: 선택한 담당자에 대해 영향을 주는 각 트레이트에 대한 설명
1. **[!UICONTROL WEIGHT]**: 선택한 성향에 대해 영향을 주는 각 트레이트의 가중치입니다. [!UICONTROL Influential Traits] 기본적으로 내림차순으로 중량 기준으로 정렬됩니다.  가중치의 값은 이들의 예측 능력을 나타낸다. 기호는 트레이트의 존재가 어떤 성향에 속할 가능성을 증가(+)하는지 아니면 감소(-)하는지를 나타낸다.
1. **[!UICONTROL 30 DAY REAL TIME POPULATION]**: 지난 30일 동안 선택한 담당자에 대해 각 영향력 있는 트레이트에 대한 고유한 트레이트 실현 수입니다.
