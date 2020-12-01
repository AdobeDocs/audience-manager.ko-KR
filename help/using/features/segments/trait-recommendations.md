---
description: 트레이트 권장 사항을 사용하면 세그먼트 빌더에서 세그먼트를 작성하거나 편집할 때 포함할 수 있는 추가 트레이트에 대한 권장 사항을 얻을 수 있습니다. 이러한 권장 사항은 세그먼트 규칙의 트레이트와 유사합니다. 세그먼트에 권장 트레이트를 추가하여 타겟 대상자를 늘리십시오.
seo-description: 세그먼트를 만들 때 라이브 트레이트 추천을 얻을 수 있습니다.
seo-title: 트레이트 추천
solution: Audience Manager
title: 트레이트 추천
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1573'
ht-degree: 8%

---


# 트레이트 추천

자사 트레이트 및 [!UICONTROL Audience Marketplace] 데이터 피드에서 세그먼트를 작성할 때 라이브 트레이트 추천을 얻을 수 있습니다.

## 비디오 데모

먼저 아래 [!UICONTROL Trait Recommendations] 비디오를 시청한 다음 계속 읽어서 자세한 내용을 확인하십시오. 비디오 데모에서는 이미 *에 가입한 [!UICONTROL Audience Marketplace] 데이터 피드의 특성 권장 사항뿐만 아니라 자사 트레이트의 권장 사항을 사용하여 작업하는 방법을 보여 줍니다.*

