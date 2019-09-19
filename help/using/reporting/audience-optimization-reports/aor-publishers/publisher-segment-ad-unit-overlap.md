---
description: 광고 단위 겹치기 세그먼트는 광고 단위와 Audience Manager 세그먼트 간의 높이와 낮은 중복을 강조 표시하는 열 차트로 표시됩니다.
seo-description: 광고 단위 겹치기 세그먼트는 광고 단위와 Audience Manager 세그먼트 간의 높이와 낮은 중복을 강조 표시하는 열 차트로 표시됩니다.
seo-title: 세그먼트 대 광고 단위 오버랩
solution: Audience Manager
title: 세그먼트 대 광고 단위 오버랩
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d2 파섹
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 세그먼트 대 광고 단위 오버랩{#segment-to-ad-unit-overlap}

광고 단위 겹치기 세그먼트는 광고 단위와 Audience Manager 세그먼트 간의 높이와 낮은 중복을 강조 표시하는 열 차트로 표시됩니다.

## 사용 사례 {#use-cases}

이 [!UICONTROL Segment to Ad Unit Overlap] 보고서를 사용하면 웹 속성을 방문하는 대상을 파악할 수 있습니다. 보고서는 [!DNL Audience Manager] 세그먼트 구성원과 웹 속성에 대한 방문자 수 간의 겹침을 표시합니다. 중복 세그먼트가 높을수록 세그먼트의 많은 구성원이 웹 속성을 방문합니다.

## 세그먼트를 사용하여 광고 단위 겹침 보고서 사용 {#using-the-report}

및 **[!UICONTROL Top N Ad Units]** 컨트롤을 사용하여 겹치는 데 필요한 광고 단위 및 세그먼트 수를 선택합니다 **[!UICONTROL Top N Segments]** . 각 항목에 대해 최대 100개 항목을 선택할 수 있습니다.

일 **범위** 및 **날짜** 스루 컨트롤을 사용하여 룩백 범위를 조정합니다. 7일 및 30일 룩백 기간은 일요일 날짜에만 사용할 수 있습니다.

세그먼트 **[!UICONTROL Segment Name]** 및 **[!UICONTROL Ad Unit]** 상자를 사용하여 세그먼트 및 광고 단위를 필터링합니다.

>[!IMPORTANT]
>
>활성화할 [!UICONTROL Audience Optimization for Publishers]때 DFP 데이터 파일을 Audience Manager로 가져오기 3단계에 설명된 [!UICONTROL Ad Unit IDs]대로 [에 대한 설명 메타데이터를 포함해야 합니다](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). 이렇게 하면 보고서가 웹 속성이 [!UICONTROL Ad Unit] 아닌 웹 속성에 대한 세부 정보를 알 수 [!UICONTROL Ad Unit ID]있습니다.

## 결과 해석 {#interpreting-results}

보고서가 아래 보고서와 유사할 수 [!UICONTROL Segment to Ad Unit Overlap] 있습니다. 특정 오버랩에 대한 자세한 내용을 보려면 셀 위로 마우스를 가져갑니다. 샘플 보고서 아래 표에 나와 있는 추가 정보는 설명을 참조하십시오.

![](assets/publisher_segment_ad_unit_overlap.png)

<table id="table_22340F45B1B94D3796174CB30A60E212"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 항목 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 광고 단위 </span> </p> </td> 
   <td colname="col2"> <p>재고 품목의 이름입니다. 예를 들어 웹 사이트 또는 웹 사이트의 아티클 중 하나일 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 세그먼트 실시간 고유 수</span> </p> </td> 
   <td colname="col2"> <p>지정된 시간 범위 동안 실시간으로 표시되고 Audience Manager에서 보았던 당시 세그먼트에 자격을 갖춘 고유 방문자 <span class="keyword"> 수입니다</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 광고 단위 고유 수</span> </p> </td> 
   <td colname="col2"> <p>이 특정 광고 단위의 방문자 수입니다. 이 정보는 DFP 로그에서 추출됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 겹치기 고유 수</span> </p> </td> 
   <td colname="col2"> <p>광고 단위 항목에 노출된 세그먼트의 구성원. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 겹치기 비율</span> </p> </td> 
   <td colname="col2"> <p>광고 단위와 세그먼트 모집단 간의 겹칩니다. 이것은 <span class="wintitle"> 겹치기 고유 수</span>(세그먼트 실시간 <span class="wintitle"> 고유 수의 백분율로 표시됨)입니다</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

