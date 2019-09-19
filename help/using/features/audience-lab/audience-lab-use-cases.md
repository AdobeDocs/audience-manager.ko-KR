---
description: Audience Lab을 사용하면 테스트 그룹을 만드는 데 기준 세그먼트를 사용할 수 있으므로 몇 가지 사용 사례를 활용할 수 있습니다. 테스트 그룹을 여러 개의 상호 배타적인 테스트 세그먼트로 나누어 다른 대상에 매핑한 다음 전환 유도 시 가장 효과적인 세그먼트 중 하나를 결정할 수 있습니다.
seo-description: Audience Lab을 사용하면 테스트 그룹을 만드는 데 기준 세그먼트를 사용할 수 있으므로 몇 가지 사용 사례를 활용할 수 있습니다. 테스트 그룹을 여러 개의 상호 배타적인 테스트 세그먼트로 나누어 다른 대상에 매핑한 다음 전환 유도 시 가장 효과적인 세그먼트 중 하나를 결정할 수 있습니다.
seo-title: Audience Lab 사용 사례
solution: Audience Manager
title: Audience Lab 사용 사례
topic: DIL API
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Lab 사용 사례 {#audience-lab-use-cases}

[!UICONTROL Audience Lab] 테스트 그룹을 만들기 위해 기준 세그먼트를 사용할 수 있도록 함으로써 여러 가지 사용 사례를 활성화합니다. 테스트 그룹을 여러 개의 상호 배타적인 테스트 세그먼트로 나누어 다른 대상에 매핑한 다음 전환 유도 시 가장 효과적인 세그먼트 중 하나를 결정할 수 있습니다.

## Audience Lab의 모델 비교 {#compare-models}

에서 여러 가지 유형의 모델과 소스를 사용할 수 [!DNL Audience Manager]있습니다. [!UICONTROL Audience Lab] 이 제품을 사용하면 활성 모델에서 고객의 전환율을 손쉽게 비교할 수 있습니다.

<!-- audience-lab-compare-models.xml -->

이 경우 서로 다른 모델을 비교합니다. 사내 데이터 웨어하우스를 통해 생성된 모델을 사용하여 온보딩 트레이트로 가져오거나 [!DNL Audience Manager] 알고리즘 모델 [기능을](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) 사용할 수 [있습니다](../../features/algorithmic-models/understanding-models.md) [!DNL Audience Manager].

1. 모델 빌더에서 또는 외부 [플랫폼을](../../features/algorithmic-models/create-model.md)통해 두 개의 모델을 만듭니다.
1. 알고리즘 모델에서 [알고리즘 특성을](../../features/traits/create-algorithmic-traits.md) 만들거나 자체 모델을 온보드 트레이트로 가져올 수 있습니다.
1. 두 모델의 사용자가 겹치지 않도록 상호 배타적인 세그먼트를 만듭니다.

   * 모델 1 *세그먼트* 및 모델 2 *세그먼트를 만듭니다*.
   * 모델 1 세그먼트에 대한 세그먼트 *규칙을 모델* 1 [!DNL AND NOT] 특성 모델 2 트레이트로, 모델 2 세그먼트의 경우 그 반대의 경우 *세그먼트 규칙이 있어야*&#x200B;합니다.

1. [두 개의 세그먼트 테스트 그룹을](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) 만듭니다. [!UICONTROL Audience Lab]하나는 *모델 1* 세그먼트가 기준선으로, 다른 하나는 모델 2 *세그먼트가 기준선으로* 되어있습니다.

   * 두 테스트 그룹에 대해 동일한 변수를 유지합니다.동일한 대상, 크리에이티브, 전환 트레이트
   * 테스트 세그먼트에 유사한 사용자 수가 있는지 확인합니다(예: 160만 명, 180만 명, 160만 명, 160만 명이 적당하지 않음).
   * 각 테스트 세그먼트 테스트 그룹에서 제어 세그먼트를 예약합니다. 이렇게 하면 테스트에서 각 세그먼트의 작은 부분을 명시적으로 타깃팅하지 않고 분리할 수 있습니다.

1. 결과를 검토합니다.

   * Audience [Lab 보고 보기에는](../../features/audience-lab/audience-lab-reporting-view.md) 각 모델이 구동하는 전환 수가 표시됩니다. 전환 기반 캠페인의 경우 가장 많은 전환을 유도하는 테스트 세그먼트는 성과가 가장 좋은 모델을 나타냅니다.
   * 제어 세그먼트가 있으므로 모델이 "표준 타깃팅"에 대해 어떻게 수행되었는지 평가할 수도 있습니다. 한 모델과 다른 모델을 테스트하는 것뿐만 아니라 "이 모델이 일반적인 방법보다 더 잘 되었습니까?"라는 질문을 테스트하는 것입니다.

## 다양한 대상에 대한 크리에이티브 테스트 {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

크리에이티브가 여러 [!UICONTROL Audience Lab] 대상을 대상으로 전환율을 측정하는 데 사용합니다. 또한 이 사용 사례를 통해 자연스러운 전환 대비 크리에이티브 전환율을 측정할 수 있습니다.

1. [세그먼트 테스트](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)그룹을 만들고 기본 세그먼트로 크리에이티브를 테스트할 세그먼트를 선택합니다.
1. 기준 세그먼트를 테스트 세그먼트로 분할하고 세그먼트를 제어합니다.
1. 테스트 세그먼트를 테스트하려는 다른 대상에 매핑합니다.
1. 제어 세그먼트는 보류할 수 있으며 대상에 매핑할 수 없습니다. 제어 세그먼트는 테스트 크리에이티브를 통해 타깃팅되어서는 안 됩니다.
1. 테스트 시작 날짜와 종료 날짜를 지정합니다.
1. 대상에서 세그먼트 및 크리에이티브를 설정합니다.
1. Audience [Lab 보고 보기에서는](../../features/audience-lab/audience-lab-reporting-view.md) 크리에이티브가 대상을 통해 이동되는 횟수를 보여줍니다.
1. 제어 세그먼트를 만들었으므로 크리에이티브가 자연 발생 변환에 대해 어떻게 수행되었는지 평가할 수도 있습니다. 질문을 테스트하고 있습니다."이러한 크리에이티브한 요소가 일반적인 방법보다 더 높은 전환율을 생성했습니까?"
