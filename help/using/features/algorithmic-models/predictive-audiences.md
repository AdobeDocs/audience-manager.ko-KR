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
source-wordcount: '1485'
ht-degree: 7%

---

# [!UICONTROL Predictive Audiences] 개요 {#predictive-audiences}

[!UICONTROL Predictive Audiences] 을 사용하면 알 수 없는 대상을 고급 데이터 과학 기술을 사용하여 실시간으로 개별 성향으로 분류할 수 있습니다.

>[!IMPORTANT]
>이 문서에는 이 기능의 설정 및 사용 방법을 안내하는 제품 설명서가 포함되어 있습니다. 여기에는 법률적인 조언이 들어 있지 않습니다. 법률 지도가 필요한 경우 법률 자문을 구하십시오.

마케팅 컨텍스트에서 성향은 인구 통계, 탐색 습관, 쇼핑 이력 등과 같은 특정 트레이트 집합을 공유하는 방문자, 사용자 또는 잠재적 구매자로 정의되는 대상 세그먼트로입니다.

[!UICONTROL Predictive Audiences] 모델은 Audience Manager의 기계 학습 기능을 사용하여 알 수 없는 대상을 개별 성향으로 분류할 수 있도록 함으로써 이러한 개념을 한 단계 더 발전시킵니다. Audience Manager를 사용하면 일단의 알려진 자사 고객에 대해 알 수 없는 자사 대상의 성향을 계산하여 이를 달성할 수 있습니다.

다음을 만들 때 [!UICONTROL Predictive Audiences] 모델, 첫 번째 단계는 타겟 대상자를 분류할 기준선 트레이트 또는 세그먼트를 선택하는 것입니다. 이러한 트레이트 또는 세그먼트는 성향을 정의합니다.

평가 단계에서 모델은 새로운 항목을 생성합니다 [!UICONTROL Predictive Audiences] 기준선으로 정의한 각 트레이트 또는 세그먼트에 대한 세그먼트입니다. 다음에 Audience Manager에게 성향에 대해 분류되지 않은(기준선 트레이트 또는 세그먼트에 적합하지 않은) 타겟 대상의 방문자가 표시되면 [!UICONTROL Predictive Audiences] 모델은 방문자가 속해야 하는 예측 세그먼트 중 하나를 결정하고 방문자를 해당 세그먼트에 추가합니다.

모델에서 생성한 예측 세그먼트를 식별할 수 있습니다. [!UICONTROL Segments] 페이지를 가리키도록 업데이트하는 중입니다. 각 [!UICONTROL Predictive Audiences] 모델은 아래에 자체 폴더가 있습니다. [!UICONTROL Predictive Audiences] 폴더를 클릭하면 모델 폴더를 클릭하여 각 모델의 세그먼트를 볼 수 있습니다.

![predictive-audiences-segments](assets/predictive-audiences-segments.png)

## 사용 사례 {#use-cases}

을(를) 사용하는 방법과 시기를 더 잘 이해할 수 있도록 [!UICONTROL Predictive Audiences]는 이 기능을 사용하여 Audience Manager 고객이 해결할 수 있는 몇 가지 사용 사례입니다.

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

## 방법 [!UICONTROL Predictive Audiences] 모델 작업 {#how-predictive-audiences-models-work}

다음을 만들 때 [!UICONTROL Predictive Audiences] 모델은 다음 세 단계를 수행합니다.

1. 먼저 담당자를 정의할 트레이트 또는 세그먼트를 최소 2개 선택합니다.
1. 그런 다음 분류할 타겟 대상을 정의하는 트레이트 또는 세그먼트를 선택합니다.
1. 마지막으로 모델 이름, 예측 세그먼트를 저장할 데이터 소스 및 [!UICONTROL Profile Merge Rule] 모델.

### 성향 선택 기준 {#selection-personas}

자사 트레이트 또는 세그먼트를 선택하여 가상 사용자를 정의할 수 있습니다. 그러나 최적의 결과를 얻으려면 다음과 같은 권장 모범 사례 세트가 있습니다.

