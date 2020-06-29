---
description: DCS에 대한 /event 호출을 만드는 방법에 대한 자세한 내용은 여기에서 시작합니다. 이 섹션에는 호출 구문, 매개 변수, 형식 지정 및 요청 예에 대한 정보가 포함되어 있습니다.
seo-description: DCS에 대한 /event 호출을 만드는 방법에 대한 자세한 내용은 여기에서 시작합니다. 이 섹션에는 호출 구문, 매개 변수, 형식 지정 및 요청 예에 대한 정보가 포함되어 있습니다.
seo-title: DCS에 데이터 보내기
solution: Audience Manager
title: DCS에 데이터 보내기
uuid: 024e307d-bfcb-46cf-ac3a-fc71df0248fe
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 6%

---


# DCS에 데이터 보내기 {#send-data-to-the-dcs}

전화 거는 방법에 대한 자세한 내용은 여기에서 `/event` 시작하십시오 [!DNL DCS]. 이 섹션에는 호출 구문, 매개 변수, 형식 지정 및 요청 예에 대한 정보가 포함되어 있습니다.

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. 이 방법으로 데이터를 보낼 때 자리 표시자의 실제 값 [!DNL DCS] 으로 대체하십시오.

## 호출 구문 {#dcs-call-syntax}

데이터를 로 전송하는 기본 `URL` 문자열은 아래 [!DNL DCS] 와 같은 구문을 사용합니다.

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

>[!NOTE]
>
>메서드를 사용하여 데이터를 [!DNL DCS] 로 보낼 수도 `POST` 있습니다. 호출 구문은 [DCS API 메서드에서 설명합니다](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md).

## 호출 매개 변수 {#dcs-call-parameters}

다음 표에서는 간단한 [!DNL DCS] 호출의 기본 구성 요소를 정의합니다.

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
   <td colname="col2"> <p>호출의 이 부분에는 다음이 포함됩니다. </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Audience Manager에 의해 <span class="keyword"> 할당된 도메인</span> 별칭(예: <code> my_domain.demdex.net</code>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">항상 대상 도메인입니다 <code> demdex.net</code>. <a href="../../../reference/demdex-calls.md">Demdex 도메인에 대한 호출 이해</a>를 참조하십시오. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /event?</code> </p> </td> 
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
   <td colname="col2"> <p>키-값 쌍에서 키에 의해 정의된 세트에 속하는 변수 값. </p> <p>값 작업 시: </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">문자열 데이터를 큰 따옴표(예: )로 묶습니다 <code> age="41 to 55"</code>. </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">여러 키를 하나의 값(예: )에 전달할 수 <i><code>key</i>=<i>val1,val2,val3</i></code></i>있습니다. </li> 
     </ul> </p> <p>See <a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md"> Formatting Key-Value Pairs in DCS Calls</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_cb=<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>선택적 응답 매개 변수입니다. </p> <p> DCS로 데이터를 전송할 필요가 <span class="wintitle"> 없습니다</span>. 그러나 DCS에서 응답을 <span class="wintitle"> 반환하려면</span> 요청에 <code> d_rtbd=json</code> 포함해야 합니다. </p> <p>정의된 <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> _ 키-값 쌍을 참조하십시오</a>. </p> </td> 
  </tr>
 </tbody>
</table>

## 샘플 호출 {#dcs-sample-call}

이 예는 가상 회사에서 [!DNL Acme, Inc.] 호출을 통해 데이터를 [!DNL DCS] 전송하는 것을 보여줍니다 [!DNL HTTP] . 이 호출에는 선택적 매개 변수, 매개 변수 `d_dst=1``d_rtbd=json`및 `d_cb=callback`가 포함됩니다. 이것은 호출 [!DNL Acme] 백 기능이 있는 [!DNL JSON] 응답으로부터 수신하려고 [!DNL DCS] 함을 나타냅니다. 기억하십시오, 이것은 단지 예시입니다. 이 코드를 잘라내 붙여 넣지 마십시오.

```js
https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback
```

## 다음 단계 {#dcs-next-steps}

이제 데이터를 전송에 익숙한 사용자에게 [!DNL DCS]데이터를 수집하여 해당 정보를 분석할 차례입니다. See [Receive Data From the DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).

>[!MORELIKETHIS]
>
>* [키-값 쌍 설명](../../../reference/key-value-pairs-explained.md)

