---
description: 특정 트레이트와 전체 세그먼트 간에 공유된 고유한 사용자 수의 데이터를 반환합니다.
seo-description: 특정 트레이트와 전체 세그먼트 간에 공유된 고유한 사용자 수의 데이터를 반환합니다.
seo-title: 세그먼트-특성 Overlap Reports
solution: Audience Manager
title: 세그먼트-특성 Overlap Reports
uuid: a6b3dd21-332e-449f-aa01-2beb47f1794e
feature: Overlap Reports
exl-id: 7ce3dd2d-ab22-46f8-90bf-a32222df2e76
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '832'
ht-degree: 5%

---

# 세그먼트-특성 Overlap Reports{#segment-to-trait-overlap-report}

특정 트레이트와 전체 세그먼트 간에 공유된 고유한 사용자 수의 데이터를 반환합니다.

>[!NOTE]
>
>Audience Manager의 중복 보고서는 RBAC 원칙을 따릅니다. 사용자가 속한 [RBAC 사용자 그룹](/help/using/features/administration/administration-overview.md)을 기반으로 액세스할 수 있는 데이터 소스의 세그먼트와 트레이트만 볼 수 있습니다.

<!-- 

c_segment_trait_overlap.xml

 -->

## 개요

최적화 도구인 [!UICONTROL Segment to Trait Overlap] 보고서를 사용하면 집중도가 높은 세그먼트를 만들거나 세그먼트 범위를 확장할 수 있습니다. 예를 들어 중점 세그먼트와 비율이 높은 트레이트를 만들어 특정 대상에게 도달할 수 있습니다. 그러나 겹치는 부분이 많으면 고유 사용자 수가 적어질 수 있습니다(도달 수 감소). 많은 세그먼트가 겹치는 트레이트를 제거하고 겹치지 않는 트레이트로 대체하여 도달 범위를 확장하는 데 도움이 되도록 이 보고서를 실행합니다.

### 샘플 보고서

다음 그림은 [!UICONTROL Segment-to-Trait Overlap] 보고서의 수준 높은 개요를 제공합니다.

![](assets/segment-to-trait-overlap.png)

### 개별 데이터 포인트 드릴다운

팝업 창에서 데이터 세부 사항을 보려면 개별 점을 선택합니다. 클릭 작업은 보고서에 표시된 데이터를 자동으로 업데이트합니다.

## 세그먼트를 트레이트 {#comparing-segments-to-traits}과 비교

결과와 의미 있는 정보를 도출하기 위해 세그먼트와 트레이트를 비교할 수 있는 방법을 설명합니다.

<!-- 

c_compare_s2t.xml

 -->

### 트레이트 및 세그먼트 고유 수 비교:예

처음에 세그먼트를 트레이트와 비교하여 결과로부터 결론을 도출하려는 것은 비논리적인 것으로 보일 수 있습니다. 결국 세그먼트와 트레이트는 다르므로, 서로 다른 항목에서 도출된 데이터에 어떤 의미를 부여할 수 있습니까? 하지만 이 경우 트레이트와 세그먼트를 비교하지 않고 이 두 방문자 간에 공유된 고유 방문자 수를 비교합니다. 공유 고유 방문자 수는 세그먼트를 트레이트 비교를 가능하게 하는 공통 값을 제공합니다.

다음 다이어그램은 트레이트와 해당 트레이트가 속한 세그먼트 간의 관계를 보여 줍니다. 이 경우 방문자가 10명이고 방문자가 1,000명인 세그먼트가 있습니다. 3명의 고유 방문자를 공통으로 공유합니다.

![](assets/s2t.png)

고유 방문자 수는 이러한 서로 다른 객체 클래스 간에 공유되는 일반적인 상수 값입니다. 그 결과 다음과 같이 이러한 방문자 간의 고유 방문자 관계를 결정할 수 있습니다.

* 이 트레이트는 고유 방문자의 30%를 세그먼트(3/10 = 0.30)와 공유합니다.
* 이 세그먼트는 고유 방문자의 0.3%를 트레이트와 공유합니다(3/1,000 = 0.003).

### 세그먼트에서 트레이트 비교에 대한 값 찾기

