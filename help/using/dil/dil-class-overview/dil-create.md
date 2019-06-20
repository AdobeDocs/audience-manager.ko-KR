---
description: 파트너 전용 DIL 인스턴스를 만듭니다.
seo-description: 파트너 전용 DIL 인스턴스를 만듭니다.
seo-title: DIL 만들기
solution: Audience Manager
title: DIL 만들기
uuid: 6 e 054600-703 c -4 a 97-af 2 a -8207 c 50013 db
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# DIL create method{#dil-create}

## DIL create {#dil-create-new}

Creates a partner-specific [!UICONTROL DIL] instance.

**함수 서명:**`DIL.create: function (initConfig) {}`

**Initconfig 요소**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>The `visitorService` property is *always* required. 여기에 나열된 다른 속성은 달리 명시되지 않는 한 선택 사항입니다.

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
   <td colname="col3"> <p>이 속성은 ID 동기화를 위해 <span class="keyword">Audience Manager</span>에서 사용하는 컨테이너 ID를 설정합니다. You would set <code> containerNSID </code> if you have <span class="wintitle"> DIL </span> deployed across multiple sites. 이러한 사이트에는 각각 고유한 컨테이너 ID와 ID 동기화가 있습니다. 사이트가 1 개뿐인 경우 컨테이너 ID가 기본적으로 0 이며 이 ID를 제대로 설정할 필요가 없습니다. 사이트 및 해당 컨테이너 ID의 목록을 얻으려면 컨설턴트에게 문의하십시오. </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID 서비스에서 </a><code> idsynccontainerid </code> 속성은 DIL의 <code> containernsid </code> 에 <span class="wintitle"> 해당합니다 </span>. Note the following if you're using <span class="wintitle"> DIL </span> <i>and</i> the ID service across multiple sites: </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">For each site, set the same container IDs on <code> containerNSID </code> and <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF"><span class="wintitle"> DIL </span> 와 ID 서비스가 모두 ID 동기화하려고 시도합니다. However, the iFrame ensures that <span class="wintitle"> DIL </span> won't fire an ID sync. 이로 인해 중복이 방지됩니다. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F"><span class="wintitle"> DIL </span> 만 <a href="../../features/destinations/destinations.md"> URL 대상으로 </a>데이터를 보냅니다. </li> 
     </ul> </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idsyncontainerid.html" format="https" scope="external"> Idsynccontainerid </a>를 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Declaredid </code> </p> </td> 
   <td colname="col2"> <p>개체 </p> </td> 
   <td colname="col3"> 
    <draft-comment> 
     <p>Sends the <a href="../../features/declared-ids.md"> Declared ID variables </a> on every event call to <span class="keyword"> Audience Manager </span>. </p> 
    </draft-comment> <p> <code> Delcaredid는 </code> 다음 중 하나를 전달하는 데 사용됩니다. </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> DPID </code>: Audience Manager에서 <span class="keyword"> 사용자에게 할당된 데이터 파트너 ID </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> DPUUID </code>: 사용자의 고유 ID. </li> 
    </ul> <p> <p>중요: ID에 인코딩되지 않은 값만 사용합니다. 인코딩은 이중 인코딩 식별자를 만듭니다. </p> </p> <p> <p>Note:  If you use the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID Service </a>, set customer IDs with the <code> setCustomerIDs </code> method instead of <span class="wintitle"> DIL </span>. <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid-authenticated-state.html" format="https" scope="external"> 고객 ID 및 인증 상태를 </a>참조하십시오. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Delayalluntilwindowload </code> </p> </td> 
   <td colname="col2"> <p>부울 </p> </td> 
   <td colname="col3"> <p> If true, defers all requests (IFRAME, event calls, ID sync, and destinationing) from executing until the <code> Page Load </code> event fires. Default is <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Disabledeclareduuidcookie </code> </p> </td> 
   <td colname="col2"> <p>부울 </p> </td> 
   <td colname="col3"> <p> False <span class="keyword"> 기본적으로, Audience Manager </span> 는 파트너 도메인에 쿠키를 설정하고 (퍼스트 파티 쿠키 설정) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>부울 </p> </td> 
   <td colname="col3"> <p> <p>Important:  This element has been deprecated with <span class="wintitle"> DIL </span> version 8.0 (released August 2018). Use the <code> visitor.disableIdSyncs </code> <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-disableidsync.html" format="https" scope="external"> function </a> in the Experience Cloud ID Service instead. </p> </p> <p> <code> true </code>인 경우 대상 게시 iframe를 DOM 또는 Fire 대상에 첨부하지 않습니다. Default is <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>부울 </p> </td> 
   <td colname="col3"> <p> <p>Important:  This element has been deprecated with <span class="wintitle"> DIL </span> version 8.0 (released August 2018). Use the <code> visitor.disableIdSyncs </code> <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-disableidsync.html" format="https" scope="external"> function </a> in the Experience Cloud ID Service instead. </p> </p> <p>ID 동기화를 사용하지 않도록 설정합니다. DIL v 6.2 + 및 방문자 ID 서비스를 사용할 때 ID 동기화를 비활성화해야 합니다. <code> Visitorservice </code> 함수 (아래의 샘플 코드 참조) 는 이 작업을 처리합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Enableerrorreporting </code> </p> </td> 
   <td colname="col2"> <p>부울 </p> </td> 
   <td colname="col3"> <p> <code> 페이지의 </code> 모든 <span class="wintitle"> DIL </span> 인스턴스에 대한 오류 보고를 활성화하려면 true로 설정합니다. Works with Boolean <code> true </code> only. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>부울 </p> </td> 
   <td colname="col3"> <p> <p>Important:  This element has been deprecated with <span class="wintitle"> DIL </span> version 8.0 (released August 2018). Use the <code> visitor.idSyncSSLUseAkamai </code> <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idSyncSSLUseAkamai.html" format="https" scope="external"> function </a> in the Experience Cloud ID Service instead. </p> </p> <p> 대상 게시 템플릿이 HTTPS 연결에 대해 Akamai를 사용하는지를 지정합니다. 파트너 기준으로 설정됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 매핑 </code> </p> </td> 
   <td colname="col2"> <p>개체 </p> </td> 
   <td colname="col3"> <p>한 키-값 쌍의 값을 다른 값과 연관시킵니다. See <a href="../../dil/dil-use-cases.md#map-key-values"> Map Key Values to Other Keys </a>. v 2.4 릴리스 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>필수 여부. </p> <p><code> 네임스페이스 </code> 키-값 쌍에 <span class="keyword"> Experience Cloud </span> 조직 ID가 포함되어 있습니다. If you don't have this ID, you can find it in the <span class="wintitle"> Administration </span> section of the <span class="keyword"> Experience Cloud </span> dashboard. 이 대시보드를 보려면 관리자 권한이 필요합니다. <a href="../../faq/faq-features.md"> 제품 기능 및 기능 FAQ </a> 와 <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html" format="https" scope="external"> 관리 - 사용자 관리 및 FAQ </a>를 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 파트너 </code> </p> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>필수 여부. </p> <p> <span class="keyword"> Audience Manager </span>에서 제공한 파트너 이름입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Removefinishedscriptsandcallbacks </code> </p> </td> 
   <td colname="col2"> <p>부울 </p> </td> 
   <td colname="col3"> <p> 스크립트 및 콜백을 제거합니다. Default is <code> False </code>. Applies to the current <span class="wintitle"> DIL </span> instance only. v 3.3 릴리스. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Uuidcookie </code> </p> </td> 
   <td colname="col2"> <p>개체 </p> </td> 
   <td colname="col3"> <p>Sets a cookie with the unique user ID returned from <span class="keyword"> Audience Manager </span>. <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> Uuidcookie 속성을 </a>참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Visitorservice </code> </p> </td> 
   <td colname="col2"> <p>개체 </p> </td> 
   <td colname="col3"> <p><span class="wintitle"> DIL </span> 6.2 이상에서 필요합니다. </p> <p> DIL relies on the <code> setCustomerIDs </code> function in the <span class="wintitle"> Experience Cloud ID Service </span> to pass declared IDs into <span class="keyword"> Audience Manager </span>. 자세한 내용은 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid-authenticated-state.html" format="https" scope="external">고객 ID 및 인증 상태</a>를 참조하십시오. </p> </td> 
  </tr> 
 </tbody> 
