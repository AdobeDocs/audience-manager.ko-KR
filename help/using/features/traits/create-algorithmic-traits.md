---
description: 알고리즘 특성 생성 프로세스에 고유한 설정 단계 및 기능에 대해 설명합니다.
seo-description: 알고리즘 특성 생성 프로세스에 고유한 설정 단계 및 기능에 대해 설명합니다.
seo-title: 알고리즘 트레이트 만들기
solution: Audience Manager
title: 알고리즘 트레이트 만들기
uuid: 50c2d2d1-f412-479b-bb70-4f139429c388
feature: Traits
translation-type: tm+mt
source-git-commit: aeaf8b14e901b4a39486ba3740f0582c9cf34559
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 5%

---


# 알고리즘 트레이트 만들기 {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

알고리즘 트레이트를 만들려면 아래 단계 [!UICONTROL Traits] 로 이동하여 수행합니다.

1. 을 클릭하고 드롭다운 메뉴 **[!UICONTROL Create New Trait]** **[!UICONTROL Algorithmic]** 에서 선택합니다.
1. 기본 [정보](../../features/traits/create-onboarded-rule-based-traits.md) 섹션
   * 트레이트의 이름을 지정합니다.
   * 데이터 소스를 선택합니다.
   * 저장소 폴더를 선택합니다.
1. 창을 [!UICONTROL Configuration] 열고 을 클릭합니다 **[!UICONTROL Browse All Models]**.
트레이트와 함께 사용할 모델을 선택할 수 있는 새 창이 열립니다.
1. 모델을 선택하고 을 클릭합니다 **[!UICONTROL Add Selected Model to Trait]**.

   >[!NOTE]
   > 
   > 선택한 모델을 기존 알고리즘 특성으로 바꿀 수 없습니다. 다른 모델을 사용하려면 새로운 알고리즘 특성을 만들어야 합니다.

   모델을 추가하면 도달 및 정확도 설정이 표시됩니다.
1. 목표로 도달 또는 정확도를 선택하고 각각의 드롭다운 메뉴에서 값을 선택합니다. 완료되면 을 **[!UICONTROL Save]** 클릭합니다.

## 알고리즘 트레이트를 위한 구성 설정 {#configure-settings}

에서 [!UICONTROL Trait Builder]이 [!UICONTROL Configuration] 섹션에서 알고리즘 모델을 트레이트에 연결할 수 있습니다. 알고리즘 특성 생성 프로세스를 완료하려면 모델을 선택하고 도달 또는 정확도 목표를 선택합니다.

### 사전 요구 사항

<!-- r_algo_trait_config_section.xml -->

* [유사 모델 만들기](../../features/algorithmic-models/create-model.md).
* 모델 데이터 실행이 완료되었음을 알 수 있는 알림 이메일을 기다립니다.
* 기본 정보 섹션에서 [필수 필드를](../../features/traits/create-onboarded-rule-based-traits.md) 완료합니다.

### 구성 필드 및 설정

| 인터페이스 요소 | 설명 |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | 단추를 **[!UICONTROL Update]** 클릭하여 모델 창을 엽니다. 창에서 트레이트를 만드는 데 사용할 알고리즘 모델을 선택합니다. |
| **[!UICONTROL Select Goal Accuracy]** | 정확도를 기반으로 트레이트를 만들려면 이 옵션을 선택합니다. 정확도는 잠재적인 사용자가 기준선에 얼마나 가까운지를 나타내는 점수의 값입니다. 정확도 척도의 범위는 0(가장 정확하지 않음)부터 1(가장 정확함)까지입니다. |
| **[!UICONTROL Reach and Accuracy Data Columns]** | 오른쪽에 있는 이 섹션에는 모델의 정확도와 도달 값을 표시하는 숫자 데이터 행이 최대 21개까지 표시됩니다. |
| **[!UICONTROL Reach and Accuracy Slider]** | 그래프 아래쪽에 있는 슬라이더를 사용하면 도달 또는 정확도 목표에 대해 숫자 값을 설정할 수 있습니다. 슬라이더를 설정한 다음 도달 또는 정확도 목표 단추를 선택하여 트레이트를 만들 수 있습니다. |

>[!MORELIKETHIS]
>
>* [정확성 및 도달 범위](../../features/traits/trait-accuracy-reach.md)

