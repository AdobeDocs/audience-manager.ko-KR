---
description: Audience Lab에서는 테스트 그룹을 생성하는 데 기준선 세그먼트를 사용할 수 있으므로 여러 사용 사례를 사용할 수 있습니다. 테스트 그룹을 여러 상호 배타적인 테스트 세그먼트로 나누고, 이들을 서로 다른 대상에 매핑한 다음 어느 세그먼트가 전환 유도에 가장 효과적인지를 결정할 수 있습니다.
seo-description: Audience Lab enables several use cases by allowing you to use baseline segments for creating test groups. You can divide test groups into several mutually exclusive test segments, map these to different destinations and then determine which of the segments are most effective in driving conversions.
seo-title: Audience Lab Use Cases
solution: Audience Manager
title: 대상 랩 사용 사례
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
feature: Audience Lab
exl-id: b68f48bd-0d5d-4b72-84f3-a6f3acea6c49
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 1%

---

# 대상 랩 사용 사례 {#audience-lab-use-cases}

[!UICONTROL Audience Lab] 에서는 테스트 그룹을 만드는 데 기준선 세그먼트를 사용할 수 있도록 하여 여러 사용 사례를 사용할 수 있습니다. 테스트 그룹을 여러 상호 배타적인 테스트 세그먼트로 나누고, 이들을 서로 다른 대상에 매핑한 다음 어느 세그먼트가 전환 유도에 가장 효과적인지를 결정할 수 있습니다.

## 대상 랩의 모델 비교 {#compare-models}

에서 모델의 여러 가지 유형과 소스를 사용할 수 있습니다 [!DNL Audience Manager]. [!UICONTROL Audience Lab] 는 활성 모델에서 고객의 전환율을 비교하는 쉬운 방법을 제공합니다.

<!-- audience-lab-compare-models.xml -->

이 사용 사례에서는 서로 다른 모델을 비교하고 있습니다. 사내 데이터 웨어하우스를 통해 만든 모델을 사용하여 로 가져올 수 있습니다. [!DNL Audience Manager] 다음으로: [온보딩된 트레이트](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) 또는 다음을 사용할 수 있습니다 [알고리즘 모델](../../features/algorithmic-models/understanding-models.md) 의 기능 [!DNL Audience Manager].

1. 다음 중 하나에서 두 모델을 만듭니다. [모델 빌더](../../features/algorithmic-models/create-model.md)또는 외부 플랫폼을 통해 실행할 수 있습니다.
1. 만들기 [알고리즘 트레이트](../../features/traits/create-algorithmic-traits.md) 알고리즘 모델에서 가져오거나 고유한 모델을 온보딩된 트레이트로 가져옵니다.
1. 두 모델의 사용자가 겹치지 않도록 함께 사용할 수 없는 세그먼트를 만듭니다.

   * 만들기 *모델 1 세그먼트* 및 a *모델 2 세그먼트*.
   * 다음에 대한 세그먼트 규칙 보유 *모델 1 세그먼트* 모델 1 트레이트 [!DNL AND NOT] 모델 2 트레이트 및 그 반대의 경우 *모델 2 세그먼트*.

1. [두 개의 세그먼트 테스트 그룹 만들기](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) 위치: [!UICONTROL Audience Lab], 1개 포함 *모델 1 세그먼트* 를 기준선으로, 를 와 함께 *모델 2 세그먼트* 를 기준선으로 사용합니다.

   * 동일한 대상, 크리에이티브, 전환 트레이트의 두 테스트 그룹에 대해 변수를 동일하게 유지합니다.
   * 테스트 세그먼트에 유사한 사용자 수가 있는지 확인합니다(예: 160만 및 180만 이 괜찮음, 160만 및 1600만 은 그렇지 않음).
   * 각 테스트 세그먼트 테스트 그룹에서 제어 세그먼트를 예약합니다. 이렇게 하면 각 세그먼트의 작은 부분을 제외하고 테스트에서 명시적으로 타겟팅하지 않을 수 있습니다.

1. 결과를 검사합니다.

   * 다음 [대상 랩 보고 보기](../../features/audience-lab/audience-lab-reporting-view.md) 에서는 각 모델이 유도하는 전환의 수를 보여 줍니다. 전환 기반 캠페인의 경우, 가장 많은 전환을 유도하는 테스트 세그먼트는 가장 성과가 좋은 모델을 나타냅니다.
   * 제어 세그먼트가 있으므로 모델이 &quot;표준 타깃팅&quot;에 대해 수행한 방법을 평가할 수도 있습니다. 단지 한 모델을 다른 모델에 대해 테스트하는 것뿐만 아니라 &quot;이 모델이 일반적인 사례보다 더 잘했습니까?&quot;라는 질문을 테스트하는 것입니다.

## 대상 간 크리에이티브 테스트 {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

사용 [!UICONTROL Audience Lab] 크리에이티브가 서로 다른 대상 간에 이동하는 전환 수를 측정합니다. 이 사용 사례에서는 자연적으로 발생하는 전환에 대한 크리에이티브의 전환을 측정할 수도 있습니다.

1. [세그먼트 테스트 그룹 만들기](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)를 클릭하고 크리에이티브를 테스트할 세그먼트를 기준선 세그먼트로 선택합니다.
1. 기준선 세그먼트를 테스트 세그먼트와 컨트롤 세그먼트로 분할합니다.
1. 테스트 세그먼트를 테스트할 다른 대상에 매핑합니다.
1. 제어 세그먼트는 보류될 수 있으며 어떤 대상에도 매핑되지 않습니다. 자연적으로 발생하는 전환에 대한 결과 기준선을 설정하기 위해 컨트롤 세그먼트를 테스트 크리에이티브의 대상으로 해서는 안 됩니다.
1. 테스트의 시작 날짜와 종료 날짜를 지정합니다.
1. 대상에서 세그먼트 및 크리에이티브를 설정합니다.
1. 다음 [대상 랩 보고 보기](../../features/audience-lab/audience-lab-reporting-view.md) 은 크리에이티브가 대상을 통해 유도하는 전환 수를 보여 줍니다.
1. 제어 세그먼트를 만들었으므로 크리에이티브가 자연적으로 발생하는 전환에 대해 어떻게 했는지 평가할 수도 있습니다. &quot;이 크리에이티브가 일반적인 사례보다 높은 전환율을 생성했습니까?&quot;라는 질문을 테스트하는 것입니다.
