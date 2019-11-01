---
description: 선언된 ID의 작동 방식, 설정 절차, 코드 예제 및 변수.
keywords: id 동기화
seo-description: 선언된 ID의 작동 방식, 설정 절차, 코드 예제 및 변수.
seo-title: 선언된 ID
solution: Audience Manager
title: 선언된 ID
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# 선언된 ID {#declared-ids}

선언된 ID의 작동 방식, 설정 절차, 코드 예제 및 변수.

## 선언된 ID 타게팅 {#declared-id-targeting}

타사 쿠키와 같은 지속적인 스토리지 메커니즘을 사용하거나 수용하지 않는 디바이스 또는 브라우저에서 사용자 ID를 Audience Manager와 교환하고 동기화할 수 있습니다.

<!-- declared_id_about.xml -->

## 선언된 ID 타깃팅 목적 {#declared-id-targeting-purpose}

일부 브라우저 및 대부분의 모바일 장치는 타사 쿠키를 허용하지 않습니다. 따라서 사이트 방문자에 대한 정보를 유지하거나 영구 ID를 할당하기가 어렵습니다. 이 문제를 해결하기 위해 Audience Manager [!UICONTROL DIL] 는 이벤트 호출에 [!UICONTROL declared IDs] 전달할 수 있도록 하는 데 사용합니다. 또한, [!UICONTROL declared ID] 는 의 모든 솔루션에서 동일한 사용자에게 적용되는 범용 ID로 작동할 수 [!DNL Experience Cloud]있습니다. 다음 표에서는 ID 타깃팅/일치 프로세스에 대해 설명합니다.

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
   <td colname="col2"> <p>작동하려면 페이지에 <span class="wintitle"> DIL </span> 및 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID 서비스 </a> 코드가 있어야 합니다. <span class="wintitle"> DIL은 Experience Cloud ID 서비스에서 </span> 제공하는 <span class="wintitle"> 기능에서 선언된 ID를 </span> 받고 해당 ID를 Audience Manager에 <code> setVisitorID </code> <span class="keyword"> </span> <span class="keyword"> </span>전달합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>일치 ID</b> </td> 
   <td colname="col2"> <p>Audience Manager는 클라이언트 및 방문자 ID와 시스템의 해당 ID를 일치시키려고 시도합니다. 일치하는 ID가 없으면 Audience Manager가 새 ID를 만들어 클라이언트 및 방문자 ID와 연결합니다. </p> <p> <p>참고: 가장 최근 매핑은 ID가 둘 이상의 Audience Manager ID에 매핑되는 경우에 사용됩니다. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>반환 ID</b> </td> 
   <td colname="col2"> <p>Audience Manager는 동기화된 ID를 클라이언트 도메인 또는 애플리케이션의 퍼스트 파티 쿠키(또는 기타 주소 지정 가능한 스토리지 공간)에 기록합니다. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>후속 이벤트 호출</b> </td>
   <td colname="col2"> <p>추가 이벤트 호출은 클라이언트의 도메인에서 Audience Manager ID를 읽은 후 Audience Manager로 보냅니다. </p> </td>
  </tr> 
 </tbody>
</table>

