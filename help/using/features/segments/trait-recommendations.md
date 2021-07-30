---
description: 트레이트 권장 사항을 사용하면 세그먼트 빌더에서 세그먼트를 작성하거나 편집할 때 포함할 수 있는 추가 트레이트에 대한 권장 사항을 얻을 수 있습니다. 이러한 권장 사항은 세그먼트 규칙의 트레이트와 유사합니다. 세그먼트에 권장 트레이트를 추가하여 타겟 대상자를 늘리십시오.
seo-description: 세그먼트를 만들 때 라이브 트레이트 권장 사항을 얻습니다.
seo-title: 트레이트 추천
solution: Audience Manager
title: 트레이트 추천
feature: 세그먼트
exl-id: 7ef862a9-7354-49fb-9af0-925d827a5165
source-git-commit: 432b12c4d4fb567d1a0bcaa9d12baaac5e3ae0f7
workflow-type: tm+mt
source-wordcount: '1574'
ht-degree: 8%

---

# 트레이트 추천

자사 트레이트 및 [!UICONTROL Audience Marketplace] 데이터 피드에서 세그먼트를 작성할 때 라이브 트레이트 추천을 받습니다.

## 비디오 데모

먼저 아래의 [!UICONTROL Trait Recommendations] 비디오를 시청한 다음 계속 읽어보십시오. 비디오 데모에서는 이미&#x200B;*에 구독한 [!UICONTROL Audience Marketplace] 데이터 피드의 트레이트 추천과 자체 자사 트레이트의 권장 사항을 사용하여 작업하는 방법을 보여줍니다.*

