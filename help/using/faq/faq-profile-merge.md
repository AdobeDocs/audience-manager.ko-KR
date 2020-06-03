---
description: 일반적인 프로필 병합 규칙 및 장치 그래프 질문에 대한 답변입니다.
keywords: Organization ID
seo-description: 일반적인 프로필 병합 규칙 및 장치 그래프 질문에 대한 답변입니다.
seo-title: 프로필 병합 규칙 및 장치 그래프 FAQ
solution: Audience Manager
title: 프로필 병합 규칙 및 장치 그래프 FAQ
uuid: ba7986f1-078f-4162-aef3-b5c8740cebf4
translation-type: tm+mt
source-git-commit: 6876ca5ee0bc5f50c2aa1acd5c683b151a07fd59
workflow-type: tm+mt
source-wordcount: '1548'
ht-degree: 2%

---


# 프로필 병합 규칙 및 장치 그래프 FAQ{#profile-merge-rules-and-device-graph-faq}

일반적인 프로필 병합 규칙 및 장치 그래프 질문에 대한 답변입니다.

<!-- profile-merge-faq.xml -->

## 장치 그래프 기본 사항 {#device-graph-basics}

**장치 그래프란?**

장치 그래프는 익명 장치 그룹을 정의하는 ID 매핑 집합입니다. 이 장치는 각 장치에서 수집된 신호의 일반적인 요소를 기준으로 사람이나 가정에 이러한 장치를 연결합니다. 이러한 신호들은 개인 또는 가정 수준에서 장치를 식별하는 것을 도와줍니다.

 

**외부 장치 그래프란?**

