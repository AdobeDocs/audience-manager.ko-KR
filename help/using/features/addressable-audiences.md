---
description: 어드레서블 대상 기능 및 사용 사례에 대한 개요입니다.
keywords: DIL
seo-description: 어드레서블 대상 기능 및 사용 사례에 대한 개요입니다.
seo-title: 대응 가능 대상
solution: Audience Manager
title: 대응 가능 대상
topic: DIL API
uuid: 3 EB 1335 A -6949-452 B-B 77 A -697 C 22856 CB 3
translation-type: tm+mt
source-git-commit: b213a1ecde4c85dc66dada24dec602ed1d9b0332

---


# Addressable Audience {#addressable-audiences}

어드레서블 대상 기능 및 사용 사례에 대한 개요입니다.

## What is an Addressable Audience? {#addressable-audience-description}

[!UICONTROL Addressable Audiences] 이 기능은 데이터 및 선택한 대상을 [!DNL Audience Manager] 수집하는 모든 속성에 걸쳐 표시되는 대상 간 오버랩을 보여줍니다. 이 개념을 이해하려면 아래 그림을 참조하십시오. 각 서클 간의 오버랩은 서로 다른 유형의 지정 가능 대상을 나타냅니다.

![](assets/addressableAudienceVenn.png)

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 지표 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
    <tr> 
   <td colname="col1"> <p> <b>대상에 대한 Audience Manager의 대응 가능 대상</b> </p> </td> 
   <td colname="col2"> <p>보고서 룩백 기간 동안 플랫폼 수준에서 모든 Audience Manager 고객과 상호 작용하고 선택한 대상에 일치할 수 있는 모든 장치의 수입니다. </p> <p>이 지표는 다음 사항을 표시하기 때문에 유용합니다. </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> <span class="keyword"> Audience Manager가 특정 타깃팅 대상에 도달할</span> 수 있는 총 지정 가능 대상의 크기입니다. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">How big the <span class="keyword"> Audience Manager</span> profile pool is for a targeting platform and the size of their audiences. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>고객 총 고객 수</b> </p> </td> 
   <td colname="col2"> <p>룩백 창 동안 오프라인 파일에서 오프라인 파일에서 규칙 기반 트레이트를 구현한 장치 수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>대응 가능한 고객 대응률</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>룩백 창과 장치 중에 규칙 기반 트레이트를 구현했거나, ID가 동기화 시간과 관계없이 선택한 대상과 동기화된 장치 겹쳐 있는 횟수입니다. </p> 
    </draft-comment> <p>이 지표는 다음과 같은 장치를 나타냅니다. 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Have realized either a rule-based or an onboarded trait during the look-back window <b>AND</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">동기화 시간에 관계없이 ID가 선택한 대상과 동기화되도록 합니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>고객 일치 비율</b> </p> </td> 
   <td colname="col2"> <p>고객 지정 가능 대상 ÷ 고객 총 고객 수 (%) </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <b>총 세그먼트 모집단 수</b> </p> </td> 
   <td colname="col2"> <p>보고서 룩백 기간 동안 세그먼트의 구성원인 모든 장치의 수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>세그먼트 지정 가능 대상</b> </p> </td> 
   <td colname="col2"> <p>보고서 룩백 기간 동안 세그먼트에 속하고 사이트에서 활성 ID 동기화가 있는 사용자의 수입니다. Segments can include your own first-party data and second party and third party data, via traits acquired in the <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>. </p> <p> <p>팁: 1 일 룩백 기간과 함께 사용하는 경우 이 지표는 세그먼트의 현재 상태를 이해하는 데 도움이 될 수 있습니다. <span class="wintitle"> 세그먼트 지정 가능 대상</span> 지표는 이전 하루 동안 세그먼트에 머물렀던 사용자를 나타내기 때문입니다. <span class="keyword"> Audience Manager가</span> <span class="wintitle"> 지정 가능한 대상을</span> 매일 새로 고침한다는 사실과 함께 이 지표를 결합하면 이 지표와 lookback 기간이 세그먼트에 대한 최신 스냅샷을 제공합니다. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>세그먼트 일치 비율</b> </p> </td> 
   <td colname="col2"> <p>세그먼트 지정 가능 대상 ÷ 총 세그먼트 모집단을 퍼센트로 나타낸 것입니다. </p> </td> 
  </tr>  
 </tbody> 
</table>

## Addressable Audience Interface {#addressable-audience-interface}

The [!UICONTROL Addressable Audience] feature turns this abstract concept into quantifiable data. In [!DNL Audience Manager], this feature displays audience overlap with data visualizations that provide at-a-glance information along with numeric data in tabular form.

[!UICONTROL Addressable Audiences]**[!UICONTROL Audience Data > Destinations]** 에 있습니다. Select **[!UICONTROL Integrated Platforms > Device-Based]** to see addressable audiences metrics.

