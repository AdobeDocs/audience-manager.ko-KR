---
description: DCS(데이터 수집 서버)에 전달할 수 있는 구문 및 지원되는 속성(또는 키-값 쌍)을 나열하고 설명합니다. 이 정보는 DCS 요청의 형식을 지정하고 이 시스템에서 반환된 매개 변수를 이해하는 데 도움이 됩니다.
seo-description: DCS(데이터 수집 서버)에 전달할 수 있는 구문 및 지원되는 속성(또는 키-값 쌍)을 나열하고 설명합니다. 이 정보는 DCS 요청의 형식을 지정하고 이 시스템에서 반환된 매개 변수를 이해하는 데 도움이 됩니다.
seo-title: DCS API 호출에 지원되는 특성
solution: Audience Manager
title: DCS API 호출에 지원되는 특성
keywords: d_caller, d_cb, d_cid, d_cid_ic, d_coppa, d_cts=1, d_cts=2, d_tdpid, d_dst=1, d_dst_filter, d_mid, d_ptfm, d_nsid, d_rs, d_rtbd=json, d_tdpid_ic
uuid: 0b98ed11-314b-4500-afde-45a041112150
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 5%

---


# 호출을 위한 [!DNL DCS] 지원되는 [!DNL API] 속성 {#supported-attributes-for-dcs-api-calls}

구문과 지원되는 속성(또는 키-값 쌍)을 [!UICONTROL Data Collection Servers] ([!DNL DCS])에 전달하고 설명합니다. 이 정보는 [!DNL DCS] 요청의 형식을 지정하고 이 시스템에서 반환된 매개 변수를 이해하는 데 도움이 됩니다.

## 속성 접두사 {#attribute-prefixes}

이 [!DNL DCS] 는 키-값 쌍의 키에 추가된 특정 접두사를 사용하여 전달하려는 데이터 유형을 분류합니다.

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
   <td colname="col2"> <p>고객 정의 속성 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> 특성입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> h_</code> </p> </td> 
   <td colname="col2"> <p>HTTP 헤더 데이터. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> p_</code> </p> </td> 
   <td colname="col2"> <p>비공개, 고객 정의 속성. </p> <p> 키에 접두사가 있을 때 DCS는 사용자의 개인 데이터를 <code> p_</code> 허용합니다. 개인 데이터는 특성 평가에 사용되지만 시스템에 기록되거나 저장되지 않습니다. 예를 들어, 트레이트가 로 정의되고 이벤트 호출 <code> customers = p_age&lt;25</code> 에 <code> p_age=23</code> 통과한다고 가정해 봅시다. 이러한 조건이 주어지면 연령 기반 자격 기준을 충족하는 사용자가 트레이트를 받을 수 있지만 키-값 쌍은 <span class="keyword"> Audience Manager</span> 가 요청을 받고 기록되지 않은 후에 삭제됩니다. </p> </td>
  </tr> 
 </tbody> 
</table>

## [!DNL d_] 속성 {#d-attributes}

