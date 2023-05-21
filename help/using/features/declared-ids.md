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
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 9%

---

# [!UICONTROL Declared IDs] {#declared-ids}

방법 [!UICONTROL declared IDs] 작업, 프로시저 설정, 코드 예제 및 변수.

## [!UICONTROL Declared ID] 타겟 지정 {#declared-id-targeting}

사용자 ID를 와 교환 및 동기화 [!DNL Audience Manager] 타사 제품과 같이 영구 스토리지 메커니즘을 사용하거나 허용하지 않는 디바이스 또는 브라우저에서 [!DNL cookies].

## 목적 [!UICONTROL Declared ID] 타겟팅 {#declared-id-targeting-purpose}

일부 브라우저 및 대부분의 모바일 장치는 서드파티를 허용하지 않습니다 [!DNL cookies]. 따라서 사이트 방문자에 대한 정보를 유지하거나 영구 ID를 할당하는 것이 어렵습니다. 이 문제를 해결하려면 [!DNL Audience Manager] 사용 [!UICONTROL DIL] 지나가게 해주십시오 [!UICONTROL declared IDs] 이벤트 호출 시. 또한 [!UICONTROL declared ID] 은 의 모든 솔루션에서 동일한 사용자에게 적용되는 범용 ID로 작동합니다 [!DNL Experience Cloud]. 다음 표에서는 ID 타겟팅/일치 프로세스에 대해 설명합니다.

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
   <td colname="col2"> <p>일을 하려면 <span class="wintitle"> DIL </span> 및 <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform ID 서비스 </a> 코드를 표시합니다. <span class="wintitle"> DIL </span> 가져오기 <span class="wintitle"> 선언된 ID </span> 다음에서 <code> setVisitorID </code> 에서 제공하는 함수 <span class="keyword"> Adobe Experience Platform ID 서비스 </span> 를 로 전달합니다. <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>일치 ID</b> </td> 
   <td colname="col2"> <p>Audience Manager은 클라이언트 및 방문자 ID를 시스템의 해당 ID와 일치시키려고 시도합니다. 일치하는 ID가 없으면 Audience Manager은 새 ID를 만들어 클라이언트 및 방문자 ID와 연결합니다. </p> <p> <p>참고: ID가 둘 이상의 Audience Manager ID에 매핑되는 경우 가장 최근 매핑이 사용됩니다. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>반환 ID</b> </td> 
   <td colname="col2"> <p>Audience Manager은 동기화된 ID를 클라이언트 도메인이나 애플리케이션의 자사 쿠키(또는 기타 주소 지정 가능한 스토리지 공간)에 기록합니다. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>후속 이벤트 호출</b> </td>
   <td colname="col2"> <p>추가 이벤트 호출은 클라이언트의 도메인에서 Audience Manager ID를 읽은 후 Audience Manager으로 보냅니다. </p> </td>
  </tr> 
 </tbody>
</table>

시작하려면 다음을 구성해야 합니다. [!DNL Experience Cloud] ID 서비스 [!UICONTROL DIL] 를 추가합니다. 다음을 참조하십시오 [DIL 만들기](../dil/dil-class-overview/dil-create.md#dil-create) 및 [선언된 ID 변수](../features/declared-ids.md#declared-id-variables).

## 옵트아웃 호출 {#opt-out-calls}

다음 [!UICONTROL declared ID] 에서 옵트아웃하도록 사이트 방문자 환경 설정 적용 [!DNL Audience Manager] 웹 사이트별 타기팅. 날짜 [!DNL Audience Manager] 옵트아웃 요청을 수신합니다. [!DNL JSON] 에 의해 반환됨 [!DNL DCS] 오류 코드 171을 포함합니다. `Encountered opt out tag`, 대신 [!DNL Audience Manager] 사용자 ID.

* [!DNL Audience Manager] 다음을 전달할 수 있음: [!UICONTROL declared ID] 와 함께 옵트아웃 [!DNL Audience Manager] [!UICONTROL UUID] 다음에서 [!DNL URL].
* 다음 [!UICONTROL declared ID] 옵트아웃은에 저장됩니다 [!UICONTROL Profile Cache Server] ([!UICONTROL PCS])을 참조하십시오. 을 사용하는 플랫폼 수준 옵트아웃은 없습니다. [!UICONTROL declared IDs]. 또한, [!DNL Audience Manager] 는 가장자리에 있는 특정 영역에서 사용자를 옵트아웃합니다(옵트아웃은 교차하지 않음) [!DNL DCS] 지역).

