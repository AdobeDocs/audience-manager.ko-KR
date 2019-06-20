---
description: DCS (데이터 수집 서버) 에 전달할 수 있는 구문 및 지원되는 속성 (또는 키-값 쌍) 를 나열하고 설명합니다. 이 정보는 DCS 요청의 형식을 지정하고 이 시스템에서 반환된 매개 변수를 이해하는 데 도움이 됩니다.
seo-description: DCS (데이터 수집 서버) 에 전달할 수 있는 구문 및 지원되는 속성 (또는 키-값 쌍) 를 나열하고 설명합니다. 이 정보는 DCS 요청의 형식을 지정하고 이 시스템에서 반환된 매개 변수를 이해하는 데 도움이 됩니다.
seo-title: DCS API 호출에 지원되는 속성
solution: Audience Manager
title: DCS API 호출에 지원되는 속성
uuid: 0 B 98 ED 11-314 B -4500-AFDE -45 A 041112150
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Supported Attributes for DCS API Calls {#supported-attributes-for-dcs-api-calls}

Lists and describes the syntax and supported attributes (or key-value pairs) you can pass in to the [!UICONTROL Data Collection Servers] ([!UICONTROL DCS]). This information can help you format your [!UICONTROL DCS] requests and understand the parameters returned by this system.

## Attribute Prefixes {#attribute-prefixes}

The [!UICONTROL DCS] relies on specific prefixes added to the keys in key-value pairs to classify the type of data you&#39;re passing in.

<table id="table_23B7E15EC13749E9A245DFB543822DB7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 키 접두사 </th> 
   <th colname="col2" class="entry"> 예약 대상 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> c_</code> </p> </td> 
   <td colname="col2"> <p>고객 정의 속성. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> 속성입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> h_</code> </p> </td> 
   <td colname="col2"> <p>HTTP 헤더 데이터. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> p_</code> </p> </td> 
   <td colname="col2"> <p>고객 정의된 비공개 속성입니다. </p> <p> The DCS accepts your own, private data when the key has a <code> p_</code> prefix. 개인 데이터는 특성 평가에 사용되지만, 시스템에 기록되거나 저장되지 않습니다. For example, lets say you have a trait defined as <code> customers = p_age&lt;25</code> and you pass in <code> p_age=23</code> in an event call. Given these conditions, the user who meets the age-based qualification criteria qualifies for the trait, but the key-value pair is dropped after <span class="keyword"> Audience Manager</span> receives the request and is not logged. </p> </td>
  </tr> 
 </tbody> 
</table>

## d_ Attributes {#d-attributes}

All of these are optional, unless you want a response from the [!UICONTROL DCS]. If you want the [!UICONTROL DCS] to return a response, then `d_rtbd=json` is required.

<table id="table_FCCE4F9D796648899772A191981EFDE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 특성 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> d_ caller</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DCS</span> API에 대한 호출을 만드는 호출자를 식별하는 데 사용됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cb</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DCS</span> 응답을 콜백 함수의 함수 매개 변수로 사용하여 실행할 JavaScript 함수를 지정합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cid</code> </p> </td> 
   <td colname="col2"> <p>Contains one or more pairs of data provider IDs (<code> DPID</code>) and data provider user IDs (<code> DPUUID</code>) assigned by <span class="keyword"> Audience Manager</span>. If you use multiple pairs of <code> DPID</code>s and <code> DPUUID</code>s, separate each pair with the non-printing character <code> %01</code>. For example: <code><i>DPID</i>%01<i>DPUUUID</i></code>. </p> <p><code> d_ cid</code> 는 더 이상 사용되지 않지만 여전히 지원되는 <code> d_ dpid</code> 및 <code> d_ dpuuid</code>를 대체합니다. <a href="../../../reference/cid.md">CID가 DPID 및 DPUUID 대체</a>를 참조하십시오. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_ cid_ ic</code> </p> </td> 
   <td colname="col2"> <p>단일 키-값 쌍에 통합 코드와 연관된 고유 사용자 ID가 포함됩니다. </p> <p><code> d_ cid_ ic</code> 는 <code> d_ dpid</code> 및 <code> d_ dpuuid를 대체합니다</code>. 이 이름은 하락하지만 여전히 지원됩니다. <a href="../../../reference/cid.md">CID가 DPID 및 DPUUID 대체</a>를 참조하십시오. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ coppa</code> </p> </td> 
   <td colname="col2"> <p>아동 보호 규정을 준수하기 위해 타사 쿠키의 사용을 비활성화할 수 있습니다. This parameter is dynamically set by the Adobe Experience Cloud ID service and depends on the <code> idSyncDisable3rdPartySyncing</code> configuration. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_coppa.html" format="https" scope="external"> COPPA Support in the Experience Cloud ID Service</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_ cts = 1</code> </p> <p><code> d_ cts = 2</code> </p> </td> 
   <td colname="col2"> <p>선택 사항입니다. 고객 요청에 대해 활성화됨. Adobe Audience Manager 컨설턴트 또는 고객 지원 센터에 문의하십시오. </p> <p>Indicates that traits and segments should be returned inside the <code> JSON</code> response. </p> <p> 
     <ul id="ul_8B936ACB18724681B959783421ACF026"> 
      <li id="li_792A6248F49141C0B4B214C754D5F5C5"> <p><code> d_ cts = 1</code> 는 세그먼트에 <a href="../../../reference/ids-in-aam.md"> 대한 레거시 세그먼트 ID</a> 를 반환합니다. </p> </li>
      <li id="li_F304CA651F3C444A9A24576726925D87"> <p><code> d_ cts = 2</code> 는 세그먼트에 대한 세그먼트 ID를 반환합니다. </p> </li>
     </ul> </p> <p>샘플 응답은 다음과 같이 표시될 수 있습니다. </p> <p>
     <code class="syntax javascript">{"stuff": [], "uuid": " 07955261652886032950143702505894272138 "," DCS_ REGION ": 7, "traits": [420020, 5421506], "세그먼트": [984263, 985264], "TID": " SS 3 otqpiqp 0 = "} </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ dpid</code> </p> </td> 
   <td colname="col2"> <p>삭제 예정. <code> d_ cid</code> 및 <code> d_ cid_ ic</code>를 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ dpuuid</code> </p> </td> 
   <td colname="col2"> <p>삭제 예정. <code> d_ cid</code> 및 <code> d_ cid_ ic</code>를 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ dst = 1</code> </p> </td> 
   <td colname="col2"> <p><code> JSON</code> 응답에서 URL 대상 데이터를 반환합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst_filter</code> </p> </td> 
   <td colname="col2"> <p><code> d_ dst_ filter</code> 는 Adobe Analytics와 Audience Manager 간의 통합에 사용되는 예약된 속성입니다. </p> <p>예약된 속성을 사용하는 트레이트를 만드는 것이 좋습니다. Adobe는 언제든지 예약된 속성을 변경할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ jsonv = 1|0</code> </p> </td> 
   <td colname="col2"> <p>Indicates the <code> JSON</code> version to use in the response. Normally, you should set this to <code> d_jsonv=1</code>. Setting <code> d_jsonv=0</code> disables ID syncs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_mid</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Experience Cloud</span> ID 서비스가 설정하고 사용하는 Experience Cloud ID를 지정합니다. For more information about the ECID, see <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ nsid</code> </p> </td> 
   <td colname="col2"> <p>이름 공간 ID. 사용된 JavaScript 컨테이너를 나타냅니다. Used by <span class="wintitle"> DIL</span> to for id-syncing. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ ptfm </code> </p> </td> 
   <td colname="col2"> <p>Audience Manager가 데스크탑 요청의 모바일 요청을 구분할 수 있도록 해줍니다. 지원되는 값은 다음과 같습니다. </p> <p> 
     <ul id="ul_A01D4B15C89F4713A39E08377924D632"> 
      <li id="li_E17CC839265B4EB9AC44A3DA31A23857"> <code> Ios</code> </li> 
      <li id="li_468F5903CD3048B5AE02A3FDA9B3C4F1"> <code> Android</code> </li> 
      <li id="li_57090DAC3BDA41DFB4BA0DD328754D55"> <code> browser</code> </li> 
      <li id="li_DA4E93A831FE4FD8971CECD508AF992F"> <code> all</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rs</code> </p> </td> 
   <td colname="col2"> <p>삭제 예정. <code> d_ rs</code> 는 Adobe <span class="keyword"> Analytics</span> 와 <span class="keyword"> Audience Manager 간의 기존 통합에 사용되는 예약된 속성입니다</span>. </p> <p>예약된 속성을 사용하는 트레이트를 만드는 것이 좋습니다. Adobe는 언제든지 예약된 속성을 변경할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ rtbd = json</code> </p> </td> 
   <td colname="col2"> <p>Required if you want a <code> JSON</code> response from the <span class="wintitle"> DCS</span>. </p> <p> 
     <ul id="ul_9EA00BD822504BCA8ECB59C1634DB91A"> 
      <li id="li_7CB890F92C4A4C6AA8B4EE32E1AD4564">If you omit this, the <span class="wintitle"> DCS</span> returns a pixel in the header. </li> 
      <li id="li_824C23B4C7AA4B5EBADF73D26016A18E">If you include this, the <span class="wintitle"> DCS</span> returns a <code> JSON</code> object in the body of the response. 아래 예를 참조하십시오. 더욱 복잡해질 수 있습니다. </li> 
     </ul> </p> <p> 
     <code class="syntax javascript">{"stuff": [], "uuid": " 2292011296801967861290439444954495490 "," DCS_ REGION ": 7, "tid": " SS 3 otqpiqp 0 = "} </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ sid</code> </p> </td> 
   <td colname="col2"> <p><code> SID</code> 는 <span class="term"> 점수 ID</span>를 나타냅니다. 트레이트 또는 세그먼트에 대한 고유 ID 입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ tdpid</code> </p> </td> 
   <td colname="col2"> <p>트레이트 평가를 위해 데이터 소스를 전달합니다. 이 데이터 소스의 특성만 평가됩니다. </p> <p>예를 들면 다음과 같습니다. </p> <p> 
     <ul id="ul_6230777E16C14DCB83025A101A4ECA14"> 
      <li id="li_71F3970417BC4B93881A3E12DADE4120"><b>특성 T 1</b> with: </li> 
      <li id="li_66125E035F524A958C6F4BFAABA2A0D2">Trait rule: "<code> key1 == val1</code>" </li> 
      <li id="li_4EE486E02CF54AEA876ABC005094E9E4">Data Source (<a href="../../../reference/ids-in-aam.md"> DPID</a>): 1 </li> 
      <li id="li_3E6BBDEAE5C644C6A96CB49766CDA988">DPID 통합 코드: IC 1 </li> 
     </ul> 
     <ul id="ul_0C30A8AE349D43A08490DA76CB4B06FA"> 
      <li id="li_F1E8DB26168B471FA35D82F4DD3AC601"><b>특성 T 2</b> : </li> 
      <li id="li_1C943F84A4A149A0A86ABC92761D3E9E">Trait rule: "<code> key2 == val2</code>" </li> 
      <li id="li_F2AA086C87B7484F8BFE1D5C09E8EBDF">데이터 소스 (DPID): 2 </li> 
      <li id="li_877CAAAE996A4707BEE74F7042708481">DPID 통합 코드: IC 2 </li> 
     </ul> </p> <p>In a sample call, <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid=1</code>, only trait T1 is returned. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ tdpid_ ic</code> </p> </td> 
   <td colname="col2"> <p>The purpose is identical to the <code> d_tdpid</code> parameter described above. 하지만 이 경우 통합 코드를 사용하여 데이터 소스가 전달됩니다. </p> <p>위에 설명된 트레이트를 그대로 유지하려면 샘플 호출을 고려하십시오. </p> <p><code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid_ic=ic2</code>의 경우 트레이트 T 2만 반환됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ uuid</code> </p> </td> 
   <td colname="col2"> <p>고유 사용자 ID. 쿠키에서 이 값을 사용할 수 없을 때 방문자를 식별합니다. </p> </td> 
  </tr>
 </tbody>
</table>