---
description: 모든 자사 트레이트와 타사 트레이트에서 공유되는 고유 사용자 수에 대한 데이터를 반환합니다.
seo-description: Returns data on the number of unique users shared among all your first and third-party traits.
seo-title: Trait-to-Trait Overlap Report
solution: Audience Manager
title: 특성-특성 중복 보고서
uuid: 7fb3fc9e-0e0b-492a-9c3a-04356afb19c7
feature: Overlap Reports
exl-id: cbc933bb-f2af-4ad0-8eb9-cbec1ee952e0
source-git-commit: 6cc1351c3a84d4d2219f33ef6175f182b9641377
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 4%

---

# 특성-특성 중복 보고서{#trait-to-trait-overlap-report}

모든 자사 트레이트와 타사 트레이트에서 공유되는 고유 사용자 수에 대한 데이터를 반환합니다.

>[!NOTE]
>
>Audience Manager의 겹치기 보고서는 RBAC 원칙을 준수합니다. 사용자가 속한 [RBAC 사용자 그룹](/help/using/features/administration/administration-overview.md)을(를) 기반으로 액세스 권한이 있는 데이터 원본에서만 특성을 볼 수 있습니다.

<!-- 

c_overlap_reports.xml

 -->

## 개요

[!UICONTROL Trait-to-Trait Overlap] 보고서는 사용자의 모든 특성과 사용자의 서드파티 특성 간에 공유된 고유 사용자 비율의 데이터를 반환합니다. 이 보고서는 최적화 도구로서 다음과 같은 작업을 수행하는 데 유용합니다.

* 필요에 따라 겹치는 부분이 높거나 낮은 세그먼트를 만듭니다. 겹치는 정도가 높은 트레이트는 타깃팅된 대상을 제공하지만 고유 방문자 수는 줄어듭니다. 겹치는 정도가 낮은 트레이트는 더 크고 고유한 방문자 세트에 도달하기 위해 유용할 수 있습니다.
* 서드파티 트레이트 데이터의 유효성 검사: 유사한 서드파티 트레이트와 서드파티 트레이트 간의 강한 겹침은 데이터 파트너의 트레이트가 정확하고 신뢰할 수 있음을 나타냅니다. 반대로 겹치는 정도가 낮으면 서드파티 트레이트가 실제로 유사한 자사 트레이트와 동일한 정보를 포함하지 않을 수 있음을 나타낼 수 있습니다.
* 트레이트 간에 예기치 않은 겹침을 찾아 해당 정보를 사용하여 혁신적인 세그먼트를 작성하십시오.

## 샘플 보고서

다음 그림에서는 [!UICONTROL Trait-to-Trait Overlap] 보고서의 요소에 대한 높은 수준의 개요를 제공합니다.

>[!NOTE]
>
>[!UICONTROL Trait-to-Trait Overlap] 보고서는 같은 특성을 자신과 비교할 때 빈 필드를 반환합니다.

>[!NOTE]
>
>트레이트 간 중복 보고서 내에서는 폴더 트레이트를 비교할 수 없습니다. 특정 폴더 특성을 사용하여 세그먼트를 만들면 [세그먼트-특성 중복 보고서](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md)를 통해 분석을 수행할 수 있습니다.

![](assets/trait-to-trait-overlap.png)

## 개별 데이터 포인트 드릴다운

개별 포인트를 선택하여 팝업 창에서 데이터 세부 정보를 봅니다. 클릭 작업은 보고서에 표시된 데이터를 자동으로 업데이트합니다.

## 정의된 트레이트 간 중복 데이터 팝업 필드 {#field-definitions}

개별 데이터 포인트를 클릭할 때 팝업 창에 표시되는 지표에 대해 설명합니다.

<!-- 

r_t2t_data_pop.xml

 -->

[!UICONTROL Trait-to-Trait Overlap] 보고서에 대한 팝업에 아래 지표가 포함되어 있습니다. 테이블의 고유 수 지표는 *실시간 사용자*&#x200B;를 나타냅니다.

<table id="table_A2A0CFC47C1A404994B82E6630E711A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 지표 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 겹치기 %</span></b> </td> 
   <td colname="col2"> 비교된 트레이트 간 고유한 겹침 비율(% 고유/고유 트레이트 겹침)을 표시합니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 데이터 Source 형식</span></b> </td> 
   <td colname="col2">트레이트가 속한 데이터 소스의 유형을 정의합니다. 다음 중 하나일 수 있습니다. 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">자사(고유한 트레이트). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">외부 데이터 파트너/공급업체의 타사. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 겹치는 트레이트 ID</span></b> </td> 
   <td colname="col2"> 겹치는 트레이트에 대한 고유 숫자 ID입니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 겹치는 트레이트 이름</span></b> </td> 
   <td colname="col2"> 겹치는 트레이트의 이름입니다. </td> 
  </tr>
    <tr> 
   <td colname="col1"><b><span class="wintitle"> 트레이트 ID 2</span></b> </td> 
   <td colname="col2"> 기본 데이터 소스의 트레이트에 대한 고유 숫자 ID입니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 트레이트 이름 2</span></b> </td> 
   <td colname="col2"> 기본 데이터 소스의 트레이트 이름. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 중복 고유</span></b> </td> 
   <td colname="col2"> <p>겹치기 %를 가져오기 위해 Audience Manager에서는 다음 공식을 사용합니다.</p> <p>중복 고유 / (기본 트레이트 고유 + 중복 트레이트 고유 - 중복 고유)</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 겹치는 트레이트 고유</span></b> </td> 
   <td colname="col2"> 겹치는 트레이트의 고유 방문자 수입니다. </td> 
  </tr> 
    <tr> 
   <td colname="col1"><b><span class="wintitle"> 기본 트레이트 고유</span></b> </td> 
   <td colname="col2"> 기본 트레이트의 고유 방문자 수입니다. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [데이터 슬라이더를 사용하여 보고서 결과 필터링](../../reporting/dynamic-reports/data-sliders.md)
>* [동적 보고서에 사용되는 모양, 색 및 크기](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [보고서 아이콘 및 도구 설명](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Overlap Reports: 일정 및 최소 세그먼트 크기 업데이트](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [선택한 Audience Manager 보고서의 데이터 샘플링 및 오류율...](../../reporting/report-sampling.md)
>* [Overlap Reports에 대한 CSV 파일](../../reporting/dynamic-reports/overlap-csv-files.md)
