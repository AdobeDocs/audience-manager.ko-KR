---
description: DIL에서 Adobe Experience Cloud Device Co-op로 데이터를 전송하거나 전송하지 않는지 여부를 결정하는 선택적 부울 구성입니다.
seo-description: DIL에서 Adobe Experience Cloud Device Co-op로 데이터를 전송하거나 전송하지 않는지 여부를 결정하는 선택적 부울 구성입니다.
seo-title: isCoopSafe
solution: Audience Manager
title: isCoopSafe
uuid: c5362a38-93c0-4edb-bdcb-106e43f33a92
translation-type: tm+mt
source-git-commit: 92751df14777335744db69bfb0c9b7b2f9088785
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 76%

---


# isCoopSafe{#iscoopsafe}

DIL에서 Adobe Experience Cloud Device Co-op로 데이터를 전송하거나 전송하지 않는지 여부를 결정하는 선택적 부울 구성입니다.

## 요구 사항 {#requirements}

To use `isCoopSafe` you must:

* v6. [!UICONTROL DIL] 11 이상을 사용하십시오.
* [Experience Cloud 장치 Co-op](https://docs.adobe.com/content/help/en/device-co-op/using/home.html)에 참여합니다. 예상 Co-op 구성원은 이 설명서를 검토하여 `isCoopSafe`가 데이터 사용하여 장치 그래프를 생성하는 방법으로 인해 발생할 수 있는 문제를 해결하는지 확인해야 합니다.

* Work with your [!DNL Adobe] consultant to set an allowlist or a denylist flag on your Device Co-op account. 이러한 플래그를 활성화할 셀프 서비스 경로가 없습니다.

## 사용 사례 {#use-cases}

`isCoopSafe`는 장치 Co-op의 현재 또는 예상 멤버의 데이터 수집과 관련된 2가지 사용 사례를 해결하는 데 도움이 됩니다. 이러한 사용 사례는 장치 그래프를 작성하는 데 도움이 되도록 사이트 방문자 데이터를 장치 Co-op에 전달하는 방식에 대한 것입니다. 다음 표에서는 `isCoopSafe`를 이러한 사용 사례에서 사용하여 데이터를 장치 그래프로 보내거나 차단하는 방법을 설명합니다.

<table id="table_A24C63D2A21F47EDBAC8FA5E7BE888D8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 사용 사례 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>인증된 방문자</b> </p> </td> 
   <td colname="col2"> <p>Add <code> isCoopSafe </code> to your <span class="wintitle"> DIL </span> code to control how data for authenticated visitors who have or have not accepted term-of-use agreements is used by the Device Co-op to build the device graph. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> </b>타사 사이트의 DIL<b> </b></p> </td> 
   <td colname="col2"> <p>Add <code> isCoopSafe </code> to your <span class="wintitle"> DIL </span> code for use on third-party sites where you: </p> <p> 
     <ul id="ul_C27BB26510314834A2A7CD99D46DA4AC"> 
      <li id="li_4E6AE574F18646F09C0CF4553EEA1A9E">인증된 방문자가 사용 약관에 동의하거나 동의하지 않았는지 확인할 수 없습니다. </li> 
      <li id="li_26D0561BF32B4278B0A6B5082C17FED8">장치 그래프를 작성하기 위해 장치 Co-op에서 데이터를 사용하는 방법을 제어해야 합니다. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 구문 및 코드 샘플 {#syntax-code-sample}

**구문:** `isCoopSafe: true | false`

부울 옵션은 장치 Co-op에서 고객 데이터를 사용하거나 사용하지 않는 방법을 결정합니다.

* `isCoopSafe: true`: 모바일 SDK 또는 웹 사이트에서 수집한 방문자 데이터를 사용하여 장치 그래프를 작성&#x200B;*할 수 있습니다*.

* `isCoopSafe: false`: 모바일 SDK 또는 웹 사이트에서 수집한 방문자 데이터를 사용하여 장치 그래프를 작성&#x200B;*할 수 없습니다*.

**코드 샘플**

DIL이 인스턴스화할 때 설정합니다.

```js
var dilInstance = DIL.create({ 
     ... 
     isCoopSafe: true 
});
```

## 이벤트 호출 POST 매개 변수 {#post-parameters}

Depending on the flag you set ( `true` or `false`), [!UICONTROL DIL] translates `isCoopSafe` into these POST parameters and sends them to [!DNL Adobe] in an event call:

* `d_coop_safe=1`
* `d_coop_unsafe=1`

POST 매개 수는 장치 그래프에 사용자 데이터를 포함할 수 있는지 여부를 [!DNL Experience Cloud] 장치 Co-op에 알립니다. 아래 표에서는 이벤트 호출 시 전달된 POST 매개 변수와 `isCoopSafe` 부울 플래그 간의 관계를 정의합니다. `isCoopSafe`를 사용하지 않는 경우에는 이벤트 호출 시 아무 것도 전달되지 않습니다.

<table id="table_0A544534CA904F4D9836A34B8C1EACBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 구성 상태 </th> 
   <th colname="col2" class="entry"> POST 매개 변수 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> isCoopSafe: true </code> </p> </td> 
   <td colname="col2"> <p> <code> d_coop_safe=1 </code> </p> <p>Co-op 장치에서 방문자 데이터를 사용하여 장치 그래프를 작성할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> isCoopSafe: false </code> </p> </td> 
   <td colname="col2"> <p> <code> d_coop_unsafe=1 </code> </p> <p>Co-op 장치에서 방문자 데이터를 사용하여 장치 그래프를 작성할 수 없습니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 사후 인스턴스화 API {#post-instantiation}

이러한 API를 사용하면 `isCoopSafe` 상태를 재정의할 수 있습니다. 이러한 API는 페이지를 새로 고치지 않은 단일 페이지 앱 또는 사이트에서 방문자의 사후 인스턴스화/사후 로그인 상태를 변경할 수 있으므로 필요합니다. 예를 들어 사용자가 사이트 또는 앱을 인증하고, 장치 Co-op에서 해당 데이터를 사용할 수 있도록 하는 사용 약관 정책에 나중에 동의하는 경우 이러한 API를 호출해야 합니다.

<table id="table_BAA96B1F82BE48C3A61A1AF1367BA45C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance.api.setAsCoopSafe(); </code> </p> </td> 
   <td colname="col2"> <p>Sets POST parameter <code> d_coop_safe=1 </code> in all subsequent event calls. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance.api.setAsCoopUnsafe(); </code> </p> </td> 
   <td colname="col2"> <p>Sets POST parameter <code> d_coop_unsafe=1 </code> in all subsequent event calls. </p> </td> 
  </tr> 
 </tbody> 
</table>

<!-- 

Wiki page https://wiki.corp.adobe.com/x/RCfFTg

 -->

