---
description: 프로필 링크 지표는 사이트를 인증하는 사람 및 장치에 대한 데이터를 제공합니다. 프로필 링크 의 데이터 및 그래프는 병합 규칙을 만들거나 프로필 병합 규칙 대시보드에서 기존 규칙을 클릭할 때 동적으로 업데이트됩니다. 이러한 지표에는 Adobe Experience Cloud Device Co-op 또는 기타 타사 장치 그래프 소스의 장치 그래프가 포함될 수 있습니다.
seo-description: 프로필 링크 지표는 사이트를 인증하는 사람 및 장치에 대한 데이터를 제공합니다. 프로필 링크 의 데이터 및 그래프는 병합 규칙을 만들거나 프로필 병합 규칙 대시보드에서 기존 규칙을 클릭할 때 동적으로 업데이트됩니다. 이러한 지표에는 Adobe Experience Cloud Device Co-op 또는 기타 타사 장치 그래프 소스의 장치 그래프가 포함될 수 있습니다.
seo-title: 프로필 병합 규칙에 대한 보고서 지표
solution: Audience Manager
title: 프로필 병합 규칙에 대한 보고서 지표
uuid: 76a86ff0-4c64-4734-aec0-0a8828942096
feature: 프로필 병합
exl-id: 2af59c60-2448-44af-90d2-eccc52f7ff02
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '835'
ht-degree: 2%

---

# 프로필 병합 규칙에 대한 보고서 지표 {#report-metrics-for-profile-merge-rules}

[!UICONTROL Profile Merge Rule] 지표는 사이트를 인증하는 사람 및 장치에 대한 데이터를 제공합니다. [!UICONTROL Profile Merge Rule Reports]의 데이터와 그래프는 병합 규칙을 만들거나 [!UICONTROL Profile Merge Rules] 대시보드에서 기존 규칙을 클릭할 때 동적으로 업데이트됩니다. 이러한 지표에는 [!DNL Adobe Experience Cloud Device Co-op] 또는 다른 타사 장치 그래프 소스의 장치 그래프가 포함될 수 있습니다.

## 병합 규칙 지표 {#merge-rule-metrics}

병합 규칙이 [Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html) 또는 [!DNL Audience Manager]에서 액세스할 수 있는 다른 타사 장치 그래프의 데이터를 사용하는 경우 보고서는 데이터를 나란히 막대 그래프로 반환합니다. 이렇게 하면 인증된 자사 데이터를 [!UICONTROL Experience Cloud Device Co-op] 또는 다른 타사 장치 그래프에서 제공한 교차 장치 데이터와 비교할 수 있습니다. [!UICONTROL Device Co-op]에서 반환한 데이터에 대한 자세한 내용은 [장치 그래프를 참조하십시오.내부 프로세스 및 출력](https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/device-graph-overview.html). 이 데이터는 매일 업데이트됩니다.

