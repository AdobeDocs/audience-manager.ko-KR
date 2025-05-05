---
description: 트레이트 Recommendations을 사용하면 세그먼트 빌더에서 세그먼트를 작성하거나 편집할 때 포함할 수 있는 추가 트레이트에 대한 권장 사항을 얻을 수 있습니다. 이러한 권장 사항은 세그먼트 규칙의 트레이트와 유사합니다. 세그먼트에 권장 트레이트를 추가하여 타겟 대상자를 늘리십시오.
seo-description: Get live trait recommendations as you build your segments.
seo-title: Trait Recommendations
solution: Audience Manager
title: 트레이트 Recommendations
feature: Segments
exl-id: 7ef862a9-7354-49fb-9af0-925d827a5165
source-git-commit: 432b12c4d4fb567d1a0bcaa9d12baaac5e3ae0f7
workflow-type: tm+mt
source-wordcount: '1584'
ht-degree: 5%

---

# 트레이트 Recommendations

세그먼트를 만들 때 자사 트레이트 및 [!UICONTROL Audience Marketplace] 데이터 피드에서 실시간 트레이트 권장 사항을 얻을 수 있습니다.

## 비디오 데모

아래의 [!UICONTROL Trait Recommendations] 비디오를 시청한 후 자세한 내용을 읽어 보십시오. 이 비디오 데모에서는 자사 트레이트의 권장 사항과 *이미 구독 중*&#x200B;인 [!UICONTROL Audience Marketplace] 데이터 피드의 트레이트 권장 사항을 사용하여 작업하는 방법을 보여 줍니다.

