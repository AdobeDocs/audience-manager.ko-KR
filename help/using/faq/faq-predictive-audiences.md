---
description: Predictive Audiences을 사용하면 데이터 과학을 사용하여 알 수 없는 대상을 실시간으로 개별 성향으로 분류할 수 있습니다.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences FAQ
solution: Audience Manager
title: Predictive Audiences FAQ
feature: Algorithmic Models
exl-id: 21073970-8457-470b-89fc-724a118a18d2
source-git-commit: 03f039a1317576c7979a5cb4c3cffc543e3bd656
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 59%

---

# Predictive Audiences FAQ

[!UICONTROL Predictive Audiences]에 대한 FAQ.

 

**언제 [!UICONTROL Predictive Audiences]이 아니라 [!UICONTROL Look-alike modeling]을 사용해야 합니까?**

[!UICONTROL Predictive Audiences]과 [!UICONTROL Look-alike modeling]은 서로 다른 활용 사례를 제공합니다. 두 알고리즘 간의 주요 차이점은 다음과 같습니다.

1. [!UICONTROL Look-alike modeling]에서는 작은 대상자를 입력으로 취하여 이 대상자를 확장합니다. [!UICONTROL Predictive Audiences]에서는 큰 대상자를 입력으로 취하여 성향별로 정의된 더 작은 구별되는 대상자로 나눕니다.
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

1. 선택한 사용자 [!UICONTROL traits]/[!UICONTROL segments]의 사용자 프로필이 충분하지 않습니다. 각 성향에 사용자 프로필이 최소 수백 개 이상 포함되도록 [!UICONTROL traits] 또는 [!UICONTROL segments]을(를) 선택하는 것이 좋습니다.
1. 선택한 성향 [!UICONTROL traits]/[!UICONTROL segments]의 사용자 프로필에 충분한 데이터가 없습니다(분석하기에 충분한 트레이트가 아님).
1. 대상 대상 트레이트/세그먼트에 활성 상태이거나 온보딩된 사용자가 없습니다.
1. 지난 30일 내에 활성 상태이거나 온보딩된 타깃 대상자 사용자의 사용자 프로필에 충분한 데이터가 없습니다(분석하기에 충분한 트레이트가 아님).
1. 대상 대상 세그먼트는 모델에 대해 선택한 세그먼트와 다른 [!UICONTROL Profile Merge Rule]을(를) 사용합니다.
1. 대상 대상의 데이터 원본이 모델에 대해 선택한 [!UICONTROL Profile Merge Rule]에 포함되지 않을 수 있습니다.

