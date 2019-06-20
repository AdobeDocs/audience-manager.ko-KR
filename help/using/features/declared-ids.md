---
description: 선언된 ID 작동 방식, 절차 설정, 코드 예제 및 변수
keywords: ID 동기화
seo-description: 선언된 ID 작동 방식, 절차 설정, 코드 예제 및 변수
seo-title: 선언된 ID
solution: Audience Manager
title: 선언된 ID
uuid: 49 bb 4 f 7 e-b 4 a 7-4 d 87-a 29 c-c 3 dca 036 d 2 a 3
translation-type: tm+mt
source-git-commit: 94046c4ed825949451d0dbad37adbe9fba0f9191

---


# Declared IDs {#declared-ids}

선언된 ID 작동 방식, 절차 설정, 코드 예제 및 변수

## 선언된 ID 타게팅 {#declared-id-targeting}

타사 쿠키와 같은 영구 스토리지 메커니즘을 사용하거나 수락하지 않는 디바이스 또는 브라우저에서 Audience Manager와 사용자 ID를 교환하고 동기화할 수 있습니다.

<!-- declared_id_about.xml -->

## Purpose of Declared ID Targeting {#declared-id-targeting-purpose}

일부 브라우저 및 대부분의 모바일 장치에서는 타사 쿠키를 수락하지 않습니다. 따라서 사이트 방문자에 대한 정보를 유지하거나 영구 ID를 할당하는 것이 어려워집니다. To resolve this issue, Audience Manager uses [!UICONTROL DIL] to let you pass in [!UICONTROL declared IDs] on an event call. Also, a [!UICONTROL declared ID] can act as a universal ID that applies to the same user across all the solutions in the [!DNL Experience Cloud]. 다음 표에서는 ID 타깃팅/일치 프로세스에 대해 설명합니다.

<table id="table_5D59CD5AF70B44C3B45D279283D4691F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 프로세스 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>이벤트 호출</b> </td> 
   <td colname="col2"> <p>To work, you need <span class="wintitle"> DIL </span> and the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID service </a> code on the page. <span class="wintitle"> DIL </span> 는 <span class="wintitle"> Experience Cloud </span> ID 서비스에서 제공하는 <code> setvisitorid </code><span class="keyword"> 함수에서 선언된 ID를 얻고 </span><span class="keyword"> 이를 Audience Manager </span>에 전달합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID 일치</b> </td> 
   <td colname="col2"> <p>Audience Manager는 Adobe 시스템의 해당 ID와 클라이언트 및 방문자 ID를 일치시킵니다. 일치하는 ID가 없는 경우 Audience Manager는 새 ID를 만들고 이를 클라이언트 및 방문자 ID와 연결합니다. </p> <p> <p>참고: ID가 두 개 이상의 Audience Manager ID에 매핑되는 경우 가장 최근의 매핑이 사용됩니다. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>반환 ID</b> </td> 
   <td colname="col2"> <p>Audience Manager는 클라이언트 도메인 또는 애플리케이션에서 자사 쿠키 (또는 기타 어드레서블 저장 공간) 에 동기화된 ID를 씁니다. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>후속 이벤트 호출</b> </td>
   <td colname="col2"> <p>추가 이벤트 호출 클라이언트의 도메인에서 Audience Manager ID를 읽고 이것을 Audience Manager로 보냅니다. </p> </td>
  </tr> 
 </tbody>
</table>