시작하려면 데이터 수집에 사용할 사이트 페이지와 [!DNL Experience Cloud] 사이트의 [!UICONTROL DIL] 페이지에서 ID 서비스를 구성해야 합니다. DIL [작성](../dil/dil-class-overview/dil-create.md#dil-create) 및 선언된 ID [변수를 참조하십시오](../features/declared-ids.md#declared-id-variables).

## 옵트아웃 호출 {#opt-out-calls}

이 [!UICONTROL declared ID] 프로세스는 웹 사이트별로 Audience Manager 타깃팅을 옵트아웃하기 위해 사이트 방문자 기본 설정을 적용합니다. Audience Manager가 옵트아웃 요청을 받으면, 에서 [!DNL JSON] 반환한 오류 코드 171이 [!UICONTROL DCS] 포함되며, Audience Manager 사용자 ID가 아닌 "옵트아웃 태그 발견 발견"이 표시됩니다.

* Audience Manager는 Audience Manager와 함께 [!UICONTROL declared ID] 옵트아웃을 전달할 [!UICONTROL UUID] 수 [!DNL URL]있습니다.
* 옵트아웃은 [!UICONTROL declared ID] 파트너별로 [!UICONTROL 프로필 캐시 서버([!UICONTROL PCS])에 저장됩니다. 사용하는 플랫폼 수준 옵트아웃은 없습니다 [!UICONTROL declared IDs]. 또한 Audience Manager는 사용자를 가장자리의 특정 영역에서 옵트아웃합니다(옵트아웃은 [!UICONTROL DCS] 지역을 벗어나지 않음).

데이터 [수집](../overview/data-security-and-privacy/data-privacy.md) 제외에 대한 자세한 내용은 데이터 개인 정보를 참조하십시오.

## 선언된 ID 옵트아웃 예 {#opt-out-examples}

및 [!UICONTROL declared ID] `d_cid` `d_cid_ic` 키-값 쌍으로 옵트아웃 요청을 만들 수 있습니다. 및 같은 기존 매개 변수는 `d_dpid` 여전히 작동하지만 `d_dpuuid` 더 이상 사용되지 않는 것으로 간주됩니다. [CID가 DPID 및 DPUUID 대체](../reference/cid.md)를 참조하십시오. In the examples, *italics* indicates a variable placeholder.

### CID 및 CID_IC가 있는 옵트아웃

설명 및 구문은 선언된 ID [에 대한 URL 변수 및 구문을 참조하십시오](../features/declared-ids.md#variables-and-syntax).

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 다음을 사용하여 옵트아웃 </th> 
   <th colname="col2" class="entry"> 코드 샘플 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>데이터 공급자 ID 및 사용자 ID입니다. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout.jpg?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>통합 코드 및 사용자 ID입니다. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>다중 <code> d_cid </code> 및 <code> d_cid_ic </code> 키-값 쌍. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### DPID, DPUUID 및 UUID가 포함된 옵트아웃(더 이상 사용되지 않음)

이러한 메서드는 여전히 작동하지만 더 이상 사용되지 않는 것으로 간주됩니다. 이 정보는 이전 목적 및 참조를 위해 제공됩니다. 기존 옵트아웃에는 다음이 포함됩니다.

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
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>파트너 수준 옵트아웃은 이 <code> dpid </code> + <code> dpuuid </code> 쌍을 AAM UUID에 최신 매핑하기 위해 저장됩니다. 이전에 기존 매핑이 없는 경우 Audience Manager는 요청에 쿠키에 AAM UUID가 포함되어 있는지 확인하고, 포함되어 있는 경우 이를 사용하여 옵트아웃을 저장합니다. 그렇지 않으면 Audience Manager가 새 AAM UUID를 생성하고 그 아래에 옵트아웃을 저장합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> 및 명시적 <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> 항상 우선합니다. + <code> dpid </code> 조합이 다른 AAM UUID에 매핑되면 옵트아웃은 요청에서 전달된 AAM UUID 아래에 저장됩니다( <code> dpuuid </code> <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## 선언된 ID에 대한 변수 및 구문 {#variables-and-syntax}

<!-- c_declared_id_var_syntax.xml -->

다음 표에는 [!DNL Audience Manager] 데이터 공급자 ID와 사용자 ID 또는 통합 코드를 전달하는 키-값 쌍이 나와 있습니다(사용되는 경우). Note, *italics* indicates a variable placeholder. 이러한 내용을 쉽게 읽을 수 있도록 공백이 추가되었습니다.

각 키-값 쌍에서:

* 기호는 키와 관련 값을 구분합니다. `=`
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
   <td colname="col2"> <p>단일 키-값 쌍에 데이터 공급자 ID와 연결된 고유한 사용자 ID가 들어 있습니다. <code> d_cid </code> 를 대체합니다. 이 <code> d_dpid </code> <code> d_dpuuid </code>은 더 이상 사용되지 않지만 여전히 지원됩니다. <a href="../reference/cid.md">CID가 DPID 및 DPUUID 대체</a>를 참조하십시오 . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>단일 키-값 쌍에 통합 코드와 관련 고유 사용자 ID가 들어 있습니다. <code> d_cid_ic </code> 은 <code> d_dpid </code> 및 를 대체하며, <code> d_dpuuid </code>이 값은 더 이상 사용되지 않지만 여전히 지원됩니다. <a href="../reference/cid.md">CID가 DPID 및 DPUUID 대체</a>를 참조하십시오 . </p> </td> 
  </tr> 
 </tbody> 
</table>

## 샘플 이벤트 호출 {#sample-event-calls}

이러한 키-값 쌍과 필수 구문이 주어지면 아래와 같이 이벤트 호출을 수행합니다.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 이벤트 호출 포함 </th> 
   <th colname="col2" class="entry"> 코드 샘플 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>데이터 공급자 ID 및 사용자 ID입니다. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>통합 코드 및 사용자 ID입니다. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>다중 <code> d_cid </code> 및 <code> d_cid_ic </code> 키-값 쌍. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 선언된 ID 변수 {#declared-id-variables}

선언된 ID를 [!UICONTROL DIL][!DNL Audience Manager.]

## DIL은 Experience Cloud ID 서비스를 사용하여 선언된 ID를 전달합니다. {#dil-id-service-pass-declared-ids}

<!-- r_dil_declared_id_vars.xml -->

Experience Cloud [ID Service와](https://marketing.adobe.com/resources/help/en_US/mcvid/)함께 사용하면 더 이상 사용되지 않는 [!UICONTROL declared IDs] 변수와 `dpid` `dpuuid` 함께 로그인할 필요가 없습니다. 대신, 의 현재 버전은 [!UICONTROL DIL] 의 `visitorService` 함수에서 함수를 [!UICONTROL declared IDs] 가져옵니다 `setCustomerIDs` [!UICONTROL Experience Cloud ID Service]. For more information, see [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html). 아래와 `visitorService` 같이 전화를 `DIL.create` 걸었습니다.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

키- `namespace` 값 쌍에서 `MCORG` 조직 ID가 [!DNL Experience Cloud] 됩니다. 이 ID가 없는 경우 [!UICONTROL Administration] 대시보드의 [!DNL Experience Cloud] 섹션에서 찾을 수 있습니다. 이 대시보드를 보려면 관리자 권한이 필요합니다. See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

## 사용되지 않는 함수 {#deprecated-functions}

최신 버전 [!UICONTROL DIL] (6.2 이상)을 사용하면 이러한 키-값 쌍을 사용하여 전달할 필요가 [!UICONTROL declared IDs]없습니다. 이는 [!UICONTROL DIL] 이제 위의 코드 샘플에 표시된 `visitorService` 함수에 의존하기 때문입니다. 이 함수는 [!UICONTROL declared IDs] 에서 가져옵니다 [!UICONTROL Experience Cloud ID Service]. 하지만 이전 및 이전 목적으로 이 변수를 여기에서 참조합니다. Adobe Experience Manager에서 Adobe Experience Manager Forms를 `DIL.create` 가져오는 방법을 살펴보려면 아래 코드를 [!UICONTROL declared ID] [!UICONTROL Visitor ID Service]참조하십시오.
다음 표에서는 `declaredId` 객체가 사용하는 기존 변수에 대해 설명합니다.

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

Audience Manager는 시스템의 결합된 `DPID` `DPUUID` 사용자 ID와 해당 사용자 ID를 비교하여 일치시킵니다. ID가 없는 경우 Audience Manager가 새 사용자 ID를 만들고 이 ID를 `DPID/DPUUID` 조합에 동기화합니다. Audience Manager가 사용자 ID와 일치하거나 사용자 ID( `UUID`)를 만들면 클라이언트의 도메인(퍼스트 파티 쿠키) 또는 기타 로컬 저장소의 쿠키에 대한 [!DNL JSON] 응답에서 해당 ID가 반환됩니다.

v6.1 또는 이전 버전을 사용하는 경우 이 함수를 [!UICONTROL DIL] 호출합니다. 그러나 이 함수 대신 에서 가져오는 새 [!UICONTROL declared IDs] 버전이 사용됩니다 [!UICONTROL Experience Cloud ID Service].

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
>참고, `d_dpuuid` 및 `d_dpid` 키에 대한 ID 값을 제공하는 코드를 프로그래밍 방식으로 개발해야 합니다.

### DIL 인스턴스화 후 ID 전달

>[!NOTE]
>
>다른 조합으로 [!DNL API] 전화를 하는 경우 새 `declaredID` 조합이 해당 호출에 대해서만 사용됩니다. 추가적인 정규 이벤트 호출은 원래 `DIL.create` `declaredID` 조합을 사용합니다.

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## 요청/응답 예 {#request-response-examples}

요청은 데이터 공급자 및 사용자 ID를 Audience Manager로 보냅니다.

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

이 응답은 페이지 도메인의 퍼스트 파티 쿠키에 기록된 Audience Manager ID(예: `UUID`)를 반환합니다.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## 타깃팅 및 옵트아웃 호출 안 함 {#do-not-target}

이 [!UICONTROL declared ID] 프로세스는 웹 사이트별로 Audience Manager 타깃팅을 옵트아웃하기 위해 사이트 방문자 기본 설정을 적용합니다. Audience Manager가 옵트아웃 요청을 받으면 Audience Manager 사용자 ID 대신 빈 [!UICONTROL DCS] [!DNL JSON] 개체를 반환합니다.

>[!MORELIKETHIS]
>
>* [CID가 DPID 및 DPUUID 대체](../reference/cid.md)

