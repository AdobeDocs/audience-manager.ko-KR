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
source-wordcount: '1831'
ht-degree: 0%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

[!UICONTROL Addressable Audience] 기능 및 사용 사례에 대한 개요입니다.

## [!UICONTROL Addressable Audience]이란? {#addressable-audience-description}

[!UICONTROL Addressable Audiences] 기능은 [!DNL Audience Manager]에서 데이터를 수집하는 모든 속성과 선택한 대상 간에 표시되는 대상 간의 겹침을 보여 줍니다. 이 개념을 이해하는 데 도움이 되도록 아래 그림을 살펴보십시오. 각 원 간의 겹침은 서로 다른 유형의 대응 가능 대상을 나타냅니다.

![](assets/addressableAudienceVenn.png)


| 지표 | 설명 |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience]에 대한 [!UICONTROL Destination] | 보고서 전환 확인 기간 동안 플랫폼 수준의 모든 [!DNL Audience Manager] 고객과 상호 작용했으며 선택한 [!UICONTROL destination]과(와) 일치할 수 있는 모든 장치의 개수입니다. <br><br>이 지표는 다음을 표시하므로 유용합니다. <ul><li>[!UICONTROL addressable audience]이(가) 특정 타깃팅 [!DNL Audience Manager]에 도달할 수 있는 총 [!UICONTROL destination]의 크기입니다.</li><li>타깃팅 플랫폼에 대한 [!DNL Audience Manager] 프로필 풀의 크기와 대상 크기입니다.</li></ul> |
| [!UICONTROL Customer Total Audience] | 전환 확인 기간 동안 속성의 [!UICONTROL rule-based trait] 또는 오프라인 파일의 [!UICONTROL onboarded trait]을(를) 실현한 장치 수입니다. |
| [!UICONTROL Customer Addressable Audience] | 전환 확인 기간 동안 [!UICONTROL rule-based trait] 또는 [!UICONTROL onboarded trait]을(를) 실현한 장치와 동기화 시간에 관계없이 선택한 [!UICONTROL destination]과(와) ID 동기화가 있는 장치의 겹침 수입니다.<br><br>이 지표는 다음과 같은 장치를 나타냅니다.<ul><li>전환 확인 기간 [!UICONTROL rule-based] 동안 [!UICONTROL onboarded trait] 또는 `AND`을(를) 실현했습니다.</li><li>동기화 시간과 관계없이 선택한 [!UICONTROL destination]과(와) ID를 동기화합니다.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience]이(가) 백분율로 표시되었습니다. |
| [!UICONTROL Total Segment Population] | 보고서 전환 확인 기간 동안 [!UICONTROL segment]의 회원이었던 모든 장치의 개수입니다. |
| [!UICONTROL Segment Addressable Audience] | 보고서 전환 확인 기간 동안 [!UICONTROL segment]에 속하고 해당 사이트에서 활성 ID 동기화를 보유한 사용자의 수입니다. [!UICONTROL Segments]은(는) [!UICONTROL traits]Audience Marketplace[에서 획득한 &#x200B;](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)을(를) 통해 고유한 자사 데이터와 제2자 데이터 및 타사 데이터를 포함할 수 있습니다. <br><br>팁: 1일 전환 확인 기간과 함께 사용할 경우 이 지표를 통해 [!UICONTROL segments]의 현재 상태를 이해할 수 있습니다. 이는 [!UICONTROL Segment Addressable Audience] 지표가 전날 내내 [!UICONTROL segment]에 있었던 사용자를 나타내기 때문입니다. [!DNL Audience Manager]이(가) 매일 [!UICONTROL Addressable Audiences]을(를) 새로 고침한다는 사실과 이 지표와 전환 확인 기간을 결합하면 [!UICONTROL segments]의 최신 스냅숏이 제공됩니다. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population]이(가) 백분율로 표시되었습니다. |

## [!UICONTROL Addressable Audiences] 인터페이스 {#addressable-audience-interface}

[!UICONTROL Addressable Audience] 기능을 사용하면 이 추상 개념을 수량화할 수 있는 데이터로 변환할 수 있습니다. [!DNL Audience Manager]에서 이 기능은 표 형식의 숫자 데이터와 함께 요약 정보를 제공하는 데이터 시각화와 대상이 겹치게 표시됩니다.

[!UICONTROL Addressable Audiences]이(가) **[!UICONTROL Audience Data > Destinations]**&#x200B;에 있습니다. 주소 지정 가능한 대상 지표를 보려면 **[!UICONTROL Integrated Platforms > Device-Based]**&#x200B;을(를) 선택하십시오.

![](assets/addressable-audiences-landing.png)

[!UICONTROL Addressable Audiences] 랜딩 페이지에서 볼 수 있는 세 가지 지표는 다음을 나타냅니다.

| 지표 | 설명 |
|---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | 이 지표는 지난 30일 동안의 [!UICONTROL Customer Addressable Audience]&#x200B;(위 표에 설명됨) *을(를) 나타냅니다.* |
| **[!UICONTROL Match Rate]** | 이 지표는 지난 30일 동안의 [!UICONTROL Addressable Audience Match Rate]&#x200B;(위 표에 설명됨) *을(를) 나타냅니다*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | 보고서 전환 확인 기간 동안 플랫폼 수준의 모든 [!DNL Audience Manager] 고객과 상호 작용했으며 이 [!UICONTROL destination]과(와) 일치할 수 있는 모든 장치의 수입니다. 자세한 내용은 [플랫폼 수준 지표](/help/using/features/addressable-audiences.md#platform-level-metrics)를 참조하십시오. |

주소 지정 가능한 대상 데이터를 보려면 [!UICONTROL server-to-server destination]의 이름을 클릭하십시오. 이 기능은 [!UICONTROL server-to-server destinations]에 대한 데이터만 반환하며 액세스하려면 관리자 권한이 필요합니다.

![](assets/addressableAudiences.png)

이 데이터를 검토하면 다음 작업에 도움이 될 수 있습니다.

* **예측 및 계획:** [!UICONTROL Segment Addressable Audience] 데이터를 사용하면 대상 타기팅 및 활성화를 위해 대상으로 보내려는 세그먼트를 더 세부적으로 파악할 수 있습니다.

* **성능 검토:** [!UICONTROL Addressable Audiences] 기능 또한 문제 해결 도구입니다. 이를 통해 캠페인 성과를 검토하고, 캠페인 도달 범위를 이해하고, 예상한 결과가 표시되지 않는 경우 타기팅/활성화 파트너와 상호 확인할 수 있습니다.

### 타사 데이터로 잠재 고객 확보 및 일치율에 대한 영향

대상 획득을 위해 타사 데이터를 구매하기 전에 고객은 다른 데이터 공급자와의 겹침을 확인할 수 있습니다. 이렇게 하면 새 데이터를 구입하기 전에 정보에 입각한 결정을 내리는 데 도움이 됩니다. 구매한 타사 데이터에 대한 ID 동기화는 데이터의 겹침 뿐만 아니라 다른 모든 [!DNL Audience Manager] 고객과의 타사 공급자의 풋프린트에 의존합니다. [!DNL Adobe] 컨설턴트가 잠재 고객 캠페인을 최적화하기 위해 추가 관련 데이터 소스를 식별하는 데 도움을 줄 수 있습니다.

### 모바일 사용자 및 일치율

타사 [!DNL Safari]이(가) 없는 [!DNL cookies] 또는 모바일 앱 사용자를 연결하려고 할 때 간격이 있습니다. 이렇게 하면 동기화된 타사 [!DNL Adobe]에 대한 [!DNL cookies] ID만 미디어 게재 로그에 제공되므로 일부 파트너와 사용자를 동기화하기 어렵습니다. 이 때문에 [에 대해 &#x200B;](../features/addressable-audiences.md#low-match-rates)낮은 일치율[!UICONTROL destinations]이 표시될 수 있습니다.

## [!UICONTROL Addressable Audiences] 및 [!UICONTROL Destinations]의 날짜 범위 {#date-ranges}

사용 가능한 날짜 범위 및 [!UICONTROL Addressable Audience] 또는 [!UICONTROL Destination]에 대한 보고서의 각 간격에서 데이터 사용 시간이 초과되는 방식에 대해서는 아래 섹션을 읽어 보십시오.

## 사용 가능한 날짜 범위 및 시간대 {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

[!UICONTROL Addressable Audiences] 및 [대상](../features/destinations/destinations.md)에 대한 보고서는 동일한 날짜 범위 간격을 사용합니다. 날짜 범위 옵션은 다음과 같습니다.

* [!UICONTROL Last 1 Day]&#x200B;(이 간격은 이전 24시간 동안 자정부터 자정까지 실행됩니다. 실시간 또는 현재 시간 지표가 아닙니다.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

모든 날짜 및 날짜 범위는 [!DNL UTC] 시간대로 설정됩니다. [Audience Manager의 시간대](../reference/aam-time-zones.md)를 참조하세요.

## 날짜 범위 간격의 데이터 {#date-range-intervals}

[!UICONTROL Addressable Audience] 및 [!UICONTROL Destination] 지표가 선택한 시간 간격 동안 고유 사용자 수를 반환합니다. 예를 들어 방문자는 사이트에 여러 번 방문하더라도 한 번만 카운트됩니다. 첫 번째 방문은 고유한 방문이며 기록됩니다. 이후 방문은 재방문이며 고유하지 않으므로 계산되지 않습니다.

날짜 범위에는 선택한 시간 간격 이상의 데이터가 포함됩니다. 그리고 시간이 경과함에 따라 데이터가 각 보고서 간격을 벗어납니다. 예를 들어 [!UICONTROL Last 30 Days] 옵션을 선택하면 2명의 방문자가 표시된다고 가정해 보겠습니다. 보고서에서 이들 방문자는 다음과 같습니다.

* *이(가)*&#x200B;이(가) 더 긴 시간 간격(60일, 90일 및 라이프타임)으로 반환된 결과에 포함됩니다.
* ** 옵션 앞에 오는 짧은 간격에 포함되지 않습니다[!UICONTROL Last 30 Day]&#x200B;(현재, 7일 및 14일).

그리고 31일에는 이러한 방문자가 60일, 90일 및 [!UICONTROL Lifetime]개의 결과에만 표시됩니다. 그들은 30일 간격을 두고 노화했다. 방문자가 [!UICONTROL Lifetime] 간격을 벗어나지 않습니다.

## [!UICONTROL Addressable Audiences] 지표 {#addressable-audience-metrics}

이 섹션에서는 [!UICONTROL Addressable Audiences]에서 제공한 지표 유형을 설명합니다.

### 고객 수준 지표 {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

이 지표는 방문자가 사이트를 방문하거나 인바운드 데이터 파일을 [!DNL Audience Manager]에 보낼 때 실현되는 트레이트에 대한 데이터를 반환합니다. 이 지표는 계정의 대상 크기를 종합적으로 보여 줍니다.

| 지표 | 설명 |
|---|---|
| [!UICONTROL Customer Addressable Audience] | 전환 확인 기간 동안 [!UICONTROL rule-based trait] 또는 [!UICONTROL onboarded trait]을(를) 실현한 장치와 동기화 시간에 관계없이 선택한 대상과 ID 동기화가 있는 장치의 겹침 수입니다.<br><br>이 지표는 다음과 같은 장치를 나타냅니다.<ul><li>전환 확인 기간 [!UICONTROL rule-based] 동안 [!UICONTROL onboarded trait] 또는 `AND`을(를) 실현했습니다.</li><li>동기화 시간과 관계없이 선택한 [!UICONTROL destination]과(와) ID를 동기화합니다.</li></ul> |
| [!UICONTROL Customer Total Audience] | 전환 확인 기간 동안 속성의 [!UICONTROL rule-based trait] 또는 오프라인 파일의 [!UICONTROL onboarded trait]을(를) 실현한 장치 수입니다. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience]이(가) 백분율로 표시되었습니다. |

### 세그먼트 수준 일치 지표 {#segment-level-metrics}

이 지표는 [!UICONTROL segment] 멤버십에 대한 데이터를 반환합니다. 각 [!UICONTROL segments]에 대한 대상 크기를 보다 세밀하게 정확하게 볼 수 있도록 해 줍니다.

>[!NOTE]
>
>[!UICONTROL segment] 수준에서 전환 확인 기간이 적용되는 방식이 고객 수준과 다릅니다. 방문자는 10일 전에 사이트에 와서 [!UICONTROL trait]을(를) 실현할 수 있으며, 이후 [!UICONTROL segment]의 자격을 얻고 2일 전에 [!UICONTROL segment]에서 제외될 수 있습니다. 7일 룩백이 적용되면 이러한 방문자는 [!UICONTROL segment] 수준에서 계산되지만 고객 수준에서는 계산되지 않습니다.

| 지표 | 설명 |
|---|---|
| [!UICONTROL Segment Addressable Audience] | 보고서 전환 확인 기간 동안 [!UICONTROL segment]에 속하고 해당 사이트에서 활성 ID 동기화를 보유한 사용자의 수입니다. 세그먼트는 [!UICONTROL traits]Audience Marketplace[에서 획득한 &#x200B;](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)을(를) 통해 자신의 자사 데이터와 제2자 데이터, 타사 데이터를 포함할 수 있습니다.<br><br>팁: 1일 전환 확인 기간과 함께 사용할 경우 이 지표를 통해 [!UICONTROL segments]의 현재 상태를 이해할 수 있습니다. 이는 [!UICONTROL Segment Addressable Audience] 지표가 전날 내내 [!UICONTROL segment]에 있었던 사용자를 나타내기 때문입니다. [!DNL Audience Manager]이(가) 매일 [!UICONTROL Addressable Audiences]을(를) 새로 고침한다는 사실과 이 지표와 전환 확인 기간을 결합하면 [!UICONTROL segments]의 최신 스냅숏이 제공됩니다. |
| [!UICONTROL Total Segment Population] | 보고서 전환 확인 기간 동안 [!UICONTROL segment]의 회원이었던 모든 장치의 개수입니다. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population]이(가) 백분율로 표시되었습니다. |

### 플랫폼 수준 지표 {#platform-level-metrics}

이 지표는 모든 [!DNL Audience Manager]명의 고객에 대해 수집된 활동에 대한 데이터를 반환합니다. 집계된 [!DNL Audience Manager]명의 고객과 비교하여 고객 대상을 더 넓게 볼 수 있습니다.

| 지표 | 설명 |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | 보고서 전환 확인 기간 동안 플랫폼 수준의 모든 [!DNL Audience Manager] 고객과 상호 작용했으며 선택한 [!UICONTROL destination]과(와) 일치할 수 있는 모든 장치의 개수입니다. <br><br>이 지표는 다음을 표시하므로 유용합니다.<ul><li>[!UICONTROL total addressable audience]이(가) 특정 타깃팅 대상에 도달할 수 있는 [!DNL Audience Manager]의 크기입니다.</li><li>타깃팅 플랫폼에 대한 [!DNL Audience Manager] 프로필 풀의 크기와 대상 크기입니다.</li></ul> |

## [!UICONTROL Customer]과(와) [!UICONTROL Segment Addressable Audiences] 비교 {#comparing-metrics}

[!UICONTROL Customer Addressable Audience]과(와) [!UICONTROL Segment Addressable Audience] 지표를 비교하여 둘 중 하나가 다른 지표보다 중요한지 판단해서는 안 됩니다. 이러한 지표는 별도의 서로 다른 독립적인 지표입니다. 전술한 정의들에서 설명된 바와 같이, 이들 각각은 상이한 데이터 세트들로부터 도출된다. 이 경우 한 지표가 다른 지표보다 큰 경우 결론을 도출하지 않아야 합니다. 이를 비교할 때 말할 수 있는 것은 다음과 같습니다.

* [!UICONTROL Customer Addressable Audiences]은(는) 사용자의 자사 데이터에 대한 [!UICONTROL trait] 실현 *을(를) 기반으로 합니다.* 이 지표는 데이터 파트너와의 통합에 대한 광범위하고 포괄적인 보기를 제공합니다.

* [!UICONTROL Segment Addressable Audiences]은(는) 자체 자사 데이터에 대한 세그먼트 자격 *과(와) 제2 및 제3자 데이터*&#x200B;을(를) 기반으로 합니다. 이 지표는 타깃팅 플랫폼에서 [!UICONTROL addressable audiences]을(를) 세부적으로 더 정확하게 볼 수 있도록 합니다.

## [!UICONTROL Addressable Audiences]에 대한 낮은 일치율의 원인 {#low-match-rates}

보고된 숫자의 낮은 [!UICONTROL Addressable Audience] 일치율 또는 불일치에 대한 일반적인 요소입니다.

| 원인 | 설명 |
|---|---|
| 모바일 트래픽 | 대부분의 [!UICONTROL server-to-server] 통합은 타사 [!DNL cookies]에 의해 촉진되는 동기화 프로세스에 의존합니다. 그러나 모바일 환경에서는 타사 [!DNL cookies]을(를) 사용하지 않습니다. 따라서 [!UICONTROL Addressable Audiences] 숫자는 [!UICONTROL segment] 크기에 비해 적어 보일 수 있습니다. <br><br>2018년 1월부터 [!DNL Google]개 대상에 대해 설정된 동일한 [!DNL Adobe Advertising Cloud] 및 [!UICONTROL cookie-based] 대상에서 모바일 대상을 활성화할 수 있습니다. 이는 결합된 [!UICONTROL segments] 및 모바일 ID 멤버십이 있는 [!DNL cookie]을(를) [!DNL Google] 및 [!DNL Advertising Cloud] 대상으로 보낼 수 있음을 의미하지만 [!UICONTROL Addressable Audiences]에는 [!DNL cookie]개의 ID와 대상 간의 중복만 표시된다는 점을 유의하십시오. [!DNL Audience Manager]이(가) 모바일 대상의 100%를 [!UICONTROL destinations]&#x200B;(으)로 전송하지만 모바일 대상은 [!UICONTROL Addressable Audience] 지표로 측정되지 않습니다. <br><br>**참고**: 예를 들어 모집단이 1,000,000인 [!UICONTROL segment]을(를) 사용합니다. 이 [!UICONTROL segment]을(를) [!DNL Google] 또는 [!DNL Adobe Advertising Cloud] 대상에 매핑하면 [!UICONTROL Addressable Audience]&#x200B;(700,000개 장치) 및 [!UICONTROL Match Rate]&#x200B;(70%)가 표시될 수 있습니다. 700,000명의 멤버십은 [!DNL cookie]과(와) ID 동기화가 있는 [!UICONTROL destination]개의 ID로 구성됩니다. 주소 지정 가능한 모바일 ID가 이 지표에 표시되지 않으므로 사실상 [!UICONTROL Addressable Audience]이(가) 훨씬 높을 수 있습니다. |
| [!DNL Safari] 트래픽 | [!DNL Safari]이(가) 서드파티 [!DNL cookies]을(를) 차단합니다. 이렇게 하면 [!DNL Audience Manager]이(가) ID를 [!UICONTROL destination]과(와) 동기화할 수 없습니다. [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/)을(를) 도입하면 [!UICONTROL addressable audiences]에 [!DNL Safari]명의 사용자가 포함되지 않을 수 있습니다. |
| 추적된 미디어 노출 횟수 | 광고 서버 모범 사례로 인해 광고 태그 내에서는 ID 동기화가 수행되지 않습니다. 대량의 오프사이트 광고를 수행하는 고객은 이러한 환경의 서드파티 통합에 사용자를 동기화하지 않습니다. 또한 수집된 미디어 노출 데이터가 많으면 [!UICONTROL addressable audience]개의 숫자를 줄일 수 있습니다. |

## [!UICONTROL Addressable Audiences] 문제 해결 {#troubleshooting}

일치율 표시 외에 [!UICONTROL Addressable Audiences]을(를) 문제 해결 도구로 사용할 수도 있습니다.

예를 들어 세그먼트를 [!UICONTROL destination]에 보내고 [!UICONTROL destination]에 낮은 보고 번호가 표시된다고 가정해 보겠습니다. [!UICONTROL Addressable Audience] 결과를 확인하면 기술적인 문제인지 또는 일치율이 낮은 경우인지 표시됩니다. 일치율이 낮으면 [!UICONTROL destination]이(가) 선택한 세그먼트에 적합하지 않다는 것을 보여줍니다. 그러나 [!UICONTROL total addressable audience]과(와) [!DNL Audience Manager] 사이의 [!UICONTROL destination] 숫자 차이는 통합, 동기화 또는 기타 기술적 문제를 나타냅니다. 이러한 경우 계정 관리자에게 문의하십시오.
