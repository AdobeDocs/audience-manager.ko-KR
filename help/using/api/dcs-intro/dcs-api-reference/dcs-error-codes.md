---
description: DCS (데이터 수집 서버) 가 생성한 오류 코드 및 메시지는 코드 ID 별로 숫자 순서로 나열됩니다.
seo-description: DCS (데이터 수집 서버) 가 생성한 오류 코드 및 메시지는 코드 ID 별로 숫자 순서로 나열됩니다.
seo-title: DCS 오류 코드, 메시지 및 예제
solution: Audience Manager
title: DCS 오류 코드, 메시지 및 예제
uuid: D 3290038-567 B -4 C 00-BC 95-2 CEC 683 DA 5 EC
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# DCS 오류 코드, 메시지 및 예제 {#dcs-error-codes-messages-and-examples}

[!UICONTROL Data Collection Servers] ([!UICONTROL DCS]) 코드 ID 별로 숫자 순서에 나열된 오류 코드 및 메시지.

In the tables below, *italics* represents a variable placeholder.

## System Error Codes {#system-error-codes}

<table id="table_43F4321BEA6A4D1BBDFE2E9FB4402914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 코드 ID </th> 
   <th colname="col2" class="entry"> 오류 메시지 </th> 
   <th colname="col3" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>0 </p> </td> 
   <td colname="col2"> <p>지정되지 않음 오류 </p> </td> 
   <td colname="col3"> <p>다른 오류 핸들러에 포함되지 않은 이벤트를 처리하는 catch-all 오류입니다. 이 오류는 해결할 수 없습니다. 알 수 없는 다양한 동작 또는 이벤트로 인해 발생할 수 있습니다. </p> <p>If you receive this error, try your <span class="wintitle"> DCS</span> request again. 문제가 지속되면 Adobe 담당자에게 문의하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>Could not find config for hostname: <code><i>hostname</i></code> </p> </td> 
   <td colname="col3"> <p>요청에서 전송된 호스트 이름이 파트너 프로비저닝 팀에서 설정되지 않았습니다. 이 오류 메시지가 표시되면 Adobe 담당자에게 문의하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>Invalid <code> d_orgid</code> value (could not find a config for this org id): <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>조직 ID가 잘못되었습니다. </p> <p>ID를 확인하고 요청을 다시 시도하십시오. If you do not know or have your Organization ID, see the "Administration Page" section in <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html" format="https" scope="external"> Experience Cloud Administration</a> for information about how to find it. </p> </td> 
  </tr>
 </tbody>
</table>

## Integration Error Codes {#integration-error-codes}

<table id="table_EFF06FB3D045459BA7802872AF22DF79"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 코드 ID </th> 
   <th colname="col2" class="entry"> 메시지 </th> 
   <th colname="col3" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>100 </p> </td> 
   <td colname="col2"> <p>요청에 대한 호스트 이름을 검색할 수 없습니다. </p> </td> 
   <td colname="col3"> <p>API 호출이 요청에서 호스트 HTTP 헤더를 전송하지 않았습니다. </p> <p>호출에 호스트 헤더를 추가하고 다시 시도하십시오. 대부분의 브라우저와 API 클라이언트는 이를 자동으로 수행합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>101 </p> </td> 
   <td colname="col2"> <p>Invalid Experience Cloud id passed in <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p><span class="wintitle"> DCS</span> 호출에 잘못된 <span class="keyword"> Experience Cloud</span> ID가 포함되어 있습니다. </p> <p>Check the <code> d_mid=</code> key-value pair in the header string. <span class="keyword"> 올바른 Experience Cloud</span> ID를 전달하고 요청을 다시 시도하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>102 </p> </td> 
   <td colname="col2"> <p>Invalid aam id passed in request <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p><span class="wintitle"> DCS</span> 호출에 잘못된 <span class="keyword"> Audience Manager</span> ID가 포함되어 있습니다. </p> <p>Check the <code> d_uuid=</code> key-value pair in the header string. <span class="keyword"> 올바른 Audience Manager</span> ID를 전달하고 요청을 다시 시도하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>104 </p> </td> 
   <td colname="col2"> <p>모든 고객 ID가 잘못되었습니다. </p> </td> 
   <td colname="col3"> <p>호출에 있는 모든 고객 ID가 유효하지 않습니다. ID를 확인하고 다시 시도하십시오. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>111 </p> </td> 
   <td colname="col2"> <p>Invalid <span class="wintitle"> IMS</span> token received </p> </td> 
   <td colname="col3"> <p>Audience Manager에 대해 반환 - Adobe Target 통합. 잘못된 IMS 토큰을 포함하는 DCS에 대한 호출이 실행되면 오류가 발생합니다. 토큰이 잘못되었거나, 만료되었거나, 사용자가 필요한 리소스에 액세스할 수 있는 권한이 없을 수 있습니다. </p> </td>
  </tr>
 </tbody>
</table>

