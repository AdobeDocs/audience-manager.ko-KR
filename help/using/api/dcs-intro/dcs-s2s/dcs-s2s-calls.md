---
seo-title: 서버 간 DCS API 호출 만들기
solution: Audience Manager
title: 서버 간 DCS API 호출 만들기
uuid: BDFE 3430-E 27 F -4 A 5 C -88 D 9-AE 164 D 28 F 601
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# 서버 간 DCS API 호출 만들기 {#making-server-to-server-dcs-api-calls}

호출 시 지역 DCS 서버의 호스트 이름과 사용자 ID가 필요합니다. 필수 사용자 및 지역 ID가 없는 경우 DCS [응답](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md) 및/또는 [Experience Cloud에서 사용자 ID 및 지역 가져오기를 참조하십시오](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md). 사용자 및 지역 ID가 있으면 DCS에 서버 간 호출을 만들 수 있습니다. 구문 및 예는 이 섹션을 참조하십시오.

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. 서버 간 호출을 [!UICONTROL DCS]호출할 때 자리 표시자에 대한 실제 값을 대체합니다.

## 호출 구문 및 예 {#call-syntax-example}

에 데이터를 전송하는 기본 서버-서버 요청은 아래 표시된 구문을 [!UICONTROL DCS] 사용합니다.

<pre><code>" 주최자:<i>domain alias</i>. demdex. net "" https://DCS<i>Host name.demdex.net/event?d_rtbd=json&amp;d_jsonv=1&amp;d_uuid=user</i><i>ID</i>.</code></pre>

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
   <td colname="col1"> <p><code><i>domain alias</i>. demdex. net</code> </p> </td> 
   <td colname="col2"> <p>호출의 이 부분에는 다음이 포함됩니다. </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Audience Manager에서 <span class="keyword"> 할당한 도메인 별칭</span> (예: <i><code> my_ domain. demdex. net</code></i>) </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">항상 <i><code> demdex. net</code></i>인 대상 도메인입니다. <a href="../../../reference/demdex-calls.md">Demdex 도메인에 대한 호출 이해</a>를 참조 하십시오. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>dcs 호스트 이름</i>demdex. net</code> </p> </td> 
   <td colname="col2"> <p>지역 <span class="wintitle"> DCS</span> 서버의 이름을 표시하는 HTTP 헤더 호스트 매개 변수. 호스트 이름은 영역 ID에 연결되어 있으므로 이러한 유형의 호출을 만들기 전에 이 ID가 필요합니다. <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS 영역 ID, 위치 및 호스트 이름</a>을 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> /이벤트에 연결된다는 점을 이용합니다?</code> </p> </td> 
   <td colname="col2"> <p>호출의 다음 부분: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">호출을 이벤트 호출로 식별합니다. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">DCS로 전송할 데이터를 포함하는 URL 문자열의 시작을 정의합니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_ uuid = <i>Audience Manager 사용자 ID</i></code> </p> </td> 
   <td colname="col2"> <p>이것은 키-값 쌍의 <span class="keyword"> Audience Manager</span> 사용자 ID 값을 보유하는 고유한 사용자 ID 키입니다. </p> <p>Audience <code><i>Manager 사용자 ID를 전달하는</i></code> <span class="keyword"> 경우 d_ uuid</span> 를 사용합니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_ mid =<i>Experience Cloud 사용자 ID</i></code> </p> </td> 
   <td colname="col2"> <p>이것은 키-값 쌍의 <span class="keyword"> Experience Cloud</span> 사용자 ID 값을 보유하는 고유한 사용자 ID 키입니다. ID 서비스 쿠키에서 사용자 ID <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie"> 가져오기를 참조하십시오</a>. </p> <p>Experience <i><code> Cloud</code></i> ID 서비스에서 캡처한 <span class="keyword"> Experience Cloud</span> ID를 전달하는 <span class="keyword"> 경우 d_ mid</span> 를 사용합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_ dst = 1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_ rtbd = json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_ cb =<i>callback</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>선택적 응답 매개 변수. </p> <p> <span class="wintitle"> DCS</span>로 데이터를 전송할 필요가 없습니다. <span class="wintitle"> DCS</span> 에서 응답을 반환하려면 요청에 <i><code> d_ rtbd = json</code></i> 를 포함해야 합니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 샘플 응답 {#sample-response}

DCS에서 데이터 [받기를 참조하십시오](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).
