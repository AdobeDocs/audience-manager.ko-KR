---
description: 어드레서블 대상 기능 및 사용 사례에 대한 개요입니다.
keywords: DIL
seo-description: 어드레서블 대상 기능 및 사용 사례에 대한 개요입니다.
seo-title: 대응 가능 대상
solution: Audience Manager
title: 대응 가능 대상
topic: DIL API
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
translation-type: tm+mt
source-git-commit: b213a1ecde4c85dc66dada24dec602ed1d9b0332

---


# 주소 지정 가능한 고객 {#addressable-audiences}

어드레서블 대상 기능 및 사용 사례에 대한 개요입니다.

## 주소 지정 가능 고객이란? {#addressable-audience-description}

이 [!UICONTROL Addressable Audiences] 기능은 데이터를 수집하는 모든 속성에서 표시되는 대상과 선택한 대상 간에 겹치는 [!DNL Audience Manager] 것을 보여줍니다. 이 개념을 이해하려면 아래 그림을 참조하십시오. 각 원 간의 겹치는 서로 다른 유형의 지정 가능한 대상을 나타냅니다.

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
   <td colname="col1"> <p> <b>대상에 대한 Audience Manager의 주소 지정 가능 대상</b> </p> </td> 
   <td colname="col2"> <p>보고서 룩백 기간 동안 플랫폼 수준에서 모든 Audience Manager 고객과 상호 작용했으며 선택한 대상과 일치할 수 있는 모든 장치의 수입니다. </p> <p>이 지표는 다음과 같이 표시되므로 유용합니다. </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> Audience Manager가 특정 타깃팅 <span class="keyword"> 대상에 도달할</span> 수 있는 총 주소 지정 가능 대상의 크기. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">타깃팅 <span class="keyword"> 플랫폼용 Audience</span> Manager 프로필 풀의 크기와 대상 크기입니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>고객 총 고객 수</b> </p> </td> 
   <td colname="col2"> <p>룩백 창 동안 속성에 대한 규칙 기반 트레이트 또는 오프라인 파일에서 온보드 트레이트를 구현한 장치 수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>주소 지정 가능한 대상 일치 비율</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>다시 보기 창에서 규칙 기반 트레이트 또는 온보드 트레이트를 구현한 장치 및 동기화 시간에 관계없이 선택한 대상과 ID를 동기화하는 장치의 오버랩 수입니다. </p> 
    </draft-comment> <p>이 지표는 다음과 같은 장치를 나타냅니다. 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">다시 보기 창에서 규칙 기반 트레이트나 온보드 트레이트를 구현했습니다. <b>AND</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">동기화 시간에 관계없이 선택한 대상과 ID를 동기화합니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>고객 일치 비율</b> </p> </td> 
   <td colname="col2"> <p>고객 주소 지정 가능 대상자 ?고객 총 대상자 %로 표시되었습니다. </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <b>총 세그먼트 모집단</b> </p> </td> 
   <td colname="col2"> <p>보고서 검색 기간 동안 세그먼트의 구성원이었던 모든 장치의 수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>세그먼트 주소 지정 가능 대상</b> </p> </td> 
   <td colname="col2"> <p>보고서 검색 기간 동안 세그먼트에 소속되어 있고 사이트에서 활성 ID를 동기화한 사용자 수입니다. 세그먼트에는 Audience Marketplace에서 확보한 트레이트를 통해 자사 데이터와 제3자 및 제3자 데이터가 포함될 수 <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> 있습니다</a>. </p> <p> <p>팁:1일 뒤로 보기 기간과 함께 사용하면 이 지표를 통해 세그먼트의 현재 상태를 이해할 수 있습니다. 이는 세그먼트 주소 지정 <span class="wintitle"> 가능 대상</span> 지표가 전날 세그먼트에 있었던 사용자를 나타내기 때문입니다. Audience Manager가 <span class="keyword"> 매일</span> 주소 지정 가능 대상을 <span class="wintitle"></span> 새로 고침한다는 점과 이 지표와 조회 기간을 결합하면 세그먼트에 대한 최신 스냅샷을 제공할 수 있다는 사실을 결합합니다. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>세그먼트 일치 비율</b> </p> </td> 
   <td colname="col2"> <p>세그먼트 주소 지정 가능 대상자 ?총 세그먼트 모집단 이 %로 표현되었습니다. </p> </td> 
  </tr>  
 </tbody> 
