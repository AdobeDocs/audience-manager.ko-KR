---
description: 선언된 ID의 작동 방식, 절차, 코드 예제 및 변수를 설정합니다.
keywords: id 동기화
seo-description: How declared IDs work, set up procedures, code examples, and variables.
seo-title: Declared IDs
solution: Audience Manager
title: 선언된 ID
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
feature: ID Syncs
exl-id: a480671a-797d-405d-905d-98ab4ef71369
source-git-commit: e17eedfb94f2936c61298c44f3d556bae254b2a7
workflow-type: tm+mt
source-wordcount: '1151'
ht-degree: 8%

---

# [!UICONTROL Declared IDs] {#declared-ids}

[!UICONTROL declared IDs]의 작동 방식, 프로시저, 코드 예제 및 변수를 설정합니다.

## [!UICONTROL Declared ID] 타겟 지정 {#declared-id-targeting}

타사 [!DNL Audience Manager]과(와) 같이 영구 저장소 메커니즘을 사용하거나 허용하지 않는 장치 또는 브라우저에서 사용자 ID를 [!DNL cookies]과(와) 교환하고 동기화합니다.

## [!UICONTROL Declared ID] 타깃팅의 목적 {#declared-id-targeting-purpose}

일부 브라우저 및 대부분의 모바일 장치에서는 서드파티 [!DNL cookies]을(를) 허용하지 않습니다. 따라서 사이트 방문자에 대한 정보를 유지하거나 영구 ID를 할당하는 것이 어렵습니다. 이 문제를 해결하기 위해 [!DNL Audience Manager]은(는) [!UICONTROL DIL]을(를) 사용하여 이벤트 호출 시 [!UICONTROL declared IDs]을(를) 전달할 수 있도록 합니다. 또한 [!UICONTROL declared ID]은(는) [!DNL Experience Cloud]의 모든 솔루션에서 동일한 사용자에게 적용되는 유니버설 ID로 사용할 수 있습니다. 다음 표에서는 ID 타겟팅/일치 프로세스에 대해 설명합니다.

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
   <td colname="col2"> <p>작업을 수행하려면 페이지에 <span class="wintitle"> DIL </span>과(와) <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ko" format="https" scope="external"> Adobe Experience Platform Identity 서비스 </a> 코드가 필요합니다. <span class="wintitle"> DIL </span>은(는) <span class="wintitle"> Adobe Experience Platform Identity 서비스 </span>에서 제공하는 <code> setVisitorID </code> 함수에서 <span class="keyword">개의 선언된 ID </span>을(를) 가져와서 <span class="keyword"> Audience Manager </span>에 전달합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>일치 ID</b> </td> 
   <td colname="col2"> <p>Audience Manager은 클라이언트 및 방문자 ID를 시스템의 해당 ID와 일치시키려고 합니다. 일치하는 ID가 없으면 Audience Manager에서 새 ID를 만들어 클라이언트 및 방문자 ID와 연결합니다. </p> <p> <p>참고: ID가 둘 이상의 Audience Manager ID에 매핑되는 경우 가장 최근 매핑이 사용됩니다. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>반환 ID</b> </td> 
   <td colname="col2"> <p>Audience Manager은 동기화된 ID를 클라이언트 도메인 또는 애플리케이션의 자사 쿠키(또는 기타 주소 지정 가능한 스토리지 공간)에 기록합니다. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>후속 이벤트 호출</b> </td>
   <td colname="col2"> <p>추가 이벤트 호출은 클라이언트의 도메인에서 Audience Manager ID를 읽고 Audience Manager으로 보냅니다. </p> </td>
  </tr> 
 </tbody>
</table>

