---
description: 인스턴스 수준 DIL API를 사용하면 프로그래밍 방식으로 Audience Manager 개체를 만들고 사용하여 작업할 수 있습니다. 인스턴스 수준 메서드는 클래스 수준 메서드로 설정된 API 기능을 향상합니다.
keywords: 트레이트 만들기;트레이트 만들기
seo-description: 인스턴스 수준 DIL API를 사용하면 프로그래밍 방식으로 Audience Manager 개체를 만들고 사용하여 작업할 수 있습니다. 인스턴스 수준 메서드는 클래스 수준 메서드로 설정된 API 기능을 향상합니다.
seo-title: 인스턴스 수준 DIL 메서드
solution: Audience Manager
title: 인스턴스 수준 DIL 메서드
uuid: aa5147bb-51d5-41d4-a78a-e550f7492056
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 인스턴스 수준 DIL 메서드{#instance-level-dil-methods}

인스턴스 수준 API를 [!UICONTROL DIL] 사용하면 프로그래밍 방식으로 Audience Manager 개체를 만들고 사용하여 작업할 수 있습니다. 인스턴스 수준 메서드는 클래스 수준 메서드로 설정된 API 기능을 향상합니다.

## 인스턴스 수준 DIL 메서드 시작 {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

인스턴스 수준 API를 사용하여 작업하는 [!UICONTROL DIL] 경우:

* 액세스하려면 파트너 이름과 컨테이너 네임스페이스 ID(NSID)가 필요합니다. 이 정보는 Audience Manager 계정 관리자에게 문의하십시오.
* API 설명서의 샘플 *기울임꼴* 텍스트를 작업 중인 메서드에 필요한 값, ID 또는 기타 변수로 바꿉니다.

<!-- 

c_instance_start.xml

 -->

## 신호 {#signals}

대기 중인 요청의 쿼리 문자열에 고객 및 플랫폼 수준 매핑을 추가합니다.

<!-- 

r_dil_signals.xml

 -->

**** 함수 서명: `signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* 이 메서드에 다른 API 호출을 체인으로 연결할 수 있습니다.
>* Adobe Experience Cloud JavaScript 라이브러리가 페이지에 있는 경우, 요청을 보내기 전에 클라우드가 쿠키를 설정할 때까지 `submit()` 기다립니다.


**예약된 요청 키**

다음 요청 키는 예약되었으며 이 방법으로 덮어쓸 수 없습니다.

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**매개 변수**

| 이름 | 유형 | 설명 |
|---|---|---|
| `obj` | 개체 | 플랫폼 수준 매핑의 키-값 쌍을 나타내는 개체입니다. 매개 변수는 객체와 배열을 개체에서 속성 값으로 허용합니다. |
| `prefix` | 문자열 | 선택 사항입니다. 각 개체 키 앞에 있는 문자열 값(원본 키 대체). |
| `return` | DIL.api | 현재 DIL 인스턴스의 API 개체를 반환합니다. |

**응답**

현재 [!UICONTROL DIL] 인스턴스의 API 개체를 반환합니다.

**샘플 코드**

<pre><code>
var dataLib = DIL.create({ partner:'<i>partnerName</i>' containerNSID: <i>containerNSID</i> });
 
// 메서드 1 var obj = { key1 :1, key2 :2 };
dataLib.api.signatures(obj, 'c_').submit();
 
// 메서드 2 dataLib.api.signatures({c_zdid:54321}).submit();
 
// 방법 3 // 'c_key=a&amp;c_key=2&amp;c_key=3'을 Audience Manager var obj = { key :['a', 'b', 'c'] };
dataLib.api.signatures(obj, 'c_').submit(); 
</code></pre>

>[!MORELIKE_THIS]
>
>* [주요 변수의 이름 요구 사항](../features/traits/trait-key-name-requirements.md)


## traits {#traits}

보류 중인 요청의 쿼리 문자열에 SID를 추가합니다.

<!-- 

r_dil_traits.xml

 -->

**** 함수 서명: `traits:function (sids){}`

>[!NOTE]
>
>이 메서드에 다른 API 호출을 체인으로 연결할 수 있습니다.

**매개 변수**

| 이름 | 유형 | 설명 |
|---|---|---|
| `sids` | 배열 | 배열에서 트레이트 세그먼트 ID입니다. |

**응답**

현재 [!UICONTROL DIL] 인스턴스의 API 개체를 반환합니다.

**샘플 코드**

<pre><code>
var partnerObject = DIL.create({ partner:'<i>partner name</i>', containerNSID:NSID <i></i> });
partnerObject.api.traits(<i>[123, 456, 789]</i>); 
</code></pre>

## logs {#logs}

대기 중인 요청의 로그 파일에 데이터를 추가합니다.

<!-- 

r_dil_logs.xml

 -->

**** 함수 서명: `logs: function {key1:value1, key2:value2}`

**응답**

현재 [!UICONTROL DIL] 인스턴스의 API 개체를 반환합니다.

**샘플 코드**

<pre><code>
var partnerObject = DIL.create({ partner:'<i>partner</i>', containerNSID:NSID <i></i> });
partnerObject.api.logs({ file:'dil.js', 메시지:'첫 번째 요청입니다' });
</code></pre>

## 제출 {#submit}

보류 중인 모든 데이터를 [!UICONTROL DIL] 인스턴스에 대해 Audience Manager에 제출합니다.

<!-- 

r_dil_submit.xml

 -->

**** 함수 서명: `submit: function () {}`

>[!NOTE]
>
>이 메서드에 다른 API 호출을 체인으로 연결할 수 있습니다. 또한 [!UICONTROL DIL] 인코딩된 데이터를 대상 쿠키에 씁니다. 예를 들어 공백은 `%20` 세미콜론으로 인코딩됩니다 `%3B`.

**응답**

현재 [!UICONTROL DIL] 인스턴스의 API 개체를 반환합니다.

**샘플 코드**

<pre><code>
var dataLib = DIL.create({ partner:'<i>partnerName</i>', containerNSID: <i>containerNSID</i> });
 
dataLib.api.traits([<i>123,456, 789</i>]).logs({ file:'dil.js', 메시지:'이것은 첫 번째 요청' }).signatures({ c_zdid: <i>1111</i> d_dma:'<i>default</i>' }).submit();
</code></pre>

>[!MORELIKE_THIS]
>
>* [주요 변수의 접두사 요구 사항](../features/traits/trait-variable-prefixes.md)


## afterResult {#afterresult}

기본 대상 게시 콜백 이후에 실행되는 함수입니다.

<!-- 

r_dil_after_result.xml

 -->

**** 함수 서명: `afterResult: function (fn) {}`

>[!NOTE]
>
>이 메서드에 다른 API 호출을 체인으로 연결할 수 있습니다.

**매개 변수**

| 이름 | 유형 | 설명 |
|---|---|---|
| `fn` | 함수로 플러그인 호출 | JSON이 처리된 후에 실행할 함수는 대상 게시를 처리하는 기본 콜백으로 처리됩니다. |

**응답**

현재 [!UICONTROL DIL] 인스턴스의 API 개체를 반환합니다.

**샘플 코드**

<pre><code>
var dataLib = DIL.create({ partner:'<i>partnerName</i>', containerNSID: <i>containerNSID</i> });
 
dataLib.api.signatures({ c_zdid: <i>54321</i> d_dma:'<i>default</i>' }).afterResult(function(json){ //서버에서 반환된 JSON 데이터로 작업을 수행합니다. 
}).제출();
</code></pre>

## clearData {#cleardata}

대기 중인 요청의 모든 데이터를 지웁니다.

<!-- 

r_dil_clear_data.xml

 -->

**** 함수 서명: `clearData: function () {}`

>[!NOTE]
>
>이 메서드에 다른 API 호출을 체인으로 연결할 수 있습니다.

**응답**

현재 [!UICONTROL DIL] 인스턴스의 API 개체를 반환합니다.

**샘플 코드**

<pre><code>
var dataLib = DIL.create({ partner:'<i>partnerName</i>', containerNSID: <i>containerNSID</i> });
 
dataLib.api.traits([<i>123,456, 789</i>]).logs({ file:'dil.js' 메시지:'이것은 첫 번째 요청' }).signatures({ c_zdid: <i>1111</i> d_dma:'<i>default</i>' });
 
//보류 중인 dataLib.clearData(); 다시 설정합니다.
</code></pre>

## customQueryParams {#customqueryparams}

데이터 수집 서버에서 명시적으로 정의되지 않은 사용자 지정 쿼리 매개 변수를 대기 중인 요청에 추가합니다.

<!-- 

r_dil_custom_query_params.xml

 -->

**** 함수 서명: `customQueryParams: function (obj) {}`

>[!NOTE]
>
>이 메서드에 다른 API 호출을 체인으로 연결할 수 있습니다.

**예약된 요청 키**

다음 요청 키는 예약되었으며 이 방법으로 덮어쓸 수 없습니다.

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
var partnerObject = DIL.create({ partner:'<i>partner</i>', containerNSID:NSID <i></i> });
partnerObject.api.customQueryParams({ nid:54231, 유형:'default' }); 
</code></pre>

## getContainerNSID {#getcontainernsid}

인스턴스에 대한 컨테이너 NSID의 값을 [!UICONTROL DIL] 반환합니다. 디버깅 및 문제 해결에 유용합니다.

<!-- 

r_dil_get_container_nsid.xml

 -->

**** 함수 서명: `dil.api.getContainerNSID: function () {}`

**샘플 코드**

<pre><code>
var dataLib = DIL.create({ partner:'<i>partnerName</i>', containerNSID: <i>containerNSID</i> });
 
//컨테이너 NSID var nsid = dataLib.api.getContainerNSID();
</code></pre>

## getEventLog {#geteventlog}

시간순으로 정렬된 이벤트 로그 데이터를 문자열 배열로 반환합니다. 디버깅 및 문제 해결에 유용합니다.

<!-- 

r_dil_get_event_log.xml

 -->

**** 함수 서명: `dil.api.getEventLog: function () {}`

**샘플 코드**

<pre><code>
var dataLib = DIL.create({ partner:'<i>partnerName</i>', containerNSID: <i>containerNSID</i> });
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs({ file:'dil.js', 메시지:'이것이 첫 번째 요청' });.signatures({ c_zdid: <i>1111</i> d_dma:'<i>default</i>' });.submit();
 
//메시지 var 로그 = dataLib.api.getEventLog(); 확인 로그
if (log &amp;&amp; log.length) { alert(log.join('\n'));
}else{ alert('로그 메시지 없음');
}</code></pre>

## getPartner {#getpartner}

인스턴스의 파트너 이름을 [!UICONTROL DIL] 반환합니다. 디버깅 및 문제 해결에 유용합니다.

<!-- 

r_dil_get_partner.xml

 -->

**** 함수 서명: `dil.api.getPartner: function () {}`

**샘플 코드**

<pre><code>
var dataLib = DIL.create({ partner:'<i>partnerName</i>' containerNSID: <i>containerNSID</i> });
 
//파트너 이름 var partner = dataLib.api.getPartner();
</code></pre>

## getState {#getstate}

현재 [!UICONTROL DIL] 인스턴스의 상태를 반환합니다. 디버깅 및 문제 해결에 유용합니다.

<!-- 

r_dil_get_state.xml

 -->

**** 함수 서명: `dil.api.getState: function () {}`

**샘플 코드**

<pre><code>
var dataLib = DIL.create({ partner:'<i>partnerName</i>', containerNSID: <i>containerNSID</i> });
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs({ file:'dil.js', message:'This is the first request' });.signatures({ c.zdid: <i>1111</i> d_dma:'<i>default</i>' });.submit();
 
var state = dataLib.api.getState();
 
/*상태 상태의 객체 아웃라인 = { pendingRequest:{<i>서버</i>호출을 위해 보류 중인 데이터}, otherRequestInfo:{ unningQueue:[], 실행됨:[], 실행:false, 오류 발생:[], reservedKeys:{ sids:true, pdata:true, logdata:true, callback:true, postCallbackFn:true, useImageRequest:true, }, firstRequestHasCalled:false, num_of_jsonp_responses:0, num_of_jsonp_errors:0, num_of_img_responses:0, num_of_img_errors:0 }, destinationPublishingInfo:{ THROTTLE_START:3000, throttleTimerSet:false, id:"destination_publishing_iframe_' + partner + '_' + containerNSID, url:(constants.isHTTPS ? 'https://' :'https://fast.') + 파트너 + '.demdex.net/dest3.html?d_nsid=' + containerNSID + '#' + encodeURIComponent(document.location.href), iframe:null, iframeHasLoaded:false, sendingMessages:false, 메시지:[], messageSendingInterval:constants.POST_MESSAGE_ENABLED ? 15:IE 6 및 7의 경우 100ms, 기타 브라우저의 경우 15ms를 추천처리됨:[] } } */</code></pre>

## idSync {#idsync}

데이터 파트너가 사용자와 Audience Manager 간에 사용자 ID를 교환하고 동기화할 수 있도록 해주는 두 가지 기능으로 구성됩니다.

<!-- 

r_dil_idsync.xml

 -->

**함수 서명:**

버전 2.10 및 [!UICONTROL DIL] 3.1 이상에서 작동합니다.

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
   <td colname="col2"> <p>서로 다른 데이터 파트너와 Audience Manager 간에 예를 들어 파트너 x는 이 변수를 사용하여 파트너 y와 사용자 ID를 동기화한 다음 Audience Manager로 보냅니다. </p> <p> <p><b></b> 중요: 이 메서드는 더 이상 사용되지 않습니다. Experience Cloud <code> ID 서비스 </code> 인스턴스의 idSyncByURL 메서드를 사용하십시오. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.aamIdSync(initConfig) </code> </td> 
   <td colname="col2"> <p>사용자 ID를 이미 알고 있고 Audience Manager로 전송하려는 경우 </p> <p> <p><b></b> 중요: 이 메서드는 더 이상 사용되지 않습니다. Experience Cloud <code> ID 서비스 </code> 인스턴스의 idSyncByDataSource 메서드를 사용하십시오. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**idSync 요소**

`idSync` can conduct of the following:

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
* **`%HTTP_PROTO%`** :페이지 프로토콜( `http` 또는 `https`)을 설정합니다.

**응답**

두 함수 모두 성공하면 `Successfully queued` 반환됩니다. 실패한 경우 오류 메시지 문자열을 반환합니다.

**샘플 코드**

`dilInstance.api.idSync(initConfig)`

<pre><code class="js">
// dilInstance.api.idSync({ dpid:'23', //는 문자열 url이어야 합니다.'//su.addthis.com/red/usync?pid=16&amp;puid=%DID%&amp;url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net %2Fibs%3Adpid%3D420%26dpuuid%3D%7B%7Buid%7A d%7D', minutesToLive:20160 // 옵션, 기본값은 20160분(14일) });
</code></pre>

`dilInstance.api.aamIdSync(initConfig)`

<pre><code class="js">
// 'https:/https:' + '//dpm.demdex.net/ibs:dpid=&lt;dpid&gt;&amp;dpuuid=&lt;dpuuid&gt;' dilInstance.api.aamIdSync({ dpid:'23', //는 문자열 dpuuid:'98765', //는 string minutesToLive:20160 // 옵션, 기본값은 20160분(14일) });
</code></pre>

>[!MORELIKE_THIS]
>
>* [Experience Cloud ID 서비스의 동기화 함수](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idsync.html)


## result {#result}

보류 중인 요청에 콜백(JSON을 수신하는)을 추가합니다.

<!-- 

r_dil_result.xml

 -->

**** 함수 서명: `result: function (callback) {}`

이 콜백은 대상 게시를 처리하는 기본 콜백을 대체합니다.

>[!NOTE]
>
>이 메서드에 다른 API 호출을 체인으로 연결할 수 있습니다.

**매개 변수**

| 이름 | 유형 | 설명 |
|---|---|---|
| `callback` | 함수로 플러그인 호출 | JSONP 콜백에 의해 실행되는 JavaScript 함수. |

**응답**

현재 [!UICONTROL DIL] 인스턴스의 API 개체를 반환합니다.

**샘플 코드**

<pre><code>
var dataLib = DIL.create({ partner:'<i>partnerName</i>', containerNSID: <i>containerNSID</i> });
 
dataLib.api.traits([<i>123, 456, 789</i>]).result(function(json){ //Do something, with the JSON data returned from the server. 
});.제출();
</code></pre>

##  secureDataCollection {#securedatacollection}

`secureDataCollection` 는 Akamai 및 Akamai [!UICONTROL DIL] 를 호출하는 방법을 제어하는 부울 매개 [!UICONTROL Data Collection Servers (DCS)] 변수입니다.

<!-- 

dil-secure-data-collection.xml

 -->

* 이때 `secureDataCollection= true` (기본값) [!UICONTROL DIL] 항상 보안 HTTPS 호출을 수행합니다.

* 이 경우 `secureDataCollection= false`페이지에서 설정한 보안 프로토콜을 따라 HTTP 또는 HTTPS 호출을 [!UICONTROL DIL] 만듭니다.

>[!IMPORTANT]
>
>visitorAPI.js를 사용하고 동일한 페이지에서 사용하는 `secureDataCollection= false` 경우 [!UICONTROL DIL] 설정합니다. 아래 코드 샘플을 참조하십시오.

<pre><code class="js">
var dilInstance = DIL.create({ ...
     secureDataCollection:false });
</code></pre>

>[!MORELIKE_THIS]
>
>* [DIL 만들기](../dil/dil-class-overview/dil-create.md#dil-create)


## useCORSOnly {#usecorsonly}

`useCORSOnly` 브라우저가 다른 도메인의 리소스를 요청하는 방법을 제어하는 부울 true/false 매개 변수입니다.

<!-- 

dil-use-cors-only.xml

 -->

**개요**

`useCORSOnly` 은 기본적으로 false입니다. False는 브라우저가 CORS 또는 JSONP를 사용하여 리소스 확인을 수행할 수 있음을 의미합니다. 그러나 CORS를 먼저 사용하여 리소스를 요청하려고 [!UICONTROL DIL] 항상 시도합니다. ID 서비스는 CORS를 지원하지 않는 오래된 브라우저에서는 JSONP로 되돌립니다. 보안 요구 사항이 높은 사이트와 같이 브라우저가 CORS만 사용하도록 강제해야 하는 경우 를 `useCORSOnly:true`설정합니다.

**코드 샘플**

<pre><code class="js">
var dilInstance = DIL.create({ ...
     useCORSOnly:true });
</code></pre>

>[!IMPORTANT]
>
>* 사이트 방문자에게 이 기능을 지원하는 브라우저가 있는 `useCORSOnly: true` 경우에만 설정하는 것이 좋습니다.
>* 이 `useCORSOnly: true`경우, Internet Explorer 버전 9 이상에서 ID 호출을 하지 [!UICONTROL DIL] 않습니다.
>



>[!MORELIKE_THIS]
>
>* [DIL 만들기](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Experience Cloud ID 서비스:Use코르소nly](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-use-cors-only.html)
>* [Experience Cloud ID 서비스의 CORS 지원](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-cors.html)


## useImageRequest {#useimagerequest}

요청 유형을 스크립트에서 `<img>` 이미지로 변경합니다 `<src>`.

<!-- 

r_dil_use_image_request.xml

 -->

**** 함수 서명: `useImageRequest: function () {}`

>[!NOTE]
>
>이 메서드에 다른 API 호출을 체인으로 연결할 수 있습니다.

**응답**

현재 [!UICONTROL DIL] 인스턴스의 API 개체를 반환합니다.

**샘플 코드**

<pre><code>
var dataLib = DIL.create({ partner:'<i>partnerName</i>', containerNSID: <i>containerNSID</i> });
 
dataLib.api.traits([<i>123, 456, 789</i>]).useImageRequest().submit();
</code></pre>

