---
description: Audience Lab을 사용하면 테스트 그룹을 만들기 위해 기준선 세그먼트를 사용할 수 있으므로 몇 가지 사용 사례를 사용할 수 있습니다. 테스트 그룹을 몇 개의 상호 배타적인 테스트 세그먼트로 나누고, 다른 대상에 매핑한 다음 전환을 유도하는 데 가장 효과적인 세그먼트 중 하나를 결정할 수 있습니다.
seo-description: Audience Lab을 사용하면 테스트 그룹을 만들기 위해 기준선 세그먼트를 사용할 수 있으므로 몇 가지 사용 사례를 사용할 수 있습니다. 테스트 그룹을 몇 개의 상호 배타적인 테스트 세그먼트로 나누고, 다른 대상에 매핑한 다음 전환을 유도하는 데 가장 효과적인 세그먼트 중 하나를 결정할 수 있습니다.
seo-title: 대상 랩 사용 사례
solution: Audience Manager
title: 대상 랩 사용 사례
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
feature: Audience Lab
exl-id: b68f48bd-0d5d-4b72-84f3-a6f3acea6c49
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 2%

---

# 대상 랩 사용 사례 {#audience-lab-use-cases}

[!UICONTROL Audience Lab] 테스트 그룹을 만드는 데 기준선 세그먼트를 사용할 수 있도록 하여 여러 사용 사례를 사용할 수 있도록 해줍니다. 테스트 그룹을 몇 개의 상호 배타적인 테스트 세그먼트로 나누고, 다른 대상에 매핑한 다음 전환을 유도하는 데 가장 효과적인 세그먼트 중 하나를 결정할 수 있습니다.

## 대상 랩에서 모델 비교 {#compare-models}

[!DNL Audience Manager]에서 여러 가지 유형의 모델과 소스를 사용할 수 있습니다. [!UICONTROL Audience Lab] 은 활성 모델 간에 고객의 전환율을 쉽게 비교할 수 있는 방법을 제공합니다.

<!-- audience-lab-compare-models.xml -->

이 사용 사례에서는 서로 다른 모델을 비교합니다. 사내 데이터 웨어하우스를 통해 생성된 모델을 사용하여 [!DNL Audience Manager]에 [온보딩된 트레이트](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) 로 가져오거나 [!DNL Audience Manager]에서 [알고리즘 모델](../../features/algorithmic-models/understanding-models.md) 기능을 사용할 수 있습니다.

1. [모델 빌더](../../features/algorithmic-models/create-model.md)에서 또는 외부 플랫폼을 통해 두 개의 모델을 만듭니다.
1. 알고리즘 모델에서 [알고리즘 트레이트](../../features/traits/create-algorithmic-traits.md)를 만들거나 온보딩된 트레이트로 고유한 모델을 가져옵니다.
1. 두 모델의 사용자가 겹치지 않도록 상호 배타적인 세그먼트를 만듭니다.

   * *모델 1 세그먼트* 및 *모델 2 세그먼트*&#x200B;를 만듭니다.
   * *모델 1 세그먼트*&#x200B;에 대한 세그먼트 규칙이 [!DNL AND NOT] 모델 2 트레이트에 대해 모델 1 트레이트  모델 2 트레이트가 되고, 그 반대의 경우 *모델 2 세그먼트*&#x200B;에 대해 세그먼트 규칙이 있어야 합니다.

1. [두 세그먼트 테스트 그룹](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) 을 만듭니다. 하나는  [!UICONTROL Audience Lab]모델 1  *세그먼트를 기준선으로 사용하고 다른 하나는* 모델 2  ** 세그먼테이션을 기준선으로 사용합니다.

   * 변수를 두 테스트 그룹 모두에 대해 동일하게 유지합니다.동일한 대상, 크리에이티브, 전환 트레이트.
   * 테스트 세그먼트에 유사한 수의 사용자가 있는지 확인합니다(예: 160만 명 및 180만 명, 정상 160만 명 및 1,600만 명이 아님).
   * 각 테스트 세그먼트 테스트 그룹에서 제어 세그먼트를 예약합니다. 이렇게 하면 각 세그먼트의 작은 부분을 따로 떼어 둘 수 있으며, 테스트에서 명시적으로 타깃팅하지 않습니다.

1. 결과를 검사합니다.

   * [Audience Lab 보고 보기](../../features/audience-lab/audience-lab-reporting-view.md)에는 각 모델이 구동하는 전환 수가 표시됩니다. 전환 기반 캠페인의 경우, 가장 많은 전환을 유도하는 테스트 세그먼트는 성과가 가장 좋은 모델을 나타냅니다.
   * 제어 세그먼트가 있으므로 &quot;표준 타깃팅&quot;에 대해 모델이 어떻게 작동하는지 평가할 수도 있습니다. 한 모델과 다른 모델을 테스트하고 있을 뿐 아니라 &quot;이 모델이 정상적인 방법보다 더 잘 작동합니까?&quot;라는 질문을 테스트하는 것입니다.

## 대상 간 광고 테스트 {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

[!UICONTROL Audience Lab] 을 사용하여 크리에이티브가 다른 대상에서 구동하는 전환 수를 측정합니다. 또한 이 사용 사례에서는 자연스러운 전환과 비교하여 크리에이티브 전환을 측정할 수 있습니다.

1. [세그먼트 테스트 그룹을](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) 만들고, 크리에이티브를 기준 세그먼트로 테스트할 세그먼트를 선택합니다.
1. 기준선 세그먼트를 테스트 세그먼트로 분할하고 세그먼트를 제어합니다.
1. 테스트 세그먼트를 테스트할 다른 대상에 매핑합니다.
1. 제어 세그먼트는 보류할 수 있으며 대상에 매핑되지 않습니다. 자연적으로 발생하는 전환에 대한 결과 기준을 설정하려면 테스트 크리에이티브를 대상으로 하지 않아야 합니다.
1. 테스트에 대한 시작 날짜 및 종료 날짜를 지정합니다.
1. 대상에서 세그먼트 및 크리에이티브를 설정합니다.
1. [Audience Lab 보고 보기](../../features/audience-lab/audience-lab-reporting-view.md)는 크리에이티브가 대상을 통해 구동하는 전환 수를 표시합니다.
1. 컨트롤 세그먼트를 만들었으므로 창의력이 자연적으로 발생하는 전환과 어떻게 작용했는지 평가할 수도 있습니다. 질문을 테스트하고 있습니다.&quot;이러한 창의성이 일반적인 방법보다 더 높은 전환율을 생성했습니까?&quot;
