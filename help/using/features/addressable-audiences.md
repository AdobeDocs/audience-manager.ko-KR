---
description: 어드레서블 대상 기능 및 사용 사례에 대한 개요입니다.
keywords: DIL
seo-description: 어드레서블 대상 기능 및 사용 사례에 대한 개요입니다.
seo-title: 대응 가능 대상
solution: Audience Manager
title: 대응 가능 대상
topic: DIL API
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: Match Rates
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1824'
ht-degree: 1%

---


# [!UICONTROL Addressable Audiences] {#addressable-audiences}

기능 및 사용 사례에 대한 [!UICONTROL Addressable Audience] 개요입니다.

##  [!UICONTROL Addressable Audience]? {#addressable-audience-description}

이 [!UICONTROL Addressable Audiences] 기능은 데이터를 수집하는 모든 속성에서 표시되는 대상 간 [!DNL Audience Manager] 과 선택한 대상 간에 겹치는 것을 보여줍니다. 이 개념을 이해하는 데 도움이 되도록 아래 일러스트레이션을 살펴보십시오. 각 원 간의 겹치는 서로 다른 유형의 지정 가능 대상을 나타냅니다.

![](assets/addressableAudienceVenn.png)


| 지표 | 설명 |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] for [!UICONTROL Destination] | 보고서 룩백 기간 동안 플랫폼 수준에서 모든 [!DNL Audience Manager] 고객과 상호 작용했으며 사용자가 선택한 장치와 일치할 수 있는 모든 장치의 수입니다 [!UICONTROL destination]. <br><br>이 지표는 다음을 보여주므로 유용합니다. <ul><li>특정 타깃팅에서 도달할 수 [!UICONTROL addressable audience] 있는 총 [!DNL Audience Manager] 크기 [!UICONTROL destination].</li><li>타깃팅 플랫폼과 [!DNL Audience Manager] 고객의 크기에 대한 프로필 풀의 크기</li></ul> |
| [!UICONTROL Customer Total Audience] | 룩백 창 동안 속성 또는 오프라인 파일 [!UICONTROL rule-based trait] 에서 발생한 장치 [!UICONTROL onboarded trait] 의 수입니다. |
| [!UICONTROL Addressable Audience Match Rate] | 다시 보기 창에서 한 번 또는 한 번 [!UICONTROL rule-based trait] 의 장치 [!UICONTROL onboarded trait] 가 겹치는 장치 및 동기화 시간에 관계없이 선택한 장치와 ID를 동기화하는 장치 [!UICONTROL destination] 의 수입니다.<br><br>이 지표는 다음과 같은 장치를 나타냅니다.<ul><li>Have realized either a [!UICONTROL rule-based] or an [!UICONTROL onboarded trait] during the look-back window `AND`</li><li>Have an ID sync with the chosen [!UICONTROL destination] regardless of the time of syncs.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ? [!UICONTROL Customer Total Audience] 백분율로 표시됨 |
| [!UICONTROL Total Segment Population] | 보고서 검색 기간 [!UICONTROL segment] 동안 사용자의 멤버였던 모든 장치의 수입니다. |
| [!UICONTROL Segment Addressable Audience] | The number of users who have belonged to the [!UICONTROL segment] during the report look-back period and have an active ID sync on your site. [!UICONTROL Segments] Audience Marketplace에서 얻은 자신의 퍼스트 파티 데이터 및 세컨드 파티 데이터 [!UICONTROL traits] 를 포함할 수 [있습니다](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>팁: 1일 룩백 기간과 함께 사용하는 경우 이 지표를 사용하여 사용자의 현재 상태를 이해할 수 있습니다 [!UICONTROL segments]. 이는 지표가 전날 동안 있었던 사용자 [!UICONTROL Segment Addressable Audience] [!UICONTROL segment] 를 나타내기 때문입니다. 이 지표를 [!DNL Audience Manager] 매일 새로 고침하고 이 지표와 룩백 기간을 결합하면 최신 스냅샷을 제공할 수 [!UICONTROL Addressable Audiences] [!UICONTROL segments]있습니다. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ? [!UICONTROL Total Segment Population] 백분율로 표시됨 |

## [!UICONTROL Addressable Audiences] 인터페이스 {#addressable-audience-interface}

이 [!UICONTROL Addressable Audience] 기능은 이 추상적인 개념을 수량화할 수 있는 데이터로 바꿉니다. 이 기능 [!DNL Audience Manager]은 탭 형식의 숫자 데이터와 함께 한 눈에 정보를 제공하는 데이터 시각화와 겹치는 대상을 표시합니다.

[!UICONTROL Addressable Audiences] 에 있습니다 **[!UICONTROL Audience Data > Destinations]**. 대응 가능 대상 지표 **[!UICONTROL Integrated Platforms > Device-Based]** 를 보려면 선택합니다.

![](assets/addressable-audiences-landing.png)

랜딩 페이지에서 볼 수 있는 세 가지 지표는 [!UICONTROL Addressable Audiences] 다음과 같습니다.

| 지표 | 설명 |
---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | 이 지표는 지난 30일 동안의 [!UICONTROL Customer Addressable Audience] (위 표에 설명됨) *을 나타냅니다.* |
| **[!UICONTROL Match Rate]** | 이 지표는 지난 30일 [!UICONTROL Addressable Audience Match Rate] 동안 위 표 **&#x200B;에 설명된 대로 나타냅니다. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | 보고서 룩백 기간 동안 플랫폼 수준에서 모든 [!DNL Audience Manager] 고객과 상호 작용했으며 이와 일치할 수 있는 모든 장치의 [!UICONTROL destination]수입니다. 자세한 내용은 [Platform 수준](/help/using/features/addressable-audiences.md#platform-level-metrics) 지표를 참조하십시오. |

주소 지정 가능한 대상 데이터를 보려면 [!UICONTROL server-to-server destination] 의 이름을 클릭합니다. 이 기능은 [!UICONTROL server-to-server destinations] 전용 데이터를 반환하고 액세스 권한에는 관리자 권한이 필요합니다.

![](assets/addressableAudiences.png)

이 데이터를 검토하면 다음과 같은 이점을 얻을 수 있습니다.

* **예측 및 계획:** [!UICONTROL Segment Addressable Audience] 데이터를 사용하면 대상 타깃팅 및 활성화를 위해 대상으로 전송하려는 세그먼트를 세부적으로 파악할 수 있습니다.

* **성능 평가:** 이 [!UICONTROL Addressable Audiences] 기능은 문제 해결 툴이기도 합니다. 캠페인 성과를 검토하고 캠페인 도달 범위를 이해하며, 예상한 결과가 표시되지 않는 경우 타깃팅/활성화 파트너와 교차 확인할 수 있습니다.

### 제3자 데이터와 일치율의 영향

고객 확보를 위해 타사 데이터를 구매하기 전에 고객은 다른 데이터 제공업체와 겹치는 사실을 확인할 수 있습니다. 이를 통해 새로운 데이터를 구매하기 전에 현명한 의사 결정을 내릴 수 있습니다. 구입한 타사 데이터에 대한 ID 동기화는 데이터 겹치뿐만 아니라 타사 제공업체의 다른 모든 [!DNL Audience Manager] 고객과의 발자국에도 의존합니다. 컨설턴트가 고객의 관심사와 연관성 있는 추가 데이터 소스를 파악하여 잠재 캠페인을 최적화할 수 있도록 도움을 줄 수 있습니다. [!DNL Adobe]

### 모바일 사용자 및 일치 비율

서드파티 [!DNL Safari] 가 없는 모바일 앱 사용자를 연결하려고 할 때 차이가 [!DNL cookies] 있습니다. 따라서 동기화된 타사 ID만 미디어 배달 로그에 제공되므로 일부 파트너 [!DNL Adobe] 와 사용자를 동기화하기가 [!DNL cookies] 어렵습니다. 이것이 여러분이 여러분의 [낮은 성냥을](../features/addressable-audiences.md#low-match-rates) 볼 수 있는 이유입니다 [!UICONTROL destinations].

## 날짜 범위( 및) [!UICONTROL Addressable Audiences] 에서 [!UICONTROL Destinations] {#date-ranges}

사용 가능한 날짜 범위와 보고서의 각 간격에서 데이터 사용 방법을 [!UICONTROL Addressable Audience] 또는 [!UICONTROL Destination]아래 섹션을 참조하십시오.

## 사용 가능한 날짜 범위 및 시간대 {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

사용자 [!UICONTROL Addressable Audiences] 및 [대상에](../features/destinations/destinations.md) 대한 보고서는 동일한 날짜 범위 간격을 사용합니다. 날짜 범위 옵션은 다음과 같습니다.

* [!UICONTROL Last 1 Day] (이 간격은 이전 24시간 기간의 자정부터 자정까지 실행됩니다. 실시간 또는 현재 시간 지표가 아닙니다.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

모든 날짜 및 날짜 범위는 [!DNL UTC] 표준 시간대에서 설정됩니다. See [Time Zones in Audience Manager](../reference/aam-time-zones.md).

## 날짜 범위 간격의 데이터 {#date-range-intervals}

및 지표 [!UICONTROL Addressable Audience] [!UICONTROL Destination] 는 선택한 시간 간격에 대한 고유한 사용자 수를 반환합니다. 예를 들어 방문자가 사이트에 여러 번 오더라도 한 번만 카운트됩니다. 첫 번째 방문은 고유한 방문으로 기록됩니다. 이후 방문은 재방문되며 고유하지 않기 때문에 카운트되지 않습니다.

날짜 범위에는 선택한 시간 간격 또는 이전 기간의 데이터가 포함됩니다. 또한 데이터가 시간이 경과함에 따라 각 보고서 간격에서 길어질 수 있습니다. 예를 들어 [!UICONTROL Last 30 Days] 옵션을 선택한 후 2명의 방문자가 있다고 가정합니다. 보고서에서 이러한 방문자는 다음과 같습니다.

* *더 긴 시간 간격(60일, 90일 및 라이프타임)이 반환되는 결과에 포함됩니다* .
* *옵션 앞에 오는 짧은 간격(현재, 7일 및 14일)에 포함되지* 않습니다 [!UICONTROL Last 30 Day] .

그리고 31일에 이러한 방문자는 60일, 90일, 그리고 [!UICONTROL Lifetime] 결과만 나타납니다. 그들은 30일 간격을 벗어나서 늙었다. 방문자는 [!UICONTROL Lifetime] 시간 간격을 벗어나지 않습니다.

## [!UICONTROL Addressable Audiences] 지표 {#addressable-audience-metrics}

이 섹션에서는 사용자가 제공하는 지표 유형을 설명합니다 [!UICONTROL Addressable Audiences].

### 고객 수준 지표 {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

이러한 지표는 방문자가 사이트를 방문하거나 인바운드 데이터 파일을 보낼 때 발생한 트레이트에 대한 데이터를 반환합니다 [!DNL Audience Manager]. 이러한 지표는 계정에 대한 대상 규모의 포괄적인 보기를 제공합니다.

| 지표 | 설명 |
|---|---|
| [!UICONTROL Customer Addressable Audience] | 다시 보기 창에서 한 번 또는 한 번 [!UICONTROL rule-based trait] [!UICONTROL onboarded trait] 의 디바이스를 인식한 장치 및 동기화된 시간에 상관없이 ID를 선택한 대상과 동기화하는 장치의 오버랩 수입니다.<br><br>이 지표는 다음과 같은 장치를 나타냅니다.<ul><li>Have realized either a [!UICONTROL rule-based] or an [!UICONTROL onboarded trait] during the look-back window `AND`</li><li>Have an ID sync with the chosen [!UICONTROL destination] regardless of the time of syncs.</li></ul> |
| [!UICONTROL Customer Total Audience] | 룩백 창 동안 속성 또는 오프라인 파일 [!UICONTROL rule-based trait] 에서 발생한 장치 [!UICONTROL onboarded trait] 의 수입니다. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ? [!UICONTROL Customer Total Audience] 백분율로 표시됨 |

### 세그먼트 수준 일치 지표 {#segment-level-metrics}

이러한 지표는 [!UICONTROL segment] 멤버십에 대한 데이터를 반환합니다. 이러한 기능을 사용하면 각 고객의 규모를 보다 세부적이고 정확하게 파악할 수 있습니다 [!UICONTROL segments].

>[!NOTE]
>
>룩백 창이 레벨에서 적용되는 방법은 [!UICONTROL segment] 고객 수준에서 적용되는 방법과 다릅니다. 방문자는 사이트를 방문하여 [!UICONTROL trait] 10일 전에 그 사이트를 실현할 수 있으며, 그 [!UICONTROL segment] 이후 자격을 갖추고 [!UICONTROL segment] 2일 전에 결석할 수 있습니다. 7일 룩백이 적용되면 이러한 방문자는 [!UICONTROL segment] 수준에서 계산되지만 고객 수준에서는 계산되지 않습니다.

| 지표 | 설명 |
|---|---|
| [!UICONTROL Segment Addressable Audience] | The number of users who have belonged to the [!UICONTROL segment] during the report look-back period and have an active ID sync on your site. Segments can include your own first-party data and second party and third party data, via [!UICONTROL traits] acquired in the [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>팁: 1일 룩백 기간과 함께 사용하는 경우 이 지표를 사용하여 사용자의 현재 상태를 이해할 수 있습니다 [!UICONTROL segments]. 이는 지표가 전날 동안 있었던 사용자 [!UICONTROL Segment Addressable Audience] [!UICONTROL segment] 를 나타내기 때문입니다. 이 지표를 [!DNL Audience Manager] 매일 새로 고침하고 이 지표와 룩백 기간을 결합하면 최신 스냅샷을 제공할 수 [!UICONTROL Addressable Audiences] [!UICONTROL segments]있습니다. |
| [!UICONTROL Total Segment Population] | 보고서 검색 기간 [!UICONTROL segment] 동안 사용자의 멤버였던 모든 장치의 수입니다. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ? [!UICONTROL Total Segment Population] 백분율로 표시됨 |

### Platform 수준 지표 {#platform-level-metrics}

이 지표는 모든 고객 [!DNL Audience Manager] 에서 수집된 활동에 대한 데이터를 반환합니다. 이러한 고객 접점은 집계된 [!DNL Audience Manager] 고객과 비교하여 고객의 전체 상황을 파악할 수 있습니다.

| 지표 | 설명 |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | 보고서 룩백 기간 동안 플랫폼 수준에서 모든 [!DNL Audience Manager] 고객과 상호 작용했으며 사용자가 선택한 장치와 일치할 수 있는 모든 장치의 수입니다 [!UICONTROL destination]. <br><br>이 지표는 다음을 보여주므로 유용합니다.<ul><li>특정 타깃팅 대상에 도달할 수 [!UICONTROL total addressable audience] 있는 [!DNL Audience Manager] 크기.</li><li>타깃팅 플랫폼과 [!DNL Audience Manager] 고객의 크기에 대한 프로필 풀의 크기</li></ul> |

## 비교 [!UICONTROL Customer] 및 [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

지표 [!UICONTROL Customer Addressable Audience] 와 [!UICONTROL Segment Addressable Audience] 지표를 비교하여 값이 다른 지표보다 더 중요한지 판단해서는 안 됩니다. 이러한 지표는 별개이고, 서로 다르며, 독립적인 지표입니다. 위의 정의에 설명된 것처럼 각 데이터 세트는 서로 다른 데이터 세트에서 파생됩니다. 따라서 한 지표가 다른 지표보다 큰 경우 어떤 결론도 도출하지 않아야 합니다. 이것들을 비교할 때 당신이 말할 수 있는 것은 다음과 같습니다.

* [!UICONTROL Customer Addressable Audiences] 는 자사 데이터 [!UICONTROL trait] 에 대한 *관계를 기반으로 합니다*. 이 지표는 데이터 파트너와의 통합에 대한 광범위하고 포괄적인 보기를 제공합니다.

* [!UICONTROL Segment Addressable Audiences] 는 자사 데이터 *에 대한 세그먼트 자격 조건과 제휴 데이터 및 타사 데이터를 기반으로 합니다*. 이 지표는 타깃팅 플랫폼에서 사용자 [!UICONTROL addressable audiences] 의 상세 보기를 제공합니다.

## 낮은 일치 비율의 원인 [!UICONTROL Addressable Audiences] {#low-match-rates}

보고된 숫자의 낮은 [!UICONTROL Addressable Audience] 일치율 또는 불일치를 책임지는 일반적인 요소입니다.

| 원인 | 설명 |
|---|---|
| 모바일 트래픽 | 대부분의 [!UICONTROL server-to-server] 통합은 서드파티의 동기화 프로세스를 기반으로 합니다 [!DNL cookies]. 그러나 모바일 환경에서는 타사 솔루션을 사용하지 않습니다 [!DNL cookies]. 그 결과, 여러분의 [!UICONTROL Addressable Audiences] 숫자는 [!UICONTROL segment] 크기에 비해 낮은 것 같습니다. <br><br>2018년 1월 현재 대상 [!DNL Google] 에 대해 설정된 동일한 및 [!DNL Adobe Advertising Cloud] 대상에서 모바일 대상을 활성화할 수 [!UICONTROL cookie-based] 있습니다. 즉, 결합 [!UICONTROL segments] 및 모바일 ID 멤버십 [!DNL cookie] 과 함께 [!DNL Google] 및 대상에 보낼 수 [!DNL Advertising Cloud] 있으며, ID와 대상 간 [!UICONTROL Addressable Audiences] 에 겹치는 부분만 표시된다는 [!DNL cookie] 점을 염두에 두십시오. [!DNL Audience Manager] 은 모바일 대상의 100%를 다음으로 보내지만 모바일 [!UICONTROL destinations]대상은 지표로 측정되지 [!UICONTROL Addressable Audience] 않습니다. <br><br>**참고&#x200B;**: 예를 들어 인구[!UICONTROL segment]가 1,000,000인 a를 예로 들면, 이[!UICONTROL segment]를[!DNL Google]또는[!DNL Adobe Advertising Cloud]대상에 매핑하면 700,000개의 장치[!UICONTROL Addressable Audience]와 70%[!UICONTROL Match Rate]의 장치를 볼 수 있습니다. 700,000의 멤버십은 ID가 동기화된 ID로[!DNL cookie][!UICONTROL destination]구성됩니다. 어드레서블 모바일 ID는 이 지표에 나타나지 않으므로 실제 더 높은[!UICONTROL Addressable Audience]것으로 간주할 수 있습니다. |
| [!DNL Safari] 트래픽 | [!DNL Safari] 타사 블록 [!DNL cookies]을 차단합니다. 이렇게 하면 ID가 ID와 동기화되지 않습니다 [!DNL Audience Manager] [!UICONTROL destination]. ITP [2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/)출시로 사용자는 [!UICONTROL addressable audiences] 사용자를 포함하지 [!DNL Safari] 않을 것으로 예상할 수 있습니다. |
| 추적된 미디어 노출 수 | 광고 서버 우수 사례로 인해 광고 태그 내에 ID 동기화가 수행되지 않습니다. 오프사이트 광고를 많이 하는 고객은 해당 환경의 타사 통합에 사용자를 동기화하지 않습니다. 또한 대량의 미디어 노출 수 데이터를 수집하면 [!UICONTROL addressable audience] 숫자를 줄일 수 있습니다. |

## 문제 해결 [!UICONTROL Addressable Audiences] {#troubleshooting}

일치 비율을 표시하는 것 외에도 문제 해결 도구 [!UICONTROL Addressable Audiences] 로 사용할 수도 있습니다.

예를 들어 세그먼트를 A로 전송하면 [!UICONTROL destination] 보고 수가 [!UICONTROL destination] 적다고 가정해 봅시다. 이 [!UICONTROL Addressable Audience] 문제가 기술적 문제인지 또는 낮은 일치율의 경우인지 결과를 확인하면 표시됩니다. 낮은 일치 비율은 선택한 세그먼트에 대해 그리 [!UICONTROL destination] 좋지 않다는 것을 보여줍니다. 하지만, 숫자 [!UICONTROL total addressable audience] 와 [!DNL Audience Manager] 의 차이는 통합, 동기화 또는 기타 기술 문제를 [!UICONTROL destination] 나타냅니다. 이러한 경우 계정 관리자에게 문의하십시오.
