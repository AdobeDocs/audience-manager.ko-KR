---
description: 인스턴스 수준 DIL API를 사용하면 Audience Manager 개체를 프로그래밍 방식으로 만들고 작업할 수 있습니다. 인스턴스 수준 메서드는 클래스 수준 메서드에서 설정한 API 기능을 향상시킵니다.
keywords: 트레이트 만들기;트레이트 만들기
seo-description: The instance-level DIL APIs let you programmatically create and work with Audience Manager objects. The instance-level methods enhance API functionality established by the class-level methods.
seo-title: Instance-level DIL Methods
solution: Audience Manager
title: 인스턴스 수준 DIL 메서드
uuid: aa5147bb-51d5-41d4-a78a-e550f7492056
feature: DIL Implementation
exl-id: 0342439d-708e-461c-b155-a3ee423f5437
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '1153'
ht-degree: 14%

---

# 인스턴스 수준 DIL 메서드{#instance-level-dil-methods}

>[!WARNING]
>
>2023년 7월부터 Adobe은 의 개발을 중단했습니다. [!DNL Data Integration Library (DIL)] 및 [!DNL DIL] 확장명.
>
>기존 고객은 [!DNL DIL] 구현. 그러나 Adobe은 개발되지 않습니다 [!DNL DIL] 이 점을 넘어서는 것입니다. 고객은 다음을 평가하는 것이 좋습니다. [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 을 참조하십시오.
>
>2023년 7월 이후 새로운 데이터 수집 통합을 구현하려는 고객은 [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 대신,

인스턴스 수준 [!UICONTROL DIL] API를 사용하면 프로그래밍 방식으로 Audience Manager 개체를 만들고 작업할 수 있습니다. 인스턴스 수준 메서드는 클래스 수준 메서드에서 설정한 API 기능을 향상시킵니다.

## 인스턴스 수준 DIL 메서드 시작 {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

인스턴스 수준 작업 시 [!UICONTROL DIL] API:

* 액세스하려면 파트너 이름과 컨테이너 네임스페이스 ID(NSID)가 필요합니다. 이 정보를 얻으려면 Audience Manager 계정 관리자에게 문의하십시오.
* 모든 샘플 바꾸기 *기울임꼴* 작업 중인 메서드에 필요한 값, ID 또는 기타 변수가 있는 API 설명서의 텍스트입니다.

<!-- 

c_instance_start.xml

 -->

## 신호 {#signals}

고객 및 플랫폼 수준 매핑을 보류 중인 요청의 쿼리 문자열에 추가합니다.

<!-- 

r_dil_signals.xml

 -->

**함수 서명:** `signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* 이 메서드에 다른 API 호출을 연결할 수 있습니다.
>* Adobe Experience Cloud JavaScript 라이브러리가 페이지에 있는 경우, `submit()` 는 클라우드가 요청을 보내기 전에 쿠키를 설정할 때까지 기다립니다.

**예약된 요청 키**

다음 요청 키는 예약되어 있으며 이 메서드로 덮어쓸 수 없습니다.

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**매개 변수**

| 이름 | 유형 | 설명 |
|---|---|---|
| `obj` | 개체 | 플랫폼 수준 매핑의 키-값 쌍을 나타내는 개체입니다. 매개 변수는 문자열 및 배열을 개체의 속성 값으로 허용합니다. |
| `prefix` | 문자열 | 선택 사항입니다. 각 개체 키 접두사가 있는 문자열 값(원래 키를 대체). |
| `return` | DIL.api | 현재 DIL 인스턴스의 API 개체를 반환합니다. |

**응답**

현재 의 API 개체 반환 [!UICONTROL DIL] 인스턴스.

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
>이 메서드에 다른 API 호출을 연결할 수 있습니다.

**매개 변수**

| 이름 | 유형 | 설명 |
|---|---|---|
| `sids` | 배열 | 배열의 트레이트 세그먼트 ID. |

**응답**

현재 의 API 개체 반환 [!UICONTROL DIL] 인스턴스.

**샘플 코드**

<pre><code>
var partnerObject = DIL.create({ 
     partner: '<i>partner name</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.traits(<i>[123, 456, 789]</i>); 
</code></pre>

## 로그 {#logs}

보류 중인 요청의 로그 파일에 데이터를 추가합니다.

<!-- 

r_dil_logs.xml

 -->

**함수 서명:** `logs: function {key1:value1, key2:value2}`

**응답**

현재 의 API 개체 반환 [!UICONTROL DIL] 인스턴스.

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

보류 중인 모든 데이터를 다음에 대한 Audience Manager으로 제출 [!UICONTROL DIL] 인스턴스.

<!-- 

r_dil_submit.xml

 -->

**함수 서명:** `submit: function () {}`

>[!NOTE]
>
>이 메서드에 다른 API 호출을 연결할 수 있습니다. 또한, [!UICONTROL DIL] 인코딩된 데이터를 대상 쿠키에 씁니다. 예를 들어 공백은 로 인코딩됩니다. `%20` 및 세미콜론으로 `%3B`.

**응답**

현재 의 API 개체 반환 [!UICONTROL DIL] 인스턴스.

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

기본 대상 게시 콜백 후에 실행되는 함수입니다.

<!-- 

r_dil_after_result.xml

 -->

**함수 서명:** `afterResult: function (fn) {}`

>[!NOTE]
>
>이 메서드에 다른 API 호출을 연결할 수 있습니다.

**매개 변수**

| 이름 | 유형 | 설명 |
|---|---|---|
| `fn` | 함수로 플러그인 호출 | JSON 후에 실행할 함수는 대상 게시를 처리하는 기본 콜백에 의해 처리됩니다. |

**응답**

현재 항목의 API 개체 반환 [!UICONTROL DIL] 인스턴스.

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
>이 메서드에 다른 API 호출을 연결할 수 있습니다.

**응답**

현재 의 API 개체 반환 [!UICONTROL DIL] 인스턴스.

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

데이터 수집 서버에서 명시적으로 정의하지 않은 사용자 지정 쿼리 매개 변수를 보류 중인 요청에 추가합니다.

<!-- 

r_dil_custom_query_params.xml

 -->

**함수 서명:** `customQueryParams: function (obj) {}`

>[!NOTE]
>
>이 메서드에 다른 API 호출을 연결할 수 있습니다.

**예약된 요청 키**

다음 요청 키는 예약되어 있으며 이 메서드로 덮어쓸 수 없습니다.

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

다음에 대한 컨테이너 NSID 값 반환: [!UICONTROL DIL] 인스턴스. 디버깅 및 문제 해결에 유용합니다.

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

연대순으로 정렬된 이벤트 로그 데이터를 문자열 배열로 반환합니다. 디버깅 및 문제 해결에 유용합니다.

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

에 대한 파트너 이름을 반환합니다. [!UICONTROL DIL] 인스턴스. 디버깅 및 문제 해결에 유용합니다.

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

현재 상태를 반환합니다. [!UICONTROL DIL] 인스턴스. 디버깅 및 문제 해결에 유용합니다.

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

데이터 파트너가 사용자와 Audience Manager 간에 사용자 ID를 교환하고 동기화할 수 있는 두 가지 기능으로 구성됩니다.

<!-- 

r_dil_idsync.xml

 -->

**함수 서명:**

와 함께 작동 [!UICONTROL DIL] 버전 2.10 및 3.1 이상.

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
   <td colname="col2"> <p>다양한 데이터 파트너와 Audience Manager 간 예를 들어 파트너 x는 이 기능을 사용하여 Audience Manager ID를 파트너 y와 동기화한 다음 사용자에게 보냅니다. </p> <p> <p><b>중요 사항:</b>  이 메서드는 더 이상 사용되지 않습니다. 다음을 사용하십시오. <code> idSyncByURL </code> Adobe Experience Platform Identity 서비스 인스턴스의 메서드입니다. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.aamIdSync(initConfig) </code> </td> 
   <td colname="col2"> <p>Audience Manager ID를 이미 알고 있고 사용자에게 보내고자 하는 경우. </p> <p> <p><b>중요 사항:</b>  이 메서드는 더 이상 사용되지 않습니다. 다음을 사용하십시오. <code> idSyncByDataSource </code> Adobe Experience Platform Identity 서비스 인스턴스의 메서드입니다. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**idSync 요소**

`idSync` 는 다음과 같이 구성할 수 있습니다.

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

`idSync` 은 다음 매크로를 허용합니다.

* **`%TIMESTAMP%`:** 타임스탬프를 생성합니다(밀리초 단위). 캐시 무효화에 사용됩니다.
* **`%DID%`:** 사용자의 Audience Manager ID를 삽입합니다.
* **`%HTTP_PROTO%`:** 페이지 프로토콜( `http` 또는 `https`).

**응답**

두 함수 모두 반환 `Successfully queued` 성공하면 실패한 경우 오류 메시지 문자열을 반환합니다.

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

## 결과 {#result}

JSON을 수신하는 콜백을 보류 중인 요청에 추가합니다.

<!-- 

r_dil_result.xml

 -->

**함수 서명:** `result: function (callback) {}`

이 콜백은 대상 게시를 처리하는 기본 콜백을 대체합니다.

>[!NOTE]
>
>이 메서드에 다른 API 호출을 연결할 수 있습니다.

**매개 변수**

| 이름 | 유형 | 설명 |
|---|---|---|
| `callback` | 함수로 플러그인 호출 | JSONP 콜백에서 실행되는 JavaScript 함수입니다. |

**응답**

현재 의 API 개체 반환 [!UICONTROL DIL] 인스턴스.

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

## 보안 데이터 수집 {#securedatacollection}

`secureDataCollection` 는 방법을 제어하는 부울 매개 변수입니다 [!UICONTROL DIL] 을(를) 호출합니다. [!UICONTROL Data Collection Servers (DCS)] 그리고 Akamai.

<!-- 

dil-secure-data-collection.xml

 -->

* 날짜 `secureDataCollection= true` (기본값), [!UICONTROL DIL] 은 항상 보안 HTTPS 호출을 수행합니다.

* 날짜 `secureDataCollection= false`, [!UICONTROL DIL] 페이지에서 설정한 보안 프로토콜을 따라 HTTP 또는 HTTPS를 호출합니다.

>[!IMPORTANT]
>
>설정 `secureDataCollection= false` visitorAPI.js 및 [!UICONTROL DIL] 같은 페이지에서. 아래 코드 샘플을 참조하십시오.

<pre><code class="js">
var dilInstance = DIL.create({ 
     ... 
     secureDataCollection: false 
});
</code></pre>

## useCORSOnly {#usecorsonly}

`useCORSOnly` 는 브라우저가 다른 도메인에서 리소스를 요청하는 방법을 제어하는 부울 true/false 매개 변수입니다.

<!-- 

dil-use-cors-only.xml

 -->

**개요**

`useCORSOnly` 는 기본적으로 false입니다. False는 브라우저가 CORS 또는 JSONP로 리소스 확인을 수행할 수 있음을 의미합니다. 그러나 [!UICONTROL DIL] 는 항상 먼저 CORS를 사용하여 리소스를 요청하려고 합니다. ID 서비스는 CORS를 지원하지 않는 오래된 브라우저에서는 JSONP로 되돌립니다. 보안 요구 사항이 높은 사이트와 같이 브라우저에서 CORS만 사용해야 하는 경우 을 설정합니다. `useCORSOnly:true`.

**코드 샘플**

<pre><code class="js">
var dilInstance = DIL.create({ 
     ... 
     useCORSOnly: true 
});
</code></pre>

>[!IMPORTANT]
>
>* 설정하는 것이 좋습니다. `useCORSOnly: true` 사이트 방문자에게 이 기능을 지원하는 브라우저가 있다고 확신할 때만 해당합니다.
>* 날짜 `useCORSOnly: true`, [!UICONTROL DIL] 은 Internet Explorer 버전 9 이상에서 ID를 호출하지 않습니다.
>

## useImageRequest {#useimagerequest}

요청 유형을 이미지로 변경합니다. `<img>` 스크립트에서 `<src>`.

<!-- 

r_dil_use_image_request.xml

 -->

**함수 서명:** `useImageRequest: function () {}`

>[!NOTE]
>
>이 메서드에 다른 API 호출을 연결할 수 있습니다.

**응답**

현재 항목의 API 개체 반환 [!UICONTROL DIL] 인스턴스.

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
>* [Adobe Experience Platform Identity 서비스의 동기화 기능](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/idsync.html)
>* [DIL 만들기](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Adobe Experience Platform Identity 서비스: UseCORSOnly](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/use-cors-only.html)
>* [Adobe Experience Platform Identity 서비스에서 CORS 지원](https://experienceleague.adobe.com/docs/id-service/using/reference/cors.html)
