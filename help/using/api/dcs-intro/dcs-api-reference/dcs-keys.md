---
description: DCS(데이터 수집 서버)에 전달할 수 있는 구문 및 지원되는 속성(또는 키-값 쌍)을 나열하고 설명합니다. 이 정보는 DCS 요청의 형식을 지정하고 이 시스템에서 반환되는 매개 변수를 이해하는 데 도움이 될 수 있습니다.
seo-description: DCS(데이터 수집 서버)에 전달할 수 있는 구문 및 지원되는 속성(또는 키-값 쌍)을 나열하고 설명합니다. 이 정보는 DCS 요청의 형식을 지정하고 이 시스템에서 반환되는 매개 변수를 이해하는 데 도움이 될 수 있습니다.
seo-title: DCS API 호출에 지원되는 특성
solution: Audience Manager
title: DCS API 호출에 지원되는 특성
keywords: d_caller, d_cb, d_cid, d_cid_ic, d_coppa, d_cts=1, d_cts=2, d_tdpid, d_ddst=1, d_mid, d_ptfm, d_nsid, d_rtbd=json, d_tdpid_ic
uuid: 0b98ed11-314b-4500-afde-45a041112150
feature: DCS
exl-id: 1bdd7dcd-9411-4b0a-a236-059eb5faf00d
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '843'
ht-degree: 5%

---

# [!DNL DCS] [!DNL API] 호출에 지원되는 특성 {#supported-attributes-for-dcs-api-calls}

[!UICONTROL Data Collection Servers]([!DNL DCS])에 전달할 수 있는 구문 및 지원되는 속성(또는 키-값 쌍)을 나열하고 설명합니다. 이 정보는 [!DNL DCS] 요청의 형식을 지정하고 이 시스템에서 반환된 매개 변수를 이해하는 데 도움이 될 수 있습니다.

## 속성 접두사 {#attribute-prefixes}

[!DNL DCS]은(는) 키-값 쌍의 키에 추가된 특정 접두사를 사용하여 전달하는 데이터의 유형을 분류합니다.

<table id="table_23B7E15EC13749E9A245DFB543822DB7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 키 접두사 </th> 
   <th colname="col2" class="entry"> 예약됨 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> c_</code> </p> </td> 
   <td colname="col2"> <p>고객 정의 속성입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience </span> Manager 속성. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> h_</code> </p> </td> 
   <td colname="col2"> <p>HTTP 헤더 데이터입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> p_</code> </p> </td> 
   <td colname="col2"> <p>비공개 고객 정의 속성입니다. </p> <p> DCS는 키에 <code> p_</code> 접두사가 있을 때 자체 개인 데이터를 허용합니다. 개인 데이터는 트레이트 평가에 사용되지만 시스템에 기록되거나 저장되지는 않습니다. 예를 들어 <code> customers = p_age&lt;25</code> 로 정의된 트레이트가 있고 이벤트 호출에서 <code> p_age=23</code> 를 전달한다고 가정해 보겠습니다. 이 경우 연령 기반 자격 기준을 충족하는 사용자가 트레이트에 대해 자격을 얻지만 키-값 쌍은 <span class="keyword"> Audience Manager</span> 이 요청을 받고 로그인되지 않은 후 삭제됩니다. </p> </td>
  </tr> 
 </tbody> 
</table>

## [!DNL d_] 속성 {#d-attributes}

[!DNL DCS]에서 응답을 원하는 경우가 아니면 모두 선택 사항입니다. [!DNL DCS]에서 응답을 반환하려면 `d_rtbd=json`이 필요합니다.

