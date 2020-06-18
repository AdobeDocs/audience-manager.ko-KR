---
description: 선언된 ID가 작동하는 방식, 절차, 코드 예제 및 변수를 설정합니다.
keywords: id sync
seo-description: 선언된 ID가 작동하는 방식, 절차, 코드 예제 및 변수를 설정합니다.
seo-title: 선언된 ID
solution: Audience Manager
title: 선언된 ID
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '1230'
ht-degree: 10%

---


# 선언된 ID {#declared-ids}

선언된 ID가 작동하는 방식, 절차, 코드 예제 및 변수를 설정합니다.

## 선언된 ID 타게팅 {#declared-id-targeting}

타사 쿠키와 같은 지속적인 스토리지 메커니즘을 사용하거나 승인하지 않는 디바이스 또는 브라우저에서 사용자 ID를 교환하고 동기화할 수 있습니다. [!DNL Audience Manager]

<!-- declared_id_about.xml -->

## 선언된 ID 타깃팅 목적 {#declared-id-targeting-purpose}

일부 브라우저 및 대부분의 모바일 장치에서는 타사 쿠키를 허용하지 않습니다. 따라서 사이트 방문자에 대한 정보를 유지하거나 영구 ID를 할당하기가 어렵습니다. 이 문제를 해결하려면 이벤트 호출 [!DNL Audience Manager] 에 [!UICONTROL DIL] 합격할 수 있도록 [!UICONTROL declared IDs] 사용합니다. 또한, a는 의 모든 솔루션에서 동일한 사용자에게 적용되는 범용 ID로 작동할 [!UICONTROL declared ID] 수 [!DNL Experience Cloud]있습니다. 다음 표에서는 ID 타깃팅/일치 프로세스에 대해 설명합니다.

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
   <td colname="col2"> <p>이 작업을 수행하려면 페이지에 <span class="wintitle"> DIL </span> 과 <a href="https://docs.adobe.com/content/help/ko-KR/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform ID 서비스 </a> 코드가 있어야 합니다. <span class="wintitle"> DIL은 Adobe Experience Platform ID 서비스 </span> 가 제공하는 <span class="wintitle"> 기능에서 Audience Manager에 </span> 대한 <code> setVisitorID </code> 에 대한 <span class="keyword"> 전달 범위 </span> <span class="keyword"> </span>에서 선언된 ID를 가져옵니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>일치 ID</b> </td> 
   <td colname="col2"> <p>Audience Manager은 클라이언트 및 방문자 ID와 시스템의 해당 ID를 일치시킵니다. 일치하는 ID가 없는 경우 Audience Manager은 새 ID를 만들어 클라이언트 및 방문자 ID와 연결합니다. </p> <p> <p>참고:  가장 최근 매핑은 ID가 두 개 이상의 Audience Manager ID에 매핑되는 경우에 사용됩니다. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>반환 ID</b> </td> 
   <td colname="col2"> <p>Audience Manager은 동기화된 ID를 클라이언트 도메인 또는 애플리케이션의 퍼스트 파티 쿠키(또는 기타 주소 지정 가능 저장소 공간)에 기록합니다. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>후속 이벤트 호출</b> </td>
   <td colname="col2"> <p>추가 이벤트 호출은 클라이언트의 도메인에서 Audience Manager ID를 읽은 후 Audience Manager으로 전송합니다. </p> </td>
  </tr> 
 </tbody>
</table>

