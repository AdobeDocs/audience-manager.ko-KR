---
description: 대응 가능 대상 기능 및 사용 사례에 대한 개요입니다.
keywords: DIL
seo-description: 대응 가능 대상 기능 및 사용 사례에 대한 개요입니다.
seo-title: 대응 가능 대상
solution: Audience Manager
title: 대응 가능 대상
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: 일치율
exl-id: 2728e4a8-522c-423f-a6ef-e4dd624f69e5
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1827'
ht-degree: 1%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

[!UICONTROL Addressable Audience] 기능 및 사용 사례에 대한 개요입니다.

##  [!UICONTROL Addressable Audience]? {#addressable-audience-description}

[!UICONTROL Addressable Audiences] 기능은 [!DNL Audience Manager]이 데이터를 수집하는 모든 속성에서 표시되는 대상과 선택한 대상 간에 겹치는 것을 보여줍니다. 이 개념을 이해하는 데 도움이 되도록 아래 설명을 살펴보십시오. 각 원 간의 겹침은 서로 다른 유형의 대응 가능 대상을 나타냅니다.

![](assets/addressableAudienceVenn.png)


| 지표 | 설명 |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] 대상  [!UICONTROL Destination] | 보고서 전환 확인 기간 동안 플랫폼 수준에서 모든 [!DNL Audience Manager] 고객과 상호 작용했으며 선택한 [!UICONTROL destination]과 일치할 수 있는 모든 장치의 수입니다. <br><br>이 지표는 다음을 보여주므로 유용합니다. <ul><li>[!DNL Audience Manager]이 특정 타깃팅 [!UICONTROL destination]에서 도달할 수 있는 총 [!UICONTROL addressable audience]의 크기입니다.</li><li>타겟 플랫폼용 [!DNL Audience Manager] 프로필 풀의 크기 및 대상 크기</li></ul> |
| [!UICONTROL Customer Total Audience] | 검색 창 중에 속성에서 [!UICONTROL rule-based trait] 또는 오프라인 파일에서 [!UICONTROL onboarded trait] 를 실현한 장치 수입니다. |
| [!UICONTROL Addressable Audience Match Rate] | 전환 확인 기간 동안 [!UICONTROL rule-based trait] 또는 [!UICONTROL onboarded trait] 중 하나를 실현한 장치 및 동기화 시간과 관계없이 선택한 [!UICONTROL destination]과 ID 동기화가 있는 장치의 겹침 수입니다.<br><br>이 지표는 다음과 같은 장치를 나타냅니다.<ul><li>전환 확인 기간 `AND` 동안 [!UICONTROL rule-based] 또는 [!UICONTROL onboarded trait]을 실현했습니다.</li><li>동기화 시간과 관계없이 선택한 [!UICONTROL destination]과 ID 동기화가 있습니다.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] 로 표현됩니다. |
| [!UICONTROL Total Segment Population] | 보고서 전환 확인 기간 동안 [!UICONTROL segment]의 구성원이었던 모든 장치의 수입니다. |
| [!UICONTROL Segment Addressable Audience] | 보고서 전환 확인 기간 동안 [!UICONTROL segment]에 속하고 사이트에 대한 활성 ID 동기화를 보유한 사용자 수입니다. [!UICONTROL Segments]  [!UICONTROL traits] Audience Marketplace [에서 획득한 를 통해 자신의 자사 데이터와 제2자 데이터, ](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)타사 데이터를 포함할 수있습니다. <br><br>팁:1일 전환 확인 기간과 함께 사용하는 경우 이 지표를 통해 의 현재 상태를 이해할 수  [!UICONTROL segments]있습니다. 이것은 [!UICONTROL Segment Addressable Audience] 지표가 전날 [!UICONTROL segment]에 있었던 사용자를 나타내므로 [!DNL Audience Manager] 이 매일 [!UICONTROL Addressable Audiences]을(를) 새로 고치므로 이 지표와 전환 기간을 결합하면 [!UICONTROL segments]의 최신 스냅숏이 제공된다는 사실을 결합하십시오. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] 로 표현됩니다. |

## [!UICONTROL Addressable Audiences] 인터페이스 {#addressable-audience-interface}

