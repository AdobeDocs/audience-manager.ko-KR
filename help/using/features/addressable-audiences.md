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

다음에 대한 개요 [!UICONTROL Addressable Audience] 기능 및 사용 사례입니다.

##  [!UICONTROL Addressable Audience]? {#addressable-audience-description}

다음 [!UICONTROL Addressable Audiences] 은 모든 속성에서 보는 대상 간의 겹침을 보여 줍니다. [!DNL Audience Manager] 데이터 및 선택한 대상을 수집합니다. 이 개념을 이해하는 데 도움이 되도록 아래 그림을 살펴보십시오. 각 원 간의 겹침은 서로 다른 유형의 대응 가능 대상을 나타냅니다.

![](assets/addressableAudienceVenn.png)


| 지표 | 설명 |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] 용 [!UICONTROL Destination] | 모든 장치와 상호 작용한 모든 장치의 수 [!DNL Audience Manager] 보고서 전환 확인 기간 동안 플랫폼 수준에서 고객이 선택한 항목과 일치할 수 있음 [!UICONTROL destination]. <br><br>이 지표는 다음을 보여주므로 유용합니다. <ul><li>총 크기 [!UICONTROL addressable audience] that [!DNL Audience Manager] 특정 타겟팅에 도달할 수 있음 [!UICONTROL destination].</li><li>크기가 어느 정도죠 [!DNL Audience Manager] 프로필 풀은 타겟팅 플랫폼 및 대상자 크기에 사용됩니다.</li></ul> |
| [!UICONTROL Customer Total Audience] | 다음 중 하나를 실현한 장치 수: [!UICONTROL rule-based trait] 속성 또는 [!UICONTROL onboarded trait] 전환 확인 기간 동안 오프라인 파일에서 |
| [!UICONTROL Customer Addressable Audience] | 다음 중 하나를 실현한 장치 겹치기 수: [!UICONTROL rule-based trait] 또는 [!UICONTROL onboarded trait] 전환 확인 기간 및 장치 중에 선택한 항목과 ID 동기화 [!UICONTROL destination] 동기화 시간과 상관없이<br><br>이 지표는 다음과 같은 장치를 나타냅니다.<ul><li>다음 중 하나를 인식함: [!UICONTROL rule-based] 또는 [!UICONTROL onboarded trait] 전환 확인 기간 동안 `AND`</li><li>선택한 과(와) ID 동기화 [!UICONTROL destination] 동기화 시간과 상관없이</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] 백분율로 표시됩니다. |
| [!UICONTROL Total Segment Population] | 의 구성원이었던 모든 장치의 수입니다. [!UICONTROL segment] 보고서 전환 확인 기간 동안. |
| [!UICONTROL Segment Addressable Audience] | 에 속한 사용자의 수입니다. [!UICONTROL segment] 보고서 전환 확인 기간 동안 및 를 사이트에 활성 ID 동기화가 있습니다. [!UICONTROL Segments] 을 통해 자신의 자사 데이터와 제2자 데이터, 타사 데이터를 포함할 수 있습니다. [!UICONTROL traits] 다음에 획득됨 [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>팁: 1일 룩백 기간과 함께 사용할 경우 이 지표를 통해 의 현재 상태를 파악할 수 있습니다. [!UICONTROL segments]. 이유는 다음과 같습니다. [!UICONTROL Segment Addressable Audience] 지표는 에 머문 사용자를 나타냅니다. [!UICONTROL segment] 전날 내내 다음과 같은 사실과 결합 [!DNL Audience Manager] 새로 고침 [!UICONTROL Addressable Audiences] 일별로, 이 지표와 전환 확인 기간을 결합하면 의 최신 스냅샷을 제공합니다. [!UICONTROL segments]. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] 백분율로 표시됩니다. |

## [!UICONTROL Addressable Audiences] 인터페이스 {#addressable-audience-interface}

다음 [!UICONTROL Addressable Audience] 기능은 이 추상적인 개념을 수량화할 수 있는 데이터로 바꿉니다. 위치 [!DNL Audience Manager], 이 기능은 숫자 데이터와 함께 테이블 형식으로 요약 정보를 제공하는 데이터 시각화와 대상 겹침을 표시합니다.

