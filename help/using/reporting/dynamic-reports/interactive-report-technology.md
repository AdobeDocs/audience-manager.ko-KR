---
description: 대화형 보고서 및 데이터 업데이트 일정을 지원하는 기본 소프트웨어에 대해 설명합니다.
seo-description: 대화형 보고서 및 데이터 업데이트 일정을 지원하는 기본 소프트웨어에 대해 설명합니다.
seo-title: 보고서 기술
solution: Audience Manager
title: 보고서 기술
uuid: 5f3d815b-e1e6-42f2-b848-ac035a5aa77d
translation-type: tm+mt
source-git-commit: b5a962381780f1a1627e39b59e3ca86fd51763b5

---


# 보고서 기술{#report-technology}

대화형 보고서 및 데이터 업데이트 일정을 지원하는 기본 소프트웨어에 대해 설명합니다.

<!-- 

c_report_technology.xml

 -->

## 대화형 보고서는 타블로 기술을 사용합니다.

[!DNL Audience Manager] 타블로 [소프트웨어를](https://www.tableausoftware.com/) 사용하여 대화형 보고서에 데이터를 표시합니다. 이 [!DNL Tableau]보고서에서는 [!UICONTROL Delivery and Overlap] 다음과 같은 기능을 제공하는 시각적 큐와 기호를 사용합니다.

* 높은 성능과 낮은 성능의 트레이트를 찾아보십시오.
* 낮은 고유 방문자와 높은 고유 방문자가 겹치는 트레이트 및 세그먼트를 찾을 수 있습니다.
* 중복 데이터를 사용하여 타깃팅된 세그먼트를 만듭니다.
* 오버랩이 낮은 관련 트레이트를 식별하여 도달 범위를 확장할 수 있습니다.

## 데이터 업데이트 일정

보고서 데이터는 매주 일요일마다 업데이트됩니다. 업데이트는 데이터를 토요일에서 이전 일요일로 다시 처리합니다.

## 대화형 보고서에 사용된 모양, 색상 및 크기 {#shapes-colors-sizes}

대부분의 대화형 보고서는 다양한 크기와 색상의 모양을 사용하여 결과를 표시합니다. 이 표시 형식은 행과 숫자 열을 일일이 확인하지 않고도 데이터를 시각적으로 이해할 수 있도록 설계되었습니다.

<!-- 

r_legend.xml

 -->

### 보고서 범례

다음 표에서는 동적 보고서에 사용되는 모양, 크기 및 색상을 정의합니다.

<table id="table_EC180A96E3784FC6B81FCFB546C4A3FA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 데이터 요소 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>모양</b> </td> 
   <td colname="col2"> 
    <ul id="ul_076773ABD0BB4CE6834ACFA8B3D6AC2E"> 
     <li id="li_BBAB37A6EC1549B48C0E4D3BFAF7062C">원은 자사 특성을 나타냅니다. </li> 
     <li id="li_371331AE984A4A999CE0596EA13987E0">제곱은 타사 트레이트를 나타냅니다. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>색상</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F5D243297F0C4E5A8EDCBD28A548869E"> 
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">빨간색 음영은 <i>낮은</i> 오버랩을 나타냅니다. </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">녹색 색상은 <i>높은</i> 겹침을 나타냅니다. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>크기</b> </td> 
   <td colname="col2"> 크기는 도달에 직접적으로 비례하여 증가 또는 감소합니다(트레이트 또는 세그먼트에서 클릭 수 또는 고유 사용자 수 또는 %). </td> 
  </tr> 
 </tbody> 
</table>

## 보고서 아이콘 및 도구 설명 {#icons-tools-explained}

동적 보고서에 사용되는 다양한 아이콘 도구를 검색하고 사용하는 방법에 대해 설명합니다.

<!-- 

r_icons.xml

 -->

### 데이터 아이콘 및 도구

다음 아이콘-도구는 각 동적 보고서 창의 아래쪽에 있습니다. 다음 그림은 이러한 도구에 대한 자세한 정보를 제공합니다.

![](assets/tools_icons90.png)

### 데이터 내보내기

이 도구를 사용하면 보고서의 데이터를 4개의 서로 다른 형식으로 내보낼 수 있습니다.

| 내보내기 옵션 | 데이터 내보내기 |
|---|---|
| **[!UICONTROL Image]** | 이미지(.png) 파일로, 보고서 데이터를 원본 그래픽 형식으로 다운로드하고 공유하려는 경우 유용합니다. |
| **[!UICONTROL PDF]** | PDF 파일로 저장 |
| **[!UICONTROL Data]** | 새 브라우저 창에서 열 및 행의 숫자 데이터로 |
| **[!UICONTROL Crosstab]** | .csv 파일로 |

### 변경 내용 되돌리기

보고서에서 수행한 대화형 클릭 변경 사항을 실행 취소하려면 이 도구를 선택합니다.

### 자동 업데이트

및 보고서는 [!UICONTROL Delivery-Performance] 사용자 클릭 동작에 따라 응답하고 변경하는 동적 보고서입니다 [!UICONTROL Trait-to-Trait Overlap] .

예를 들어 보고서에서 여러 광고주를 선택한다고 [!UICONTROL Overlap] 가정해 봅시다. 활성화되면 확인란을 선택하자마자 자동 업데이트가 데이터를 반환하기 시작합니다. 다른 광고주를 선택하기 전에 보고서 처리가 완료될 때까지 기다려야 하므로 이 동적 동작은 워크플로우를 방해할 수 있습니다. 이 도구를 사용하여 필요에 따라 해당 기능을 해제(및 다시 켜기)합니다.

### 데이터 새로 고침

새로 고침 아이콘을 클릭하여 보고서를 실행하거나 데이터 세트를 다시 로드합니다. 자동 업데이트가 꺼져 있으면 새로 고침을 클릭하여 보고서를 실행하거나 업데이트합니다.

### 검색 도구

검색은 일반 확대경 아이콘(표시되지 않음)으로 표시됩니다. 검색 필드는 화면 왼쪽의 선택 레이블을 클릭할 때까지 숨겨집니다. 아래 표에서는 각 보고서에 대한 검색 도구의 위치를 설명합니다.

| 보고서 | 검색을 찾으려면 마우스를 |
|---|---|
| [!UICONTROL Delivery and Performance] 보고서에 표시되지 않습니다 | "광고주 이름" 레이블입니다. |
| [!UICONTROL Overlap] 보고서 | "SID 이름" 레이블입니다. |
