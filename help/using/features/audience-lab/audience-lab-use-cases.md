---
description: Audience Lab 에서는 테스트 그룹을 만들기 위해 기준 세그먼트를 사용할 수 있어 여러 가지 사용 사례를 사용할 수 있습니다. 테스트 그룹을 상호 배타적인 여러 테스트 세그먼트로 나누고, 이를 다른 대상에 매핑한 다음, 전환 시 가장 효과적인 세그먼트 중에서 가장 효과적인 세그먼트를 판별할 수 있습니다.
seo-description: Audience Lab 에서는 테스트 그룹을 만들기 위해 기준 세그먼트를 사용할 수 있어 여러 가지 사용 사례를 사용할 수 있습니다. 테스트 그룹을 상호 배타적인 여러 테스트 세그먼트로 나누고, 이를 다른 대상에 매핑한 다음, 전환 시 가장 효과적인 세그먼트 중에서 가장 효과적인 세그먼트를 판별할 수 있습니다.
seo-title: Audience Lab 사용 사례
solution: Audience Manager
title: Audience Lab 사용 사례
topic: DIL API
uuid: 727 bec 8 a-df 9 a -40 cc-b 8 a 7-e 1980 d 146 a 84
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Lab Use Cases {#audience-lab-use-cases}

[!UICONTROL Audience Lab] 테스트 그룹을 만들기 위해 기준 세그먼트를 사용할 수 있도록 하여 여러 가지 사용 사례를 활성화합니다. 테스트 그룹을 상호 배타적인 여러 테스트 세그먼트로 나누고, 이를 다른 대상에 매핑한 다음, 전환 시 가장 효과적인 세그먼트 중에서 가장 효과적인 세그먼트를 판별할 수 있습니다.

## Compare Models in Audience Lab {#compare-models}

You can use several different types and sources of models in [!DNL Audience Manager]. [!UICONTROL Audience Lab] 활성 모델에서 고객의 전환율을 손쉽게 비교할 수 있는 방법을 제공합니다.

<!-- audience-lab-compare-models.xml -->

이 경우 다른 모델을 비교하게 됩니다. You can either use models created via an in-house data warehouse and import them in [!DNL Audience Manager] as [Onboarded Traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) or you can use the [Algorithmic Models](../../features/algorithmic-models/understanding-models.md) feature in [!DNL Audience Manager].

1. [모델 빌더에서](../../features/algorithmic-models/create-model.md)또는 외부 플랫폼을 통해 두 개의 모델을 만듭니다.
1. Create [algorithmic traits](../../features/traits/create-algorithmic-traits.md) from the algorithmic model or import your own models as onboarded traits.
1. 두 모델의 사용자가 겹치지 않도록 상호 배타적인 세그먼트를 만듭니다.

   * *모델 1 세그먼트와* *모델 2 세그먼트를 만듭니다*.
   * *모델 1 세그먼트에* 대한 세그먼트 규칙은 모델 1 트레이트 [!DNL AND NOT] 모델 2 트레이트, 그 반대로 *모델 2 세그먼트에 대한 세그먼트 규칙이 있어야*&#x200B;합니다.

1. [두 세그먼트 테스트 그룹을](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) 만듭니다. [!UICONTROL Audience Lab]하나는 *모델 1 세그먼트가* 있고, 다른 하나는 *모델 2 세그먼트가* 있는 세그먼트 테스트 그룹입니다.

   * 두 테스트 그룹 모두에 대해 변수를 동일하게 유지합니다. 동일한 대상, 크리에이티브, 전환 트레이트입니다.
   * 테스트 세그먼트의 사용자 수가 비슷한지 확인합니다 (예: 160만 및 1800만 명, 160만 및 1600만 명 이상 포함).
   * 각 테스트 세그먼트 테스트 그룹에서 제어 세그먼트를 예약합니다. 이렇게 하면 각 세그먼트의 작은 부분을 별도로 설정하고 테스트에서 명시적으로 타깃팅하지 않아도 됩니다.

1. 결과 검사:

   * [Audience Lab 보고 보기에는](../../features/audience-lab/audience-lab-reporting-view.md) 각 모델이 운전하는 전환 수가 표시됩니다. 전환 기반 캠페인의 경우 가장 많은 전환을 유도하는 테스트 세그먼트는 성과가 가장 좋은 모델을 나타냅니다.
   * 제어 세그먼트가 있으므로 모델이 "표준 타깃팅" 에 대해 어떻게 수행되었는지 평가할 수도 있습니다. 단순히 하나의 모델과 다른 모델을 테스트하는 것뿐만 아니라 "이 모델이 정상적인 관행보다 더 나은 방법은 무엇입니까?" 라는 질문을 테스트하는 것입니다.

## Testing Creatives Across Destinations {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Use [!UICONTROL Audience Lab] to measure the number of conversions a creative is driving across different destinations. 또한 이 사용 사례는 자연적으로 발생하는 전환에 대한 크리에이티브 전환을 측정할 수 있도록 해줍니다.

1. [세그먼트 테스트 그룹을](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)만들고, 크리에이티브를 기준 세그먼트로 테스트하려는 세그먼트를 선택합니다.
1. 세그먼트 세그먼트를 테스트 세그먼트로 분할하고 세그먼트를 제어합니다.
1. 테스트할 다른 대상에 테스트 세그먼트를 매핑합니다.
1. 제어 세그먼트는 대상화되고 대상에 매핑되지 않습니다. 테스트 크리에이티브가 제어 세그먼트를 타깃팅하면 자연어 전환을 위한 결과 기준선을 설정할 수 없습니다.
1. 테스트의 시작 날짜 및 종료 날짜를 지정합니다.
1. 대상에 세그먼트와 크리에이티브를 설정합니다.
1. [Audience Lab 보고 보기에는](../../features/audience-lab/audience-lab-reporting-view.md) 크리에이티브가 대상으로 하는 전환 수가 표시됩니다.
1. 제어 세그먼트를 만들었으므로 크리에이티브가 자연적으로 발생하는 전환을 기준으로 한 방법을 평가할 수도 있습니다. 다음 질문을 테스트하고 있습니다. " 이 크리에이티브는 일반 관행보다 전환율을 높였습니다. "
