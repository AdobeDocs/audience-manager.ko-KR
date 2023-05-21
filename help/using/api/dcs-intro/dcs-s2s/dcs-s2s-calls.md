---
seo-title: Making Server-to-Server DCS API Calls
solution: Audience Manager
title: 서버 간 DCS API 호출 만들기
uuid: bdfe3430-e27f-4a5c-88d9-ae164d28f601
feature: DCS
description: 서버 간 DCS API를 호출할 때 구문, 예 및 매개 변수를 호출합니다
exl-id: 977f4dfe-0beb-43c8-b64e-df4042427474
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 8%

---

# 서버 간 DCS API 호출 만들기 {#making-server-to-server-dcs-api-calls}

호출에는 지역 DCS 서버의 호스트 이름과 사용자 ID가 필요합니다. 필요한 사용자 및 지역 ID가 없는 경우 다음을 참조하십시오. [DCS 응답에서 사용자 ID 및 지역 가져오기](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md) 및/또는 [Experience Cloud](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md). 사용자 및 지역 ID가 있으면 DCS를 서버 간에 호출할 수 있습니다. 구문 및 예는 이 섹션을 참조하십시오.

>[!NOTE]
>
>코드 및 예에서 *기울임체* 변수 자리 표시자를 나타냅니다. 에 대한 서버 간 호출을 수행할 때 자리 표시자에 대한 실제 값 대체 [!DNL DCS].

## 호출 구문 및 예 {#call-syntax-example}

로 데이터를 전송하는 기본 서버 간 요청 [!DNL DCS] 는 아래에 표시된 구문을 사용합니다.

```js
"Host:domain_alias.demdex.net" "https://DCS_host_name.demdex.net/event?d_rtbd=json&d_jsonv=1&d_uuid=userID
```

샘플 호출은 다음 예제와 유사합니다.

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
   <td colname="col2"> <p>이 호출 부분에는 다음이 포함됩니다. </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">이(가) 할당한 도메인 별칭 <span class="keyword"> Audience Manager</span> (예: <i><code> my_domain.demdex.net</code></i>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">대상 도메인(항상) <i><code> demdex.net</code></i>. <a href="../../../reference/demdex-calls.md">Demdex 도메인에 대한 호출 이해</a>를 참조하십시오. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> <i>DCS host name</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>지역 이름을 보여 주는 http 헤더 호스트 매개 변수 <span class="wintitle"> DCS</span> 서버입니다. 호스트 이름은 지역 ID에 연결되어 있으므로 이러한 유형의 호출을 수행하기 전에 이 이름이 필요합니다. <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS 영역 ID, 위치 및 호스트 이름</a>을 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> /event?</code> </p> </td> 
   <td colname="col2"> <p>호출의 이 부분: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">호출을 이벤트 호출로 식별합니다. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">DCS로 전송할 데이터가 포함된 URL 문자열의 시작을 정의합니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_uuid= <i>Audience Manager user ID</i></code> </p> </td> 
   <td colname="col2"> <p>이 키는 을 보유하는 고유한 사용자 ID 키입니다. <span class="keyword"> Audience Manager</span> 키-값 쌍의 사용자 ID 값. </p> <p>사용 <code><i>d_uuid</i></code> 다음을 전달하는 경우 <span class="keyword"> Audience Manager</span> 사용자 ID. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_mid=<i>Experience Cloud user ID</i></code> </p> </td> 
   <td colname="col2"> <p>이 키는 을 보유하는 고유한 사용자 ID 키입니다. <span class="keyword"> Experience Cloud</span> 키-값 쌍의 사용자 ID 값. 참조: <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie"> ID 서비스 쿠키에서 사용자 ID 가져오기</a>. </p> <p>사용 <i><code> d_mid</code></i> 다음을 전달하는 경우 <span class="keyword"> Experience Cloud</span> 에서 캡처된 ID <span class="keyword"> Experience Cloud</span> ID 서비스 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_cb=<i>callback</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>선택적 응답 매개 변수. </p> <p> 데이터를 로 보내는 데 이러한 항목이 필요하지 않습니다. <span class="wintitle"> DCS</span>. 그러나 원하는 경우 <span class="wintitle"> DCS</span> 응답을 반환하려면 다음을 포함해야 합니다. <i><code> d_rtbd=json</code></i> 을 참조하십시오. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 샘플 응답 {#sample-response}

다음을 참조하십시오 [DCS로부터 데이터 받기](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).
