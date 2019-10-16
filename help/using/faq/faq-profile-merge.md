---
description: 일반적인 프로필 병합 규칙 및 장치 그래프 질문에 대한 답변입니다.
keywords: 조직 ID
seo-description: 일반적인 프로필 병합 규칙 및 장치 그래프 질문에 대한 답변입니다.
seo-title: 프로필 병합 규칙 및 장치 그래프 FAQ
solution: Audience Manager
title: 프로필 병합 규칙 및 장치 그래프 FAQ
uuid: ba7986f1-078f-4162-aef3-b5c8740cebf4
translation-type: tm+mt
source-git-commit: a4f0b9d2252fd85322d00f965ff35a9fed04d3f8

---


# 프로필 병합 규칙 및 장치 그래프 FAQ{#profile-merge-rules-and-device-graph-faq}

일반적인 프로필 병합 규칙 및 장치 그래프 질문에 대한 답변입니다.

<!-- profile-merge-faq.xml -->

## 장치 그래프 기본 사항 {#device-graph-basics}

**디바이스 그래프란 무엇입니까?**

장치 그래프는 익명 장치 그룹을 정의하는 ID 매핑 세트입니다. 이 장치는 각 장치에서 수집된 신호의 일반적인 요소를 기반으로 개인 또는 가정에 이러한 장치를 연결합니다. 이러한 신호들은 개인 또는 가정 수준에서 장치를 식별하는 데 도움을 줍니다.

 

**외부 장치 그래프란 무엇입니까?**

