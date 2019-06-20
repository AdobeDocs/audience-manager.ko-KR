---
description: 첫 번째 및 서드 파티 트레이트들 간에 공유되는 고유 사용자 수의 데이터를 반환합니다.
seo-description: 첫 번째 및 서드 파티 트레이트들 간에 공유되는 고유 사용자 수의 데이터를 반환합니다.
seo-title: 특성-특성 중복 보고서
solution: Audience Manager
title: 특성-특성 중복 보고서
uuid: 7 FB 3 FC 9 E -0 E 0 B -492 A -9 C 3 A -04356 AFB 19 C 7
translation-type: tm+mt
source-git-commit: 4dc8aad623198cbc24c5c76ac3818d7ee00e9a5e

---


# 특성-특성 중복 보고서{#trait-to-trait-overlap-report}

첫 번째 및 서드 파티 트레이트들 간에 공유되는 고유 사용자 수의 데이터를 반환합니다.

>[!NOTE]
>
>Audience Manager의 겹침 보고서는 RBAC 원칙을 준수합니다. You can only see traits from data sources that you have access to based on the [RBAC User Group](/help/using/features/administration/administration-overview.md) that you belong to.

<!-- 

c_overlap_reports.xml

 -->

## 개요

[!UICONTROL Trait-to-Trait Overlap] 보고서는 고유 사용자의 모든 특성과 타사 특성 간에 공유되는 고유한 사용자의 데이터를 반환합니다. 이 보고서는 최적화 도구로서 다음과 같은 이점을 제공합니다.

* 필요에 따라 겹치거나 낮은 오버랩으로 세그먼트를 만듭니다. 오버랩이 높은 트레이트는 대상화된 대상이지만 고유 방문자 수는 적습니다. 오버랩이 낮은 트레이트는 고유한 방문자 세트에 도달하는 데 유용합니다.
* 타사 특성 데이터의 유효성 검사: 유사 트레이트와 서드파티 트레이트간의 긴밀한 오버랩은 데이터 파트너의 트레이트가 정확하고 신뢰할 수 있다는 것을 의미합니다. 반대로, 낮은 오버랩은 타사 트레이트가 실제로 사용자 고유의 유사 트레이트와 동일한 정보를 포함하지 않을 수 있음을 나타낼 수 있습니다.
* 특성 간에 예상치 않은 오버랩을 발견하고 해당 정보를 사용하여 혁신적인 세그먼트를 구축할 수 있습니다.

## 샘플 보고서

The following illustration provides a high-level overview of elements in the [!UICONTROL Trait-to-Trait Overlap] report.

>[!NOTE]
>
>[!UICONTROL Trait-to-Trait Overlap] 보고서는 동일한 트레이트를 자신과 비교할 때 빈 필드를 반환합니다.

![](assets/trait-to-trait-overlap.png)

## 개별 데이터 포인트 드릴다운

팝업 창에서 데이터를 볼 개별 지점을 선택합니다. 클릭 동작은 보고서에 표시되는 데이터를 자동으로 업데이트합니다.

## Trait-to-Trait Overlap Data Pop Fields Defined {#field-definitions}

개별 데이터 포인트를 클릭할 때 팝업 창에 표시되는 지표를 설명합니다.

<!-- 

r_t2t_data_pop.xml

 -->

The popup for the [!UICONTROL Trait-to-Trait Overlap] report contains the metrics below. Note that the uniques metric in the table represents your *real-time users*.

<table id="table_A2A0CFC47C1A404994B82E6630E711A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 지표 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 데이터 공급자 이름</span></b> </td> 
   <td colname="col2"> 트레이트 소유자 이름입니다. </td> 
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
   <td colname="col1"><b><span class="wintitle"> 특성 ID</span></b> </td> 
   <td colname="col2"> 해당 트레이트에 대한 고유한 숫자 ID 입니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 특성 이름</span></b> </td> 
   <td colname="col2"> 특성 이름입니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 겹침 %</span></b> </td> 
   <td colname="col2"> 특성 비교 간에 고유한 겹침 비율 (고유 값/특성 고유 값) 를 표시합니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 고유 방문자 수</span></b> </td> 
   <td colname="col2"> <p>겹침 비율을 얻기 위해 Audience Manager는 다음 공식을 사용합니다.</p> <p>중첩 고유 항목/(기본 세그먼트 고유 항목 + 중복 세그먼트 고유 자릿수 - 고유 방문자 수)</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 특성 고유 방문자</span></b> </td> 
   <td colname="col2"> 트레이트 고유 방문자 수. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ like_ this]
>
>* [데이터 슬라이더를 사용하여 보고서 결과 필터링](../../reporting/dynamic-reports/data-sliders.md)
>* [동적 보고서에 사용된 모양, 색상 및 크기](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [보고서 아이콘 및 도구 설명](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [겹침 보고서: 업데이트 예약 및 최소 세그먼트 크기](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [선택한 Audience Manager 보고서에서 데이터 샘플링 및 오류율...](../../reporting/report-sampling.md)
>* [중복 보고서에 대한 CSV 파일](../../reporting/dynamic-reports/overlap-csv-files.md)