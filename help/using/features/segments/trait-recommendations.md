---
description: 트레이트 권장 사항을 사용하면 세그먼트 빌더에서 세그먼트를 작성하거나 편집할 때 포함할 수 있는 추가 트레이트에 대한 권장 사항을 얻을 수 있습니다. 이러한 권장 사항은 세그먼트 규칙의 트레이트와 유사합니다. 세그먼트에 권장 트레이트를 추가하여 타겟 대상자를 늘리십시오.
seo-description: Get live trait recommendations as you build your segments.
seo-title: Trait Recommendations
solution: Audience Manager
title: 트레이트 추천
feature: Segments
exl-id: 7ef862a9-7354-49fb-9af0-925d827a5165
source-git-commit: 432b12c4d4fb567d1a0bcaa9d12baaac5e3ae0f7
workflow-type: tm+mt
source-wordcount: '1562'
ht-degree: 8%

---

# 트레이트 추천

고유한 자사 트레이트에서 세그먼트를 만들 때 라이브 트레이트 권장 사항을 얻을 수 있습니다. [!UICONTROL Audience Marketplace] 데이터 피드.

## 비디오 데모

다음 항목을 보는 것으로 시작하십시오. [!UICONTROL Trait Recommendations] 아래 비디오에서 자세한 내용을 확인하십시오. 이 비디오 데모에서는 자사 트레이트의 권장 사항과 의 트레이트 권장 사항을 사용하여 작업하는 방법을 보여 줍니다 [!UICONTROL Audience Marketplace] 다음 데이터 피드: *을(를) 이미 구독 중입니다.*.

