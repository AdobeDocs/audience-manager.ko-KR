---
description: 파트너별 DIL 인스턴스를 만듭니다.
seo-description: Creates a partner-specific DIL instance.
seo-title: DIL create
solution: Audience Manager
title: DIL 만들기
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
exl-id: 0bef149c-4458-43d6-affe-6d79fe1fca46
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 10%

---

# DIL 만들기 메서드{#dil-create}

## DIL 만들기 {#dil-create-new}

파트너별 만들기 [!UICONTROL DIL] 인스턴스.

**함수 서명:** `DIL.create: function (initConfig) {}`

**initConfig 요소**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>다음 `visitorService` 속성은 입니다. *항상* 필수. 여기에 나열된 다른 속성은 달리 표시되지 않는 한 선택 사항입니다.

`initConfig` 은 다음 요소를 허용합니다.

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
   <td colname="col3"> <p>이 속성은 ID 동기화를 위해 <span class="keyword">Audience Manager</span>에서 사용하는 컨테이너 ID를 설정합니다. 다음을 설정합니다. <code> containerNSID </code> 다음을 보유한 경우 <span class="wintitle"> DIL </span> 여러 사이트에 배포되었습니다. 이러한 각 사이트에는 자체 컨테이너 ID와 ID 동기화가 있습니다. 사이트가 1개만 있는 경우 컨테이너 ID는 기본적으로 0이며 이를 제대로 설정할 필요가 없습니다. 사이트 및 해당 컨테이너 ID 목록을 얻으려면 컨설턴트에게 문의하십시오. </p> <p>다음에서 <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform ID 서비스 </a>, 속성 <code> idSyncContainerID </code> 다음에 해당 <code> containerNSID </code> 위치: <span class="wintitle"> DIL </span>. 을 사용하는 경우 다음 사항을 참고하십시오. <span class="wintitle"> DIL </span> <i>및</i> 여러 사이트에서 ID 서비스: </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">각 사이트에 대해 동일한 컨테이너 ID를에 설정합니다. <code> containerNSID </code> 및 <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">모두 <span class="wintitle"> DIL </span> 그리고 ID 서비스는 ID 동기화를 데이터 수집 iFrame으로 보내려고 합니다. 그러나 iFrame에서는 <span class="wintitle"> DIL </span> ID 동기화를 실행하지 않습니다. 이렇게 하면 중복이 방지됩니다. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">전용 <span class="wintitle"> DIL </span> 에 데이터 전송 <a href="../../features/destinations/destinations.md"> URL 대상 </a>. </li> 
     </ul> </p> <p>다음을 참조하십시오. <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncontainerid.html" format="https" scope="external"> idSyncContainerID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>개체 </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code> 는 다음 중 하나를 전달하는 데 사용됩니다. </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>: 다음에 의해 사용자에게 할당된 데이터 파트너 ID <span class="keyword"> Audience Manager </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>: 사용자의 고유 ID입니다. </li> 
    </ul> <p> <p>중요: ID에는 인코딩되지 않은 값만 사용하십시오. 인코딩은 이중으로 인코딩된 식별자를 생성합니다. </p> </p> <p> <p>참고: <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform ID 서비스 </a>, 고객 ID 설정 <code> setCustomerIDs </code> 대신 메서드 <span class="wintitle"> DIL </span>. 다음을 참조하십시오 <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html" format="https" scope="external"> 고객 ID 및 인증 상태 </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>부울 </p> </td> 
   <td colname="col3"> <p> true인 경우 은 (이)가 다음을 실행할 때까지 모든 요청(IFRAME, 이벤트 호출, ID 동기화 및 대상)의 실행을 지연합니다. <code> Page Load </code> 이벤트가 실행됩니다. 기본값은 <code> false </code>입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>부울 </p> </td> 
   <td colname="col3"> <p> False 기본적으로 <span class="keyword"> Audience Manager </span> 파트너의 도메인에 쿠키를 설정합니다(자사 쿠키 설정). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>부울 </p> </td> 
   <td colname="col3"> <p> <p>중요: 이 요소는 다음으로 더 이상 사용되지 않습니다. <span class="wintitle"> DIL </span> 버전 8.0(2018년 8월 릴리스). 사용 <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> 함수 </a> Adobe Experience Platform Identity 서비스에서 을 참조하십시오. </p> </p> <p> If <code> true </code>는 대상 게시 IFRAME을 DOM 또는 화재 대상에 연결하지 않습니다. 기본값은 <code> false </code>입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>부울 </p> </td> 
   <td colname="col3"> <p> <p>중요: 이 요소는 다음으로 더 이상 사용되지 않습니다. <span class="wintitle"> DIL </span> 버전 8.0(2018년 8월 릴리스). 사용 <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> 함수 </a> Adobe Experience Platform Identity 서비스에서 을 참조하십시오. </p> </p> <p>ID 동기화를 사용하지 않도록 설정합니다. DIL v6.2+ 및 방문자 ID 서비스를 사용할 때 ID 동기화를 비활성화해야 합니다. 다음 <code> visitorService </code> 함수(아래 샘플 코드 참조)가 이 작업을 처리합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>부울 </p> </td> 
   <td colname="col3"> <p> 다음으로 설정 <code> true </code> 모든 항목에 대한 오류 보고를 활성화하려면 <span class="wintitle"> DIL </span> 페이지의 인스턴스. 부울을 사용한 작업 <code> true </code> 만 해당. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>부울 </p> </td> 
   <td colname="col3"> <p> <p>중요: 이 요소는 다음으로 더 이상 사용되지 않습니다. <span class="wintitle"> DIL </span> 버전 8.0(2018년 8월 릴리스). 사용 <code> visitor.idSyncSSLUseAkamai </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncssluseakamai.html" format="https" scope="external"> 함수 </a> Adobe Experience Platform Identity 서비스에서 을 참조하십시오. </p> </p> <p> 대상 게시 템플릿이 HTTPS 연결에 대해 Akamai를 사용하는지를 지정합니다. 파트너 기준으로 설정됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>개체 </p> </td> 
   <td colname="col3"> <p>한 키-값 쌍의 값을 다른 키-값 쌍에 연결합니다. 다음을 참조하십시오 <a href="../../dil/dil-use-cases.md#map-key-values"> 다른 키에 키 값 매핑 </a>. v2.4와 함께 릴리스되었습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>필수 여부. </p> <p>다음 <code> namespace </code> 키-값 쌍에 <span class="keyword"> Experience Cloud </span> 조직 ID. 이 ID가 없으면 <span class="wintitle"> 관리 </span> 의 섹션 <span class="keyword"> Experience Cloud </span> 대시보드입니다. 이 대시보드를 보려면 관리자 권한이 필요합니다. 다음을 참조하십시오. <a href="../../faq/faq-features.md"> 제품 및 기능 FAQ </a> 및 <a href="https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/faq.html" format="https" scope="external"> 관리 - 사용자 관리 및 FAQ </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>필수 여부. </p> <p> 에서 제공한 파트너 이름 <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>부울 </p> </td> 
   <td colname="col3"> <p> 스크립트 및 콜백을 제거합니다. 기본값은 <code> False </code>입니다. 현재 항목에 적용 <span class="wintitle"> DIL </span> 인스턴스만. v3.3과 함께 릴리스되었습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>개체 </p> </td> 
   <td colname="col3"> <p>에서 반환된 고유 사용자 ID로 쿠키를 설정합니다. <span class="keyword"> Audience Manager </span>. 다음을 참조하십시오 <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> uuidCookie 속성 </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>개체 </p> </td> 
   <td colname="col3"> <p>필수 항목: <span class="wintitle"> DIL </span> 6.2 이상 </p> <p> DIL은 <code> setCustomerIDs </code> 의 함수 <span class="wintitle"> Adobe Experience Platform ID 서비스 </span> 선언된 ID를에 전달하려면 <span class="keyword"> Audience Manager </span>. 자세한 내용은 <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html" format="https" scope="external">고객 ID 및 인증 상태</a>를 참조하십시오. </p> </td> 
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

