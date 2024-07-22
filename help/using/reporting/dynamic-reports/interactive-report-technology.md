---
description: 대화형 보고서 및 데이터 업데이트 일정을 지원하는 기본 소프트웨어에 대해 설명합니다.
seo-description: Describes the underlying software that powers the interactive reports and the data update schedule.
seo-title: Report Technology
solution: Audience Manager
title: 보고서 기술
uuid: 5f3d815b-e1e6-42f2-b848-ac035a5aa77d
feature: Overlap Reports
exl-id: 59d875d6-a630-4795-93a7-1d432860f0a1
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 0%

---

# 보고서 기술{#report-technology}

대화형 보고서 및 데이터 업데이트 일정을 지원하는 기본 소프트웨어에 대해 설명합니다.

<!-- 

c_report_technology.xml

 -->

## Tableau 기술을 사용하는 대화형 보고서

[!DNL Audience Manager]은(는) [Tableau](https://www.tableausoftware.com/) 소프트웨어를 사용하여 대화형 보고서에 데이터를 표시합니다. [!DNL Tableau]에서 [!UICONTROL Delivery and Overlap] 보고서는 다음 작업에 도움이 되는 시각적 큐와 기호를 사용합니다.

* 고성능 및 저성능의 특성을 찾습니다.
* 고유 방문자 수가 적고 높은 스팟 트레이트 및 세그먼트가 겹칩니다.
* 중복 데이터를 사용하여 타깃팅된 세그먼트를 만듭니다.
* 겹치는 부분이 낮은 관련 트레이트를 식별하여 도달 범위를 넓힌다.

## 데이터 업데이트 일정

보고서 데이터는 매주 일요일에 업데이트됩니다. 업데이트는 토요일(전날)부터 이전 일요일까지 데이터를 처리합니다.

## 대화형 보고서에 사용되는 모양, 색상 및 크기 {#shapes-colors-sizes}

대부분의 대화형 보고서는 서로 다른 크기와 색상의 모양을 사용하여 결과를 표시합니다. 이 표시 형식은 숫자의 행과 열을 검색하지 않고도 데이터를 시각적으로 이해할 수 있도록 설계되었습니다.

<!-- 

r_legend.xml

 -->

### 보고서 범례

다음 표는 동적 보고서에 사용되는 모양, 크기 및 색상을 정의합니다.

<table id="table_EC180A96E3784FC6B81FCFB546C4A3FA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 데이터 요소 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>도형</b> </td> 
   <td colname="col2"> 
    <ul id="ul_076773ABD0BB4CE6834ACFA8B3D6AC2E"> 
     <li id="li_BBAB37A6EC1549B48C0E4D3BFAF7062C">원은 고유한 자사 특성을 나타냅니다. </li> 
     <li id="li_371331AE984A4A999CE0596EA13987E0">사각형은 서드파티 특성을 나타냅니다. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>색상</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F5D243297F0C4E5A8EDCBD28A548869E"> 
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">빨간색 음영은 <i>low</i> 겹침을 나타냅니다. </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">녹색 음영은 <i>높음</i> 겹침을 나타냅니다. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>크기</b> </td> 
   <td colname="col2"> 도달 가능 여부(트레이트 또는 세그먼트의 클릭 수 또는 고유 사용자 수 또는 비율)에 따라 크기가 증가하거나 감소합니다. </td> 
  </tr> 
 </tbody> 
</table>

## 타블로 설명서 {#tableau-documentation}

대화형 보고서에서 볼 수 있는 Tableau 컨트롤에 대한 자세한 내용은 [Linux 2018.2](https://help.tableau.com/v2018.2/server-linux/en-us/get_started_server.htm)의 Tableau Server 공식 설명서를 참조하십시오.