>[!VIDEO](https://video.tv.adobe.com/v/26228/)

다음 비디오에서는 의 워크플로에 대해 간략하게 설명합니다. [!UICONTROL Marketplace Recommendations], 에서는 의 데이터 피드에서 권장 사항을 기반으로 세그먼트에 트레이트를 추가하는 방법을 보여 줍니다. [!UICONTROL Audience Marketplace]. 이러한 권장 사항은 다음과 같은 데이터 피드를 기반으로 합니다. *을(를) 구독하지 않았습니다.*.

>[!VIDEO](https://video.tv.adobe.com/v/29363/)

## 개요

[!UICONTROL Trait Recommendations], 제공 [!DNL Adobe Sensei]는 데이터 과학을 Audience Manager의 일반 워크플로우에 적용하는 것입니다.
포함 [!UICONTROL Trait Recommendations]에서 세그먼트를 만들거나 편집할 때 [세그먼트 빌더](segment-builder.md)를 사용하면 포함할 수 있는 추가 트레이트에 대한 권장 사항을 얻을 수 있습니다. 이러한 권장 사항은 세그먼트 규칙의 트레이트와 유사합니다.

Audience Manager은 자사 트레이트의 트레이트 권장 사항을에서 보여줍니다. **[!UICONTROL Recommendations]** 섹션 및 시작 **[!UICONTROL Audience Marketplace]**, **[!UICONTROL Recommendations from Marketplace]** 섹션.

세그먼트에 권장 트레이트를 추가하여 타겟 대상자를 늘리십시오.

![트레이트 Recommendations 개요](assets/trait-recommendations-overview-full.png)

**간단히 말해,**

* Audience Manager은 의 자사 트레이트를 [!UICONTROL Recommendations] 섹션. 구독하지 않는 공개 및 비공개 피드의 마켓플레이스 권장 사항이에 표시됩니다. [!UICONTROL Recommendations from Marketplace] 섹션. 이동할 피드 이름을 클릭합니다. [!UICONTROL Audience Marketplace] 구독할 수 있습니다.
* Audience Manager은 세그먼트 규칙의 트레이트와 유사한 트레이트를 최대 50개까지 보여 줍니다.
* 권장 사항을 보지 않으려는 데이터 소스를 필터링할 수 있습니다.
* 유사성을 계산할 때 Audience Manager은 다음을 고려합니다 [UUIDs](../../reference/ids-in-aam.md) 지난 30일 동안 트레이트에 적합한 트레이트입니다.
* &quot;유사한 트레이트를 찾을 수 없습니다. 트레이트가 너무 새로울 수 있습니다.&quot;, 이것은 지난 30일 동안 해당 트레이트에 대한 활동이 없었거나 Audience Manager이 해당 트레이트에 대한 권장 사항을 아직 업데이트하지 않았음을 의미합니다. 24시간 후에 다시 시도하십시오.

## 사용 사례

포함 [!UICONTROL Trait Recommendations], Audience Manager 사용 방법에 따라 워크플로우를 개선할 수 있습니다.

* 마케터로서 유사한 트레이트의 도움을 받아 보조 제품에 관심이 있는 대상자를 빠르게 찾을 수 있으므로 도달 범위를 늘릴 수 있습니다.
* Audience Manager을 게시자로 사용하는 경우 [!UICONTROL Trait Recommendations], 대상 행동을 이해하고 광고 판매 또는 사용자 획득을 위한 더 나은 세그먼트를 만들 수 있습니다.
* (으)로 [!UICONTROL Audience Marketplace] 데이터 구매자, 많은 피드를 탐색하지 않고 관련 타사 데이터를 찾고 싶습니다.
* (으)로 [!UICONTROL Audience Marketplace] 데이터 제공업체, 나는 최적의 관련 구독으로 혜택을 얻을 수 있도록 구매자에게 관련 데이터를 추천하고 싶습니다.

## 트레이트 Recommendations과 알고리즘 모델 간의 차이점

### 알고리즘 모델

[!UICONTROL Algorithmic Models] 가장 영향력 있는 트레이트를 찾을 뿐만 아니라 해당 트레이트를 기반으로 사용자에게 점수를 매기고 각 사용자에게 개별 점수를 지정합니다. 그런 다음, 사용자를 타겟팅하는 알고리즘 트레이트를 만듭니다. 의 정확성 및 도달 범위 제어 [!UICONTROL Trait Builder]을(를) 통해 영향력 있는 트레이트를 가진 모든 사용자 중 타겟팅할 사용자를 지정할 수 있습니다.

[!UICONTROL Algorithmic Models] 에서 다양한 정확도 수준에서 사용자를 선택하고 테스트할 수 있습니다 [!UICONTROL Audience Lab] 어느 사용자 그룹이 더 잘 전환되는지 확인합니다. [대상 랩의 모델 비교](../../features/audience-lab/audience-lab-use-cases.md#compare-models)에서 자세한 사용 사례를 확인하십시오.

위치 [!UICONTROL Algorithmic Models], 모델은 8일마다 실행되고 알고리즘 트레이트에 맞는 사용자를 새로 고칩니다.

### 트레이트 추천

[!UICONTROL Trait Recommendations] 는 세그먼트에서 사용 중인 트레이트와 유사한 다른 트레이트에 대한 통찰력을 얻는 빠른 방법입니다.

다음을 사용해야 합니다. [!UICONTROL Trait Recommendations] 시기:

* 세그먼트를 만드는 동안 빠른 통찰력이 필요한 경우
* 짧은 캠페인에 세그먼트를 사용하거나 전환되는 대상을 빠르게 억제하려는 경우
* 도달 범위를 극대화하려는 경우

## 워크플로

에서 세그먼트를 작성하거나 편집할 때 [세그먼트 빌더](segment-builder.md), 세그먼트 규칙의 트레이트와 유사한 트레이트를 탐색할 수 있습니다. 다음 [세그먼트 빌더](segment-builder.md) 워크플로우는 새 세그먼트와 기존 세그먼트에 대해 매우 유사합니다.

### 새 세그먼트

1. 다음으로 이동 **대상 데이터 > 세그먼트**, 및 클릭 **새로 추가**.
1. 다음에서 **트레이트** 드롭다운 상자에서, 세그먼트 규칙에 트레이트를 하나 이상 추가합니다.
1. 자사 추천 트레이트 및 을 볼 수 있습니다. [!UICONTROL Audience Marketplace] 에서 구독 중인 피드의 트레이트 권장 사항 **[!UICONTROL Recommendations]** 섹션. 다음 **[!UICONTROL Recommendations from Marketplace]** 섹션에는 구독하지 않은 피드에서 트레이트 권장 사항이 표시됩니다. 이러한 모든 권장 사항은 세그먼트 규칙에 추가한 트레이트와 유사합니다. 아래로 스크롤하여 모든 권장 트레이트를 확인합니다.
1. (선택 사항) 특정 데이터 소스에서 권장되는 자사 트레이트를 제외하려면 **X** 제외할 데이터 소스의 기호입니다.

   >[!NOTE]
   >
   >제외된 데이터 소스는 권장 트레이트 목록 바로 위에 표시됩니다. 클릭 **X** 회색 상자에서 제외를 제거하고 각 데이터 소스에서 결과를 다시 확인합니다.
1. 세그먼트 규칙에 권장 트레이트를 추가하려면 **+** 기호.

>[!IMPORTANT]
>
>추가 시 [!UICONTROL Marketplace] 세그먼트에 대한 트레이트. 해당 데이터 피드에 가입할 때까지 트레이트는 세그먼트 추정에 대해서만 사용됩니다. 구독하지 않은 데이터 피드에서 가져온 트레이트는 트레이트 목록에 장바구니 아이콘으로 표시됩니다. 트레이트 이름을 클릭하여 데이터 피드 페이지로 이동하고 구독합니다.
>
>![마켓플레이스가 구독하지 않음](assets/trait-recommendations-marketplace.png)
>
>해당 데이터 피드에 가입한 후에만 타사 트레이트와 함께 세그먼트를 저장할 수 있습니다.

### 기존 세그먼트

1. 다음으로 이동 **[!UICONTROL Audience Data]>[!UICONTROL Segments]**&#x200B;편집할 세그먼트를 선택하고 ![편집](assets/edit-button.png).
1. 아래로 스크롤하여 [!UICONTROL Traits] 드롭다운 상자.
1. 세그먼트 규칙에 이미 있는 트레이트와 유사한 권장 트레이트를 볼 수 있습니다. 아래로 스크롤하여 모든 권장 트레이트를 확인합니다.
1. (선택 사항) 특정 데이터 소스에서 권장 트레이트를 제외하려면 **X** 제외할 데이터 소스의 기호입니다.

   >[!NOTE]
   >
   >제외된 데이터 소스는 권장 트레이트 목록 바로 위에 표시됩니다. 클릭 **X** 회색 상자에서 제외를 제거하고 각 데이터 소스에서 결과를 다시 확인합니다.
1. 세그먼트 규칙에 권장 트레이트를 추가하려면 **+** 기호.

세그먼트를 만들거나 편집하고 세그먼트 규칙에 트레이트를 추가하면 추가한 트레이트와 유사한 최대 50개의 권장 트레이트가 표시됩니다. 세그먼트 규칙에 트레이트가 두 개 이상 포함된 경우 Audience Manager은 라운드 로빈 방법을 사용하여 각 트레이트에 가장 적합한 일치 항목을 표시한 다음, 모집단별로 가장 큰 50개 트레이트에 대해 두 번째로 적합한 일치 항목 등을 세그먼트 규칙에서 표시합니다.

![세 가지 기본 트레이트](assets/three-base-traits.png)

예를 들어 세그먼트 규칙에 아래 표시된 대로 세 가지 트레이트가 있는 경우 권장되는 트레이트는 다음과 같습니다.

1. 트레이트 3(인구가 가장 많은 트레이트)에 대한 최적 일치
1. 트레이트 1에 대한 최적 일치
1. 트레이트 2에 대한 최적 일치
1. 트레이트 3에 대한 두 번째 우수 일치
1. 트레이트 1에 대해 두 번째로 좋은 일치 항목 등등 50개 트레이트에 도달할 때까지 일치합니다.

특정 트레이트에 대한 권장 사항을 얻으려면 세그먼트 규칙 (1)이나 권장 트레이트 보기 (2)에서 트레이트를 클릭할 수 있습니다.

![기본 트레이트-예](assets/three-base-traits-numbered.png)

자사 트레이트를 클릭하면 아래 그림과 같이 팝업 창이 열립니다. 권장 트레이트가 세그먼트에 속하지 않으면 를 눌러 트레이트를 세그먼트에 추가할 수 있습니다 **+**.

![세그먼트에 추가](assets/add_to_segments.png)

>[!TIP]
>
>트레이트 정보 팝업 창 내에서 권장 사항을 생성하는 동안 기본 페이지에서 제외된 데이터 소스를 고려합니다. 또한 이 보기에서 데이터 소스를 제외하는 경우 제외가 기본 페이지에 적용됩니다.

>[!NOTE]
>
>권장되는 트레이트는에서 구독하는 자사 트레이트 또는 데이터 피드의 타사 트레이트일 수 있습니다 [!UICONTROL Audience Marketplace].

## 작동 방법

트레이트 권장 사항을 만들려면 Audience Manager은 [자카드 유사성](https://en.wikipedia.org/wiki/Jaccard_index) 대상 트레이트와 타사 데이터를 포함하여 계정이 액세스할 수 있는 모든 다른 트레이트 간에 매핑됩니다. 그런 다음 Audience Manager은 유사성이 가장 높은 최대 50개의 트레이트를 표시합니다.

## 트레이트 유사성 점수 {#trait-similarity-score}

Audience Manager 계산 [!UICONTROL Trait Similarity Score] 다음 숫자로 교차와 결합을 계산하여 두 트레이트 사이 [!UICONTROL UUID]s를 만들고 둘을 나눕니다. 두 트레이트 A와 B의 경우 다음과 같이 계산됩니다.

![자카드-유사성](assets/jaccard_similarity.png)

아래의 두 가지 예제를 참조하십시오.

### 예제 1 - 낮은 트레이트 유사성 점수

두 개의 트레이트 A와 B를 고려할 때, 각 트레이트의 인구는 100만 명이라고 하자 [!UICONTROL UUID]s, 25,000 [!UICONTROL UUID]의 두 가지 트레이트에 모두 적합합니다.
위의 공식을 사용하면 25,000 / 1,975,000 = 0.012가 됩니다. 낮은 수준입니다 [!UICONTROL Trait Similarity Score], 두 트레이트는 매우 다릅니다.

![트레이트-권장 사항-낮은 겹치기](assets/Trait-Recommendations-Low-overlap.png)

### 예제 2 - 트레이트 유사성 점수

만약 동일한 트레이트 A와 B가 40만 개라면 [!UICONTROL UUID]두 특성 모두에 적합한 경우 [!UICONTROL Trait Similarity Score] 많이 높음: 400,000 / 1,600,000 = 0.25

![트레이트-권장 사항-높은-중복](assets/Trait-Recommendations-High-overlap.png)

### 트레이트 유사성 점수를 해석하는 방법

아래 표를 트레이트 유사성에 대한 대략적인 안내서로 사용하십시오. 이 안내서는 대부분의 트레이트에서 관찰된 유사성 점수를 기반으로 합니다.

| [!UICONTROL Trait Similarity Score] | 중요도 |
|---------|----------|
| 0.1 이상 | 트레이트 간 높은 유사성 |
| 0.03 - 0.1 | 트레이트 간 중간 유사성 |
| 0.01 - 0.03 | 트레이트 간 낮은 유사성 |
| 0 - 0.01 | 트레이트 간 매우 낮은 유사성 |

## 역할 기반 액세스 제어(RBAC)

을 사용하는 회사의 경우 [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC])에서 권장되는 트레이트를 보려면 세그먼트를 만들고 편집할 수 있는 권한이 있어야 합니다. 표시되는 트레이트 권장 사항은 를 통해 액세스할 수 있는 데이터 소스의 트레이트 권장 사항일 뿐입니다 [!UICONTROL RBAC].

>[!IMPORTANT]
>
>추가하려면 [!UICONTROL Marketplace Recommendations] 세그먼트에 대한 사용자는 먼저 해당 데이터 피드에 가입해야 합니다. 관리자 권한이 있는 사용자만 가입할 수 있습니다. [!UICONTROL Audience Marketplace] 데이터 피드.

자세한 내용 [!UICONTROL RBAC] 컨트롤 [여기](../administration/administration-overview.md).

## 제한

* 현재 Audience Manager은 폴더 트레이트를 권장 트레이트로 표시하지 않습니다. 폴더 트레이트에 대해 자세히 알아보기 [여기](../traits/manage-folder-traits.md).
* 트레이트 Recommendations을 표시할 때 Audience Manager은 이를 고려하지 않습니다 [!DNL Boolean] 연산자 ([!DNL AND], [!DNL OR], [!DNL NOT])을 사용할 수 있습니다.
