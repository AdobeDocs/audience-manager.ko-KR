---
description: 대응 가능 대상 기능 및 사용 사례에 대한 개요입니다.
keywords: DIL
seo-description: An overview of the Addressable Audience feature and use cases.
seo-title: Addressable Audiences
solution: Audience Manager
title: 대응 가능 대상
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: Match Rates
exl-id: 2728e4a8-522c-423f-a6ef-e4dd624f69e5
source-git-commit: cecdc0b0f43a146e11f7d23eb21a06146496ac2d
workflow-type: tm+mt
source-wordcount: '1813'
ht-degree: 1%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

의 개요 [!UICONTROL Addressable Audience] 기능 및 사용 사례

##  [!UICONTROL Addressable Audience]? {#addressable-audience-description}

다음 [!UICONTROL Addressable Audiences] 기능은 모든 속성에서 표시되는 대상 간에 겹치는 경우를 보여 줍니다. [!DNL Audience Manager] 데이터 및 선택한 대상을 수집합니다. 이 개념을 이해하는 데 도움이 되도록 아래 설명을 살펴보십시오. 각 원 간의 겹침은 서로 다른 유형의 대응 가능 대상을 나타냅니다.

![](assets/addressableAudienceVenn.png)


| 지표 | 설명 |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] 대상 [!UICONTROL Destination] | 모든 장치와 상호 작용한 모든 장치의 수입니다 [!DNL Audience Manager] 보고서 전환 확인 기간 동안 플랫폼 수준에서 선택한 고객과 일치할 수 있는 고객 [!UICONTROL destination]. <br><br>이 지표는 다음을 보여주므로 유용합니다. <ul><li>합계 크기 [!UICONTROL addressable audience] 그게 [!DNL Audience Manager] 특정 타겟팅에 도달할 수 있음 [!UICONTROL destination].</li><li>얼마나 큰 [!DNL Audience Manager] 프로필 풀은 타겟팅 플랫폼과 해당 대상의 크기를 위한 것입니다.</li></ul> |
| [!UICONTROL Customer Total Audience] | 다음 중 하나를 실현한 장치 수 [!UICONTROL rule-based trait] 속성 또는 [!UICONTROL onboarded trait] 전환 확인 기간 동안 오프라인 파일에서 |
| [!UICONTROL Customer Addressable Audience] | 두 장치 중 하나를 실현한 겹치는 장치 수 [!UICONTROL rule-based trait] 또는 [!UICONTROL onboarded trait] 전환 확인 기간 및 장치 동안 선택한 [!UICONTROL destination] 동기화 시간에 상관없이<br><br>이 지표는 다음과 같은 장치를 나타냅니다.<ul><li>다음 중 하나를 실현했습니다. [!UICONTROL rule-based] 또는 [!UICONTROL onboarded trait] 다시 보기 기간 동안 `AND`</li><li>선택한 사용자와 ID 동기화가 있습니다. [!UICONTROL destination] 동기화 시간에 상관없이</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] 백분율로 표시됨. |
| [!UICONTROL Total Segment Population] | 사용자의 구성원이었던 모든 장치의 수입니다 [!UICONTROL segment] 보고서 전환 확인 기간 동안 표시되지 않습니다. |
| [!UICONTROL Segment Addressable Audience] | 에 속했던 사용자 수 [!UICONTROL segment] 보고서 전환 확인 기간 동안 사이트에 대한 활성 ID 동기화가 있습니다. [!UICONTROL Segments] 를 통해 자신의 자사 데이터와 제2자 데이터 및 타사 데이터를 포함할 수 있습니다. [!UICONTROL traits] 에서 [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>팁: 1일 전환 확인 기간과 함께 사용하는 경우 이 지표를 통해 사용자의 현재 상태를 이해할 수 있습니다 [!UICONTROL segments]. 이것은 [!UICONTROL Segment Addressable Audience] 지표는 [!UICONTROL segment] 이전 날 내내. 이를 다음과 같은 사실들과 결합하십시오 [!DNL Audience Manager] 새로 고침 [!UICONTROL Addressable Audiences] 일별로, 이 지표와 전환 기간을 결합하여 최신 스냅샷을 제공합니다. [!UICONTROL segments]. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] 백분율로 표시됨. |

