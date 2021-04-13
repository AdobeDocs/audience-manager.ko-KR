---
description: 어드레서블 대상 기능 및 사용 사례에 대한 개요입니다.
keywords: DIL
seo-description: 어드레서블 대상 기능 및 사용 사례에 대한 개요입니다.
seo-title: 대응 가능 대상
solution: Audience Manager
title: 대응 가능 대상
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: 일치율
exl-id: 2728e4a8-522c-423f-a6ef-e4dd624f69e5
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '1827'
ht-degree: 1%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

[!UICONTROL Addressable Audience] 기능 및 사용 사례에 대한 개요입니다.

##  [!UICONTROL Addressable Audience]? {#addressable-audience-description}

[!UICONTROL Addressable Audiences] 기능은 [!DNL Audience Manager]에서 데이터와 선택한 대상을 수집하는 모든 속성에서 표시되는 대상 간에 겹치는 것을 보여줍니다. 이 개념을 이해하려면 아래 그림을 참조하십시오. 각 원 사이의 겹치는 대응 가능 대상의 서로 다른 유형을 나타냅니다.

![](assets/addressableAudienceVenn.png)


| 지표 | 설명 |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] for  [!UICONTROL Destination] | 보고서 룩백 기간 동안 플랫폼 수준에서 모든 [!DNL Audience Manager] 고객과 상호 작용했으며 이 장치가 선택한 [!UICONTROL destination]과 일치할 수 있는 모든 장치의 수입니다. <br><br>이 지표는 다음과 같이 표시되므로 유용합니다. <ul><li>특정 타깃팅 [!UICONTROL destination]에서 [!DNL Audience Manager]에 도달할 수 있는 총 [!UICONTROL addressable audience]의 크기입니다.</li><li>타깃팅 플랫폼용 [!DNL Audience Manager] 프로필 풀의 크기 및 대상의 크기입니다.</li></ul> |
| [!UICONTROL Customer Total Audience] | 룩백 창 중에 속성에 [!UICONTROL rule-based trait] 또는 오프라인 파일에서 [!UICONTROL onboarded trait] 항목을 구현한 장치 수입니다. |
| [!UICONTROL Addressable Audience Match Rate] | 검색 창 중에 [!UICONTROL rule-based trait] 또는 [!UICONTROL onboarded trait] 중 하나를 인식한 장치 및 동기화 시간에 상관없이 선택한 [!UICONTROL destination]와 ID가 동기화된 장치의 오버랩 수입니다.<br><br>이 지표는 다음과 같은 장치를 나타냅니다.<ul><li>룩백 창 `AND`에서 [!UICONTROL rule-based] 또는 [!UICONTROL onboarded trait]을(를) 실현했습니다.</li><li>동기화 시간에 관계없이 선택한 [!UICONTROL destination]과 ID를 동기화해야 합니다.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ 백분율로  [!UICONTROL Customer Total Audience] 표현됨. |
| [!UICONTROL Total Segment Population] | 보고서 룩백 기간 동안 [!UICONTROL segment]의 멤버였던 모든 장치의 수입니다. |
| [!UICONTROL Segment Addressable Audience] | 보고서 검색 기간 동안 [!UICONTROL segment]에 속했으며 사이트에서 활성 ID 동기화를 가진 사용자 수입니다. [!UICONTROL Segments] Audience Marketplace에서  [!UICONTROL traits] 취득한 데이터를 통해 자신의 자사 데이터와 제2자 및 제3자 데이터를 포함할 수  [있습니다](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>팁:1일 룩백 기간과 함께 사용할 때 이 지표를 사용하여 사용자의 현재 상태를 이해할 수 있습니다 [!UICONTROL segments]. 이것은 [!UICONTROL Segment Addressable Audience] 지표가 전날 동안 [!UICONTROL segment]에 있었던 사용자를 나타내기 때문입니다. [!DNL Audience Manager]이(가) 매일 [!UICONTROL Addressable Audiences]을(를) 새로 고침하여 이 지표와 조회 기간을 결합하면 [!UICONTROL segments]의 최신 스냅샷을 제공할 수 있다는 사실과 함께 결합하십시오. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ 백분율로  [!UICONTROL Total Segment Population] 표현됨. |

## [!UICONTROL Addressable Audiences] 인터페이스 {#addressable-audience-interface}

[!UICONTROL Addressable Audience] 기능을 사용하면 이 추상적인 개념을 수량화할 수 있는 데이터로 변환할 수 있습니다. [!DNL Audience Manager]에서 이 기능은 테이블 형식의 숫자 데이터와 함께 한눈에 정보를 제공하는 데이터 시각화와 겹치는 대상을 표시합니다.

[!UICONTROL Addressable Audiences] 가 위치 **[!UICONTROL Audience Data > Destinations]**&#x200B;에 있습니다. 지정 가능한 대상 지표를 보려면 **[!UICONTROL Integrated Platforms > Device-Based]**&#x200B;을 선택합니다.

![](assets/addressable-audiences-landing.png)

[!UICONTROL Addressable Audiences] 랜딩 페이지에서 볼 수 있는 3개의 지표는 다음과 같습니다.

| 지표 | 설명 |
---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | 이 지표는 지난 30일 동안 [!UICONTROL Customer Addressable Audience](위 표에 설명됨) *을 나타냅니다.* |
| **[!UICONTROL Match Rate]** | 이 지표는 지난 30일 동안 [!UICONTROL Addressable Audience Match Rate](위 표에 설명됨) *을 나타냅니다.* |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | 보고서 룩백 기간 동안 플랫폼 수준에서 모든 [!DNL Audience Manager] 고객과 상호 작용했으며 이 [!UICONTROL destination]과 일치할 수 있는 모든 장치의 수입니다. 자세한 내용은 [플랫폼 수준 지표](/help/using/features/addressable-audiences.md#platform-level-metrics)를 참조하십시오. |

지정 가능한 대상 데이터를 보려면 [!UICONTROL server-to-server destination] 이름을 클릭합니다. 이 기능은 [!UICONTROL server-to-server destinations]에 대한 데이터만 반환하며 액세스하려면 관리자 권한이 필요합니다.

![](assets/addressableAudiences.png)

이 데이터를 검토하면 다음과 같은 이점을 얻을 수 있습니다.

* **예측 및 계획:** [!UICONTROL Segment Addressable Audience] 데이터는 대상 타깃팅 및 활성화를 위해 대상으로 전송하려는 세그먼트를 세부적으로 파악할 수 있도록 해줍니다.

* **성능 평가:** 이  [!UICONTROL Addressable Audiences] 기능은 문제 해결 도구이기도 합니다. 캠페인 성과를 검토하고 캠페인 도달 범위를 이해하며, 원하는 결과가 표시되지 않으면 타깃팅/활성화 파트너와 상호 검사할 수 있습니다.

### 제3자 데이터와 일치율에 대한 의미

고객 확보를 위한 제3자 데이터를 구매하기 전에 고객은 다른 데이터 제공업체와 겹치는 사항을 확인할 수 있습니다. 새로운 데이터를 구매하기 전에 현명한 의사 결정을 내릴 수 있습니다. 구입한 제3자 데이터에 대한 ID 동기화는 데이터가 중복될 뿐만 아니라 다른 모든 [!DNL Audience Manager] 고객과 제3자 공급자의 발자국에 의존합니다. [!DNL Adobe] 컨설턴트를 통해 잠재 캠페인을 최적화하기 위해 관련 있는 추가 데이터 소스를 식별할 수 있습니다.

### 모바일 사용자 및 일치율

제3자 [!DNL cookies]가 없는 [!DNL Safari] 또는 모바일 앱 사용자를 연결하려고 할 때 간격이 있습니다. 동기화된 제3자 [!DNL cookies]에 대한 [!DNL Adobe] ID만 미디어 배달 로그에 제공되므로 일부 파트너와 사용자를 동기화하기가 어렵습니다. 이것은 [!UICONTROL destinations]에 대해 [낮은 일치 비율](../features/addressable-audiences.md#low-match-rates)이 표시되는 이유입니다.

## [!UICONTROL Addressable Audiences] 및 [!UICONTROL Destinations] {#date-ranges}의 날짜 범위

사용 가능한 날짜 범위 및 [!UICONTROL Addressable Audience] 또는 [!UICONTROL Destination]에 대한 보고서의 각 간격에서 데이터가 어떻게 시간대를 벗어나지 않는지 아래 섹션을 참조하십시오.

## 사용 가능한 날짜 범위 및 시간대 {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

[!UICONTROL Addressable Audiences] 및 [대상](../features/destinations/destinations.md)에 대한 보고서는 동일한 날짜 범위 간격을 사용합니다. 날짜 범위 옵션은 다음과 같습니다.

* [!UICONTROL Last 1 Day] 이 간격은 이전 24시간 기간의 자정부터 자정까지 실행됩니다. 실시간 또는 현재 시간 지표가 아닙니다.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

모든 날짜 및 날짜 범위는 [!DNL UTC] 시간대에서 설정됩니다. [Audience Manager](../reference/aam-time-zones.md)의 시간대를 참조하십시오.

## 날짜 범위 간격의 데이터 {#date-range-intervals}

[!UICONTROL Addressable Audience] 및 [!UICONTROL Destination] 지표는 선택한 시간 간격에 대한 고유 사용자 수를 반환합니다. 예를 들어 방문자가 사이트에 여러 번 오더라도 한 번만 카운트됩니다. 첫 번째 방문은 고유한 방문으로 기록됩니다. 그 이후의 방문은 재방문되며 고유하지 않기 때문에 카운트되지 않습니다.

날짜 범위에는 선택한 시간 간격 또는 그 이전의 데이터가 포함됩니다. 그리고 데이터는 시간이 경과함에 따라 각 보고서 간격에서 제외됩니다. 예를 들어 [!UICONTROL Last 30 Days] 옵션을 선택한 후 2명의 방문자가 표시된다고 가정합니다. 보고서에서 이러한 방문자는 다음과 같습니다.

* *더 긴 시간 간격(60일, 90일 및 라이프타임)에 의해 반환된 결과에* 포함됩니다.
* *옵션* 앞에 오는 짧은 간격( [!UICONTROL Last 30 Day] 현재, 7일 및 14일)에 포함되지 않습니다.

그리고 31일에 이러한 방문자는 60일, 90일 및 [!UICONTROL Lifetime] 결과만 표시됩니다. 그들은 30일 간격을 벗어나 늙었다. 방문자는 [!UICONTROL Lifetime] 간격 중에서 나이를 먹지 않습니다.

## [!UICONTROL Addressable Audiences] 지표 {#addressable-audience-metrics}

이 섹션에서는 [!UICONTROL Addressable Audiences]에서 제공하는 지표 유형을 설명합니다.

### 고객 수준 지표 {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

이러한 지표는 방문자가 사이트를 방문하거나 인바운드 데이터 파일을 [!DNL Audience Manager]으로 보낼 때 발생한 트레이트에 대한 데이터를 반환합니다. 이러한 지표는 계정에 대한 대상 규모의 포괄적인 보기를 제공합니다.

| 지표 | 설명 |
|---|---|
| [!UICONTROL Customer Addressable Audience] | 검색 창 중에 [!UICONTROL rule-based trait] 또는 [!UICONTROL onboarded trait] 중 하나를 인식한 장치 및 동기화 시간에 관계없이 선택한 대상과 ID를 동기화하는 장치가 겹치는 횟수입니다.<br><br>이 지표는 다음과 같은 장치를 나타냅니다.<ul><li>룩백 창 `AND`에서 [!UICONTROL rule-based] 또는 [!UICONTROL onboarded trait]을(를) 실현했습니다.</li><li>동기화 시간에 관계없이 선택한 [!UICONTROL destination]과 ID를 동기화해야 합니다.</li></ul> |
| [!UICONTROL Customer Total Audience] | 룩백 창 중에 속성에 [!UICONTROL rule-based trait] 또는 오프라인 파일에서 [!UICONTROL onboarded trait] 항목을 구현한 장치 수입니다. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ 백분율로  [!UICONTROL Customer Total Audience] 표현됨. |

### 세그먼트 수준 일치 지표 {#segment-level-metrics}

이러한 지표는 [!UICONTROL segment] 멤버십의 데이터를 반환합니다. 이러한 기능을 통해 각 [!UICONTROL segments]에 대한 고객 규모를 보다 세분화되고 정확하게 파악할 수 있습니다.

>[!NOTE]
>
>룩백 윈도우를 [!UICONTROL segment] 수준에서 적용하는 방법은 고객 수준에서 적용하는 방법과 다릅니다. 방문자는 사이트를 방문하여 10일 전에 [!UICONTROL trait] 이벤트를 인지할 수 있으며, 그 이후로 [!UICONTROL segment]의 자격을 얻게 되고 2일 전에 [!UICONTROL segment]에서 탈퇴할 수 있습니다. 7일 룩백이 적용되면 이러한 방문자는 [!UICONTROL segment] 수준에서 계산되지만 고객 수준에서는 계산되지 않습니다.

| 지표 | 설명 |
|---|---|
| [!UICONTROL Segment Addressable Audience] | 보고서 검색 기간 동안 [!UICONTROL segment]에 속했으며 사이트에서 활성 ID 동기화를 가진 사용자 수입니다. 세그먼트에는 [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)에서 취득한 [!UICONTROL traits]을 통해 자신의 자사 데이터와 제3자 데이터가 포함될 수 있습니다.<br><br>팁:1일 룩백 기간과 함께 사용할 때 이 지표를 사용하여 사용자의 현재 상태를 이해할 수 있습니다 [!UICONTROL segments]. 이것은 [!UICONTROL Segment Addressable Audience] 지표가 전날 동안 [!UICONTROL segment]에 있었던 사용자를 나타내기 때문입니다. [!DNL Audience Manager]이(가) 매일 [!UICONTROL Addressable Audiences]을(를) 새로 고침하여 이 지표와 조회 기간을 결합하면 [!UICONTROL segments]의 최신 스냅샷을 제공할 수 있다는 사실과 함께 결합하십시오. |
| [!UICONTROL Total Segment Population] | 보고서 룩백 기간 동안 [!UICONTROL segment]의 멤버였던 모든 장치의 수입니다. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ 백분율로  [!UICONTROL Total Segment Population] 표현됨. |

### 플랫폼 수준 지표 {#platform-level-metrics}

이 지표는 모든 [!DNL Audience Manager] 고객을 대상으로 수집된 활동에 대한 데이터를 반환합니다. 집계된 [!DNL Audience Manager] 고객과 비교하여 고객의 전체 상황을 보다 광범위하게 파악할 수 있습니다.

| 지표 | 설명 |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | 보고서 룩백 기간 동안 플랫폼 수준에서 모든 [!DNL Audience Manager] 고객과 상호 작용했으며 이 장치가 선택한 [!UICONTROL destination]과 일치할 수 있는 모든 장치의 수입니다. <br><br>이 지표는 다음과 같이 표시되므로 유용합니다.<ul><li>특정 타깃팅 대상에서 [!DNL Audience Manager]이(가) 도달할 수 있는 [!UICONTROL total addressable audience]의 크기입니다.</li><li>타깃팅 플랫폼용 [!DNL Audience Manager] 프로필 풀의 크기 및 대상의 크기입니다.</li></ul> |

## [!UICONTROL Customer] 및 [!UICONTROL Segment Addressable Audiences] {#comparing-metrics} 비교

[!UICONTROL Customer Addressable Audience] 지표와 [!UICONTROL Segment Addressable Audience] 지표를 비교해서는 해당 지표가 다른 지표보다 중요한지 확인할 수 없습니다. 이것은 별개, 다른 지표 및 독립적인 지표입니다. 위의 정의에 설명된 바와 같이 각 데이터 세트는 서로 다른 데이터 세트에서 파생됩니다. 이 경우 한 지표가 다른 지표보다 크면 어떤 결론도 도출하지 않아야 합니다. 다음과 같이 말할 수 있습니다.

* [!UICONTROL Customer Addressable Audiences] 는 자사  [!UICONTROL trait] 데이터 *를 위한 통합을 기반으로 합니다*. 이 지표는 데이터 파트너와의 통합에 대한 광범위하고 포괄적인 보기를 제공합니다.

* [!UICONTROL Segment Addressable Audiences] 는 자사 데이터 *에 대한 세그먼트 자격 조건과 제2자 및 제3자 데이터를 기반으로 합니다*. 이 지표는 타깃팅 플랫폼에서 [!UICONTROL addressable audiences]의 세부 묘사를 보다 정확하게 제공합니다.

## [!UICONTROL Addressable Audiences] {#low-match-rates}에 대한 낮은 일치 비율의 원인

[!UICONTROL Addressable Audience]이(가) 보고된 수치의 일치 속도 또는 불일치에 책임이 있는 일반적인 요소입니다.

| 원인 | 설명 |
|---|---|
| 모바일 트래픽 | 대부분의 [!UICONTROL server-to-server] 통합은 제3자 [!DNL cookies]의 동기화 프로세스를 통해 이루어집니다. 그러나 모바일 환경에서는 타사 [!DNL cookies]을 사용하지 않습니다. 따라서 [!UICONTROL Addressable Audiences] 숫자는 [!UICONTROL segment] 크기와 비교하여 낮을 수 있습니다. <br><br>2018년 1월부터 대상에 대해 설정된 동일한  [!DNL Google] 대상 및 대상 [!DNL Adobe Advertising Cloud] 에서 모바일 대상을 활성화할 수  [!UICONTROL cookie-based] 있습니다. 즉, [!DNL cookie] 및 모바일 ID 멤버십이 결합된 [!UICONTROL segments]을(를) [!DNL Google] 및 [!DNL Advertising Cloud] 대상으로 보낼 수 있지만 [!UICONTROL Addressable Audiences]은 [!DNL cookie] ID와 대상 간에 겹치는 부분만 표시한다는 점을 염두에 두십시오. [!DNL Audience Manager] 은 모바일 대상의 100%를 다음으로  [!UICONTROL destinations]전송하지만 모바일 대상은 지표로 측정되지  [!UICONTROL Addressable Audience] 않습니다. <br><br>**참고**:예를 들어 인구 1,000,000 [!UICONTROL segment] 이 있는 a를 선택합니다. 이 [!UICONTROL segment]을 [!DNL Google] 또는 [!DNL Adobe Advertising Cloud] 대상에 매핑하면 700,000개 장치의 [!UICONTROL Addressable Audience] 및 70%의 [!UICONTROL Match Rate]가 표시될 수 있습니다. 700,000의 멤버십은 [!UICONTROL destination]과(와) ID가 동기화된 [!DNL cookie] ID로 구성됩니다. 주소 지정 가능한 모바일 ID는 이 지표에 나타나지 않으므로 실제 [!UICONTROL Addressable Audience]은(는) 훨씬 더 높은 것일 수 있습니다. |
| [!DNL Safari] 트래픽 | [!DNL Safari] 블록(third-party) [!DNL cookies]. 이렇게 하면 [!DNL Audience Manager]이(가) [!UICONTROL destination]과(와) ID를 동기화할 수 없습니다. [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/)이 도입되면 [!UICONTROL addressable audiences]에 [!DNL Safari] 사용자가 포함되지 않을 것으로 예상할 수 있습니다. |
| 추적된 미디어 노출 수 | 광고 서버 우수 사례로 인해 광고 태그 내에 ID 동기화가 수행되지 않습니다. 오프사이트 광고를 많이 하는 고객은 그러한 환경에서 사용자를 타사 통합에 동기화하지 않습니다. 또한 대량의 미디어 노출 수 데이터를 수집하면 [!UICONTROL addressable audience] 수가 줄어들 수 있습니다. |

## [!UICONTROL Addressable Audiences] {#troubleshooting} 문제 해결

일치 비율을 표시하는 것 외에도 문제 해결 도구로 [!UICONTROL Addressable Audiences]을 사용할 수도 있습니다.

예를 들어 세그먼트를 [!UICONTROL destination]에 보냈고 [!UICONTROL destination]에 보고 수가 낮다고 가정해 봅시다. [!UICONTROL Addressable Audience] 결과를 선택하면 기술적 문제인지 또는 낮은 일치 비율의 사례인지 표시됩니다. 낮은 일치 비율은 선택한 세그먼트에 대해 [!UICONTROL destination]이(가) 그다지 좋지 않음을 나타냅니다. 그러나 [!DNL Audience Manager]과 [!UICONTROL destination] 사이의 [!UICONTROL total addressable audience] 숫자의 차이는 통합, 동기화 또는 기타 기술 문제를 나타냅니다. 이러한 경우 계정 관리자에게 문의하십시오.
