---
description: 특정 트레이트와 전체 세그먼트 간에 공유된 고유 사용자 수에 대한 데이터를 반환합니다.
seo-description: Returns data on the number of unique users shared between a particular trait and an entire segment.
seo-title: Segment-to-Trait Overlap Report
solution: Audience Manager
title: 세그먼트-특성 중복 보고서
uuid: a6b3dd21-332e-449f-aa01-2beb47f1794e
feature: Overlap Reports
exl-id: 7ce3dd2d-ab22-46f8-90bf-a32222df2e76
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 3%

---

# 세그먼트-특성 중복 보고서{#segment-to-trait-overlap-report}

특정 트레이트와 전체 세그먼트 간에 공유된 고유 사용자 수에 대한 데이터를 반환합니다.

>[!NOTE]
>
>Audience Manager의 겹치기 보고서는 RBAC 원칙을 준수합니다. 사용자가 속한 [RBAC 사용자 그룹](/help/using/features/administration/administration-overview.md)을(를) 기반으로 액세스 권한이 있는 데이터 원본의 세그먼트와 트레이트만 볼 수 있습니다.

<!-- 

c_segment_trait_overlap.xml

 -->

## 개요

최적화 도구로서 [!UICONTROL Segment to Trait Overlap] 보고서를 사용하면 집중도가 높은 세그먼트를 작성하거나 세그먼트 범위를 확장할 수 있습니다. 예를 들어, 특정 대상에게 도달하기 위해 겹치는 정도가 높은 집중 세그먼트 및 트레이트를 만들 수 있습니다. 그러나 겹치는 부분이 많으면 고유 사용자가 적을 수 있습니다(도달 범위가 적을 수 있음). 세그먼트 겹침이 많은 트레이트를 제거하고 겹침이 적은 트레이트로 대체하여 도달 범위를 확장하는 데 도움이 되도록 이 보고서를 실행합니다.

### 샘플 보고서

다음 그림에서는 [!UICONTROL Segment-to-Trait Overlap] 보고서에 대한 높은 수준의 개요를 제공합니다.

![](assets/segment-to-trait-overlap.png)

### 개별 데이터 포인트 드릴다운

개별 포인트를 선택하여 팝업 창에서 데이터 세부 정보를 봅니다. 클릭 작업은 보고서에 표시된 데이터를 자동으로 업데이트합니다.

## 세그먼트와 트레이트 비교 {#comparing-segments-to-traits}

세그먼트와 트레이트를 비교하여 결과에서 의미 있는 정보를 도출하는 방법에 대해 설명합니다.

<!-- 

c_compare_s2t.xml

 -->

### 트레이트 및 세그먼트 고유 비교: 예제

세그먼트를 트레이트에 비교하고 결과에서 결론을 도출하려는 것은 언뜻 보기에 비논리적으로 보일 수 있다. 결국, 세그먼트와 트레이트가 다르므로, 서로 다른 항목에서 파생된 데이터가 어떻게 의미를 가질 수 있는가? 그러나 이 경우 트레이트와 세그먼트를 비교하는 것이 아니라 공유한 고유 방문자의 수를 비교합니다. 공유된 고유 방문자 수는 세그먼트와 트레이트 비교를 가능하게 하는 공통 값을 제공합니다.

다음 다이어그램은 트레이트와 해당 트레이트가 속한 세그먼트 간의 관계를 보여 줍니다. 이 경우 방문자가 10명인 트레이트와 방문자가 1,000명인 세그먼트가 있습니다. 세 명의 고유 방문자를 공통으로 공유합니다.

![](assets/s2t.png)

고유 방문자 수는 이러한 서로 다른 객체 클래스 간에 공유되는 공통된 상수 값입니다. 그 결과, 다음과 같이 방문자 간의 고유한 방문자 관계를 결정할 수 있습니다.

* 트레이트는 고유 방문자 수의 30%를 세그먼트와 공유합니다(3/10 = 0.30).
* 이 세그먼트는 고유 방문자 수 0.3%를 트레이트와 공유합니다(3/1,000 = 0.003)

### 세그먼트 대 트레이트 비교에서 값 찾기