## [!UICONTROL Addressable Audiences] 인터페이스 {#addressable-audience-interface}

다음 [!UICONTROL Addressable Audience] 기능은 이 추상적인 개념을 수량화할 수 있는 데이터로 변환합니다. in [!DNL Audience Manager]을 사용하면 이 기능은 테이블 형식의 숫자 데이터와 함께 요약 정보를 제공하는 데이터 시각화와 대상 겹침을 표시합니다.

[!UICONTROL Addressable Audiences] 에 있습니다. **[!UICONTROL Audience Data > Destinations]**. 선택 **[!UICONTROL Integrated Platforms > Device-Based]** 주소 지정 가능한 대상 지표를 확인합니다.

![](assets/addressable-audiences-landing.png)

에 표시되는 세 가지 지표 [!UICONTROL Addressable Audiences] 랜딩 페이지 표시:

| 지표 | 설명 |
|---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | 이 지표는 [!UICONTROL Customer Addressable Audience] (위 표에 설명되어 있음) *지난 30일 동안* |
| **[!UICONTROL Match Rate]** | 이 지표는 [!UICONTROL Addressable Audience Match Rate] (위 표에 설명되어 있음) *지난 30일 동안*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | 모든 장치와 상호 작용한 모든 장치의 수입니다 [!DNL Audience Manager] 보고서 전환 확인 기간 동안 플랫폼 수준에서 고객과 일치할 수 있는 고객 [!UICONTROL destination]. 자세한 내용은 [플랫폼 수준 지표](/help/using/features/addressable-audiences.md#platform-level-metrics) 추가 정보. |

이름을 클릭합니다 [!UICONTROL server-to-server destination] 대응 가능 대상 데이터를 보려면 참고: 이 기능은 [!UICONTROL server-to-server destinations] 및 액세스에만 관리자 권한이 필요합니다.

![](assets/addressableAudiences.png)

이 데이터를 검토하면 다음을 수행할 수 있습니다.

* **예측 및 계획:** [!UICONTROL Segment Addressable Audience] 데이터는 대상 타깃팅 및 활성화를 위해 대상으로 전송하려는 세그먼트를 더 세부적으로 제공합니다.

* **성능 검토:** 다음 [!UICONTROL Addressable Audiences] 기능은 문제 해결 도구이기도 합니다. 이 기능을 사용하면 캠페인 성과를 검토하고, 캠페인 도달 범위를 이해하며, 예상 결과가 표시되지 않는 경우 타깃팅/활성화 파트너와 상호 확인할 수 있습니다.

### 타사 데이터와 일치율에 대한 의미 비교

대상 획득을 위한 타사 데이터를 구매하기 전에 고객이 다른 데이터 공급자와 겹치는지 확인할 수 있습니다. 이렇게 하면 새 데이터를 사기 전에 현명한 결정을 내릴 수 있습니다. 구매한 타사 데이터에 대한 ID 동기화는 데이터가 겹칠 뿐만 아니라 타사 공급자의 풋프린트에 의존합니다 [!DNL Audience Manager] 고객. 사용자 [!DNL Adobe] 컨설턴트는 잠재 고객 대상 캠페인을 최적화하기 위해 추가적인 관련 데이터 소스를 식별하는 데 도움을 줄 수 있습니다.

### 모바일 사용자 및 일치율

연결을 시도할 때 간격이 있습니다 [!DNL Safari] 또는 타사가 없는 모바일 앱 사용자 [!DNL cookies] 표시합니다. 따라서 일부 파트너와 사용자를 동기화하는 것은 매우 어렵습니다. 이는 파트너만 있기 때문입니다 [!DNL Adobe] 동기화된 타사 ID입니다 [!DNL cookies] 미디어 게재 로그에 제공됩니다. 이러한 이유로 [낮은 일치율](../features/addressable-audiences.md#low-match-rates) 에 대해 [!UICONTROL destinations].

## 날짜 범위 입력 [!UICONTROL Addressable Audiences] 및 [!UICONTROL Destinations] {#date-ranges}

사용 가능한 날짜 범위와 보고서에서 각 간격에 따라 데이터가 어떻게 만료되는지 아래 섹션을 참조하십시오. [!UICONTROL Addressable Audience] 또는 [!UICONTROL Destination].

## 사용 가능한 날짜 범위 및 시간대 {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

보고서 [!UICONTROL Addressable Audiences] 및 [대상](../features/destinations/destinations.md) 동일한 날짜 범위 간격을 사용합니다. 날짜 범위 옵션은 다음과 같습니다.

* [!UICONTROL Last 1 Day] (이 간격은 이전 24시간 기간 중 자정부터 자정까지 실행됩니다. 실시간 또는 현재 시간 지표가 아닙니다.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

모든 날짜 및 날짜 범위는 [!DNL UTC] 시간대 자세한 내용은 [Audience Manager의 시간대](../reference/aam-time-zones.md).

## 날짜 범위 간격의 데이터 {#date-range-intervals}

다음 [!UICONTROL Addressable Audience] 및 [!UICONTROL Destination] 지표는 선택한 시간 간격에 대한 고유 사용자 수를 반환합니다. 예를 들어 방문자는 사이트를 여러 번 방문하는 경우에도 한 번만 카운트됩니다. 첫 번째 방문은 고유한 방문이며 기록됩니다. 후속 방문이 재방문이며 고유하지 않으므로 계산되지 않습니다.

날짜 범위에는 선택한 시간 간격 또는 그 이상의 데이터가 포함됩니다. 또한 시간이 경과함에 따라 데이터가 각 보고서 간격에서 시간 초과됩니다. 예를 들어 을 선택한 후 방문자가 2명이라고 가정해 보겠습니다. [!UICONTROL Last 30 Days] 선택 사항입니다. 보고서에서 이러한 방문자는 다음과 같습니다.

* *다음* 긴 시간 간격(60일, 90일 및 라이프타임)에 의해 반환된 결과에 포함됩니다.
* *안 됨* 앞에 오는 짧은 간격에 포함됨 [!UICONTROL Last 30 Day] 옵션(현재, 7일 및 14일).

그리고, 31일에, 이 방문자들은 60일, 90일에만 나타났고, [!UICONTROL Lifetime] 결과. 그들은 30일 간격 중 이미 나이가 들었다. 방문자는 오래되지 않습니다 [!UICONTROL Lifetime] 간격.

## [!UICONTROL Addressable Audiences] 지표 {#addressable-audience-metrics}

이 섹션에서는 다음 방법으로 제공하는 지표 유형을 설명합니다 [!UICONTROL Addressable Audiences].

### 고객 수준 지표 {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

이 지표는 방문자가 사이트를 방문하거나 인바운드 데이터 파일을 로 보낼 때 실현된 트레이트에 대한 데이터를 반환합니다 [!DNL Audience Manager]. 이러한 지표는 계정에 대한 대상 크기에 대한 포괄적인 보기를 제공합니다.

| 지표 | 설명 |
|---|---|
| [!UICONTROL Customer Addressable Audience] | 두 장치 중 하나를 실현한 겹치는 장치 수 [!UICONTROL rule-based trait] 또는 [!UICONTROL onboarded trait] 전환 확인 기간 및 장치 동안 동기화 시간과 관계없이 선택한 대상과의 ID 동기화가 있습니다.<br><br>이 지표는 다음과 같은 장치를 나타냅니다.<ul><li>다음 중 하나를 실현했습니다. [!UICONTROL rule-based] 또는 [!UICONTROL onboarded trait] 다시 보기 기간 동안 `AND`</li><li>선택한 사용자와 ID 동기화가 있습니다. [!UICONTROL destination] 동기화 시간에 상관없이</li></ul> |
| [!UICONTROL Customer Total Audience] | 다음 중 하나를 실현한 장치 수 [!UICONTROL rule-based trait] 속성 또는 [!UICONTROL onboarded trait] 전환 확인 기간 동안 오프라인 파일에서 |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] 백분율로 표시됨. |

### 세그먼트 수준 일치 지표 {#segment-level-metrics}

이 지표는 데이터를 [!UICONTROL segment] 멤버십. 이 도구를 사용하면 각 대상의 대상 크기를 더 세부적인 그리고 정확하게 볼 수 있습니다 [!UICONTROL segments].

>[!NOTE]
>
>전환 확인 창이 [!UICONTROL segment] 수준은 고객 수준의 레벨과 다릅니다. 방문자가 사이트를 방문하여 다음을 실현할 수 있습니다. [!UICONTROL trait] 10일 전, 그들은 [!UICONTROL segment] 그때 이후로 [!UICONTROL segment] 2일 전 7일 전환 확인 작업이 적용되면 이러한 방문자는 [!UICONTROL segment] 수준 ( 고객 수준이 아님).

| 지표 | 설명 |
|---|---|
| [!UICONTROL Segment Addressable Audience] | 에 속했던 사용자 수 [!UICONTROL segment] 보고서 전환 확인 기간 동안 사이트에 대한 활성 ID 동기화가 있습니다. 세그먼트는 를 통해 자신의 자사 데이터와 제2자 데이터, 타사 데이터를 포함할 수 있습니다 [!UICONTROL traits] 에서 [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>팁: 1일 전환 확인 기간과 함께 사용하는 경우 이 지표를 통해 사용자의 현재 상태를 이해할 수 있습니다 [!UICONTROL segments]. 이것은 [!UICONTROL Segment Addressable Audience] 지표는 [!UICONTROL segment] 이전 날 내내. 이를 다음과 같은 사실들과 결합하십시오 [!DNL Audience Manager] 새로 고침 [!UICONTROL Addressable Audiences] 일별로, 이 지표와 전환 기간을 결합하여 최신 스냅샷을 제공합니다. [!UICONTROL segments]. |
| [!UICONTROL Total Segment Population] | 사용자의 구성원이었던 모든 장치의 수입니다 [!UICONTROL segment] 보고서 전환 확인 기간 동안 표시되지 않습니다. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] 백분율로 표시됨. |

### 플랫폼 수준 지표 {#platform-level-metrics}

이 지표는 전체적으로 수집된 활동에 대한 데이터를 반환합니다 [!DNL Audience Manager] 고객. 집계된 대상과 비교하여 고객 대상에 대한 더 광범위한 보기를 제공할 수 있습니다 [!DNL Audience Manager] 고객.

| 지표 | 설명 |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | 모든 장치와 상호 작용한 모든 장치의 수입니다 [!DNL Audience Manager] 보고서 전환 확인 기간 동안 플랫폼 수준에서 선택한 고객과 일치할 수 있는 고객 [!UICONTROL destination]. <br><br>이 지표는 다음을 보여주므로 유용합니다.<ul><li>크기 [!UICONTROL total addressable audience] 그게 [!DNL Audience Manager] 특정 타깃팅 대상에 도달할 수 있습니다.</li><li>얼마나 큰 [!DNL Audience Manager] 프로필 풀은 타겟팅 플랫폼과 해당 대상의 크기를 위한 것입니다.</li></ul> |

## 비교 [!UICONTROL Customer] 및 [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

와 비교해서는 안 됩니다 [!UICONTROL Customer Addressable Audience] 및 [!UICONTROL Segment Addressable Audience] 지표가 다른 지표보다 더 중요한지 판별하는 지표입니다. 이는 별도의, 서로 다른, 독립적인 지표입니다. 위의 정의에 설명된 대로 이러한 각 데이터 세트는 서로 다른 데이터 세트에서 파생됩니다. 이 경우 한 지표가 다른 지표보다 큰 경우 결론에 도달하지 않아야 합니다. 이것들을 비교할 때 당신이 말할 수 있는 것은 다음과 같습니다.

* [!UICONTROL Customer Addressable Audiences] 는 [!UICONTROL trait] 실현 *자사 데이터에 대한*. 이 지표는 데이터 파트너와 통합하는 방법에 대한 포괄적이고 광범위한 보기를 제공합니다.

* [!UICONTROL Segment Addressable Audiences] 은 세그먼트 자격에 기반합니다 *자사 데이터와 제2자 데이터, 타사 데이터*. 이 지표는 사용자의 세부 사항을 보다 정확하게 보여줍니다 [!UICONTROL addressable audiences] 타겟팅 플랫폼

## 에 대한 낮은 일치율의 원인 [!UICONTROL Addressable Audiences] {#low-match-rates}

저하를 담당하는 일반적인 요소 [!UICONTROL Addressable Audience] 보고된 숫자의 일치율 또는 불일치

| 원인 | 설명 |
|---|---|
| 모바일 트래픽 | 가장 많이 [!UICONTROL server-to-server] 통합은 타사에서 제공하는 동기화 프로세스를 사용합니다 [!DNL cookies]. 그러나 모바일 환경에서는 타사를 사용하지 않습니다 [!DNL cookies]. 따라서, [!UICONTROL Addressable Audiences] 숫자가 낮은 것 같다 [!UICONTROL segment] 크기. <br><br>2018년 1월 현재, 동일한 위치에서 모바일 대상을 활성화할 수 있습니다 [!DNL Google] 및 [!DNL Adobe Advertising Cloud] 대상 설정 대상 [!UICONTROL cookie-based] 대상. 을 전송하는 것은 [!UICONTROL segments] 결합 [!DNL cookie] 및 모바일 ID 멤버십에 대한 액세스 권한을 부여합니다 [!DNL Google] 및 [!DNL Advertising Cloud] 대상, 다음 사항에 주의하십시오. [!UICONTROL Addressable Audiences] 다음 사이 겹치기만 표시 [!DNL cookie] ID 및 대상. [!DNL Audience Manager] 는 모바일 대상의 100%를 로 로 보냅니다 [!UICONTROL destinations]하지만 모바일 대상은 다음으로 측정되지 않습니다. [!UICONTROL Addressable Audience] 지표. <br><br>**참고**: 예를 들어 [!UICONTROL segment] 인구 100만 명. 매핑하면 [!UICONTROL segment] 변환 후 [!DNL Google] 또는 [!DNL Adobe Advertising Cloud] 대상, [!UICONTROL Addressable Audience] 장치 70만 개 중 [!UICONTROL Match Rate] 70% 중 70만 명의 회원이 [!DNL cookie] 와 ID 동기화가 있는 ID [!UICONTROL destination]. 사용자 [!UICONTROL Addressable Audience] 대응 가능 모바일 ID는 이 지표에 표시되지 않으므로 실제로 더 높일 수 있습니다. |
| [!DNL Safari] 트래픽 | [!DNL Safari] 서드파티 블록 [!DNL cookies]. 이렇게 하면 [!DNL Audience Manager] ID와 동기화 [!UICONTROL destination]. 의 도입으로 [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/), 다음 작업을 수행할 수 있습니다. [!UICONTROL addressable audiences] 포함하지 않음 [!DNL Safari] 사용자 참조. |
| 추적된 미디어 노출 횟수 | 광고 서버 우수 사례로 인해 ID 동기화는 광고 태그 내에 작성되지 않습니다. 대량의 오프사이트 광고를 수행하는 고객은 해당 환경의 타사 통합에 사용자를 동기화하지 않습니다. 또한 많은 양의 수집된 미디어 노출 데이터가 감소될 수 있습니다 [!UICONTROL addressable audience] 번호. |

## 문제 해결 [!UICONTROL Addressable Audiences] {#troubleshooting}

서피싱 일치율 외에 [!UICONTROL Addressable Audiences] 을 문제 해결 도구로 사용할 수 있습니다.

예를 들어 세그먼트를 [!UICONTROL destination] 그리고 [!UICONTROL destination] 낮은 보고 수치를 표시합니다. 확인 [!UICONTROL Addressable Audience] 기술적인 문제인지 또는 일치율이 낮은 경우인지 결과가 표시됩니다. 낮은 일치율은 [!UICONTROL destination] 은 선택한 세그먼트에 대해 그다지 좋지 않습니다. 하지만, [!UICONTROL total addressable audience] 숫자 사이의 [!DNL Audience Manager] 그리고 [!UICONTROL destination] 통합, 동기화 또는 기타 기술 문제를 나타냅니다. 이러한 경우 계정 관리자에게 문의하십시오.