시작하려면 데이터 수집에 사용할 사이트 [!DNL Experience Cloud] [!UICONTROL DIL] 의 페이지와 ID 서비스를 구성해야 합니다. DIL [생성](../dil/dil-class-overview/dil-create.md#dil-create) 및 [선언된 ID 변수를 참조하십시오](../features/declared-ids.md#declared-id-variables).

## 옵트아웃 통화 {#opt-out-calls}

이 [!UICONTROL declared ID] 프로세스는 웹 사이트별 타깃팅 [!DNL Audience Manager] 을 옵트아웃하기 위해 사이트 방문자 기본 설정을 적용합니다. 옵트아웃 요청을 [!DNL Audience Manager] 받으면, [!DNL JSON] 에서 반환되는 [!DNL DCS] 오류 코드 171에 사용자 ID 대신 &quot;수신 거부 태그가 발생했습니다.&quot;라는 메시지가 포함된 [!DNL Audience Manager] 오류 코드가 포함됩니다.

* [!DNL Audience Manager] 옵트아웃이 [!UICONTROL declared ID] 옵트아웃으로 [!DNL Audience Manager] 들어올 수 [!UICONTROL UUID] [!DNL URL]있습니다.
* 옵트아웃은 [!UICONTROL declared ID] 파트너별로 [!UICONTROL 프로필 캐시 서버([!UICONTROL PCS])에 저장됩니다. 사용하는 플랫폼 수준 옵트아웃은 없습니다 [!UICONTROL declared IDs]. 또한, [!DNL Audience Manager] 사용자를 가장자리에서 특정 영역에서 옵트아웃합니다(옵트아웃은 [!DNL DCS] 지역을 넘지 않음).

데이터 수집 [의](../overview/data-security-and-privacy/data-privacy.md) 제외에 대한 자세한 내용은 데이터 개인 정보를 참조하십시오.

## 선언된 ID 옵트아웃 예 {#opt-out-examples}

You can make a [!UICONTROL declared ID] opt-out requests with the `d_cid` and `d_cid_ic` key-value pairs. `d_dpid` 및 `d_dpuuid`와 같은 기존 매개 변수는 여전히 작동하지만 더 이상 사용되지 않는 것으로 간주됩니다. [CID가 DPID 및 DPUUID 대체](../reference/cid.md)를 참조하십시오. 예에서 *기울임꼴*&#x200B;은 가변 자리 표시자를 나타냅니다.

### CID 및 CID_IC가 있는 옵트아웃

설명 및 구문이 필요하면 [선언된 ID에 대한 URL 변수 및 구문](../features/declared-ids.md#variables-and-syntax)을 참조하십시오.

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 옵트아웃에 사용하는 값 </th> 
   <th colname="col2" class="entry"> 코드 샘플 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>데이터 공급자 ID 및 사용자 ID. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout.jpg?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>통합 코드 및 사용자 ID. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>다중 <code> d_cid </code> 및 <code> d_cid_ic </code> 키-값 쌍. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### DPID, DPUUID 및 UUID가 포함된 옵트아웃(더 이상 사용되지 않음)

이러한 메서드는 여전히 작동하지만 더 이상 사용되지 않는 것으로 간주됩니다. 이 정보는 이전 목적 및 참조 자료로 제공됩니다. 기존 옵트아웃에는 다음이 포함됩니다.

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 옵트아웃(더 이상 사용되지 않음) </th> 
   <th colname="col2" class="entry"> 코드 샘플 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid </code>  </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid=AAM ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>파트너 수준 옵트아웃 </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>파트너 수준 옵트아웃은 이 <code> dpid </code> + 쌍의 최신 매핑을 AAM UUID에 <code> dpuuid </code> 위해 저장됩니다. 이전에 기존 매핑이 없는 경우 Audience Manager은 요청에 쿠키에 AAM UUID가 포함되어 있는지 확인하고, 포함되어 있는 경우 이를 사용하여 옵트아웃을 저장합니다. 그렇지 않으면 Audience Manager이 새 AAM UUID를 생성하고 그 아래에 옵트아웃을 저장합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> 및 명시적 <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> 항상 우선합니다. + <code> dpid </code> 조합이 다른 AAM UUID에 매핑되면 옵트아웃은 요청에서 전달된 AAM UUID 아래에 저장됩니다( <code> dpuuid </code> <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## 선언된 ID에 대한 변수 및 구문 {#variables-and-syntax}

<!-- c_declared_id_var_syntax.xml -->

다음 표에는 데이터 공급자 ID와 사용자 ID 또는 통합 코드를 전달하는 키-값 쌍(사용되는 경우)이 나와 있습니다. [!DNL Audience Manager] Note, *italics* indicates a variable placeholder. 이렇게 쉽게 읽을 수 있도록 공백이 추가되었습니다.

각 키-값 쌍에서:

* 심볼은 키와 관련 값을 구분합니다. `=`
* 인쇄되지 않는 [!DNL ASCII] 문자는 값을 `%01` 구분합니다.

<table id="table_DFA9A584A5DE40669EAF0DB62DDC5AAF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 변수 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid =<i>data provider ID</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>하나의 키-값 쌍에 데이터 공급자 ID와 연결된 고유 사용자 ID가 들어 있습니다. <code> d_cid </code> 교체 <code> d_dpid </code> 및 <code> d_dpuuid </code>를 참조하십시오. <a href="../reference/cid.md">CID가 DPID 및 DPUUID 대체</a>를 참조하십시오 . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>단일 키-값 쌍에 통합 코드와 관련 고유 사용자 ID가 들어 있습니다. <code> d_cid_ic </code> 교체 <code> d_dpid </code> 및 <code> d_dpuuid </code>더 이상 사용되지 않지만 여전히 지원됩니다. <a href="../reference/cid.md">CID가 DPID 및 DPUUID 대체</a>를 참조하십시오 . </p> </td> 
  </tr> 
 </tbody> 
</table>

## 샘플 이벤트 호출 {#sample-event-calls}

이러한 키-값 쌍 및 필수 구문이 주어지면 아래와 같이 이벤트를 호출합니다.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 이벤트 호출 포함 </th> 
   <th colname="col2" class="entry"> 코드 샘플 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>데이터 공급자 ID 및 사용자 ID. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>통합 코드 및 사용자 ID. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>다중 <code> d_cid </code> 및 <code> d_cid_ic </code> 키-값 쌍. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 선언된 ID 변수 {#declared-id-variables}

선언된 ID를 [!UICONTROL DIL] [!DNL Audience Manager.]

## DIL은 Adobe Experience Platform ID 서비스를 사용하여 선언된 ID 전달 {#dil-id-service-pass-declared-ids}

<!-- r_dil_declared_id_vars.xml -->

Adobe Experience Platform [ID 서비스](https://docs.adobe.com/content/help/ko-KR/id-service/using/home.html)와 함께 사용할 때 더 이상 사용되지 않는 [!UICONTROL declared IDs] 변수와 `dpid` 함께 전달하지 않아도 `dpuuid` 됩니다. 대신, 현재 버전의 Flash Player는 [!UICONTROL DIL] 함수 `visitorService` 에서 Flash Player [!UICONTROL declared IDs] 를 가져오는 기능을 `setCustomerIDs` [!UICONTROL Adobe Experience Platform Identity Service]사용합니다. For more information, see [Customer IDs and Authentication States](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). 아래 `visitorService` 와 `DIL.create` 같이 전화하셨을 것입니다.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

키-값 쌍에서 `namespace` 는 `MCORG` [!DNL Experience Cloud] 조직 ID입니다. 이 ID가 없는 경우 [!UICONTROL Administration] 대시보드 섹션 [!DNL Experience Cloud] 에서 찾을 수 있습니다. 이 대시보드를 보려면 관리자 권한이 필요합니다. See [Administration: Core Services](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html).

## 사용되지 않는 함수 {#deprecated-functions}

최신 버전의 [!UICONTROL DIL] (6.2 이상)에서는 이러한 키-값 쌍을 사용하여 전달할 필요가 없습니다 [!UICONTROL declared IDs]. 이는 [!UICONTROL DIL] 이제 위의 코드 샘플에 표시된 `visitorService` 함수에 의존하기 때문입니다. 이 함수 [!UICONTROL declared IDs] [!UICONTROL Adobe Experience Platform Identity Service]는 하지만 이전 및 이전 목적을 위해 이 변수를 여기에서 참조합니다. Adobe Experience Manager Forms에서 JavaScript를 가져오는 방법 `DIL.create` 에 대한 예는 아래 코드 [!UICONTROL declared ID] 를 참조하십시오 [!UICONTROL Visitor ID Service].
다음 표에서는 개체가 사용하는 기존 변수에 대해 `declaredId` 설명합니다.

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
   <td colname="col3"> <p>Audience Manager에서 지정한 데이터 파트너 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> 문자열 </td> 
   <td colname="col3"> <p>사용자에 대한 데이터 제공업체의 고유한 ID입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

### `DPID` 및 `DPUUID`

[!DNL Audience Manager] 시스템의 해당 사용자 ID `DPID` 및 `DPUUID` 를 조합하여 일치시킵니다. ID가 없는 경우 새 사용자 ID를 [!DNL Audience Manager] 만들고 이 ID를 조합에 `DPID/DPUUID` 동기화합니다. 사용자 ID와 [!DNL Audience Manager] 일치하거나 사용자 ID를 만들면( `UUID`) 클라이언트의 도메인(퍼스트 파티 쿠키) 또는 기타 로컬 저장소의 쿠키에 대한 [!DNL JSON] 응답에서 해당 ID를 반환합니다.

v6.1 이전 버전을 사용하는 경우 이 함수를 [!UICONTROL DIL] 호출합니다. 그러나 이 함수는 더 이상 사용되지 않으며 대신 URL에서 가져오는 새 버전 [!UICONTROL declared IDs] 을 사용합니다 [!DNL Adobe Experience Platform Identity Service].

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
>키와 키의 ID 값을 제공하는 코드를 프로그래밍 방식으로 개발해야 `d_dpuuid` 합니다 `d_dpid` .

### DIL 인스턴스화 후 ID 전달

>[!NOTE]
>
>다른 조합으로 [!DNL API] 호출을 하는 경우 새로운 `declaredID` 조합이 해당 호출에 대해서만 사용됩니다. 추가적인 일반 이벤트 호출에서는 원래 `DIL.create` 조합을 `declaredID` 사용합니다.

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## 요청/응답 예 {#request-response-examples}

요청은 데이터 공급자 및 사용자 ID를 다음 주소로 보냅니다. [!DNL Audience Manager]

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

응답은 페이지 도메인의 퍼스트 파티 쿠키에 기록된 Audience Manager ID( `UUID`예:)를 반환합니다.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Target 및 옵트아웃 호출 안 함 {#do-not-target}

이 [!UICONTROL declared ID] 프로세스는 웹 사이트별 타깃팅 [!DNL Audience Manager] 을 옵트아웃하기 위해 사이트 방문자 기본 설정을 적용합니다. 옵트아웃 요청을 받으면 [!DNL Audience Manager] 사용자 ID 대신 빈 [!DNL DCS] 개체를 [!DNL JSON] [!DNL Audience Manager] 반환합니다.

>[!MORELIKETHIS]
>
>* [CID가 DPID 및 DPUUID 대체](../reference/cid.md)