To get started, you need to configure the [!DNL Experience Cloud] ID service and [!UICONTROL DIL] across the pages on your site that you want to use for data collection. [DIL 만들기](../dil/dil-class-overview/dil-create.md#dil-create) 및 [선언된 ID 변수를 참조하십시오](../features/declared-ids.md#declared-id-variables).

## Opt-out Calls {#opt-out-calls}

[!UICONTROL declared ID] 이 프로세스는 웹 사이트별로 대상 관리자가 타깃팅되지 않도록 사이트 방문자 기본 설정을 준수합니다. When Audience Manager receives an opt-out request, the [!DNL JSON] returned by the [!UICONTROL DCS] contains the error code 171, with the message &quot;Encountered opt out tag&quot;, instead of the Audience Manager user ID.

* Audience Manager can pass in a [!UICONTROL declared ID] opt-out alongside an Audience Manager [!UICONTROL UUID] in the [!DNL URL].
* [!UICONTROL declared ID] 옵트아웃은 [! Uicontrol 프로필 캐시 serveîr ([!UICONTROL PCS]) 를 파트너 기준으로 사용합니다. There is no platform-level opt-out using [!UICONTROL declared IDs]. Additionally, Audience Manager opts the user out from that particular region on the edge (the opt-out does not cross [!UICONTROL DCS] regions).

See [Data Privacy](../overview/data-security-and-privacy/data-privacy.md) for more information about opting-out of data collection.

## Declared ID Opt-Out Examples {#opt-out-examples}

You can make a [!UICONTROL declared ID] opt-out requests with the `d_cid` and `d_cid_ic` key-value pairs. The legacy parameters like `d_dpid` and `d_dpuuid` still work, but are considered deprecated. [CID가 DPID 및 DPUUID 대체](../reference/cid.md)를 참조하십시오. In the examples, *italics* indicates a variable placeholder.

### CID 및 CID_ IC 사용 옵트아웃

For a description and syntax, see [URL Variables and Syntax for Declared IDs](../features/declared-ids.md#variables-and-syntax).

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 옵트아웃 </th> 
   <th colname="col2" class="entry"> 코드 샘플 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>데이터 공급자 ID 및 사용자 ID 입니다. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>name</i>/demoptout.jpg? d_ cid = 123% 01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>통합 코드 및 사용자 ID. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>Name</i>/demoptout? d_ cid_ ic = 456% 01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Multiple <code> d_cid </code> and <code> d_cid_ic </code> key-value pairs. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>Name</i>/demoptout? d_ cid = 123% 01987 &amp; d_ cid_ ic = 456% 01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### DPID, DPUUID 및 UUID (더 이상 사용되지 않음) 옵트아웃

이러한 메서드는 여전히 작동하지만 더 이상 사용되지 않습니다. 이 정보는 이전 목적 및 참조용으로 제공됩니다. 기존 옵트아웃은 다음과 같습니다.

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 옵트아웃 (더 이상 사용되지 않음) </th> 
   <th colname="col2" class="entry"> 코드 샘플 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ uuid </code> 만 해당 </p> </td> 
   <td colname="col2"> <p> <code> https://domain/demoptout.jpg?d_uuid=AAM<i></i>ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>파트너 수준 옵트아웃 </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= 사용자 ID &amp; D_ DPID = 데이터 공급자 ID </code> </p> <p>A partner level opt-out gets stored for the latest mapping of this <code> dpid </code> + <code> dpuuid </code> pair to an AAM UUID. 이전에 기존 매핑이 없는 경우 Audience Manager는 쿠키에 AAM UUID가 포함되어 있는지 여부를 확인하고, 경우 옵트아웃을 저장하는 데 사용합니다. 그렇지 않은 경우 Audience Manager는 새 AAM UUID를 생성하고 옵트아웃을 IT 아래에 저장합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpuuid </code> + <code> d_ dpid </code> 및 명시적 <code> d_ uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://domain/demoptout.jpg?d_uuid=<i></i>사용자 ID &amp; D_ DPUUID = 데이터 공급자의 사용자 ID &amp;<i>D_ DPID = 데이터 공급자 ID</i></code> </p> <p> <code> d_ uuid </code> 는 항상 우선합니다. <code> dpid </code> + <code> dpuuid </code> 조합이 다른 aam uuid로 매핑되면 옵트아웃은 요청 <code> (d_ uuid </code>) 에 전달된 AAM UUID 아래에 저장됩니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variables and Syntax for Declared IDs {#variables-and-syntax}

<!-- c_declared_id_var_syntax.xml -->

The following table lists the key-value pairs that pass in your [!DNL Audience Manager] data provider ID and user IDs or integration codes, if used. *기울임꼴은* 변수 자리 표시자를 나타냅니다. 더 쉽게 읽을 수 있도록 공백이 추가되었습니다.

각 키-값 쌍:

* `=` 심볼은 키와 관련 값을 구분합니다.
* The non-printing [!DNL ASCII] character `%01` separates the values.

<table id="table_DFA9A584A5DE40669EAF0DB62DDC5AAF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 변수 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ cid =<i>데이터 공급자 ID</i> % 01<i>사용자 ID</i></code> </p> </td> 
   <td colname="col2"> <p>단일 키-값 쌍에 데이터 공급자 ID와 연관된 고유 사용자 ID가 포함됩니다. <code> d_ cid </code> 는 d_ dpid <code></code> 및 <code> d_ dpuuid </code>를 대체하며, 이것은 더 이상 사용되지 않지만 여전히 지원됩니다. <a href="../reference/cid.md">CID가 DPID 및 DPUUID 대체</a>를 참조하십시오 . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ cid_ ic =<i>통합 코드</i> % 01<i>사용자 ID</i></code> </p> </td> 
   <td colname="col2"> <p>단일 키-값 쌍에 통합 코드와 연관된 고유 사용자 ID가 포함됩니다. <code> d_ cid_ ic </code> 는 d_ dpid <code></code> 및 <code> d_ dpuuid를 대체하며, 이 변수는 </code>더 이상 사용되지 않지만 여전히 지원됩니다. <a href="../reference/cid.md">CID가 DPID 및 DPUUID 대체</a>를 참조하십시오 . </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sample Event Calls {#sample-event-calls}

이러한 키-값 쌍 및 필요한 구문을 감안할 때, 아래와 같이 이벤트 호출을 만듭니다.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 이벤트 호출에는 다음이 포함됩니다. </th> 
   <th colname="col2" class="entry"> 코드 샘플 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>데이터 공급자 ID 및 사용자 ID 입니다. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>이름</i>/이벤트? d_ cid = 123% 01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>통합 코드 및 사용자 ID. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>이름</i>/이벤트? d_ cid_ ic = 456% 01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Multiple <code> d_cid </code> and <code> d_cid_ic </code> key-value pairs. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>이름</i>/이벤트? d_ cid = 123% 01987 &amp; d_ cid_ ic = 456% 01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ like_ this]
>
>* [CID가 DPID 및 DPUUID를 대신함](../reference/cid.md)


## Declared ID Variables {#declared-id-variables}

Describes the configuration variables used to pass declared IDs through [!UICONTROL DIL] to [!DNL Audience Manager.]

## DIL Uses the Experience Cloud ID Service to Pass Declared IDs {#dil-id-service-pass-declared-ids}

<!-- r_dil_declared_id_vars.xml -->

[Experience Cloud ID 서비스와](https://marketing.adobe.com/resources/help/en_US/mcvid/)함께 사용하는 경우 더 이상 가치 하락 [!UICONTROL declared IDs]`dpid` 및 `dpuuid` 변수로 전달할 필요가 없습니다. Instead, the current versions of [!UICONTROL DIL] rely on the `visitorService` function to get the [!UICONTROL declared IDs] from the `setCustomerIDs` function in the [!UICONTROL Experience Cloud ID Service]. For more information, see [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html). You would call `visitorService` in `DIL.create` as shown below.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

`namespace` 키-값 쌍은 `MCORG`[!DNL Experience Cloud] 조직 ID 입니다. If you don&#39;t have this ID, you can find it in the [!UICONTROL Administration] section of the [!DNL Experience Cloud] dashboard. 이 대시보드를 보려면 관리자 권한이 필요합니다. [관리 참조: 핵심 서비스](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

## Deprecated Functions {#deprecated-functions}

With the latest versions of [!UICONTROL DIL] (6.2+), you don&#39;t need to use these key-value pairs to pass in [!UICONTROL declared IDs]. That&#39;s because [!UICONTROL DIL] now relies on the `visitorService` function shown in the code sample above. This function gets [!UICONTROL declared IDs] from the [!UICONTROL Experience Cloud ID Service]. 그러나 이전 및 이전 목적으로 이러한 변수를 참조합니다. See the code below for an example of how to configure `DIL.create` to get a [!UICONTROL declared ID] from the [!UICONTROL Visitor ID Service].
The following table describes the legacy variables used by the `declaredId` object:

<table id="table_A1884B72950F4BBDA87F17DDFF173628"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 이름 </th> 
   <th colname="col2" class="entry"> 유형 </th> 
   <th colname="col3" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> dpid </code> </td> 
   <td colname="col2"> 문자열 </td> 
   <td colname="col3"> <p>Audience Manager에서 할당한 데이터 파트너 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> 문자열 </td> 
   <td colname="col3"> <p>사용자에 대한 데이터 제공업체의 고유한 ID입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

### `DPID` 및 `DPUUID`

Audience Manager compares and matches the combined `DPID` and `DPUUID` to a corresponding user ID in our system. If an ID does not exist, Audience Manager creates a new user ID and synchronizes it to the `DPID/DPUUID` combination. Once Audience Manager matches or creates a user ID (the `UUID`) it returns that ID in the [!DNL JSON] response to the cookie in the client&#39;s domain (first-party cookie) or other local storage.

Call this function when you&#39;re using [!UICONTROL DIL] v6.1 or earlier. However, this function has been deprecated in favor of the new version that gets [!UICONTROL declared IDs] from the [!UICONTROL Experience Cloud ID Service].

<pre class="js"><code>dil. create ({ 
 파트너: " 파트너 이름 ", 
 Declaredid: { 
 DPUUID: <i>Dpuuid</i>, 
 DPID: <i>dpid</i> 
 } 
 });</code>
</pre>

>[!NOTE]
>
>Note, you need to programmatically develop the code that supplies the ID values for the `d_dpuuid` and `d_dpid` keys.

### DIL 인스턴스화 후 ID 전달

>[!NOTE]
>
>If you make an [!DNL API] call with a different `declaredID` combination, the new combination will be used for that call only. Further regular event calls will use the original `DIL.create`  `declaredID` combination.

<pre class="js"><code>dil. getdil (' partner name '). api. signals ({...}). declaredid ({ 
 DPUUID:<i>Dpuuid</i> 
 DPID:<i>dpid</i> }). 
submit ();</code>
</pre>

## Request/Response Examples {#request-response-examples}

요청은 데이터 공급자와 사용자 ID를 Audience Manager로 보냅니다.

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

The response returns the Audience Manager ID (e.g., `UUID`) which is written to a first-party cookie in the page domain.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Do Not Target and Opt-Out Calls {#do-not-target}

[!UICONTROL declared ID] 이 프로세스는 웹 사이트별로 대상 관리자가 타깃팅되지 않도록 사이트 방문자 기본 설정을 준수합니다. When Audience Manager receives an opt-out request, the [!UICONTROL DCS] returns an empty [!DNL JSON] object instead of the Audience Manager user ID.