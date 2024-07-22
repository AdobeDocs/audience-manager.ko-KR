---
description: 세그먼트 대 광고 단위 겹치기 보고서는 광고 단위와 Audience Manager 세그먼트 간의 높음 및 낮음 겹침을 강조 표시하는 히트차트로 표시됩니다.
seo-description: The Segment to Ad Unit Overlap report is displayed as a heat chart that highlights high and low overlaps between your Ad Units and Audience Manager segments.
seo-title: Segment to Ad Unit Overlap
solution: Audience Manager
title: 세그먼트 대 광고 단위 겹치기
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: Audience Optimization Reports
exl-id: 6c7cf2e6-8ed4-42de-92ee-0df90940f441
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 1%

---

# 세그먼트 대 광고 단위 겹치기{#segment-to-ad-unit-overlap}

세그먼트 대 광고 단위 겹치기 보고서는 광고 단위와 Audience Manager 세그먼트 간의 높음 및 낮음 겹침을 강조 표시하는 히트차트로 표시됩니다.

## 사용 사례 {#use-cases}

[!UICONTROL Segment to Ad Unit Overlap] 보고서를 사용하면 웹 속성을 방문하는 대상을 파악할 수 있습니다. 보고서에 [!DNL Audience Manager] 세그먼트의 멤버와 웹 속성의 방문자 수가 겹쳐 표시됩니다. 겹치는 정도가 높을수록 세그먼트의 많은 멤버가 웹 속성을 방문함을 의미합니다.

## 세그먼트-광고 단위 중복 보고서 사용 {#using-the-report}

**[!UICONTROL Top N Ad Units]** 및 **[!UICONTROL Top N Segments]** 컨트롤을 사용하여 겹치는 광고 단위와 세그먼트를 원하는 수만큼 선택합니다. 각각에 대해 최대 100개의 항목을 선택할 수 있습니다.

**일 범위** 및 **날짜 범위** 컨트롤을 사용하여 전환 확인 범위를 조정하세요. 7일 및 30일 전환 확인 기간은 일요일 날짜에만 사용할 수 있습니다.

**[!UICONTROL Segment Name]** 및 **[!UICONTROL Ad Unit]** 상자를 사용하여 세그먼트 및 광고 단위를 필터링합니다.

>[!IMPORTANT]
>
>[!UICONTROL Audience Optimization for Publishers]을(를) 활성화할 때 [Google 광고 관리자(이전의 DFP) 데이터 파일을 Audience Manager으로 가져오기](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)의 3단계에 설명된 대로 [!UICONTROL Ad Unit IDs]에 대한 설명 메타데이터를 포함해야 합니다. 이렇게 하면 보고서에 웹 속성이 [!UICONTROL Ad Unit ID] 대신 [!UICONTROL Ad Unit](으)로 자세히 설명되어 있습니다.

## 결과 해석 {#interpreting-results}

[!UICONTROL Segment to Ad Unit Overlap] 보고서는 아래 보고서와 유사할 수 있습니다. 특정 겹치기 항목에 대한 자세한 내용을 보려면 셀 위로 마우스를 가져갑니다. 샘플 보고서 아래 표에 있는 추가 정보에 대해서는 설명을 참조하십시오.

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
   <td colname="col2"> <p>재고 항목의 이름입니다. 예를 들어 웹 사이트 중 하나 또는 웹 사이트의 문서일 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">개 세그먼트 실시간 고유 개수</span> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span>이(가) 본 순간 지정된 시간 범위 동안 실시간으로 확인되었으며 세그먼트에 대한 자격이 있는 고유 방문자의 수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 광고 단위 고유 개수</span> </p> </td> 
   <td colname="col2"> <p>이 특정 광고 단위에 대한 방문자의 수입니다. 이 정보는 Google 광고 관리자 로그에서 추출됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 중복 고유 개수</span> </p> </td> 
   <td colname="col2"> <p>광고 단위 항목에 노출된 세그먼트 멤버입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 겹침 비율</span> </p> </td> 
   <td colname="col2"> <p>광고 단위와 세그먼트 모집단 간의 겹칩니다. <span class="wintitle"> 세그먼트 실시간 고유 </span>의 비율로 표현되는 <span class="wintitle"> 중복 고유 개수</span>입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>
