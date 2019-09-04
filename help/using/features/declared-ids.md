---
description: 선언된 ID 작동 방식, 절차 설정, 코드 예제 및 변수
keywords: ID 동기화
seo-description: 선언된 ID 작동 방식, 절차 설정, 코드 예제 및 변수
seo-title: 선언된 ID
solution: Audience Manager
title: 선언된 ID
uuid: 49 bb 4 f 7 e-b 4 a 7-4 d 87-a 29 c-c 3 dca 036 d 2 a 3
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# 선언된 ID {#declared-ids}

선언된 ID 작동 방식, 절차 설정, 코드 예제 및 변수

## 선언된 ID 타게팅 {#declared-id-targeting}

타사 쿠키와 같은 영구 스토리지 메커니즘을 사용하거나 수락하지 않는 디바이스 또는 브라우저에서 Audience Manager와 사용자 ID를 교환하고 동기화할 수 있습니다.

<!-- declared_id_about.xml -->

## 선언된 ID 타깃팅의 목적 {#declared-id-targeting-purpose}

일부 브라우저 및 대부분의 모바일 장치에서는 타사 쿠키를 수락하지 않습니다. 따라서 사이트 방문자에 대한 정보를 유지하거나 영구 ID를 할당하는 것이 어려워집니다. Audience Manager는 이 문제를 해결하기 위해 이벤트 호출을 전달할 수 있도록 [!UICONTROL DIL][!UICONTROL declared IDs] 해줍니다. 또한 A는 [!UICONTROL declared ID] 의 모든 솔루션에서 동일한 사용자에게 적용되는 유니버설 ID 역할을 [!DNL Experience Cloud]합니다. 다음 표에서는 ID 타깃팅/일치 프로세스에 대해 설명합니다.

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
   <td colname="col2"> <p>작업을 하려면 페이지에서 <span class="wintitle"> DIL </span> 와 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID 서비스 </a> 코드가 필요합니다. <span class="wintitle"> DIL </span> 는 <span class="wintitle"> Experience Cloud </span> ID 서비스에서 제공하는 <code> setvisitorid </code><span class="keyword"> 함수에서 선언된 ID를 얻고 </span><span class="keyword"> 이를 Audience Manager </span>에 전달합니다. </p> </td> 
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

