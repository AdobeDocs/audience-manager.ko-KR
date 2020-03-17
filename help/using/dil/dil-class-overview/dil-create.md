---
description: 파트너별 DIL 인스턴스를 만듭니다.
seo-description: 파트너별 DIL 인스턴스를 만듭니다.
seo-title: DIL 만들기
solution: Audience Manager
title: DIL 만들기
uuid: 6e054600-703c-4a97-af2a-8207c50013db
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# DIL 만들기 메서드{#dil-create}

## DIL 만들기 {#dil-create-new}

파트너별 [!UICONTROL DIL] 인스턴스를 만듭니다.

**함수 서명:** `DIL.create: function (initConfig) {}`

**initConfig Elements**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>속성은 `visitorService` 항상 ** 필요합니다. 별도로 명시하지 않는 한 여기에 나열된 기타 속성은 선택 사항입니다.

`initConfig` 다음 요소를 수락합니다.

<table id="table_1334973505F54B238127FED9845B16C4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 이름 </th> 
   <th colname="col2" class="entry"> 유형 </th> 
   <th colname="col3" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> containerNSID </code> </p> </td> 
   <td colname="col2"> <p>정수 </p> </td> 
   <td colname="col3"> <p>이 속성은 ID 동기화를 위해 <span class="keyword">Audience Manager</span>에서 사용하는 컨테이너 ID를 설정합니다. DIL이 여러 사이트에 <code> containerNSID </code><span class="wintitle"> </span> 배포된 경우 설정합니다. 이러한 각 사이트에는 고유한 컨테이너 ID와 ID 동기화가 있습니다. 사이트가 1개만 있는 경우 컨테이너 ID는 기본적으로 0이며 제대로 설정할 필요가 없습니다. 사이트 및 해당 컨테이너 ID 목록을 확인하려면 컨설턴트에게 문의하십시오. </p> <p>Adobe <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Platform ID Service에서 </a>이 <code> idSyncContainerID </code> 속성은 DIL <code> containerNSID </code> 에 <span class="wintitle"> 해당합니다 </span>. 여러 사이트에서 DIL <span class="wintitle"> 및 </span> <i></i> ID 서비스를 사용하는 경우 다음을 참고하십시오. </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">각 사이트에 대해 및 에서 동일한 컨테이너 ID를 <code> containerNSID </code> 설정합니다 <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">DIL <span class="wintitle"> 및 </span> ID 서비스는 모두 ID 동기화를 데이터 수집 iFrame에 보내려고 시도합니다. 그러나 iFrame은 DIL에서 ID <span class="wintitle"> 동기화를 실행하지 </span> 않도록 합니다. 이렇게 하면 중복을 방지할 수 있습니다. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">DIL만 <span class="wintitle"> URL </span> 대상으로 데이터를 <a href="../../features/destinations/destinations.md"> 전송합니다 </a>. </li> 
     </ul> </p> <p>idSyncContainerID <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idsyncontainerid.html" format="https" scope="external"> 도 참조하십시오 </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>개체 </p> </td> 
   <td colname="col3"> 
    <draft-comment> 
     <p>선언된 <a href="../../features/declared-ids.md"> ID 변수를 모든 이벤트 호출에 </a> 대해 Audience Manager에 <span class="keyword"> 전송합니다 </span>. </p> 
    </draft-comment> <p> <code> delcaredId </code> 는 다음 중 하나를 전달합니다. </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>:Audience Manager가 사용자에게 할당한 데이터 파트너 <span class="keyword"> ID </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>:사용자의 고유 ID. </li> 
    </ul> <p> <p>중요: ID에 대해 인코딩되지 않은 값만 사용합니다. 인코딩은 이중으로 인코딩된 식별자를 만듭니다. </p> </p> <p> <p>참고: Adobe Experience Platform <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Identity Service를 사용하는 </a>경우 DIL 대신 <code> setCustomerIDs </code> 방법으로 고객 ID를 <span class="wintitle"> 설정하십시오 </span>. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid-authenticated-state.html" format="https" scope="external"> Customer IDs and Authentication States </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>부울 </p> </td> 
   <td colname="col3"> <p> true이면 이벤트가 발생할 때까지 모든 요청(IFRAME, 이벤트 호출, ID 동기화 및 대상)을 <code> Page Load </code> 실행합니다. 기본값은 <code> false </code>입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>부울 </p> </td> 
   <td colname="col3"> <p> False 기본적으로 Audience Manager <span class="keyword"> 는 파트너 도메인에 쿠키를 </span> 설정합니다(퍼스트 파티 쿠키 설정). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>부울 </p> </td> 
   <td colname="col3"> <p> <p>중요: 이 요소는 DIL <span class="wintitle"></span> 버전 8.0(2018년 8월 릴리스)에서 더 이상 사용되지 않습니다. Adobe Experience Platform ID Service <code> visitor.disableIdSyncs </code> <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-disableidsync.html" format="https" scope="external"> </a> 의 기능을 대신 사용하십시오. </p> </p> <p> 이 <code> true </code>경우, 대상 게시 IFRAME을 DOM이나 화재 대상에 연결하지 않습니다. 기본값은 <code> false </code>입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>부울 </p> </td> 
   <td colname="col3"> <p> <p>중요: 이 요소는 DIL <span class="wintitle"></span> 버전 8.0(2018년 8월 릴리스)에서 더 이상 사용되지 않습니다. Adobe Experience Platform ID Service <code> visitor.disableIdSyncs </code> <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-disableidsync.html" format="https" scope="external"> </a> 의 기능을 대신 사용하십시오. </p> </p> <p>ID 동기화를 사용하지 않도록 설정합니다. DIL v6.2+ 및 방문자 ID 서비스를 사용할 때는 ID 동기화를 비활성화해야 합니다. 이 <code> visitorService </code> 함수는 아래 샘플 코드 참조)에서 처리합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>부울 </p> </td> 
   <td colname="col3"> <p> 페이지의 모든 DIL 인스턴스에 대해 오류 보고를 <code> true </code> 활성화하도록 <span class="wintitle"></span> 설정합니다. Boolean에서만 <code> true </code> 작동합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>부울 </p> </td> 
   <td colname="col3"> <p> <p>중요: 이 요소는 DIL <span class="wintitle"></span> 버전 8.0(2018년 8월 릴리스)에서 더 이상 사용되지 않습니다. Adobe Experience Platform ID Service <code> visitor.idSyncSSLUseAkamai </code> <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idSyncSSLUseAkamai.html" format="https" scope="external"> </a> 의 기능을 대신 사용하십시오. </p> </p> <p> 대상 게시 템플릿이 HTTPS 연결에 대해 Akamai를 사용하는지를 지정합니다. 파트너 기준으로 설정됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>개체 </p> </td> 
   <td colname="col3"> <p>한 키-값 쌍의 값을 다른 값으로 연결합니다. 다른 <a href="../../dil/dil-use-cases.md#map-key-values"> 키에 키 값 매핑을 참조하십시오 </a>. v2.4와 함께 출시되었습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>필수 여부. </p> <p>키-값 쌍에는 Experience Cloud <code> namespace </code> 조직 ID가 <span class="keyword"> </span> 포함되어 있습니다. 이 ID가 없는 경우 Experience Cloud <span class="wintitle"> 대시보드의 </span> 관리 <span class="keyword"> 섹션에서 찾을 </span> 수 있습니다. 이 대시보드를 보려면 관리자 권한이 필요합니다. 제품 <a href="../../faq/faq-features.md"> 기능 FAQ 및 </a> 관리 - 사용자 관리 및 <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html" format="https" scope="external"> FAQ를 참조하십시오 </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>필수 여부. </p> <p> Audience Manager에서 제공한 파트너 <span class="keyword"> 이름입니다 </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>부울 </p> </td> 
   <td colname="col3"> <p> 스크립트 및 콜백을 제거합니다. 기본값은 <code> False </code>입니다. 현재 DIL <span class="wintitle"> 인스턴스에만 </span> 적용됩니다. v3.3으로 출시되었습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>개체 </p> </td> 
   <td colname="col3"> <p>Audience Manager에서 반환된 고유 사용자 ID를 사용하여 쿠키를 <span class="keyword"> 설정합니다 </span>. uuidCookie <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> 속성을 참조하십시오 </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>개체 </p> </td> 
   <td colname="col3"> <p>DIL <span class="wintitle"> 6. </span> 2 이상에서 필요합니다. </p> <p> DIL은 Adobe Experience Platform ID Service의 <code> setCustomerIDs </code> 기능을 사용하여 <span class="wintitle"> 선언된 ID를 Audience Manager </span> 에 <span class="keyword"> 전달합니다 </span>. 자세한 내용은 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid-authenticated-state.html" format="https" scope="external">고객 ID 및 인증 상태</a>를 참조하십시오. </p> </td> 
  </tr> 
 </tbody> 
