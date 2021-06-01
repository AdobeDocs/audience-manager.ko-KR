---
description: Predictive Audiences을 사용하면 데이터 과학을 사용하여 알 수 없는 대상을 실시간으로 개별 성향으로 분류할 수 있습니다.
seo-description: Predictive Audiences을 사용하면 데이터 과학을 사용하여 알 수 없는 대상을 실시간으로 개별 성향으로 분류할 수 있습니다.
seo-title: Predictive Audiences 개요
solution: Audience Manager
title: Audience Manager Predictive Audiences
feature: 알고리즘 모델
exl-id: 57eaeb09-0e0e-4ce9-9b25-f1a27f4f35ce
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1513'
ht-degree: 8%

---

# [!UICONTROL Predictive Audiences] 개요 {#predictive-audiences}

[!UICONTROL Predictive Audiences] 은 알 수 없는 대상을 고급 데이터 과학 기술을 사용하여 실시간으로 개별 성향으로 분류하는 데 도움이 됩니다.

>[!IMPORTANT]
>이 문서에는 이 기능의 설정 및 사용을 안내하는 제품 설명서가 포함되어 있습니다. 여기에 포함된 어떤 것도 법률적인 조언이 아닙니다. 법률 자문을 구하시려면 법률 자문을 구하십시오.

마케팅 컨텍스트에서 성향은 인구 통계, 탐색 습관, 쇼핑 이력 등과 같은 특정 트레이트 집합을 공유하는 방문자, 사용자 또는 잠재적 구매자로 정의되는 대상 세그먼트로입니다.

[!UICONTROL Predictive Audiences] 모델은 Audience Manager의 기계 학습 기능을 사용하여 알 수 없는 대상을 개별 성향으로 분류할 수 있도록 함으로써 이러한 개념을 한 단계 더 발전시킵니다. Audience Manager를 사용하면 일단의 알려진 자사 고객에 대해 알 수 없는 자사 대상의 성향을 계산하여 이를 달성할 수 있습니다.

[!UICONTROL Predictive Audiences] 모델을 만들 때, 첫 번째 단계는 대상 대상을 분류할 기준 트레이트 또는 세그먼트를 선택하는 것입니다. 이러한 트레이트나 세그먼트는 개인성을 정의합니다.

평가 단계 동안 모델은 베이스라인으로 정의한 각 트레이트 또는 세그먼트에 대해 새 [!UICONTROL Predictive Audiences] 세그먼트를 만듭니다. 다음 번에 Audience Manager이 성향으로 분류되지 않는(기준 트레이트 또는 세그먼트에 대한 자격이 없는) 타겟 대상의 방문자를 보게 되면 [!UICONTROL Predictive Audiences] 모델은 방문자가 속해야 하는 예측 세그먼트 중 하나를 결정하고 해당 세그먼트에 방문자를 추가합니다.

[!UICONTROL Segments] 페이지에서 모델이 생성한 예측 세그먼트를 식별할 수 있습니다. 각 [!UICONTROL Predictive Audiences] 모델에는 [!UICONTROL Predictive Audiences] 폴더 아래에 고유한 폴더가 있으며 모델 폴더를 클릭하여 각 모델의 세그먼트를 볼 수 있습니다.

![predictive-audiences-segments](assets/predictive-audiences-segments.png)

## 사용 사례 {#use-cases}

[!UICONTROL Predictive Audiences] 사용 방법과 시기를 더 잘 이해할 수 있도록 Audience Manager 고객이 이 기능을 사용하여 해결할 수 있는 몇 가지 사용 사례가 있습니다.

### 사용 사례 #1

전자 상거래 회사의 마케터는 모든 웹 및 모바일 방문자를 다양한 브랜드 친화성 카테고리로 분류하여 자신의 사용자 경험을 개인화할 수 있도록 하려고 합니다.

### 사용 사례 #2

미디어 회사의 마케터로서, 인증되지 않은 웹 및 모바일 방문자를 즐겨찾는 장르 별로 분류하려고 하므로 모든 채널에서 개인화된 콘텐츠를 제공할 수 있습니다.

### 사용 사례 #3

항공사 광고주로서, 짧은 재타겟팅 기간 내에 실시간으로 그들에게 광고할 수 있도록 여행 대상의 관심사에 따라 대상을 분류하고 싶습니다.

### 사용 사례 #4

광고주로서 자사 대상을 실시간으로 분류하여 최신 트렌드 뉴스에 빠르게 대응할 수 있도록 하려고 합니다.

### 사용 사례 #5

마케터는 검색, 참여, 구매 또는 보존과 같이 웹 사이트 방문자가 있는 고객 여정 단계를 예측하여 그에 따라 타깃팅할 수 있도록 하려고 합니다.

### 사용 사례 #6

미디어 회사로서, 대상을 분류하고 싶습니다. 그래야 방문자에게 적절한 광고를 제공하는 동시에 프리미엄 가격으로 광고 공간을 판매할 수 있습니다.

