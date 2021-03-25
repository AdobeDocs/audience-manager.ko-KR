---
description: 인스턴스 수준 DIL API를 사용하여 프로그래밍 방식으로 Audience Manager 개체를 만들고 사용할 수 있습니다. 인스턴스 수준 메서드는 클래스 수준 메서드로 설정된 API 기능을 개선합니다.
keywords: 트레이트 만들기;트레이트 만들기
seo-description: 인스턴스 수준 DIL API를 사용하여 프로그래밍 방식으로 Audience Manager 개체를 만들고 사용할 수 있습니다. 인스턴스 수준 메서드는 클래스 수준 메서드로 설정된 API 기능을 개선합니다.
seo-title: 인스턴스 수준 DIL 메서드
solution: Audience Manager
title: 인스턴스 수준 DIL 메서드
uuid: aa5147bb-51d5-41d4-a78a-e550f7492056
feature: DIL 구현
translation-type: tm+mt
source-git-commit: e40233ace5cb74743db7d0f9f90707fa596a7e79
workflow-type: tm+mt
source-wordcount: '1111'
ht-degree: 15%

---


# 인스턴스 수준 DIL 메서드{#instance-level-dil-methods}

인스턴스 수준 [!UICONTROL DIL] API를 사용하여 프로그래밍 방식으로 Audience Manager 개체를 만들고 사용할 수 있습니다. 인스턴스 수준 메서드는 클래스 수준 메서드로 설정된 API 기능을 개선합니다.

## 인스턴스 수준 DIL 메서드 시작 {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

인스턴스 수준 [!UICONTROL DIL] API로 작업하는 경우:

* 액세스하려면 파트너 이름과 컨테이너 네임스페이스 ID(NSID)가 필요합니다. 이 정보를 얻으려면 Audience Manager 계정 관리자에게 문의하십시오.
* API 설명서의 샘플 *기울임화된* 텍스트를 작업 중인 메서드에서 요구하는 값, ID 또는 기타 변수로 바꿀 수 있습니다.

<!-- 

c_instance_start.xml

 -->

## signal {#signals}

보류 중인 요청의 쿼리 문자열에 고객 및 플랫폼 수준 매핑을 추가합니다.

<!-- 

r_dil_signals.xml

 -->