</table>

## 주소 지정 가능한 대상 인터페이스 {#addressable-audience-interface}

이 [!UICONTROL Addressable Audience] 기능은 이 추상적인 개념을 수량화 가능한 데이터로 변환합니다. 이 [!DNL Audience Manager]기능은 테이블 형식의 숫자 데이터와 함께 한눈에 정보를 제공하는 데이터 시각화와 겹치는 대상을 표시합니다.

[!UICONTROL Addressable Audiences] 에 **[!UICONTROL Audience Data > Destinations]**&#x200B;있습니다. 지정 가능한 대상 지표를 **[!UICONTROL Integrated Platforms > Device-Based]** 보려면 선택합니다.

![](assets/addressable-audiences-landing.png)

지정 가능 대상자 랜딩 페이지에서 볼 수 있는 세 가지 지표는 다음과 같습니다.

| 지표 | 설명 |
---------|----------|
| **주소 지정 가능 대상(디바이스)** | 이 지표는 지난 30일 *동안 고객 주소 지정 가능 대상자(위 표에 설명됨)를 나타냅니다.* |
| **일치 비율** | 이 지표는 지난 30일 **&#x200B;동안 지정 가능한 대상 일치율(위 표에 설명됨)을 나타냅니다. |
| **라이프타임 주소 지정 가능 대상(디바이스)** | 보고서 룩백 기간 동안 플랫폼 수준에서 모든 Audience Manager 고객과 상호 작용했으며 이 대상과 일치할 수 있는 모든 장치의 수입니다. 자세한 [내용은 플랫폼 수준](/help/using/features/addressable-audiences.md#platform-level-metrics) 지표를 참조하십시오. |

주소 지정 가능한 대상 데이터를 보려면 서버 간 대상 이름을 클릭합니다. 이 기능은 서버 간 대상에 대한 데이터만 반환하고 액세스 권한에는 관리자 권한이 필요합니다.

![](assets/addressableAudiences.png)

이 데이터를 검토하면 다음과 같은 이점을 얻을 수 있습니다.

* **** 예측 및 계획:데이터를 [!UICONTROL Segment Addressable Audience] 사용하면 대상 타깃팅 및 활성화를 위해 대상으로 전송하려는 세그먼트를 세부적으로 파악할 수 있습니다.

* **** 성능 평가:이 [!UICONTROL Addressable Audiences] 기능은 문제 해결 툴이기도 합니다. 캠페인 성과를 검토하고 캠페인 도달 수를 파악할 수 있으며, 원하는 결과가 표시되지 않는 경우 타깃팅/활성화 파트너와 상호 확인할 수 있습니다.

### 서드 파티 데이터를 통한 전망 및 일치율

고객 확보를 위해 타사 데이터를 구매하기 전에 고객은 다른 데이터 공급자와의 중복 여부를 확인할 수 있습니다. 이를 통해 새로운 데이터를 구매하기 전에 현명한 결정을 내릴 수 있습니다. ID는 구입한 타사 데이터에 대해 동기화되므로 데이터가 중복될 뿐만 아니라 타사 제공업체의 다른 모든 [!DNL Audience Manager] 고객과의 발자취에도 의존합니다. 컨설턴트는 [!DNL Adobe] 고객의 관심사와 연관성 있는 추가 데이터 소스를 파악하여 잠재 고객 캠페인을 최적화할 수 있도록 지원합니다.

### 모바일 사용자 및 일치율

타사 쿠키가 없는 경우 [!DNL Safari] 또는 모바일 앱 사용자를 연결하려고 할 때 간격이 있습니다. 동기화된 타사 쿠키에 대한 ID만 미디어 배달 로그에 제공되므로 일부 [!DNL Adobe] 파트너와 사용자를 동기화하기가 어렵습니다. 이러한 이유로 귀하의 대상에 대해 [낮은 일치율을](../features/addressable-audiences.md#low-match-rates) 볼 수 있습니다.

## 지정 가능 대상 및 대상의 날짜 범위 {#date-ranges}

사용 가능한 날짜 범위 및 [!UICONTROL Addressable Audience] 또는 [!UICONTROL Destination]에 대한 보고서의 각 간격에서 데이터 사용 방법을 아래 섹션을 참조하십시오.

## 사용 가능한 날짜 범위 및 시간대 {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

사용자 [!UICONTROL Addressable Audiences] 및 [대상에 대한](../features/destinations/destinations.md) 보고서는 동일한 날짜 범위 간격을 사용합니다. 날짜 범위 옵션은 다음과 같습니다.

* [!UICONTROL Last 1 Day] (이 간격은 이전 24시간 기간의 자정부터 자정까지 실행됩니다. 이것은 실시간 또는 현재 시간 지표가 아닙니다.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

모든 날짜 및 날짜 범위는 [!DNL UTC] 표준 시간대에서 설정됩니다. Audience [Manager의 시간대를 참조하십시오](../reference/aam-time-zones.md).

## 날짜 범위 간격의 데이터 {#date-range-intervals}

및 [!UICONTROL Addressable Audience] [!UICONTROL Destination] 지표는 선택한 시간 간격에 대한 고유 사용자 수를 반환합니다. 예를 들어 방문자가 여러 번 사이트를 방문하는 경우에도 한 번만 카운트됩니다. 첫 번째 방문은 고유한 방문으로 기록됩니다. 이후 방문은 재방문되며 고유하지 않기 때문에 카운트되지 않습니다.

날짜 범위에는 선택한 시간 간격 또는 이전 버전의 데이터가 포함됩니다. 또한 데이터가 시간이 지남에 따라 각 보고서 간격에서 연장됩니다. 예를 들어 [!UICONTROL Last 30 Days] 옵션을 선택한 후 2명의 방문자가 있다고 가정합니다. 보고서에서 이러한 방문자는 다음과 같습니다.

* *더 긴 시간 간격(60일, 90일 및 라이프타임)이 반환되는 결과에 포함됩니다* .
* *옵션 앞에 오는 짧은 간격(현재* , 7일 및 14일)에 포함되지 않습니다 [!UICONTROL Last 30 Day] .

그리고 31일에 이 방문자는 60일, 90일, 그리고 [!UICONTROL Lifetime] 결과만 표시됩니다. 그들은 30일의 간격을 벗어나게 되었다. 방문자는 [!UICONTROL Lifetime] 시간 간격을 벗어나지 않습니다.

##  주소 지정 가능한 고객 지표 {#addressable-audience-metrics}

이 섹션에서는 에서 제공하는 지표 유형을 [!UICONTROL Addressable Audiences]설명합니다.

### 고객 수준 지표 {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

이러한 지표는 방문자가 사이트를 방문하거나 인바운드 데이터 파일을 보낼 때 발생한 트레이트에 대한 데이터를 [!DNL Audience Manager]반환합니다. 이러한 지표는 계정에 대한 대상 크기를 종합적으로 볼 수 있도록 해줍니다.

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 지표 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>고객 주소 지정 가능 고객</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>다시 보기 창에서 규칙 기반 트레이트 또는 온보드 트레이트를 구현한 장치 및 동기화 시간에 관계없이 선택한 대상과 ID를 동기화하는 장치의 오버랩 수입니다. </p> 
    </draft-comment> <p>이 지표는 다음과 같은 장치를 나타냅니다. 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">다시 보기 창에서 규칙 기반 트레이트나 온보드 트레이트를 구현했습니다. <b>AND</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">동기화 시간에 관계없이 선택한 대상과 ID를 동기화합니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>고객 총 고객 수</b> </p> </td> 
   <td colname="col2"> <p>룩백 창 동안 속성에 대한 규칙 기반 트레이트 또는 오프라인 파일에서 온보드 트레이트를 구현한 장치 수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>고객 일치 비율</b> </p> </td> 
   <td colname="col2"> <p>고객 주소 지정 가능 대상자 ?고객 총 대상자 %로 표시되었습니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

### 세그먼트 수준 일치 지표 {#segment-level-metrics}

이러한 지표는 세그먼트 멤버십에 대한 데이터를 반환합니다. 이러한 기능을 사용하면 각 세그먼트에 대한 고객 규모를 보다 세밀하고 정확하게 파악할 수 있습니다.

>[!NOTE]
>
>세그먼트 수준에서 다시 보기 창이 적용되는 방식은 고객 수준에서 적용되는 방법과 다릅니다. 방문자는 사이트를 방문하여 10일 전에 트레이트를 인식할 수 있으며, 그 이후 세그먼트에 대한 자격을 갖추었고 2일 전에 세그먼트에서 제외될 수 있습니다. 7일 룩백이 적용되면 이러한 방문자는 세그먼트 수준에서 계산되지만 고객 수준에서는 계산되지 않습니다.

<table id="table_4185AA02CC774B6C93B02E45F88BBBD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 지표 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>세그먼트 주소 지정 가능 대상</b> </p> </td> 
   <td colname="col2"> <p>보고서 검색 기간 동안 세그먼트에 소속되어 있고 사이트에서 활성 ID를 동기화한 사용자 수입니다. 세그먼트에는 Audience Marketplace에서 확보한 트레이트를 통해 자사 데이터와 제3자 및 제3자 데이터가 포함될 수 <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> 있습니다</a>. </p> <p> <p>팁:1일 뒤로 보기 기간과 함께 사용하면 이 지표를 통해 세그먼트의 현재 상태를 이해할 수 있습니다. 이는 세그먼트 주소 지정 <span class="wintitle"> 가능 대상</span> 지표가 전날 세그먼트에 있었던 사용자를 나타내기 때문입니다. Audience Manager가 <span class="keyword"> 매일</span> 주소 지정 가능 대상을 <span class="wintitle"></span> 새로 고침한다는 점과 이 지표와 조회 기간을 결합하면 세그먼트에 대한 최신 스냅샷을 제공할 수 있다는 사실을 결합합니다. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>총 세그먼트 모집단</b> </p> </td> 
   <td colname="col2"> <p>보고서 검색 기간 동안 세그먼트의 구성원이었던 모든 장치의 수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>세그먼트 일치 비율</b> </p> </td> 
   <td colname="col2"> <p>세그먼트 주소 지정 가능 대상자 ?총 세그먼트 모집단 이 %로 표현되었습니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

### 플랫폼 수준 지표 {#platform-level-metrics}

이 지표는 모든 Audience Manager 고객 전체에서 수집된 활동에 대한 데이터를 반환합니다. 또한 통합된 Audience Manager 고객과 비교하여 고객의 전체 상황을 파악할 수 있습니다.

<table id="table_B6654D9858FF46AF95B1C181D4608D26"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 지표 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Audience Manager의 어드레서블 대상</b> </p> </td> 
   <td colname="col2"> <p>보고서 룩백 기간 동안 플랫폼 수준에서 모든 Audience Manager 고객과 상호 작용했으며 선택한 대상과 일치할 수 있는 모든 장치의 수입니다. </p> <p>이 지표는 다음과 같이 표시되므로 유용합니다. </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> Audience Manager가 특정 타깃팅 <span class="keyword"> 대상에 도달할</span> 수 있는 총 주소 지정 가능 대상의 크기. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">타깃팅 <span class="keyword"> 플랫폼용 Audience</span> Manager 프로필 풀의 크기와 대상 크기입니다. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 고객 및 세그먼트 주소 지정 가능 대상 비교{#comparing-metrics}

지표 [!UICONTROL Customer Addressable Audience] 및 [!UICONTROL Segment Addressable Audience] 지표를 비교하여 지표가 다른 지표보다 중요한지 판단해서는 안 됩니다. 이러한 지표는 별개이며, 다르고, 독립적인 지표입니다. 위의 정의에 설명된 바와 같이 각 데이터 세트는 서로 다른 데이터 세트에서 파생됩니다. 이 경우 한 지표가 다른 지표보다 큰 경우 결론을 도출하지 않아야 합니다. 이것들을 비교할 때 당신이 말할 수 있는 것은 다음과 같습니다.

* [!UICONTROL Customer Addressable Audiences] 는 자사 데이터에 *대한 특성*&#x200B;실현에 기반합니다. 이 지표는 데이터 파트너와의 통합에 대한 광범위하고 포괄적인 보기를 제공합니다.

* [!UICONTROL Segment Addressable Audiences] 는 자사 데이터에 *대한 세그먼트 자격 조건과 제휴 데이터와*&#x200B;타사 데이터를 기반으로 합니다. 이 지표는 타깃팅 플랫폼에서 주소 지정 가능한 대상을 보다 정확하고 세밀하게 볼 수 있도록 해줍니다.

## 지정 가능한 대상의 낮은 일치율 원인 {#low-match-rates}

보고된 숫자의 낮은 [!UICONTROL Addressable Audience] 일치율 또는 불일치를 책임지는 일반적인 요소입니다.

<!-- addressable-audiences.xml -->

<table id="table_895D536F69134330A4F13887ECAFD4F5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 원인 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>모바일 트래픽</b> </p> </td> 
   <td colname="col2"> <p>대부분의 서버 대 서버 통합은 타사 쿠키의 동기화 프로세스에 의존합니다. 그러나 모바일 환경에서는 타사 쿠키를 사용하지 않습니다. 따라서 지정 가능한 대상 수가 세그먼트 크기와 비교하여 낮은 것으로 보일 수 있습니다. </p> <p>2018년 1월 현재 쿠키 기반 고객을 위해 설정된 동일한 Google 및 Adobe Advertising Cloud 대상에서 모바일 고객을 활성화할 수 있습니다. 즉, 쿠키 및 모바일 ID 멤버십이 결합된 세그먼트를 Google 및 Advertising Cloud 대상으로 보낼 수 있습니다. 따라서 주소 지정 가능 대상은 쿠키 ID와 대상 간의 겹치만 표시된다는 점을 염두에 두십시오. Audience Manager는 모바일 대상의 100%를 대상으로 전송하지만 모바일 대상은 지정 가능 대상 지표로 측정되지 않습니다. </p> <p> <p><b>참고</b>: 예를 들어 모집단 수가 1,000,000인 세그먼트를 만듭니다. 이 세그먼트를 Google 또는 Adobe Advertising Cloud 대상에 매핑하면 700,000개의 장치의 주소 지정 가능 대상 및 70%의 일치율을 볼 수 있습니다. 700,000의 멤버십은 대상과 ID를 동기화하는 쿠키 ID로 구성됩니다. 주소 지정 가능 모바일 ID는 이 지표에 나타나지 않으므로 실제로 더 높은 수가 있을 수 있습니다. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Safari 트래픽</b> </p> </td> 
   <td colname="col2"> <p>Safari는 타사 쿠키를 차단합니다. 이렇게 하면 Audience Manager가 ID를 대상과 동기화할 수 없습니다. ITP 2.0 <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> 의</a>도입으로 Safari 사용자는 지정 가능한 고객에게 포함되지 않을 수 있습니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>추적된 미디어 노출 수</b> </p> </td> 
   <td colname="col2"> <p>광고 서버 우수 사례로 인해 ID 동기화는 광고 태그 내에서 만들어지지 않습니다. 오프사이트 광고를 많이 하는 고객은 해당 환경의 타사 통합에 사용자를 동기화하지 않습니다. 또한 대량의 미디어 노출 데이터를 수집하면 주소 지정 가능한 고객 수를 줄일 수 있습니다. </p> </td>
  </tr> 
 </tbody> 
</table>

## 지정 가능한 대상을 사용한 문제 해결 {#troubleshooting}

일치 비율을 표시할 뿐만 아니라 문제 해결 [!UICONTROL Addressable Audiences] 도구로 사용할 수도 있습니다.

<!-- addressable-audiences-troubleshooting.xml -->

예를 들어 세그먼트를 대상에 전송하면 해당 대상에 낮은 보고 수가 표시됩니다. 이 [!UICONTROL Addressable Audience] 결과가 기술적 문제인지 또는 낮은 일치율인지 여부를 확인하면 표시됩니다. 낮은 일치 비율은 선택한 세그먼트에 대해 대상이 그리 좋지 않다는 것을 보여줍니다. 그러나 Audience Manager와 대상 간의 주소 지정이 가능한 총 고객 수의 차이는 통합, 동기화 또는 기타 기술 문제를 나타냅니다. 이러한 경우 계정 관리자에게 문의하십시오.