트레이트와 세그먼트 간의 겹침을 확인하면 사용 가능한 총 방문자 풀(예측)을 예측하거나 겹치는 부분이 너무 많은 비효율적인 세그먼트를 찾는 데 도움이 될 수 있습니다.

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
   <td colname="col2"> <p>사용 가능한 방문자 풀을 결정하려면 트레이트 합계(적게 겹침)와 세그먼트 합계(적게 겹침) 간의 차이를 합합니다. </p> <p>이 세그먼트-트레이트 조합은 최대 1004명의 신규 사용자에게 도달할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>비효율적인 세그먼트 찾기</b> </td> 
   <td colname="col2"> <p>트레이트가 세그먼트 정의에서 <span class="wintitle"> AND</span> 그룹의 일부인 경우 해당 트레이트를 가진 고유 방문자는 이미 세그먼트에 있으므로 세그먼트에 추가할 수 없습니다. 이 보고서를 사용하여 겹치는 정도가 낮은 관련 트레이트를 찾아 세그먼트 정의에 추가할 수 있으므로 해당 세그먼트 대상자 풀의 도달 범위를 늘릴 수 있습니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 세그먼트-특성 중복 보고서의 데이터 필터 이해 {#data-filters-s2t-report}

트레이트 및 세그먼트 고유 겹치기 % 슬라이더가 작동하는 방식을 설명합니다.

<!-- 

r_s2t_sliders.xml

 -->

[!UICONTROL Segment-to-Trait overlap] 보고서를 사용하면 두 개의 슬라이더를 사용하여 특성 또는 세그먼트별로 겹침(%)을 기준으로 데이터를 필터링할 수 있습니다.

* **[!UICONTROL Filter Trait Uniques %:]**&#x200B;은(는) 트레이트와 세그먼트 사이에 공유되는 고유 방문자 수의 %로 데이터를 필터링합니다.
* **[!UICONTROL Filter Segment Uniques Overlap %:]**&#x200B;은(는) 세그먼트와 트레이트 간 고유 방문자 공유의 %로 데이터를 필터링합니다.

### 예

다음 다이어그램은 트레이트 고유 비율(%)과 세그먼트 고유 비율(%)의 차이를 보여 줍니다. 이 경우 트레이트 및 세그먼트는 3명의 고유 방문자를 공유합니다. 비율로:

* 트레이트는 고유 방문자 수의 30%를 세그먼트와 공유합니다(3/10 = 0.30).
* 이 세그먼트는 고유 방문자 수 0.3%를 트레이트와 공유합니다(3/1,000 = 0.003)

![](assets/s2t.png)

## 세그먼트-특성 데이터 팝 필드 정의됨 {#fields-defined}

개별 데이터 포인트를 클릭할 때 팝업 창에 표시되는 지표에 대해 설명합니다.

<!-- 

r_s2t_data_pop.xml

 -->

[!UICONTROL Segment-to-Trait Overlap] 보고서에 대한 팝업에 아래 지표가 포함되어 있습니다. 테이블의 고유 수 지표는 *실시간 사용자*&#x200B;를 나타냅니다.

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
   <td colname="col2"> 세그먼트에 대한 고유 숫자 ID입니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 트레이트 데이터 Source </span></b> </td> 
   <td colname="col2"> 트레이트 소유자의 이름입니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 데이터 Source 형식</span></b> </td> 
   <td colname="col2">트레이트가 속한 공급자 유형을 정의합니다. 다음 중 하나일 수 있습니다. 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">자사(고유한 트레이트). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">외부 데이터 파트너/공급업체의 타사. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 트레이트 ID</span></b> </td> 
   <td colname="col2"> 트레이트에 대한 고유 숫자 ID입니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 트레이트 이름</span></b> </td> 
   <td colname="col2"> 트레이트 이름. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 트레이트 고유 겹치기 %</span></b> </td> 
   <td colname="col2"> 트레이트가 세그먼트와 공유하는 고유 방문자 수의 %입니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 세그먼트 고유 수 겹침 %</span></b> </td> 
   <td colname="col2"> 세그먼트가 트레이트와 공유하는 고유 방문자 수(%)입니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 중복 고유</span></b> </td> 
   <td colname="col2"> 세그먼트와 트레이트 간에 공유된 고유 방문자 수입니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 세그먼트 고유 수</span></b> </td> 
   <td colname="col2"> 세그먼트의 고유 방문자 수입니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1">트레이트 고유 수 <b><span class="wintitle">개</span></b> </td> 
   <td colname="col2"> 트레이트의 고유 방문자 수입니다. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [데이터 슬라이더를 사용하여 보고서 결과 필터링](../../reporting/dynamic-reports/data-sliders.md)
>* 대화형 보고서에 사용되는 [모양, 색 및 크기](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [보고서 아이콘 및 도구 설명](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Overlap Reports: 일정 및 최소 세그먼트 크기 업데이트](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [선택한 Audience Manager 보고서의 데이터 샘플링 및 오류율...](../../reporting/report-sampling.md)
>* [Overlap Reports에 대한 CSV 파일](../../reporting/dynamic-reports/overlap-csv-files.md)
