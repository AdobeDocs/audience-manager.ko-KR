---
description: 광고 단위 대 광고 단위 겹침 보고서는 광고 단위와 Audience Manager 세그먼트 간에 높은 겹치고 겹치는 강조 표시로 표시됩니다.
seo-description: 광고 단위 대 광고 단위 겹침 보고서는 광고 단위와 Audience Manager 세그먼트 간에 높은 겹치고 겹치는 강조 표시로 표시됩니다.
seo-title: 광고 단위 겹침 세그먼트
solution: Audience Manager
title: 광고 단위 겹침 세그먼트
uuid: AAA 20163-58 AA -42 C 9-8 F 72-A 1 DFB 0 D 20 E 57
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Segment to Ad Unit Overlap{#segment-to-ad-unit-overlap}

광고 단위 대 광고 단위 겹침 보고서는 광고 단위와 Audience Manager 세그먼트 간에 높은 겹치고 겹치는 강조 표시로 표시됩니다.

## 사용 사례 {#use-cases}

[!UICONTROL Segment to Ad Unit Overlap] 보고서를 사용하여 웹 속성을 방문하는 고객을 파악할 수 있습니다. The report displays the overlap between members of your [!DNL Audience Manager] segments and the number of visitors to your web properties. 겹치게 되면 세그먼트의 많은 구성원이 웹 속성을 방문합니다.

## Using the Segment to Ad Unit Overlap Report {#using-the-report}

**[!UICONTROL Top N Ad Units]** AND **[!UICONTROL Top N Segments]** 컨트롤을 사용하여 오버랩에 대해 원하는 광고 단위와 세그먼트 수를 선택합니다. 각각에 대해 최대 100 개의 항목을 선택할 수 있습니다.

Use the **Day Range** and **Date Through** controls to adjust your look-back range. 7 일과 30 일 룩백 기간은 일요일 날짜에 대해서만 사용할 수 있습니다.

**[!UICONTROL Segment Name]** AND를 **[!UICONTROL Ad Unit]** 사용하여 세그먼트와 광고 단위를 필터링합니다.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Ad Unit IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Ad Unit] instead of the [!UICONTROL Ad Unit ID].

## Interpreting the Results {#interpreting-results}

[!UICONTROL Segment to Ad Unit Overlap] 보고서가 아래 나와 표시될 수 있습니다. 셀 위로 마우스를 가져가면 특정 겹침에 대한 자세한 내용이 표시됩니다. 샘플 보고서 아래 표의 추가 정보는 설명을 참조하십시오.

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
   <td colname="col2"> <p>인벤토리 항목의 이름입니다. 예를 들어, 웹 사이트나 웹 사이트의 아티클 중 하나일 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 세그먼트 실시간 고유 방문자 수</span> </p> </td> 
   <td colname="col2"> <p>The number of unique visitors seen in real-time for the specified time range and who were qualified for the segment at the moment they were seen by <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 광고 단위 고유 횟수</span> </p> </td> 
   <td colname="col2"> <p>이 특정 광고 단위에 대한 방문자 수입니다. 이 정보는 DFP 로그에서 추출됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 중첩 고유 수 계산</span> </p> </td> 
   <td colname="col2"> <p>광고 유닛 항목에 노출된 세그먼트 구성원. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 겹침 백분율</span> </p> </td> 
   <td colname="col2"> <p>광고 단위와 세그먼트 모집단의 겹침. <span class="wintitle"> 이것은 중첩된 고유 수 카운트로서</span><span class="wintitle"> , 세그먼트의 실시간 고유 수를 백분율로 나타냅니다</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