다음을 참조하십시오 [데이터 개인 정보 보호](../overview/data-security-and-privacy/data-privacy.md) 데이터 수집을 옵트아웃하는 방법에 대한 자세한 정보입니다.

## [!UICONTROL Declared ID] 옵트아웃 예 {#opt-out-examples}

다음을 수행할 수 있습니다. [!UICONTROL declared ID] 을 사용한 옵트아웃 요청 `d_cid` 및 `d_cid_ic` 키-값 쌍입니다. `d_dpid` 및 `d_dpuuid`와 같은 기존 매개 변수는 여전히 작동하지만 더 이상 사용되지 않는 것으로 간주됩니다. [CID가 DPID 및 DPUUID 대체](../reference/cid.md)를 참조하십시오. 예에서 *기울임꼴*&#x200B;은 가변 자리 표시자를 나타냅니다.

### 옵트아웃 [!UICONTROL CID] 및 [!UICONTROL CID_IC]

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
   <td colname="col1"> <p>복수 <code> d_cid </code> 및 <code> d_cid_ic </code> 키-값 쌍입니다. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### 옵트아웃 [!UICONTROL DPID], [!UICONTROL DPUUID], 및 [!UICONTROL UUID] (사용하지 않음)

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
   <td colname="col1"> <p> <code> d_uuid </code>  </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid=AAM ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>파트너 수준 옵트아웃 </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>파트너 수준 옵트아웃은 이 의 최신 매핑을 위해 저장됩니다. <code> dpid </code> + <code> dpuuid </code> AAM UUID에 연결 이전에 존재하는 매핑이 없는 경우 Audience Manager은 요청에 쿠키에 AAM UUID가 포함되어 있는지 확인하고 포함되어 있으면 를 사용하여 옵트아웃을 저장합니다. 그렇지 않으면 Audience Manager은 새 AAM UUID를 생성하고 그 아래에 옵트아웃을 저장합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> 및 명시적 <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> 항상 우선입니다. 다음과 같은 경우 <code> dpid </code> + <code> dpuuid </code> 조합이 다른 AAM UUID에 매핑되면 옵트아웃은 요청에서 전달된 AAM UUID 아래에 저장됩니다( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## 변수 및 구문 [!UICONTROL Declared IDs] {#variables-and-syntax}

다음 표에는 를 전달하는 키-값 쌍이 나와 있습니다 [!DNL Audience Manager] 데이터 공급자 ID 및 사용자 ID 또는 통합 코드(사용되는 경우). 참고, *기울임체* 변수 자리 표시자를 나타냅니다. 읽기 쉽도록 공백이 추가되었습니다.

각 키-값 쌍에서:

* 다음 `=` 기호는 키를 관련 값에서 분리합니다.
* 인쇄되지 않는 [!DNL ASCII] 문자 `%01` 는 값을 구분합니다.

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
   <td colname="col2"> <p>단일 키-값 쌍에 데이터 공급자 ID와 관련 고유 사용자 ID를 포함합니다. <code> d_cid </code> 바꾸기 <code> d_dpid </code> 및 <code> d_dpuuid </code>: 더 이상 사용되지 않는 것으로 간주되지만 계속 지원됩니다. <a href="../reference/cid.md">CID가 DPID 및 DPUUID 대체</a>를 참조하십시오 . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>단일 키-값 쌍에 통합 코드 및 관련 고유 사용자 ID를 포함합니다. <code> d_cid_ic </code> 바꾸기 <code> d_dpid </code> 및 <code> d_dpuuid </code>: 더 이상 사용되지 않지만 계속 지원됩니다. <a href="../reference/cid.md">CID가 DPID 및 DPUUID 대체</a>를 참조하십시오 . </p> </td> 
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
   <td colname="col1"> <p>복수 <code> d_cid </code> 및 <code> d_cid_ic </code> 키-값 쌍입니다. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] 변수 {#declared-id-variables}

전달에 사용되는 구성 변수를 설명합니다. [!UICONTROL declared IDs] 에서 [!UICONTROL DIL] 끝 [!DNL Audience Manager.]

## [!UICONTROL DIL] 를 사용합니다. [!DNL Adobe Experience Platform Identity Service] 전달 [!UICONTROL Declared IDs] {#dil-id-service-pass-declared-ids}

와 함께 사용할 경우 [Adobe Experience Platform ID 서비스](https://experienceleague.adobe.com/docs/id-service/using/home.html), 더 이상 전달할 필요가 없습니다. [!UICONTROL declared IDs] 더 이상 사용되지 않는 `dpid` 및 `dpuuid` 변수를 채우는 방법에 따라 페이지를 순서대로 표시합니다. 대신 의 현재 버전은 [!UICONTROL DIL] 다음에 의존 `visitorService` 함수 가져오기 [!UICONTROL declared IDs] 다음에서 `setCustomerIDs` 의 함수 [!UICONTROL Adobe Experience Platform Identity Service]. 자세한 내용은 [고객 ID 및 인증 상태](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html). 다음을 호출할 수 있습니다. `visitorService` 위치: `DIL.create` 아래와 같이 표시됩니다.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

다음에서 `namespace` 키-값 쌍, `MCORG` 본인 [!DNL Experience Cloud] 조직 ID. 이 ID가 없으면 [!UICONTROL Administration] 의 섹션 [!DNL Experience Cloud] 대시보드입니다. 이 대시보드를 보려면 관리자 권한이 필요합니다. 다음을 참조하십시오 [관리: 핵심 서비스](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services.html).

## 더 이상 사용되지 않는 함수 {#deprecated-functions}

최신 버전의 [!UICONTROL DIL] (6.2+), 이러한 키-값 쌍을 사용하여 전달할 필요가 없습니다 [!UICONTROL declared IDs]. 그 이유는 [!UICONTROL DIL] 은(는) 이제 `visitorService` 위의 코드 샘플에 표시된 함수입니다. 이 함수는 [!UICONTROL declared IDs] 다음에서 [!UICONTROL Adobe Experience Platform Identity Service]. 하지만 여기에서는 이러한 변수를 기록 및 레거시 목적으로 참조하고 있습니다. 구성 방법에 대한 예는 아래 코드를 참조하십시오 `DIL.create` 을(를) 받으려면 [!UICONTROL declared ID] 다음에서 [!UICONTROL Visitor ID Service].
다음 표에서는 `declaredId` 개체:

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
   <td colname="col3"> <p>Audience Manager이 할당한 데이터 파트너 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> 문자열 </td> 
   <td colname="col3"> <p>사용자에 대한 데이터 제공업체의 고유한 ID입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL DPID] 및 [!UICONTROL DPUUID]

[!DNL Audience Manager] 결합된 를 비교하고 일치시킵니다. `DPID` 및 `DPUUID` 을 입력합니다. ID가 없는 경우 [!DNL Audience Manager] 새 사용자 ID를 만들어 와 동기화합니다. `DPID/DPUUID` 결합. 한 번 [!DNL Audience Manager] 사용자 ID(와 일치하거나 사용자 ID를 만듭니다. `UUID`)에서 해당 ID를 반환합니다 [!DNL JSON] 에 대한 응답 [!DNL cookie] 클라이언트의 도메인(자사) [!DNL cookie]) 또는 다른 로컬 저장소입니다.

