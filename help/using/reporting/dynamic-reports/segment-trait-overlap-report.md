---
description: 특정 트레이트 및 전체 세그먼트 간에 공유되는 고유 사용자 수의 데이터를 반환합니다.
seo-description: 특정 트레이트 및 전체 세그먼트 간에 공유되는 고유 사용자 수의 데이터를 반환합니다.
seo-title: 세그먼트-특성 중복 보고서
solution: Audience Manager
title: 세그먼트-특성 중복 보고서
uuid: A 6 B 3 DD 21-332 E -449 F-AA 01-2 BEB 47 F 1794 E
translation-type: tm+mt
source-git-commit: 8f2ec880cbbe2f516ebc240a712337dc09c4e7f7

---


# 세그먼트-특성 중복 보고서{#segment-to-trait-overlap-report}

특정 트레이트 및 전체 세그먼트 간에 공유되는 고유 사용자 수의 데이터를 반환합니다.

>[!NOTE]
>
>Audience Manager의 겹침 보고서는 RBAC 원칙을 준수합니다. You can only see segments and traits from data sources that you have access to based on the [RBAC User Group](/help/using/features/administration/administration-overview.md) that you belong to.

<!-- 

c_segment_trait_overlap.xml

 -->

## 개요

As an optimization tool, the [!UICONTROL Segment to Trait Overlap] reports helps you build highly focused segments or expand segment reach. 예를 들어 초점이 높은 세그먼트와 특성을 만들어 특정 대상자에게 도달할 수 있습니다. 그러나 겹치는 부분이 많으면 고유 사용자 수가 줄어들 수 있습니다 (도달 수가 감소함). 이 보고서를 실행하면 많은 세그먼트 겹쳐 있는 트레이트를 제거하고 겹치는 특성이 있는 트레이트로 교체하여 도달 범위를 확장할 수 있습니다.

### 샘플 보고서

The following illustration provides a high-level overview of the [!UICONTROL Segment-to-Trait Overlap] report.

![](assets/segment-to-trait-overlap.png)

### 개별 데이터 포인트 드릴다운

팝업 창에서 데이터를 볼 개별 지점을 선택합니다. 클릭 동작은 보고서에 표시되는 데이터를 자동으로 업데이트합니다.

## Comparing Segments to Traits {#comparing-segments-to-traits}

세그먼트와 트레이트를 비교하여 결과에서 의미 있는 정보를 도출할 수 있는 방법을 설명합니다.

<!-- 

c_compare_s2t.xml

 -->

### 특성 및 세그먼트 고유 값 비교: 예

처음에는 세그먼트를 트레이트와 비교하고 결과를 도출하기 위한 시도를 하기 어려운 것 같습니다. 결국 세그먼트와 특징은 서로 다르므로 서로 다른 항목에서 파생된 데이터를 어떻게 의미합니까? 하지만 이 경우 트레이트와 세그먼트를 비교하지 않고 각 방문자 간에 공유된 고유 방문자의 수를 비교하지 않습니다. 공유된 고유 방문자 수는 세그먼트를 트레이트 비교를 가능하게 하는 일반적인 값을 제공합니다.

다음 다이어그램은 트레이트 및 세그먼트가 속한 세그먼트 간의 관계를 보여줍니다. 이 경우 10 명의 방문자로 구성된 트레이트 및 1,000 명의 방문자가 있는 세그먼트가 있습니다. 공통 방문자를 공통로 공유합니다.

![](assets/s2t.png)

고유 방문자 수는 이러한 여러 개체 클래스 간에 공유되는 공통된 상수 값입니다. 그 결과, 다음과 같이 고유한 방문자 관계를 결정할 수 있습니다.

* 트레이트 수는 고유 방문자의 30%를 세그먼트 (3/10 = 0.30) 와 공유합니다.
* 세그먼트는 고유 방문자의 0.3%를 특성 (3/1,000 = 0.003) 와 공유합니다.

### 세그먼트에서 트레이트 비교를 위한 가치 찾기

특성과 세그먼트 간 오버랩을 보면 사용 가능한 총 방문자 풀 (예측) 를 예상하거나 너무 겹치는 비효율적인 세그먼트를 찾을 수 있습니다.

