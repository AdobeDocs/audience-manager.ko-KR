---
description: 모든 자사 및 타사 트레이트에서 공유된 고유한 사용자 수에 대한 데이터를 반환합니다.
seo-description: 모든 자사 및 타사 트레이트에서 공유된 고유한 사용자 수에 대한 데이터를 반환합니다.
seo-title: 특성-특성 Overlap Reports
solution: Audience Manager
title: 특성-특성 Overlap Reports
uuid: 7fb3fc9e-0e0b-492a-9c3a-04356afb19c7
feature: overlap reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 8%

---


# 특성-특성 Overlap Reports{#trait-to-trait-overlap-report}

모든 자사 및 타사 트레이트에서 공유된 고유한 사용자 수에 대한 데이터를 반환합니다.

>[!NOTE]
>
>Audience Manager의 겹치기 보고서는 RBAC 원칙을 따릅니다. 사용자가 속한 [RBAC 사용자 그룹](/help/using/features/administration/administration-overview.md)을 기반으로 액세스할 수 있는 데이터 소스에서만 트레이트를 볼 수 있습니다.

<!-- 

c_overlap_reports.xml

 -->

## 개요

[!UICONTROL Trait-to-Trait Overlap] 보고서는 자신의 모든 트레이트와 타사 트레이트 간에 공유된 고유한 사용자의 % 데이터를 반환합니다. 이 보고서는 최적화 도구로서 다음과 같은 이점을 제공합니다.

* 요구 사항에 따라 겹치거나 낮은 세그먼트를 만들 수 있습니다. 겹치는 트레이트는 타깃팅된 대상이지만 고유 방문자 수는 줄어듭니다. 오버랩이 낮은 트레이트는 더 크고 고유한 방문자 세트에 도달하는 데 유용합니다.
* 타사 특성 데이터의 유효성 검사:유사한 자사 트레이트와 타사 트레이트 간의 강한 오버랩은 데이터 파트너의 특성이 정확하고 신뢰할 수 있음을 나타냅니다. 반대로, 낮은 겹침은 타사 트레이트가 실제로 자신과 비슷한 자사 트레이트와 동일한 정보를 포함하지 않을 수도 있음을 나타낼 수 있습니다.
* 트레이트 간에 예기치 않은 겹침을 찾아 이 정보를 사용하여 혁신적인 세그먼트를 만들 수 있습니다.

## 샘플 보고서

다음 그림은 [!UICONTROL Trait-to-Trait Overlap] 보고서의 요소에 대한 고급 개요를 제공합니다.

>[!NOTE]
>
>[!UICONTROL Trait-to-Trait Overlap] 보고서는 동일한 특성을 자신과 비교할 때 빈 필드를 반환합니다.

![](assets/trait-to-trait-overlap.png)

## 개별 데이터 포인트 드릴다운

개별 포인트를 선택하여 팝업 창에서 데이터 세부 사항을 봅니다. 클릭 작업은 보고서에 표시된 데이터를 자동으로 업데이트합니다.

## 트레이트-트레이트 겹치기 데이터 팝 필드 정의 {#field-definitions}

개별 데이터 포인트를 클릭할 때 팝업 창에 표시되는 지표를 설명합니다.

<!-- 

r_t2t_data_pop.xml

 -->

[!UICONTROL Trait-to-Trait Overlap] 보고서의 팝업에 아래 지표가 포함되어 있습니다. 표의 고유 수 지표는 *실시간 사용자*&#x200B;를 나타냅니다.

<table id="table_A2A0CFC47C1A404994B82E6630E711A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 지표 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 겹치기 비율</span></b> </td> 
   <td colname="col2"> 비교 트레이트(겹치는 고유/트레이트 고유 값) 간 고유한 겹침 비율을 표시합니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 데이터 소스 유형</span></b> </td> 
   <td colname="col2">트레이트가 속하는 데이터 소스의 유형을 정의합니다. 다음 중 하나를 수행할 수 있습니다. 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">자사(사용자 고유의 특성). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">타사(외부 데이터 파트너/공급업체에서 제공) </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 겹치는 특성 ID</span></b> </td> 
   <td colname="col2"> 겹치는 트레이트에 대한 고유 숫자 ID. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 겹치는 특성 이름</span></b> </td> 
   <td colname="col2"> 겹치는 트레이트의 이름입니다. </td> 
  </tr>
    <tr> 
   <td colname="col1"><b><span class="wintitle"> 특성 ID 2</span></b> </td> 
   <td colname="col2"> 기본 데이터 소스의 특성에 대한 고유 숫자 ID. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 특성 이름 2</span></b> </td> 
   <td colname="col2"> 기본 데이터 소스의 특성 이름입니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 겹치기 고유</span></b> </td> 
   <td colname="col2"> <p>겹침 %를 가져오려면 Audience Manager에서 다음 공식을 사용합니다.</p> <p>겹치는 고유 수 /(기본 특성 고유 수 + 겹치는 특성 고유 수 - 겹치는 고유 수)</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 겹치는 특성 고유</span></b> </td> 
   <td colname="col2"> 겹치는 트레이트의 고유 방문자 수입니다. </td> 
  </tr> 
    <tr> 
   <td colname="col1"><b><span class="wintitle"> 기본 특성 고유</span></b> </td> 
   <td colname="col2"> 기본 트레이트의 고유 방문자 수입니다. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [데이터 슬라이더를 사용하여 보고서 결과 필터링](../../reporting/dynamic-reports/data-sliders.md)
>* [동적 보고서에 사용된 모양, 색상 및 크기](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [보고서 아이콘 및 도구 설명](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Overlap Reports: 일정 및 최소 세그먼트 크기 업데이트](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [선택한 Audience Manager 보고서의 데이터 샘플링 및 오류율...](../../reporting/report-sampling.md)
>* [Overlap Reports에 대한 CSV 파일](../../reporting/dynamic-reports/overlap-csv-files.md)