이 모든 것은 선택 사항이며, 단, [!DNL DCS] 응답을 [!DNL DCS] 반환하려면 필수 `d_rtbd=json` 가 됩니다.

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
   <td colname="col2"> <p>DCS <span class="wintitle"> API를 호출하고 있는 호출자를 식별하는 데</span> 사용됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cb</code> </p> </td> 
   <td colname="col2"> <p>콜백 함수의 함수 매개 변수로 <span class="wintitle"> DCS</span> 응답을 사용하여 실행할 JavaScript 함수를 지정합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cid</code> </p> </td> 
   <td colname="col2"> <p>Audience Manager에서 할당한 하나 이상의 데이터 공급자 ID(<code> DPID</code>)와 데이터 공급자 사용자 ID(<code> DPUUID</code>)를 <span class="keyword"> 포함합니다</span>. 여러 쌍의 <code> DPID</code>s와 <code> DPUUID</code>s를 사용하는 경우 각 쌍을 인쇄되지 않은 문자와 구분하십시오 <code> %01</code>. 예: <code><i>DPID</i>%01<i>DPUUUID</i></code>. </p> <p><code> d_cid</code> 교체 <code> d_dpid</code> 및 <code> d_dpuuid</code>대체 - 더 이상 사용되지 않지만 여전히 지원됩니다. <a href="../../../reference/cid.md">CID가 DPID 및 DPUUID 대체</a>를 참조하십시오. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cid_ic</code> </p> </td> 
   <td colname="col2"> <p>단일 키-값 쌍에 통합 코드와 관련 고유 사용자 ID가 들어 있습니다. </p> <p><code> d_cid_ic</code> 교체 <code> d_dpid</code> 및 <code> d_dpuuid</code>대체 - 더 이상 사용되지 않지만 여전히 지원됩니다. <a href="../../../reference/cid.md">CID가 DPID 및 DPUUID 대체</a>를 참조하십시오. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_coppa</code> </p> </td> 
   <td colname="col2"> <p>자녀 보호 규정을 준수하기 위해 타사 쿠키 사용을 비활성화합니다. 이 매개 변수는 Adobe Adobe Experience Platform ID 서비스에 의해 동적으로 설정되며 구성에 따라 <code> idSyncDisable3rdPartySyncing</code> 달라집니다. Adobe Experience Platform ID 서비스에서 <a href="https://docs.adobe.com/content/help/en/id-service/using/reference/coppa.html" format="https" scope="external"> COPPA 지원을 참조하십시오</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cts=1</code> </p> <p><code> d_cts=2</code> </p> </td> 
   <td colname="col2"> <p>선택 사항입니다. 고객 요청 시 활성화됩니다. Adobe Audience Manager 컨설턴트 또는 고객 지원 센터에 문의하십시오. </p> <p>응답 내에서 트레이트와 세그먼트를 반환해야 함을 <code> JSON</code> 나타냅니다. </p> <p> 
     <ul id="ul_8B936ACB18724681B959783421ACF026"> 
      <li id="li_792A6248F49141C0B4B214C754D5F5C5"> <p><code> d_cts=1</code> 세그먼트에 대한 <a href="../../../reference/ids-in-aam.md"> 기존 세그먼트 ID를</a> 반환합니다. </p> </li>
      <li id="li_F304CA651F3C444A9A24576726925D87"> <p><code> d_cts=2</code> 세그먼트에 대한 세그먼트 ID를 반환합니다. </p> </li>
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
   <td colname="col2"> <p>삭제 예정. 및 <code> d_cid</code> 을 참조하십시오 <code> d_cid_ic</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dpuuid</code> </p> </td> 
   <td colname="col2"> <p>삭제 예정. 및 <code> d_cid</code> 을 참조하십시오 <code> d_cid_ic</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst=1</code> </p> </td> 
   <td colname="col2"> <p>응답의 URL 대상 데이터를 <code> JSON</code> 반환합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst_filter</code> </p> </td> 
   <td colname="col2"> <p><code> d_dst_filter</code> 는 예약된 속성으로서, Adobe Analytics과 Audience Manager 간의 통합에 사용됩니다. </p> <p>예약된 특성을 사용하는 특성을 만들지 않는 것이 좋습니다. Adobe는 언제든지 예약 속성을 변경할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_jsonv=1|0</code> </p> </td> 
   <td colname="col2"> <p>응답에 사용할 <code> JSON</code> 버전을 나타냅니다. 일반적으로 이 설정을 로 설정해야 합니다 <code> d_jsonv=1</code>. ID 동기화 <code> d_jsonv=0</code> 를 사용하지 않도록 설정합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_mid</code> </p> </td> 
   <td colname="col2"> <p>Experience Cloud <span class="keyword"></span> ID 서비스가 설정하고 사용하는 Experience Cloud ID를 지정합니다. ECID에 대한 자세한 내용은 쿠키 <a href="https://docs.adobe.com/content/help/ko-KR/id-service/using/intro/cookies.html" format="https" scope="external"> 및 Experience Cloud ID 서비스를 참조하십시오</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_nsid</code> </p> </td> 
   <td colname="col2"> <p>이름 공간 ID. 사용되는 JavaScript 컨테이너를 나타냅니다. DIL에서 <span class="wintitle"> ID를</span> 동기화하는 데 사용됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ptfm </code> </p> </td> 
   <td colname="col2"> <p>Audience Manager이 모바일 요청을 데스크톱 요청과 구분할 수 있습니다. 지원되는 값은 다음과 같습니다. </p> <p> 
     <ul id="ul_A01D4B15C89F4713A39E08377924D632"> 
      <li id="li_E17CC839265B4EB9AC44A3DA31A23857"> <code> ios</code> </li> 
      <li id="li_468F5903CD3048B5AE02A3FDA9B3C4F1"> <code> android</code> </li> 
      <li id="li_57090DAC3BDA41DFB4BA0DD328754D55"> <code> browser</code> </li> 
      <li id="li_DA4E93A831FE4FD8971CECD508AF992F"> <code> all</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rs</code> </p> </td> 
   <td colname="col2"> <p>삭제 예정. <code> d_rs</code> 는 예약된 속성으로서, <span class="keyword"> Adobe Analytics</span> 와 <span class="keyword"> Audience Manager</span>간의 기존 통합에 사용됩니다. </p> <p>예약된 특성을 사용하는 특성을 만들지 않는 것이 좋습니다. Adobe는 언제든지 예약 속성을 변경할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rtbd=json</code> </p> </td> 
   <td colname="col2"> <p>DCS에서 <code> JSON</code> 응답을 받으려면 <span class="wintitle"> 필요합니다</span>. </p> <p> 
     <ul id="ul_9EA00BD822504BCA8ECB59C1634DB91A"> 
      <li id="li_7CB890F92C4A4C6AA8B4EE32E1AD4564">이 값을 생략하면 DCS에서 <span class="wintitle"> 헤더의</span> 픽셀을 반환합니다. </li> 
      <li id="li_824C23B4C7AA4B5EBADF73D26016A18E">이 값을 포함하면 <span class="wintitle"> DCS는</span> 응답 본문에 <code> JSON</code> 개체를 반환합니다. 아래 예를 참조하십시오. 보다 복잡한 응답을 얻을 수 있습니다. </li> 
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
   <td colname="col2"> <p><code> SID</code> 는 <span class="term"> 점수 ID를 나타냅니다</span>. 특성 또는 세그먼트에 대한 고유 ID입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid</code> </p> </td> 
   <td colname="col2"> <p>트레이트 평가를 위한 데이터 소스를 전달합니다. 이 데이터 소스의 특성만 평가됩니다. </p> <p>예를 들어 다음과 같은 이점이 있습니다. </p> <p> 
     <ul id="ul_6230777E16C14DCB83025A101A4ECA14"> 
      <li id="li_71F3970417BC4B93881A3E12DADE4120"><b>트레이트 T1</b> with: </li> 
      <li id="li_66125E035F524A958C6F4BFAABA2A0D2">특성 규칙: "<code> key1 == val1</code>" </li> 
      <li id="li_4EE486E02CF54AEA876ABC005094E9E4">데이터 소스(DPID<a href="../../../reference/ids-in-aam.md"></a>): 1 </li> 
      <li id="li_3E6BBDEAE5C644C6A96CB49766CDA988">DPID 통합 코드: ic1 </li> 
     </ul> 
     <ul id="ul_0C30A8AE349D43A08490DA76CB4B06FA"> 
      <li id="li_F1E8DB26168B471FA35D82F4DD3AC601"><b>트레이트 T2</b> 및 </li> 
      <li id="li_1C943F84A4A149A0A86ABC92761D3E9E">특성 규칙: "<code> key2 == val2</code>" </li> 
      <li id="li_F2AA086C87B7484F8BFE1D5C09E8EBDF">데이터 소스(DPID): 2 </li> 
      <li id="li_877CAAAE996A4707BEE74F7042708481">DPID 통합 코드: ic2 </li> 
     </ul> </p> <p>샘플 호출에서는 <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid=1</code>특성 T1만 반환됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid_ic</code> </p> </td> 
   <td colname="col2"> <p>목적은 위에서 설명한 매개 변수와 <code> d_tdpid</code> 동일합니다. 그러나 이 경우 데이터 소스는 통합 코드를 사용하여 전달됩니다. </p> <p>위에 설명된 트레이트를 유지하려면 샘플 호출을 고려하십시오. </p> <p>예를 <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid_ic=ic2</code>들어 특성 T2만 반환됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_uuid</code> </p> </td> 
   <td colname="col2"> <p>고유 사용자 ID. 쿠키에서 이 값을 사용할 수 없을 때 방문자를 식별합니다. </p> </td> 
  </tr>
 </tbody>
</table>