[!UICONTROL Addressable Audience] 기능은 이 추상적인 개념을 수량화할 수 있는 데이터로 변환합니다. [!DNL Audience Manager]에서 이 기능은 요약 정보를 숫자 데이터와 함께 테이블 형식으로 제공하는 데이터 시각화와 겹치는 대상을 표시합니다.

[!UICONTROL Addressable Audiences] 에 있습니다 **[!UICONTROL Audience Data > Destinations]**. 지정 대상 지표를 보려면 **[!UICONTROL Integrated Platforms > Device-Based]** 을 선택합니다.

![](assets/addressable-audiences-landing.png)

[!UICONTROL Addressable Audiences] 랜딩 페이지에 표시되는 세 개의 지표는 다음과 같습니다.

| 지표 | 설명 |
|---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | 이 지표는 지난 30일 동안 [!UICONTROL Customer Addressable Audience](위의 표에 설명)을 나타냅니다.** |
| **[!UICONTROL Match Rate]** | 이 지표는 지난 30일&#x200B;*에 대한 [!UICONTROL Addressable Audience Match Rate](위의 표에 설명)을 나타냅니다.* |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | 보고서 전환 확인 기간 동안 플랫폼 수준에서 모든 [!DNL Audience Manager] 고객과 상호 작용했으며 이 [!UICONTROL destination]과 일치할 수 있는 모든 장치의 수입니다. 자세한 내용은 [플랫폼 수준 지표](/help/using/features/addressable-audiences.md#platform-level-metrics)를 참조하십시오. |

지정 대상 데이터를 보려면 [!UICONTROL server-to-server destination] 이름을 클릭하십시오. 참고: 이 기능은 [!UICONTROL server-to-server destinations]에 대해서만 데이터를 반환하며 액세스하려면 관리자 권한이 필요합니다.

![](assets/addressableAudiences.png)

이 데이터를 검토하면 다음을 수행할 수 있습니다.

* **예측 및 계획:** [!UICONTROL Segment Addressable Audience]  데이터는 대상 타깃팅 및 활성화를 위해 대상에 전송하려는 세그먼트를 더 세부적으로 제공합니다.

* **성능 검토:** 이  [!UICONTROL Addressable Audiences] 기능은 문제 해결 도구이기도 합니다. 이 기능을 사용하면 캠페인 성과를 검토하고, 캠페인 도달 범위를 이해하며, 예상 결과가 표시되지 않는 경우 타깃팅/활성화 파트너와 상호 확인할 수 있습니다.

### 타사 데이터와 일치율에 대한 의미 비교

대상 획득을 위한 타사 데이터를 구매하기 전에 고객이 다른 데이터 공급자와 겹치는지 확인할 수 있습니다. 이렇게 하면 새 데이터를 사기 전에 현명한 결정을 내릴 수 있습니다. 구매한 타사 데이터에 대한 ID 동기화는 데이터가 겹칠 뿐만 아니라 다른 모든 [!DNL Audience Manager] 고객과의 타사 공급자의 풋프린트에 의존합니다. [!DNL Adobe] 컨설턴트는 대상 캠페인을 최적화하기 위해 추가적인 관련 데이터 소스를 식별하는 데 도움을 줄 수 있습니다.

### 모바일 사용자 및 일치율