>[!VIDEO](https://video.tv.adobe.com/v/26228/)

다음 비디오에서는 [!UICONTROL Marketplace Recommendations]에 있는 데이터 피드의 권장 사항을 기반으로 세그먼트를 트레이트를 추가하는 방법을 보여주는 [!UICONTROL Audience Marketplace] 워크플로우에 대해 간략하게 설명합니다. 이러한 권장 사항은 *이*&#x200B;에 가입되지 않은 데이터 피드를 기반으로 합니다.

>[!VIDEO](https://video.tv.adobe.com/v/29363/)

## 개요

[!UICONTROL Trait Recommendations]을( [!DNL Adobe Sensei]를) 통해 은(는) 데이터 과학을 Audience Manager의 일반 워크플로우에 적용하는 것입니다.
[!UICONTROL Trait Recommendations]을 사용하면 [세그먼트 빌더](segment-builder.md)에서 세그먼트를 작성하거나 편집할 때 포함할 수 있는 추가 트레이트에 대한 권장 사항을 얻을 수 있습니다. 이러한 권장 사항은 세그먼트 규칙의 트레이트와 유사합니다.

Audience Manager은 자사 트레이트의 트레이트 권장 사항을 **[!UICONTROL Recommendations]** 섹션과 **[!UICONTROL Audience Marketplace]** 섹션의 **[!UICONTROL Recommendations from Marketplace]** 섹션에 모두 표시합니다.

세그먼트에 권장 트레이트를 추가하여 타겟 대상자를 늘리십시오.

![트레이트 Recommendations 개요](assets/trait-recommendations-overview-full.png)

**간단히 말해서:**

* Audience Manager은 [!UICONTROL Recommendations] 섹션에 자사 트레이트를 표시합니다. 구독하지 않은 공개 및 비공개 피드의 마켓플레이스 권장 사항은 [!UICONTROL Recommendations from Marketplace] 섹션에 표시됩니다. 피드 이름을 클릭하여 [!UICONTROL Audience Marketplace] 로 이동하고 구독합니다.
* Audience Manager은 세그먼트 규칙의 트레이트와 유사한 최대 50개의 트레이트를 표시합니다.
* 권장 사항을 표시하지 않을 데이터 소스를 필터링할 수 있습니다.
* 유사성을 계산할 때 Audience Manager은 지난 30일 동안 트레이트에 대해 자격이 있는 [UUIDs](../../reference/ids-in-aam.md)를 고려합니다.
* 오류 메시지가 표시되면 &quot;유사한 트레이트가 없습니다. 트레이트가 너무 새로울 수 있음.&quot;을 의미하는 것은 지난 30일 동안 해당 트레이트에 대한 활동이 없거나 Audience Manager이 해당 트레이트에 대한 권장 사항을 아직 업데이트하지 않았음을 의미합니다. 24시간 후에 다시 시도하세요.

## 사용 사례

[!UICONTROL Trait Recommendations] 을 사용하면 Audience Manager 사용 방식에 따라 워크플로우를 개선할 수 있습니다.

* 마케터는 유사한 트레이트의 도움을 받아 상호 보완적인 제품에 관심이 있는 대상을 신속하게 찾을 수 있으므로 도달 범위를 늘릴 수 있습니다.
* 게시자로 Audience Manager을 사용하는 경우 [!UICONTROL Trait Recommendations]을 사용하여 대상 행동을 이해하고 광고 판매 또는 사용자 획득을 위한 더 나은 세그먼트를 작성할 수 있습니다.
* [!UICONTROL Audience Marketplace] 데이터 구매자는 많은 피드를 탐색하지 않고 관련 있는 타사 데이터를 검색하려고 합니다.
* [!UICONTROL Audience Marketplace] 데이터 제공업체에서는 최적 및 관련 구독의 혜택을 누릴 수 있도록 관련 데이터를 구매자에게 추천하고 싶습니다.

## 트레이트 Recommendations과 알고리즘 모델의 차이점

### 알고리즘 모델

[!UICONTROL Algorithmic Models] 가장 영향력 있는 트레이트를 찾을 뿐만 아니라 이러한 트레이트를 기반으로 사용자에 대한 점수를 매기고 각 사용자에게 개별 점수를 지정합니다. 그런 다음, 사용자를 타겟팅하는 알고리즘 트레이트를 만듭니다. [!UICONTROL Trait Builder]의 정확도와 도달 범위 컨트롤을 사용하면 영향력 있는 트레이트를 가진 모든 사용자 중에서 타겟팅할 사용자를 지정할 수 있습니다.

[!UICONTROL Algorithmic Models] 다른 정확도 수준에서 사용자를 선택하고 더 잘 전환되 [!UICONTROL Audience Lab] 는 사용자 그룹을 테스트할 수 있습니다. [대상 랩의 모델 비교](../../features/audience-lab/audience-lab-use-cases.md#compare-models)에서 자세한 사용 사례를 확인하십시오.

[!UICONTROL Algorithmic Models]에서 모델은 8일마다 실행되고 알고리즘 트레이트에 맞는 사용자를 새로 고칩니다.

### 트레이트 추천

[!UICONTROL Trait Recommendations] 는 세그먼트에서 사용 중인 트레이트와 유사한 다른 트레이트에 대한 통찰력을 얻는 빠른 방법입니다.

다음 경우에 [!UICONTROL Trait Recommendations]을 사용해야 합니다.

* 세그먼트를 만드는 동안 빠른 통찰력이 필요한 경우
* 짧은 캠페인에 세그먼트를 사용하거나 전환되는 대상을 빠르게 억제하려는 경우
* 도달 범위를 극대화하려는 경우

## 워크플로우

[세그먼트 빌더](segment-builder.md)에서 세그먼트를 만들거나 편집할 때 세그먼트 규칙의 트레이트와 유사한 트레이트를 탐색할 수 있습니다. [세그먼트 빌더](segment-builder.md) 워크플로우는 새 세그먼트와 기존 세그먼트에 대해 매우 유사합니다.

### 새 세그먼트

1. **대상 데이터 > 세그먼트**&#x200B;로 이동하고 **새로 추가**&#x200B;를 클릭합니다.
1. **트레이트** 드롭다운 상자에서 하나 이상의 트레이트를 세그먼트 규칙에 추가합니다.
1. 구독한 피드에서 **[!UICONTROL Recommendations]** 섹션에서 자사 권장 트레이트 및 [!UICONTROL Audience Marketplace] 트레이트 권장 사항을 볼 수 있습니다. **[!UICONTROL Recommendations from Marketplace]** 섹션에는 구독하지 않은 피드의 트레이트 권장 사항이 표시됩니다. 이러한 모든 권장 사항은 세그먼트 규칙에 추가한 트레이트와 유사합니다. 아래로 스크롤하여 모든 권장 트레이트를 봅니다.
1. (선택 사항) 특정 데이터 소스에서 권장 자사 트레이트를 제외하려면 제외할 데이터 소스에 대해 **X** 기호를 클릭합니다.

   >[!NOTE]
   >
   >제외된 데이터 소스는 권장 트레이트 목록 바로 위에 표시됩니다. 회색 상자에서 **X**&#x200B;을 클릭하여 제외를 제거하고 각 데이터 소스의 결과를 다시 확인합니다.
1. 권장 트레이트를 세그먼트 규칙에 추가하려면 **+** 기호를 클릭합니다.

>[!IMPORTANT]
>
>세그먼트에 [!UICONTROL Marketplace] 트레이트를 추가할 때 해당 데이터 피드에 가입하기 전까지 트레이트는 세그먼트 예측에만 사용됩니다. 구독하지 않은 데이터 피드에서 발생한 트레이트는 트레이트 목록에서 장바구니 아이콘으로 표시됩니다. 트레이트 이름을 클릭하여 데이터 피드 페이지로 이동하여 구독합니다.
>
>![marketplace에서 구독하지 않음](assets/trait-recommendations-marketplace.png)
>
>해당 데이터 피드에 가입해야 타사 트레이트가 있는 세그먼트를 저장할 수 있습니다.

### 기존 세그먼트

1. **[!UICONTROL Audience Data]>[!UICONTROL Segments]** 로 이동하여 편집할 세그먼트를 선택하고 ![편집](assets/edit-button.png)을 클릭합니다.
1. [!UICONTROL Traits] 드롭다운 상자로 스크롤합니다.
1. 세그먼트 규칙에 이미 있는 트레이트와 유사한 권장 트레이트를 볼 수 있습니다. 아래로 스크롤하여 모든 권장 트레이트를 봅니다.
1. (선택 사항) 특정 데이터 소스에서 권장 트레이트를 제외하려면 제외할 데이터 소스에 대해 **X** 기호를 클릭합니다.

   >[!NOTE]
   >
   >제외된 데이터 소스는 권장 트레이트 목록 바로 위에 표시됩니다. 회색 상자에서 **X**&#x200B;을 클릭하여 제외를 제거하고 각 데이터 소스의 결과를 다시 확인합니다.
1. 권장 트레이트를 세그먼트 규칙에 추가하려면 **+** 기호를 클릭합니다.

세그먼트를 만들거나 편집하고 세그먼트 규칙에 트레이트를 추가하면 추가한 트레이트와 유사한 최대 50개의 권장 트레이트가 표시됩니다. 세그먼트 규칙에 두 개 이상의 트레이트가 포함된 경우 Audience Manager은 라운드 로빈 방법을 사용하여 각 트레이트에 대해 가장 일치하는 항목을 표시한 다음, 각 트레이트에 대해 두 번째 가장 일치하는 항목 등을 세그먼트 규칙에서 모집단별로 가장 큰 50개의 트레이트에 대해 표시합니다.

![세 가지 기본 트레이트](assets/three-base-traits.png)

예를 들어 아래 표시된 대로 세그먼트 규칙에 세 가지 트레이트가 있는 경우 권장되는 트레이트는 다음과 같습니다.

1. 트레이트 3에 대한 일치 항목(모집단이 가장 큰 트레이트);
1. 트레이트 1에 대한 최상의 일치
1. 트레이트 2에 대한 최상의 일치
1. 트레이트 3에 대한 두 번째 우수 사례;
1. 트레이트 1에 대해 두 번째 우수 사례와 50개의 트레이트가 나올 때까지 연결합니다.

특정 트레이트에 대한 권장 사항을 가져오려면 세그먼트 규칙(1) 또는 권장 트레이트 보기(2)에서 트레이트를 클릭하면 됩니다.

![base-traits-example](assets/three-base-traits-numbered.png)

자사 트레이트를 클릭하면 아래 이미지와 같이 팝업 창이 열립니다. 권장되는 트레이트가 세그먼트의 일부가 아닌 경우 **+**&#x200B;를 눌러 세그먼트에 추가할 수 있습니다.

![세그먼트 추가](assets/add_to_segments.png)

>[!TIP]
>
>트레이트 정보 팝업 창 내에서 권장 사항을 생성하는 동안 기본 페이지에서 제외된 데이터 소스가 고려됩니다. 또한 이 보기에서 데이터 소스를 제외하는 경우 기본 페이지에 제외 사항이 적용됩니다.

>[!NOTE]
>
>권장 트레이트는 [!UICONTROL Audience Marketplace]에서 구독한 데이터 피드의 자사 트레이트 또는 타사 트레이트일 수 있습니다.

## 작동 방법

트레이트 추천을 생성하기 위해 Audience Manager은 대상 트레이트와 사용자 계정이 액세스 권한이 있는 모든 다른 트레이트 간 [Jaccard 유사성](https://en.wikipedia.org/wiki/Jaccard_index)을 계산합니다(타사 데이터 포함). Audience Manager은 가장 높은 유사성을 갖는 최대 50개의 트레이트를 표시합니다.

## 트레이트 유사성 점수 {#trait-similarity-score}

Audience Manager은 [!UICONTROL UUID]s 수에 따라 교집합 및 결합을 계산한 다음 두 트레이트 간에 [!UICONTROL Trait Similarity Score]을 계산합니다. 두 트레이트 A와 B의 경우 계산은 다음과 같습니다.

![jaccard-유사성](assets/jaccard_similarity.png)

아래의 두 가지 예도 참조하십시오.

### 예제 1 - 낮은 트레이트 유사성 점수

두 트레이트 A와 B가 주어지면 각 트레이트의 모집단이 100만 [!UICONTROL UUID]s이고, 이 두 트레이트에 모두 사용할 수 있는 인구는 25,000[!UICONTROL UUID]입니다.
위의 공식을 사용하면 다음과 같은 결과가 발생합니다. 25,000 / 1,975,000 = 0.012. 낮은 [!UICONTROL Trait Similarity Score], 두 트레이트는 매우 유사합니다.

![특성-recommendations-low-overlap](assets/Trait-Recommendations-Low-overlap.png)

### 예제 2 - 트레이트 유사성 점수

동일한 트레이트 A와 B에 두 트레이트에 대한 자격이 있는 400,000 [!UICONTROL UUID]이 있는 경우 [!UICONTROL Trait Similarity Score]이 훨씬 높습니다.
400,000 / 1,600,000 = 0.25

![특성-recommendations-high-overlap](assets/Trait-Recommendations-High-overlap.png)

### 트레이트 유사성 점수를 해석하는 방법

트레이트 유사성에 대한 대략적인 안내서로 아래 표를 사용하십시오. 이 안내서는 대부분의 트레이트에서 관찰되는 유사성 점수를 기반으로 합니다.

| [!UICONTROL Trait Similarity Score] | 유의 |
|---------|----------|
| 0.1 이상 | 트레이트 간 높은 유사성 |
| 0.03 - 0.1 | 트레이트 간 중간 유사성 |
| 0.01 - 0.03 | 트레이트 간 낮은 유사성 |
| 0 - 0.01 | 트레이트 간 매우 낮은 유사성 |

## 역할 기반 액세스 제어(RBAC)

[!UICONTROL Role-Based Access Controls]([!UICONTROL RBAC])을 사용하는 회사의 경우, 권장 트레이트를 보려면 세그먼트를 만들고 편집할 수 있는 권한이 있어야 합니다. 표시되는 트레이트 권장 사항은 [!UICONTROL RBAC]을 통해 액세스할 수 있는 데이터 소스의 트레이트 권장 사항일 뿐입니다.

>[!IMPORTANT]
>
>세그먼트에 [!UICONTROL Marketplace Recommendations]을 추가하려면 먼저 사용자가 해당 데이터 피드에 가입해야 합니다. 관리자 권한이 있는 사용자만 [!UICONTROL Audience Marketplace] 데이터 피드에 가입할 수 있습니다.

[!UICONTROL RBAC] 컨트롤 [여기](../administration/administration-overview.md)에 대해 자세히 알아보십시오.

## 제한

* 현재, Audience Manager은 폴더 트레이트를 권장 트레이트로 표시하지 않습니다. 폴더 트레이트 [여기](../traits/manage-folder-traits.md)에 대해 자세히 알아보십시오.
* 트레이트 Recommendations을 표시할 때 Audience Manager은 세그먼트 규칙에서 [!DNL Boolean] 연산자([!DNL AND], [!DNL OR], [!DNL NOT])를 고려하지 않습니다.
