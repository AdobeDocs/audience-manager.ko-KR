---
description: 광고 단위 겹치기 보고서는 광고 단위 간의 높음 및 낮음 겹침을 강조 표시하는 히트차트로 표시됩니다.
seo-description: The Ad Unit Overlap report is displayed as a heat chart that highlights high and low overlaps between your Ad Units.
seo-title: Ad Unit Overlap
solution: Audience Manager
title: 광고 단위 겹치기
uuid: e4467e81-acbf-474e-b501-89d57395651f
feature: Audience Optimization Reports
exl-id: 08b219c6-bf0c-4473-9459-83b3657dfb15
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%

---

# 광고 단위 겹치기{#ad-unit-overlap}

**[!UICONTROL Ad Unit Overlap]** 보고서는 광고 단위 간의 높음 및 낮음 겹침을 강조 표시하는 히트차트로 표시됩니다.

## 사용 사례 {#use-cases}

**[!UICONTROL Ad Unit Overlap]** 보고서를 사용하면 웹 속성에서 대상이 겹치는 insight을 가져올 수 있습니다. 이 보고서는 100개의 상위 관련 속성을 고려하며 이들 속성 간의 겹침을 보여 줍니다.

## 광고 단위 겹치기 보고서 사용 {#using-the-report}

**[!UICONTROL Top N Base Ad Units]** 및 **[!UICONTROL Top N Overlapping Ad Units]** 컨트롤을 사용하여 겹칠 광고 단위 수를 선택합니다. 각각에 대해 최대 100개의 항목을 선택할 수 있습니다.

**일 범위** 및 **날짜 범위** 컨트롤을 사용하여 전환 확인 범위를 조정하세요. 7일 및 30일 전환 확인 기간은 일요일 날짜에만 사용할 수 있습니다.

**[!UICONTROL Base Ad Unit]** 및 **[!UICONTROL Overlap Ad Unit]** 컨트롤을 사용하여 중복 보고서에 표시할 광고 단위를 선택합니다.

>[!IMPORTANT]
>
>[!UICONTROL Audience Optimization for Publishers]을(를) 활성화할 때 [!UICONTROL Ad Unit IDs]Google 광고 관리자(이전의 DFP) 데이터 파일을 Audience Manager으로 가져오기[의 3단계에 설명된 대로 &#x200B;](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)에 대한 설명 메타데이터를 포함해야 합니다. 이렇게 하면 보고서에 웹 속성이 [!UICONTROL Ad Unit] 대신 [!UICONTROL Ad Unit ID]&#x200B;(으)로 자세히 설명되어 있습니다.

## 결과 해석 {#interpreting-results}

[!UICONTROL Ad Unit Overlap] 보고서는 아래 보고서와 유사할 수 있습니다. 특정 겹치기 항목에 대한 자세한 내용을 보려면 셀 위로 마우스를 가져갑니다. 샘플 보고서 아래 표에 있는 추가 정보에 대해서는 설명을 참조하십시오.

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
   <td colname="col2"> <p>재고 항목의 이름입니다. 예를 들어 웹 사이트 중 하나 또는 웹 사이트의 문서일 수 있습니다. 위의 이미지에서 기본 광고 단위는 문서 9 - 18입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 기본 광고 단위</span> </p> </td> 
   <td colname="col2"> <p>재고 항목의 이름입니다. 예를 들어 웹 사이트 중 하나 또는 웹 사이트의 문서일 수 있습니다. 위의 이미지에서 기본 광고 단위는 문서 1 - 8입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 겹치기 광고 단위 고유 개수</span> </p> </td> 
   <td colname="col2"> <p>광고 단위 항목 9 - 18을 방문한 사용자 수. 이 정보는 Google 광고 관리자 로그에서 추출됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 기본 광고 단위 고유 개수</span> </p> </td> 
   <td colname="col2"> <p>광고 단위 항목 1 - 8을 방문한 사용자 수. 이 정보는 Google 광고 관리자 로그에서 추출됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 중복 고유 개수</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 기본 광고 단위 </span>과(와) <span class="wintitle"> 중복 광고 단위 </span>을(를) 방문한 사용자 간의 겹칩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 겹침 비율</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 기본 광고 단위 </span>과(와) <span class="wintitle"> 중복 광고 단위 </span>을(를) 방문한 사용자 간의 겹칩니다. <span class="wintitle"> 기본 광고 단위 </span>의 비율로 표현되는 <span class="wintitle"> 중복 고유 개수</span>입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>
