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
source-wordcount: '408'
ht-degree: 2%

---

# 광고 단위 겹치기{#ad-unit-overlap}

다음 **[!UICONTROL Ad Unit Overlap]** 보고서는 광고 단위 간 높이와 낮은 겹침을 강조 표시하는 히트차트로 표시됩니다.

## 사용 사례 {#use-cases}

포함 **[!UICONTROL Ad Unit Overlap]** 보고서에서 대상이 웹 속성에서 겹치는 위치에 대한 통찰력을 얻을 수 있습니다. 이 보고서는 100개의 상위 관련 속성을 고려하며 이들 속성 간의 겹침을 보여 줍니다.

## 광고 단위 겹치기 보고서 사용 {#using-the-report}

사용 **[!UICONTROL Top N Base Ad Units]** 및 **[!UICONTROL Top N Overlapping Ad Units]** 를 제어하여 겹칠 광고 단위 수를 선택합니다. 각각에 대해 최대 100개의 항목을 선택할 수 있습니다.

사용 **일 범위** 및 **종료 날짜** 를 제어하여 룩백 범위를 조정합니다. 7일 및 30일 전환 확인 기간은 일요일 날짜에만 사용할 수 있습니다.

사용 **[!UICONTROL Base Ad Unit]** 및 **[!UICONTROL Overlap Ad Unit]** overlap report에 표시할 광고 단위를 선택하도록 제어합니다.

>[!IMPORTANT]
>
>활성화 시 [!UICONTROL Audience Optimization for Publishers], 다음에 대한 설명 메타데이터를 포함해야 합니다. [!UICONTROL Ad Unit IDs]의 3단계에 설명된 대로 [Google Ad Manager(이전의 DFP) 데이터 파일을 Audience Manager에 가져오기](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). 이렇게 하면 보고서에서 다음과 같이 웹 속성을 자세히 알 수 있습니다. [!UICONTROL Ad Unit] 대신 [!UICONTROL Ad Unit ID].

## 결과 해석 {#interpreting-results}

사용자 [!UICONTROL Ad Unit Overlap] 보고서는 아래 보고서와 유사할 수 있습니다. 특정 겹치기 항목에 대한 자세한 내용을 보려면 셀 위로 마우스를 가져갑니다. 샘플 보고서 아래 표에 있는 추가 정보에 대해서는 설명을 참조하십시오.

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
   <td colname="col1"> <p><span class="wintitle"> 광고 단위 고유 수 겹침</span> </p> </td> 
   <td colname="col2"> <p>광고 단위 항목 9 - 18을 방문한 사용자 수. 이 정보는 Google 광고 관리자 로그에서 추출됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 기본 광고 단위 고유 수</span> </p> </td> 
   <td colname="col2"> <p>광고 단위 항목 1 - 8을 방문한 사용자 수. 이 정보는 Google 광고 관리자 로그에서 추출됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 중복 고유 수</span> </p> </td> 
   <td colname="col2"> <p>을(를) 방문한 사용자 간의 겹침 <span class="wintitle"> 기본 광고 단위</span> 및 <span class="wintitle"> 광고 단위 겹치기</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 오버랩 비율</span> </p> </td> 
   <td colname="col2"> <p>을(를) 방문한 사용자 간의 겹침 <span class="wintitle"> 기본 광고 단위</span> 및 <span class="wintitle"> 광고 단위 겹치기</span>. 다음 은 <span class="wintitle"> 중복 고유 수</span>, 다음에 대한 백분율로 표시: <span class="wintitle"> 기본 광고 단위</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