외부 장치 그래프는 자체 크로스 장치 데이터 소스에서만 만들지 [!DNL Audience Manager] 않은 모든 장치 그래프입니다. 예를 들어 프로필 병합 규칙을 [만들고](merge-rules-start.md) 타사 장치 그래프 옵션을 선택하면 [!UICONTROL Co-op Device Graph] 외부 장치 그래프를 사용하여 작업하게 됩니다. 장치 [옵션을 참조하십시오](merge-rule-definitions.md#device-options).

 

**외부 장치 그래프를 사용하는 데 일반적인 사용 사례는[!UICONTROL Profile Merge Rule]무엇입니까?**

장치 그래프를 사용하는 주된 목적은 [!UICONTROL Profile Merge Rule] 한 사람 또는 한 세대에 속하는 여러 장치를 특정 세그먼트에 대해 평가하고 평가하는 것입니다. 세그먼트 자체에는 DSP에서 제공하는 광고를 통해 잠재 고객을 타깃팅하거나 온사이트 개인화 플랫폼을 통해 고객의 온사이트 경험을 개인화하는 등 다양한 용도가 있을 수 있습니다. See [External Device Graph Use Cases](external-graph-use-cases.md).

 

**Audience Manager는 외부 디바이스 그래프에 대한 글로벌 지원을 제공합니까?**

아니요. 외부 장치 그래프는 미국과 캐나다에서만 사용할 수 있습니다.

 

**외부 장치 그래프 데이터를 얼마나 자주[!DNL Audience Manager]업데이트합니까?**

일주일에 한 번

 

## 장치 그래프 및 프로필 병합 규칙 {#device-graph-profile-merge-rules}

**장치 그래프는 어떻게[!DNL Audience Manager]사용합니까?**

에서 [!DNL Audience Manager]장치 그래프는 프로파일 병합 규칙을 [만들 때 구성 옵션으로 나타납니다](merge-rules-start.md). 다음 디바이스 그래프를 [!UICONTROL Profile Merge Rules]통해 다음과 같은 작업을 수행할 수 있습니다 [!DNL Audience Manager].

* 여러 디바이스 프로파일을 함께 병합 이렇게 하면 단일 상위 트레이트가 만들어집니다.
* 각 장치 프로파일을 개별적으로 평가하는 대신 세그먼트 자격에 대한 트레이트 상위 세트를 평가합니다.
* 사용 가능한 세그먼트에 자격 조건을 갖춘 장치를 추가합니다.

 

**몇 개를 만들[!UICONTROL Profile Merge Rules]수 있습니까?**

현재 최대 4개를 만들 수 [!UICONTROL Profile Merge Rules]있습니다. 네 번째 프로필 병합 규칙([!UICONTROL All Cross-Device Profiles])은 [!UICONTROL People-Based Destinations] Add-on을 구매하는 고객만 사용할 수 있습니다.

 

**장치 그래프를 사용할 때 병합하고 읽을 수 있는 장치 프로파일은[!DNL Audience Manager][!UICONTROL Profile Merge Rule]몇 개입니까?**

Audience Manager는 장치를 사용하여 세그먼트용으로 자격을 부여하면 현재 장치 프로파일과 선택한 장치 그래프 옵션으로 연결된 최대 99개의 추가 장치 프로파일을 취합하여 읽습니다. [!UICONTROL Profile Merge Rule]

 

**장치 그래프를 사용할 때 어떤 장치가 세그먼트에 적합합니까?[!UICONTROL Profile Merge Rule]**

장치 [!DNL Audience Manager] 병합 및 읽기는 세그먼트에 적합한 장치와 동일한 장치입니다.

 

**장치 그래프를 사용하는 세그먼트는 어디에서[!DNL Audience Manager]보낼 수[!UICONTROL Profile Merge Rule]있습니까?**

[!DNL Audience Manager] 세그먼트를 배치 파일 또는 실시간으로 대상에 보낼 수 있습니다.

 

## 세그먼트, 장치 그래프 및 프로필 병합 규칙 {#segments-device-graphs-rules}

**장치 그래프를 사용하는 세그먼트에 대해 더 이상 자격이 없을 때 장치의[!DNL Audience Manager][!UICONTROL Profile Merge Rule]세그먼트를 해제할 수 있는 방법은 무엇입니까?**

Audience Manager는 세그먼트를 장치 그래프를 사용하는 장치로 평가할 때 최대 100개의 장치를 [!UICONTROL Profile Merge Rule] 병합합니다. 세그먼트 해제 신호가 발행되면 현재 장치와 최대 99개의 추가 장치가 대상의 세그먼트에서 제거됩니다. 세그멘테이션에 대한 자세한 내용은 프로필 [병합 규칙 및 장치 세그멘테이션 취소 프로세스를 참조하십시오](merge-rule-unsegment.md).

 

**대상이 장치 세그먼트를 해제할 수 있는 경우 장치 그래프를 사용하는[!UICONTROL Profile Merge Rules]방식으로 장치가 세그먼트에서 제거됩니까?**

예. 위의 설명을 참조하십시오.

 

**장치 그래프를 사용하는 세그먼트가[!UICONTROL Profile Merge Rule]있는 경우 세그먼트가 실시간 및 온보드 데이터를 모두 사용하는 경우 내 세그먼트가 온보드 데이터 변경 사항으로 업데이트됩니까?**

예. 

 

**세그먼트 크기 추정치에는 장치 그래프 옵션을 사용하는 연결로 제공되는[!UICONTROL Profile Merge Rule]세그먼트를 평가하는 장치가 포함되어 있습니까?**

아니요. 세그먼트 빌더의 트레이트 및 세그먼트 [!UICONTROL Estimated Real-Time Population] 채우기 데이터에 대한 정의를 [!UICONTROL Estimated Total Population] 참조하십시오 [](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/segments/segment-builder-data.html).

 

**장치 그래프 옵션을 사용하는 연결에서 제공하는 연결을 기반으로 한 세그먼트에 적합한 장치를[!UICONTROL Addressable Audiences][!UICONTROL Profile Merge Rule]포함합니까?**

예. 

 

**세그먼트가[!UICONTROL Profile Merge Rule]with를 사용하고 세그먼트에 맞는 장치를[!UICONTROL No Cross-Device Profile]분류할 수 있는 트레이트가 장치 간 프로필에만 저장되어 있는 경우 세그먼트의 총 인구는 0이 됩니까?**

예. 프로필 병합 규칙이 로 설정된 경우 Audience Manager는 세그먼트 평가에서 장치 간 프로필에 저장된 트레이트를 카운트하지 않습니다 [!UICONTROL No Cross-Device Profile].

 

## 트레이트 빈도, 장치 그래프 및 프로필 병합 규칙 {#trait-freq-device-rules}

**장치 그래프를 사용하는 것으로 트레이트 빈도를 어떻게[!DNL Audience Manager][!UICONTROL Profile Merge Rule]계산합니까?**

트레이트 빈도는 여러 장치에서 특정 트레이트에 대한 자격 수의 합으로 정의됩니다. 이를 이해하려면 다음 사용 사례를 살펴보십시오.

<table id="table_DE7A308705C84B93B3089CAD2228569E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 사용 사례 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>조건</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_52EA0F142E3F488CAAC7CF541E7F3472"> 
      <li id="li_11228EC0266A4A02BB4057B77FE93A8A">장치 A와 장치 B는 장치 그래프로 연결됩니다. </li> 
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">장치 그래프 옵션을 <span class="wintitle"> 사용하는</span> 프로필 병합 규칙이 있습니다. </li> 
      <li id="li_B46C4DE6CBD44D44B0F02EC9987140A5">단일 트레이트(트레이트 1)로 구성된 단일 세그먼트(세그먼트 1)로서, 트레이트 1의 빈도는 8입니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>작업</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience</span> Manager는 장치 A 및 장치 B에 대한 장치 프로파일을 읽고 병합합니다.여기에서 다음을 확인할 수 있습니다. </p> <p> 
     <ul id="ul_7AB307154C034695B4486E68D55CB084"> 
      <li id="li_5760BEE513C94152AA307AEE10894718">장치 A는 트레이트를 3번 인증했습니다. 트레이트 1의 주파수는 3입니다. </li> 
      <li id="li_E20BC24CCCEC407C820A8032D56BC3F0">장치 B가 트레이트 15번 자격을 획득했습니다. 트레이트 1의 경우 5회 주파수입니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>결과</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience</span> Manager는 트레이트 1의 빈도를 합계하고 8(3 + 5 = 8)을 사용하여 세그먼트 자격을 결정합니다. 장치 A와 장치 B는 8의 주파수를 가지므로 세그먼트 1을 사용할 수 있습니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

## 보고서, 장치 그래프 및 프로필 병합 규칙 {#reports-device-graphs-rules}

**장치 그래프를 사용하는 장치로 연결할 수 있는 장치 수를 볼 수[!UICONTROL Profile Merge Rule]있습니까?**

예. 보고서는 [!UICONTROL Profile Merge Rule] 수준에서 데이터를 반환합니다. 보고서 데이터는 매일 업데이트됩니다. 데이터는 장치 그래프로 연결된 장치가 아니라 계정에 표시되는 장치를 기반으로 합니다. 프로필 [병합 규칙에 대한 보고서 지표를 참조하십시오](profile-link-metrics.md).

 

**장치 그래프를 사용하는 특정 세그먼트에 대해 적격한 장치의 수를&#x200B;*실시간으로*볼 수[!UICONTROL Profile Merge Rules]있습니까?**

예. 실시간 모집단 지표는 장치 그래프로 연결된 모든 장치의 프로필을 사용하여 현재 장치(실시간으로 표시되는 장치)에 대한 세그먼트 자격 조건을 캡처합니다.

<table id="table_D37A51E99B314C04A96A084491A5FEC7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 사용 사례 요소 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>조건</b> </p> </td> 
   <td colname="col2"> <p>다음과 같은 기능이 있다고 가정합니다. </p> <p> 
     <ul id="ul_B8B627FBF6A04C0CAE6C8543EA3EA56D"> 
      <li id="li_2557CE3F109C42DC8CB5E99B93E96265">다음 트레이트 및 자격 로직을 기반으로 구축된 세그먼트 1:세그먼트 1 = 트레이트 A 및 트레이트 B와 트레이트 C. </li> 
      <li id="li_F7D559B3C0CA424DA2C1A0703C1E1717">디바이스 프로파일 3개:장치 1(현재 장치), 장치 2(장치 그래프), 장치 3(장치 그래프). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>작업</b> </p> </td> 
   <td colname="col2"> <p>사용 가능한 각 트레이트는 장치와 연결됩니다. </p> <p> 
     <ul id="ul_E60A5CBBEC484BB78F2A4AB0D6306019"> 
      <li id="li_26D7300BA0164426949FA43A60AC7023">장치 1:특성 A </li> 
      <li id="li_B0C3D7ACC7754ED985974317362AFF85">장치 2:트레이트 B </li> 
      <li id="li_32C32DD0E87F461AA2C7FB77FB35C6DA">장치 3:트레이트 C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>결과</b> </p> </td> 
   <td colname="col2"> <p>이전 요소가 주어지면 세그먼트 1의 총 모집단 수가 1입니다. </p> <p>이 경우 프로필 병합 <span class="wintitle"> 규칙은</span> 모든 장치 및 특성을 사용하여 세그먼트 자격 조건을 결정합니다. 즉, 장치 1, 2 및 3은 세그먼트 1의 자격이 되지만 위에서 언급한 바와 같이 실시간 세그먼트 모집단에는 장치 1만 포함됩니다. 이는 다음과 같습니다. </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">장치 1은 Audience Manager DCS(Data Collection <span class="wintitle"> Server</span> )와 실시간으로 상호 작용하는<span class="wintitle"> 현재</span>장치입니다. </li> 
      <li id="li_57165E96289F4E20BF2244BC68B90BA3">장치 2 및 3은 장치 그래프로 장치 1과 연결되지만 장치 1과 동시에 DCS와 상호 작용하지 않습니다. </li> 
     </ul> </p> <p>따라서 장치 2와 3은 실시간 세그먼트 모집단 지표에 포함되지 않습니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**장치 그래프를 사용하는 특정 세그먼트에 대해 자격이 있는 장치의 총 수를 볼[!UICONTROL Profile Merge Rule]수 있습니까?**

예. 총 세그먼트 채우기 지표에는 장치 그래프의 연결을 기반으로 세그먼트에 대한 자격이 있는 추가 장치가 포함됩니다.

<table id="table_932E61B1D4374DD58F673C3B35C365EB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 사용 사례 요소 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>조건</b> </p> </td> 
   <td colname="col2"> <p>다음과 같은 기능이 있다고 가정합니다. </p> <p> 
     <ul id="ul_DC0AC0F79323451C8C2480E4A85AE2EB"> 
      <li id="li_790F24FA1F0747F385640EDB1AE9E59E">다음 트레이트 및 자격 로직을 기반으로 구축된 세그먼트 1:세그먼트 1 = 트레이트 A 및 트레이트 B와 트레이트 C. </li> 
      <li id="li_6628727DDD0644BF8F5B6A8A9FA71E67">디바이스 프로파일 3개:장치 1(현재 장치), 장치 2(장치 그래프), 장치 3(장치 그래프). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>연결</b> </p> </td> 
   <td colname="col2"> <p>사용 가능한 각 트레이트는 장치와 연결됩니다. </p> <p> 
     <ul id="ul_FE16B1639D2541009110E77A605D2CE0"> 
      <li id="li_25959C3822384CFAB8B18D3CD80A30DD">장치 1:특성 A </li> 
      <li id="li_CDAC38F4CF3A4BEDA49A92BAEC48583E">장치 2:트레이트 B </li> 
      <li id="li_6063A91C482E48FD9FC5C00600B05E31">장치 3:트레이트 C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>결과</b> </p> </td> 
   <td colname="col2"> <p>이전 요소가 주어지면 세그먼트 1의 총 모집단 수는 3입니다. </p> <p>이 경우 프로필 병합 <span class="wintitle"> 규칙은</span> 모든 장치 및 특성을 사용하여 세그먼트 자격 조건을 결정합니다. 즉, 장치 1, 2 및 3은 세그먼트 1의 자격이 되고 세 개 모두 총 모집단에 포함됩니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**장치 그래프를 사용하는 세그먼트가 보고서,[!UICONTROL Profile Merge Rule]보고서 및[!UICONTROL Interactive]보고서에 포함되어 있는 경우 해당 장치가[!UICONTROL Overlap][!UICONTROL Audience Optimization]세그먼트에 적합합니까?**

아니요. 

>[!MORELIKE_THIS]
>
>* [프로필 링크](merge-rules-overview.md)