</table>

**샘플 코드**

샘플 [!UICONTROL DIL] 호출은 다음과 유사할 수 있습니다.

```js
var partnerObject1 = DIL.create({ 
  partner: "partner name", 
  visitorService:{ 
    namespace: "INSERT-ORGANIZATION-ID-HERE" 
  }, 
  containerNSID: 3, 
  uuidCookie:{ 
    name:'ad_uuid', 
    days:200, 
    path:'/test', 
    domain:'adobe.com', 
    secure:true 
  } 
}); 
 
var partnerObject2 = DIL.create({ 
  partner: "partner name", 
  visitorService:{ 
    namespace: "INSERT-MCORG-ID-HERE" 
  }, 
  containerNSID: 3 
}); 
```

성공적인 응답은 [!UICONTROL DIL] 인스턴스를 반환합니다. 코드가 잘못 구성되었거나 오류가 발생할 때마다 오류 객체(throw되지 않음)가 반환됩니다.

## uuidCookie 속성 {#uuidcookie-props}

변수에 사용되는 속성을 `uuidCookie` 정의합니다. 이 변수는 `DIL.create` 메서드의 일부입니다.

`uuidCookie` 에는 다음 속성이 있습니다.

<!-- 

r_dil_uuid_cookie.xml

 -->

| 이름 | 설명 |
|---|---|
| `name` | The cookie name ( `aam_did` is default). |
| `days` | 쿠키 라이프타임(기본값 100일) |
| `path` | 쿠키 경로(예: `'/test'` ( `/` 기본값) |
| `domain` | 쿠키가 설정된 도메인(예: 기본값) `'adobe.com'` ( `'.'+document.domain` 기본값)입니다. |
| `secure` | HTTPS 연결을 통해서만 데이터를 전송하도록 플래그를 설정합니다. |

## visitorService 속성 {#visitor-service-props}

변수에 사용되는 속성을 `visitorService` 정의합니다. 이 변수는 `DIL.create` 메서드의 일부입니다.

`visitorService` 에는 다음 속성이 있습니다.

| 이름 | 유형 | 설명 |
|---|---|---|
| `namespace` | 문자열 | 필수. Experience Cloud 조직 ID를 나타냅니다. 이 기능은 Experience Cloud 코어 서비스 기능을 위해 필요합니다. 방문자 ID 기능을 인스턴스화하는 데 사용되는 동일한 매개 변수입니다. |

**코드 샘플:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