최적의 결과를 얻으려면 [성향 선택 기준](../features/algorithmic-models/predictive-audiences.md#selection-personas) 및 [타깃 대상자 선택 기준](../features/algorithmic-models/predictive-audiences.md#selection-audience)의 제안된 지침을 따르십시오.

 

**내 모델이 [!UICONTROL Error] 상태를 표시하는 이유는 무엇입니까?**

모델을 실행하지 못했습니다. 이러한 경우 [!DNL Adobe] 담당자에게 문의하십시오.

 

**[!UICONTROL Profile Merge Rule] [!UICONTROL Predictive Audiences]에 대한 [!UICONTROL segment]을(를) 변경하려면 어떻게 해야 합니까?**

이전 모델과 동일한 가상 사용자 및 타겟 대상을 선택하여 새 모델을 만듭니다. 모델을 만드는 동안 다른 [!UICONTROL Profile Merge Rule]을(를) 할당하십시오.

>[!WARNING]
> 또는 [세그먼트 빌더](../features/segments/segment-builder.md)를 사용하여 기존 예측 [!UICONTROL segment]을(를) 사용하여 [!UICONTROL trait]을(를) 수동으로 만들고 선택한 [!UICONTROL Profile Merge Rule]을(를) 할당할 수 있습니다.
> 
> 그러나 예측 [!UICONTROL traits]은(는) 자신이 속한 모델의 [!UICONTROL Profile Merge Rule]을(를) 자동으로 상속하며 모델의 [!UICONTROL traits]을(를) 준수하는 영향력 있는 [!UICONTROL Profile Merge Rule]에서 빌드되므로 이 방법을 사용하지 않는 것이 좋습니다.

 

**어떤 [!UICONTROL Profile Merge Rule]을(를) 선택해야 합니까?**

모델에 대한 [!UICONTROL Profile Merge Rule]을(를) 선택할 때 사용 사례를 면밀히 분석하십시오.

대상 대상 [!UICONTROL segment]이(가) 인증된 프로필 + [!UICONTROL Profile Merge Rule]개 프로필을 기반으로 [!DNL Device Graph]을(를) 사용하고 예측 [!UICONTROL Profile Merge Rule]에 대해 동일한 [!UICONTROL segments]을(를) 선택한다고 가정해 보겠습니다. 이 경우 장치 수준 및 교차 장치 수준 [!UICONTROL traits]이(가) 모두 모델 교육 및 예측 [!UICONTROL segment]에 사용자 배치에 사용됩니다.

그러나 장치 프로필만 기반으로 [!UICONTROL Profile Merge Rule]을(를) 선택하면 교차 장치 [!UICONTROL traits]의 영향력이 없어지고 예측 [!UICONTROL segment]에 사용자를 배치하는 데 기여하지 않습니다. 이는 모델 정확도 및 도달 거리에 악영향을 미칠 수 있다.

사용 사례를 주의 깊게 분석하고 모델을 학습할 [!UICONTROL trait] 유형과 모델이 분류에 사용할 데이터 유형을 결정합니다.

**어떤 성향 트레이트/세그먼트에도 속하지 않는 타깃 대상자의 사용자를 분류할 수 있습니까?**

예, 사용자의 프로필에 어떤 트레이트도 포함되어 있지 않은 경우 분류할 수 있습니다. 이 경우, 사용자는 모든 성향 트레이트/세그먼트에 대해 일치 점수 0을 받게 되며, 따라서 예측 세그먼트로 분류되지 않습니다.

 

**예측 세그먼트 중 하나로 분류된 사용자가 다른 [!UICONTROL Predictive Audiences] 세그먼트로 재분류될 수 있습니까?**

예. 알고리즘은 매일 훈련되므로 트레이트 점수 측면에서 각 성향에 대한 변경 사항을 적용합니다. [!UICONTROL Predictive Audiences] 세그먼트에 속하는 사용자가 활성 상태인 경우, 트레이트 점수가 변경되면 지난 30일 활동을 기반으로 분류가 변경될 수 있습니다.

 

**대상자 분류가 수행되는 기준 트레이트를 볼 수 있습니까?**

예, 모델 보고 페이지에서 모든 기준선에 대해 영향을 주는 모든 트레이트를 볼 수 있습니다. [영향력 있는 트레이트](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits)를 참조하십시오.

 

**예측 특성에 대한 TTL(Time to Live)을 변경할 수 있습니까?**

예측 트레이트 TTL은 0(라이프타임)으로 설정되며 변경할 수 없습니다. [!UICONTROL Predictive Audiences]은(는) 기본 세그먼트에 대한 자격이 있거나 다른 예측 세그먼트로 재분류된 경우에만 예측 세그먼트에서 사용자 세그먼트를 해제할 수 있습니다.

필요한 경우 지정된 TTL로 예측 트레이트와 활동 트레이트를 모두 포함하는 새 세그먼트를 만들어 이 기능을 해결할 수 있습니다.

 


**기준선 트레이트 또는 세그먼트 중 하나를 편집하면 모델은 어떻게 됩니까?**

모델은 하루에 한 번 트레이트나 세그먼트를 평가합니다. 업데이트 다음 날에 업데이트된 분류가 표시됩니다.

 

**모델이 학습할 데이터 소스를 선택할 수 있습니까?**

아니요, 데이터 소스 선택은 지원되지 않습니다. [!UICONTROL Predictive Audiences] 알고리즘은 모든 자사 트레이트로부터 학습합니다.