* 각 성향에 최소한 수백 개의 성향이 포함되도록 성향 트레이트 또는 세그먼트를 선택하십시오. [장치 ID](../../reference/ids-in-aam.md).
* 트레이트가 다음에 기반을 둔 경우 [교차 장치 ID](../../reference/ids-in-aam.md)를 사용하여 세그먼트에서 래핑할 수 있습니다. [프로필 병합 규칙](../profile-merge-rules/merge-rules-overview.md) that use [장치 ID](../../reference/ids-in-aam.md), 예: [!UICONTROL Device Graph]. 이렇게 하면 충분히 [장치 ID](../../reference/ids-in-aam.md) 알고리즘이 배울 수 있는 부분입니다.
* 성향에 대해 1~3개의 트레이트로 구성된 트레이트 또는 단순 세그먼트를 선택하는 것이 좋습니다.
* 겹치는 부분이 최소인 기준선 트레이트 또는 세그먼트를 선택하십시오.
* 디지털 속성에서 세분화된 트레이트를 캡처하고 있는지 확인합니다.

### Target 대상의 선택 기준 {#selection-audience}

사용 사례에 따라 실시간으로, 일괄 처리로 또는 두 가지 모두로 사용자를 분류할지 여부에 관계없이 타겟 대상([!UICONTROL trait] 또는 [!UICONTROL segment]) 상당한 실시간 및/또는 총 인구가 있습니다. 사용자 선택과 유사하게, 타겟 대상자에게 권장합니다 [!UICONTROL trait] 또는 [!UICONTROL segment] 은(는) 풍부한 프로필을 가진 사용자 있음 (다양한 세트) [!UICONTROL traits]).

타겟 대상을 선택할 때 사용 사례를 분석하고 분류할 ID 유형을 결정합니다. [!UICONTROL device IDs] 또는 [!UICONTROL cross-device IDs]. 다음 [!UICONTROL Profile Merge Rule] 모델을 만들 때 선택하는 것은 각 사용자를 예측으로 배치하는 데 사용할 데이터를 정의합니다 [!UICONTROL segments].

모범 사례로서 다음 중 하나를 선택하는 것이 좋습니다. [!UICONTROL Profile Merge Rule] 타겟 대상자와 동일한 구성을 갖습니다. [!UICONTROL Profile Merge Rule]또는 target 대상의 프로필 유형(장치 프로필 또는 인증된 프로필)을 포함하는 프로필입니다.

### [!UICONTROL Predictive Audiences] 모델 교육 단계 {#model-training}

알고리즘이 자사 대상자를 적합한 개인으로 분류하려면 먼저 데이터에 대해 자신을 교육해야 합니다.

정의한 각 담당자에 대해 알고리즘은 각각의 대상자를 분석하고 지난 30일 동안 사용자에 대한 실시간 및/또는 온보딩된 트레이트 활동을 평가합니다.
이 단계는 자사 대상의 변경 사항을 고려하여 24시간마다 한 번씩 수행됩니다.

### [!UICONTROL Predictive Audiences] 모델 분류 단계 {#model-classification}

실시간 및 배치 대상 분류의 경우 모델은 먼저 사용자가 타겟 대상에 속하는지 여부를 확인합니다. 사용자가 타겟 대상 자격을 충족하고 어떤 성향에도 속하지 않는 경우 모델은 사용자에게 성향 자격 점수를 지정합니다.

자사 대상을 평가하고 점수를 할당하는 동안 모델은 기본값을 사용합니다 **[!UICONTROL Profile Merge Rule]** 을(를) 계정에 정의했습니다. 마지막으로 방문자는 가장 높은 점수를 받은 담당자로 분류됩니다.

![predictive-audiences-graph](assets/predictive-audiences-graph.png)

## 고려 사항 및 제한 사항 {#considerations}

>[!IMPORTANT]
> 구현 단계로 이동하기 전에 이 섹션을 주의 깊게 읽으십시오.

구성 시 [!UICONTROL Predictive Audiences] 모델, 다음 고려 사항 및 제한 사항에 유의하십시오.

* 최대 10개의 [!UICONTROL Predictive Audiences] 모델을 만들 수 있습니다.
* 각 모델에 대해 최대 50개의 기본 트레이트/세그먼트를 선택할 수 있습니다.
* 제2자 데이터와 타사 데이터는에서 현재 지원되지 않습니다 [!UICONTROL Predictive Audiences].
* [!UICONTROL Predictive Audiences] 은 모든 자사 데이터 소스의 자사 트레이트를 기반으로 대상 분류를 수행합니다.
* 다음에 대한 세그먼트 평가 [!UICONTROL Predictive Audiences] 를 사용합니다. **[!UICONTROL Profile Merge Rule]** 모델을 만드는 동안 선택하는 옵션입니다. 에 대해 자세히 알아보기 [!UICONTROL Profile Merge Rules] 전용 항목 보기 [설명서](../profile-merge-rules/merge-rules-overview.md).
* 일부 트레이트 및 세그먼트는 기준선 또는 타겟 대상자로 지원되지 않습니다. [!UICONTROL Predictive Audiences] 다음 중 하나를 기준선 또는 타겟 대상으로 선택할 때 모델이 저장되지 않습니다.
   * 예측 트레이트로 생성된 예측 트레이트 및 세그먼트
   * [Adobe Experience Platform](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) 트레이트 또는 세그먼트;
   * 알고리즘 트레이트
   * 제2자 및 타사 트레이트.