시작하려면 [!DNL Experience Cloud] , ID 서비스와 데이터 수집에 사용할 사이트의 [!UICONTROL DIL] 페이지 간에 구성해야 합니다. [DIL 만들기](../dil/dil-class-overview/dil-create.md#dil-create) 및 [선언된 ID 변수를 참조하십시오](../features/declared-ids.md#declared-id-variables).

## 옵트아웃 호출 {#opt-out-calls}

[!UICONTROL declared ID] 이 프로세스는 웹 사이트별로 대상 관리자가 타깃팅되지 않도록 사이트 방문자 기본 설정을 준수합니다. Audience Manager가 옵트아웃 요청을 받으면에 의해 [!DNL JSON] 반환되는 [!UICONTROL DCS] 에 Audience Manager 사용자 ID 대신 "옵트아웃 태그" 라는 메시지와 함께 오류 코드 171 이 반환됩니다.

* Audience Manager는에서 Audience Manager와 함께 [!UICONTROL declared ID] 옵트아웃을 전달할 수 [!UICONTROL UUID][!DNL URL]있습니다.
* [!UICONTROL declared ID] 옵트아웃은 [! Uicontrol 프로필 캐시 서버 ([!UICONTROL PCS]) 를 파트너 기준으로 사용합니다. 사용 중인 플랫폼 수준의 [!UICONTROL declared IDs]옵트아웃은 없습니다. 또한 Audience Manager는 사용자를 가장자리의 특정 특정 지역에서 옵트아웃합니다 (옵트아웃이 지역화되지 [!UICONTROL DCS] 않음).

데이터 수집의 선택 취소에 대한 자세한 내용은 [데이터 개인 정보를](../overview/data-security-and-privacy/data-privacy.md) 참조하십시오.

## 선언된 ID 옵트아웃 예 {#opt-out-examples}

키와 키-값 쌍으로 [!UICONTROL declared ID] 옵트아웃 요청을 `d_cid` 할 `d_cid_ic` 수 있습니다. 기존 매개 변수는 `d_dpid` 여전히 `d_dpuuid` 작동하지만 여전히 사용되지 않습니다. [CID가 DPID 및 DPUUID 대체](../reference/cid.md)를 참조하십시오. In the examples, *italics* indicates a variable placeholder.

### CID 및 CID_ IC 사용 옵트아웃

설명과 구문에 대한 자세한 내용은 선언된 ID에 [대한 URL 변수 및 구문을 참조하십시오](../features/declared-ids.md#variables-and-syntax).

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
   <td colname="col1"> <p>여러 <code> d_ cid </code> 및 <code> d_ cid_ ic </code> 키-값 쌍. </p> </td> 
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
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= 사용자 ID &amp; D_ DPID = 데이터 공급자 ID </code> </p> <p>파트너 수준의 옵트아웃은 이 <code> dpid </code> + <code> dpuuid </code> 쌍의 최신 매핑에 대한 AAM UUID에 저장됩니다. 이전에 기존 매핑이 없는 경우 Audience Manager는 쿠키에 AAM UUID가 포함되어 있는지 여부를 확인하고, 경우 옵트아웃을 저장하는 데 사용합니다. 그렇지 않은 경우 Audience Manager는 새 AAM UUID를 생성하고 옵트아웃을 IT 아래에 저장합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpuuid </code> + <code> d_ dpid </code> 및 명시적 <code> d_ uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://domain/demoptout.jpg?d_uuid=<i></i>사용자 ID &amp; D_ DPUUID = 데이터 공급자의 사용자 ID &amp;<i>D_ DPID = 데이터 공급자 ID</i></code> </p> <p> <code> d_ uuid </code> 는 항상 우선합니다. <code> dpid </code> + <code> dpuuid </code> 조합이 다른 aam uuid로 매핑되면 옵트아웃은 요청 <code> (d_ uuid </code>) 에 전달된 AAM UUID 아래에 저장됩니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 선언된 ID에 대한 변수 및 구문 {#variables-and-syntax}

<!-- c_declared_id_var_syntax.xml -->

다음 표에는 [!DNL Audience Manager] 데이터 공급자 ID와 사용자 ID 또는 통합 코드를 전달하는 키-값 쌍이 나열되어 있습니다. *기울임꼴은* 변수 자리 표시자를 나타냅니다. 더 쉽게 읽을 수 있도록 공백이 추가되었습니다.

각 키-값 쌍:

* `=` 심볼은 키와 관련 값을 구분합니다.
* 인쇄할 수 없는 [!DNL ASCII] 문자는 `%01` 값을 구분합니다.

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

## 샘플 이벤트 호출 {#sample-event-calls}

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
   <td colname="col1"> <p>여러 <code> d_ cid </code> 및 <code> d_ cid_ ic </code> 키-값 쌍. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>이름</i>/이벤트? d_ cid = 123% 01987 &amp; d_ cid_ ic = 456% 01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ like_ this]
>
>* [CID가 DPID 및 DPUUID를 대신함](../reference/cid.md)


## 선언된 ID 변수 {#declared-id-variables}

선언된 ID [!UICONTROL DIL] 를 [!DNL Audience Manager.]

## DIL는 Experience Cloud ID 서비스를 사용하여 선언된 ID 전달 {#dil-id-service-pass-declared-ids}

<!-- r_dil_declared_id_vars.xml -->

[Experience Cloud ID 서비스와](https://marketing.adobe.com/resources/help/en_US/mcvid/)함께 사용하는 경우 더 이상 가치 하락 [!UICONTROL declared IDs]`dpid` 및 `dpuuid` 변수로 전달할 필요가 없습니다. 대신의 현재 버전은 함수에 [!UICONTROL DIL]`visitorService` 있는 함수에서를 [!UICONTROL declared IDs]`setCustomerIDs` 가져옵니다 [!UICONTROL Experience Cloud ID Service]. For more information, see [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html). 아래와 `visitorService``DIL.create` 같이 전화합니다.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

`namespace` 키-값 쌍은 `MCORG`[!DNL Experience Cloud] 조직 ID 입니다. 이 ID가 없는 경우 대시보드 [!UICONTROL Administration] 섹션에서 찾을 [!DNL Experience Cloud] 수 있습니다. 이 대시보드를 보려면 관리자 권한이 필요합니다. [관리 참조: 핵심 서비스](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

## 사용되지 않는 함수 {#deprecated-functions}

최신 버전의 [!UICONTROL DIL] (6.2 +) 에서는 이러한 키-값 쌍을 사용하여 전달할 [!UICONTROL declared IDs]필요가 없습니다. 이는 [!UICONTROL DIL] 위의 코드 샘플에 표시된 `visitorService` 함수에 의존하기 때문입니다. 이 함수는에서 가져옵니다 [!UICONTROL declared IDs][!UICONTROL Experience Cloud ID Service]. 그러나 이전 및 이전 목적으로 이러한 변수를 참조합니다. 에서 A를 받도록 구성하는 `DIL.create` 방법의 예는 아래 코드를 [!UICONTROL declared ID] 참조하십시오 [!UICONTROL Visitor ID Service].
다음 표에서는 객체에서 사용되는 이전 변수에 대해 설명합니다 `declaredId` .

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

Adobe Audience Manager는 시스템에 있는 해당 `DPID` 사용자 `DPUUID` ID와 결합하고 일치시킵니다. ID가 없는 경우 Audience Manager는 새 사용자 ID를 만들고 이 ID를 `DPID/DPUUID` 조합과 동기화합니다. Audience Manager가 사용자 ID를 일치시키거나 만들기 () `UUID`하면, 클라이언트의 도메인 (퍼스트 파티 쿠키) 또는 기타 로컬 스토리지의 쿠키에 [!DNL JSON] 대한 응답에서 해당 ID가 반환됩니다.

v 6.1 이전 버전을 사용하는 [!UICONTROL DIL] 경우 이 함수를 호출합니다. 그러나 이 함수는에서 가져오는 [!UICONTROL declared IDs] 새 버전에 대해 더 이상 사용되지 않습니다 [!UICONTROL Experience Cloud ID Service].

```js
DIL.create({
    partner : "partner name",
    declaredId : {
       dpuuid : dpuuid,
       DPID : dpid
    }
 });
```

>[!NOTE]
>
>및 키에 대한 ID 값을 제공하는 코드를 프로그래밍 방식으로 개발해야 `d_dpuuid``d_dpid` 합니다.

### DIL 인스턴스화 후 ID 전달

>[!NOTE]
>
>다른 조합으로 [!DNL API] 전화를 걸면 `declaredID` 해당 호출에 대해서만 새 조합이 사용됩니다. 추가 일반 이벤트 호출은 원래 `DIL.create``declaredID` 조합을 사용합니다.

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## 요청/응답 예제 {#request-response-examples}

요청은 데이터 공급자와 사용자 ID를 Audience Manager로 보냅니다.

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

응답은 페이지 도메인의 퍼스트 파티 쿠키에 기록되는 Audience Manager ID (예: `UUID`) 를 반환합니다.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## 전화 걸기 및 옵트아웃 안 함 {#do-not-target}

[!UICONTROL declared ID] 이 프로세스는 웹 사이트별로 대상 관리자가 타깃팅되지 않도록 사이트 방문자 기본 설정을 준수합니다. Audience Manager에서 옵트아웃 요청을 받으면은 [!UICONTROL DCS] Audience Manager 사용자 ID 대신 빈 [!DNL JSON] 개체를 반환합니다.
