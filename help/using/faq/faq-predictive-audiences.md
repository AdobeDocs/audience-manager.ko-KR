---
description: Predictive Audiences을 사용하면 데이터 과학을 사용하여 알 수 없는 대상을 실시간으로 개별 성향으로 분류할 수 있습니다.
seo-description: Predictive Audiences을 사용하면 데이터 과학을 사용하여 알 수 없는 대상을 실시간으로 개별 성향으로 분류할 수 있습니다.
seo-title: Predictive Audiences FAQ
solution: Audience Manager
title: Audience Manager Predictive Audiences
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '895'
ht-degree: 64%

---


# 예측 대상 FAQ

[!UICONTROL Predictive Audiences]에 대한 FAQ.

 

**언제 [!UICONTROL Predictive Audiences]이 아니라 [!UICONTROL Look-alike modeling]을 사용해야 합니까?**

[!UICONTROL Predictive Audiences]과 [!UICONTROL Look-alike modeling]은 서로 다른 활용 사례를 제공합니다. 두 알고리즘 간의 주요 차이점은 다음과 같습니다.

1. [!UICONTROL Look-alike modeling]에서는 작은 대상을 입력으로 취하여 이 대상을 확장합니다. [!UICONTROL Predictive Audiences]에서는 큰 대상을 입력으로 취하여 성향별로 정의된 더 작은 구별되는 대상으로 나눕니다.
1. 기본 세그먼트 수는 각 알고리즘에 대해 다릅니다. [!UICONTROL Predictive Audiences]에서는 기준선을 두 개 이상 필요로 하는 반면 [!UICONTROL Look-alike modeling]에서는 최대 하나의 기준선을 사용합니다.
1. [!UICONTROL Predictive Audiences]에서는 실시간 세그먼트 평가를 수행하지만 [!UICONTROL Look-alike modeling]에서는 실시간 세그먼트 평가를 수행하지 않습니다.

사용 사례를 기반으로 귀사에 더 적절한 모델을 결정해야 합니다.

다수의 기준선을 사용하는 [!UICONTROL Predictive Audiences] 모델을 구축하는 것은 실시간 평가만 없고 방문자가 하나의 구별되는 성향이 아니라 서로 다른 여러 성향에 속할 가능성이 매우 높은 동일한 수의 유사 모델을 구축하는 것과 동일한 것으로 생각할 수 있습니다.

 

**성향/모델은 몇 개까지 만드는 것이 허용됩니까?**

최대 10개의 [!UICONTROL Predictive Audiences] 모델을 만들 수 있습니다. 각 모델에 대해 최대 50개의 기준선 트레이트 또는 세그먼트를 정의할 수 있습니다.

 

**[!UICONTROL Predictive Audiences] 세그먼트에서 새 세그먼트를 만들려면 어떻게 해야 합니까?**

**[!UICONTROL Audience Data]** > **[!UICONTROL Segments]**&#x200B;로 이동하고 **[!UICONTROL Predictive Audiences]** 폴더를 클릭합니다. 원하는 세그먼트를 찾아 복제한 다음 필요에 따라 편집하십시오.

 

**내 모델에서 나온 첫 번째 결과는 언제 볼 수 있습니까?**

[!UICONTROL Predictive Audiences] 모델이 성공적으로 실행되는 경우 모델 생성 후 24시간 내에 이 모델의 결과를 사용할 수 있습니다.

모델이 24시간 내에 결과를 내지 못하는 경우에는 Adobe 담당자에게 문의하십시오.

 

**내 모델이 결과를 내놓거나 경고 상태를 표시하지 않는 이유는 무엇입니까?**

[!UICONTROL Predictive Audiences] 모델이 다수의 이유로 인해 결과를 내놓지 못할 수 있습니다.

1. 선택한 페르소나 [!UICONTROL traits] / [!UICONTROL segments]에 사용자 프로필이 충분하지 않습니다. 각 가상 사용자의 사용자 프로필이 최소 수백 명 이상 포함되도록 [!UICONTROL traits] 또는 [!UICONTROL segments]을 선택하는 것이 좋습니다.
1. 선택한 페르소나 [!UICONTROL traits]/ [!UICONTROL segments]에 사용자 프로필에 충분한 데이터가 없습니다(분석할 만한 트레이트가 충분하지 않음).
1. 대상 대상 특성/세그먼트에 활성 또는 온보드 사용자가 없습니다.
1. 지난 30일 내에 활성 상태이거나 온보딩된 타겟 대상 사용자의 사용자 프로필에 충분한 데이터가 없습니다(분석하기에 충분한 트레이트가 아님).
1. 대상 대상 세그먼트는 모델에 대해 선택한 세그먼트의 다른 [!UICONTROL Profile Merge Rule]을 사용합니다.
1. 대상 대상 트레이트의 데이터 소스는 모델에 대해 선택한 [!UICONTROL Profile Merge Rule]에 포함되지 않을 수 있습니다.

