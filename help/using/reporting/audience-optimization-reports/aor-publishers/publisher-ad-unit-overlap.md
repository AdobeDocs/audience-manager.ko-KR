---
description: 광고 단위 겹치기 보고서는 광고 단위 간에 높은 중복과 낮은 겹침을 강조 표시하는 열 차트로 표시됩니다.
seo-description: 광고 단위 겹치기 보고서는 광고 단위 간에 높은 중복과 낮은 겹침을 강조 표시하는 열 차트로 표시됩니다.
seo-title: 광고 단위 겹치기
solution: Audience Manager
title: 광고 단위 겹치기
uuid: e4467e81-acbf-474e-b501-89d57395651f
feature: 대상 최적화 보고서
exl-id: 08b219c6-bf0c-4473-9459-83b3657dfb15
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 3%

---

# 광고 단위 겹치기{#ad-unit-overlap}

**[!UICONTROL Ad Unit Overlap]** 보고서는 광고 단위 간에 높은 오버랩과 낮은 오버랩을 강조 표시하는 열 차트로 표시됩니다.

## 사용 사례 {#use-cases}

**[!UICONTROL Ad Unit Overlap]** 보고서를 사용하면 웹 속성에서 대상이 겹치는 위치에 대한 통찰력을 얻을 수 있습니다. 보고서는 100개의 최상위 관련 속성을 고려하며 두 속성 간에 겹치는 부분이 있음을 보여줍니다.

## 광고 단위 중복 보고서 사용 {#using-the-report}

겹치는 부분에 대해 원하는 광고 단위 수를 선택하려면 **[!UICONTROL Top N Base Ad Units]** 및 **[!UICONTROL Top N Overlapping Ad Units]** 컨트롤을 사용하십시오. 각각에 대해 최대 100개의 항목을 선택할 수 있습니다.

**일 범위** 및 **Date Through** 컨트롤을 사용하여 전환 확인 범위를 조정합니다. 7일 및 30일 전환 확인 기간은 일요일 날짜에만 사용할 수 있습니다.

**[!UICONTROL Base Ad Unit]** 및 **[!UICONTROL Overlap Ad Unit]** 컨트롤을 사용하여 중복 보고서에 표시할 광고 단위를 선택합니다.

>[!IMPORTANT]
>
>[!UICONTROL Audience Optimization for Publishers]을(를) 활성화할 때, [!UICONTROL Ad Unit IDs]에 대한 설명 메타데이터를 포함해야 합니다. 자세한 내용은 [Google Ad Manager 가져오기(이전 DFP) 데이터 파일을 Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)에 가져오는 단계에 설명되어 있습니다. 이렇게 하면 보고서에 웹 속성이 [!UICONTROL Ad Unit ID] 대신 [!UICONTROL Ad Unit](으)로 자세히 설명되어 있는지 확인합니다.

## 결과 해석 {#interpreting-results}

[!UICONTROL Ad Unit Overlap] 보고서는 아래 보고서와 유사할 수 있습니다. 셀 위로 마우스를 가져가면 특정 겹침에 대한 자세한 정보가 표시됩니다. 샘플 보고서 아래 표에 있는 추가 정보에 대해서는 설명을 참조하십시오.

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
   <td colname="col1"> <p><span class="wintitle"> 겹치기 광고 단위</span> </p> </td> 
   <td colname="col2"> <p>재고 품목의 이름입니다. 예를 들어 웹 사이트 또는 웹 사이트의 문서가 될 수 있습니다. 위의 이미지에서 기본 광고 단위는 Article 9 - 18입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 기본 광고 단위</span> </p> </td> 
   <td colname="col2"> <p>재고 품목의 이름입니다. 예를 들어 웹 사이트 또는 웹 사이트의 문서가 될 수 있습니다. 위의 이미지에서 기본 광고 단위는 Article 1 - 8입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 겹치기 광고 단위 고유 수</span> </p> </td> 
   <td colname="col2"> <p>광고 단위 항목 9 - 18을 방문한 사용자 수입니다. 이 정보는 Google Ad Manager 로그에서 추출됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 기본 광고 단위 고유 수</span> </p> </td> 
   <td colname="col2"> <p>광고 단위 항목 1 - 8을 방문한 사용자 수입니다. 이 정보는 Google Ad Manager 로그에서 추출됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 겹치기 고유 수</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 기본 광고 단위</span> 와 <span class="wintitle"> Overlap Ad Unit</span>을 방문한 사용자 간에 겹칩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 겹치기 비율</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 기본 광고 단위</span> 와 <span class="wintitle"> Overlap Ad Unit</span>을 방문한 사용자 간에 겹칩니다. 이것은 <span class="wintitle"> 기본 광고 단위</span>의 백분율로 표시되는 <span class="wintitle"> 겹치기 고유 개수</span>입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>
