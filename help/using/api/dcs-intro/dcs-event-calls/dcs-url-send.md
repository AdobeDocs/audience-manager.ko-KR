---
description: DCS에 대한 /event 호출을 만드는 방법에 대한 자세한 내용은 여기에서 시작합니다. 이 섹션에는 호출 구문, 매개 변수, 형식 지정 및 요청 예에 대한 정보가 포함되어 있습니다.
seo-description: DCS에 대한 /event 호출을 만드는 방법에 대한 자세한 내용은 여기에서 시작합니다. 이 섹션에는 호출 구문, 매개 변수, 형식 지정 및 요청 예에 대한 정보가 포함되어 있습니다.
seo-title: DCS로 데이터 보내기
solution: Audience Manager
title: DCS로 데이터 보내기
uuid: 024e307d-bfcb-46cf-ac3a-fc71df0248fe
translation-type: tm+mt
source-git-commit: 9c692ae41a309b4f1d8323a501619c02d2aef6a0

---


# DCS로 데이터 보내기 {#send-data-to-the-dcs}

전화 통화에 대한 자세한 내용은 여기에서 `/event` 시작하십시오 [!UICONTROL DCS]. 이 섹션에는 호출 구문, 매개 변수, 형식 지정 및 요청 예에 대한 정보가 포함되어 있습니다.

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. 이 방법으로 데이터를 로 보낼 때 자리 표시자의 실제 값으로 [!UICONTROL DCS] 대체합니다.

## 호출 구문 {#dcs-call-syntax}

데이터를 로 전송하는 기본 `URL` 문자열은 [!UICONTROL DCS] 아래에 표시된 구문을 사용합니다.

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

>[!NOTE]
>
>또한 메서드를 사용하여 데이터를 [!UICONTROL DCS] 로 보낼 수도 `POST` 있습니다. 호출 구문은 DCS API [메서드에서 설명합니다](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md).

## 호출 매개 변수 {#dcs-call-parameters}

다음 표에서는 간단한 [!UICONTROL DCS] 호출의 기본 구성 요소를 정의합니다.

<table id="table_5F6A5B324EB848168543386516FBF384"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 구성 요소 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> domain alias.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>이 호출에는 다음이 포함됩니다. </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Audience Manager에서 할당한 도메인 <span class="keyword"> 별칭</span> (예: <code> my_domain.demdex.net</code>)입니다. </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">항상 demdex.net <code> 인 대상 도메인입니다</code>. <a href="../../../reference/demdex-calls.md">Demdex 도메인에 대한 호출 이해</a>를 참조 하십시오. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /이벤트에 연결된다는 점을 이용합니다?</code> </p> </td> 
   <td colname="col2"> <p>이 통화 부분: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">호출을 이벤트 호출로 식별합니다. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">DCS로 전송할 데이터가 포함된 URL 문자열의 시작을 <span class="wintitle"> 정의합니다</span>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> key</code> </p> </td> 
   <td colname="col2"> <p>키-값 쌍의 고유 식별자입니다. </p> <p>이러한 키-값 쌍은 특정 접두사를 사용하여 DCS로 전송하려는 데이터 유형을 <span class="wintitle"> 식별합니다</span>. For more information, see <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Supported Attributes for DCS API Calls</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>키-값 쌍의 키로 정의된 세트에 속하는 변수 값. </p> <p>값 작업 시: </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">문자열 데이터를 큰 따옴표(예: page="41 ~ 55" <code></code>)로 묶습니다. </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">단일 값(예: <i><code>key</i>=<i>val1,val2,val3</i></code></i>)에 여러 키를 전달할 수 있습니다. </i></li> 
     </ul> </p> <p>DCS <a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md"> 호출에서 키-값 쌍 서식 지정을 참조하십시오</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_cb=<i>콜백</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>선택적 응답 매개 변수입니다. </p> <p> DCS로 데이터를 전송하는 데 필요한 것은 <span class="wintitle"> 없습니다</span>. 그러나 DCS에서 <span class="wintitle"> 응답을</span> 반환하려면 <code> 요청에 d_rtbd=json</code> 을포함해야 합니다. </p> <p>d_ <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> 키-값 쌍 정의를</a>참조하십시오. </p> </td> 
  </tr>
 </tbody>
</table>

## 샘플 호출 {#dcs-sample-call}

이 예는 가상의 회사가 [!DNL Acme, Inc.] 호출을 통해 데이터를 [!UICONTROL DCS] [!DNL HTTP] 서버로 전송하는 것을 보여줍니다. 이 호출에는 선택적 매개 변수, `d_dst=1``d_rtbd=json`및 `d_cb=callback`가 포함됩니다. 이는 호출 [!DNL Acme] 백 기능이 있는 응답으로부터 [!DNL JSON] 응답을 받으려는 [!UICONTROL DCS] 것을 나타냅니다. 기억하십시오, 이것은 단지 예시입니다. 이 코드를 잘라내어 붙여 넣지 마십시오.

```js
https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback
```

## 다음 단계 {#dcs-next-steps}

이제 데이터 전송에 익숙한 사용자에게 데이터를 [!UICONTROL DCS]수집하여 해당 정보를 분석할 때입니다. DCS [에서 데이터 받기를 참조하십시오](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).

>[!MORELIKE_THIS]
>
>* [키-값 쌍 설명](../../../reference/key-value-pairs-explained.md)

