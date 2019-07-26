---
description: 공통 프로필 병합 규칙 및 장치 그래프 질문에 대한 답변입니다.
keywords: 조직 ID
seo-description: 공통 프로필 병합 규칙 및 장치 그래프 질문에 대한 답변입니다.
seo-title: 프로필 병합 규칙 및 장치 그래프 FAQ
solution: Audience Manager
title: 프로필 병합 규칙 및 장치 그래프 FAQ
uuid: BA 7986 F 1-078 F -4162-AEF 3-B 5 C 8740 CEBF 4
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Profile Merge Rules and Device Graph FAQ{#profile-merge-rules-and-device-graph-faq}

공통 프로필 병합 규칙 및 장치 그래프 질문에 대한 답변입니다.

<!-- 

profile-merge-faq.xml

 -->

## Device Graph Basics {#device-graph-basics}

**디바이스 그래프 소개**

장치 그래프는 익명 장치 그룹을 정의하는 ID 매핑 세트입니다. 또한 각 디바이스에서 수집한 신호의 공통 요소를 기반으로 이 장치를 개인 또는 가정에 연결합니다. 이러한 신호는 개인 또는 가정별 장치를 식별하는 데 도움이 됩니다.

<br> 

**외부 장치 그래프**

An external device graph is any device graph in [!DNL Audience Manager] that has not been created exclusively from your own cross-device data sources. For example, when you create a [Profile Merge Rule](../features/profile-merge-rules/merge-rules-start.md) and choose the [!UICONTROL Co-op Device Graph] or third-party device graph options, you're working with an external device graph. [장치 옵션을 참조하십시오](../features/profile-merge-rules/merge-rule-definitions.md#device-options).

<br> 

**A에서 외부 장치 그래프를 사용하기 위한 일반적인 사용 사례는[!UICONTROL Profile Merge Rule]무엇입니까?**

The main objective of using a device graph in a [!UICONTROL Profile Merge Rule] is to evaluate and qualify multiple devices belonging to a single person or household for a specific segment. 세그먼트 자체에는 예를 들어, DSP가 제공하는 광고 및 광고의 잠재 고객을 대상으로 하거나 온사이트 개인화 플랫폼을 통해 고객의 사이트 경험을 개인화하는 등 여러 가지 방법이 있습니다. [외부 장치 그래프 사용 사례를 참조하십시오](../features/profile-merge-rules/external-graph-use-cases.md).

<br> 

**Audience Manager는 외부 장치 그래프에 대한 글로벌 지원을 제공합니까?**

아니요. 외부 장치 그래프는 미국 및 캐나다에서만 사용할 수 있습니다.

<br> 

**외부 장치 그래프 데이터는[!DNL Audience Manager]얼마나 자주 업데이트됩니까?**

일주일에 한 번.

<br> 

## Device Graphs and Profile Merge Rules {#device-graph-profile-merge-rules}

**장치 그래프는[!DNL Audience Manager]어떻게 사용합니까?**

In [!DNL Audience Manager], device graphs appear as configuration options when you [create a Profile Merge Rule](../features/profile-merge-rules/merge-rules-start.md). Through your [!UICONTROL Profile Merge Rules], these device graphs help [!DNL Audience Manager]:

* 여러 디바이스 프로파일 병합 이를 통해 단일 주요 트레이트가 만들어집니다.
* 각 장치 프로파일을 개별적으로 평가하지 않고 세그먼트 자격 조건에 대한 트레이트 상위 세트를 평가합니다.
* 사용 가능한 세그먼트에 적격한 장치를 추가합니다.

<br> 

**[!UICONTROL Profile Merge Rules]얼마나 제작할 수 있습니까?**

Currently, you can create a maximum of 3 [!UICONTROL Profile Merge Rules].

<br> 

**A에서 장치 그래프를 사용할 때[!DNL Audience Manager]병합하고 읽은 장치 프로파일은[!UICONTROL Profile Merge Rule]몇 개입니까?**

When qualifying a device for a segment using a [!UICONTROL Profile Merge Rule], Audience Manager merges and reads the current device profile and a maximum of 3 additional device profiles linked by your selected device graph option.

<br> 

**A에서 장치 그래프를 사용할 때 세그먼트에 사용할 수 있는 장치는[!UICONTROL Profile Merge Rule]무엇입니까?**

The devices [!DNL Audience Manager] merges and reads are the same devices that are qualified for a segment.

>[!NOTE]
>
>For external device graphs, [!DNL Audience Manager] stores the mapping between devices at the platform level and selects 3 without evaluating their relationship to the devices seen in your instance of [!DNL Audience Manager].

<br> 

**장치 그래프를&#x200B;*포함하는 세그먼트를 사용하여 세그먼트를*[!UICONTROL Profile Merge Rule]분류할 수 있는 장치는 무엇입니까?**

To qualify for a segment, devices must have been seen by Audience Manager on our [edge data servers](../reference/system-components/components-edge.md) after the segment was created. 또한 Edge Server:

* 최대 14 일간 프로파일 데이터를 저장할 수 있습니다.
* 14 일 이상 비활성화된 경우 장치 프로필을 삭제합니다. 참고: 이 작업은 가장자리에서만 데이터를 제거합니다. 다른 시스템에서는 더 긴 시간 간격에 기록을 유지합니다. [개인 정보 및 데이터 유지 FAQ](../faq/faq-privacy.md)를 참조하십시오.
* Reset the 14-day interval if [!DNL Audience Manager] records any activity for that profile across the entire platform.

[데이터 수집 구성 요소를 참조하십시오](../reference/system-components/components-data-collection.md).

<br> 

**장치[!DNL Audience Manager]그래프를 사용하는 A[!UICONTROL Profile Merge Rule]로 인증된 세그먼트를 어디에서 보낼 수 있습니까?**

[!DNL Audience Manager] 세그먼트를 일괄 처리 파일의 대상 또는 실시간으로 보낼 수 있습니다. And, as noted in the FAQ entry above, To qualify for a segment, devices must have been seen by [!DNL Audience Manager] on our [edge data servers](../reference/system-components/components-edge.md) after the segment was created.

<br> 

## Segments, Device Graphs, and Profile Merge Rules {#segments-device-graphs-rules}

**장치 그래프를 사용하는 세그먼트가 있는 세그먼트에 더 이상 적합하지 않은[!DNL Audience Manager]경우 장치의[!UICONTROL Profile Merge Rule]세그먼트는 어떻게 해제됩니까?**

Audience Manager merges up to four devices when evaluating segments with a [!UICONTROL Profile Merge Rule] that uses a device graph. 세그먼트 해제 신호가 발급되면, 현재 장치 및 실시간 본 추가 장치가 대상에 있는 세그먼트에서 제거됩니다. 예를 들어, 6 장치 클러스터에서는 세그먼트에 대해 최대 4 개의 장치를 병합하고 평가하며 정규화합니다. 마찬가지로 최대 4 개의 장치가 병합되고 평가되며 세그먼트화되지 않습니다.

<br> 

**대상이 장치 세분화를 해제할 수 있는 경우 장치 그래프를 사용하는 세그먼트에서[!UICONTROL Profile Merge Rules]장치가 제거됩니다.**

예. 위의 설명을 참조하십시오.

<br> 

**장치 그래프를 사용하는 세그먼트가[!UICONTROL Profile Merge Rule]있는 세그먼트를 빌드하고 세그먼트가 실시간 데이터와 온보드 데이터를 모두 사용하고 있는 경우, 온보드 데이터가 변경되면 세그먼트가 업데이트됩니까?**

아니요. Currently, [!DNL Audience Manager] evaluates segments with a [!UICONTROL Profile Merge Rule] that uses a device graph in real-time only. Updates made to on-boarded traits after the segment has been evaluated will be used to qualify the segment when the device is next seen by our [edge data servers](../reference/system-components/components-edge.md). 여기서는 장치 프로필이 Edge Server에서 여전히 활성 상태이고, 온보드 데이터를 해당 시스템에서 사용할 수 있다고 가정합니다. [개인 정보 및 데이터 유지 FAQ](../faq/faq-privacy.md)를 참조하십시오.

<br> 

**세그먼트 크기 예측에는 장치 그래프 옵션을 사용하는에서 제공한 연결에 따라 세그먼트를 사용할 수 있는[!UICONTROL Profile Merge Rule]장치가 포함되어 있습니까?**

아니요. See the definitions for the [!UICONTROL Estimated Real-Time Population] and [!UICONTROL Estimated Total Population] in [Trait and Segment Population Data in Segment Builder](../features/segments/segment-builder-data.md).

<br> 

**장치[!UICONTROL Addressable Audiences]그래프 옵션을 사용하는 연결을 기준으로 세그먼트를 사용할 수 있는[!UICONTROL Profile Merge Rule]장치를 포함합니까?**

예. 

<br> 

**세그먼트에서 A[!UICONTROL Profile Merge Rule][!UICONTROL No Authenticated Profile]를 사용하고 세그먼트에 대한 장치가 인증된 프로필에만 영향을 주는 트레이트를 사용하는 경우 세그먼트의 총 모집단은 0 이 됩니까?**

아니요. 현재 Audience Manager는 인증된 프로필에 매핑된 장치를 세그먼트에 대한 적격한 것으로 계산합니다.

<br> 

## Trait Frequency, Device Graphs, and Profile Merge Rules {#trait-freq-device-rules}

**장치[!DNL Audience Manager]그래프를 사용하는 A[!UICONTROL Profile Merge Rule]의 특성 빈도는 어떻게 계산합니까?**

특성 빈도는 여러 장치에서 특정 트레이트의 자격 조건 합계에 의해 정의됩니다. 이를 이해하려면 다음 사용 사례를 살펴보십시오.

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
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">You have a <span class="wintitle"> Profile Merge Rule</span> that uses a device graph option. </li> 
      <li id="li_B46C4DE6CBD44D44B0F02EC9987140A5">단일 트레이트 (트레이트 1) 로 구성된 단일 세그먼트 (세그먼트 1). 트레이트 1는 8의 빈도입니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>작업</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> 는 장치 A와 장치 B의 장치 프로파일을 읽고 병합합니다. 이를 통해 다음을 확인할 수 있습니다. </p> <p> 
     <ul id="ul_7AB307154C034695B4486E68D55CB084"> 
      <li id="li_5760BEE513C94152AA307AEE10894718">장치 A는 트레이트 1에 세 번 적용되었습니다. 트레이트 1의 주파수는 3 입니다. </li> 
      <li id="li_E20BC24CCCEC407C820A8032D56BC3F0">장치 B는 트레이트를 5 회 이상 적용했습니다. 트레이트 1는 빈도수가 5 입니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>결과</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> 는 트레이트 1의 빈도를 계산하고 8 (3 + 5 = 8) 를 사용하여 세그먼트 자격 조건을 결정합니다. 장치 A와 장치 B는 8의 빈도수가 있으므로 세그먼트 1의 자격이 됩니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

## Reports, Device Graphs, and Profile Merge Rules {#reports-device-graphs-rules}

**장치 그래프를 사용하는 A[!UICONTROL Profile Merge Rule]로 도달할 수 있는 장치 수를 볼 수 있습니까?**

예. Reports return data at the [!UICONTROL Profile Merge Rule] level. 보고서 데이터는 매일 업데이트됩니다. 데이터는 장치 그래프로 연결된 장치가 아니라 계정에 표시되는 장치를 기반으로 합니다. See [Report Metrics for Profile Merge Rules](../features/profile-merge-rules/profile-link-metrics.md).

<br> 

**장치 그래프를 사용하는 특정 세그먼트에 대한 장치&#x200B;*수를 실시간으로*[!UICONTROL Profile Merge Rules]볼 수 있습니까?**

예. 실시간 인구 통계 지표는 장치 그래프로 연결된 모든 장치의 프로필을 사용하여 현재 장치 (실시간으로 표시되는 장치) 에 대한 세그먼트 자격 조건을 캡처합니다.

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
   <td colname="col2"> <p>다음과 같은 경우 </p> <p> 
     <ul id="ul_B8B627FBF6A04C0CAE6C8543EA3EA56D"> 
      <li id="li_2557CE3F109C42DC8CB5E99B93E96265">세그먼트 1는 다음 특성 및 자격 조건에 따라 작성되었습니다. segment 1 = 특성 A and 특성 B and 특성 C. </li> 
      <li id="li_F7D559B3C0CA424DA2C1A0703C1E1717">3 디바이스 프로파일: 장치 1 (현재 장치), 장치 2 (장치 그래프), 장치 3 (장치 그래프). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>작업</b> </p> </td> 
   <td colname="col2"> <p>사용 가능한 각 트레이트: </p> <p> 
     <ul id="ul_E60A5CBBEC484BB78F2A4AB0D6306019"> 
      <li id="li_26D7300BA0164426949FA43A60AC7023">장치 1: 트레이트 A </li> 
      <li id="li_B0C3D7ACC7754ED985974317362AFF85">장치 2: 특성 B </li> 
      <li id="li_32C32DD0E87F461AA2C7FB77FB35C6DA">장치 3: 특성 C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>결과</b> </p> </td> 
   <td colname="col2"> <p>이전 요소를 고려할 때 세그먼트 1의 총 인구는 1 입니다. </p> <p>In this case, the <span class="wintitle"> Profile Merge Rule</span> uses all the devices and their traits to decide segment qualification. 이것은 장치 1, 2 및 3 이 세그먼트 1를 적용한다는 것을 의미하지만, 위에 언급된 것처럼, 장치 1만 실시간 세그먼트 모집단에는 포함됩니다. 이것은 다음과 같습니다. </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">Device 1 is the current device interacting with the Audience Manager <span class="wintitle"> Data Collection Servers</span> (<span class="wintitle"> DCS</span>) in real-time. </li> 
      <li id="li_57165E96289F4E20BF2244BC68B90BA3">장치 2와 3는 장치 1에 의해 장치 1와 연결되어 있지만, 장치 1와 동시에 DCS와 상호 작용하지 않습니다. </li> 
     </ul> </p> <p>따라서 장치 2와 3는 실시간 세그먼트 모집단 지표에 포함되지 않습니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**장치 그래프를 사용하는 특정[!UICONTROL Profile Merge Rule]세그먼트에 대해 정규화된 총 장치 수를 볼 수 있습니까?**

예. 총 세그먼트 모집단 지표에는 장치 그래프에서 연결을 기반으로 한 세그먼트에 대한 자격이 있는 추가 장치가 포함됩니다.

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
   <td colname="col2"> <p>다음과 같은 경우 </p> <p> 
     <ul id="ul_DC0AC0F79323451C8C2480E4A85AE2EB"> 
      <li id="li_790F24FA1F0747F385640EDB1AE9E59E">세그먼트 1는 다음 특성 및 자격 조건에 따라 작성되었습니다. segment 1 = 특성 A and 특성 B and 특성 C. </li> 
      <li id="li_6628727DDD0644BF8F5B6A8A9FA71E67">3 디바이스 프로파일: 장치 1 (현재 장치), 장치 2 (장치 그래프), 장치 3 (장치 그래프). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>협회</b> </p> </td> 
   <td colname="col2"> <p>사용 가능한 각 트레이트: </p> <p> 
     <ul id="ul_FE16B1639D2541009110E77A605D2CE0"> 
      <li id="li_25959C3822384CFAB8B18D3CD80A30DD">장치 1: 트레이트 A </li> 
      <li id="li_CDAC38F4CF3A4BEDA49A92BAEC48583E">장치 2: 특성 B </li> 
      <li id="li_6063A91C482E48FD9FC5C00600B05E31">장치 3: 특성 C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>결과</b> </p> </td> 
   <td colname="col2"> <p>이전 요소를 고려할 때 세그먼트 1의 총 인구는 세 개입니다. </p> <p>In this case, the <span class="wintitle"> Profile Merge Rule</span> uses all the devices and their traits to decide segment qualification. 즉, 장치 1, 2 및 3는 세그먼트 1의 자격이 되고 모든 3는 총 모집단에 포함됩니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**보고서,[!UICONTROL Profile Merge Rule][!UICONTROL Interactive][!UICONTROL Overlap]보고서 및[!UICONTROL Audience Optimization]보고서에 포함된 장치 그래프를 사용하는 세그먼트를 사용할 수 있는 장치가 있습니까?**

아니오

>[!MORE_ like_ this]
>
>* [프로필 링크](../features/profile-merge-rules/merge-rules-overview.md)

