---
seo-title: 서버 간 DCS API 호출 만들기
solution: Audience Manager
title: 서버 간 DCS API 호출 만들기
uuid: bdfe3430-e27f-4a5c-88d9-ae164d28f601
translation-type: tm+mt
source-git-commit: bc2a9364b771436fe0191f9d69a8c291563f9229

---


# 서버 간 DCS API 호출 만들기 {#making-server-to-server-dcs-api-calls}

호출에는 지역 DCS 서버의 호스트 이름과 사용자 ID가 필요합니다. 필요한 사용자 및 지역 ID가 없는 경우 DCS 응답 [및/또는 Experience Cloud에서 사용자 ID](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md) 및 지역 가져오기를 [참조하십시오](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md). 사용자 및 지역 ID가 있으면 DCS를 서버 간 호출하도록 할 수 있습니다. 구문과 예는 이 섹션을 참조하십시오.

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. 서버에 대한 호출을 수행할 때 자리 표시자에 대한 실제 값으로 대체합니다 [!UICONTROL DCS].

## 호출 구문 및 예 {#call-syntax-example}

데이터를 서버로 보내는 기본 서버 간 요청은 아래에 표시된 구문을 [!UICONTROL DCS] 사용합니다.

```js
"Host:domain_alias.demdex.net" "https://DCS_host_name.demdex.net/event?d_rtbd=json&d_jsonv=1&d_uuid=userID
```

샘플 호출은 다음 예제와 비슷합니다.

```
"Host:foo.demdex.net" "https://usw2.demdex.net/event?d_rtbd=json&d_jsonv=1& d_uuid=123456789"`
```

## 호출 매개 변수 {#call-parameters}

<table id="table_3AF4466009B64F0C9CBE7904A4096E0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 매개 변수 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> <i>도메인 별칭</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>이 호출에는 다음이 포함됩니다. </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Audience Manager에서 할당한 도메인 <span class="keyword"> 별칭</span> (예: <i><code> my_domain.demdex.net</code></i>)입니다. </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">항상 demdex.net <i><code> 인 대상 도메인입니다</code></i>. <a href="../../../reference/demdex-calls.md">Demdex 도메인에 대한 호출 이해</a>를 참조 하십시오. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> DCS <i>호스트 이름</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>지역 DCS 서버의 이름을 표시하는 http 헤더 호스트 <span class="wintitle"> 매개</span> 변수입니다. 호스트 이름은 지역 ID에 연결되어 있으므로 이러한 유형의 호출을 하기 전에 이 이름이 필요합니다. <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS 영역 ID, 위치 및 호스트 이름</a>을 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> /이벤트에 연결된다는 점을 이용합니다?</code> </p> </td> 
   <td colname="col2"> <p>이 통화 부분: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">호출을 이벤트 호출로 식별합니다. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">DCS로 전송할 데이터가 포함된 URL 문자열의 시작을 정의합니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_uuid= <i>Audience Manager 사용자 ID</i></code> </p> </td> 
   <td colname="col2"> <p>이 키는 Audience Manager 사용자 ID 값을 <span class="keyword"> 키</span> -값 쌍으로 보유하는 고유한 사용자 ID 키입니다. </p> <p>Audience <code><i>Manager</i></code> 사용자 ID를 전달하는 경우 <span class="keyword"> d_uuid를</span> 사용합니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_mid=<i>Experience Cloud 사용자 ID</i></code> </p> </td> 
   <td colname="col2"> <p>키-값 쌍으로 Experience Cloud <span class="keyword"> 사용자</span> ID 값을 보유하는 고유한 사용자 ID 키입니다. ID <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie"> 서비스 쿠키에서 사용자 ID 가져오기를 참조하십시오</a>. </p> <p>Experience <i><code> Cloud</code></i> ID 서비스에서 캡처한 Experience Cloud <span class="keyword"> ID를 전달하는 경우</span> d_mid를 <span class="keyword"> 사용하십시오</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_cb=<i>콜백</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>선택적 응답 매개 변수입니다. </p> <p> DCS로 데이터를 전송하는 데 필요한 것은 <span class="wintitle"> 없습니다</span>. 그러나 DCS에서 <span class="wintitle"> 응답을</span> 반환하려면 <i><code> 요청에 d_rtbd=json</code></i> 을포함해야 합니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 샘플 응답 {#sample-response}

DCS [에서 데이터 받기를 참조하십시오](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).
