---
description: Predictive Audiences을 사용하면 데이터 과학을 사용하여 알 수 없는 대상을 실시간으로 개별 성향으로 분류할 수 있습니다.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences Overview
solution: Audience Manager
title: Audience Manager Predictive Audiences
feature: Algorithmic Models
exl-id: 57eaeb09-0e0e-4ce9-9b25-f1a27f4f35ce
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1470'
ht-degree: 3%

---

# [!UICONTROL Predictive Audiences] 개요 {#predictive-audiences}

[!UICONTROL Predictive Audiences]을(를) 사용하면 알 수 없는 대상을 고급 데이터 과학 기술을 사용하여 실시간으로 개별 성향으로 분류할 수 있습니다.

>[!IMPORTANT]
>이 문서에는 이 기능의 설정 및 사용 방법을 안내하는 제품 설명서가 포함되어 있습니다. 여기에는 법률적인 조언이 들어 있지 않습니다. 법률 지도가 필요한 경우 법률 자문을 구하십시오.

마케팅 컨텍스트에서 성향은 인구 통계, 탐색 습관, 쇼핑 내역 등과 같은 특정 트레이트 집합을 공유하는 방문자, 사용자 또는 잠재적 구매자로 정의되는 대상 세그먼트입니다.

[!UICONTROL Predictive Audiences] 모델은 Audience Manager의 기계 학습 기능을 사용하여 알 수 없는 대상을 개별 성향으로 분류할 수 있도록 함으로써 이러한 개념을 한 단계 더 발전시킵니다. Audience Manager을 사용하면 일단의 알려진 자사 고객에 대해 알 수 없는 자사 대상의 성향을 계산하여 이를 달성할 수 있습니다.

[!UICONTROL Predictive Audiences] 모델을 만들 때 첫 번째 단계는 대상 대상자를 분류할 기준 특성 또는 세그먼트를 선택하는 것입니다. 이러한 트레이트 또는 세그먼트는 성향을 정의합니다.

평가 단계 동안 모델은 기준선으로 정의한 각 트레이트 또는 세그먼트에 대해 새 [!UICONTROL Predictive Audiences] 세그먼트를 만듭니다. 다음에 Audience Manager이 어떤 성향에 대해 분류되지 않은(기준 트레이트 또는 세그먼트에 적합하지 않은) 대상 대상의 방문자를 보게 되면, [!UICONTROL Predictive Audiences] 모델은 방문자가 속해야 하는 예측 세그먼트 중 하나를 결정하고 해당 세그먼트에 방문자를 추가합니다.

[!UICONTROL Segments] 페이지에서 모델이 만든 예측 세그먼트를 식별할 수 있습니다. 각 [!UICONTROL Predictive Audiences] 모델의 폴더는 [!UICONTROL Predictive Audiences] 폴더 아래에 있으며 모델 폴더를 클릭하면 각 모델의 세그먼트를 볼 수 있습니다.

![predictive-audiences-segments](assets/predictive-audiences-segments.png)

## 사용 사례 {#use-cases}

[!UICONTROL Predictive Audiences]을(를) 사용하는 방법과 시기를 더 잘 이해할 수 있도록 Audience Manager 고객이 이 기능을 사용하여 해결할 수 있는 몇 가지 사용 사례를 소개합니다.

### 사용 사례 #1

전자 상거래 회사의 마케터로서 사용자 경험을 개인화할 수 있도록 모든 웹 및 모바일 방문자를 다양한 브랜드 선호도 범주로 분류하고 싶습니다.

### 사용 사례 #2

미디어 회사의 마케터로서 인증되지 않은 웹 및 모바일 방문자를 즐겨 찾는 장르로 분류하여 모든 채널에서 개인화된 콘텐츠를 제안할 수 있도록 하려고 합니다.

### 사용 사례 #3

저는 항공사의 광고주로서, 여행지에 대한 관심도에 따라 고객들을 분류하여 짧은 리타겟팅 기간 내에서 실시간으로 광고할 수 있게 하고 싶습니다.

### 사용 사례 #4

광고주로서, 저는 실시간으로 자사 대상자를 분류하여 트렌드 뉴스에 신속하게 대응할 수 있도록 하고 싶습니다.

### 사용 사례 #5

마케터는 웹 사이트 방문자가 검색, 참여, 구매 또는 유지와 같은 어떤 고객 여정 단계에 있는지 예측하여 그에 따라 타깃팅할 수 있도록 하고 싶습니다.

### 사용 사례 #6

미디어 회사로서 대상을 분류하여 방문자에게 관련 광고를 제공하면서 프리미엄 가격으로 광고 공간을 판매할 수 있도록 하고 싶습니다.

## [!UICONTROL Predictive Audiences] 모델 작동 방식 {#how-predictive-audiences-models-work}

[!UICONTROL Predictive Audiences] 모델을 만들 때 다음 세 단계를 수행합니다.

