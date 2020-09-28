---
description: Predictive Audiences을 사용하면 데이터 과학을 사용하여 알 수 없는 대상을 실시간으로 개별 성향으로 분류할 수 있습니다.
seo-description: Predictive Audiences을 사용하면 데이터 과학을 사용하여 알 수 없는 대상을 실시간으로 개별 성향으로 분류할 수 있습니다.
seo-title: Predictive Audiences 개요
solution: Audience Manager
title: Audience Manager Predictive Audiences
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: 1df6e8a76e5eae85483820926474ebc8633d5591
workflow-type: tm+mt
source-wordcount: '1551'
ht-degree: 7%

---


# [!UICONTROL Predictive Audiences] 개요 {#predictive-audiences}

[!UICONTROL Predictive Audiences] 고급 데이터 과학 기술을 사용하여 알려지지 않은 고객을 개별 인물로 실시간으로 분류할 수 있습니다.

>[!IMPORTANT]
>이 문서에는 이 기능의 설정 및 사용을 안내하는 제품 설명서가 포함되어 있습니다. 여기에 들어 있는 어떠한 것도 법적 권고사항이다. 법률 자문을 위해 법률 자문을 구할 수 있습니다.

마케팅 컨텍스트에서 성향은 인구 통계, 탐색 습관, 쇼핑 이력 등과 같은 특정 트레이트 집합을 공유하는 방문자, 사용자 또는 잠재적 구매자로 정의되는 대상 세그먼트로입니다.

[!UICONTROL Predictive Audiences] 모델은 Audience Manager의 기계 학습 기능을 사용하여 알 수 없는 대상을 개별 성향으로 분류할 수 있도록 함으로써 이러한 개념을 한 단계 더 발전시킵니다. Audience Manager를 사용하면 일단의 알려진 자사 고객에 대해 알 수 없는 자사 대상의 성향을 계산하여 이를 달성할 수 있습니다.

모델을 만들 때 첫 번째 단계는 대상 대상을 분류할 기준 특성이나 세그먼트를 선택하는 것입니다. [!UICONTROL Predictive Audiences] 이러한 트레이트 또는 세그먼트는 사용자의 성격을 정의합니다.

평가 단계 동안 모델은 베이스라인으로 정의한 각 특성 또는 세그먼트에 대한 새 [!UICONTROL Predictive Audiences] 세그먼트를 만듭니다. 다음 번에 Audience Manager에서 가상 사용자로 분류되지 않은 타겟 대상의 방문자를 볼 때(기본 특성 또는 세그먼트에 대한 자격이 부여되지 않음), [!UICONTROL Predictive Audiences] 모델은 방문자가 속해야 하는 예측 세그먼트 중 어떤 예측 세그먼트를 결정하고 해당 세그먼트에 방문자를 추가합니다.

모델에서 생성된 예측 세그먼트를 페이지에서 식별할 수 [!UICONTROL Segments] 있습니다. 각 [!UICONTROL Predictive Audiences] 모델에는 [!UICONTROL Predictive Audiences] 폴더 아래에 자체 폴더가 있으며 모델 폴더를 클릭하여 각 모델의 세그먼트를 볼 수 있습니다.

![predictive-audiences-segments](assets/predictive-audiences-segments.png)

## 사용 사례 {#use-cases}

사용 방법 및 시기를 보다 잘 이해할 수 있도록 Audience Manager 고객이 이 기능 [!UICONTROL Predictive Audiences]을 사용하여 해결할 수 있는 몇 가지 사용 사례를 소개합니다.

### 사용 사례 #1

e커머스 회사의 마케터로서 모든 웹 및 모바일 방문자를 다양한 브랜드 친화성 카테고리로 분류하여 사용자 경험을 개인화할 수 있습니다.

### 사용 사례 #2

미디어 기업의 마케터로서 저는 인증되지 않은 웹 및 모바일 방문자를 즐겨 사용하는 장르별로 분류하고 싶습니다. 그러면 모든 채널에서 개인화된 컨텐츠를 제공할 수 있습니다.

### 사용 사례 #3

항공사 광고주로서, 저는 제 고객을 여행 목적지에 대한 관심에 따라 분류하고, 짧은 리타겟팅 기간 내에 그들에게 실시간으로 광고할 수 있도록 하고 싶습니다.

### 사용 사례 #4

광고주로서 저는 제 퍼스트 파티 참가자를 실시간으로 분류하여 트렌드 뉴스에 빠르게 반응하고 싶습니다.

### 사용 사례 #5

마케터는 검색, 참여, 구매 또는 유지 등 웹 사이트 방문자가 어떤 고객 경로 단계를 경험하는지 예측하여 그에 따라 타깃팅할 수 있습니다.

### 사용 사례 #6

미디어 회사로서 고객을 분류하고 싶은데, 이를 통해 방문자에게 연관성 있는 광고를 제공하는 동시에 프리미엄 가격으로 광고 공간을 판매할 수 있습니다.

## 모델 [!UICONTROL Predictive Audiences] 작동 방식 {#how-predictive-audiences-models-work}