트레이트와 세그먼트 간의 오버랩을 보면 총 사용 가능한 방문자 풀(예측)을 예상하거나 너무 겹치는 비효율적인 세그먼트를 찾을 수 있습니다.

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
   <td colname="col2"> <p>사용 가능한 방문자 풀을 결정하려면 트레이트 합계(겹치지 않음)와 세그먼트 합계(덜 겹침) 간의 차이를 합합니다. </p> <p>이 세그먼트 트레이트 조합은 최대 1004명의 신규 사용자에게 도달할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>비효율적인 세그먼트 찾기</b> </td> 
   <td colname="col2"> <p>트레이트가 세그먼트 정의에서 <span class="wintitle"> AND</span> 그룹의 일부인 경우 해당 트레이트를 가진 고유 방문자는 이미 세그먼트에 있으며 세그먼트에 추가할 수 없습니다. 이 보고서를 사용하여 오버랩이 낮은 관련 트레이트를 찾아 세그먼트 정의에 추가하여 해당 세그먼트 대상 풀의 범위를 늘릴 수 있습니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 세그먼트에서 트레이트로 겹치기 보고서의 데이터 필터 이해 {#data-filters-s2t-report}

트레이트 및 세그먼트 고유 겹침 % 슬라이더의 작동 방식을 설명합니다.

<!-- 

r_s2t_sliders.xml

 -->

[!UICONTROL Segment-to-Trait overlap] 보고서에서는 두 개의 슬라이더를 사용하여 트레이트 또는 세그먼트별로 겹치는 %의 데이터를 필터링할 수 있습니다.

* **[!UICONTROL Filter Trait Uniques %:]** 트레이트와 세그먼트 간에 공유된 고유 방문자 수의 %에 따라 데이터를 필터링합니다.
* **[!UICONTROL Filter Segment Uniques Overlap %:]** 세그먼트와 트레이트 간에 공유되는 고유 방문자 수의 %에 따라 데이터를 필터링합니다.

### 예

다음 다이어그램은 트레이트 고유 수 %와 세그먼트 고유 수 %의 차이를 보여줍니다. 이 경우 트레이트와 세그먼트는 3명의 고유 방문자를 공유합니다. 비율:

* 이 트레이트는 고유 방문자의 30%를 세그먼트(3/10 = 0.30)와 공유합니다.
* 이 세그먼트는 고유 방문자의 0.3%를 트레이트와 공유합니다(3/1,000 = 0.003).

![](assets/s2t.png)

## 세그먼트-트레이트 데이터 팝 필드 정의 {#fields-defined}

개별 데이터 포인트를 클릭할 때 팝업 창에 표시되는 지표를 설명합니다.

<!-- 

r_s2t_data_pop.xml

 -->

[!UICONTROL Segment-to-Trait Overlap] 보고서 팝업에 아래 지표가 포함되어 있습니다. 표의 고유 수 지표는 *실시간 사용자*&#x200B;를 나타냅니다.

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
   <td colname="col2"> 세그먼트의 고유 숫자 ID. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 특성 데이터 소스  </span></b> </td> 
   <td colname="col2"> 트레이트 소유자의 이름입니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 데이터 소스 유형</span></b> </td> 
   <td colname="col2">트레이트가 속한 공급자 유형을 정의합니다. 다음 중 하나를 수행할 수 있습니다. 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">자사(사용자 고유의 특성). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">제3자(외부 데이터 파트너/공급업체에서 제공). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 특성 ID</span></b> </td> 
   <td colname="col2"> 트레이트에 대한 고유 숫자 ID. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 특성 이름</span></b> </td> 
   <td colname="col2"> 트레이트의 이름입니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 특성 고유 수 겹치기 %</span></b> </td> 
   <td colname="col2"> 트레이트가 세그먼트와 공유하는 고유 방문자의 %. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 세그먼트 고유 항목 겹치기 %</span></b> </td> 
   <td colname="col2"> 세그먼트가 트레이트와 공유하는 고유 방문자의 %. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 고유 항목 겹치기</span></b> </td> 
   <td colname="col2"> 세그먼트와 트레이트 간에 공유된 고유 방문자 수입니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 세그먼트 고유 수</span></b> </td> 
   <td colname="col2"> 세그먼트의 고유 방문자 수. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 특성 고유 수</span></b> </td> 
   <td colname="col2"> 트레이트에 있는 고유 방문자 수입니다. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [데이터 슬라이더를 사용하여 보고서 결과 필터링](../../reporting/dynamic-reports/data-sliders.md)
>* [대화형 보고서에 사용된 모양, 색상 및 크기](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [보고서 아이콘 및 도구 설명](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Overlap Reports: 일정 및 최소 세그먼트 크기 업데이트](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [선택한 Audience Manager 보고서의 데이터 샘플링 및 오류율...](../../reporting/report-sampling.md)
>* [Overlap Reports에 대한 CSV 파일](../../reporting/dynamic-reports/overlap-csv-files.md)