시작하려면 사이트의 페이지에서 데이터 수집에 사용할 [!DNL Experience Cloud] ID 서비스와 [!UICONTROL DIL]을(를) 구성해야 합니다. [DIL 만들기](../dil/dil-class-overview/dil-create.md#dil-create) 및 [선언된 ID 변수](../features/declared-ids.md#declared-id-variables)를 참조하십시오.

## 옵트아웃 호출 {#opt-out-calls}

[!UICONTROL declared ID] 프로세스는 웹 사이트에서 [!DNL Audience Manager] 타깃팅을 옵트아웃하도록 사이트 방문자 환경 설정을 적용합니다. [!DNL Audience Manager]이(가) 옵트아웃 요청을 받으면 [!DNL JSON]이(가) 반환한 [!DNL DCS]에 `Encountered opt out tag` 사용자 ID 대신 [!DNL Audience Manager] 메시지가 있는 오류 코드 171이 포함됩니다.

* [!DNL Audience Manager]은(는) [!UICONTROL declared ID]의 [!DNL Audience Manager] [!UICONTROL UUID]과(와) 함께 [!DNL URL] 옵트아웃을 전달할 수 있습니다.
* [!UICONTROL declared ID] 옵트아웃은 파트너별로 [!UICONTROL Profile Cache Server]&#x200B;([!UICONTROL PCS])에 저장됩니다. [!UICONTROL declared IDs]을(를) 사용하는 플랫폼 수준 옵트아웃이 없습니다. 또한 [!DNL Audience Manager]은(는) 가장자리의 특정 영역에서 사용자를 옵트아웃합니다(옵트아웃은 [!DNL DCS] 영역과 교차하지 않음).

데이터 수집 옵트아웃에 대한 자세한 내용은 [데이터 개인 정보](../overview/data-security-and-privacy/data-privacy.md)을 참조하세요.

## [!UICONTROL Declared ID] 옵트아웃 예 {#opt-out-examples}

[!UICONTROL declared ID] 및 `d_cid` 키-값 쌍으로 `d_cid_ic` 옵트아웃을 요청할 수 있습니다. `d_dpid` 및 `d_dpuuid`와 같은 기존 매개 변수는 여전히 작동하지만 더 이상 사용되지 않는 것으로 간주됩니다. [CID가 DPID 및 DPUUID 대체](../reference/cid.md)를 참조하십시오. 예에서 *기울임꼴*&#x200B;은 가변 자리 표시자를 나타냅니다.

### [!UICONTROL CID] 및 [!UICONTROL CID_IC]&#x200B;(으)로 옵트아웃

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
   <td colname="col1"> <p>여러 <code> d_cid </code> 및 <code> d_cid_ic </code> 키-값 쌍입니다. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL DPID], [!UICONTROL DPUUID] 및 [!UICONTROL UUID]의 옵트아웃(더 이상 사용되지 않음)

