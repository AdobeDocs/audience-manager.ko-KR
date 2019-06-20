---
description: 인스턴스 수준 DIL API를 사용하여 프로그래밍 방식으로 Audience Manager 개체를 만들고 작업할 수 있습니다. 인스턴스 수준 메서드는 클래스 수준 메서드로 설정된 API 기능을 향상시킵니다.
keywords: 트레이트를 만들어트레이트 제작
seo-description: 인스턴스 수준 DIL API를 사용하여 프로그래밍 방식으로 Audience Manager 개체를 만들고 작업할 수 있습니다. 인스턴스 수준 메서드는 클래스 수준 메서드로 설정된 API 기능을 향상시킵니다.
seo-title: 인스턴스 수준 DIL 메서드
solution: Audience Manager
title: 인스턴스 수준 DIL 메서드
uuid: AA 5147 BB -51 D 5-41 D 4-A 78 A-E 550 F 7492056
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Instance-level DIL Methods{#instance-level-dil-methods}

The instance-level [!UICONTROL DIL] APIs let you programmatically create and work with Audience Manager objects. 인스턴스 수준 메서드는 클래스 수준 메서드로 설정된 API 기능을 향상시킵니다.

## Getting started with Instance-level DIL Methods {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

When working with the instance-level [!UICONTROL DIL] APIs:

* 액세스 권한은 파트너 이름과 컨테이너 네임스페이스 ID (NSID) 가 필요합니다. 이 정보를 얻으려면 Audience Manager 계정 관리자에게 문의하십시오.
* Replace any sample *italicized* text in the API documentation with value, ID, or other variable as required by the method you&#39;re working with.

<!-- 

c_instance_start.xml

 -->

## signals {#signals}

보류 중인 요청의 쿼리 문자열에 고객 및 플랫폼 수준 매핑을 추가합니다.

<!-- 

r_dil_signals.xml

 -->

**함수 서명:**`signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* 다른 API 호출을 이 메서드에 체인으로 연결할 수 있습니다.
>* If the Adobe Experience Cloud JavaScript library is on the page, `submit()` waits for the Cloud to set a cookie before sending a request.


**예약 요청 키**

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
| `obj` | 개체 | 플랫폼 수준 매핑에 대한 키-값 쌍을 나타내는 개체. 매개 변수는 문자열에서 문자열 및 배열을 속성 값으로 수락합니다. |
| `prefix` | 문자열 | 선택 사항입니다. 각 객체 키에 접두사가 붙은 문자열 값 (원본 키 대체) |
| `return` | dil. api | 현재 DIL 인스턴스의 API 객체를 반환합니다. |

**응답**

Returns the API object of the current [!UICONTROL DIL] instance.

**샘플 코드**

<pre><code>var datalib = dil. create ({ 
 파트너: '<i>Partnername</i>' 
 Containernsid: <i>containernsid</i> }); 
 
// 메서드 1 
var obj = {key 1: 1, Key 2: 2}; 
datalib. api. signals (obj,' c_'). submit (); 
 
// 메서드 2 
datalib. api. signals ({c_ zdid: 54321}). submit (); 
 
// 메서드 3 
//는 Audience Manager 
Var obj = {key: 로'c_ key = A &amp; c_ key = 2 &amp; c_ key = 3 ' 를 전송합니다. [' a ',' b ',' c ']}; 
datalib. api. signals (obj,' c_'). submit ();</code>
</pre>

>[!MORE_ like_ this]
>
>* [주요 변수의 이름 요구 사항](../features/traits/trait-key-name-requirements.md)


## traits {#traits}

대기 중인 요청의 쿼리 문자열에 SID를 추가합니다.

<!-- 

r_dil_traits.xml

 -->

**함수 서명:**`traits:function (sids){}`

>[!NOTE]
>
>다른 API 호출을 이 메서드에 체인으로 연결할 수 있습니다.

**매개 변수**

| 이름 | 유형 | 설명 |
|---|---|---|
| `sids` | 배열 | 특성 세그먼트 ID를 배열에서 지정합니다. |

**응답**

Returns the API object of the current [!UICONTROL DIL] instance.

**샘플 코드**

<pre><code>var partnerobject = dil. create ({ 
 파트너: '<i>파트너 이름</i>', 
 Containernsid: <i>nsid</i> }); 
partnerobject. api. traits (<i>[123, 456, 789]</i>);</code>
</pre>

## logs {#logs}

보류 중인 요청에서 로그 파일에 데이터를 추가합니다.

<!-- 

r_dil_logs.xml

 -->

**함수 서명:**`logs: function {key1:value1, key2:value2}`

**응답**

Returns the API object of the current [!UICONTROL DIL] instance.

**샘플 코드**

<pre><code>var partnerobject = dil. create ({ 
 파트너:<i>' 파트너</i>', 
 Containernsid: <i>nsid</i> }); 
partnerobject. api. logs ({ 
 파일: ' dil. js ', 
 메시지: ' this is the first request '});</code>
</pre>

## 제출 {#submit}

Submits all pending data to Audience Manager for the [!UICONTROL DIL] instance.

<!-- 

r_dil_submit.xml

 -->

**함수 서명:**`submit: function () {}`

>[!NOTE]
>
>다른 API 호출을 이 메서드에 체인으로 연결할 수 있습니다. Also, [!UICONTROL DIL] writes encoded data to a destination cookie. For example, spaces are encoded as `%20` and semicolons as `%3B`.

**응답**

Returns the API object of the current [!UICONTROL DIL] instance.

**샘플 코드**

<pre><code>var datalib = dil. create ({ 
 파트너: '<i>Partnername</i>', 
 Containernsid: <i>containernsid</i> }); 
 
datalib. api. traits ([<i>123,456, 
789</i>]). logs ({ 
 파일: ' dil. js ', 
 메시지: ' this is the first request '}). 
signals ({ 
 c_ zdid: <i>1111</i> 
 D_ DMA: '<i>default</i>'}). 
submit ();</code>
</pre>

>[!MORE_ like_ this]
>
>* [주요 변수의 접두사 요구 사항](../features/traits/trait-variable-prefixes.md)


## afterResult {#afterresult}

기본 대상 게시 콜백 이후에 실행되는 함수입니다.

<!-- 

r_dil_after_result.xml

 -->

**함수 서명:**`afterResult: function (fn) {}`

>[!NOTE]
>
>다른 API 호출을 이 메서드에 체인으로 연결할 수 있습니다.

**매개 변수**

| 이름 | 유형 | 설명 |
|---|---|---|
| `fn` | 함수로 플러그인 호출 | JSON 이 대상 게시를 처리하는 기본 콜백에 의해 처리된 후 실행하려는 함수입니다. |

**응답**

Returns an API object of the current [!UICONTROL DIL] instance.

**샘플 코드**

<pre><code>var datalib = dil. create ({ 
 파트너: '<i>Partnername</i>', 
 Containernsid: <i>containernsid</i> }); 
 
datalib. api. signals ({ 
 c_ zdid: <i>54321</i> 
 D_ DMA: '<i>default</i>'}). 
afterresult (function (JSON) { 
 //Do 서버에서 반환된 JSON 데이터를 사용하여 원하는 내용을 찾습니다. 
}).제출();
</code></pre>

## clearData {#cleardata}

보류 중인 요청에서 모든 데이터를 지웁니다.

<!-- 

r_dil_clear_data.xml

 -->

**함수 서명:**`clearData: function () {}`

>[!NOTE]
>
>다른 API 호출을 이 메서드에 체인으로 연결할 수 있습니다.

**응답**

Returns the API object of the current [!UICONTROL DIL] instance.

**샘플 코드**

<pre><code>var datalib = dil. create ({ 
 파트너: '<i>Partnername</i>', 
 Containernsid: <i>containernsid</i> }); 
 
datalib. api. traits ([<i>123,456, 789</i>]). logs ({ 
 파일: ' dil. js ' 
 메시지: ' this is the first request '}). 
signals ({ 
 c_ zdid: <i>1111</i> 
 D_ DMA: '<i>default</i>'}); 
 
//Reset 보류 중인 데이터 
datalib. cleardata ();</code>
</pre>

## customQueryParams {#customqueryparams}

데이터 수집 서버에서 명시적으로 정의되지 않은 사용자 지정 쿼리 매개 변수를 보류 중인 요청에 추가합니다.

<!-- 

r_dil_custom_query_params.xml

 -->

**함수 서명:**`customQueryParams: function (obj) {}`

>[!NOTE]
>
>다른 API 호출을 이 메서드에 체인으로 연결할 수 있습니다.

**예약 요청 키**

다음 요청 키는 예약되어 있으며 이 방법으로 덮어쓸 수 없습니다.

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**응답**

현재 DIL 인스턴스의 API 객체를 반환합니다.

**샘플 코드**

<pre><code>var partnerobject = dil. create ({ 
 파트너:<i>' 파트너</i>', 
 Containernsid: <i>nsid</i> }); 
partnerobject. api. customqueryparams ({ 
 NID: 54231, 
 Ntype: ' default '});</code>
</pre>

## getContainerNSID {#getcontainernsid}

Returns the value of the container NSID for the [!UICONTROL DIL] instance. 디버깅 및 문제 해결에 유용합니다.

<!-- 

r_dil_get_container_nsid.xml

 -->

**함수 서명:**`dil.api.getContainerNSID: function () {}`

**샘플 코드**

<pre><code>var datalib = dil. create ({ 
 파트너: '<i>Partnername</i>', 
 Containernsid: <i>containernsid</i> }); 
 
//Verify 컨테이너 nsid 
var nsid = datalib. api. getcontainernsid ();</code>
</pre>

## getEventLog {#geteventlog}

시간순으로 정렬된 이벤트 로그 데이터를 문자열 배열로 반환합니다. 디버깅 및 문제 해결에 유용합니다.

<!-- 

r_dil_get_event_log.xml

 -->

**함수 서명:**`dil.api.getEventLog: function () {}`

**샘플 코드**

<pre><code>var datalib = dil. create ({ 
 파트너: '<i>Partnername</i>', 
 Containernsid: <i>containernsid</i> }); 
 
datalib. api. traits ([<i>123, 456, 789</i>]). logs ({ 
 파일: ' dil. js ', 
 메시지: ' this is the first request '}); . 신호 ({ 
 c_ zdid: <i>1111</i> 
 D_ DMA: '<i>default</i>'}); . submit (); 
 
//Check log = dat = datalib. api. geteventlog (); 
if (log &amp; &amp; log. length) { 
 alert (log. join ('\ n ')); 
} else { 
 alert (' no log messages '); 
}</code>
</pre>

## getPartner {#getpartner}

Returns the partner name for a [!UICONTROL DIL] instance. 디버깅 및 문제 해결에 유용합니다.

<!-- 

r_dil_get_partner.xml

 -->

**함수 서명:**`dil.api.getPartner: function () {}`

**샘플 코드**

<pre><code>var datalib = dil. create ({ 
 파트너: '<i>Partnername</i>' 
 Containernsid: <i>containernsid</i> }); 
 
//Verify 파트너 이름 
var partner = datalib. api. getpartner ();</code>
</pre>

## getState {#getstate}

Returns the state of the current [!UICONTROL DIL] instance. 디버깅 및 문제 해결에 유용합니다.

<!-- 

r_dil_get_state.xml

 -->

**함수 서명:**`dil.api.getState: function () {}`

**샘플 코드**

<pre><code>var datalib = dil. create ({ 
 파트너: '<i>Partnername</i>', 
 Containernsid: <i>containernsid</i> }); 
 
datalib. api. traits ([<i>123, 456, 789</i>]). logs ({ 
 파일: ' dil. js ', 
 메시지: ' this is the first request '}); . 신호 ({ 
 c. zdid: <i>1111</i> 
 D_ DMA: '<i>default</i>'}); . submit (); 
 
var state = datalib. api. getstate (); 
 
/* 상태 
상태 개요 = { 
 Pendingrequest: {<i>pending data for call to server</i>}, 
 Otherrequestinfo: { 
 Firingqueue: [], 
 발판: [], 
 실행: false, 
 잘못된 문제: [], 
 Reservedkeys: { 
 SID: true, 
 Pdata: true, 
 Logdata: true, 
 콜백: true, 
 Postcallbackfn: true, 
 Useimagerequest: true, 
 }, 
 Firstrequesthasfiring: false, 
 num_ of_ jsonp_ response: 0, 
 num_ of_ jsonp_ errors: 0, 
 NUM_ OF_ IMG_ RESPONSES: 0, 
 num_ of_ img_ errors: 0 
 }, 
 Destinationpublishinginfo: { 
 throttle_ start: 3000, 
 Throttletimerset: false, 
 ID: " destination_ publishing_ iframe_' + partner +'_' + containernsid, 
 URL: (constants. ishttps? ' https://': ' https://fast.') + Partner +' .demdex.net/dest3.html?d_nsid=' 
 + containernsid +' #' + encodeuricomponent (document. location. href), 
 iframe: null, 
 Iframehasloaded: false, 
 Sendingmessages: false, 
 메시지: [], 
 Messagesendinginterval: 상수 post_ message_ enabled? 15: 100, 
               //Recommend 100ms for IE 6 &amp; 7, 15ms for other browsers 
               jsonProcessed: [] 
     } 
} 
*/
</code></pre>

## idSync {#idsync}

데이터 파트너가 자신과 Audience Manager 간에 사용자 ID를 교환하고 동기화할 수 있는 두 가지 함수로 구성됩니다.

<!-- 

r_dil_idsync.xml

 -->

**함수 서명:**

Works with [!UICONTROL DIL] versions 2.10 and 3.1 or higher.

<table id="table_ADC7501511914805A6A6B24B2DFEBA51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 코드 </th> 
   <th colname="col2" class="entry"> 사용자 ID 동기화 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil. instance. api. idsync (initconfig) </code> </td> 
   <td colname="col2"> <p>다양한 데이터 파트너와 고객 관리자 간의 공동 작업 예를 들어 파트너 X는 이 아이콘을 사용하여 파트너 Y와 사용자 ID를 동기화한 다음 Audience Manager로 전송합니다. </p> <p> <p><b>중요:</b> 이 메서드는 더 이상 사용되지 않습니다. Please use the <code> idSyncByURL </code> method of the Experience Cloud ID Service instance. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil. instance. api. aamidsync (initconfig) </code> </td> 
   <td colname="col2"> <p>사용자 ID를 이미 알고 있고 Audience Manager로 전송하려는 경우 </p> <p> <p><b>중요:</b> 이 메서드는 더 이상 사용되지 않습니다. Please use the <code> idSyncByDataSource </code> method of the Experience Cloud ID Service instance. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Idsync 요소**

`idSync` 다음으로 구성될 수 있습니다.

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

`idSync` 다음 매크로를 수락합니다.

* **`%TIMESTAMP%`:** 타임스탬프를 생성합니다(밀리초 단위). 캐시 무효화에 사용됩니다.
* **`%DID%`:** 사용자의 Audience Manager ID를 삽입합니다.
* **`%HTTP_PROTO%`:** 페이지 프로토콜 ( `http` 또는 `https`) 를 설정합니다.

**응답**

Both functions return `Successfully queued` if successful. 실패한 경우 오류 메시지 문자열을 반환합니다.

**샘플 코드**

`dilInstance.api.idSync(initConfig)`

<pre><code class="js">// 매크로가 Dilinstance. api. 
idsync ({ 
 DPID: ' 23 ' 이면, //는 문자열이어야 합니다. 
 URL: '//su.addthis.com/red/usync?pid=16&amp;puid=%DID%&amp;url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net 
% 2 fibs % 3 adpid % 3 d 420% 26 dpuuid % 3 d % 7 b % 7 buid % 7 d % 7 d ', 
 Minutestolive: 20160 // 옵션, 기본값은 20160 분 (14 일)})</code>
</pre>

`dilInstance.api.aamIdSync(initConfig)`

<pre><code class="js">// fires ' https:/https:' +'//dpm.demdex.net/ibs:dpid= &lt; dpid &gt; &amp; dpuuid = &lt; dpuuid &gt;' 
dilinstance. api. aamidsync ({ 
 DPID: ' 23 ' 이면, //는 문자열이어야 합니다. 
 DPUUID: ' 98765 ', //는 문자열이어야 함 
 Minutestolive: 20160 // 옵션, 기본값은 20160 분 (14 일)})</code>
</pre>

>[!MORE_ like_ this]
>
>* [Experience Cloud ID 서비스의 동기화 함수](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idsync.html)


## result {#result}

보류 중인 요청에 콜백을 받는 콜백을 추가합니다.

<!-- 

r_dil_result.xml

 -->

**함수 서명:**`result: function (callback) {}`

이 콜백은 대상 게시를 처리하는 기본 콜백을 대체합니다.

>[!NOTE]
>
>다른 API 호출을 이 메서드에 체인으로 연결할 수 있습니다.

**매개 변수**

| 이름 | 유형 | 설명 |
|---|---|---|
| `callback` | 함수로 플러그인 호출 | JSONP 콜백에 의해 실행된 JavaScript 함수. |

**응답**

Returns the API object of the current [!UICONTROL DIL] instance.

**샘플 코드**

<pre><code>var datalib = dil. create ({ 
 파트너: '<i>Partnername</i>', 
 Containernsid: <i>containernsid</i> }); 
 
datalib. api. traits ([<i>123, 456, 789</i>]). result (JSON) { 
 //Do 서버에서 반환된 JSON 데이터가 있을 가능성이 있는 것 
});.제출();
</code></pre>

## secureDataCollection {#securedatacollection}

`secureDataCollection` 은 및 Akamai를 호출하는 방법을 [!UICONTROL DIL] 제어하는 부울 [!UICONTROL Data Collection Servers (DCS)] 매개 변수입니다.

<!-- 

dil-secure-data-collection.xml

 -->

* When `secureDataCollection= true` (default), [!UICONTROL DIL] always makes secure, HTTPS calls.

* When `secureDataCollection= false`, [!UICONTROL DIL] makes either HTTP or HTTPS calls by following the security protocol set by the page.

>[!IMPORTANT]
>
>Set `secureDataCollection= false` if you use visitorAPI.js and [!UICONTROL DIL] on the same page. 아래의 코드 샘플을 참조하십시오.

<pre><code class="js">var dilinstance = dil. create ({ 
 ... 
 Securedatacollection: false});</code>
</pre>

>[!MORE_ like_ this]
>
>* [DIL 만들기](../dil/dil-class-overview/dil-create.md#dil-create)


## useCORSOnly {#usecorsonly}

`useCORSOnly` 는 브라우저가 다른 도메인의 리소스를 요청하는 방법을 제어하는 부울 true/false 매개 변수입니다.

<!-- 

dil-use-cors-only.xml

 -->

**개요**

`useCORSOnly` 은 기본적으로 false 입니다. false는 브라우저가 CORS 또는 JSONP를 사용하여 리소스 확인을 수행할 수 있음을 의미합니다. However, [!UICONTROL DIL] always tries to request resources with CORS first. ID 서비스는 CORS를 지원하지 않는 오래된 브라우저에서는 JSONP로 되돌립니다. If you need to force the browser to use CORS only, such as with sites that have high-security requirements, set `useCORSOnly:true`.

**코드 샘플**

<pre><code class="js">var dilinstance = dil. create ({ 
 ... 
 Usecorsonly: true});</code>
</pre>

>[!IMPORTANT]
>
>* We recommend that you set `useCORSOnly: true` only when you&#39;re sure that your site visitors have browsers that support this feature.
>* When `useCORSOnly: true`, [!UICONTROL DIL] will not make ID calls from Internet Explorer version 9 or older.
>



>[!MORE_ like_ this]
>
>* [DIL 만들기](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Experience Cloud ID 서비스: Usecorsonly](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-use-cors-only.html)
>* [Experience Cloud ID 서비스의 CORS 지원](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-cors.html)


## useImageRequest {#useimagerequest}

Changes the request type to image `<img>` from script `<src>`.

<!-- 

r_dil_use_image_request.xml

 -->

**함수 서명:**`useImageRequest: function () {}`

>[!NOTE]
>
>다른 API 호출을 이 메서드에 체인으로 연결할 수 있습니다.

**응답**

Returns an API object of the current [!UICONTROL DIL] instance.

**샘플 코드**

<pre><code>var datalib = dil. create ({ 
 파트너: '<i>Partnername</i>', 
 Containernsid: <i>containernsid</i> }); 
 
datalib. api. traits ([<i>123, 456, 789</i>]). useimagerequest (). submit ();</code>
</pre>

