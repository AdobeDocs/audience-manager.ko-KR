---
description: 알고리즘 특성 작성 프로세스에 고유한 설정 및 기능에 대해 설명합니다.
seo-description: 알고리즘 특성 작성 프로세스에 고유한 설정 및 기능에 대해 설명합니다.
seo-title: 알고리즘 특성 만들기
solution: Audience Manager
title: 알고리즘 특성 만들기
uuid: 50 c 2 D 2 D 1-F 412-479 B-BB 70-4 F 139429 C 388
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create Algorithmic Traits {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

To create an algorithmic trait, go to [!UICONTROL Traits] and follow the steps below:

1. Click **[!UICONTROL Create New Trait]** and select **[!UICONTROL Algorithmic]** from the drop down menu.
1. In the [Basic Information](../../features/traits/create-onboarded-rule-based-traits.md) section
   * 특성 이름을 지정합니다.
   * 데이터 소스를 선택합니다.
   * 저장소 폴더를 선택합니다.
1. [!UICONTROL Configuration] 창을 확장하고 **[!UICONTROL Browse All Models]**를 클릭합니다.
이렇게 하면 트레이트와 함께 사용할 모델을 선택할 수 있는 새 창이 열립니다.
1. Select a model and click **[!UICONTROL Add Selected Model to Trait]**.
모델을 추가하면 도달 및 정확도 설정이 노출됩니다.
1. 도달 수 또는 정확도를 목표로 선택하고 해당 드롭다운 메뉴에서 값을 선택합니다. Click **[!UICONTROL Save]** when done.

>[!MORE_ like_ this]
>
>* [정확성 및 전달 범위](../../features/traits/trait-accuracy-reach.md)


## Configuration Settings for Algorithmic Traits {#configure-settings}

In [!UICONTROL Trait Builder], the [!UICONTROL Configuration] section lets you associate an algorithmic model to a trait. 알고리즘 특성 작성 프로세스를 완료하려면 모델을 선택하고 도달 또는 정확도 목표를 선택합니다.

### 전제 조건

<!-- r_algo_trait_config_section.xml -->

* [알고리즘 모델을](../../features/algorithmic-models/create-model.md#build-model)만들 수 있습니다.
* 모델 데이터 실행이 완료되었음을 알려주는 알림 이메일을 기다립니다.
* [기본 정보](../../features/traits/create-onboarded-rule-based-traits.md) 섹션의 필수 필드를 완료합니다.

### 구성 필드 및 설정

| 인터페이스 요소 | 설명 |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | **[!UICONTROL Update]** 단추를 클릭하여 모델 창을 엽니다. 창에서 특성 작성에 사용할 알고리즘 모델을 선택합니다. |
| **[!UICONTROL Select Goal Accuracy]** | 정확도를 기반으로 트레이트를 만들려면 이 옵션을 선택합니다. 정확도는 잠재적인 사용자가 기준선에 얼마나 가까운지 나타내는 점수 매기기 값입니다. 정확도 범위는 0 (가장 덜 정확함) 에서 1 (가장 정확함) 까지 다양합니다. |
| **[!UICONTROL Reach and Accuracy Data Columns]** | 오른쪽에 위치한 이 섹션에는 모델에 대한 정확도 및 도달 값을 표시하는 최대 21 개의 숫자 데이터가 표시됩니다. |
| **[!UICONTROL Reach and Accuracy Slider]** | 그래프 하단에 있는 슬라이더를 사용하여 도달 또는 정확도 목표에 대한 숫자 값을 설정할 수 있습니다. 슬라이더를 설정한 다음 도달 또는 정확도 목표 단추를 선택하여 트레이트를 만들 수 있습니다. |

>[!MORE_ like_ this]
>
>* [정확성 및 전달 범위](../../features/traits/trait-accuracy-reach.md)