![](assets/addressable-audiences-landing.png)

지정 가능 대상 랜딩 페이지에서 볼 수 있는 세 가지 지표는 다음과 같습니다.

| 지표 | 설명 |
---------|----------|
| **대응 가능 대상 (장치)** | This metric represents the Customer Addressable Audience (described in the table above) *for the last 30 days.* |
| **일치 비율** | This metric represents the Addressable Audience Match Rate (described in the table above) *for the last 30 days*. |
| **라이프타임 주소 지정 가능 대상 (장치)** | 보고서 룩백 기간 동안 플랫폼 수준에서 모든 Audience Manager 고객과 상호 작용하고 이 대상에 일치할 수 있는 모든 장치의 수입니다. See [Platform-Level Metrics](/help/using/features/addressable-audiences.md#platform-level-metrics) for more information. |

주소 지정 가능 대상 데이터를 확인하려면 서버 간 대상의 이름을 클릭합니다. 참고: 이 기능은 서버-서버 대상에만 데이터를 반환하고 액세스하려면 관리자 권한이 필요합니다.

![](assets/addressableAudiences.png)

이 데이터를 검토하여 다음과 같은 일을 할 수 있습니다.

* **예측 및 기획:**[!UICONTROL Segment Addressable Audience] 데이터는 대상 타깃팅 및 활성화를 위해 대상으로 전송할 세그먼트에 더 많은 세부기간을 제공합니다.

* **성능 평가:** 이 기능은 [!UICONTROL Addressable Audiences] 문제 해결 도구이기도 합니다. 캠페인 성과를 검토하고 캠페인 도달 범위를 이해하며, 예상한 결과가 표시되지 않을 경우 타깃팅/활성화 파트너와 상호 확인할 수 있습니다.

### 제 3 자 데이터와 일치율에 대한 연관성 확보

고객 확보를 위해 서드 파티 데이터를 구매하기 전에 고객은 다른 데이터 제공업체와 겹치는 것을 확인할 수 있습니다. 이렇게 하면 새 데이터를 구매하기 전에 현명한 의사 결정을 내릴 수 있습니다. The ID syncs for purchased third-party data rely not only on the overlap of your data but also on third-party providers’ footprints with all other [!DNL Audience Manager] customers. Your [!DNL Adobe] consultant can help you identify additional relevant data sources to optimize prospecting campaigns.

### 모바일 사용자 및 일치 비율

There are gaps when trying to connect [!DNL Safari] or mobile app users where there are no third-party cookies present. That makes it difficult to sync users with some partners because only those [!DNL Adobe] IDs for synced third-party cookies are provided in the media delivery logs. This is a reason why you might see [low match rates](../features/addressable-audiences.md#low-match-rates) for your destinations.

## Date Ranges in Addressable Audiences and Destinations {#date-ranges}

Read the sections below for available date ranges and how data ages out of each interval in the reports for an [!UICONTROL Addressable Audience] or [!UICONTROL Destination].

## Available Date Ranges and Time Zones {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

[!UICONTROL Addressable Audiences] 사용자 및 [대상에](../features/destinations/destinations.md) 대한 보고서는 동일한 날짜 범위 간격을 사용합니다. 날짜 범위 옵션은 다음과 같습니다.

* [!UICONTROL Last 1 Day] (이 간격은 24 시간 전의 자정부터 자정까지 실행됩니다. 실제 시간 지표가 아닙니다.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

All dates and date ranges are set in the [!DNL UTC] time zone. See [Time Zones in Audience Manager](../reference/aam-time-zones.md).

## Data in Date Range Intervals {#date-range-intervals}

[!UICONTROL Addressable Audience] AND [!UICONTROL Destination] 지표는 선택한 시간 간격에 대한 고유 사용자의 수를 반환합니다. 예를 들어 방문자가 사이트에 여러 번 방문하는 경우에도 한 번만 카운트됩니다. 첫 번째 방문은 고유 방문이며 기록됩니다. 이후의 방문은 방문을 반환하며 고유하지 않기 때문에 카운트되지 않습니다.

날짜 범위에는 선택한 시간 간격 이상의 데이터가 포함됩니다. 또한 시간이 경과함에 따라 각 보고서 간격에서 데이터가 삭제됩니다. For example, let&#39;s assume you see 2 visitors after choosing the [!UICONTROL Last 30 Days] option. 보고서에서 이러한 방문자는 다음과 같습니다.

* *긴 시간 간격 (60 일, 90 일 및 라이프타임) 에 의해 반환된 결과에* 포함됩니다.
* *옵션 앞에 오는 짧은 간격에* 포함되지 [!UICONTROL Last 30 Day] 않습니다 (현재, 7 일 및 14 일).

And, on day 31, these visitors only show up in the 60 day, 90 day, and [!UICONTROL Lifetime] results. 30 일 간 지속되었습니다. Visitors do not age out of the [!UICONTROL Lifetime] interval.

## Addressable Audience Metrics {#addressable-audience-metrics}

This section describes the types of metrics provided by [!UICONTROL Addressable Audiences].

### Customer-Level Metrics {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

These metrics return data for traits realized when visitors come to your site or when you send inbound data files to [!DNL Audience Manager]. 이 지표는 계정에 대한 대상 크기의 포괄적인 보기를 제공합니다.

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 지표 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>고객 지정 가능 대상</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>룩백 창과 장치 중에 규칙 기반 트레이트를 구현했거나, ID가 동기화 시간과 관계없이 선택한 대상과 동기화된 장치 겹쳐 있는 횟수입니다. </p> 
    </draft-comment> <p>이 지표는 다음과 같은 장치를 나타냅니다. 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Have realized either a rule-based or an onboarded trait during the look-back window <b>AND</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">동기화 시간에 관계없이 ID가 선택한 대상과 동기화되도록 합니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>고객 총 고객 수</b> </p> </td> 
   <td colname="col2"> <p>룩백 창 동안 오프라인 파일에서 오프라인 파일에서 규칙 기반 트레이트를 구현한 장치 수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>고객 일치 비율</b> </p> </td> 
   <td colname="col2"> <p>고객 지정 가능 대상 ÷ 고객 총 고객 수 (%) </p> </td> 
  </tr> 
 </tbody> 
</table>

### Segment-Level Match Metrics {#segment-level-metrics}

이러한 지표는 세그먼트 멤버십에 대한 데이터를 반환합니다. 각 세그먼트에 대한 고객 규모를 보다 정확하고 정확하게 파악할 수 있습니다.

>[!NOTE]
>
>세그먼트 수준에서 룩백 창이 적용되는 방식은 고객 수준의 경우와 다릅니다. 방문자는 사이트에 와서 10 일 전에 트레이트를 실현할 수 있으며, 그 후 세그먼트를 적용받을 수 있고 2 일 전에 세그먼트를 그만둘 수 있습니다. 7 일 룩백이 적용되면 이러한 방문자는 세그먼트 수준에서 계산되지만 고객 수준은 계산되지 않습니다.

<table id="table_4185AA02CC774B6C93B02E45F88BBBD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 지표 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>세그먼트 지정 가능 대상</b> </p> </td> 
   <td colname="col2"> <p>보고서 룩백 기간 동안 세그먼트에 속하고 사이트에서 활성 ID 동기화가 있는 사용자의 수입니다. Segments can include your own first-party data and second party and third party data, via traits acquired in the <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>. </p> <p> <p>팁: 1 일 룩백 기간과 함께 사용하는 경우 이 지표는 세그먼트의 현재 상태를 이해하는 데 도움이 될 수 있습니다. <span class="wintitle"> 세그먼트 지정 가능 대상</span> 지표는 이전 하루 동안 세그먼트에 머물렀던 사용자를 나타내기 때문입니다. <span class="keyword"> Audience Manager가</span> <span class="wintitle"> 지정 가능한 대상을</span> 매일 새로 고침한다는 사실과 함께 이 지표를 결합하면 이 지표와 lookback 기간이 세그먼트에 대한 최신 스냅샷을 제공합니다. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>총 세그먼트 모집단 수</b> </p> </td> 
   <td colname="col2"> <p>보고서 룩백 기간 동안 세그먼트의 구성원인 모든 장치의 수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>세그먼트 일치 비율</b> </p> </td> 
   <td colname="col2"> <p>세그먼트 지정 가능 대상 ÷ 총 세그먼트 모집단을 퍼센트로 나타낸 것입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Platform-Level Metrics {#platform-level-metrics}

이 지표는 모든 Audience Manager 고객 간에 수집된 활동에 대한 데이터를 반환합니다. 통합된 Audience Manager 고객과 비교하여 고객의 고객에 대한 광범위한 관점을 제공할 수 있습니다.

<table id="table_B6654D9858FF46AF95B1C181D4608D26"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 지표 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Audience Manager의 대응 가능 대상</b> </p> </td> 
   <td colname="col2"> <p>보고서 룩백 기간 동안 플랫폼 수준에서 모든 Audience Manager 고객과 상호 작용하고 선택한 대상에 일치할 수 있는 모든 장치의 수입니다. </p> <p>이 지표는 다음 사항을 표시하기 때문에 유용합니다. </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> <span class="keyword"> Audience Manager가 특정 타깃팅 대상에 도달할</span> 수 있는 총 지정 가능 대상의 크기입니다. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">How big the <span class="keyword"> Audience Manager</span> profile pool is for a targeting platform and the size of their audiences. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Comparing Customer and Segment Addressable Audiences{#comparing-metrics}

You shouldn&#39;t compare the [!UICONTROL Customer Addressable Audience] and [!UICONTROL Segment Addressable Audience] metrics to determine if one is more significant than the other. 이것은 별도의 지표, 서로 다른 지표 및 독립적인 지표입니다. 위의 정의에 설명된 바와 같이, 이 변수들 각각은 서로 다른 데이터 세트에서 파생됩니다. 따라서 한 지표가 다른 지표가 더 큰 경우 결론을 도출하지 마십시오. 비교할 때 다음과 같은 것이 가능합니다.

* [!UICONTROL Customer Addressable Audiences] 고유한 자사 데이터에 *대한 특성 구현을 기반으로*합니다. 이 지표는 데이터 파트너와의 통합에 대한 포괄적이고 포괄적인 보기를 제공합니다.

* [!UICONTROL Segment Addressable Audiences] 는 자사 데이터, 제 2 자 데이터 및 제 3 자 데이터의 세그먼트 자격 조건을 *기반으로*합니다. 이 지표는 타깃팅 플랫폼에서 지정 가능 대상을 세부적으로, 보다 정확하게 보여줍니다.

## Causes of Low Match Rates for Addressable Audiences {#low-match-rates}

Common elements responsible for low [!UICONTROL Addressable Audience] match rates or discrepancies in reported numbers.

<!-- addressable-audiences.xml -->

<table id="table_895D536F69134330A4F13887ECAFD4F5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> cause </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>모바일 트래픽</b> </p> </td> 
   <td colname="col2"> <p>대부분의 서버 간 통합은 타사 쿠키로 인한 동기화 프로세스에 의존합니다. 그러나 모바일 환경에서는 타사 쿠키를 사용하지 않습니다. 따라서 어드레서블 고객 수가 세그먼트 크기보다 낮게 보일 수 있습니다. </p> <p>2018 년 1 월 현재 쿠키 기반의 고객을 위해 설정한 동일한 Google 및 Adobe Advertising Cloud 대상에서 모바일 고객을 활성화할 수 있습니다. 이는 통합 쿠키 및 모바일 ID 멤버쉽이 있는 세그먼트를 Google 및 Advertising Cloud 대상으로 전송할 수 있음을 의미하지만, 주소 지정 가능 대상은 쿠키 ID와 대상 간의 중복만 표시합니다. Audience Manager는 모바일 대상의 100%를 대상으로 보내지만 모바일 대상은 지정 가능한 대상 지표로 측정되지 않습니다. </p> <p> <p><b></b>참고: 예를 들어 인구 수가 1,000,000 명인 세그먼트를 만듭니다. 이 세그먼트를 Google 또는 Adobe Advertising Cloud 대상에 매핑하면 700,000 명의 장치 및 70%의 일치 비율이 지정된 대상자를 볼 수 있습니다. 700,000 회원은 ID가 대상과 동기화된 ID ID로 구성됩니다. 주소 지정이 가능한 모바일 ID가 이 지표에 표시되지 않으므로 지정 가능 대상이 실제로 훨씬 더 높아질 수 있습니다. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Safari 트래픽</b> </p> </td> 
   <td colname="col2"> <p>Safari는 타사 쿠키를 차단합니다. 이렇게 하면 Audience Manager에서 ID를 대상과 동기화할 수 없습니다. <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>를 도입하면 어드레서블 고객이 Safari 사용자를 포함하지 않도록 할 수 있습니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>추적된 미디어 노출 횟수</b> </p> </td> 
   <td colname="col2"> <p>광고 서버 우수 사례에 따라 ID 동기화는 광고 태그 내에서 수행되지 않습니다. 오프사이트 광고를 대량으로 작업하는 고객은 이러한 환경에서 사용자를 서드파티 통합으로 동기화할 수 없습니다. 또한 수집된 많은 미디어 노출 데이터는 주소 지정이 가능한 대상 수를 줄일 수 있습니다. </p> </td>
  </tr> 
 </tbody> 
</table>

## Troubleshooting with Addressable Audiences {#troubleshooting}

In addition to surfacing match rates, you can also use [!UICONTROL Addressable Audiences] as a troubleshooting tool.

<!-- addressable-audiences-troubleshooting.xml -->

예를 들어 세그먼트를 대상으로 보내고 해당 대상에 낮은 보고 숫자가 표시되었다고 가정합니다. Checking the [!UICONTROL Addressable Audience] results will show you if this is a technical problem or just a case of low match rates. 낮은 일치 비율은 대상이 선택한 세그먼트에 적합하지 않다는 것을 보여줍니다. 하지만 Audience Manager와 대상 간 총 지정 가능 대상 수의 차이는 통합, 동기화 또는 기타 기술 문제를 나타냅니다. 이러한 경우 계정 관리자에게 문의하십시오.