* [!UICONTROL Predictive Audience] [!UICONTROL segments] 다음에서 사용할 수 없음: [!UICONTROL Audience Lab].

## [!UICONTROL Data Export Controls] {#dec}

다음에 의해 생성된 예측 세그먼트 [!UICONTROL Predictive Audiences] 모델은 [데이터 내보내기 제어](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html) 다음 자사 데이터 소스에서:

1. 모델을 작성할 때 선택하는 자사 데이터 소스.
1. 타겟 대상의 자사 데이터 소스입니다. 특히 의 데이터 내보내기 제어 [!UICONTROL traits] 또는 [!UICONTROL segments] 타겟 대상자를 구성합니다.
1. 다음 [데이터 내보내기 제어](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html) / [!UICONTROL Profile Merge Rule] 을(를) 모델에 대해 선택했습니다.

새로 생성된 예측 [!UICONTROL traits] 및 [!UICONTROL segments] 위에서 설명한 자사 데이터 소스의 통합과 동일한 개인 정보 보호 제한 사항을 갖습니다.

에 속하지 않는 추가 제한이 있는 트레이트 [!UICONTROL Predictive Audiences] 세그먼트 개인 정보 보호 제한은 교육 단계에서 제외되며, 모델에 영향을 주지 않습니다.

## [!UICONTROL Profile Merge Rules] {#pmr}

모든 예측 세그먼트에 [!UICONTROL Profile Merge Rule] 모델을 만들 때 선택한 옵션입니다. 다음 [!UICONTROL Profile Merge Rule] 다음과 같은 이유로 선택해야 합니다.

* 모델이 영향력을 분석할 때 고려해야 하는 장치 및/또는 인증된 프로필을 정의합니다 [!UICONTROL traits], 사용자를 예측으로 분류 시 [!UICONTROL segment].
* 어느 것이 지배적인지 [!UICONTROL trait] 유형(장치 수준 또는 교차 장치 수준)은 모델 교육 단계에서 사용해야 하며 영향력 있는 것으로 표시되어야 합니다 [!UICONTROL traits]. 예측 [!UICONTROL segments] 는 타겟 대상의 하위 집합입니다.
   * 타겟 대상이 세그먼트인 경우 동일한 을 선택하는 것이 좋습니다 [!UICONTROL Profile Merge Rule] 대상 대상자에게 할당된 모델인 경우 또는 [!UICONTROL Profile Merge Rule] 여기에는 타겟 대상의 프로필 유형이 포함됩니다.
   * 대상 대상이 다음과 같은 경우 [!UICONTROL trait], 을(를) 선택하는 것이 좋습니다. [!UICONTROL Profile Merge Rule] 대상 대상 트레이트와 동일한 유형의 데이터(장치 프로필 데이터 또는 교차 장치 프로필 데이터)에 액세스할 수 있습니다.
* [!UICONTROL Profile Merge Rules] 사용 [!UICONTROL Current Authenticated Profiles] 및 [!UICONTROL No Device Profile] 옵션은 실시간 대상 분류에 대해서만 지원됩니다. 자세한 내용은 [정의된 프로필 병합 규칙 옵션](../profile-merge-rules/merge-rule-definitions.md).

선택 [!UICONTROL Profile Merge Rule] 디바이스 데이터와 디바이스 간 데이터를 모두 사용하는 은 [!UICONTROL traits] 모델 교육 및 사용자 분류에 사용될 수 있습니다. [!UICONTROL segments].

## [!UICONTROL Role-Based Access Controls] {#rbac}

성향 및 대상 분류에 대해 선택하는 트레이트 및 세그먼트는 Audience Manager의 대상입니다 [역할 기반 액세스 제어](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html).

Audience Manager 사용자는 보유한 가상 사용자 및 타겟 대상에 대한 트레이트 또는 세그먼트만 선택할 수 있습니다. [보기 권한](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions).
