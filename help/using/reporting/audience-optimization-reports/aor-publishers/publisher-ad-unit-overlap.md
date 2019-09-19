---
description: 광고 단위 겹침 보고서는 광고 단위 간의 높이와 낮은 중복을 강조 표시하는 열 차트로 표시됩니다.
seo-description: 광고 단위 겹침 보고서는 광고 단위 간의 높이와 낮은 중복을 강조 표시하는 열 차트로 표시됩니다.
seo-title: 광고 단위 오버랩
solution: Audience Manager
title: 광고 단위 오버랩
uuid: e4467e81-acbf-474e-b501-89d57395651f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 광고 단위 오버랩{#ad-unit-overlap}

보고서는 **[!UICONTROL Ad Unit Overlap]** 광고 단위 간의 높이와 낮은 중복을 강조 표시하는 열 차트로 표시됩니다.

## 사용 사례 {#use-cases}

이 **[!UICONTROL Ad Unit Overlap]** 보고서를 사용하면 웹 속성에서 고객이 겹치는 위치를 파악할 수 있습니다. 이 보고서는 100개의 상위 관련 속성을 고려하며 두 속성 간에 겹치는 것을 보여줍니다.

## 광고 단위 겹침 보고서 사용 {#using-the-report}

오버랩에 대해 **[!UICONTROL Top N Base Ad Units]** 및 **[!UICONTROL Top N Overlapping Ad Units]** 컨트롤을 사용하여 원하는 광고 단위 수를 선택합니다. 각 항목에 대해 최대 100개 항목을 선택할 수 있습니다.

일 **범위** 및 **날짜** 스루 컨트롤을 사용하여 룩백 범위를 조정합니다. 7일 및 30일 룩백 기간은 일요일 날짜에만 사용할 수 있습니다.

겹침 **[!UICONTROL Base Ad Unit]** 보고서와 컨트롤을 사용하여 겹치기 보고서에 표시할 광고 단위를 선택합니다 **[!UICONTROL Overlap Ad Unit]** .

>[!IMPORTANT]
>
>활성화할 [!UICONTROL Audience Optimization for Publishers]때 DFP 데이터 파일을 Audience Manager로 가져오기 3단계에 설명된 [!UICONTROL Ad Unit IDs]대로 [에 대한 설명 메타데이터를 포함해야 합니다](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). 이렇게 하면 보고서가 웹 속성이 [!UICONTROL Ad Unit] 아닌 웹 속성에 대한 세부 정보를 알 수 [!UICONTROL Ad Unit ID]있습니다.

## 결과 해석 {#interpreting-results}

보고서가 아래 보고서와 유사할 수 [!UICONTROL Ad Unit Overlap] 있습니다. 특정 오버랩에 대한 자세한 내용을 보려면 셀 위로 마우스를 가져갑니다. 샘플 보고서 아래 표에 나와 있는 추가 정보는 설명을 참조하십시오.

![](assets/publisher_ad_unit_overlap.png)

<table id="table_22340F45B1B94D3796174CB30A60E212"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 항목 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 광고 단위 겹치기</span> </p> </td> 
   <td colname="col2"> <p>재고 품목의 이름입니다. 예를 들어 웹 사이트 또는 웹 사이트의 아티클 중 하나일 수 있습니다. 위의 이미지에서 기본 광고 단위는 Article 9 - 18입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 기본 광고 단위</span> </p> </td> 
   <td colname="col2"> <p>재고 품목의 이름입니다. 예를 들어 웹 사이트 또는 웹 사이트의 아티클 중 하나일 수 있습니다. 위의 이미지에서 기본 광고 단위는 Article 1 - 8입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 광고 단위 고유 수 겹치기</span> </p> </td> 
   <td colname="col2"> <p>광고 단위 항목 9 - 18을 방문한 사용자 수입니다. 이 정보는 DFP 로그에서 추출됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 기본 광고 단위 고유 수</span> </p> </td> 
   <td colname="col2"> <p>광고 단위 항목 1 - 8을 방문한 사용자 수입니다. 이 정보는 DFP 로그에서 추출됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 겹치기 고유 수</span> </p> </td> 
   <td colname="col2"> <p>기본 광고 단위를 방문한 사용자와 광고 <span class="wintitle"> 단위</span> 겹치는 <span class="wintitle"> 사용자</span>간의 겹칩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 겹치기 비율</span> </p> </td> 
   <td colname="col2"> <p>기본 광고 단위를 방문한 사용자와 광고 <span class="wintitle"> 단위</span> 겹치는 <span class="wintitle"> 사용자</span>간의 겹칩니다. 이것은 <span class="wintitle"> 겹치기 고유 수</span>수로 기본 광고 단위의 백분율로 <span class="wintitle"> 표현됩니다</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