## [!UICONTROL Predictive Audiences] 모델이 작동하는 방법 {#how-predictive-audiences-models-work}

[!UICONTROL Predictive Audiences] 모델을 만들 때 다음 세 단계를 수행합니다.

1. 먼저 개인화를 정의할 최소 2개의 트레이트 또는 2개의 세그먼트를 선택합니다.
1. 그런 다음 분류할 대상 대상을 정의하는 트레이트 또는 세그먼트를 선택합니다.
1. 마지막으로, 모델의 이름, 예측 세그먼트를 저장할 데이터 소스 및 모델의 [!UICONTROL Profile Merge Rule] 을 선택합니다.

### 가상 사용자 {#selection-personas} 선택 기준

자사 트레이트나 세그먼트를 선택하여 개인화를 정의할 수 있습니다. 그러나 최적의 결과를 얻으려면 권장되는 우수 사례 세트가 있습니다.

* 각 성향에 최소 수백 개의 [장치 ID](../../reference/ids-in-aam.md)가 포함되도록 성향 트레이트 또는 세그먼트를 선택하십시오.
* 트레이트가 [교차 장치 ID](../../reference/ids-in-aam.md)를 기반으로 하는 경우 [장치 ID](../../reference/ids-in-aam.md)를 사용하는 [프로필 병합 규칙](../profile-merge-rules/merge-rules-overview.md)을 사용하여 세그먼트에 래핑할 수 있습니다(예: [!UICONTROL Device Graph]). 이렇게 하면 알고리즘에서 학습할 수 있는 충분한 [장치 ID](../../reference/ids-in-aam.md)가 있습니다.
* 1~3개의 트레이트로 구성된 특성에 대해 트레이트나 단순 세그먼트를 선택하는 것이 좋습니다.
* 겹치지 않는 기준선 트레이트 또는 세그먼트를 선택합니다.
* 디지털 속성에서 세부적으로 트레이트를 캡처하는지 확인합니다.

### Target 대상 {#selection-audience} 선택 기준

사용 사례에 따라 사용자를 실시간으로, 일괄적으로 또는 둘 다 분류할지 여부에 따라 상당한 실시간 및/또는 총 모집단이 있는 대상([!UICONTROL trait] 또는 [!UICONTROL segment])을 선택하십시오. 성향 선택 사항과 유사하게, 타겟 대상 [!UICONTROL trait] 또는 [!UICONTROL segment]에 풍부한 프로필(풍부한 [!UICONTROL traits] 세트)이 있는 사용자가 있는 것이 좋습니다.

타겟 대상을 선택할 때 사용 사례를 분석하고 분류할 ID 유형을 결정합니다.[!UICONTROL device IDs] 또는 [!UICONTROL cross-device IDs] 모델을 만들 때 선택하는 [!UICONTROL Profile Merge Rule] 은 각 사용자를 예측 [!UICONTROL segments]에 배치하는 데 사용할 데이터를 정의합니다.

타겟 대상 [!UICONTROL Profile Merge Rule]과 동일한 구성을 가지는 [!UICONTROL Profile Merge Rule] 또는 타겟 대상의 프로필 유형(장치 프로필 또는 인증된 프로필)을 포함하는 것을 선택하는 것이 좋습니다.

### [!UICONTROL Predictive Audiences] 모델 교육 단계  {#model-training}

알고리즘에서 자사 대상을 적합한 개인으로 분류하려면 먼저 데이터에 대한 자체 교육을 수행해야 합니다.

정의한 각 성향에 대해 알고리즘은 해당 대상을 분석하고 지난 30일 동안 해당 사용자에 대한 실시간 및/또는 온보딩된 트레이트 활동을 평가합니다.
이 단계는 자사 대상의 변경 사항을 설명하기 위해 24시간마다 한 번 수행됩니다.

### [!UICONTROL Predictive Audiences] 모델 분류 단계  {#model-classification}

실시간 및 배치 대상 분류의 경우 모델은 먼저 사용자가 타겟 대상에 속하는지 여부를 확인합니다. 사용자가 target 대상 자격을 확보하고 가상 사용자가 아닌 경우, 모델은 사용자에게 성향 자격 점수를 지정합니다.

자사 대상을 평가하고 점수를 할당하는 동안 모델은 계정에 정의된 기본 **[!UICONTROL Profile Merge Rule]** 을 사용합니다. 마지막으로 방문자는 가장 높은 점수를 받은 성향으로 분류됩니다.

![predictive-audiences-graph](assets/predictive-audiences-graph.png)

## 고려 사항 및 제한 사항 {#considerations}

>[!IMPORTANT]
> 구현 단계로 이동하기 전에 이 섹션을 자세히 살펴보십시오.

[!UICONTROL Predictive Audiences] 모델을 구성할 때는 다음 고려 사항과 제한 사항을 기억하십시오.