>[!VIDEO](https://video.tv.adobe.com/v/26228/)

다음 비디오에서는 [!UICONTROL Marketplace Recommendations]의 데이터 피드의 권장 사항을 기반으로 세그먼트에 트레이트를 추가하는 방법을 보여주는 &lt;a0/>의 워크플로우에 대해 간략하게 설명합니다. [!UICONTROL Audience Marketplace] 이러한 권장 사항은 *이(가)*&#x200B;에 구독되지 않은 데이터 피드를 기반으로 합니다.

>[!VIDEO](https://video.tv.adobe.com/v/29363/)

## 개요

[!UICONTROL Trait Recommendations]데이터 과학 [!DNL Adobe Sensei]을 Audience Manager의 일상적인 워크플로우로 가져옵니다.
[!UICONTROL Trait Recommendations]을 사용하여 [세그먼트 빌더](segment-builder.md)에서 세그먼트를 만들거나 편집할 때 세그먼트 규칙의 트레이트와 유사한 추가 트레이트에 대한 권장 사항을 얻을 수 있습니다.

Audience Manager은 퍼스트 파티 트레이트, **[!UICONTROL Recommendations]** 섹션 및 **[!UICONTROL Audience Marketplace]**&#x200B;의 **[!UICONTROL Recommendations from Marketplace]** 섹션에서 모두 트레이트 권장 사항을 보여줍니다.

세그먼트에 권장 트레이트를 추가하여 타겟 대상자를 늘리십시오.

![특성 Recommendations 개요](assets/trait-recommendations-overview-full.png)

**간단히 말해:**

* Audience Manager은 [!UICONTROL Recommendations] 섹션에 퍼스트 파티 트레이트를 표시합니다. 구독하지 않은 공개 및 비공개 피드의 마켓플레이스 권장 사항은 [!UICONTROL Recommendations from Marketplace] 섹션에 표시됩니다. 피드 이름을 클릭하여 [!UICONTROL Audience Marketplace]으로 이동하고 구독합니다.
* Audience Manager은 세그먼트 규칙의 특성과 가장 비슷한 최대 50개의 특성을 보여줍니다.
* 권장 사항을 표시하지 않을 데이터 소스를 필터링할 수 있습니다.
* 유사성을 계산할 때 Audience Manager은 지난 30일 동안 트레이트에 자격을 갖춘 [UUIDs](../../reference/ids-in-aam.md)를 고려합니다.
* &quot;비슷한 트레이트를 찾을 수 없습니다. 트레이트가 너무 새것일 수 있습니다.&quot; 즉, 지난 30일 동안 해당 트레이트에 대한 활동이 없거나 Audience Manager이 아직 해당 트레이트에 대한 권장 사항을 업데이트하지 않았음을 의미합니다. 24시간 후에 다시 시도하십시오.

## 사용 사례

[!UICONTROL Trait Recommendations]을 사용하면 Audience Manager 사용 방법에 따라 워크플로우를 향상시킬 수 있습니다.

* 마케터는 유사한 트레이트를 활용하여 보완 제품에 관심 있는 고객을 신속하게 찾아 도달 범위를 확대할 수 있습니다.
* 게시자로 Audience Manager을 사용하는 경우 [!UICONTROL Trait Recommendations]을(를) 사용하여 고객 행동을 파악하고 광고 판매 또는 사용자 확보를 위해 더 나은 세그먼트를 만들 수 있습니다.
* [!UICONTROL Audience Marketplace] 데이터 구매자로서 대량의 피드를 검색하지 않고도 관련 타사 데이터를 검색하려고 합니다.
* [!UICONTROL Audience Marketplace] 데이터 제공업체로서, 최적적이고 연관성 있는 가입으로 혜택을 볼 수 있도록 구매자에게 관련 데이터를 추천하고자 합니다.

## 특성 Recommendations과 알고리즘 모델의 차이점

### 알고리즘 모델

[!UICONTROL Algorithmic Models] 가장 영향력 있는 트레이트를 찾을 뿐만 아니라 이러한 트레이트를 기반으로 사용자의 점수를 매기고 각 사용자에게 개별 점수를 지정합니다. 그런 다음, 사용자를 타겟팅하는 알고리즘 트레이트를 만듭니다. [!UICONTROL Trait Builder]의 정확도 및 도달 컨트롤을 사용하면 타깃팅하려는 영향력 있는 특성을 가진 모든 사용자 중에서 어떤 사용자를 지정할 수 있습니다.

[!UICONTROL Algorithmic Models] 다른 정확도 수준에서 사용자를 선택하고 사용자 그룹 [!UICONTROL Audience Lab] 에서 보다 효과적으로 전환할 수 있습니다. [대상 랩의 모델 비교](../../features/audience-lab/audience-lab-use-cases.md#compare-models)에서 자세한 사용 사례를 확인하십시오.

[!UICONTROL Algorithmic Models]에서 모델은 8일마다 실행되고 알고리즘 특성에 맞는 사용자를 새로 고칩니다.

### 트레이트 추천

[!UICONTROL Trait Recommendations] 세그먼트에서 사용 중인 트레이트와 유사한 다른 트레이트에 대한 통찰력을 얻는 빠른 방법입니다.

다음 경우 [!UICONTROL Trait Recommendations]을(를) 사용해야 합니다.

* 세그먼트를 만드는 동안 빠른 통찰력이 필요한 경우
* 짧은 캠페인에 세그먼트를 사용하거나 전환되는 대상을 빠르게 억제하려는 경우
* 도달 범위를 극대화하려는 경우

## 워크플로우

[세그먼트 빌더](segment-builder.md)에서 세그먼트를 빌드하거나 편집할 때 세그먼트 규칙의 트레이트와 유사한 트레이트를 탐색할 수 있습니다. [세그먼트 빌더](segment-builder.md) 워크플로우는 새 세그먼트와 기존 세그먼트에 대해 매우 유사합니다.

### 새 세그먼트

1. **대상 데이터 > 세그먼트**&#x200B;로 이동하고 **새로 추가**&#x200B;를 클릭합니다.
1. **트레이트** 드롭다운 상자에서 세그먼트 규칙에 트레이트를 하나 이상 추가합니다.
1. 가입한 피드의 퍼스트 파티 권장 트레이트 및 [!UICONTROL Audience Marketplace] 트레이트 권장 사항은 **[!UICONTROL Recommendations]** 섹션에 표시됩니다. **[!UICONTROL Recommendations from Marketplace]** 섹션에는 가입하지 않은 피드의 트레이트 권장 사항이 표시됩니다. 이러한 권장 사항은 모두 세그먼트 규칙에 추가한 트레이트와 비슷합니다. 아래로 스크롤하여 모든 권장 트레이트를 확인합니다.
1. (선택 사항) 특정 데이터 소스에서 권장 퍼스트 파티 트레이트를 제외하려면 제외할 데이터 소스에 대해 **X** 기호를 클릭합니다.

   >[!NOTE]
   >
   >제외된 데이터 소스는 권장 트레이트 목록 바로 위에 표시됩니다. 회색 상자에서 **X**&#x200B;을 클릭하여 제외를 제거하고 각 데이터 소스의 결과를 다시 봅니다.
1. 권장되는 트레이트를 세그먼트 규칙에 추가하려면 **+** 기호를 클릭합니다.

>[!IMPORTANT]
>
>세그먼트에 [!UICONTROL Marketplace] 트레이트를 추가할 때 해당 데이터 피드에 가입하기 전까지 트레이트는 세그먼트 예측에만 사용됩니다. 가입하지 않은 데이터 피드에서 발생한 트레이트는 트레이트 목록에 장바구니 아이콘으로 표시됩니다. 특성 이름을 클릭하여 데이터 피드 페이지로 이동하고 구독합니다.
>
>![marketplace를 구독하지 않음](assets/trait-recommendations-marketplace.png)
>
>해당 데이터 피드에 가입한 후에만 타사 트레이트로 세그먼트를 저장할 수 있습니다.

### 기존 세그먼트

1. **[!UICONTROL Audience Data]>[!UICONTROL Segments]**&#x200B;으로 이동하여 편집할 세그먼트를 선택하고 ![편집](assets/edit-button.png)을 클릭합니다.
1. [!UICONTROL Traits] 드롭다운 상자로 아래로 스크롤합니다.
1. 세그먼트 규칙에 이미 있는 트레이트와 유사한 권장 트레이트를 볼 수 있습니다. 아래로 스크롤하여 모든 권장 트레이트를 확인합니다.
1. (선택 사항) 특정 데이터 소스에서 권장 특성을 제외하려면 제외할 데이터 소스에 대해 **X** 기호를 클릭합니다.

   >[!NOTE]
   >
   >제외된 데이터 소스는 권장 트레이트 목록 바로 위에 표시됩니다. 회색 상자에서 **X**&#x200B;을 클릭하여 제외를 제거하고 각 데이터 소스의 결과를 다시 봅니다.
1. 권장되는 트레이트를 세그먼트 규칙에 추가하려면 **+** 기호를 클릭합니다.

세그먼트를 만들거나 편집하고 세그먼트 규칙에 트레이트를 추가하면 추가한 트레이트와 유사한 최대 50개의 권장 트레이트가 표시됩니다. 세그먼트 규칙에 둘 이상의 특성이 포함된 경우 Audience Manager은 라운드 로빈 방법을 사용하여 각 트레이트에 가장 적합한 일치 항목을 표시한 다음 각 트레이트에 대한 두 번째 일치 등을 세그먼트 규칙에서 인구 기준으로 가장 큰 50개의 트레이트에 대해 표시합니다.

![세 가지 기본 트레이트](assets/three-base-traits.png)

예를 들어, 다음과 같이 세그먼트 규칙에 세 가지 트레이트가 있을 때 권장되는 트레이트는 다음과 같습니다.

1. 트레이트 3에 가장 잘 일치합니다(인구 규모가 가장 큰 특성).
1. 트레이트 1에 가장 일치
1. 트레이트 2에 가장 일치
1. 트레이트 3에 대한 두 번째 일치
1. 트레이트 1에 두 번째, 50가지 트레이트가 나올 때까지 계속.

특정 트레이트에 대한 권장 사항을 얻으려면 세그먼트 규칙(1) 또는 권장 트레이트 보기(2)에서 트레이트를 클릭할 수 있습니다.

![base-traits-example](assets/three-base-traits-numbered.png)

퍼스트 파티 트레이트를 클릭하면 아래 이미지와 같이 팝업 창이 열립니다. 권장되는 트레이트가 세그먼트의 일부가 아닌 경우 **+**&#x200B;을 눌러 세그먼트에 추가할 수 있습니다.

![세그먼트에 추가](assets/add_to_segments.png)

>[!TIP]
>
>주 페이지에서 제외된 데이터 소스는 트레이트 정보 팝업 창 내에서 권장 사항을 생성하는 동안 고려됩니다. 이 보기에서 데이터 소스를 제외하는 경우 기본 페이지에 제외가 적용됩니다.

>[!NOTE]
>
>권장 트레이트는 [!UICONTROL Audience Marketplace]에 가입한 데이터 피드의 자사 트레이트 또는 타사 트레이트일 수 있습니다.

## 작동 방법

특성 권장 사항을 만들기 위해 Audience Manager은 대상 트레이트와 사용자 계정에서 액세스할 수 있는 다른 모든 트레이트 간 [Java 유사성](https://en.wikipedia.org/wiki/Jaccard_index)을 계산합니다(타사 데이터 포함). Audience Manager은 가장 비슷한 특성을 최대 50개까지 표시합니다.

## 특성 유사성 점수 {#trait-similarity-score}

Audience Manager은 [!UICONTROL UUID]s 수에 대한 관점에서 교차와 조합을 계산하여 두 트레이트 사이의 [!UICONTROL Trait Similarity Score]을 계산한 다음 두 트레이트를 나눕니다. 두 트레이트 A와 B의 경우 계산은 다음과 같습니다.

![자카드 유사성](assets/jaccard_similarity.png)

아래의 두 가지 예도 참조하십시오.

### 예 1 - 낮은 트레이트 유사성 점수

두 가지 특성 A와 B가 주어지면 각각의 트레이트에 1,000,000개의 [!UICONTROL UUID]의 모집단, 25,000개의 [!UICONTROL UUID]이 있다고 가정해 봅시다. 이 두 트레이트는 모두 사용할 수 있습니다.
위의 공식을 사용하면 다음과 같은 결과가 발생합니다.25,000 / 1,975,000 = 0.012입니다. 이 두 가지 특징은 매우 다릅니다.[!UICONTROL Trait Similarity Score]

![trait-recommendations-low-overlap](assets/Trait-Recommendations-Low-overlap.png)

### 예 2 - 특성 유사성 점수

동일한 트레이트 A와 B에 두 트레이트를 모두 사용할 수 있는 400,000개의 [!UICONTROL UUID]이(가) 있는 경우 [!UICONTROL Trait Similarity Score]이(가) 훨씬 높습니다.
400,000 / 1,600,000 = 0.25

![trait-recommendations-high-overlap](assets/Trait-Recommendations-High-overlap.png)

### 트레이트 유사성 점수를 해석하는 방법

아래 표를 트레이트 유사성에 대한 대략적인 안내서로 사용하십시오. 이 안내서는 대부분의 특성에서 관찰한 유사성에 근거한다.

| [!UICONTROL Trait Similarity Score] | 중요도 |
---------|----------|
| 0.1 이상 | 특성 간 높은 유사성 |
| 0.03 - 0.1 | 트레이트 간의 중간 유사성 |
| 0.01 - 0.03 | 특성 간 낮은 유사성 |
| 0 - 0.01 | 특성 간 매우 낮은 유사성 |

## 역할 기반 액세스 제어(RBAC)

[!UICONTROL Role-Based Access Controls]([!UICONTROL RBAC])을 사용하는 회사의 경우 권장 트레이트를 보려면 세그먼트를 만들고 편집할 수 있는 권한이 있어야 합니다. 표시되는 특성 권장 사항은 [!UICONTROL RBAC]을 통해 액세스할 수 있는 데이터 소스의 특성 권장 사항일 뿐입니다.

>[!IMPORTANT]
>
>세그먼트에 [!UICONTROL Marketplace Recommendations]을(를) 추가하려면 먼저 해당 데이터 피드에 가입해야 합니다. 관리자 권한이 있는 사용자만 [!UICONTROL Audience Marketplace] 데이터 피드에 가입할 수 있습니다.

[!UICONTROL RBAC] 컨트롤 [여기](../administration/administration-overview.md)에 대한 자세한 내용을 참조하십시오.

## 제한

* 현재 Audience Manager에서는 권장되는 트레이트로 폴더 트레이트를 표시하지 않습니다. 폴더 특성 [여기](../traits/manage-folder-traits.md)에 대한 자세한 내용을 참조하십시오.
* 트레이트 Recommendations을 표시할 때 Audience Manager은 세그먼트 규칙에서 [!DNL Boolean] 연산자([!DNL AND], [!DNL OR], [!DNL NOT])를 고려하지 않습니다.
