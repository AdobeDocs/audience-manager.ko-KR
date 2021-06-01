---
description: DCS에 대한 /event 호출 방법에 대해서는 여기에서 시작하십시오. 이 섹션에는 호출 구문, 매개 변수, 형식 지정 및 요청 예에 대한 정보가 포함되어 있습니다.
seo-description: DCS에 대한 /event 호출 방법에 대해서는 여기에서 시작하십시오. 이 섹션에는 호출 구문, 매개 변수, 형식 지정 및 요청 예에 대한 정보가 포함되어 있습니다.
seo-title: DCS에 데이터 보내기
solution: Audience Manager
title: DCS에 데이터 보내기
uuid: 024e307d-bfcb-46cf-ac3a-fc71df0248fe
feature: DCS
exl-id: 8a6798c3-aafd-48c8-acd7-a0e29e04dc8e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 6%

---

# DCS에 데이터 보내기 {#send-data-to-the-dcs}

[!DNL DCS] 호출을 수행하는 방법에 대한 자세한 내용은 여기에서 시작하십시오. `/event` 이 섹션에는 호출 구문, 매개 변수, 형식 지정 및 요청 예에 대한 정보가 포함되어 있습니다.

>[!NOTE]
>
>코드 및 예에서 *기울임꼴*&#x200B;은 변수 자리 표시자를 나타냅니다. 이 메서드를 사용하여 [!DNL DCS]에 데이터를 보낼 때 자리 표시자의 실제 값을 바꿉니다.

## 호출 구문 {#dcs-call-syntax}

[!DNL DCS]에 데이터를 전송하는 기본 `URL` 문자열은 아래 표시된 구문을 사용합니다.

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

>[!NOTE]
>
>`POST` 메서드를 사용하여 데이터를 [!DNL DCS]에 보낼 수도 있습니다. 호출 구문은 [DCS API 메서드](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)에 설명되어 있습니다.

## 호출 매개 변수 {#dcs-call-parameters}

다음 표에서는 단순 [!DNL DCS] 호출의 기본 구성 요소를 정의합니다.

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
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9"><span class="keyword"> Audience Manager</span>(예: <code> my_domain.demdex.net</code>)에서 지정한 도메인 별칭입니다. </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">항상 <code> demdex.net</code>인 대상 도메인입니다. <a href="../../../reference/demdex-calls.md">Demdex 도메인에 대한 호출 이해</a>를 참조하십시오. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /event?</code> </p> </td> 
   <td colname="col2"> <p>호출의 이 부분: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">호출을 이벤트 호출로 식별합니다. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198"><span class="wintitle"> DCS</span>에 전송할 데이터가 포함된 URL 문자열의 시작을 정의합니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> key</code> </p> </td> 
   <td colname="col2"> <p>키-값 쌍의 고유 식별자입니다. </p> <p>이러한 키-값 쌍은 특정 접두사를 사용하여 <span class="wintitle"> DCS</span>에 전송하는 데이터 유형을 식별합니다. 자세한 내용은 <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> DCS API 호출에 지원되는 특성</a>을 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>키-값 쌍에서 키로 정의한 집합에 속하는 변수 값입니다. </p> <p>값 작업 시: </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">문자열 데이터를 큰 따옴표(예: <code> age="41 to 55"</code>)로 묶습니다. </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">여러 키를 하나의 값(예: <i><code>key</i>=<i>val1,val2,val3</i></code></i>)에 전달할 수 있습니다. </li> 
     </ul> </p> <p>DCS 호출에서 <a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md"> 키-값 쌍 형식 지정</a>을 참조하십시오. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_cb=<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>선택적 응답 매개 변수. </p> <p> 이 중 어느 것도 <span class="wintitle"> DCS</span>에 데이터를 보낼 필요가 없습니다. 그러나 <span class="wintitle"> DCS</span>에서 응답을 반환하려면 요청에 <code> d_rtbd=json</code>를 포함해야 합니다. </p> <p><a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> d_ Key-Value Pairs Defined</a>를 참조하십시오. </p> </td> 
  </tr>
 </tbody>
</table>

## 샘플 호출 {#dcs-sample-call}

이 예는 [!DNL HTTP] 호출을 통해 [!DNL DCS]에 데이터를 전송하는 가상의 회사 [!DNL Acme, Inc.]를 보여줍니다. 이 호출에는 선택적 매개 변수 `d_dst=1`, `d_rtbd=json` 및 `d_cb=callback`가 포함됩니다. 즉, [!DNL Acme]이 [!DNL DCS]에서 호출 백 함수와 함께 [!DNL JSON] 응답을 수신하려고 합니다. 기억하십시오, 이것은 단지 하나의 예일 뿐입니다. 이 코드를 잘라내어 붙여 넣지 마십시오.

```js
https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback
```

## 다음 단계 {#dcs-next-steps}

이제 [!DNL DCS]에 데이터를 전송하는 것에 익숙하므로 데이터를 다시 가져와서 해당 정보를 구문 분석하는 방법을 살펴볼 차례입니다. [DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md)에서 데이터 받기 를 참조하십시오.

>[!MORELIKETHIS]
>
>* [키-값 쌍 설명](../../../reference/key-value-pairs-explained.md)