외부 장치 그래프는 자체 크로스 디바이스 데이터 소스에서만 특별히 제작되지 [!DNL Audience Manager] 않은 모든 장치 그래프입니다. 예를 들어, [프로필 병합 규칙](../features/profile-merge-rules/merge-rules-start.md) 을 만들고 [!UICONTROL Co-op Device Graph] 또는 타사 장치 그래프 옵션을 선택하면 외부 장치 그래프로 작업하게 됩니다. 장치 [옵션을 참조하십시오](../features/profile-merge-rules/merge-rule-definitions.md#device-options).

 

**외부 장치 그래프를 사용하는 일반적인 사용 사례는 무엇입니까[!UICONTROL Profile Merge Rule]?**

장치 그래프를 사용하는 주요 목적은 한 사람 또는 가정에 속하는 여러 장치를 특정 세그먼트에 대해 평가하고 평가하는 것입니다. [!UICONTROL Profile Merge Rule] 세그먼트 자체에는 DSP에서 제공하는 광고를 통해 잠재 고객을 타깃팅하거나 온사이트 개인화 플랫폼을 통해 고객의 온사이트 경험을 개인화하는 등 다양한 용도가 있을 수 있습니다. See [External Device Graph Use Cases](../features/profile-merge-rules/external-graph-use-cases.md).

 

**Audience Manager는 외부 디바이스 그래프에 대한 글로벌 지원을 제공합니까?**

아니요. 외부 장치 그래프는 미국과 캐나다에서만 사용할 수 있습니다.

 

**외부 장치 그래프 데이터를 얼마나 자주[!DNL Audience Manager]업데이트합니까?**

일주일에 한 번

 

## 장치 그래프 및 프로필 병합 규칙 {#device-graph-profile-merge-rules}

**장치 그래프는 어떻게[!DNL Audience Manager]사용합니까?**

에서 [!DNL Audience Manager]장치 그래프는 프로파일 병합 규칙 [을 만들 때 구성 옵션으로 나타납니다](../features/profile-merge-rules/merge-rules-start.md). 다음 디바이스 그래프 [!UICONTROL Profile Merge Rules]를 통해 다음을 수행할 수 있습니다 [!DNL Audience Manager].

* 여러 디바이스 프로파일을 함께 병합 이렇게 하면 하나의 상위 트레이트가 만들어집니다.
* 각 장치 프로파일을 개별적으로 평가하는 대신 세그먼트 자격에 대한 트레이트 상위 세트를 평가합니다.
* 사용 가능한 세그먼트에 자격 조건을 갖춘 장치를 추가합니다.

 

**몇 개를 만들[!UICONTROL Profile Merge Rules]수 있습니까?**

현재 최대 4개를 만들 수 있습니다 [!UICONTROL Profile Merge Rules]. 네 번째 프로필 병합 규칙([!UICONTROL All Cross-Device Profiles])은 Add-On을 구매하는 고객에게만 [!UICONTROL People-Based Destinations] 제공됩니다.

 

**장치 그래프를 사용할 때 병합하고 읽는 장치 프로파일은 몇 개입니까[!DNL Audience Manager][!UICONTROL Profile Merge Rule]?**

Audience Manager는 한 세그먼트를 사용하여 장치를 인증하면 현재 장치 프로파일 [!UICONTROL Profile Merge Rule]과 선택한 장치 그래프 옵션으로 연결된 최대 99개의 추가 장치 프로파일을 병합하여 읽습니다.

 

**장치 그래프를 사용할 때 어떤 장치가 세그먼트에 적합합니까[!UICONTROL Profile Merge Rule]?**

장치 병합 [!DNL Audience Manager] 및 읽기는 세그먼트에 자격이 있는 동일한 장치입니다.

 

**장치 그래프를 사용하는 세그먼트가 자격을[!DNL Audience Manager][!UICONTROL Profile Merge Rule]얻은 경우 어디로 보낼 수 있습니까?**

[!DNL Audience Manager] 세그먼트를 배치 파일 또는 실시간으로 대상에 보낼 수 있습니다.

 

## 세그먼트, 장치 그래프 및 프로필 병합 규칙 {#segments-device-graphs-rules}

**장치 그래프를 사용하는 세그먼트가 더 이상 적격하지 않을 때 장치의[!DNL Audience Manager]세그먼트는 어떻게[!UICONTROL Profile Merge Rule]분리합니까?**

Audience Manager는 세그먼트를 장치 그래프를 사용하는 장치로 평가할 때 최대 100개의 장치 [!UICONTROL Profile Merge Rule] 를 병합합니다. 세그먼트 해제 신호가 발급되면 현재 장치 및 최대 99개의 추가 장치가 대상의 세그먼트에서 제거됩니다. 세그멘테이션에 대한 자세한 내용은 프로필 [병합 규칙 및 장치 분리 세그멘테이션 프로세스를 참조하십시오](../features/profile-merge-rules/merge-rule-unsegment.md).

 

**대상이 장치를 세그먼트화할 수 있는 경우 장치 그래프를 사용하는 장치[!UICONTROL Profile Merge Rules]가 세그먼트에서 제거됩니까?**

예. 위의 설명을 참조하십시오.

 

**장치 그래프를 사용하는 세그먼트[!UICONTROL Profile Merge Rule]를 작성하고 세그먼트가 실시간 데이터와 온보드 데이터를 모두 사용하는 경우 내 세그먼트가 온보드 데이터 변경 사항으로 업데이트됩니까?**

예. 

 

**세그먼트 크기 추정치에는 장치 그래프 옵션을 사용하는 연결 기반으로 세그먼트를 분류할 수 있는 장치[!UICONTROL Profile Merge Rule]가 포함됩니까?**

아니요. 세그먼트 빌더 [!UICONTROL Estimated Real-Time Population] 에서 및 [!UICONTROL Estimated Total Population] 의 특성 및 세그먼트 [모집단 데이터에 대한 정의를 참조하십시오](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/segments/segment-builder-data.html).

 

**장치 그래프 옵션을 사용하는 연결 기반[!UICONTROL Addressable Audiences][!UICONTROL Profile Merge Rule]으로 세그먼트를 분류할 수 있는 장치가 포함되어 있습니까?**

예. 

 

**세그먼트가[!UICONTROL Profile Merge Rule]with[!UICONTROL No Cross-Device Profile]를 사용하고 세그먼트에 맞는 장치의 자격이 되는 트레이트가 장치 간 프로필에만 저장되는 경우 세그먼트의 총 인구는 0이 됩니까?**

예. 프로필 병합 규칙이 로 설정된 경우 Audience Manager는 세그먼트 평가에서 장치 간 프로필에 저장된 트레이트를 계산하지 않습니다 [!UICONTROL No Cross-Device Profile].

 

## 특성 빈도, 장치 그래프 및 프로필 병합 규칙 {#trait-freq-device-rules}

**장치 그래프를 사용하는[!DNL Audience Manager]특성 빈도는 어떻게[!UICONTROL Profile Merge Rule]계산합니까?**

특성 빈도는 여러 장치에서 특정 트레이트에 대한 자격 수의 합으로 정의됩니다. 이를 이해하는 데 도움이 되도록 다음 사용 사례를 살펴보십시오.

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
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">장치 그래프 옵션을 사용하는 <span class="wintitle"> 프로필</span> 병합 규칙이 있습니다. </li> 
      <li id="li_B46C4DE6CBD44D44B0F02EC9987140A5">트레이트 1의 주파수가 8인 단일 트레이트(트레이트 1)로 구성된 단일 세그먼트(세그먼트 1)입니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>작업</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager는</span> 장치 A 및 장치 B의 장치 프로파일을 읽고 병합합니다. 여기에서 다음을 볼 수 있습니다. </p> <p> 
     <ul id="ul_7AB307154C034695B4486E68D55CB084"> 
      <li id="li_5760BEE513C94152AA307AEE10894718">장치 A는 트레이트를 3번 인증했습니다. 특성 1의 주파수는 3입니다. </li> 
      <li id="li_E20BC24CCCEC407C820A8032D56BC3F0">장치 B는 트레이트를 15번 인증했습니다. 트레이트 1에 5번 주파수가 있습니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>결과</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> 는 트레이트 1의 빈도를 합계하고 8(3 + 5 = 8)을 사용하여 세그먼트 자격을 결정합니다. 장치 A와 장치 B는 8의 주파수가 있으므로 세그먼트 1을 사용할 수 있습니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

## 보고서, 장치 그래프 및 프로필 병합 규칙 {#reports-device-graphs-rules}

**장치 그래프를 사용하는 장치 수에 도달할 수[!UICONTROL Profile Merge Rule]있는 장치 수를 볼 수 있습니까?**

예. 보고서는 [!UICONTROL Profile Merge Rule] 수준에서 데이터를 반환합니다. 보고서 데이터는 매일 업데이트됩니다. 데이터는 장치 그래프로 연결된 장치가 아니라 계정에 표시되는 장치를 기반으로 합니다. 프로필 [병합 규칙에 대한 보고서 지표를 참조하십시오](../features/profile-merge-rules/profile-link-metrics.md).

 

**장치 그래프를 사용하는 특정 세그먼트에 대해 적격한 장치 수를&#x200B;*실시간으로*볼[!UICONTROL Profile Merge Rules]수 있습니까?**

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
   <td colname="col2"> <p>다음과 같은 결과가 있다고 가정합니다. </p> <p> 
     <ul id="ul_B8B627FBF6A04C0CAE6C8543EA3EA56D"> 
      <li id="li_2557CE3F109C42DC8CB5E99B93E96265">이러한 트레이트 및 자격 로직을 기반으로 구축된 세그먼트 1: 세그먼트 1 = 트레이트 A 및 트레이트 B와 트레이트 C. </li> 
      <li id="li_F7D559B3C0CA424DA2C1A0703C1E1717">디바이스 프로파일 3개: 장치 1(현재 장치), 장치 2(장치 그래프), 장치 3(장치 그래프). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>작업</b> </p> </td> 
   <td colname="col2"> <p>사용 가능한 각 트레이트는 장치에 연결됩니다. </p> <p> 
     <ul id="ul_E60A5CBBEC484BB78F2A4AB0D6306019"> 
      <li id="li_26D7300BA0164426949FA43A60AC7023">장치 1: 특성 A </li> 
      <li id="li_B0C3D7ACC7754ED985974317362AFF85">장치 2: 특성 B </li> 
      <li id="li_32C32DD0E87F461AA2C7FB77FB35C6DA">장치 3: 특성 C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>결과</b> </p> </td> 
   <td colname="col2"> <p>이전 요소가 주어지면 세그먼트 1의 총 모집단 수가 1입니다. </p> <p>이 경우 프로필 병합 규칙은 <span class="wintitle"> 모든 장치</span> 및 해당 특성을 사용하여 세그먼트 자격 조건을 결정합니다. 이는 장치 1, 2 및 3이 세그먼트 1의 자격이 있음을 의미하지만, 위에서 언급한 바와 같이, 장치 1만 실시간 세그먼트 모집단으로 포함됩니다. 이는 다음 때문입니다. </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">장치 1은 DCS <span class="wintitle"> (Audience Manager Data Collection Server)와 실시간으로 상호 작용하는</span> 현재<span class="wintitle"></span>장치입니다. </li> 
      <li id="li_57165E96289F4E20BF2244BC68B90BA3">장치 2와 3은 장치 그래프로 장치 1과 연결되지만 장치 1과 동시에 DCS와 상호 작용하지 않습니다. </li> 
     </ul> </p> <p>따라서 장치 2와 3은 실시간 세그먼트 모집단 지표에 포함되지 않습니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**장치 그래프를 사용하는 특정 세그먼트에 대해 자격이 부여된 총 장치 수를 볼 수[!UICONTROL Profile Merge Rule]있습니까?**

예. 총 세그먼트 모집단 지표에는 장치 그래프의 연결을 기반으로 세그먼트에 자격을 부여받은 추가 장치가 포함됩니다.

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
   <td colname="col2"> <p>다음과 같은 결과가 있다고 가정합니다. </p> <p> 
     <ul id="ul_DC0AC0F79323451C8C2480E4A85AE2EB"> 
      <li id="li_790F24FA1F0747F385640EDB1AE9E59E">이러한 트레이트 및 자격 로직을 기반으로 구축된 세그먼트 1: 세그먼트 1 = 트레이트 A 및 트레이트 B와 트레이트 C. </li> 
      <li id="li_6628727DDD0644BF8F5B6A8A9FA71E67">디바이스 프로파일 3개: 장치 1(현재 장치), 장치 2(장치 그래프), 장치 3(장치 그래프). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>연결</b> </p> </td> 
   <td colname="col2"> <p>사용 가능한 각 트레이트는 장치에 연결됩니다. </p> <p> 
     <ul id="ul_FE16B1639D2541009110E77A605D2CE0"> 
      <li id="li_25959C3822384CFAB8B18D3CD80A30DD">장치 1: 특성 A </li> 
      <li id="li_CDAC38F4CF3A4BEDA49A92BAEC48583E">장치 2: 특성 B </li> 
      <li id="li_6063A91C482E48FD9FC5C00600B05E31">장치 3: 특성 C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>결과</b> </p> </td> 
   <td colname="col2"> <p>이전 요소가 주어진 경우 세그먼트 1의 총 모집단수는 3입니다. </p> <p>이 경우 프로필 병합 규칙은 <span class="wintitle"> 모든 장치</span> 및 해당 특성을 사용하여 세그먼트 자격 조건을 결정합니다. 즉, 장치 1, 2 및 3은 세그먼트 1의 자격이 되고 세 개 모두 총 모자에 포함됩니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**보고서, 보고서 및[!UICONTROL Profile Merge Rule]보고서에 포함된 장치 그래프를 사용하는 세그먼트[!UICONTROL Interactive][!UICONTROL Overlap][!UICONTROL Audience Optimization]를 사용할 수 있는 장치입니까?**

아니요. 

**2020년 3월 16일 이후 Adobe Campaign으로 세그먼트 내보내기에 0개의 세그먼트 모집단만 표시되는 이유는 무엇입니까?**

2019년 말에는 크로스 장치 ID를 사용하여 생성된 일괄 처리 파일의 정확도를 향상시키기 위해 일련의 향상된 프로필 병합 규칙을 발표했습니다. 이러한 개선 사항은 2020년 3월 16일 월요일부터 Audience Manager 인스턴스에서 엄격하게 적용됩니다. 마지막으로, 장치 간 ID를 사용하여 대상에 매핑된 세그먼트는 일부 프로필 병합 규칙 구성에서 내보내기 생성을 중지합니다.

Adobe Campaign과 같은 장치 간 ID를 사용하는 Audience Manager 인스턴스와 대상 간의 올바른 통합을 보장하려면 다음 요구 사항을 충족해야 합니다.

1. Adobe Campaign 선언 ID 대상에 매핑된 세그먼트가 사용한 프로필 병합 규칙을 검토하십시오. 프로필 병합 규칙은 이 옵션을 사용해야 [!UICONTROL Last Authenticated Profile] 하므로 인증된 모든 프로필을 내보내기에 포함할 수 있습니다. 프로필 병합 규칙이 다른 옵션을 사용하고 있는 경우 다른 옵션으로 전환합니다 [!UICONTROL Last Authenticated Profile].
2. 프로필 병합 규칙 설정에서 Adobe Campaign 선언된 ID 데이터 소스를 선택합니다.

>[!NOTE]
>
> 이러한 상황에 처한 고객에 대해 프로필 병합 규칙 제한을 1로 늘렸기 때문에 다른 사용 사례에 대한 프로필 병합 규칙을 변경하지 않고 Adobe Campaign 선언 ID 대상에 매핑된 세그먼트에 대한 전용 프로필 병합 규칙을 만들 수 있습니다.

>[!MORELIKETHIS]
>
>* [프로필 링크](../features/profile-merge-rules/profile-link-use-case.md)

