---
seo-title: 서버 간 DCS API 호출 만들기
solution: Audience Manager
title: 서버 간 DCS API 호출 만들기
uuid: bdfe3430-e27f-4a5c-88d9-ae164d28f601
feature: DCS
description: 서버 간 DCS API 호출을 수행할 때 구문, 예 및 매개 변수 호출
translation-type: tm+mt
source-git-commit: e40233ace5cb74743db7d0f9f90707fa596a7e79
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 9%

---


# 서버 간 DCS API 호출 만들기 {#making-server-to-server-dcs-api-calls}

호출에는 지역 DCS 서버의 호스트 이름과 사용자 ID가 필요합니다. 필요한 사용자 및 지역 ID가 없는 경우 [DCS 응답에서 사용자 ID 및 지역 가져오기](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md) 및/또는 [Experience Cloud](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md)를 참조하십시오. 사용자 및 지역 ID가 있으면 DCS에 대한 서버 간 호출을 수행할 수 있습니다. 구문 및 예는 이 섹션을 참조하십시오.

>[!NOTE]
>
>코드 및 예에서 *기울임체*&#x200B;는 변수 자리 표시자를 나타냅니다. 서버 간 호출에서 [!DNL DCS]을(를) 호출할 때 자리 표시자의 실제 값을 대체합니다.

## 호출 구문 및 예 {#call-syntax-example}

데이터를 [!DNL DCS]으로 전송하는 기본 서버 간 요청에서는 아래에 표시된 구문을 사용합니다.

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
   <td colname="col1"> <p><code> <i>domain alias</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>이 호출 부분은 다음을 포함합니다. </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9"><span class="keyword"> Audience Manager</span>(예: <i><code> my_domain.demdex.net</code></i>)에 의해 할당된 도메인 별칭입니다. </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">대상 도메인(항상 <i><code> demdex.net</code></i>)입니다. <a href="../../../reference/demdex-calls.md">Demdex 도메인에 대한 호출 이해</a>를 참조하십시오. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> <i>DCS host name</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>지역 <span class="wintitle"> DCS</span> 서버의 이름을 표시하는 http 헤더 호스트 매개 변수입니다. 호스트 이름은 지역 ID에 연결되어 있으므로 이러한 유형의 호출을 하기 전에 이 이름이 필요합니다. <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS 영역 ID, 위치 및 호스트 이름</a>을 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> /event?</code> </p> </td> 
   <td colname="col2"> <p>호출 부분: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">호출을 이벤트 호출로 식별합니다. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">DCS로 전송할 데이터가 포함된 URL 문자열의 시작을 정의합니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_uuid= <i>Audience Manager user ID</i></code> </p> </td> 
   <td colname="col2"> <p>키-값 쌍에 <span class="keyword"> Audience Manager</span> 사용자 ID 값을 포함하는 고유한 사용자 ID 키입니다. </p> <p><span class="keyword"> Audience Manager</span> 사용자 ID를 전달하는 경우 <code><i>d_uuid</i></code>을 사용합니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_mid=<i>Experience Cloud user ID</i></code> </p> </td> 
   <td colname="col2"> <p>키-값 쌍에 <span class="keyword"> Experience Cloud</span> 사용자 ID 값을 포함하는 고유한 사용자 ID 키입니다. ID 서비스 쿠키</a>에서 사용자 ID 가져오기를 참조하십시오.<a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie"> </a></p> <p><span class="keyword"> Experience Cloud</span> ID 서비스에서 캡처한 <span class="keyword"> Experience Cloud</span> ID를 전달하는 경우 <i><code> d_mid</code></i>을 사용합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_cb=<i>callback</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>선택적 응답 매개 변수입니다. </p> <p> 이러한 데이터 중 <span class="wintitle"> DCS</span>에 데이터를 보낼 필요가 없습니다. 그러나 <span class="wintitle"> DCS</span>에서 응답을 반환하려면 요청에 <i><code> d_rtbd=json</code></i>를 포함해야 합니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 샘플 응답 {#sample-response}

[DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md)에서 데이터 받기를 참조하십시오.