모델을 만들 때 [!UICONTROL Predictive Audiences] 다음 세 단계를 진행합니다.

1. 먼저, 성향을 정의할 최소한 두 개의 특성이나 두 개의 세그먼트를 선택합니다.
1. 그런 다음 분류할 대상 대상을 정의하는 트레이트 또는 세그먼트를 선택합니다.
1. 마지막으로, 모델의 이름, 예측 세그먼트를 저장할 데이터 소스 및 모델 [!UICONTROL Profile Merge Rule] 의 이름을 선택합니다.

### 개인 선택 기준 {#selection-personas}

자사 특성 또는 세그먼트를 선택하여 개인 이름을 정의할 수 있습니다. 그러나 최적의 결과를 얻으려면 다음 권장 우수 사례 세트가 있습니다.

* 각 페르소나의 [장치 ID가 최소 수백 개 되도록 페르소나 트레이트 또는 세그먼트를 선택합니다](../../reference/ids-in-aam.md).
* 트레이트가 [크로스 장치 ID를](../../reference/ids-in-aam.md)기반으로 하는 경우 [장치 ID를](../profile-merge-rules/merge-rules-overview.md) 사용하는 [프로필 병합 규칙](../../reference/ids-in-aam.md)을 사용하여 [!UICONTROL Device Graph]세그먼트로래핑할 수있습니다. 이렇게 하면 알고리즘에서 배울 수 있는 [장치](../../reference/ids-in-aam.md) ID가 충분합니다.
* 1~3개의 트레이트로 구성된 특성에 대해 특성이나 간단한 세그먼트를 선택하는 것이 좋습니다.
* 겹치지 않는 기준 특성이나 세그먼트를 선택할 수 있습니다.
* 디지털 자산에서 세부적인 트레이트를 캡처하고 있는지 확인합니다.

### Target 대상을 위한 선택 기준 {#selection-audience}

페르소나 선택과 유사하게, [!UICONTROL trait] 또는 타겟 고객을 정의하는 대상을 선택하는 [!UICONTROL segment] 방법은 풍부한 세트의 실시간 사용자가 적절한 페르소나를 분류할 수 [!UICONTROL traits]있도록 해야 합니다.

대상 대상을 선택할 때 사용 사례를 분석하고 분류할 ID 유형을 결정합니다. [!UICONTROL device IDs] 또는 [!UICONTROL cross-device IDs]. 모델을 생성할 때 선택하는 [!UICONTROL Profile Merge Rule] 데이터는 각 사용자를 예측으로 배치하는 데 사용할 데이터를 정의합니다 [!UICONTROL segments].

타겟 대상과 동일한 구성 [!UICONTROL Profile Merge Rule] 을 가진 사용자 또는 대상 대상의 프로필 유형(장치 프로파일 또는 인증된 프로필)을 포함하는 사용자 [!UICONTROL Profile Merge Rule]를 선택하는 것이 좋습니다.

### [!UICONTROL Predictive Audiences] 모델 교육 단계 {#model-training}

이 알고리즘이 자사 고객을 적합한 개인으로 분류하려면 먼저 데이터를 기반으로 학습해야 합니다.

사용자가 정의하는 각 페르소나에 대해 알고리즘은 해당 대상을 분석하고 지난 30일 동안 해당 사용자에 대한 실시간 및/또는 온보딩 트레이트 활동을 평가합니다.
이 단계는 자사 대상의 변경 사항을 반영하기 위해 24시간마다 한 번씩 수행됩니다.

### [!UICONTROL Predictive Audiences] 모델 분류 단계 {#model-classification}

타겟 대상의 일부인 방문자를 실시간으로 볼 때 모델은 방문자가 정의된 성향에 속하는지 여부를 평가합니다. 어떤 개인에도 속하지 않는 모든 방문자에 대해 모델은 페르소나 자격 점수를 지정합니다.

자사 대상을 평가하고 점수를 할당하는 동안 모델은 계정에 정의된 기본값을 사용합니다. **[!UICONTROL Profile Merge Rule]** 마지막으로 방문자는 최고 점수를 받은 가상 사용자로 분류됩니다.

![예측 대상 그래프](assets/predictive-audiences-graph.png)

## 고려 사항 및 제한 사항 {#considerations}

>[!IMPORTANT]
> 구현 단계로 이동하기 전에 이 섹션을 자세히 읽어 보십시오.

모델을 구성할 때 다음 고려 사항 및 제한 사항에 [!UICONTROL Predictive Audiences] 유의하십시오.