[!DNL Safari] 또는 타사 [!DNL cookies] 가 없는 모바일 앱 사용자를 연결하려고 할 때 간격이 있습니다. 따라서 동기화된 타사 [!DNL cookies]에 대한 [!DNL Adobe] ID만 미디어 게재 로그에 제공되므로 일부 파트너와 사용자를 동기화하기가 어렵습니다. [!UICONTROL destinations]에 대해 [낮은 일치율](../features/addressable-audiences.md#low-match-rates)이 표시되는 이유입니다.

## [!UICONTROL Addressable Audiences] 및 [!UICONTROL Destinations] {#date-ranges}의 날짜 범위

사용 가능한 날짜 범위에 대해 아래 섹션을 읽고, 데이터가 [!UICONTROL Addressable Audience] 또는 [!UICONTROL Destination]에 대해 보고서에서 각 간격에서 어떻게 시간되는지 확인하십시오.

## 사용 가능한 날짜 범위 및 시간대 {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

[!UICONTROL Addressable Audiences] 및 [대상](../features/destinations/destinations.md)에 대한 보고서는 동일한 날짜 범위 간격을 사용합니다. 날짜 범위 옵션은 다음과 같습니다.

* [!UICONTROL Last 1 Day] (이 간격은 이전 24시간 기간 중 자정부터 자정까지 실행됩니다. 실시간 또는 현재 시간 지표가 아닙니다.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

모든 날짜 및 날짜 범위는 [!DNL UTC] 표준 시간대에 설정됩니다. Audience Manager](../reference/aam-time-zones.md)의 [시간대 를 참조하십시오.

## 날짜 범위 간격의 데이터 {#date-range-intervals}

[!UICONTROL Addressable Audience] 및 [!UICONTROL Destination] 지표는 선택한 시간 간격에 대한 고유 사용자 수를 반환합니다. 예를 들어 방문자는 사이트를 여러 번 방문하는 경우에도 한 번만 카운트됩니다. 첫 번째 방문은 고유한 방문이며 기록됩니다. 후속 방문이 재방문이며 고유하지 않으므로 계산되지 않습니다.

날짜 범위에는 선택한 시간 간격 또는 그 이상의 데이터가 포함됩니다. 또한 시간이 경과함에 따라 데이터가 각 보고서 간격에서 시간 초과됩니다. 예를 들어 [!UICONTROL Last 30 Days] 옵션을 선택한 후 2명의 방문자가 표시된다고 가정해 보겠습니다. 보고서에서 이러한 방문자는 다음과 같습니다.

* *더 긴 시간 간격(60일, 90일 및 라이프타임)에 의해 반환된 결과에* 포함됩니다.
* *옵션* 앞에 있는 짧은 간격( [!UICONTROL Last 30 Day] 현재, 7일 및 14일)에 포함되지 않습니다.

그리고 31일에 이러한 방문자는 60일, 90일 및 [!UICONTROL Lifetime] 결과에만 나타납니다. 그들은 30일 간격 중 이미 나이가 들었다. 방문자는 [!UICONTROL Lifetime] 간격을 벗어나지 않습니다.

## [!UICONTROL Addressable Audiences] 지표 {#addressable-audience-metrics}

이 섹션에서는 [!UICONTROL Addressable Audiences]에서 제공하는 지표 유형을 설명합니다.

### 고객 수준 지표 {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

이 지표는 방문자가 사이트를 방문하거나 인바운드 데이터 파일을 [!DNL Audience Manager]에 보낼 때 구현된 트레이트에 대한 데이터를 반환합니다. 이러한 지표는 계정에 대한 대상 크기에 대한 포괄적인 보기를 제공합니다.

| 지표 | 설명 |
|---|---|
| [!UICONTROL Customer Addressable Audience] | 전환 확인 기간 동안 [!UICONTROL rule-based trait] 또는 [!UICONTROL onboarded trait] 중 하나를 실현한 장치 및 동기화 시간과 관계없이 선택한 대상과의 ID 동기화가 있는 장치의 겹침 수입니다.<br><br>이 지표는 다음과 같은 장치를 나타냅니다.<ul><li>전환 확인 기간 `AND` 동안 [!UICONTROL rule-based] 또는 [!UICONTROL onboarded trait]을 실현했습니다.</li><li>동기화 시간과 관계없이 선택한 [!UICONTROL destination]과 ID 동기화가 있습니다.</li></ul> |
| [!UICONTROL Customer Total Audience] | 검색 창 중에 속성에서 [!UICONTROL rule-based trait] 또는 오프라인 파일에서 [!UICONTROL onboarded trait] 를 실현한 장치 수입니다. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] 로 표현됩니다. |

### 세그먼트 수준 일치 지표 {#segment-level-metrics}

이러한 지표는 [!UICONTROL segment] 멤버십에 대한 데이터를 반환합니다. 이 도구를 사용하면 각 [!UICONTROL segments]에 대한 대상 크기를 보다 세분화되고 정확하게 볼 수 있습니다.

>[!NOTE]
>
>[!UICONTROL segment] 수준에서 전환 확인 창이 적용되는 방식은 고객 수준에서 적용되는 방식과 다릅니다. 방문자는 사이트를 방문하여 10일 전에 [!UICONTROL trait] 을 실현할 수 있으며, 이 경우 [!UICONTROL segment] 자격이 부여되어 2일 전에 [!UICONTROL segment]에서 탈퇴할 수 있습니다. 7일 되돌아보기가 적용되면 이 방문자는 [!UICONTROL segment] 수준에서 계산되지만 고객 수준에서는 계산되지 않습니다.

| 지표 | 설명 |
|---|---|
| [!UICONTROL Segment Addressable Audience] | 보고서 전환 확인 기간 동안 [!UICONTROL segment]에 속하고 사이트에 대한 활성 ID 동기화를 보유한 사용자 수입니다. 세그먼트는 [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)에서 획득한 [!UICONTROL traits]을 통해 자신의 자사 데이터와 제2자 데이터, 타사 데이터를 포함할 수 있습니다.<br><br>팁:1일 전환 확인 기간과 함께 사용하는 경우 이 지표를 통해 의 현재 상태를 이해할 수  [!UICONTROL segments]있습니다. 이것은 [!UICONTROL Segment Addressable Audience] 지표가 전날 [!UICONTROL segment]에 있었던 사용자를 나타내므로 [!DNL Audience Manager] 이 매일 [!UICONTROL Addressable Audiences]을(를) 새로 고치므로 이 지표와 전환 기간을 결합하면 [!UICONTROL segments]의 최신 스냅숏이 제공된다는 사실을 결합하십시오. |
| [!UICONTROL Total Segment Population] | 보고서 전환 확인 기간 동안 [!UICONTROL segment]의 구성원이었던 모든 장치의 수입니다. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] 로 표현됩니다. |

