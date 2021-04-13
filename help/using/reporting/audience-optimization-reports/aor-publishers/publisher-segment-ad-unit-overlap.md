---
description: 광고 단위 오버랩에 대한 세그먼트 보고서는 광고 단위와 Audience Manager 세그먼트 간의 높거나 낮은 오버랩을 강조 표시하는 열 차트로 표시됩니다.
seo-description: 광고 단위 오버랩에 대한 세그먼트 보고서는 광고 단위와 Audience Manager 세그먼트 간의 높거나 낮은 오버랩을 강조 표시하는 열 차트로 표시됩니다.
seo-title: 세그먼트 대 광고 단위 겹치기
solution: Audience Manager
title: 세그먼트 대 광고 단위 겹치기
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: 대상 최적화 보고서
exl-id: 6c7cf2e6-8ed4-42de-92ee-0df90940f441
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 5%

---

# 세그먼트 대 광고 단위 겹치기{#segment-to-ad-unit-overlap}

광고 단위 오버랩에 대한 세그먼트 보고서는 광고 단위와 Audience Manager 세그먼트 간의 높거나 낮은 오버랩을 강조 표시하는 열 차트로 표시됩니다.

## 사용 사례 {#use-cases}

[!UICONTROL Segment to Ad Unit Overlap] 보고서를 사용하여 웹 속성을 방문하는 대상을 파악할 수 있습니다. 보고서는 [!DNL Audience Manager] 세그먼트의 구성원과 웹 속성에 대한 방문자 수 사이의 오버랩을 표시합니다. 겹치기가 클수록 세그먼트의 많은 구성원이 웹 속성을 방문합니다.

## 세그먼트를 사용하여 광고 단위 겹치기 보고서 {#using-the-report} 사용

겹치는 광고 단위 및 세그먼트의 원하는 수를 선택하려면 **[!UICONTROL Top N Ad Units]** 및 **[!UICONTROL Top N Segments]** 컨트롤을 사용합니다. 각 항목에 대해 최대 100개 항목을 선택할 수 있습니다.

룩백 범위를 조정하려면 **일 범위** 및 **Date Through** 컨트롤을 사용합니다. 7일 및 30일 룩백 기간은 일요일 날짜에만 사용할 수 있습니다.

세그먼트 및 광고 단위를 필터링하려면 **[!UICONTROL Segment Name]** 및 **[!UICONTROL Ad Unit]** 상자를 사용합니다.

>[!IMPORTANT]
>
>[!UICONTROL Audience Optimization for Publishers]을(를) 활성화할 때 [Google 광고 관리자 가져오기(이전 DFP) 데이터 파일을 Audience Manager으로 가져오기](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)의 3단계에 설명된 대로 [!UICONTROL Ad Unit IDs]에 대한 설명 메타데이터를 포함해야 합니다. 이렇게 하면 보고서가 웹 속성을 [!UICONTROL Ad Unit ID] 대신 [!UICONTROL Ad Unit](으)로 상세 정보를 지정하도록 합니다.

## 결과 해석 {#interpreting-results}

[!UICONTROL Segment to Ad Unit Overlap] 보고서가 아래 보고서와 유사할 수 있습니다. 특정 오버랩에 대한 자세한 내용을 보려면 셀 위로 마우스를 가져갑니다. 샘플 보고서 아래 표에 나와 있는 추가 정보에 대한 설명을 참조하십시오.

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
   <td colname="col1"> <p><span class="wintitle"> 광고 단위  </span> </p> </td> 
   <td colname="col2"> <p>재고 항목의 이름입니다. 예를 들어 웹 사이트 또는 웹 사이트의 아티클 중 하나일 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 세그먼트 실시간 고유 수</span> </p> </td> 
   <td colname="col2"> <p>지정된 시간 범위 동안 실시간으로 보고 해당 세그먼트에 자격이 부여된 고유 방문자 수입니다(<span class="keyword"> Audience Manager</span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 광고 단위 고유 수</span> </p> </td> 
   <td colname="col2"> <p>특정 광고 단위에 대한 방문자 수입니다. 이 정보는 Google 광고 관리자 로그에서 추출됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 겹치기 고유 수</span> </p> </td> 
   <td colname="col2"> <p>광고 단위 항목에 노출된 세그먼트의 구성원. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 겹치기 비율</span> </p> </td> 
   <td colname="col2"> <p>광고 단위와 세그먼트 모집단 간에 겹칩니다. 이것은 <span class="wintitle"> 세그먼트 실시간 고유 수</span>의 백분율로 표현된 <span class="wintitle"> 겹치기 고유 수</span>입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>