</table>

**샘플 코드**

A sample [!UICONTROL DIL] call could look similar to the following:

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

A successful response returns the [!UICONTROL DIL] instance. 실패한 시도는 코드가 잘못 구성되거나 오류가 발생할 때마다 오류 개체 (throw 되지 않음) 를 반환합니다.

## uuidCookie Properties {#uuidcookie-props}

Defines the properties used by the `uuidCookie` variable. This variable is part of the `DIL.create` method.

`uuidCookie` 에는 다음 속성이 있습니다.

<!-- 

r_dil_uuid_cookie.xml

 -->

| 이름 | 설명 |
|---|---|
| `name` | The cookie name ( `aam_did` is default). |
| `days` | 쿠키 라이프타임 (기본값은 100 일). |
| `path` | Cookie path, e.g., `'/test'` ( `/` is default). |
| `domain` | The domain the cookie is set in, e.g., `'adobe.com'` ( `'.'+document.domain` is default). |
| `secure` | HTTPS 연결에서만 데이터를 보내도록 플래그를 설정합니다. |

## visitorService Properties {#visitor-service-props}

Defines the properties used by the `visitorService` variable. This variable is part of the `DIL.create` method.

`visitorService` 에는 다음 속성이 있습니다.

| 이름 | 유형 | 설명 |
|---|---|---|
| `namespace` | 문자열 | 필수. Experience Cloud 조직 ID를 나타냅니다. Adobe Experience Cloud 코어 서비스 기능에 필요합니다. 방문자 ID 기능을 인스턴스화하는 데 사용되는 매개 변수입니다. |

**코드 샘플:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