### 플랫폼 수준 지표 {#platform-level-metrics}

이 지표는 모든 [!DNL Audience Manager] 고객 간에 수집된 활동에 대한 데이터를 반환합니다. 집계된 [!DNL Audience Manager] 고객과 비교하여 고객 대상에 대한 더 광범위한 보기를 제공할 수 있습니다.

| 지표 | 설명 |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | 보고서 전환 확인 기간 동안 플랫폼 수준에서 모든 [!DNL Audience Manager] 고객과 상호 작용했으며 선택한 [!UICONTROL destination]과 일치할 수 있는 모든 장치의 수입니다. <br><br>이 지표는 다음을 보여주므로 유용합니다.<ul><li>[!DNL Audience Manager]이 특정 타깃팅 대상에서 도달할 수 있는 [!UICONTROL total addressable audience]의 크기입니다.</li><li>타겟 플랫폼용 [!DNL Audience Manager] 프로필 풀의 크기 및 대상 크기</li></ul> |

## [!UICONTROL Customer] 및 [!UICONTROL Segment Addressable Audiences] {#comparing-metrics} 비교

[!UICONTROL Customer Addressable Audience] 및 [!UICONTROL Segment Addressable Audience] 지표를 비교하여 하나가 다른 지표보다 더 중요한지 판단해서는 안 됩니다. 이는 별도의, 서로 다른, 독립적인 지표입니다. 위의 정의에 설명된 대로 이러한 각 데이터 세트는 서로 다른 데이터 세트에서 파생됩니다. 이 경우 한 지표가 다른 지표보다 큰 경우 결론에 도달하지 않아야 합니다. 이것들을 비교할 때 당신이 말할 수 있는 것은 다음과 같습니다.

* [!UICONTROL Customer Addressable Audiences] 는  [!UICONTROL trait] 고유한 자사 데이터 *에 대한 실현을 기반으로 합니다*. 이 지표는 데이터 파트너와 통합하는 방법에 대한 포괄적이고 광범위한 보기를 제공합니다.

* [!UICONTROL Segment Addressable Audiences] 는 자사 데이터 *에 대한 세그먼트 자격 증명과 제2 데이터와 타사 데이터를 기반으로 합니다*. 이 지표는 타깃팅 플랫폼에서 [!UICONTROL addressable audiences]을(를) 보다 세밀하게 볼 수 있도록 해줍니다.