**함수 서명:** `signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* 이 메서드에 다른 API 호출을 체인으로 연결할 수 있습니다.
>* Adobe Experience Cloud JavaScript 라이브러리가 페이지에 있는 경우 `submit()` 는 요청을 보내기 전에 클라우드가 쿠키를 설정하기를 기다립니다.


**예약된 요청 키**

다음 요청 키는 예약되어 있으며 이 방법으로 덮어쓸 수 없습니다.

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**매개 변수**

| 이름 | 유형 | 설명 |
|---|---|---|
| `obj` | 개체 | 플랫폼 수준 매핑의 키-값 쌍을 나타내는 객체입니다. 매개 변수는 객체와 배열을 객체의 속성 값으로 허용합니다. |
| `prefix` | 문자열 | 선택 사항입니다. 각 개체 키 앞에 있는 문자열 값(원래 키 대체). |
| `return` | DIL.api | 현재 DIL 인스턴스의 API 개체를 반환합니다. |

**응답**

현재 [!UICONTROL DIL] 인스턴스의 API 개체를 반환합니다.

**샘플 코드**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
}); 
 
// Method 1 
var obj = { key1 : 1, key2 : 2 }; 
dataLib.api.signals(obj, 'c_').submit(); 
 
// Method 2 
dataLib.api.signals({c_zdid: 54321}).submit(); 
 
// Method 3 
// Will send 'c_key=a&c_key=2&c_key=3' to Audience Manager 
var obj = { key : ['a', 'b', 'c'] }; 
dataLib.api.signals(obj, 'c_').submit(); 
</code></pre>

## traits {#traits}

보류 중인 요청의 쿼리 문자열에 SID를 추가합니다.

<!-- 

r_dil_traits.xml

 -->

**함수 서명:** `traits:function (sids){}`

>[!NOTE]
>
>이 메서드에 다른 API 호출을 체인으로 연결할 수 있습니다.

**매개 변수**

| 이름 | 유형 | 설명 |
|---|---|---|
| `sids` | 배열 | 배열에 있는 트레이트 세그먼트 ID입니다. |

**응답**

현재 [!UICONTROL DIL] 인스턴스의 API 개체를 반환합니다.

**샘플 코드**

<pre><code>
var partnerObject = DIL.create({ 
     partner: '<i>partner name</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.traits(<i>[123, 456, 789]</i>); 
</code></pre>

## logs {#logs}

대기 중인 요청에서 로그 파일에 데이터를 추가합니다.

<!-- 

r_dil_logs.xml

 -->

**함수 서명:** `logs: function {key1:value1, key2:value2}`

**응답**

현재 [!UICONTROL DIL] 인스턴스의 API 개체를 반환합니다.

**샘플 코드**

<pre><code>
var partnerObject = DIL.create({ 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.logs({ 
     file: 'dil.js', 
     message: 'This is the first request' 
});
</code></pre>

## 제출 {#submit}

보류 중인 모든 데이터를 [!UICONTROL DIL] 인스턴스에 대한 Audience Manager에 제출합니다.

<!-- 

r_dil_submit.xml

 -->

**함수 서명:** `submit: function () {}`

>[!NOTE]
>
>이 메서드에 다른 API 호출을 체인으로 연결할 수 있습니다. 또한 [!UICONTROL DIL]은(는) 인코딩된 데이터를 대상 쿠키에 씁니다. 예를 들어 공백은 `%20`으로 인코딩되고 세미콜론은 `%3B`로 인코딩됩니다.

**응답**

현재 [!UICONTROL DIL] 인스턴스의 API 개체를 반환합니다.

**샘플 코드**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([ 
<i>123,456, 789</i>]).logs({ 
     file: 'dil.js', 
     message: 'This is the first request' 
}).signals({ 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
}).submit();
</code></pre>

## afterResult {#afterresult}

기본 대상 게시 콜백 이후에 실행되는 함수입니다.

<!-- 

r_dil_after_result.xml

 -->

**함수 서명:** `afterResult: function (fn) {}`

>[!NOTE]
>
>이 메서드에 다른 API 호출을 체인으로 연결할 수 있습니다.

**매개 변수**

| 이름 | 유형 | 설명 |
|---|---|---|
| `fn` | 함수로 플러그인 호출 | 대상 게시를 처리하는 기본 콜백에서 JSON을 처리한 후 실행할 함수입니다. |

**응답**

현재 [!UICONTROL DIL] 인스턴스의 API 개체를 반환합니다.

**샘플 코드**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.signals({ 
     c_zdid: <i>54321</i> 
     d_dma: '<i>default</i>' 
}).afterResult(function(json){ 
     //Do something with the JSON data returned from the server. 
}).submit();
</code></pre>

## clearData {#cleardata}

보류 중인 요청의 모든 데이터를 지웁니다.

<!-- 

r_dil_clear_data.xml

 -->

**함수 서명:** `clearData: function () {}`

>[!NOTE]
>
>이 메서드에 다른 API 호출을 체인으로 연결할 수 있습니다.

**응답**

현재 [!UICONTROL DIL] 인스턴스의 API 개체를 반환합니다.

**샘플 코드**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123,456, 789</i>]).logs({ 
     file: 'dil.js' 
     message: 'This is the first request' 
}).signals({ 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
}); 
 
//Reset the pending data 
dataLib.clearData();
</code></pre>

## customQueryParams {#customqueryparams}

데이터 수집 서버에서 명시적으로 정의되지 않은 사용자 지정 쿼리 매개 변수를 대기 중인 요청에 추가합니다.

<!-- 

r_dil_custom_query_params.xml

 -->

**함수 서명:** `customQueryParams: function (obj) {}`

>[!NOTE]
>
>이 메서드에 다른 API 호출을 체인으로 연결할 수 있습니다.

**예약된 요청 키**

다음 요청 키는 예약되어 있으며 이 방법으로 덮어쓸 수 없습니다.

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**응답**

현재 DIL 인스턴스의 API 개체를 반환합니다.

**샘플 코드**

<pre><code>
var partnerObject = DIL.create({ 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.customQueryParams({ 
     nid: 54231, 
     ntype: 'default' 
}); 
</code></pre>

## getContainerNSID {#getcontainernsid}

[!UICONTROL DIL] 인스턴스에 대한 컨테이너 NSID의 값을 반환합니다. 디버깅 및 문제 해결에 유용합니다.

<!-- 

r_dil_get_container_nsid.xml

 -->

**함수 서명:** `dil.api.getContainerNSID: function () {}`

**샘플 코드**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
//Verify the container NSID 
var nsid = dataLib.api.getContainerNSID();
</code></pre>

## getEventLog {#geteventlog}

시간순으로 정렬된 이벤트 로그 데이터를 문자열 배열로 반환합니다. 디버깅 및 문제 해결에 유용합니다.

<!-- 

r_dil_get_event_log.xml

 -->

**함수 서명:** `dil.api.getEventLog: function () {}`

**샘플 코드**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs({ 
     file: 'dil.js', 
     message: 'This is the first request' 
});.signals({ 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
});.submit(); 
 
//Check log for messages 
var log = dataLib.api.getEventLog(); 
if (log && log.length) { 
     alert(log.join('\n')); 
}else{ 
     alert('No log messages'); 
}
</code></pre>

## getPartner {#getpartner}

[!UICONTROL DIL] 인스턴스의 파트너 이름을 반환합니다. 디버깅 및 문제 해결에 유용합니다.

<!-- 

r_dil_get_partner.xml

 -->

**함수 서명:** `dil.api.getPartner: function () {}`

**샘플 코드**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
}); 
 
//Verify the partner name 
var partner = dataLib.api.getPartner();
</code></pre>

## getState {#getstate}

현재 [!UICONTROL DIL] 인스턴스의 상태를 반환합니다. 디버깅 및 문제 해결에 유용합니다.

<!-- 

r_dil_get_state.xml

 -->

**함수 서명:** `dil.api.getState: function () {}`

**샘플 코드**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs({ 
     file: 'dil.js', 
     message:'This is the first request' 
});.signals({ 
     c.zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
});.submit(); 
 
var state = dataLib.api.getState(); 
 
/*Object outline of state 
state = { 
     pendingRequest: {<i>pending data for call to server</i>}, 
     otherRequestInfo:{ 
          firingQueue: [], 
          fired: [], 
          firing: false, 
          errored: [], 
          reservedKeys: { 
               sids: true, 
               pdata: true, 
               logdata: true, 
               callback: true, 
               postCallbackFn: true, 
               useImageRequest: true, 
          }, 
          firstRequestHasFired: false, 
          num_of_jsonp_responses: 0, 
          num_of_jsonp_errors: 0, 
          num_of_img_responses: 0, 
          num_of_img_errors: 0 
     }, 
     destinationPublishingInfo: { 
          THROTTLE_START: 3000, 
          throttleTimerSet: false, 
          id: ''destination_publishing_iframe_' + partner + '_' + containerNSID, 
          url: (constants.isHTTPS ? 'https://' : 'https://fast.') + partner + '.demdex.net/dest3.html?d_nsid=' 
          + containerNSID + '#' + encodeURIComponent(document.location.href), 
               iframe: null, 
               iframeHasLoaded: false, 
               sendingMessages: false, 
               messages: [], 
               messageSendingInterval: constants.POST_MESSAGE_ENABLED ? 15: 100, 
               //Recommend 100ms for IE 6 & 7, 15ms for other browsers 
               jsonProcessed: [] 
     } 
} 
*/
</code></pre>

## idSync {#idsync}

데이터 파트너가 자신과 Audience Manager 간에 사용자 ID를 교환하고 동기화할 수 있는 2개의 함수로 구성됩니다.

<!-- 

r_dil_idsync.xml

 -->

**함수 서명:**

[!UICONTROL DIL] 버전 2.10 및 3.1 이상에서 작동합니다.

<table id="table_ADC7501511914805A6A6B24B2DFEBA51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 코드 </th> 
   <th colname="col2" class="entry"> 사용자 ID 동기화 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.idSync(initConfig) </code> </td> 
   <td colname="col2"> <p>서로 다른 데이터 파트너와 Audience Manager 간의 관계 예를 들어 파트너 x는 이 변수를 사용하여 파트너 y와 사용자 ID를 동기화한 다음 Audience Manager으로 보냅니다. </p> <p> <p><b>중요: </b>  이 메서드는 사용되지 않습니다. Adobe Experience Platform ID 서비스 인스턴스의 <code> idSyncByURL </code> 메서드를 사용하십시오. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.aamIdSync(initConfig) </code> </td> 
   <td colname="col2"> <p>사용자 ID를 이미 알고 있고 Audience Manager으로 보내려는 경우 </p> <p> <p><b>중요: </b>  이 메서드는 사용되지 않습니다. Adobe Experience Platform ID 서비스 인스턴스의 <code> idSyncByDataSource </code> 메서드를 사용하십시오. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**idSync 요소**

`idSync` 다음 항목으로 구성할 수 있습니다.

<table id="table_5343BE784E694C67B09A0A8878CF8001"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 이름 </th> 
   <th colname="col2" class="entry"> 유형 </th> 
   <th colname="col3" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> dpid </code> </td> 
   <td colname="col2"> 문자열 </td> 
   <td colname="col3"> <p>Audience Manager가 할당한 데이터 제공업체 ID입니다. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> 문자열 </td> 
   <td colname="col3"> <p>사용자에 대한 데이터 제공업체의 고유한 ID입니다. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> minutesToLive </code> </td> 
   <td colname="col2"> 숫자 </td> 
   <td colname="col3"> <p><i>(선택 사항)</i> 쿠키 만료 시간을 설정하며 정수여야 합니다. 기본값은 20160분(14일)입니다. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> url </code> </td> 
   <td colname="col2"> 문자열 </td> 
   <td colname="col3"> <p>대상 URL. </p> </td> 
  </tr> 
 </tbody> 
</table>

**매크로**

`idSync` 다음 매크로를 허용합니다.

* **`%TIMESTAMP%`:** 타임스탬프를 생성합니다(밀리초 단위). 캐시 무효화에 사용됩니다.
* **`%DID%`:** 사용자의 Audience Manager ID를 삽입합니다.
* **`%HTTP_PROTO%`:** 페이지 프로토콜(  `http` 또는  `https`)을 설정합니다.

**응답**

두 함수 모두 성공한 경우 `Successfully queued`을 반환합니다. 실패한 경우 오류 메시지 문자열을 반환합니다.

**샘플 코드**

`dilInstance.api.idSync(initConfig)`

<pre><code class="js">
// Fires url with macros replaced 
dilInstance.api.idSync({ 
 dpid: '23', // must be a string 
 url: '//su.addthis.com/red/usync?pid=16&puid=%DID%&url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net 
%2Fibs%3Adpid%3D420%26dpuuid%3D%7B%7Buid%7D%7D', 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
});
</code></pre>

`dilInstance.api.aamIdSync(initConfig)`

<pre><code class="js">
// Fires 'https:/https:' + '//dpm.demdex.net/ibs:dpid=&lt;dpid&gt;&dpuuid=&lt;dpuuid&gt;' 
dilInstance.api.aamIdSync({ 
 dpid: '23', // must be a string 
 dpuuid: '98765', // must be a string 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
});
</code></pre>

## result {#result}

보류 중인 요청에 콜백(JSON을 수신하는)을 추가합니다.

<!-- 

r_dil_result.xml

 -->

**함수 서명:** `result: function (callback) {}`

이 콜백은 대상 게시를 처리하는 기본 콜백을 대체합니다.

>[!NOTE]
>
>이 메서드에 다른 API 호출을 체인으로 연결할 수 있습니다.

**매개 변수**

| 이름 | 유형 | 설명 |
|---|---|---|
| `callback` | 함수로 플러그인 호출 | JSONP 콜백에서 실행되는 JavaScript 함수입니다. |

**응답**

현재 [!UICONTROL DIL] 인스턴스의 API 개체를 반환합니다.

**샘플 코드**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).result(function(json){ 
     //Do something, possibly with the JSON data returned from the server. 
});.submit();
</code></pre>

## secureDataCollection {#securedatacollection}

`secureDataCollection` 는 및 Akamai에 대한  [!UICONTROL DIL] 호출 방법을 제어하는 부울  [!UICONTROL Data Collection Servers (DCS)] 매개 변수입니다.

<!-- 

dil-secure-data-collection.xml

 -->

* `secureDataCollection= true`(기본값)에서는 [!UICONTROL DIL]이 항상 안전한 HTTPS 호출을 수행합니다.

* `secureDataCollection= false`이(가) 페이지에서 설정한 보안 프로토콜을 따라 [!UICONTROL DIL]이 HTTP 또는 HTTPS 호출을 만듭니다.

>[!IMPORTANT]
>
>동일한 페이지에서 visitorAPI.js와 [!UICONTROL DIL]을 사용하는 경우 `secureDataCollection= false`을 설정합니다. 아래 코드 샘플을 참조하십시오.

<pre><code class="js">
var dilInstance = DIL.create({ 
     ... 
     secureDataCollection: false 
});
</code></pre>

## useCORSOnly {#usecorsonly}

`useCORSOnly` 브라우저가 다른 도메인의 리소스를 요청하는 방법을 제어하는 부울 true/false 매개 변수입니다.

<!-- 

dil-use-cors-only.xml

 -->

**개요**

`useCORSOnly` 은 기본적으로 false입니다. False는 브라우저가 CORS 또는 JSONP로 리소스 검사를 수행할 수 있음을 의미합니다. 그러나 [!UICONTROL DIL]은 항상 CORS가 있는 리소스를 먼저 요청하려고 합니다. ID 서비스는 CORS를 지원하지 않는 오래된 브라우저에서는 JSONP로 되돌립니다. 높은 보안 요구 사항이 있는 사이트와 같이 브라우저가 CORS만 사용하도록 강제해야 하는 경우 `useCORSOnly:true`을 설정합니다.

**코드 샘플**

<pre><code class="js">
var dilInstance = DIL.create({ 
     ... 
     useCORSOnly: true 
});
</code></pre>

>[!IMPORTANT]
>
>* 사이트 방문자에게 이 기능을 지원하는 브라우저가 있는 경우에만 `useCORSOnly: true`을 설정하는 것이 좋습니다.
>* `useCORSOnly: true`이면 [!UICONTROL DIL]은(는) Internet Explorer 버전 9 이상에서 ID 호출을 하지 않습니다.

>



## useImageRequest {#useimagerequest}

요청 유형을 `<src>` 스크립트에서 `<img>` 이미지로 변경합니다.

<!-- 

r_dil_use_image_request.xml

 -->

**함수 서명:** `useImageRequest: function () {}`

>[!NOTE]
>
>이 메서드에 다른 API 호출을 체인으로 연결할 수 있습니다.

**응답**

현재 [!UICONTROL DIL] 인스턴스의 API 개체를 반환합니다.

**샘플 코드**

<pre><code>
var dataLib = DIL.create({ 
     partner:'<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).useImageRequest().submit();
</code></pre>

>[!MORELIKETHIS]
>
>* [주요 변수의 이름 요구 사항](../features/traits/trait-key-name-requirements.md)
>* [주요 변수의 접두사 요구 사항](../features/traits/trait-variable-prefixes.md)
>* [Adobe Experience Platform Identity Service의 동기화 함수](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/idsync.html)
>* [DIL 만들기](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Adobe Experience Platform ID 서비스:UseSOnly](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/use-cors-only.html)
>* [Adobe Experience Platform ID 서비스의 CORS 지원](https://docs.adobe.com/content/help/en/id-service/using/reference/cors.html)