성공적인 응답은 다음을 반환합니다. [!UICONTROL DIL] 인스턴스. 실패한 시도는 코드가 잘못 구성되었거나 오류가 발생할 때마다 오류 개체(throw되지 않음)를 반환합니다.

## uuidCookie 속성 {#uuidcookie-props}

에서 사용하는 속성을 정의합니다. `uuidCookie` 변수를 채우는 방법에 따라 페이지를 순서대로 표시합니다. 이 변수는 `DIL.create` 메서드를 사용합니다.

`uuidCookie` 에는 다음 속성이 있습니다.

<!-- 

r_dil_uuid_cookie.xml

 -->

| 이름 | 설명 |
|---|---|
| `name` | 쿠키 이름( `aam_did` 기본값). |
| `days` | 쿠키 라이프타임(기본값: 100일). |
| `path` | 쿠키 경로(예: ) `'/test'` ( `/` 기본값). |
| `domain` | 쿠키가 설정된 도메인(예: ) `'adobe.com'` ( `'.'+document.domain` 기본값). |
| `secure` | HTTPS 연결을 통해서만 데이터를 전송하는 플래그를 설정합니다. |

## visitorService 속성 {#visitor-service-props}

에서 사용하는 속성을 정의합니다. `visitorService` 변수를 채우는 방법에 따라 페이지를 순서대로 표시합니다. 이 변수는 `DIL.create` 메서드를 사용합니다.

`visitorService` 에는 다음 속성이 있습니다.

| 이름 | 유형 | 설명 |
|---|---|---|
| `namespace` | 문자열 | 필수. Experience Cloud 조직 ID를 나타냅니다. Experience Cloud 핵심 서비스 기능에 필요합니다. 방문자 ID 기능을 인스턴스화하는 데 사용되는 것과 동일한 매개 변수입니다. |

**코드 샘플:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