1. 먼저 담당자를 정의할 트레이트 또는 세그먼트를 최소 2개 선택합니다.
1. 그런 다음 분류할 타겟 대상을 정의하는 트레이트 또는 세그먼트를 선택합니다.
1. 마지막으로 모델 이름, 예측 세그먼트를 저장할 데이터 원본 및 모델에 대한 [!UICONTROL Profile Merge Rule]을(를) 선택합니다.

### 성향 선택 기준 {#selection-personas}

자사 트레이트 또는 세그먼트를 선택하여 가상 사용자를 정의할 수 있습니다. 그러나 최적의 결과를 얻으려면 다음과 같은 권장 모범 사례 세트가 있습니다.

* 각 성향에 최소 수백 개의 [장치 ID](../../reference/ids-in-aam.md)가 포함되도록 성향 트레이트 또는 세그먼트를 선택하십시오.
* 트레이트가 [장치 간 ID](../../reference/ids-in-aam.md)를 기반으로 하는 경우 [!UICONTROL Device Graph]과 같이 [장치 ID](../../reference/ids-in-aam.md)를 사용하는 [프로필 병합 규칙](../profile-merge-rules/merge-rules-overview.md)을 사용하여 세그먼트로 래핑할 수 있습니다. 이렇게 하면 알고리즘에서 학습할 수 있는 [장치 ID](../../reference/ids-in-aam.md)이(가) 충분히 있습니다.
* 성향에 대해 1~3개의 트레이트로 구성된 트레이트 또는 단순 세그먼트를 선택하는 것이 좋습니다.
* 겹치는 부분이 최소인 기준선 트레이트 또는 세그먼트를 선택하십시오.
* 디지털 속성에서 세분화된 트레이트를 캡처하고 있는지 확인합니다.

### 타겟 대상에 대한 선택 기준 {#selection-audience}

사용 사례에 따라 실시간, 일괄 처리 중 어느 방법으로 사용자를 분류할지 또는 두 가지 모두로 분류할지, 중요한 실시간 및/또는 총 모집단을 가진 대상([!UICONTROL trait] 또는 [!UICONTROL segment])을 선택하십시오. 사용자 선택과 유사하게 대상 대상자 [!UICONTROL trait] 또는 [!UICONTROL segment]에게 풍부한 프로필([!UICONTROL traits]의 풍부한 집합)을 가진 사용자가 있는 것이 좋습니다.

대상 대상을 선택할 때 사용 사례를 분석하고 분류할 ID 유형([!UICONTROL device IDs] 또는 [!UICONTROL cross-device IDs])을 결정하십시오. 모델을 만들 때 선택하는 [!UICONTROL Profile Merge Rule]은(는) 각 사용자를 예측 [!UICONTROL segments]에 배치하는 데 사용할 데이터를 정의합니다.

가장 좋은 방법은 타겟 대상 [!UICONTROL Profile Merge Rule]과(와) 구성이 동일한 [!UICONTROL Profile Merge Rule]을(를) 선택하거나 타겟 대상의 프로필 유형(장치 프로필 또는 인증된 프로필)을 포함하는 것을 선택하는 것입니다.

### [!UICONTROL Predictive Audiences] 모델 교육 단계 {#model-training}

알고리즘이 자사 대상자를 적합한 개인으로 분류하려면 먼저 데이터에 대해 자신을 교육해야 합니다.

정의한 각 담당자에 대해 알고리즘은 각각의 대상자를 분석하고 지난 30일 동안 사용자에 대한 실시간 및/또는 온보딩된 트레이트 활동을 평가합니다.
이 단계는 자사 대상의 변경 사항을 고려하여 24시간마다 한 번씩 수행됩니다.

### [!UICONTROL Predictive Audiences] 모델 분류 단계 {#model-classification}

실시간 및 배치 대상 분류의 경우 모델은 먼저 사용자가 타겟 대상에 속하는지 여부를 확인합니다. 사용자가 타겟 대상 자격을 충족하고 어떤 성향에도 속하지 않는 경우 모델은 사용자에게 성향 자격 점수를 지정합니다.

자사 대상을 평가하고 점수를 할당하는 동안 모델은 계정에 정의된 기본 **[!UICONTROL Profile Merge Rule]**&#x200B;을(를) 사용합니다. 마지막으로 방문자는 가장 높은 점수를 받은 담당자로 분류됩니다.

![predictive-audiences-graph](assets/predictive-audiences-graph.png)

## 고려 사항 및 제한 사항 {#considerations}

>[!IMPORTANT]
> 구현 단계로 이동하기 전에 이 섹션을 주의 깊게 읽으십시오.

[!UICONTROL Predictive Audiences] 모델을 구성할 때는 다음 고려 사항과 제한 사항에 유의하십시오.

