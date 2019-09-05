---
description: DCS로 /event 호출을 하는 방법에 대한 자세한 내용은 여기를 시작합니다. 이 섹션에는 호출 구문, 매개 변수, 서식 및 요청 예제에 대한 정보가 포함되어 있습니다.
seo-description: DCS로 /event 호출을 하는 방법에 대한 자세한 내용은 여기를 시작합니다. 이 섹션에는 호출 구문, 매개 변수, 서식 및 요청 예제에 대한 정보가 포함되어 있습니다.
seo-title: DCS로 데이터 전송
solution: Audience Manager
title: DCS로 데이터 전송
uuid: 024 e 307 d-bfcb -46 cf-ac 3 a-fc 71 df 0248 fe
translation-type: tm+mt
source-git-commit: bc2a9364b771436fe0191f9d69a8c291563f9229

---


# DCS로 데이터 전송 {#send-data-to-the-dcs}

에 `/event` 대한 전화 걸기 정보를 보려면 여기를 시작합니다 [!UICONTROL DCS]. 이 섹션에는 호출 구문, 매개 변수, 서식 및 요청 예제에 대한 정보가 포함되어 있습니다.

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. 이 방법으로 데이터를 보낼 [!UICONTROL DCS] 때 자리 표시자에 대한 실제 값을 대체합니다.

## 호출 구문 {#dcs-call-syntax}

에 데이터를 보내는 기본 `URL` 문자열은 아래와 같이 구문을 [!UICONTROL DCS] 사용합니다.

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

>[!NOTE]
>
>메서드를 사용하여 데이터를으로 [!UICONTROL DCS] 보낼 `POST` 수도 있습니다. 호출 구문은 [DCS API 메서드에서 설명합니다](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md).

## 호출 매개 변수 {#dcs-call-parameters}

다음 표는 간단한 호출의 기본 구성 요소를 정의합니다 [!UICONTROL DCS] .

<table id="table_5F6A5B324EB848168543386516FBF384"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 구성 요소 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> domain alias. demdex. net</code> </p> </td> 
   <td colname="col2"> <p>호출의 이 부분에는 다음이 포함됩니다. </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Audience Manager에서 <span class="keyword"> 할당한 도메인 별칭</span> (예: <code> my_ domain. demdex. net</code>) </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">항상 <code> demdex. net</code>인 대상 도메인입니다. <a href="../../../reference/demdex-calls.md">Demdex 도메인에 대한 호출 이해</a>를 참조 하십시오. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /이벤트에 연결된다는 점을 이용합니다?</code> </p> </td> 
   <td colname="col2"> <p>호출의 다음 부분: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">호출을 이벤트 호출로 식별합니다. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">DCS로 전송할 데이터를 포함하는 URL 문자열의 시작을 <span class="wintitle"> 정의합니다</span>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> key</code> </p> </td> 
   <td colname="col2"> <p>키-값 쌍의 고유 식별자. </p> <p>이러한 키-값 쌍은 특정 접두사를 사용하여 <span class="wintitle"> DCS</span>로 보내는 데이터 유형을 식별합니다. For more information, see <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Supported Attributes for DCS API Calls</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>키-값 쌍의 키에 의해 정의된 세트에 속하는 변수 값. </p> <p>값을 사용하여 작업하는 경우: </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">문자열 데이터를 큰 따옴표로 묶습니다 (예: <code> age = "41 ~ 55"</code>). </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">단일 값 (예: <i><code>key</i>=<i>val 1, val 2, val 3</i></code></i>) 에 여러 키를 전달할 수 있습니다. </i></li> 
     </ul> </p> <p>DCS 호출에서 키-값 쌍 <a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md"> 지정을 참조하십시오</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_ dst = 1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_ rtbd = json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_ cb =<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>선택적 응답 매개 변수. </p> <p> <span class="wintitle"> DCS</span>로 데이터를 전송할 필요가 없습니다. <span class="wintitle"> DCS</span> 에서 응답을 반환하려면 요청에 <code> d_ rtbd = json</code> 를 포함해야 합니다. </p> <p><a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> 정의된 d_ key-value 쌍을 참조하십시오</a>. </p> </td> 
  </tr>
 </tbody>
</table>

## 샘플 호출 {#dcs-sample-call}

이 예는 전화로 데이터를 [!DNL Acme, Inc.] 전송하는 가상 회사를 [!UICONTROL DCS][!DNL HTTP] 보여줍니다. 이 호출에는 선택적 매개 변수 `d_dst=1`, `d_rtbd=json`및이 포함되어 `d_cb=callback`있습니다. 이것은 콜백 [!DNL Acme] 기능을 사용하여 로부터 [!DNL JSON] 응답을 [!UICONTROL DCS] 받으려는 것을 나타냅니다. 이것은 단지 한 예입니다. 이 코드를 잘라내지 마십시오.

```js
https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback
```
## 다음 단계 {#dcs-next-steps}

이제 데이터 전송에 익숙하다면 데이터를 [!UICONTROL DCS]다시 보고 해당 정보를 분석하는 방법을 살펴볼 차례입니다. DCS에서 데이터 [받기를 참조하십시오](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).

>[!MORE_ like_ this]
>
>* [키-값 쌍을 설명했습니다.](../../../reference/key-value-pairs-explained.md)

