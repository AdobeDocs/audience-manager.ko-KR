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
source-wordcount: '388'
ht-degree: 3%

---

# 세그먼트 대 광고 단위 겹치기{#segment-to-ad-unit-overlap}

세그먼트 대 광고 단위 겹치기 보고서는 광고 단위와 Audience Manager 세그먼트 간의 높음 및 낮음 겹침을 강조 표시하는 히트차트로 표시됩니다.

## 사용 사례 {#use-cases}

포함 [!UICONTROL Segment to Ad Unit Overlap] 보고서에서는 웹 속성을 방문하는 대상을 이해할 수 있습니다. 이 보고서는 멤버 간의 겹침을 표시합니다. [!DNL Audience Manager] 세그먼트 및 웹 속성에 대한 방문자 수입니다. 겹치는 정도가 높을수록 세그먼트의 많은 멤버가 웹 속성을 방문함을 의미합니다.

## 세그먼트-광고 단위 중복 보고서 사용 {#using-the-report}

사용 **[!UICONTROL Top N Ad Units]** 및 **[!UICONTROL Top N Segments]** 를 제어하여 겹칠 광고 단위 및 세그먼트 수를 선택합니다. 각각에 대해 최대 100개의 항목을 선택할 수 있습니다.

사용 **일 범위** 및 **종료 날짜** 를 제어하여 룩백 범위를 조정합니다. 7일 및 30일 전환 확인 기간은 일요일 날짜에만 사용할 수 있습니다.

사용 **[!UICONTROL Segment Name]** 및 **[!UICONTROL Ad Unit]** 세그먼트 및 광고 단위를 필터링하는 상자입니다.

>[!IMPORTANT]
>
>활성화 시 [!UICONTROL Audience Optimization for Publishers], 다음에 대한 설명 메타데이터를 포함해야 합니다. [!UICONTROL Ad Unit IDs]의 3단계에 설명된 대로 [Google Ad Manager(이전의 DFP) 데이터 파일을 Audience Manager에 가져오기](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). 이렇게 하면 보고서에서 다음과 같이 웹 속성을 자세히 알 수 있습니다. [!UICONTROL Ad Unit] 대신 [!UICONTROL Ad Unit ID].

## 결과 해석 {#interpreting-results}

사용자 [!UICONTROL Segment to Ad Unit Overlap] 보고서는 아래 보고서와 유사할 수 있습니다. 특정 겹치기 항목에 대한 자세한 내용을 보려면 셀 위로 마우스를 가져갑니다. 샘플 보고서 아래 표에 있는 추가 정보에 대해서는 설명을 참조하십시오.

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
   <td colname="col1"> <p><span class="wintitle"> 세그먼트 실시간 고유 수</span> </p> </td> 
   <td colname="col2"> <p>지정된 시간 범위 동안 실시간으로 확인되었으며, 확인되는 순간 세그먼트에 대한 자격이 확인된 고유 방문자의 수입니다. <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 광고 단위 고유 수</span> </p> </td> 
   <td colname="col2"> <p>이 특정 광고 단위에 대한 방문자의 수입니다. 이 정보는 Google 광고 관리자 로그에서 추출됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 중복 고유 수</span> </p> </td> 
   <td colname="col2"> <p>광고 단위 항목에 노출된 세그먼트 멤버입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 오버랩 비율</span> </p> </td> 
   <td colname="col2"> <p>광고 단위와 세그먼트 모집단 간의 겹칩니다. 다음 은 <span class="wintitle"> 중복 고유 수</span>, 다음에 대한 백분율로 표시: <span class="wintitle"> 세그먼트 실시간 고유 수</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