* 최대 10개의 [!UICONTROL Predictive Audiences] 모델을 만들 수 있습니다.
* 각 모델에 대해 최대 50개의 기본 트레이트/세그먼트를 선택할 수 있습니다.
* 두 번째 및 타사 데이터는 현재 [!UICONTROL Predictive Audiences]에서 지원되지 않습니다.
* [!UICONTROL Predictive Audiences] 모든 자사 데이터 소스에서 자사 트레이트에 따라 대상 분류를 수행합니다.
* [!UICONTROL Predictive Audiences]에 대한 세그먼트 평가는 모델을 생성하는 동안 선택하는 **[!UICONTROL Profile Merge Rule]**&#x200B;을 사용합니다. [!UICONTROL Profile Merge Rules]에 대해 자세히 알아보려면 전용 [설명서](../profile-merge-rules/merge-rules-overview.md)를 참조하십시오.
* 일부 트레이트 및 세그먼트는 기준선 또는 타겟 대상으로 지원되지 않습니다. [!UICONTROL Predictive Audiences] 다음 중 하나를 기준 요소 또는 대상 대상으로 선택할 때 모델이 저장되지 않습니다.
   * 예측 트레이트로 생성된 예측 트레이트 및 세그먼트
   * [Adobe Experience ](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) Platform 트레이트 또는 세그먼트
   * 알고리즘 트레이트;
   * 제2자 트레이트 및 타사 트레이트.
* [!UICONTROL Predictive Audience] [!UICONTROL segments] 에서는 사용할 수 없습니다  [!UICONTROL Audience Lab].

## [!UICONTROL Data Export Controls] {#dec}

[!UICONTROL Predictive Audiences] 모델에서 만든 예측 세그먼트는 다음 자사 데이터 소스에서 [데이터 내보내기 컨트롤](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html)을 상속합니다.

1. 모델을 작성할 때 선택하는 자사 데이터 소스입니다.
1. 타겟 대상의 자사 데이터 소스. 특히 대상 대상을 구성하는 [!UICONTROL traits] 또는 [!UICONTROL segments]의 데이터 내보내기 제어.
1. 모델에 대해 선택한 [!UICONTROL Profile Merge Rule]의 [데이터 내보내기 컨트롤](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html)

새로 만든 예측 [!UICONTROL traits] 및 [!UICONTROL segments]에는 위에 설명된 자사 데이터 소스의 결합과 동일한 개인 정보 보호 제한이 있습니다.

[!UICONTROL Predictive Audiences] 세그먼트 개인 정보 보호 제한에 속하지 않는 추가 제한 사항이 있는 트레이트는 교육 단계에서 제외되며 모델에 영향을 주지 않습니다.

## [!UICONTROL Profile Merge Rules] {#pmr}

모든 예측 세그먼트에는 모델을 만들 때 선택한 [!UICONTROL Profile Merge Rule]이 할당됩니다. 선택하는 [!UICONTROL Profile Merge Rule]은 다음과 같은 이유로 중요합니다.

* 사용자를 예측 [!UICONTROL segment]으로 분류할 때 모델이 영향력 있는 [!UICONTROL traits]을 분석할 때 고려할 장치 및/또는 인증된 프로필을 정의합니다.
* 모델 교육 단계에서 사용해야 하는 [!UICONTROL trait] 유형(장치 수준 또는 교차 장치 수준)이 제어되며 [!UICONTROL traits] 영향으로 표시됩니다. 예측 [!UICONTROL segments]은(는) 타겟 대상의 하위 세트입니다.
   * 타겟 대상이 세그먼트인 경우 타겟 대상에 지정된 모델과 동일한 [!UICONTROL Profile Merge Rule] 또는 타겟 대상의 프로필 유형을 포함하는 [!UICONTROL Profile Merge Rule] 을 선택하는 것이 좋습니다.
   * 타겟 대상이 [!UICONTROL trait]인 경우 타겟 대상 트레이트(장치 프로필 데이터 또는 교차 장치 프로필 데이터)와 동일한 유형의 데이터에 액세스할 수 있는 [!UICONTROL Profile Merge Rule]을 선택하는 것이 좋습니다.
* [!UICONTROL Profile Merge Rules]  [!UICONTROL Current Authenticated Profiles] 및  [!UICONTROL No Device Profile] 옵션을 사용하는 것은 실시간 대상 분류에만 지원됩니다. 자세한 내용은 정의된 [프로필 병합 규칙 옵션](../profile-merge-rules/merge-rule-definitions.md)을 참조하십시오.

장치 데이터와 교차 장치 데이터를 모두 사용하는 [!UICONTROL Profile Merge Rule] 을 선택하면 모델 교육 및 사용자 분류에 사용할 수 있는 [!UICONTROL traits] 수가 예측 [!UICONTROL segments]에 도달하는 데 최대화됩니다.

## [!UICONTROL Role-Based Access Controls] {#rbac}

개인화 및 대상 분류에 대해 선택하는 트레이트 및 세그먼트는 Audience Manager [역할 기반 액세스 제어](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html)에 따릅니다.

Audience Manager 사용자는 [보기 권한이 있는 개인 및 target 대상에 대해서만 트레이트 또는 세그먼트를 선택할 수 있습니다.](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions)