<table id="table_FCCE4F9D796648899772A191981EFDE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 특성 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> d_caller</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DCS</span> API를 호출하는 호출자를 식별하는 데 사용됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cb</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DCS</span> 응답을 콜백 함수의 함수 매개 변수로 사용하여 실행할 JavaScript 함수를 지정합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cid</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span>에 의해 지정된 하나 이상의 데이터 공급자 ID(<code> DPID</code>) 및 데이터 공급자 사용자 ID(<code> DPUUID</code>)가 포함되어 있습니다. <code> DPID</code>s 및 <code> DPUUID</code>s의 여러 쌍을 사용하는 경우 인쇄되지 않는 문자 <code> %01</code>로 각 쌍을 구분합니다. 예: <code><i>DPID</i>%01<i>DPUUUID</i></code>. </p> <p><code> d_cid</code> 는 더 이상 사용되지 않지만 여전히 지원되는 <code> d_dpid</code> 및 <code> d_dpuuid</code> 를 대체합니다. <a href="../../../reference/cid.md">CID가 DPID 및 DPUUID 대체</a>를 참조하십시오. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cid_ic</code> </p> </td> 
   <td colname="col2"> <p>단일 키-값 쌍에 통합 코드 및 연결된 고유 사용자 ID를 포함합니다. </p> <p><code> d_cid_ic</code> 는 더 이상 사용되지 않지만 여전히 지원되는 <code> d_dpid</code> 및 <code> d_dpuuid</code> 를 대체합니다. <a href="../../../reference/cid.md">CID가 DPID 및 DPUUID 대체</a>를 참조하십시오. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_coppa</code> </p> </td> 
   <td colname="col2"> <p>하위 보호 규정을 준수하기 위해 타사 쿠키 사용을 비활성화합니다. 이 매개 변수는 Adobe Experience Platform Identity 서비스 Adobe에 의해 동적으로 설정되며 <code> idSyncDisable3rdPartySyncing</code> 구성에 따라 다릅니다. Adobe Experience Platform Identity 서비스에서 <a href="https://docs.adobe.com/content/help/en/id-service/using/reference/coppa.html" format="https" scope="external"> COPPA 지원</a>을 참조하십시오. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cts=1</code> </p> <p><code> d_cts=2</code> </p> </td> 
   <td colname="col2"> <p>선택 사항입니다. 고객 요청에 대해 활성화되었습니다. Adobe Audience Manager 컨설턴트나 고객 지원에 문의하십시오. </p> <p>트레이트 및 세그먼트가 <code> JSON</code> 응답 내에 반환되어야 함을 나타냅니다. </p> <p> 
     <ul id="ul_8B936ACB18724681B959783421ACF026"> 
      <li id="li_792A6248F49141C0B4B214C754D5F5C5"> <p><code> d_cts=1</code> 세그먼트에 대한 <a href="../../../reference/ids-in-aam.md"> 기존 세그먼트 ID</a>를 반환합니다. </p> </li>
      <li id="li_F304CA651F3C444A9A24576726925D87"> <p><code> d_cts=2</code> 세그먼트의 세그먼트 ID를 반환합니다. </p> </li>
     </ul> </p> <p>샘플 응답은 아래 응답과 비슷합니다. </p> <p>
     <code class="syntax javascript">
      {
      &nbsp;&nbsp;&nbsp;&nbsp;"stuff":&nbsp;[],
      &nbsp;&nbsp;&nbsp;&nbsp;"uuid":&nbsp;"07955261652886032950143702505894272138",
      &nbsp;&nbsp;&nbsp;&nbsp;"dcs_region":&nbsp;7,
      &nbsp;&nbsp;&nbsp;&nbsp;"traits":&nbsp;[420020,&nbsp;5421506],
      &nbsp;&nbsp;&nbsp;&nbsp;"segments":&nbsp;[984263,&nbsp;985264],
      &nbsp;&nbsp;&nbsp;&nbsp;"tid":&nbsp;"ss3OTqPiQp0="
      }
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dpid</code> </p> </td> 
   <td colname="col2"> <p>삭제 예정. <code> d_cid</code> 및 <code> d_cid_ic</code> 를 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dpuuid</code> </p> </td> 
   <td colname="col2"> <p>삭제 예정. <code> d_cid</code> 및 <code> d_cid_ic</code> 를 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst=1</code> </p> </td> 
   <td colname="col2"> <p><code> JSON</code> 응답에서 URL 대상 데이터를 반환합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst_filter</code> </p> </td> 
   <td colname="col2"> <p><code> d_dst_filter</code> 는 Adobe Analytics과 Audience Manager 간의 통합에 사용되는 예약된 속성입니다. </p> <p>예약된 속성을 사용하는 트레이트를 만들지 않는 것이 좋습니다. Adobe은 언제든지 예약된 속성을 변경할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_jsonv=1|0</code> </p> </td> 
   <td colname="col2"> <p>응답에 사용할 <code> JSON</code> 버전을 나타냅니다. 일반적으로 <code> d_jsonv=1</code>(으)로 설정해야 합니다. <code> d_jsonv=0</code>을 설정하면 ID 동기화가 비활성화됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_mid</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Experience Cloud</span> ID 서비스에 의해 설정되고 사용되는 Experience Cloud ID를 지정합니다. ECID에 대한 자세한 내용은 <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html" format="https" scope="external"> 쿠키 및 Experience Cloud Identity 서비스</a>를 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_nsid</code> </p> </td> 
   <td colname="col2"> <p>이름 공간 ID입니다. 사용되는 JavaScript 컨테이너를 나타냅니다. <span class="wintitle"> DIL</span>에서 ID 동기화를 위해 사용됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ptfm </code> </p> </td> 
   <td colname="col2"> <p>Audience Manager이 모바일 요청을 데스크톱 요청과 구분할 수 있도록 해줍니다. 지원되는 값은 다음과 같습니다. </p> <p> 
     <ul id="ul_A01D4B15C89F4713A39E08377924D632"> 
      <li id="li_E17CC839265B4EB9AC44A3DA31A23857"> <code> ios</code> </li> 
      <li id="li_468F5903CD3048B5AE02A3FDA9B3C4F1"> <code> android</code> </li> 
      <li id="li_57090DAC3BDA41DFB4BA0DD328754D55"> <code> browser</code> </li> 
      <li id="li_DA4E93A831FE4FD8971CECD508AF992F"> <code> all</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rs</code> </p> </td> 
   <td colname="col2"> <p>삭제 예정. <code> d_rs</code> 는  <span class="keyword"> Adobe Analytics와 </span> Audience Manager <span class="keyword">  간의 기존 통합에 사용되는 예약된 </span>속성입니다. </p> <p>예약된 속성을 사용하는 트레이트를 만들지 않는 것이 좋습니다. Adobe은 언제든지 예약된 속성을 변경할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rtbd=json</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DCS</span>에서 <code> JSON</code> 응답을 원하는 경우 필수입니다. </p> <p> 
     <ul id="ul_9EA00BD822504BCA8ECB59C1634DB91A"> 
      <li id="li_7CB890F92C4A4C6AA8B4EE32E1AD4564">이를 생략하면 <span class="wintitle"> DCS</span>이 헤더에서 픽셀을 반환합니다. </li> 
      <li id="li_824C23B4C7AA4B5EBADF73D26016A18E">이를 포함하는 경우 <span class="wintitle"> DCS</span>은 응답 본문에 <code> JSON</code> 개체를 반환합니다. 아래 예를 참조하십시오. 응답이 더 복잡할 수 있습니다. </li> 
     </ul> </p> <p> 
     <code class="syntax javascript">
      {
      &nbsp;&nbsp;&nbsp;&nbsp;"stuff":&nbsp;[],
      &nbsp;&nbsp;&nbsp;&nbsp;"uuid":&nbsp;"22920112968019678612904394744954398990",
      &nbsp;&nbsp;&nbsp;&nbsp;"dcs_region":&nbsp;7,
      &nbsp;&nbsp;&nbsp;&nbsp;"tid":&nbsp;"ss3OTqPiQp0="
      }
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_sid</code> </p> </td> 
   <td colname="col2"> <p><code> SID</code> 는 <span class="term"> 점수 ID</span>를 의미합니다. 트레이트 또는 세그먼트에 대한 고유 ID입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid</code> </p> </td> 
   <td colname="col2"> <p>트레이트 평가를 위한 데이터 소스를 전달합니다. 이 데이터 소스의 트레이트만 평가됩니다. </p> <p>예를 들어 다음과 같은 경우가 있습니다. </p> <p> 
     <ul id="ul_6230777E16C14DCB83025A101A4ECA14"> 
      <li id="li_71F3970417BC4B93881A3E12DADE4120"><b></b> 의 트레이트 T1: </li> 
      <li id="li_66125E035F524A958C6F4BFAABA2A0D2">트레이트 규칙:"<code> key1 == val1</code>" </li> 
      <li id="li_4EE486E02CF54AEA876ABC005094E9E4">데이터 소스(<a href="../../../reference/ids-in-aam.md"> DPID</a>):3 </li> 
      <li id="li_3E6BBDEAE5C644C6A96CB49766CDA988">DPID 통합 코드:ic1 </li> 
     </ul> 
     <ul id="ul_0C30A8AE349D43A08490DA76CB4B06FA"> 
      <li id="li_F1E8DB26168B471FA35D82F4DD3AC601"><b></b> 의 트레이트 T2: </li> 
      <li id="li_1C943F84A4A149A0A86ABC92761D3E9E">트레이트 규칙:"<code> key2 == val2</code>" </li> 
      <li id="li_F2AA086C87B7484F8BFE1D5C09E8EBDF">데이터 소스(DPID):2개 </li> 
      <li id="li_877CAAAE996A4707BEE74F7042708481">DPID 통합 코드:ic2 </li> 
     </ul> </p> <p>샘플 호출에서 <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid=1</code> 트레이트 T1만 반환됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid_ic</code> </p> </td> 
   <td colname="col2"> <p>목적은 위에 설명된 <code> d_tdpid</code> 매개 변수와 동일합니다. 그러나 이 경우 통합 코드를 사용하여 데이터 소스가 전달됩니다. </p> <p>위에 설명된 트레이트를 유지하려면 샘플 호출을 고려하십시오. </p> <p><code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid_ic=ic2</code>의 경우 트레이트 T2만 반환됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_uuid</code> </p> </td> 
   <td colname="col2"> <p>고유 사용자 ID. 쿠키에서 이 값을 사용할 수 없을 때 방문자를 식별합니다. </p> </td> 
  </tr>
 </tbody>
</table>