최적의 결과를 얻으려면 [성향 선택 기준](../features/algorithmic-models/predictive-audiences.md#selection-personas) 및 [타겟 대상 선택 기준](../features/algorithmic-models/predictive-audiences.md#selection-audience)의 제안된 지침을 따르십시오.

 

**모델이  [!UICONTROL Error] 상태를 표시하는 이유는 무엇입니까?**

모델을 실행하지 못했습니다. 이러한 경우 [!DNL Adobe] 담당자에게 문의하십시오.

 

**어떻게  [!UICONTROL Profile Merge Rule] 바꿔 드릴까요 [!UICONTROL Predictive Audiences] [!UICONTROL segment]?**

이전 모델과 동일한 개인 및 대상 대상을 선택하여 새 모델을 만듭니다. 모델을 만드는 동안 다른 [!UICONTROL Profile Merge Rule]을 지정합니다.

>[!WARNING]
> 또는 [세그먼트 빌더](../features/segments/segment-builder.md)를 사용하여 기존 예측 [!UICONTROL trait]과 함께 [!UICONTROL segment]를 수동으로 만들고 원하는 [!UICONTROL Profile Merge Rule]에 할당할 수 있습니다.
> 
> 그러나 예측 [!UICONTROL traits]은(는) 자신들이 속한 모델의 [!UICONTROL Profile Merge Rule]을 자동으로 상속하고 해당 모델의 [!UICONTROL Profile Merge Rule]을 준수하는 영향력 있는 [!UICONTROL traits]에서 구축되므로 이러한 방법을 권장하지 않습니다.

 

**무엇을  [!UICONTROL Profile Merge Rule] 선택해야 합니까?**

모델의 [!UICONTROL Profile Merge Rule]을 선택할 때 사용 사례를 면밀히 분석하십시오.

대상 대상 [!UICONTROL segment]이(가) 인증된 프로필 + [!DNL Device Graph] 프로필을 기반으로 [!UICONTROL Profile Merge Rule]을(를) 사용하고 예측 [!UICONTROL segments]에 대해 동일한 [!UICONTROL Profile Merge Rule]을(를) 선택한다고 가정해 보겠습니다. 이 경우, 장치 수준 및 장치 간 수준 [!UICONTROL traits]은 모두 모델을 교육하는 데 사용되고 사용자 배치는 예측 [!UICONTROL segment]에 사용됩니다.

그러나 장치 프로파일만을 기준으로 [!UICONTROL Profile Merge Rule]을 선택하면 크로스 디바이스 [!UICONTROL traits]에 영향을 주지 않으며 사용자가 예측 [!UICONTROL segment]에 배치되는 데 영향을 주지 않습니다. 이로 인해 모델 정확도와 도달 수가 저하될 수 있습니다.

사용 사례를 주의 깊게 분석하고 모델이 학습할 유형 및 분류에 사용할 데이터 유형을 결정합니다.[!UICONTROL trait]

**어떤 성향 트레이트/세그먼트에도 속하지 않는 타겟 대상의 사용자를 분류할 수 있습니까?**

예, 사용자의 프로필에 어떤 트레이트도 포함되어 있지 않은 경우 분류할 수 있습니다. 이 경우, 사용자는 모든 성향 트레이트/세그먼트에 대해 일치 점수 0을 받게 되며, 따라서 예측 세그먼트로 분류되지 않습니다.

 

**예측 세그먼트 중 하나로 분류된 사용자가 다른 [!UICONTROL Predictive Audiences] 세그먼트로 재분류될 수 있습니까?**

예. 알고리즘은 매일 훈련되므로 트레이트 점수 측면에서 각 성향에 대한 변경 사항을 적용합니다. [!UICONTROL Predictive Audiences] 세그먼트에 속하는 사용자가 활성 상태인 경우, 트레이트 점수가 변경되면 지난 30일 활동을 기반으로 분류가 변경될 수 있습니다.

 

**대상 분류가 수행되는 기준 트레이트를 볼 수 있습니까?**

예, 모델 보고 페이지에서 모든 기준선에 대해 영향을 주는 모든 트레이트를 볼 수 있습니다. [영향력 있는 트레이트](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits)를 참조하십시오.

 

**기준선 트레이트 또는 세그먼트 중 하나를 편집하면 모델은 어떻게 됩니까?**

모델은 하루에 한 번 트레이트나 세그먼트를 평가합니다. 업데이트 다음 날에 업데이트된 분류가 표시됩니다.

 

**모델이 학습할 데이터 소스를 선택할 수 있습니까?**

아니요, 데이터 소스 선택은 지원되지 않습니다. [!UICONTROL Predictive Audiences] 알고리즘은 모든 자사 트레이트로부터 학습합니다.