## [!UICONTROL Addressable Audiences] {#low-match-rates}에 대한 낮은 일치율의 원인

보고된 숫자의 낮은 [!UICONTROL Addressable Audience] 일치율 또는 불일치를 담당하는 일반적인 요소.

| 원인 | 설명 |
|---|---|
| 모바일 트래픽 | 대부분의 [!UICONTROL server-to-server] 통합은 타사 [!DNL cookies]에서 제공하는 동기화 프로세스에 의존합니다. 그러나 모바일 환경에서는 타사 [!DNL cookies]을 사용하지 않습니다. 따라서 [!UICONTROL Addressable Audiences] 숫자가 [!UICONTROL segment] 크기와 비교하여 낮을 수 있습니다. <br><br>2018년 1월부터 대상에 대해 설정된 동일한  [!DNL Google] 및 대상에서 모바일  [!DNL Adobe Advertising Cloud] 대상을 활성화할 수  [!UICONTROL cookie-based] 있습니다. 즉, [!DNL cookie] 및 모바일 ID 멤버십이 결합된 [!UICONTROL segments]을 [!DNL Google] 및 [!DNL Advertising Cloud] 대상에 보낼 수 있지만 [!UICONTROL Addressable Audiences]는 [!DNL cookie] ID와 대상 간에 겹치는 부분만 표시한다는 점을 기억하십시오. [!DNL Audience Manager] 는 모바일 대상의 100% [!UICONTROL destinations]를 로 전송하지만 모바일 대상은 지표로 측정되지  [!UICONTROL Addressable Audience] 않습니다. <br><br>**참고**:예를 들어  [!UICONTROL segment] 모집단이 1,000,000인 를 선택합니다. 이 [!UICONTROL segment]을 [!DNL Google] 또는 [!DNL Adobe Advertising Cloud] 대상에 매핑하면 70만 개의 장치 중 [!UICONTROL Addressable Audience]과 70%의 [!UICONTROL Match Rate]가 표시될 수 있습니다. 70만 명의 멤버십은 [!DNL cookie] ID와 [!UICONTROL destination] ID의 ID로 구성됩니다. 대응 가능 모바일 ID는 이 지표에 표시되지 않으므로 실제로 [!UICONTROL Addressable Audience]이 훨씬 더 높을 수 있습니다. |
| [!DNL Safari] 트래픽 | [!DNL Safari] 타사 블록을  [!DNL cookies]차단합니다. 따라서 [!DNL Audience Manager]이 [!UICONTROL destination]과 ID를 동기화하지 못합니다. [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/)의 도입으로 [!UICONTROL addressable audiences]에 [!DNL Safari] 사용자가 포함되지 않을 것으로 예상할 수 있습니다. |
| 추적된 미디어 노출 횟수 | 광고 서버 우수 사례로 인해 ID 동기화는 광고 태그 내에 작성되지 않습니다. 대량의 오프사이트 광고를 수행하는 고객은 해당 환경의 타사 통합에 사용자를 동기화하지 않습니다. 또한 많은 양의 미디어 노출 데이터가 수집되면 [!UICONTROL addressable audience] 숫자가 줄어들 수 있습니다. |

## [!UICONTROL Addressable Audiences] 문제 해결 {#troubleshooting}

일치 비율 표시 외에도 [!UICONTROL Addressable Audiences] 을 문제 해결 도구로 사용할 수도 있습니다.

예를 들어 세그먼트를 [!UICONTROL destination]에 보내고 [!UICONTROL destination]에 낮은 보고 숫자가 표시된다고 가정해 보겠습니다. [!UICONTROL Addressable Audience] 결과를 확인하면 기술적 문제인지 아니면 일치율이 낮은 경우인지 표시됩니다. 낮은 일치율은 [!UICONTROL destination]이 선택한 세그먼트에 대해 그리 좋지 않다는 것을 보여줍니다. 그러나 [!DNL Audience Manager] 와 [!UICONTROL destination] 간의 [!UICONTROL total addressable audience] 숫자 차이는 통합, 동기화 또는 기타 기술 문제를 나타냅니다. 이러한 경우 계정 관리자에게 문의하십시오.