을(를) 사용할 때 이 함수 호출 [!UICONTROL DIL] v6.1 이하 그러나 이 함수는 다음과 같은 새 버전을 위해 더 이상 사용되지 않습니다. [!UICONTROL declared IDs] 다음에서 [!DNL Adobe Experience Platform Identity Service].

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
>에 대한 ID 값을 제공하는 코드를 프로그래밍 방식으로 개발해야 합니다. `d_dpuuid` 및 `d_dpid` 키.

### 다음 시간 후에 ID 전달 [!UICONTROL DIL] 인스턴스화

>[!NOTE]
>
>다음을 수행하는 경우 [!DNL API] 다른 사용자로 호출 `declaredID` 조합, 새 조합은 해당 호출에만 사용됩니다. 이후 일반 이벤트 호출에서는 원본을 사용합니다. `DIL.create`  `declaredID` 결합.

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## 요청/응답 예 {#request-response-examples}

이 요청은에 데이터 공급자와 사용자 ID를 보냅니다. [!DNL Audience Manager]:

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

응답은 Audience Manager ID를 반환합니다(예: `UUID`): 페이지 도메인의 자사 쿠키에 작성됩니다.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Target 및 옵트아웃 호출 안 함 {#do-not-target}

다음 [!UICONTROL declared ID] 에서 옵트아웃하도록 사이트 방문자 환경 설정 적용 [!DNL Audience Manager] 웹 사이트별 타기팅. 날짜 [!DNL Audience Manager] 옵트아웃 요청을 수신합니다. [!DNL DCS] 빈 을 반환합니다. [!DNL JSON] 개체 대신 [!DNL Audience Manager] 사용자 ID.

>[!MORELIKETHIS]
>
>* [CID가 DPID 및 DPUUID 대체](../reference/cid.md)