이러한 메서드는 여전히 작동하지만 더 이상 사용되지 않는 것으로 간주됩니다. 이 정보는 레거시 목적 및 참조를 위해 제공됩니다. 레거시 옵트아웃에는 다음이 포함됩니다.

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 옵트아웃(더 이상 사용되지 않음) </th> 
   <th colname="col2" class="entry"> 코드 샘플 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid </code>만 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid=AAM ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>파트너 수준 옵트아웃 </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>이 <code> dpid </code> + <code> dpuuid </code> 쌍을 AAM UUID에 매핑하기 위해 파트너 수준 옵트아웃이 저장됩니다. 이전에 존재한 매핑이 없는 경우 Audience Manager은 요청에 쿠키에 AAM UUID가 포함되어 있는지 확인하고 포함되어 있으면 옵트아웃을 저장하는 데 이를 사용합니다. 그렇지 않으면 Audience Manager은 새 AAM UUID를 생성하고 그 아래에 옵트아웃을 저장합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> 및 명시적 <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code>이(가) 항상 우선합니다. <code> dpid </code> + <code> dpuuid </code> 조합이 다른 AAM UUID에 매핑되는 경우 옵트아웃은 요청(<code> d_uuid </code>)에서 전달된 AAM UUID 아래에 저장됩니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared IDs]에 대한 변수 및 구문 {#variables-and-syntax}

다음 표에는 [!DNL Audience Manager] 데이터 공급자 ID와 사용자 ID 또는 통합 코드를 전달하는 키-값 쌍이 나열되어 있습니다(사용되는 경우). *기울임꼴*&#x200B;은(는) 변수 자리 표시자를 나타냅니다. 읽기 쉽도록 공백이 추가되었습니다.

각 키-값 쌍에서:

* `=` 기호는 키와 관련 값을 구분합니다.
* 인쇄되지 않는 [!DNL ASCII] 문자 `%01`이(가) 값을 구분합니다.

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
   <td colname="col2"> <p>단일 키-값 쌍에 데이터 공급자 ID와 관련 고유 사용자 ID를 포함합니다. <code> d_cid </code>은(는) 더 이상 사용되지 않는 것으로 간주되지만 여전히 지원되는 <code> d_dpid </code> 및 <code> d_dpuuid </code>을(를) 대체합니다. <a href="../reference/cid.md"> CID Replaces DPID 및 DPUUID </a> 을(를) 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>단일 키-값 쌍에 통합 코드 및 관련 고유 사용자 ID를 포함합니다. <code> d_cid_ic </code>은(는) 더 이상 사용되지 않지만 여전히 지원되는 <code> d_dpid </code> 및 <code> d_dpuuid </code>을(를) 대체합니다. <a href="../reference/cid.md"> CID Replaces DPID 및 DPUUID </a> 을(를) 참조하십시오. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 샘플 이벤트 호출 {#sample-event-calls}

이러한 키-값 쌍과 필요한 구문이 주어지면 아래와 같이 이벤트를 호출하게 됩니다.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 이벤트 호출에는 다음이 포함됩니다. </th> 
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
   <td colname="col1"> <p>여러 <code> d_cid </code> 및 <code> d_cid_ic </code> 키-값 쌍입니다. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] 변수 {#declared-id-variables}

[!UICONTROL declared IDs]에서 [!UICONTROL DIL]까지 [!DNL Audience Manager.]을(를) 전달하는 데 사용되는 구성 변수를 설명합니다.

## [!UICONTROL DIL]이(가) [!DNL Adobe Experience Platform Identity Service]을(를) 사용하여 [!UICONTROL Declared IDs]을(를) 전달합니다. {#dil-id-service-pass-declared-ids}

[Adobe Experience Platform ID 서비스](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ko)와 함께 사용하는 경우 더 이상 사용되지 않는 [!UICONTROL declared IDs] 및 `dpid` 변수를 사용하여 `dpuuid`을(를) 전달할 필요가 없습니다. 대신 현재 버전의 [!UICONTROL DIL]은(는) `visitorService` 함수를 사용하여 [!UICONTROL declared IDs]의 `setCustomerIDs` 함수에서 [!UICONTROL Adobe Experience Platform Identity Service]을(를) 가져옵니다. 자세한 내용은 [고객 ID 및 인증 상태](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=ko)를 참조하십시오. 아래와 같이 `visitorService`에서 `DIL.create`을(를) 호출합니다.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

`namespace` 키-값 쌍에서 `MCORG`은(는) [!DNL Experience Cloud] 조직 ID입니다. 이 ID가 없으면 [!UICONTROL Administration] 대시보드의 [!DNL Experience Cloud] 섹션에서 찾을 수 있습니다. 이 대시보드를 보려면 관리자 권한이 필요합니다. [Experience Cloud 서비스 시작](https://experienceleague.adobe.com/ko/docs/core-services/interface/services/getting-started)을 참조하세요.

## 더 이상 사용되지 않는 함수 {#deprecated-functions}

최신 버전의 [!UICONTROL DIL]&#x200B;(6.2+)에서는 이러한 키-값 쌍을 사용하여 [!UICONTROL declared IDs]을(를) 전달할 필요가 없습니다. [!UICONTROL DIL]이(가) 이제 위의 코드 샘플에 표시된 `visitorService` 함수에 의존하기 때문입니다. 이 함수는 [!UICONTROL declared IDs]에서 [!UICONTROL Adobe Experience Platform Identity Service]을(를) 가져옵니다. 하지만 여기에서는 이러한 변수를 기록 및 레거시 목적으로 참조하고 있습니다. `DIL.create`에서 [!UICONTROL declared ID]을(를) 가져오도록 [!UICONTROL Visitor ID Service]을(를) 구성하는 방법에 대한 예는 아래 코드를 참조하십시오.
다음 표에서는 `declaredId` 개체에서 사용하는 기존 변수를 설명합니다.

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

### [!UICONTROL DPID] 및 [!UICONTROL DPUUID]

[!DNL Audience Manager]은(는) 결합된 `DPID`과(와) `DPUUID`을(를) 비교하여 시스템의 해당 사용자 ID와 일치시킵니다. ID가 없으면 [!DNL Audience Manager]에서 새 사용자 ID를 만들어 `DPID/DPUUID` 조합에 동기화합니다. [!DNL Audience Manager]이(가) 사용자 ID(`UUID`)와 일치하거나 만들면 클라이언트의 도메인(자사 [!DNL JSON]) 또는 다른 로컬 저장소에 있는 [!DNL cookie]에 대한 [!DNL cookie] 응답에서 해당 ID를 반환합니다.

[!UICONTROL DIL] v6.1 또는 이전 버전을 사용하는 경우 이 함수를 호출합니다. 그러나 이 함수는 [!UICONTROL declared IDs]에서 [!DNL Adobe Experience Platform Identity Service]을(를) 가져오는 새 버전을 위해 더 이상 사용되지 않습니다.

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
>`d_dpuuid` 및 `d_dpid` 키의 ID 값을 제공하는 코드를 프로그래밍 방식으로 개발해야 합니다.

### [!UICONTROL DIL]이(가) 인스턴스화된 후 ID 전달

>[!NOTE]
>
>다른 [!DNL API] 조합으로 `declaredID` 호출을 수행하면 해당 호출에만 새 조합이 사용됩니다. 이후 일반 이벤트 호출에서는 원래 `DIL.create` `declaredID` 조합을 사용합니다.

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## 요청/응답 예 {#request-response-examples}

요청이 데이터 공급자와 사용자 ID를 [!DNL Audience Manager]&#x200B;(으)로 보냅니다.

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

응답이 페이지 도메인의 자사 쿠키에 기록된 Audience Manager ID(예: `UUID`)를 반환합니다.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## 타겟 및 옵트아웃 호출 안 함 {#do-not-target}

[!UICONTROL declared ID] 프로세스는 웹 사이트에서 [!DNL Audience Manager] 타깃팅을 옵트아웃하도록 사이트 방문자 환경 설정을 적용합니다. [!DNL Audience Manager]이(가) 옵트아웃 요청을 받으면 [!DNL DCS]이(가) [!DNL JSON] 사용자 ID 대신 빈 [!DNL Audience Manager] 개체를 반환합니다.

>[!MORELIKETHIS]
>
>* [CID가 DPID 및 DPUUID 대체](../reference/cid.md)