<table id="table_A7FB2F9804F84AC8A6DD05C0E6EE7555"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 지표 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> 인증된 활동</span></b> </p> </td> 
   <td colname="col2"> <p>표시: </p> 
    <ul id="ul_7F7373919A4A49028EF4BF7B28D9F8E9"> 
     <li id="li_FE2F93C496D64ED8928B3E522C9585EA"> <span class="wintitle"> 활성 사용자</span>:지난 60일 동안 사이트에 대해 인증한 사람 수입니다. </li> 
     <li id="li_60CFD26EE68B442683C0ED5FED1A79C8"> <span class="wintitle"> 교차 장치</span>:데이터 소스 <a href="merge-rules-start.md#create-data-source"> 가 존재했던 라이프타임</a> 에 대해 선택한  <a href="https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/manage-datasources.html"> 인증된 프로필</a> 의  <a href="merge-rule-definitions.md">  </a> 데이터 소스에 저장된 총 교차 장치 ID 수입니다. </li> 
     <li id="li_F2F07B6A326C4A18B79A0CF2C47D9677"> <span class="wintitle"> 활성 사용자</span> %:활성  <span class="wintitle"> 사람을 </span> %로 표시합니다. </li> 
    </ul> <p> <span class="wintitle"> 인증된 </span> 활동을 사용하면 활동, 볼륨 및 백분율별로 데이터 소스를 비교할 수 있습니다. 많은 사람과 활성 사용자가 많은 데이터 소스를 찾는 데 도움이 됩니다. 또는 데이터 소스를 전체 대상 크기와 비교하여 활성 사용자 비율이 높은 값을 찾을 수 있습니다. 예를 들어, 경우에 따라 총 라이프타임 수가 적고 활동이 많은 데이터 소스가 라이프타임 결과가 높고 활동 수가 적은 데이터보다 더 유용합니다. </p> <p> <p>참고:<span class="wintitle"> 인증된 활동</span> 지표에는 <span class="wintitle"> 프로필 링크</span> 데이터만 포함됩니다. 이 보고서에는 <span class="wintitle"> Device Graph</span> 데이터가 포함되지 않습니다. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> 1인당 평균 장치</span></b> </p> </td> 
   <td colname="col2"> <p> 선택한 데이터 소스에 대해 사이트에 인증된 방문자가 사용한 평균 장치 수를 표시합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> 총 장치</span></b> </p> </td> 
   <td colname="col2"> <p>사용자가 선택한 데이터 소스에 대한 사이트를 인증하는 데 사용한 총 장치 수를 표시합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> 총 사용자 수</span></b> </p> </td> 
   <td colname="col2"> <p>선택한 데이터 소스에 대해 결정적으로 식별된 총 사용자 수를 표시합니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 장치 그래프 지표 {#device-graph-metrics}

또한 [!UICONTROL Merge Rules] 보고서는 선택한 데이터 소스 및 장치 그래프의 사이트를 방문한 총 사용자 및 장치 수에 대한 데이터를 보여줍니다. 이러한 지표는 규칙을 만들 때 선택하는 장치 옵션에 따라 달라지는 사전 설정된 시간 간격(전환 확인 기간)을 기반으로 데이터를 반환합니다. 다음 표에는 각 장치 그래프 옵션에 대한 이러한 보고서 간격이 나열되어 있습니다.

<table id="table_038983EBC71F4A55BBCA99212AC5DEE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 장치 그래프 옵션 </th> 
   <th colname="col2" class="entry"> 보고서 전환 확인 간격 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 프로필 링크</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_B2FF2341573840549FFB96579F537082"> 
      <li id="li_B37323C2F2434F41B407500AC5C15447">총 사용자 수:60일 </li> 
      <li id="li_08D911224A60418BBB3CFB4E70CE73D4">총 장치:120일 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Co-op 장치 그래프</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_64AD1DD89DF64703B70B973A463BA020"> 
      <li id="li_D7D3A3871F434CBFA71BE8929EB41648">총 사용자 수:180일 </li> 
      <li id="li_125D387986B2463EB310203CE5857EDA">총 장치:180일 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> LiveRamp</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_2772F3AD7E1440789B635794ECDE8DFB"> 
      <li id="li_1432363829D64615B1D349A3722D6268">총 사용자 수:180일 </li> 
      <li id="li_D5C0E3CE92524B54BBD36C73A326292B">총 장치:180일 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Tapad</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_274529DB58E6442E95C6AD89BECB1362"> 
      <li id="li_67102211A72A4E47AACFE5E369793C17">총 사용자 수:60일 </li> 
      <li id="li_3E8F3DA6A7B5487895A626674DA363A5">총 장치 60일 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 샘플 보고서 {#sample-reports}

### 표준 프로필 링크 보고서

표준 [!UICONTROL Profile Link] 보고서는 다음 예제와 비슷합니다. 여러 데이터 소스를 사용하는 병합 규칙(최대 3, 최대)은 각 데이터 소스에 대한 개별 탭에 그래프를 표시합니다. 이 병합 규칙에는 [!UICONTROL Device Co-op] 데이터가 포함되지 않습니다.

![](assets/profile-link-metrics.png)

### 장치 그래프 데이터가 있는 프로필 링크 보고서

[!UICONTROL Adobe Experience Cloud Device Co-op] 또는 타사 장치 그래프의 장치 그래프 데이터를 포함하는 [!UICONTROL Profile Link Device Graph] 보고서는 [!UICONTROL Profile Link] 및 장치 그래프 데이터를 나란히 막대그래프로 표시합니다. 이러한 그래프를 서로 인접하게 배치하면 [!UICONTROL Profile Link]과 비교하여 [!UICONTROL Experience Cloud Device Co-op]을 사용하는 것의 이점을 평가할 수 있습니다. 여러 데이터 소스를 사용하는 병합 규칙(최대 3, 최대)은 각 데이터 소스에 대한 개별 탭에 그래프를 표시합니다. 미리 알림으로, [!UICONTROL Authenticated Activity] 그래프 및 지표는 [!DNL Adobe] 장치 그래프 또는 [!DNL Audience Manager]에서 액세스할 수 있는 다른 타사 장치 그래프에서 데이터를 반환하지 않습니다.

![](assets/profile-link-graph.png)

## 프로필 링크 트렌드 그래프 {#profile-link-trend}

다른 데이터 시각화 외에도 [!UICONTROL Profile Link] 보고서에는 선 그래프가 포함됩니다. 선 그래프는 프로필 규칙에 대한 시간 경과에 따른 트렌드를 보여주도록 설계되었습니다. 트렌드 그래프(및 다른 보고서)는 [!UICONTROL Profile Merge Rules] 랜딩 페이지( **[!UICONTROL Audience Data > Profile Merge Rules]**)에서 규칙을 클릭할 때 사용할 수 있습니다. 이러한 그래프는 [!UICONTROL Device Co-op] 또는 [!DNL Audience Manager]에서 액세스할 수 있는 다른 타사 장치 그래프의 구성원인 경우 장치 그래프 데이터를 포함합니다. 기본 데이터를 보려면 꺾은 선형을 클릭하십시오.

>[!MORELIKETHIS]
>
>* [프로필 병합 규칙 FAQ](../../faq/faq-profile-merge.md)