* 최대 10개의 [!UICONTROL Predictive Audiences] 모델을 만들 수 있습니다.
* 각 모델에 대해 최대 50개의 기본 트레이트/세그먼트를 선택할 수 있습니다.
* 현재 [!UICONTROL Predictive Audiences]에서 제2자 데이터와 타사 데이터를 지원하지 않습니다.
* [!UICONTROL Predictive Audiences]은(는) 모든 자사 데이터 소스의 자사 트레이트에 따라 대상 분류를 수행합니다.
* [!UICONTROL Predictive Audiences]에 대한 세그먼트 평가에서는 모델을 만드는 동안 선택한 **[!UICONTROL Profile Merge Rule]**&#x200B;을(를) 사용합니다. [!UICONTROL Profile Merge Rules]에 대한 자세한 내용은 전용 [설명서](../profile-merge-rules/merge-rules-overview.md)를 참조하세요.
* 일부 트레이트 및 세그먼트는 기준선 또는 타겟 대상자로 지원되지 않습니다. 다음 중 하나를 기준 요소 또는 대상 대상으로 선택하면 [!UICONTROL Predictive Audiences] 모델이 저장되지 않습니다.
   * 예측 트레이트로 생성된 예측 트레이트 및 세그먼트
   * [Adobe Experience Platform](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) 트레이트 또는 세그먼트;
   * 알고리즘 트레이트
   * 제2자 및 타사 트레이트.
* [!UICONTROL Audience Lab]에서 [!UICONTROL Predictive Audience] [!UICONTROL segments]을(를) 사용할 수 없습니다.

## [!UICONTROL Data Export Controls] {#dec}

[!UICONTROL Predictive Audiences] 모델에서 만든 예측 세그먼트는 다음 자사 데이터 원본에서 [데이터 내보내기 제어](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html)를 상속합니다.

1. 모델을 작성할 때 선택하는 자사 데이터 소스.
1. 타겟 대상의 자사 데이터 소스입니다. 특히 타겟 대상을 구성하는 [!UICONTROL traits] 또는 [!UICONTROL segments]의 데이터 내보내기 제어
1. 모델에 대해 선택한 [!UICONTROL Profile Merge Rule]의 [데이터 내보내기 제어](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html)입니다.

새로 만든 예측 [!UICONTROL traits] 및 [!UICONTROL segments]은(는) 위에서 설명한 자사 데이터 원본의 통합과 동일한 개인 정보 보호 제한 사항을 갖습니다.

[!UICONTROL Predictive Audiences] 세그먼트 개인 정보 보호 제한에 속하지 않는 추가 제한이 있는 트레이트는 교육 단계에서 제외되며, 모델에 영향을 주지 않습니다.

## [!UICONTROL Profile Merge Rules] {#pmr}

모델을 만들 때 선택한 [!UICONTROL Profile Merge Rule]에 모든 예측 세그먼트가 할당됩니다. 선택한 [!UICONTROL Profile Merge Rule]은(는) 다음과 같은 이유로 중요합니다.

* 모델이 사용자를 예측 [!UICONTROL segment] (으)로 분류할 때 영향력 있는 [!UICONTROL traits]을(를) 분석할 때 고려해야 하는 장치 및/또는 인증된 프로필을 정의합니다.
* 모델 교육 단계에서 사용해야 하는 [!UICONTROL trait] 유형(장치 수준 또는 교차 장치 수준)을 제어하며 [!UICONTROL traits]에 영향을 줍니다. 예측 [!UICONTROL segments]은(는) 대상 대상의 하위 집합입니다.
   * 대상 대상이 세그먼트인 경우 모델에 대해 대상 대상에 할당된 모델과 동일한 [!UICONTROL Profile Merge Rule]을(를) 선택하거나 대상 대상의 프로필 유형을 포함하는 [!UICONTROL Profile Merge Rule]을(를) 선택하는 것이 좋습니다.
   * 대상 대상이 [!UICONTROL trait]인 경우 대상 대상 트레이트와 동일한 유형의 데이터(장치 프로필 데이터 또는 교차 장치 프로필 데이터)에 액세스할 수 있는 [!UICONTROL Profile Merge Rule]을(를) 선택하는 것이 좋습니다.
* [!UICONTROL Current Authenticated Profiles] 및 [!UICONTROL No Device Profile] 옵션을 사용하는 [!UICONTROL Profile Merge Rules]은(는) 실시간 대상 분류에 대해서만 지원됩니다. 자세한 내용은 [정의된 프로필 병합 규칙 옵션](../profile-merge-rules/merge-rule-definitions.md)을 참조하세요.

장치 데이터와 교차 장치 데이터를 모두 사용하는 [!UICONTROL Profile Merge Rule]을(를) 선택하면 모델 교육 및 사용자 분류에 사용할 수 있는 [!UICONTROL traits]의 수를 예측 [!UICONTROL segments]로 최대화합니다.

## [!UICONTROL Role-Based Access Controls] {#rbac}

성향 및 대상 분류에 대해 선택하는 트레이트 및 세그먼트는 Audience Manager [역할 기반 액세스 제어](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html)의 적용을 받습니다.

Audience Manager 사용자는 [볼 수 있는 권한](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions)이 있는 가상 사용자 및 대상 대상에 대한 트레이트 또는 세그먼트만 선택할 수 있습니다.
