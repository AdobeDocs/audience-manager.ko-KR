---
description: 프로필 링크 지표는 사이트에 인증하는 사람 및 장치에 대한 데이터를 제공합니다. 병합 규칙을 만들거나 프로필 병합 규칙 대시보드에서 기존 규칙을 클릭하면 프로필 링크의 데이터 및 그래프가 동적으로 업데이트됩니다. 이러한 지표에는 Adobe Experience Cloud Device Co-op 또는 기타 타사 장치 그래프 소스의 장치 그래프가 포함될 수 있습니다.
seo-description: 프로필 링크 지표는 사이트에 인증하는 사람 및 장치에 대한 데이터를 제공합니다. 병합 규칙을 만들거나 프로필 병합 규칙 대시보드에서 기존 규칙을 클릭하면 프로필 링크의 데이터 및 그래프가 동적으로 업데이트됩니다. 이러한 지표에는 Adobe Experience Cloud Device Co-op 또는 기타 타사 장치 그래프 소스의 장치 그래프가 포함될 수 있습니다.
seo-title: 프로필 병합 규칙에 대한 보고서 지표
solution: Audience Manager
title: 프로필 병합 규칙에 대한 보고서 지표
uuid: 76a86ff0-4c64-4734-aec0-0a8828942096
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# 프로필 병합 규칙에 대한 보고서 지표 {#report-metrics-for-profile-merge-rules}

[!UICONTROL Profile Merge Rule] 지표는 사이트에 인증하는 사람 및 장치에 대한 데이터를 제공합니다. 병합 규칙을 만들거나 대시보드에서 기존 규칙을 클릭할 때 데이터 및 그래프가 동적으로 [!UICONTROL Profile Merge Rule Reports] [!UICONTROL Profile Merge Rules] 업데이트됩니다. 이러한 지표는 [!DNL Adobe Experience Cloud Device Co-op] 또는 기타 타사 장치 그래프 소스의 장치 그래프를 포함할 수 있습니다.

## 규칙 지표 병합 {#merge-rule-metrics}

