---
description: 예측 고객(Predictive Audiences)을 사용하면 데이터 과학을 사용하여 알 수 없는 고객을 고유한 개인으로 실시간으로 분류할 수 있습니다.
seo-description: 예측 고객(Predictive Audiences)을 사용하면 데이터 과학을 사용하여 알 수 없는 고객을 고유한 개인으로 실시간으로 분류할 수 있습니다.
seo-title: 예측 대상 FAQ
solution: Audience Manager
title: Audience Manager 예측 고객
translation-type: tm+mt
source-git-commit: 8cf504fa811e4043f83d0b9f11754065efccf7bb

---


# 예측 대상 FAQ

FAQ를 [!UICONTROL Predictive Audiences]참조하십시오.

 

**언제[!UICONTROL Predictive Audiences]반대로 사용해야[!UICONTROL Look-alike modeling]합니까?**

[!UICONTROL Predictive Audiences] 다양한 사용 사례를 [!UICONTROL Look-alike modeling] 제공합니다. 두 알고리즘의 주요 차이점은 다음과 같습니다.

1. [!UICONTROL Look-alike modeling] 작은 대상을 입력으로 가져와 확장합니다. [!UICONTROL Predictive Audiences] 많은 고객을 입력으로 가져와 개인별로 정의된 소규모 개별 고객으로 나눕니다.
1. 기본 세그먼트 수는 각 알고리즘에 대해 다릅니다. [!UICONTROL Predictive Audiences] 을 사용하려면 기준선이 두 개 이상 필요하고 동시에 기준선은 한 [!UICONTROL Look-alike modeling] 개 이상 있어야 합니다.
1. [!UICONTROL Predictive Audiences] 실시간 세그먼트 평가를 수행하지만 [!UICONTROL Look-alike modeling] 그렇지 않습니다.

사용 사례에 따라 귀하와 더욱 연관성 있는 모델을 결정해야 합니다.

많은 기준선을 사용하여 [!UICONTROL Predictive Audiences] 모델을 만드는 것은 실시간 평가 없이 동일한 유사 모델을 작성하는 것과 동일한 것으로 간주할 수 있으며 방문자가 별개의 한 사람이 아니라 여러 다른 성향에 속할 가능성이 매우 높습니다.

 

**몇 개의 개인/모델을 만들 수 있습니까?**

최대 10개의 [!UICONTROL Predictive Audiences] 모델을 만들 수 있습니다. 각 모델에 대해 최대 50개의 기준 트레이트 또는 세그먼트를 정의할 수 있습니다.

 

**세그먼트에서 새 세그먼트를 만드는 방법은[!UICONTROL Predictive Audiences]무엇입니까?**

> **[!UICONTROL Audience Data]** 로 **[!UICONTROL Segments]**&#x200B;이동하고 **[!UICONTROL Predictive Audiences]** 폴더를 클릭합니다. 원하는 세그먼트를 찾아 복제한 다음 필요에 따라 편집합니다.

 

**내 온보딩된 방문자 중 몇 명이 분류되지 않은 이유는 무엇입니까?**

현재 대상 분류는 컨텐츠의 일부로 정의된 인증된 사용자를 제외하고 실시간 인증에만 작동합니다 [!UICONTROL Profile Merge Rules].

온보드 데이터에 대한 전체 지원이 향후 업데이트에 추가됩니다.

 

**모델이 만든 첫 번째 결과는 언제 볼 수 있습니까?**

[!UICONTROL Predictive Audiences] 모델이 성공적으로 실행된 경우 모델 생성 후 24시간 이내에 모델 결과를 사용할 수 있습니다.

24시간 이내에 모델이 결과를 내지 않는 경우 Adobe 담당자에게 문의하십시오.

 

**모델이 결과를 생성하지 않거나 경고 상태를 표시하지 않는 이유는 무엇입니까?**

[!UICONTROL Predictive Audiences] 다음과 같은 여러 가지 이유로 인해 모델이 결과를 생성하지 못할 수 있습니다.

1. 선택한 페르소나 트레이트/세그먼트 중 사용자 프로필이 충분하지 않습니다. 각 가상 사람이 최소 수백 개의 사용자 프로필을 보유할 수 있도록 트레이트 또는 세그먼트를 선택하는 것이 좋습니다.
1. 선택한 페르소나 트레이트/세그먼트 중 사용자 프로필에 충분한 데이터가 없습니다(분석할 트레이트가 충분하지 않음).
1. 대상 대상 트레이트/세그먼트에 지난 30일 이내에 활성 또는 온보드 사용자가 없습니다.
1. 지난 30일 이내에 활성 상태이거나 온보드 대상 사용자의 사용자 프로필에 충분한 데이터가 없습니다(분석할 트레이트가 충분하지 않음).

관련 결과를 얻기 위해 [!UICONTROL Predictive Audiences] 알고리즘은 DCS에서 보는 실시간 사용자 활동을 기반으로 트레이트 및 세그먼트 관계를 평가합니다. 아직 충분한 사용자가 없는 새 기본 트레이트 및 세그먼트를 선택하는 경우 알고리즘은 대상을 분류하는 데 2-3일이 걸릴 수 있습니다.

최적의 결과를 얻으려면 개인 선택 [기준 및 타겟 대상자 선택](../features/algorithmic-models/predictive-audiences.md#selection-personas) 기준의 제안된 지침을 [따르십시오](../features/algorithmic-models/predictive-audiences.md#selection-audience).

 

**모델이 오류 상태를 표시하는 이유는 무엇입니까?**

모델을 실행하지 못했습니다. 이러한 경우 Adobe 담당자에게 문의하십시오.

 

**예측 대상 세그먼트에 대한 프로필 병합 규칙을 변경하려면 어떻게 합니까?**

세그먼트를 [!UICONTROL Predictive Audiences] 복제하고 중복된 세그먼트에 [!UICONTROL Profile Merge Rule] 대한 세그먼트를 변경합니다.

 

**특정 특성/세그먼트에 속하지 않는 대상 대상의 사용자가 분류되지 않을 수 있습니까?**

예. 사용자의 프로필에 어떤 트레이트도 포함되어 있지 않은 경우 이 경우, 사용자는 모든 페르소나 트레이트/세그먼트에 대해 일치 점수를 0으로 받게 되므로 예측 세그먼트로 분류되지 않습니다.

 

**예측 세그먼트 중 하나로 분류된 사용자를 다른[!UICONTROL Predictive Audiences]세그먼트로 재분류할 수 있습니까?**

예. 알고리즘은 매일 훈련되므로 특성 점수 측면에서 각 개인에 대한 변경 사항을 적용합니다. 세그먼트의 일부인 사용자가 활성 상태인 경우 트레이트 점수의 변경은 지난 30일 활동을 기준으로 분류를 변경할 수 있습니다. [!UICONTROL Predictive Audiences]

 

**대상 분류가 수행되는 특성을 볼 수 있습니까?**

예. 모델 보고 페이지에서 모든 기준선에 대해 영향력 있는 모든 트레이트를 볼 수 있습니다. 영향력 [있는 트레이트를 참조하십시오](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits).

 

**기준선 트레이트 또는 세그먼트를 편집하면 모델은 어떻게 됩니까?**

모델은 하루에 한 번 트레이트 또는 세그먼트를 평가합니다. 업데이트 다음날 업데이트된 분류가 표시됩니다.

 

**모델이 배울 데이터 소스를 선택할 수 있습니까?**

아니요. 데이터 소스 선택은 지원되지 않습니다. 알고리즘은 모든 자사 트레이트에서 [!UICONTROL Predictive Audiences] 학습합니다.