---
description: 알고리즘 트레이트 만들기 프로세스에 고유한 설정 단계 및 기능에 대해 설명합니다.
seo-description: Describes set up steps and features unique to the algorithmic trait creation process.
seo-title: Create Algorithmic Traits
solution: Audience Manager
title: 알고리즘 트레이트 만들기
uuid: 50c2d2d1-f412-479b-bb70-4f139429c388
feature: Traits
exl-id: dc799688-e38b-469b-bc55-507df0d28f43
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 1%

---

# 알고리즘 트레이트 만들기 {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

알고리즘 특성을 만들려면 [!UICONTROL Traits] (으)로 이동하여 아래 단계를 수행합니다.

1. **[!UICONTROL Create New Trait]**&#x200B;을(를) 클릭하고 드롭다운 메뉴에서 **[!UICONTROL Algorithmic]**&#x200B;을(를) 선택합니다.
1. [기본 정보](../../features/traits/create-onboarded-rule-based-traits.md) 섹션에서
   * 트레이트 이름을 지정합니다.
   * 데이터 소스를 선택합니다.
   * 저장소 폴더를 선택하십시오.
1. [!UICONTROL Configuration] 창을 확장하고 **[!UICONTROL Browse All Models]**&#x200B;을(를) 클릭합니다.
그러면 트레이트와 함께 사용할 모델을 선택할 수 있는 새 창이 열립니다.
1. 모델을 선택하고 **[!UICONTROL Add Selected Model to Trait]**&#x200B;을(를) 클릭합니다.
모델을 추가하면 도달 범위와 정확도 설정이 노출됩니다.
1. 도달 범위 또는 정확도를 목표로 선택하고 해당 드롭다운 메뉴에서 값을 선택합니다. 완료되면 **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.

## 알고리즘 트레이트에 대한 구성 설정 {#configure-settings}

[!UICONTROL Trait Builder]에서 [!UICONTROL Configuration] 섹션을 통해 알고리즘 모델을 트레이트에 연결할 수 있습니다. 알고리즘 트레이트 만들기 프로세스를 완료하려면 모델을 선택하고 도달 또는 정확도 목표를 선택하십시오.

### 전제 조건

<!-- r_algo_trait_config_section.xml -->

* [유사 모델 만들기](../../features/algorithmic-models/create-model.md).
* 모델 데이터 실행이 완료되었음을 알리는 알림 이메일을 기다립니다.
* [기본 정보](../../features/traits/create-onboarded-rule-based-traits.md) 섹션에서 필수 필드를 작성합니다.

### 구성 필드 및 설정

| 인터페이스 요소 | 설명 |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | **[!UICONTROL Update]** 단추를 클릭하여 모델 창을 엽니다. 창에서 트레이트를 생성하는 데 사용할 알고리즘 모델을 선택합니다. |
| **[!UICONTROL Select Goal Accuracy]** | 정확도를 기반으로 트레이트를 만들려면 이 옵션을 선택합니다. 정확도는 잠재적 사용자가 기준선에 얼마나 가까운지를 나타내는 점수 값입니다. 정확도 척도의 범위는 0(가장 정확하지 않음)부터 1(가장 정확함)까지입니다. |
| **[!UICONTROL Reach and Accuracy Data Columns]** | 오른쪽에 있는 이 섹션에는 모델의 정확도 및 도달 범위를 표시하는 숫자 데이터 행이 최대 21개까지 표시됩니다. |
| **[!UICONTROL Reach and Accuracy Slider]** | 그래프 맨 아래에 있는 슬라이더를 사용하여 도달 또는 정확도 목표에 대한 숫자 값을 설정할 수 있습니다. 슬라이더를 설정한 다음 도달 또는 정확도 목표 버튼을 선택하여 트레이트를 만들 수 있습니다. |

>[!MORELIKETHIS]
>
>* [정확성 및 도달 범위](../../features/traits/trait-accuracy-reach.md)
