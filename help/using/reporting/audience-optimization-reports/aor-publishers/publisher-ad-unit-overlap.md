---
description: 광고 단위 겹침 보고서는 광고 단위 간에 겹치고 낮은 겹쳐 보이는 히트 표로 표시됩니다.
seo-description: 광고 단위 겹침 보고서는 광고 단위 간에 겹치고 낮은 겹쳐 보이는 히트 표로 표시됩니다.
seo-title: 광고 단위 겹침
solution: Audience Manager
title: 광고 단위 겹침
uuid: E 4467 E 81-ACBF -474 E-B 501-89 D 57395651 F
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Ad Unit Overlap{#ad-unit-overlap}

**[!UICONTROL Ad Unit Overlap]** 보고서는 광고 단위 간에 하이와 낮은 겹쳐 보이는 히트 표로 표시됩니다.

## 사용 사례 {#use-cases}

**[!UICONTROL Ad Unit Overlap]** 보고서를 통해 웹 속성에 대한 고객의 접점에 대한 통찰력을 얻을 수 있습니다. 보고서에는 100 개의 상위 관련 속성이 고려되며 이러한 속성이 겹쳐 표시됩니다.

## Using the Ad Unit Overlap Report {#using-the-report}

**[!UICONTROL Top N Base Ad Units]** AND **[!UICONTROL Top N Overlapping Ad Units]** 컨트롤을 사용하여 오버랩에 대해 원하는 광고 단위 수를 선택합니다. 각각에 대해 최대 100 개의 항목을 선택할 수 있습니다.

Use the **Day Range** and **Date Through** controls to adjust your look-back range. 7 일과 30 일 룩백 기간은 일요일 날짜에 대해서만 사용할 수 있습니다.

**[!UICONTROL Base Ad Unit]** 와 **[!UICONTROL Overlap Ad Unit]** 컨트롤을 사용하여 겹침 보고서에 표시할 광고 단위를 선택합니다.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Ad Unit IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Ad Unit] instead of the [!UICONTROL Ad Unit ID].

## Interpreting the Results {#interpreting-results}

[!UICONTROL Ad Unit Overlap] 보고서가 아래 나와 표시될 수 있습니다. 셀 위로 마우스를 가져가면 특정 겹침에 대한 자세한 내용이 표시됩니다. 샘플 보고서 아래 표의 추가 정보는 설명을 참조하십시오.

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
   <td colname="col1"> <p><span class="wintitle"> 겹치는 광고 단위</span> </p> </td> 
   <td colname="col2"> <p>인벤토리 항목의 이름입니다. 예를 들어, 웹 사이트나 웹 사이트의 아티클 중 하나일 수 있습니다. 위의 이미지에서 기본 광고 단위는 9 - 18 입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 기본 광고 단위</span> </p> </td> 
   <td colname="col2"> <p>인벤토리 항목의 이름입니다. 예를 들어, 웹 사이트나 웹 사이트의 아티클 중 하나일 수 있습니다. 위의 이미지에서 기본 광고 단위는 기사 1 - 8 입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 겹침 광고 단위 고유 수</span> </p> </td> 
   <td colname="col2"> <p>광고 유닛 항목 9 - 18를 방문한 사용자 수입니다. 이 정보는 DFP 로그에서 추출됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 기본 광고 단위 고유 횟수</span> </p> </td> 
   <td colname="col2"> <p>광고 유닛 항목 1 - 8를 방문한 사용자 수입니다. 이 정보는 DFP 로그에서 추출됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 중첩 고유 수 계산</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 기본 광고 단위와</span> <span class="wintitle"> 겹치는 광고 단위를 방문한 사용자 사이의</span>겹침. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 겹침 백분율</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 기본 광고 단위와</span> <span class="wintitle"> 겹치는 광고 단위를 방문한 사용자 사이의</span>겹침. <span class="wintitle"> 이것은 중첩 고유 수 카운트로서</span><span class="wintitle"> 기본 광고 단위의 백분율로</span>표현됩니다. </p> </td> 
  </tr> 
 </tbody> 
</table>