<table id="table_5B211EF95216426299EB20253A5A9C1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 사용 사례 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>예측</b> </td> 
   <td colname="col2"> <p>사용 가능한 방문자 풀을 결정하려면 트레이트 합계 (중복) 와 세그먼트 합계 (중복 사항 낮음) 간의 차이를 합칩니다. </p> <p>이 세그먼트 특성 조합은 최대 1004 명의 신규 사용자에게 도달할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>비효율적인 세그먼트 찾기</b> </td> 
   <td colname="col2"> <p>If a trait is part of an <span class="wintitle"> AND</span> group in a segment definition, the unique visitors who have that trait are already in the segment and not available for adding to the segment. 이 보고서를 사용하여 낮은 오버랩으로 관련 트레이트를 찾고 세그먼트 정의에 추가하면 해당 세그먼트 대상 풀의 범위를 늘릴 수 있습니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Understanding the Data Filters in the Segment-to-Trait Overlap Report {#data-filters-s2t-report}

특성 및 세그먼트 고유 겹침 % 슬라이더가 작동하는 방식을 설명합니다.

<!-- 

r_s2t_sliders.xml

 -->

[!UICONTROL Segment-to-Trait overlap] 이 보고서를 사용하면 두 개의 슬라이더를 사용하여 특성 또는 세그먼트별로 겹치는 %를 기준으로 데이터를 필터링할 수 있습니다.

* **[!UICONTROL Filter Trait Uniques %:]** 트레이트 및 세그먼트 간에 공유되는 고유 방문자의 % 단위로 데이터를 필터링합니다.
* **[!UICONTROL Filter Segment Uniques Overlap %:]** 세그먼트와 트레이트 간에 고유 방문자의 % 단위로 데이터를 필터링합니다.

### 예

다음 다이어그램은 트레이트 고유 %와 세그먼트 고유 % 간의 차이를 보여줍니다. 이 경우 트레이트 및 세그먼트는 세 명의 고유 방문자를 공유합니다. 비율:

* 트레이트 수는 고유 방문자의 30%를 세그먼트 (3/10 = 0.30) 와 공유합니다.
* 세그먼트는 고유 방문자의 0.3%를 특성 (3/1,000 = 0.003) 와 공유합니다.

![](assets/s2t.png)

## Segment-to-Trait Data Pop Fields Defined {#fields-defined}

개별 데이터 포인트를 클릭할 때 팝업 창에 표시되는 지표를 설명합니다.

<!-- 

r_s2t_data_pop.xml

 -->

The popup for the [!UICONTROL Segment-to-Trait Overlap] report contains the metrics below. Note that the uniques metric in the table represents your *real-time users*.

<table id="table_4AF72754276242FFB11543635B43AD90"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 지표 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 세그먼트 ID</span></b> </td> 
   <td colname="col2"> 세그먼트에 대한 고유 숫자 ID. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 데이터 공급자 이름</span></b> </td> 
   <td colname="col2"> 세그먼트 소유자의 이름입니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 데이터 공급자 유형</span></b> </td> 
   <td colname="col2">속성이 속한 공급자 유형을 정의합니다. 다음 중 하나일 수 있습니다. 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">자사 (고유 특성). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">타사 (외부 데이터 파트너/공급업체). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> SID</span></b> </td> 
   <td colname="col2"> 세그먼트에 대한 고유 숫자 ID. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> SID 이름</span></b> </td> 
   <td colname="col2"> 세그먼트 이름입니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 특성 고유 방문자 겹침 %</span></b> </td> 
   <td colname="col2"> 고유 방문자 %의 %는 세그먼트와 공유됩니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 세그먼트 고유 겹침 %</span></b> </td> 
   <td colname="col2"> 세그먼트 공유의 고유 방문자 %. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 고유 방문자 수</span></b> </td> 
   <td colname="col2"> 세그먼트와 트레이트 간에 공유되는 고유 방문자 수. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 세그먼트 고유 방문자</span></b> </td> 
   <td colname="col2"> 세그먼트에 있는 고유 방문자 수. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 특성 고유 방문자</span></b> </td> 
   <td colname="col2"> 트레이트의 고유 방문자 수. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ like_ this]
>
>* [데이터 슬라이더를 사용하여 보고서 결과 필터링](../../reporting/dynamic-reports/data-sliders.md)
>* [대화형 보고서에 사용된 모양, 색상 및 크기](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [보고서 아이콘 및 도구 설명](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [겹침 보고서: 업데이트 예약 및 최소 세그먼트 크기](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [선택한 Audience Manager 보고서에서 데이터 샘플링 및 오류율...](../../reporting/report-sampling.md)
>* [중복 보고서에 대한 CSV 파일](../../reporting/dynamic-reports/overlap-csv-files.md)