* 최대 10개의 [!UICONTROL Predictive Audiences] 모델을 만들 수 있습니다.
* 각 모델에 대해 최대 50개의 기본 트레이트/세그먼트를 선택할 수 있습니다.
* 타사 및 타사 데이터는 현재 에서 지원되지 않습니다 [!UICONTROL Predictive Audiences].
* 고객 분류는 퍼스트 파티 대상자에게만 수행됩니다. 향후 업데이트에서는 온보드 퍼스트 파티 분류가 지원될 수 있습니다.
   >[!IMPORTANT]
   > 예측 트레이트를 일반 세그먼트에 추가하면 예측 세그먼트가 됩니다. 따라서 모든 관련 프로필은 세그먼트화되지 않습니다.

   >[!IMPORTANT]
   > 현재 예측 세그먼트는 실시간 대상에서만 활성화할 수 있습니다. 예측 세그먼트 [!UICONTROL Total Segment Population] 와 [!UICONTROL Addressable Audience] 가 0으로 표시되고, [아웃바운드 데이터 전송](../../integration/receiving-audience-data/batch-outbound-transfers/batch-outbound-overview.md) 일괄 [!UICONTROL Predictive Audiences]작업은 지원되지 않습니다. 이 동작은 향후 업데이트 시 변경됩니다.
* [!UICONTROL Predictive Audiences] 모든 자사 데이터 소스에서 자사 트레이트를 기반으로 고객 분류를 수행합니다.
* 세그먼트 평가 [!UICONTROL Predictive Audiences] 는 모델을 생성하는 동안 선택한 **[!UICONTROL Profile Merge Rule]** 값을 사용합니다. 자세한 내용은 [!UICONTROL Profile Merge Rules] 전용 [설명서를 참조하십시오](../profile-merge-rules/merge-rules-overview.md).
* 일부 트레이트 및 세그먼트는 기준선 또는 대상 대상으로 지원되지 않습니다. [!UICONTROL Predictive Audiences] 다음 중 하나를 기준선 또는 대상 대상으로 선택할 때 모델이 저장되지 않습니다.
   * 예측 트레이트로 생성된 예측 트레이트 및 세그먼트
   * [Adobe Experience Platform](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) 트레이트 또는 세그먼트
   * 알고리즘 특성;
   * 제휴 및 제3자 특성

## [!UICONTROL Data Export Controls] {#dec}

모델로 생성된 예측 세그먼트는 다음 자사 데이터 소스 [!UICONTROL Predictive Audiences] 에서 [](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) 데이터 내보내기 컨트롤을 상속합니다.

1. 모델을 작성할 때 선택하는 퍼스트 파티 데이터 소스.
1. 타겟 고객의 퍼스트 파티 데이터 소스 특히 타겟 고객을 구성하는 [!UICONTROL traits] 또는 [!UICONTROL segments] 의 데이터 내보내기 제어
1. 모델에 대해 선택한 [데이터 내보내기](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) 컨트롤 [!UICONTROL Profile Merge Rule] 입니다.

새로 만들어진 예측 [!UICONTROL traits] 및 [!UICONTROL segments] 는 위에 설명된 자사 데이터 소스의 결합과 동일한 개인 정보 보호 제한을 가집니다.

세그먼트 개인 정보 보호 제한에 속하지 않는 추가 제한 사항이 있는 트레이트는 [!UICONTROL Predictive Audiences] 교육 단계에서 제외되며 모델에 영향을 주지 않습니다.

## [!UICONTROL Profile Merge Rules] {#pmr}

모든 예측 세그먼트는 모델을 만들 때 선택한 [!UICONTROL Profile Merge Rule] 에 할당됩니다. 다음 이유 [!UICONTROL Profile Merge Rule] 로 선택하는 것이 중요합니다.

* 또한 사용자가 예측 분석으로 분류될 때 모델이 영향력 있는 요소를 분석할 때 고려할 디바이스 및/또는 인증된 프로필 [!UICONTROL traits]을 정의합니다 [!UICONTROL segment].
* 모델 교육 단계에서 사용해야 하는 [!UICONTROL trait] 유형(장치 수준 또는 장치 간 수준)을 규율하고 영향력이 있는 것으로 드러났습니다 [!UICONTROL traits]. 예측 [!UICONTROL segments] 은 타겟 대상의 하위 세트입니다.
   * 대상 대상이 세그먼트인 경우 대상 대상에 할당된 대상 또는 대상 대상의 프로필 유형을 포함하는 모델 [!UICONTROL Profile Merge Rule] 에 대해 동일한 것을 선택하는 것이 [!UICONTROL Profile Merge Rule] 좋습니다.
   * 대상 대상이 a인 경우 대상 특성 [!UICONTROL trait]과 동일한 유형의 데이터(장치 프로필 데이터 또는 장치 간 프로필 데이터)에 액세스할 수 [!UICONTROL Profile Merge Rule] 있는 데이터를 선택하는 것이 좋습니다.

장치 데이터와 [!UICONTROL Profile Merge Rule] 장치 간 데이터를 모두 사용하는 데이터를 선택하면 모델 교육 및 사용자 분류에 사용할 수 [!UICONTROL traits] 있는 개수가 예측으로 극대화됩니다 [!UICONTROL segments].

## [!UICONTROL Role-Based Access Controls] {#rbac}

개인 및 대상 분류에 대해 선택하는 트레이트 및 세그먼트는 Audience Manager 역할 기반 액세스 제어 [의 적용을 받습니다](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html).

Audience Manager 사용자는 볼 [권한이 있는 개인 및 대상 대상의 특성이나 세그먼트만 선택할 수 있습니다](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions).