## Opt-Out Error Codes {#opt-out-error-codes}

<table id="table_A50C284AB84F48A79B01223D991884A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 코드 ID </th> 
   <th colname="col2" class="entry"> 메시지 </th> 
   <th colname="col3" class="entry"> 설명 </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>171 </p> </td> 
   <td colname="col2"> <p>Encountered opt out tag for id <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>고객이 관심 기반 광고를 받지 않기로 선택한 경우 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>172 </p> </td> 
   <td colname="col2"> <p>차단된 쿠키 </p> </td> 
   <td colname="col3"> <p>사용자의 브라우저가 서드 파티 쿠키를 차단할 때 반환됩니다.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>173 </p> </td> 
   <td colname="col2"> <p>Encountered trust relationship via <a href="https://www.networkadvertising.org/" format="http" scope="external"> NAI</a> </p> </td> 
   <td colname="col3"> <p>사용자가 NAI를 통해 옵트아웃 프로세스를 시작했습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>198 </p> </td> 
   <td colname="col2"> <p>이 국가의 요청은 파트너에 의해 차단됩니다. </p> </td> 
   <td colname="col3"> <p>Based on the IP address, the <span class="wintitle"> DCS</span> blocks requests from countries where the partner has deliberately limited the traffic. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>이 국가의 요청은 허용되지 않습니다. </p> </td> 
   <td colname="col3"> <p>Based on the IP address, the <span class="wintitle"> DCS</span> blocks requests from the following countries: </p> <p> 
     <ul id="ul_4017A7D074064FE7A8B5618AFCFA4E28"> 
      <li id="li_EE65DEC3C64F4522B214C503DC754DC1">쿠바 (CU) </li> 
      <li id="li_EDE8B304D35A41458DCFF11E9328802A">이란 (IR) </li> 
      <li id="li_36664315A06540E0BE024EE60638D5DC">북한 (KP) </li> 
      <li id="li_B508A5FF173E491AAE41334C074D9DED">수단 (SD) </li> 
      <li id="li_0875540C20204158ADBD92698CEB10EA">시리아 (SY) </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Profile Retrieval Error Codes {#profile-retrieval-error-codes}

<table id="table_CFF2252A3CC54960802905454A867D7A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 코드 ID </th> 
   <th colname="col2" class="entry"> 메시지 </th> 
   <th colname="col3" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>200 </p> </td> 
   <td colname="col2"> <p> Cannot read traits from profile cache for id: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>내부 저장소에서 사용자 프로필을 읽을 수 없을 때 반환됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> Cannot read device ids from profile cache for customer id: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Returned when the <a href="../../../reference/ids-in-aam.md"> device ID</a> cannot be retrieved for a Profile Link merge rule. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>Cannot read related customer for device id: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Returned when the <a href="../../../reference/ids-in-aam.md"> customer ID (UUID)</a> associated to a device ID cannot be retrieved for a Last Authenticated merge rule from our internal storage. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> Cannot read device cluster for id: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>같은 장치 그래프 클러스터의 연결된 장치 ID를 이 장치 ID에 대해 반환할 수 없습니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>기본 장치에 대해 프로필 읽기가 실패한 이후 마이그레이션을 수행할 수 없음 </p> </td> 
   <td colname="col3"> <p>If you receive this error, we may be experiencing scalability issues with our data store (<span class="wintitle"> PCS</span>). 문제가 지속되면 Adobe 담당자에게 문의하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>Could not perform migration from <code><i>ID</i></code> to <code><i>ID</i></code>, because profile read failed for <code><i>ID</i></code> </p> </td>
   <td colname="col3"> <p>If you receive this error, we may be experiencing scalability issues with our data store (<span class="wintitle"> PCS</span>). 문제가 지속되면 Adobe 담당자에게 문의하십시오. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Integration Warning Codes {#integration-warning-codes}

<table id="table_31F1593C46804DDBA2E9BEDE83F2417F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 코드 ID </th> 
   <th colname="col2" class="entry"> 메시지 </th> 
   <th colname="col3" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>300 </p> </td> 
   <td colname="col2"> <p>Invalid customer id <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>고객 ID가 잘못되었습니다 (데이터 소스에 대한 값 누락, 통합 코드 누락, Data Sources에 대한 잘못된 형식, 차단된 고객 ID, 빈 고객 ID, 파트너에 속하지 않은 데이터 소스에 대한 권한 없는 액세스 시도). </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>301 </p> </td> 
   <td colname="col2"> <p>최대 고객 ID 수를 초과했습니다. Maximum allowed is <code><i>maximum allowed</i></code>. Found is <code><i>maximum found</i></code>.</p> </td> 
   <td colname="col3"> <p>장치 간 데이터 소스와 연결된 고객 ID 수가 요청당 허용되는 장치 ID 수를 초과합니다. 이러한 ID 에는 크로스 디바이스, 모바일 또는 쿠키 ID가 포함됩니다. 현재 제한은 10로 설정되어 있습니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p>Unauthorized customer id <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>고객 ID 데이터 소스가 현재 조직 ID가 소유하지 않을 때 반환됩니다. If you do not know or have your Organization ID, see the "Find your Organization ID" section in <a href="https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html" format="https" scope="external"> Organizations and Account Linking</a> for information about how to find it. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>Blocked customer id <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>고객 ID가 악성 것으로 식별되고 블랙리스트에 추가된 경우에 반환됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>Blocked datasource id <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>데이터 소스 ID가 악성 것으로 식별되고 블랙리스트에 추가된 경우에 반환됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p>Blocked declared device id <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>장치 ID가 악성 것으로 식별되었으며 차단되었습니다. This can happen when we receive an extreme amount of <span class="wintitle"> DCS</span> requests containing this device ID in a short amount of time. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p>Blocked profile operation for <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>ID가 악성 것으로 식별되고 차단된 경우 읽기/쓰기 작업이 차단되었습니다. 오류 코드 306를 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p>Customer id <code><i>ID</i></code> was discarded because it exceeded the limit of declared customer ids per request </p> </td> 
   <td colname="col3"> <p>오류 301와 관련되어 있습니다. 이 오류는 제한을 초과하였으므로 어느 고객 ID가 폐기되었는지를 지정합니다. </p> <p>For example, If there are 12 customer IDs declared on the <span class="wintitle"> DCS</span> call, two of them will be discarded. 버려진 항목을 릴레이하기 위해 이 오류는 응답에 두 번 나타납니다 (무시된 고객 ID 각각에 대해 한 번). </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>고객 ID가 주어진 네임스페이스에 대한 제한을 초과하여 무시되었습니다. Namespace id is <code><i>ID</i></code>, customer id is <code><i>ID</i></code>. </p> </td> 
   <td colname="col3"> <p>This error code is returned if there are more than 3 customer IDs declared for the same namespace (<code> DPID</code>) on a <span class="wintitle"> DCS</span> call. </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one </code> </p> <p>In this sample <span class="wintitle"> DCS</span> request, there are 4 ids declared for the same namespace (with the integration code one). ID 중 하나가 무시되고 오류 310 이 반환됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311 </p> </td> 
   <td colname="col2"> <p>요청에 잘못된 매개 변수가 들어 있습니다. </p> </td> 
   <td colname="col3"> <p><span class="wintitle"> 하나</span> 이상의 URL 매개 변수가 제대로 인코딩되지 않은 경우 DCS는 이 오류 코드를 반환합니다. In this case, the <span class="wintitle"> DCS</span> disregards the entire request. </p> <p><code>HTTP: partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp; d_ creative = % ECID!&amp; d_ adgroup = % eaid!&amp; d_ placement = % EPID!&amp; d_ campaign = % ebuy!&amp;d_adsrc=48123</code> </p> <p>In the sample request above, the <code> %</code> sequence is incorrectly encoded. Consequently, the <span class="wintitle"> DCS</span> will disregard it. </p> <p>올바르게 인코딩된 샘플은 다음과 같아야 합니다. </p> <p><code>HTTP: partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp; d_ creative = % 25 ECID!&amp; d_ adgroup = % 25 eaid!&amp; d_ placement = % 25 epid!&amp; d_ campaign = % 25 ebuy!&amp;d_adsrc=48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>요청에 잘못된 전역 장치 ID가 들어 있습니다. </p> </td> 
   <td colname="col3"> <p>The <span class="wintitle">DCS</span> returns this error code when  the request contains an invalid Global Device ID. DCS는 잘못된 ID를 무시하고 잘못된 ID의 특정 오류와 함께 312 오류를 발생시킵니다. Refer to <a href="../../../features/global-data-sources.md" format="dita" scope="local">Global Data Sources</a> and <a href="../../../reference/ids-in-aam.md" format="dita" scope="local">Index of IDs in Audience Manager</a> for detailed information on the correct device advertising ID formats and corresponding global data sources.</p>
   <p>Example of an incorrect call: <code>"http://partner.demdex.net/event?d_rtbd=json&amp;d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"</code></p>
   <p>Explanation: An <span class="keyword">IDFA (DPID 20915)</span> must be an uppercase ID. 요청에 제공된 ID는 소문자입니다.</p>
   </td>
  </tr>

</tbody>
</table>

## Sample Error Code Messages {#sample-error-codes}

The [!UICONTROL DCS] returns error codes and messages in a [!DNL JSON] object or in an X- header in the HTTP response string.

### DCS 오류 코드 및 메시지 샘플

```
{ 
   "errors":[ 
      { 
         "code":101,
         "msg":"Invalid Experience Cloud id passed in"
      },
      { 
         "code":102,
         "msg":"Invalid aam id passed in request"
      }
   ]
}
```

### x-error

Error codes captured by the X- header appear in the URL string like this, `X-Error: 101,102`.

[레이스 조건 및 오류 처리](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)