>[!VIDEO](https://video.tv.adobe.com/v/40845?captions=kor)

다음 비디오는 [!UICONTROL Audience Marketplace]의 데이터 피드에서 권장 사항을 기반으로 세그먼트에 트레이트를 추가하는 방법을 보여 주는 [!UICONTROL Marketplace Recommendations]의 워크플로에 대해 간략하게 설명합니다. 이러한 권장 사항은 *구독하지 않은* 데이터 피드를 기반으로 합니다.

>[!VIDEO](https://video.tv.adobe.com/v/32754?captions=kor)

## 개요

[!DNL Adobe Sensei]에서 제공하는 [!UICONTROL Trait Recommendations]은(는) 데이터 과학을 Audience Manager의 일반 워크플로우로 가져옵니다.
[!UICONTROL Trait Recommendations]을(를) 사용하면 [세그먼트 빌더](segment-builder.md)에서 세그먼트를 작성하거나 편집할 때 포함할 수 있는 추가 트레이트에 대한 권장 사항을 얻을 수 있습니다. 이러한 권장 사항은 세그먼트 규칙의 트레이트와 유사합니다.

Audience Manager은 자사 트레이트, **[!UICONTROL Recommendations]** 섹션 및 **[!UICONTROL Audience Marketplace]**, **[!UICONTROL Recommendations from Marketplace]** 섹션 모두에서 트레이트 권장 사항을 표시합니다.

세그먼트에 권장 트레이트를 추가하여 타겟 대상자를 늘리십시오.

![트레이트 Recommendations 개요](assets/trait-recommendations-overview-full.png)

**전체:**

* Audience Manager은 [!UICONTROL Recommendations] 섹션의 자사 트레이트를 표시합니다. 구독하지 않은 공개 및 비공개 피드의 마켓플레이스 권장 사항은 [!UICONTROL Recommendations from Marketplace] 섹션에 표시됩니다. [!UICONTROL Audience Marketplace] (으)로 이동하여 가입하려면 피드 이름을 클릭하십시오.
* Audience Manager은 세그먼트 규칙의 트레이트와 유사한 트레이트를 최대 50개까지 보여 줍니다.
* 권장 사항을 보지 않으려는 데이터 소스를 필터링할 수 있습니다.
* 유사성을 계산할 때 Audience Manager은 지난 30일 동안 트레이트에 적합한 [UUID](../../reference/ids-in-aam.md)을(를) 고려합니다.
* &quot;유사한 트레이트를 찾을 수 없습니다. 트레이트가 너무 새로울 수 있습니다.&quot;, 이것은 지난 30일 동안 해당 트레이트에 대한 활동이 없었거나 Audience Manager이 해당 트레이트에 대한 권장 사항을 아직 업데이트하지 않았음을 의미합니다. 24시간 후에 다시 시도하십시오.

## 사용 사례

[!UICONTROL Trait Recommendations]을(를) 사용하면 Audience Manager 사용 방식에 따라 워크플로를 개선할 수 있습니다.

* 마케터로서 유사한 트레이트의 도움을 받아 보조 제품에 관심이 있는 대상자를 빠르게 찾을 수 있으므로 도달 범위를 늘릴 수 있습니다.
* [!UICONTROL Trait Recommendations]과(와) 함께 게시자로 Audience Manager을 사용하는 경우 대상 행동을 이해하고 광고 판매 또는 사용자 획득을 위한 더 나은 세그먼트를 만들 수 있습니다.
* [!UICONTROL Audience Marketplace] 데이터 구매자는 많은 피드를 탐색하지 않고 관련 타사 데이터를 검색하려고 합니다.
* [!UICONTROL Audience Marketplace] 데이터 공급자로서 최적의 관련 구독을 통해 혜택을 받을 수 있도록 구매자에게 관련 데이터를 추천하고 싶습니다.

## 트레이트 Recommendations과 알고리즘 모델 간의 차이점

### 알고리즘 모델

[!UICONTROL Algorithmic Models]은(는) 가장 영향력 있는 트레이트를 찾을 뿐만 아니라 해당 트레이트를 기반으로 사용자에 대한 점수를 매기고 각 사용자에게 개별 점수를 할당합니다. 그런 다음, 사용자를 타겟팅하는 알고리즘 트레이트를 만듭니다. [!UICONTROL Trait Builder]의 정확성 및 도달 범위 컨트롤을 사용하면 영향력 있는 특성을 가진 모든 사용자 중에서 타깃팅할 사용자를 지정할 수 있습니다.

[!UICONTROL Algorithmic Models]을(를) 사용하면 다양한 정확도 수준에서 사용자를 선택하고 [!UICONTROL Audience Lab]에서 어떤 사용자 그룹이 더 잘 전환되는지 테스트할 수 있습니다. [대상 랩의 모델 비교](../../features/audience-lab/audience-lab-use-cases.md#compare-models)에서 자세한 사용 사례를 확인하십시오.

[!UICONTROL Algorithmic Models]에서 모델은 8일마다 실행되고 알고리즘 트레이트에 적합한 사용자를 새로 고칩니다.

### 트레이트 Recommendations

[!UICONTROL Trait Recommendations]은(는) 세그먼트에서 사용 중인 트레이트와 유사한 다른 트레이트에 대한 통찰력을 빠르게 얻을 수 있는 방법입니다.

다음과 같은 경우 [!UICONTROL Trait Recommendations]을(를) 사용해야 합니다.

* 세그먼트를 만드는 동안 빠른 통찰력이 필요한 경우
* 짧은 캠페인에 세그먼트를 사용하거나 전환되는 대상을 빠르게 억제하려는 경우
* 도달 범위를 극대화하려는 경우

## 워크플로

[세그먼트 빌더](segment-builder.md)에서 세그먼트를 작성하거나 편집할 때 세그먼트 규칙의 트레이트와 유사한 트레이트를 살펴볼 수 있습니다. [세그먼트 빌더](segment-builder.md) 워크플로는 새 세그먼트와 기존 세그먼트에 대해 매우 유사합니다.

### 새 세그먼트

1. **대상 데이터 > 세그먼트**(으)로 이동한 다음 **새로 추가**&#x200B;를 클릭합니다.
1. **트레이트** 드롭다운 상자에서 세그먼트 규칙에 트레이트를 하나 이상 추가합니다.
1. **[!UICONTROL Recommendations]** 섹션에서 구독 중인 피드에서 자사 추천 트레이트 및 [!UICONTROL Audience Marketplace] 트레이트 추천 항목을 볼 수 있습니다. **[!UICONTROL Recommendations from Marketplace]** 섹션에는 구독하지 않는 피드의 트레이트 권장 사항이 표시됩니다. 이러한 모든 권장 사항은 세그먼트 규칙에 추가한 트레이트와 유사합니다. 아래로 스크롤하여 모든 권장 트레이트를 확인합니다.
1. (선택 사항) 특정 데이터 소스에서 권장되는 자사 트레이트를 제외하려면 제외할 데이터 소스의 **X** 기호를 클릭합니다.

   >[!NOTE]
   >
   >제외된 데이터 소스는 권장 트레이트 목록 바로 위에 표시됩니다. 제외를 제거하고 각 데이터 원본의 결과를 다시 보려면 회색 상자에서 **X**&#x200B;을(를) 클릭하십시오.
1. 세그먼트 규칙에 권장 트레이트를 추가하려면 **+** 기호를 클릭합니다.

>[!IMPORTANT]
>
>세그먼트에 [!UICONTROL Marketplace] 트레이트를 추가할 때 해당 데이터 피드에 가입할 때까지 트레이트는 세그먼트 추정에 대해서만 사용됩니다. 구독하지 않은 데이터 피드에서 가져온 트레이트는 트레이트 목록에 장바구니 아이콘으로 표시됩니다. 트레이트 이름을 클릭하여 데이터 피드 페이지로 이동하고 구독합니다.
>
>![마켓플레이스 미가입](assets/trait-recommendations-marketplace.png)
>
>해당 데이터 피드에 가입한 후에만 타사 트레이트와 함께 세그먼트를 저장할 수 있습니다.

### 기존 세그먼트

1. **[!UICONTROL Audience Data]>[!UICONTROL Segments]**(으)로 이동하여 편집할 세그먼트를 선택하고 ![편집](assets/edit-button.png)을 클릭합니다.
1. [!UICONTROL Traits] 드롭다운 상자로 스크롤합니다.
1. 세그먼트 규칙에 이미 있는 트레이트와 유사한 권장 트레이트를 볼 수 있습니다. 아래로 스크롤하여 모든 권장 트레이트를 확인합니다.
1. (선택 사항) 특정 데이터 소스에서 권장 트레이트를 제외하려면 제외할 데이터 소스의 **X** 기호를 클릭합니다.

   >[!NOTE]
   >
   >제외된 데이터 소스는 권장 트레이트 목록 바로 위에 표시됩니다. 제외를 제거하고 각 데이터 원본의 결과를 다시 보려면 회색 상자에서 **X**&#x200B;을(를) 클릭하십시오.
1. 세그먼트 규칙에 권장 트레이트를 추가하려면 **+** 기호를 클릭합니다.

세그먼트를 만들거나 편집하고 세그먼트 규칙에 트레이트를 추가하면 추가한 트레이트와 유사한 최대 50개의 권장 트레이트가 표시됩니다. 세그먼트 규칙에 트레이트가 두 개 이상 포함된 경우 Audience Manager은 라운드 로빈 방법을 사용하여 각 트레이트에 가장 적합한 일치 항목을 표시한 다음, 모집단별로 가장 큰 50개 트레이트에 대해 두 번째로 적합한 일치 항목 등을 세그먼트 규칙에서 표시합니다.

![기본 트레이트 세 개](assets/three-base-traits.png)

예를 들어 세그먼트 규칙에 아래 표시된 대로 세 가지 트레이트가 있는 경우 권장되는 트레이트는 다음과 같습니다.

1. 트레이트 3(인구가 가장 많은 트레이트)에 대한 최적 일치
1. 트레이트 1에 대한 최적 일치
1. 트레이트 2에 대한 최적 일치
1. 트레이트 3에 대한 두 번째 우수 일치
1. 트레이트 1에 대해 두 번째로 좋은 일치 항목 등등 50개 트레이트에 도달할 때까지 일치합니다.

특정 트레이트에 대한 권장 사항을 얻으려면 세그먼트 규칙 (1)이나 권장 트레이트 보기 (2)에서 트레이트를 클릭할 수 있습니다.

![base-traits-example](assets/three-base-traits-numbered.png)

자사 트레이트를 클릭하면 아래 그림과 같이 팝업 창이 열립니다. 권장 트레이트가 세그먼트에 속하지 않는 경우 **+**&#x200B;을 눌러 세그먼트에 추가할 수 있습니다.

![세그먼트에 추가](assets/add_to_segments.png)

>[!TIP]
>
>트레이트 정보 팝업 창 내에서 권장 사항을 생성하는 동안 기본 페이지에서 제외된 데이터 소스를 고려합니다. 또한 이 보기에서 데이터 소스를 제외하는 경우 제외가 기본 페이지에 적용됩니다.

>[!NOTE]
>
>권장 트레이트는 자사 트레이트이거나 [!UICONTROL Audience Marketplace]에서 구독하는 데이터 피드의 타사 트레이트일 수 있습니다.

## 작동 방법

트레이트 권장 사항을 만들려면 Audience Manager은 대상 트레이트와 타사 데이터를 포함하여 계정에 액세스할 수 있는 다른 모든 트레이트 간의 [Jaccard 유사성](https://en.wikipedia.org/wiki/Jaccard_index)을 계산합니다. 그런 다음 Audience Manager은 유사성이 가장 높은 최대 50개의 트레이트를 표시합니다.

## 트레이트 유사성 점수 {#trait-similarity-score}

Audience Manager은 [!UICONTROL UUID]의 수로 교차와 합집합을 계산하여 두 특성 사이의 [!UICONTROL Trait Similarity Score]을(를) 계산한 다음 두 특성을 나눕니다. 두 트레이트 A와 B의 경우 다음과 같이 계산됩니다.

![jaccard-similarity](assets/jaccard_similarity.png)

아래의 두 가지 예제를 참조하십시오.

### 예제 1 - 낮은 트레이트 유사성 점수

두 개의 트레이트 A와 B를 고려할 때 각 트레이트의 모집단은 1,000,000 [!UICONTROL UUID]이고, 이 중 25,000 [!UICONTROL UUID]개가 두 트레이트에 모두 해당한다고 가정해 보겠습니다.
위의 공식을 사용하면 25,000 / 1,975,000 = 0.012가 됩니다. 낮은 [!UICONTROL Trait Similarity Score]입니다. 두 특성이 매우 다릅니다.

![트레이트 권장 사항-low-overlap](assets/Trait-Recommendations-Low-overlap.png)

### 예제 2 - 트레이트 유사성 점수

동일한 트레이트 A와 B에 두 트레이트 모두에 해당하는 [!UICONTROL UUID]이(가) 40만 개 있는 경우 [!UICONTROL Trait Similarity Score]이(가) 훨씬 높습니다.
400,000 / 1,600,000 = 0.25

![트레이트-권장 사항-높음-겹치기](assets/Trait-Recommendations-High-overlap.png)

### 트레이트 유사성 점수를 해석하는 방법

아래 표를 트레이트 유사성에 대한 대략적인 안내서로 사용하십시오. 이 안내서는 대부분의 트레이트에서 관찰된 유사성 점수를 기반으로 합니다.

| [!UICONTROL Trait Similarity Score] | 중요도 |
|---------|----------|
| 0.1 이상 | 트레이트 간 높은 유사성 |
| 0.03 - 0.1 | 트레이트 간 Medium 유사성 |
| 0.01 - 0.03 | 트레이트 간 낮은 유사성 |
| 0 - 0.01 | 트레이트 간 매우 낮은 유사성 |

## 역할 기반 액세스 제어(RBAC)

[!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC])을(를) 사용하는 회사의 경우 권장 트레이트를 보려면 세그먼트를 만들고 편집할 수 있는 권한이 있어야 합니다. 표시되는 트레이트 권장 사항은 [!UICONTROL RBAC]을(를) 통해 액세스할 수 있는 데이터 소스의 트레이트 권장 사항뿐입니다.

>[!IMPORTANT]
>
>세그먼트에 [!UICONTROL Marketplace Recommendations]을(를) 추가하려면 먼저 사용자가 해당 데이터 피드에 가입해야 합니다. 관리자 권한이 있는 사용자만 [!UICONTROL Audience Marketplace] 데이터 피드를 구독할 수 있습니다.

[!UICONTROL RBAC] 컨트롤 [여기](../administration/administration-overview.md)에 대해 자세히 알아보세요.

## 제한

* 현재 Audience Manager은 폴더 트레이트를 권장 트레이트로 표시하지 않습니다. 폴더 특성 [여기](../traits/manage-folder-traits.md)에 대해 자세히 알아보세요.
* 트레이트 Recommendations을 표시할 때 Audience Manager은 세그먼트 규칙의 [!DNL Boolean] 연산자([!DNL AND], [!DNL OR], [!DNL NOT])를 고려하지 않습니다.