보고서는 병합 규칙이 Adobe Experience Cloud Device Co-op [이나](https://marketing.adobe.com/resources/help/en_US/mcdc/) 액세스 권한이 있는 다른 타사 장치 그래프의 데이터를 사용할 때 막대 그래프로 데이터를 나란히 반환합니다 [!DNL Audience Manager]. 이렇게 하면 인증된 자사 데이터와 [!UICONTROL Experience Cloud Device Co-op] 또는 다른 타사 장치 그래프에서 제공하는 장치 간 데이터를 비교할 수 있습니다. 에서 반환한 데이터에 대한 자세한 [!UICONTROL Device Co-op]내용은 장치 [그래프를 참조하십시오.내부 프로세스 및 출력](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-processes.html). 이 데이터는 매일 업데이트됩니다.

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
     <li id="li_FE2F93C496D64ED8928B3E522C9585EA"> <span class="wintitle"> 활성 사용자</span>:지난 60일 동안 사이트에 인증한 사람 수입니다. </li> 
     <li id="li_60CFD26EE68B442683C0ED5FED1A79C8"> <span class="wintitle"> 크로스 디바이스</span>:선택한 인증된 프로필의 데이터 소스에 <a href="merge-rules-start.md#create-data-source"> 저장된</a> 전체 <a href="https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/manage-datasources.html"> 장치</a> ID의 <a href="merge-rule-definitions.md"> 총</a> 수입니다. 데이터 소스가 존재했던 라이프타임 동안 </li> 
     <li id="li_F2F07B6A326C4A18B79A0CF2C47D9677"> <span class="wintitle"> % 활성 사용자</span>:활성 <span class="wintitle"> 사람을</span> %로 표시합니다. </li> 
    </ul> <p> <span class="wintitle"> 인증된 활동을</span> 사용하면 활동, 볼륨 및 비율별로 데이터 소스를 비교할 수 있습니다. 많은 사람과 활성 사용자 중 높은 비율이 있는 데이터 소스를 찾는 데 도움이 됩니다. 또는 총 고객 수와 비교하여 활성 사용자의 비율이 높은 데이터 소스를 비교하는 데 있어 가치를 찾을 수 있습니다. 예를 들어, 전체 라이프타임 수가 낮고 활동이 많은 데이터 소스는 라이프타임 결과가 높고 활동 수가 적은 데이터 소스입니다. </p> <p> <p>참고:인증된 <span class="wintitle"> 활동</span> 지표에는 프로필 링크 <span class="wintitle"> 데이터만</span> 포함됩니다. 이 보고서에는 장치 그래프 <span class="wintitle"> 데이터가 포함되지</span> 않습니다. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> 1인당 평균 장치</span></b> </p> </td> 
   <td colname="col2"> <p> 선택한 데이터 소스에 대해 사이트에 인증한 방문자가 사용한 평균 장치 수를 표시합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> 총 장치 수</span></b> </p> </td> 
   <td colname="col2"> <p>선택한 데이터 소스에 대해 사용자가 사이트에 인증하는 데 사용한 총 장치 수를 보여줍니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> 총 사용자 수</span></b> </p> </td> 
   <td colname="col2"> <p>선택한 데이터 소스에 대해 결정적으로 식별된 총 사람 수를 표시합니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 장치 그래프 지표 {#device-graph-metrics}

또한 [!UICONTROL Merge Rules] 보고서는 선택한 데이터 소스 및 장치 그래프의 사이트를 방문한 총 사람 및 장치 수에 대한 데이터를 보여줍니다. 이러한 지표는 규칙을 만들 때 선택하는 장치 옵션에 따라 달라지는 사전 설정된 시간 간격(뒤로 보기 기간)을 기반으로 데이터를 반환합니다. 다음 표는 각 장치 그래프 옵션에 대한 이러한 보고서 간격을 나열합니다.

<table id="table_038983EBC71F4A55BBCA99212AC5DEE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 장치 그래프 옵션 </th> 
   <th colname="col2" class="entry"> 보고서 검색 간격 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 프로필 링크</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_B2FF2341573840549FFB96579F537082"> 
      <li id="li_B37323C2F2434F41B407500AC5C15447">총 사용자 수:60일 </li> 
      <li id="li_08D911224A60418BBB3CFB4E70CE73D4">총 장치 수:120일 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Co-op 장치 그래프</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_64AD1DD89DF64703B70B973A463BA020"> 
      <li id="li_D7D3A3871F434CBFA71BE8929EB41648">총 사용자 수:180일 </li> 
      <li id="li_125D387986B2463EB310203CE5857EDA">총 장치 수:180일 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> LiveRamp</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_2772F3AD7E1440789B635794ECDE8DFB"> 
      <li id="li_1432363829D64615B1D349A3722D6268">총 사용자 수:180일 </li> 
      <li id="li_D5C0E3CE92524B54BBD36C73A326292B">총 장치 수:180일 </li> 
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

표준 [!UICONTROL Profile Link] 보고서는 다음 예와 같습니다. 여러 데이터 소스(최대 3개, 최대)를 사용하는 병합 규칙은 각 데이터 소스에 대해 별도의 탭에 그래프를 표시합니다. 이 병합 규칙에는 [!UICONTROL Device Co-op] 데이터가 포함되지 않습니다.

![](assets/profile-link-metrics.png)

### 장치 그래프 데이터가 있는 프로필 링크 보고서

타사 장치 그래프의 장치 그래프 데이터가 [!UICONTROL Profile Link Device Graph] 포함된 [!UICONTROL Adobe Experience Cloud Device Co-op] 보고서는 나란히 막대 그래프와 함께 [!UICONTROL Profile Link] 장치 그래프 데이터를 보여줍니다. 이러한 그래프를 서로 인접하여 배치하면 [!UICONTROL Experience Cloud Device Co-op] 비교 결과를 사용한 이점을 평가할 [!UICONTROL Profile Link] 수 있습니다. 여러 데이터 소스(최대 3개, 최대)를 사용하는 병합 규칙은 각 데이터 소스에 대해 별도의 탭에 그래프를 표시합니다. 다시 말해, [!UICONTROL Authenticated Activity] 그래프와 지표는 사용자가 액세스할 수 있는 장치 그래프나 기타 타사 장치 그래프에서 데이터를 반환하지 않습니다 [!DNL Adobe] [!DNL Audience Manager].

![](assets/profile-link-graph.png)

## 프로필 링크 트렌드 그래프 {#profile-link-trend}

다른 데이터 시각화 외에도 [!UICONTROL Profile Link] 보고서에는 라인 그래프가 포함됩니다. 라인 그래프는 시간 경과에 따른 프로필 규칙 트렌드를 표시하도록 디자인되었습니다. 트렌드 그래프(및 기타 보고서)는 [!UICONTROL Profile Merge Rules] 랜딩 페이지( **[!UICONTROL Audience Data > Profile Merge Rules]**)에서 규칙을 클릭할 때 사용할 수 있습니다. 이러한 그래프에는 사용자가 [!UICONTROL Device Co-op] 또는 타사의 장치 그래프에 액세스할 수 있는 경우 장치 그래프 데이터가 포함됩니다 [!DNL Audience Manager]. 트렌드 라인을 클릭하여 기본 데이터를 봅니다.

>[!MORELIKETHIS]
>
>* [프로필 병합 규칙 FAQ](../../faq/faq-profile-merge.md)