[!UICONTROL Addressable Audiences] 위치: **[!UICONTROL Audience Data > Destinations]**. 선택 **[!UICONTROL Integrated Platforms > Device-Based]** 지정 대상 지표를 확인합니다.

![](assets/addressable-audiences-landing.png)

에서 볼 수 있는 세 가지 지표 [!UICONTROL Addressable Audiences] 랜딩 페이지는 다음을 나타냅니다.

| 지표 | 설명 |
|---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | 이 지표는 [!UICONTROL Customer Addressable Audience] (위의 표에 설명됨) *지난 30일 동안* |
| **[!UICONTROL Match Rate]** | 이 지표는 [!UICONTROL Addressable Audience Match Rate] (위의 표에 설명됨) *지난 30일 동안*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | 모든 장치와 상호 작용한 모든 장치의 수 [!DNL Audience Manager] 보고서 전환 확인 기간 동안의 플랫폼 수준 고객 및 이와 일치할 수 있는 고객 [!UICONTROL destination]. 다음을 참조하십시오 [플랫폼 수준 지표](/help/using/features/addressable-audiences.md#platform-level-metrics) 추가 정보. |

이름 클릭 [!UICONTROL server-to-server destination] 지정 대상 데이터를 볼 수 있습니다. 참고: 이 기능은 다음에 대한 데이터를 반환합니다. [!UICONTROL server-to-server destinations] 및 액세스에만 관리자 권한이 필요합니다.

![](assets/addressableAudiences.png)

이 데이터를 검토하면 다음 작업에 도움이 될 수 있습니다.

* **예측 및 계획:** [!UICONTROL Segment Addressable Audience] 데이터는 대상 타기팅 및 활성화를 위해 대상으로 전송하려는 세그먼트에 대해 더 세분화된 데이터를 제공합니다.

* **성능 검토:** 다음 [!UICONTROL Addressable Audiences] 이 기능은 문제 해결 도구이기도 합니다. 이를 통해 캠페인 성과를 검토하고, 캠페인 도달 범위를 이해하고, 예상한 결과가 표시되지 않는 경우 타기팅/활성화 파트너와 상호 확인할 수 있습니다.

### 타사 데이터로 잠재 고객 확보 및 일치율에 대한 영향

대상 획득을 위해 타사 데이터를 구매하기 전에 고객은 다른 데이터 공급자와의 겹침을 확인할 수 있습니다. 이렇게 하면 새 데이터를 구입하기 전에 정보에 입각한 결정을 내리는 데 도움이 됩니다. 구매한 타사 데이터에 대한 ID 동기화는 데이터의 겹침뿐만 아니라 타사 공급자의 다른 모든 발자국에 의존합니다 [!DNL Audience Manager] 고객. 사용자 [!DNL Adobe] 컨설턴트는 잠재 고객 캠페인을 최적화하기 위해 추가 관련 데이터 소스를 식별하는 데 도움을 줄 수 있습니다.

### 모바일 사용자 및 일치율

연결을 시도할 때 간격이 있습니다. [!DNL Safari] 또는 서드파티가 없는 모바일 앱 사용자 [!DNL cookies] 있음. 따라서 일부 파트너와 사용자를 동기화하지 못할 수 있습니다. [!DNL Adobe] 동기화된 타사 ID [!DNL cookies] 미디어 게재 로그에 제공됩니다. 이것이 다음을 볼 수 있는 이유입니다. [낮은 일치율](../features/addressable-audiences.md#low-match-rates) 에 대한 [!UICONTROL destinations].

## 의 날짜 범위 [!UICONTROL Addressable Audiences] 및 [!UICONTROL Destinations] {#date-ranges}

사용 가능한 날짜 범위 및 보고서에 있는 각 간격에서 데이터가 어떻게 초과되는지에 대해서는 아래 섹션을 참조하십시오. [!UICONTROL Addressable Audience] 또는 [!UICONTROL Destination].

## 사용 가능한 날짜 범위 및 시간대 {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

다음에 대한 보고서 [!UICONTROL Addressable Audiences] 및 [대상](../features/destinations/destinations.md) 동일한 날짜 범위 간격을 사용합니다. 날짜 범위 옵션은 다음과 같습니다.

* [!UICONTROL Last 1 Day] (이 간격은 이전 24시간 동안 자정부터 자정까지 계속됩니다. 실시간 또는 현재 시간 지표가 아닙니다.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

모든 날짜 및 날짜 범위는 [!DNL UTC] 시간대. 다음을 참조하십시오 [Audience Manager의 시간대](../reference/aam-time-zones.md).

## 날짜 범위 간격의 데이터 {#date-range-intervals}

다음 [!UICONTROL Addressable Audience] 및 [!UICONTROL Destination] 지표는 선택한 시간 간격에 대한 고유 사용자 수를 반환합니다. 예를 들어 방문자는 사이트에 여러 번 방문하더라도 한 번만 카운트됩니다. 첫 번째 방문은 고유한 방문이며 기록됩니다. 이후 방문은 재방문이며 고유하지 않으므로 계산되지 않습니다.

날짜 범위에는 선택한 시간 간격 이상의 데이터가 포함됩니다. 그리고 시간이 경과함에 따라 데이터가 각 보고서 간격을 벗어납니다. 예를 들어 을 선택한 후 2명의 방문자가 보인다고 가정해 보겠습니다. [!UICONTROL Last 30 Days] 옵션을 선택합니다. 보고서에서 이들 방문자는 다음과 같습니다.

* *다음이 됨:* 더 긴 시간 간격(60일, 90일 및 라이프타임)으로 반환된 결과에 포함됩니다.
* *다음이 아님* 앞에 오는 짧은 간격에 포함됨 [!UICONTROL Last 30 Day] 옵션(현재, 7일 및 14일).

그리고 31일째에는 이러한 방문자가 60일, 90일에만 표시됩니다. [!UICONTROL Lifetime] 결과. 그들은 30일 간격을 두고 노화했다. 방문자는 다음 기간 이후에 방문하지 않습니다. [!UICONTROL Lifetime] 간격.

## [!UICONTROL Addressable Audiences] 지표 {#addressable-audience-metrics}

이 섹션에서는 다음에서 제공하는 측정 단위 유형에 대해 설명합니다. [!UICONTROL Addressable Audiences].

### 고객 수준 지표 {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

이러한 지표는 방문자가 사이트를 방문하거나 인바운드 데이터 파일을 로 보낼 때 실현된 트레이트에 대한 데이터를 반환합니다 [!DNL Audience Manager]. 이 지표는 계정의 대상 크기를 종합적으로 보여 줍니다.

| 지표 | 설명 |
|---|---|
| [!UICONTROL Customer Addressable Audience] | 다음 중 하나를 실현한 장치 겹치기 수: [!UICONTROL rule-based trait] 또는 [!UICONTROL onboarded trait] 전환 확인 기간과 동기화 시간에 관계없이 선택한 대상과 ID가 동기화되는 디바이스 동안.<br><br>이 지표는 다음과 같은 장치를 나타냅니다.<ul><li>다음 중 하나를 인식함: [!UICONTROL rule-based] 또는 [!UICONTROL onboarded trait] 전환 확인 기간 동안 `AND`</li><li>선택한 과(와) ID 동기화 [!UICONTROL destination] 동기화 시간과 상관없이</li></ul> |
| [!UICONTROL Customer Total Audience] | 다음 중 하나를 실현한 장치 수: [!UICONTROL rule-based trait] 속성 또는 [!UICONTROL onboarded trait] 전환 확인 기간 동안 오프라인 파일에서 |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] 백분율로 표시됩니다. |

### 세그먼트 수준 일치 지표 {#segment-level-metrics}

이 지표는 다음에 대한 데이터를 반환합니다. [!UICONTROL segment] 멤버십. 이렇게 하면 각 사용자에 대한 대상 크기를 보다 세부적이고 정확하게 볼 수 있습니다. [!UICONTROL segments].

>[!NOTE]
>
>다음에서 전환 확인 기간이 적용되는 방식 [!UICONTROL segment] 수준은 고객 수준과 다릅니다. 방문자가 사이트를 방문하여 다음을 실현할 수 있습니다. [!UICONTROL trait] 10일 전, 그들은 [!UICONTROL segment] 이후 및 이(가) [!UICONTROL segment] 2일 전입니다. 7일 룩백이 적용되면 이 방문자는 다음에서 계산됩니다. [!UICONTROL segment] 레벨이지만 고객 레벨에는 없습니다.

| 지표 | 설명 |
|---|---|
| [!UICONTROL Segment Addressable Audience] | 에 속한 사용자의 수입니다. [!UICONTROL segment] 보고서 전환 확인 기간 동안 및 를 사이트에 활성 ID 동기화가 있습니다. 를 통해 세그먼트에는 자체 자사 데이터와 제2자 데이터, 타사 데이터가 포함될 수 있습니다. [!UICONTROL traits] 다음에 획득됨 [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>팁: 1일 룩백 기간과 함께 사용할 경우 이 지표를 통해 의 현재 상태를 파악할 수 있습니다. [!UICONTROL segments]. 이유는 다음과 같습니다. [!UICONTROL Segment Addressable Audience] 지표는 에 머문 사용자를 나타냅니다. [!UICONTROL segment] 전날 내내 다음과 같은 사실과 결합 [!DNL Audience Manager] 새로 고침 [!UICONTROL Addressable Audiences] 일별로, 이 지표와 전환 확인 기간을 결합하면 의 최신 스냅샷을 제공합니다. [!UICONTROL segments]. |
| [!UICONTROL Total Segment Population] | 의 구성원이었던 모든 장치의 수입니다. [!UICONTROL segment] 보고서 전환 확인 기간 동안. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] 백분율로 표시됩니다. |

### 플랫폼 수준 지표 {#platform-level-metrics}

이 지표는 모든 활동에 대해 수집된 활동의 데이터를 반환합니다 [!DNL Audience Manager] 고객. 집계된 내용과 비교하여 고객 대상을 더 넓게 볼 수 있습니다 [!DNL Audience Manager] 고객.

| 지표 | 설명 |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | 모든 장치와 상호 작용한 모든 장치의 수 [!DNL Audience Manager] 보고서 전환 확인 기간 동안 플랫폼 수준에서 고객이 선택한 항목과 일치할 수 있음 [!UICONTROL destination]. <br><br>이 지표는 다음을 보여주므로 유용합니다.<ul><li>크기 [!UICONTROL total addressable audience] that [!DNL Audience Manager] 특정 타겟팅 대상에 도달할 수 있습니다.</li><li>크기가 어느 정도죠 [!DNL Audience Manager] 프로필 풀은 타겟팅 플랫폼 및 대상자 크기에 사용됩니다.</li></ul> |

## 비교 [!UICONTROL Customer] 및 [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

다음 항목을 비교해서는 안 됩니다. [!UICONTROL Customer Addressable Audience] 및 [!UICONTROL Segment Addressable Audience] 지표 를 사용하여 둘 중 하나가 다른 하나보다 중요한지 확인할 수 있습니다. 이러한 지표는 별도의 서로 다른 독립적인 지표입니다. 전술한 정의들에서 설명된 바와 같이, 이들 각각은 상이한 데이터 세트들로부터 도출된다. 이 경우 한 지표가 다른 지표보다 큰 경우 결론을 도출하지 않아야 합니다. 이를 비교할 때 말할 수 있는 것은 다음과 같습니다.

* [!UICONTROL Customer Addressable Audiences] 은(는) 다음을 기반으로 합니다. [!UICONTROL trait] 실현 *자사 데이터를 위한*. 이 지표는 데이터 파트너와의 통합에 대한 광범위하고 포괄적인 보기를 제공합니다.

* [!UICONTROL Segment Addressable Audiences] 세그먼트 자격을 기반으로 함 *자사 데이터와 제2자 데이터, 타사 데이터의 경우*. 이 지표는 다음에 대한 세부적이고 더 정확한 보기를 제공합니다. [!UICONTROL addressable audiences] 타깃팅 플랫폼에서.

## 에 대한 낮은 일치율의 원인 [!UICONTROL Addressable Audiences] {#low-match-rates}

낮음에 대한 책임이 있는 일반적인 요소 [!UICONTROL Addressable Audience] 보고된 숫자의 일치율 또는 불일치.

| 원인 | 설명 |
|---|---|
| 모바일 트래픽 | 가장 [!UICONTROL server-to-server] 통합은 서드파티가 지원하는 동기화 프로세스에 의존합니다. [!DNL cookies]. 그러나 모바일 환경에서는 서드파티를 사용하지 않습니다 [!DNL cookies]. 그 결과 [!UICONTROL Addressable Audiences] 숫자는 다음에 비해 적어 보일 수 있습니다. [!UICONTROL segment] 크기. <br><br>2018년 1월부터는 같은 시각에서 모바일 대상을 활성화할 수 있습니다 [!DNL Google] 및 [!DNL Adobe Advertising Cloud] 대상 설정됨 [!UICONTROL cookie-based] 대상. 반면에 다음을 보낼 수 있습니다. [!UICONTROL segments] 결합된 것 [!DNL cookie] 및 모바일 ID 멤버십을 [!DNL Google] 및 [!DNL Advertising Cloud] 대상, 다음 사항에 유의하십시오. [!UICONTROL Addressable Audiences] 다음 사이의 겹침만 표시 [!DNL cookie] ID 및 대상. [!DNL Audience Manager] 는 모바일 대상의 100%를 [!UICONTROL destinations], 하지만 모바일 대상자는 [!UICONTROL Addressable Audience] 지표. <br><br>**참고**: 예를 들어 [!UICONTROL segment] 인구가 100만 명이죠 매핑하면 [!UICONTROL segment] (으)로 [!DNL Google] 또는 [!DNL Adobe Advertising Cloud] 대상, 다음 항목이 표시될 수 있습니다. [!UICONTROL Addressable Audience] / 700,000 개의 디바이스 및 [!UICONTROL Match Rate] 70% 700,000명의 회원은 다음과 같이 구성되어 있다. [!DNL cookie] 와 ID 동기화가 있는 ID [!UICONTROL destination]. 사용자 [!UICONTROL Addressable Audience] 주소 지정 가능한 모바일 ID가 이 지표에 표시되지 않으므로 실제로 이 값은 훨씬 더 높을 수 있습니다. |
| [!DNL Safari] 트래픽 | [!DNL Safari] 서드파티 차단 [!DNL cookies]. 이렇게 하면 [!DNL Audience Manager] ID를 와 동기화의 [!UICONTROL destination]. 의 도입으로 [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/), 다음을 예상할 수 있습니다. [!UICONTROL addressable audiences] 포함하지 않음 [!DNL Safari] 사용자. |
| 추적된 미디어 노출 횟수 | 광고 서버 모범 사례로 인해 광고 태그 내에서는 ID 동기화가 수행되지 않습니다. 대량의 오프사이트 광고를 수행하는 고객은 이러한 환경의 서드파티 통합에 사용자를 동기화하지 않습니다. 또한, 많은 양의 수집된 미디어 노출 데이터가 감소할 수 있습니다 [!UICONTROL addressable audience] 숫자. |

## 문제 해결 [!UICONTROL Addressable Audiences] {#troubleshooting}

일치율 표시 외에도 다음을 사용할 수도 있습니다 [!UICONTROL Addressable Audiences] 문제 해결 도구로 사용하십시오.

예를 들어 세그먼트를 로 보낸다고 가정해 보겠습니다 [!UICONTROL destination] 및 [!UICONTROL destination] 낮은 보고 번호를 표시합니다. 확인 중 [!UICONTROL Addressable Audience] 기술적인 문제이거나 일치율이 낮은 경우 결과가 표시됩니다. 낮은 일치율은 다음을 보여줍니다. [!UICONTROL destination] 은(는) 선택한 세그먼트에 대해 훌륭하지 않습니다. 하지만, [!UICONTROL total addressable audience] 다음 사이의 숫자: [!DNL Audience Manager] 및 [!UICONTROL destination] 통합, 동기화 또는 기타 기술 문제를 나타냅니다. 이러한 경우 계정 관리자에게 문의하십시오.
