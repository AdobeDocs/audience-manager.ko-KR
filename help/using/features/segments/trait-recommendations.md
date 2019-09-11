---
description: 트레이트 권장 사항을 사용하면 세그먼트 빌더에서 세그먼트를 작성하거나 편집할 때 포함할 수 있는 추가 트레이트에 대한 권장 사항을 얻을 수 있습니다. 이러한 권장 사항은 세그먼트 규칙의 트레이트와 유사합니다. 세그먼트에 권장 트레이트를 추가하여 타겟 대상자를 늘리십시오.
seo-description: 세그먼트를 만들 때 라이브 트레이트 추천을 받을 수 있습니다.
seo-title: 트레이트 권장 사항
solution: Audience Manager
title: 트레이트 권장 사항
uuid: null
translation-type: tm+mt
source-git-commit: 76adee013246c68da7ad871cef57f6ef174a239c

---


# 트레이트 권장 사항

세그먼트를 만들 때 라이브 트레이트 추천을 받을 수 있습니다.

## 비디오 데모

트레이트 추천 비디오를 시청한 다음 자세한 내용을 보려면을 읽어 보십시오.

>[!VIDEO](https://video.tv.adobe.com/v/26228/?captions=kor)

## 개요

[!UICONTROL Trait Recommendations]이 서비스를 통해 [!DNL Adobe Sensei]고객 관리자에게는 데이터 과학을 일상적인 워크플로우로 가져올 수 있습니다.
With [!UICONTROL Trait Recommendations], when you build or edit a segment in [Segment Builder](segment-builder.md), you get recommendations on additional traits you can include, that are similar to the traits in the segment rule. 세그먼트에 권장 트레이트를 추가하여 타겟 대상자를 늘리십시오.

![특성 권장 사항 개요](assets/trait-recommendations-overview.png)

**요약하자면 다음과 같습니다.**

* Audience Manager는 사용자의 현재 구독 데이터 피드에서 제 3 자 트레이트와 타사 트레이트를 권장되는 트레이트로서 보여줍니다.
* Audience Manager는 세그먼트 규칙과 유사한 최대 50 개의 트레이트를 표시합니다.
* 권장 사항을 보지 않으려는 데이터 소스를 필터링할 수 있습니다.
* 유사점을 계산할 때 Audience Manager는 지난 30 일 동안 트레이트에 대한 자격 조건을 충족하는 [UUID](../../reference/ids-in-aam.md) 를 고려합니다.
* " 유사한 트레이트가 없습니다. 특성 너무 새로워질 수 있습니다. " 즉, 지난 30 일 동안 해당 트레이트에 대한 활동이 없었거나 Audience Manager에서 해당 트레이트에 대한 권장 사항을 업데이트하지 않았음을 의미합니다. 24 시간 후에 다시 시도하십시오.

## 사용 사례

를 사용하면 [!UICONTROL Trait Recommendations]Audience Manager 사용 방법에 따라 워크플로우를 개선할 수 있습니다.

* 마케터는 유사한 트레이트의 도움을 받아 보완 제품에 관심이 있는 고객을 신속하게 찾을 수 있으므로 도달 범위를 늘릴 수 있습니다.
* Audience Manager를 게시자로 사용하는 경우 고객 [!UICONTROL Trait Recommendations]행동을 파악하고 광고 판매 또는 사용자 확보를 위한 더 나은 세그먼트를 만들 수 있습니다.

## 트레이트 추천 및 알고리즘 모델의 차이점

### 알고리즘 모델

[!UICONTROL Algorithmic Models] 가장 영향력 있는 트레이트를 찾을 뿐만 아니라 해당 트레이트를 기반으로 사용자를 점수 지정하고 각 사용자에게 개별 점수를 지정합니다. 그런 다음 사용자를 타깃팅하는 알고리즘 특성을 만듭니다. 의 [!UICONTROL Trait Builder]정확도 및 도달 제어를 통해 타깃팅하려는 영향력이 있는 트레이트가 있는 모든 사용자를 지정할 수 있습니다.

[!UICONTROL Algorithmic Models] 사용자를 다른 정확도 수준에서 선택하고 사용자 그룹이 더 나은 [!UICONTROL Audience Lab] 것으로 전환되는 테스트를 수행할 수 있습니다. Audience Lab의 모델 비교에서 [자세한 사용 사례를 참조하십시오](../../features/audience-lab/audience-lab-use-cases.md#compare-models).

에서 [!UICONTROL Algorithmic Models]모델은 8 일마다 실행되며 알고리즘 트레이트에 대한 자격을 갖춘 사용자를 새로 고칩니다.

### 트레이트 권장 사항

[!UICONTROL Trait Recommendations] 세그먼트에 사용하는 것과 유사한 다른 트레이트에 대한 통찰력을 빠르게 얻을 수 있는 방법입니다.

다음 [!UICONTROL Trait Recommendations] 경우에 사용해야 합니다.

* 세그먼트를 구축하는 동안 빠른 통찰력이 필요합니다.
* 짧은 캠페인에 세그먼트를 사용하거나 전환 대상 고객을 빠르게 표시하지 않으려는 경우
* 고객에 대한 도달 범위를 확대하고 있습니다.

## 워크플로우

세그먼트 빌더에서 [](segment-builder.md)세그먼트를 만들거나 편집할 때 세그먼트 규칙의 트레이트와 유사한 트레이트를 탐색할 수 있습니다. 세그먼트 빌더 워크플로우는 새 세그먼트와 기존 세그먼트에 매우 비슷합니다.

### 새 세그먼트

1. 대상 데이터 &gt; 세그먼트에서 ****&#x200B;새로 **추가를 선택합니다**.
2. **특성** 드롭다운 상자에서 세그먼트 규칙에 최소 한 개의 트레이트를 추가합니다.
3. 이제 세그먼트 규칙에 추가한 트레이트와 유사한 권장 트레이트를 볼 수 있습니다. 아래로 스크롤하여 권장되는 모든 트레이트를 확인합니다.
4. (선택 사항) 특정 Data Sources에서 권장 특성을 제외하려면 제외할 Data Sources의 **X** 기호를 클릭합니다.
   > [!NOTE]
   > 
   >제외된 데이터 소스는 권장되는 특성 목록 바로 위에 표시됩니다. 회색 상자에서 **X** 를 눌러 제외를 제거하고 해당 데이터 소스의 결과를 다시 확인합니다.
5. 세그먼트 규칙에 권장 트레이트를 추가하려면 **+** 기호를 클릭합니다.

### 기존 세그먼트

1. 이동 **[!UICONTROL Audience Data]&gt;[!UICONTROL Segments]**&#x200B;편집할 세그먼트를 선택하고 ![편집을 누릅니다](assets/edit-button.png).
1. 아래로 스크롤하여 [!UICONTROL Traits] 드롭다운 상자로 이동합니다.
1. 세그먼트 규칙에 이미 있는 트레이트와 유사한 권장 트레이트가 표시됩니다. 아래로 스크롤하여 권장되는 모든 트레이트를 확인합니다.
1. (선택 사항) 특정 Data Sources에서 권장 특성을 제외하려면 제외할 Data Sources의 **X** 기호를 클릭합니다.
   > [!NOTE]
   > 
   >제외된 데이터 소스는 권장되는 특성 목록 바로 위에 표시됩니다. 회색 상자에서 **X** 를 눌러 제외를 제거하고 해당 데이터 소스의 결과를 다시 확인합니다.
1. 세그먼트 규칙에 권장 트레이트를 추가하려면 **+** 기호를 클릭합니다.

세그먼트를 만들거나 편집하고 세그먼트 규칙에 트레이트를 추가하면 추가된 것과 유사한 최대 50 개의 권장 트레이트가 표시됩니다. 세그먼트 규칙에 둘 이상의 트레이트 특성이 있는 경우 Audience Manager는 둥근 로빈 방법을 사용하여 각 트레이트, 각 트레이트 등에 가장 적합한 일치, 세그먼트 규칙에서 최대 50 개의 트레이트에 대해 두 번째 일치 등을 표시합니다.

![세 가지 기본 특성](assets/three-base-traits.png)

예를 들어, 아래와 같이 세그먼트 규칙에 세 가지 특징이 있을 경우 권장 트레이트는 다음과 같습니다.

1. 트레이트 3 (최대 인구 수가 있는 특성) 에 가장 적합합니다.
2. 특성 1에 가장 적합합니다.
3. 트레이트 2에 가장 적합한 일치
4. second-best match for trait 3;
5. 트레이트 1에 대한 두 번째 일치, 50 가지 트레이트가 표시될 때까지

특정 트레이트에 대한 추천을 얻으려면 세그먼트 규칙 (1) 또는 권장 특성 보기 (2) 에서 트레이트를 클릭합니다.

![](assets/three-base-traits-numbered.png)

트레이트를 클릭하면 아래 이미지에서와 같이 팝업 창이 열립니다. 권장 트레이트가 세그먼트에 속하지 않는 경우 +를 눌러 **세그먼트에 추가할 수 있습니다**.

![](assets/add_to_segments.png)

> [!TIP]
>
>트레이트 정보 팝업 창에서 권장 사항을 생성하는 동안 기본 페이지의 제외된 데이터 소스가 고려됩니다. 또한 이 보기에서 Data Sources를 제외하면 제외가 기본 페이지에 적용됩니다.

> [!NOTE]
>
> 권장되는 트레이트는 구독하는 피드에서 자사 트레이트 또는 타사 트레이트가 될 수 있습니다.

## 작동 방법

특성 추천을 만들기 위해 Audience Manager는 Target 트레이트 및 타사 데이터 등 계정에서 액세스할 수 있는 모든 기타 특성 간의 [jaccard 유사성을](https://en.wikipedia.org/wiki/Jaccard_index) 계산합니다. 그러면 Audience Manager에 최대 50 개의 트레이트가 표시됩니다.

## 특성 유사점 점수

Audience Manager는 s의 수로 intersection 및 union를 계산하여 두 가지 특성 [!UICONTROL Trait Similarity Score] 간 계산을 계산한 다음 [!UICONTROL UUID]이 둘을 분류합니다. 두 가지 특성 A와 B의 계산은 다음과 같습니다.

![](assets/jaccard_similarity.png)

아래 두 가지 예를 참조하십시오.

### 예제 1 - 낮은 특성 유사점 점수

두 가지 특성 A와 B가 주어지면 트레이트에 트레이트가 각각 1,000,000 [!UICONTROL UUID]명, 25,000 [!UICONTROL UUID]명이 됩니다.
위의 공식을 사용하면 다음과 같은 결과가 나타납니다. 25,000/1,975,000 = 0.012. This is a low [!UICONTROL Trait Similarity Score], the two characteristics is very dissimilar.

![](assets/Trait-Recommendations-Low-overlap.png)

### 예제 2 - 특성 유사점

동일한 특성 A와 B에 두 트레이트를 모두 사용할 수 있는 400,000 [!UICONTRL 개의 UUID]가 있을 경우, The [!UICONTROL Trait Similarity Score] is much:
400,000/1,600,000 = 0.25

![](assets/Trait-Recommendations-High-overlap.png)

### 트레이트 유사성 점수를 해석하는 방법

유사성을 높이기 위한 대략적인 가이드로 아래 표를 사용하십시오. This guide is based on the similarity score observed across a majority of the characteristics.

| [!UICONTROL Trait Similarity Score] | 중요도 |
---------|----------|
| 0.1 이상 | 특성 간 유사성 높음 |
| 0.03 - 0.1 | 특성 간의 중간 유사성 |
| 0.01 - 0.03 | 특성 간의 유사성 낮음 |
| 0 - 0.01 | 특성이 매우 유사함 |

## RBAC (역할 기반 액세스 제어)

[!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]) 를 사용하는 회사의 경우 권장 트레이트를 보려면 세그먼트를 만들고 편집할 수 있는 권한이 있어야 합니다. 권장되는 트레이트는 via [!UICONTROL RBAC]에 액세스할 수 있는 Data Sources의 권장 사항입니다. [!UICONTROL RBAC] 여기에서 컨트롤에 [](../administration/administration-overview.md)대한 자세한 내용을 살펴보십시오.

## 제한

* 현재 Audience Manager는 폴더 트레이트를 권장 트레이트로서 표시하지 않습니다. 폴더 트레이트에 [](../traits/manage-folder-traits.md)대한 자세한 내용을 살펴보십시오.
* 특성 권장 사항을 표시할 때 Audience Manager는 세그먼트 규칙에서 [!DNL Boolean] 연산자 ([!DNL AND][!DNL OR], [!DNL NOT]) 를 고려하지 않습니다.