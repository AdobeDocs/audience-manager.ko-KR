---
description: 공급업체 및 대상 관리자 간 사용자 ID를 동기화하는 초기 HTTP 호출에 사용된 구문 및 매개 변수에 대해 설명합니다. 데이터 분류법을 Audience Manager로 보낸 후 ID 동기화를 시작할 수 있습니다.
seo-description: 공급업체 및 대상 관리자 간 사용자 ID를 동기화하는 초기 HTTP 호출에 사용된 구문 및 매개 변수에 대해 설명합니다. 데이터 분류법을 Audience Manager로 보낸 후 ID 동기화를 시작할 수 있습니다.
seo-title: 인바운드 데이터 전송을 위한 ID 동기화
solution: Audience Manager
title: 인바운드 데이터 전송을 위한 ID 동기화
uuid: 037 e 74 a 6-acfd -4 cef-b 693-16 b 7 aaa 8 e 976
translation-type: tm+mt
source-git-commit: 0fac081c93be36d2aa40023c7323ef1886b3860a

---


# ID Synchronization for Inbound Data Transfers{#id-synchronization-for-inbound-data-transfers}

Describes the syntax and parameters used in the initial `HTTP` call to synchronize user IDs between a vendor and Audience Manager. 데이터 분류법을 Audience Manager로 보낸 후 ID 동기화를 시작할 수 있습니다.

<!-- c_id_sync_in.xml -->

ID 동기화는 인바운드 비동기 데이터 전송 프로세스의 첫 번째 단계입니다. 이 단계에서 Audience Manager와 공급업체는 각 사이트 방문자에 대해 ID를 비교하고 일치시킵니다. For example, an [!DNL Audience Manager] customer may know a user by ID 123. 데이터 파트너는 ID 456를 사용하여 이 사용자를 식별할 수 있었습니다. The synchronization process allows [!DNL Audience Manager] and a data vendor to reconcile these different IDs and identify users in their respective systems. Once complete, [!DNL Audience Manager] and your third-party partner should have corresponding IDs for each unique user seen on our networks.

You can use the following methods to get your data into [!DNL Audience Manager]:

* [ID 동기화 HTTP 요청](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [선언된 ID 이벤트](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [이메일 임베드 이미지에서 ID 동기화](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## ID Synchronization `HTTP` Request {#id-sync-http}

In an ID exchange, a properly formatted [!DNL URL] string should look like this:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

The [!DNL URL] for your inbound ID synchronization call should contain variables described in the table below.

>[!NOTE]
>
>기울임꼴 컨텐츠를 실제 매개 변수 값으로 바꿉니다.

<table id="table_EB9F4246E2A34ABB8ED06EA458EB186F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 매개 변수 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code><i>&lt; vendor_ id &gt;</i></code> </td> 
   <td colname="col2"> <p>Unique ID for the content provider (assigned by <span class="keyword"> Audience Manager</span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>&lt; vendor_ uuid &gt;</i></code> </td> 
   <td colname="col2"> <p>URL (퍼센트) 고유한 사용자 ID의 인코딩된 표현. 예약된 ASCII 문자를 인코딩하는 것 외에도 ASCII -8 문자 인코딩 테이블을 기반으로 ASCII가 아닌 모든 문자는 인코딩할 수 있습니다. </p> <p>For more information, see the <a href="https://www.url-encode-decode.com" format="http" scope="external"> URL Encode/Decode Online</a> website. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>&lt; redirect_ url &gt;</i></code> </td> 
   <td colname="col2"> <p>An encoded URL redirect with the macro <code> ${DD_UUID}</code> embedded within it. </p> <p>참고: 컨텐츠 공급자가 호출을 시작할 때에만 추가되었습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr = &lt; 0|1 &gt;</i></code> </td> 
   <td colname="col2"> <p>선택 사항입니다. Add this parameter if you are using the <a href="../../../overview/aam-gdpr/aam-iab-plugin.md">Audience Manager Plug-in for IAB TCF.</a></p> <p><code> GDPR</code> 는 0 (GDPR는 적용되지 않음) 또는 1 (GDPR 적용) 이 될 수 있습니다. </p> <p> <b>참고:</b> 이 매개 변수는 <code>gdpr_ consent</code>와 함께 사용할 수만 있습니다.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_ consent = &lt; 인코딩된 문자열 &gt;</i></code> </td> 
   <td colname="col2"> <p>선택 사항입니다. Add this parameter if you are using the <a href="../../../overview/aam-gdpr/aam-iab-plugin.md">Audience Manager Plug-in for IAB TCF.</a></p> <p><code>gdpr_ consent</code> 는 URL-Safe Base 64 인코딩 GDPR 동의 문자열입니다 ( <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB 사양</a>참조). </p> <p> <b>참고:</b> 이 매개 변수는 <code>GDPR</code>와 함께 사용할 수 있습니다.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Declared ID Event {#declared-id-event}

For more information, see [Declared IDs](../../../features/declared-ids.md).

## ID Synchronization From an Email Embedded Image {#id-sync-email-image}

이메일 이미지를 통해 ID를 연결하기 위한 형식은 위에 표시된 것과 동일합니다. 하지만 이메일에 있는 이미지는 작동하도록 설정되어야 합니다. 대부분의 메일 시스템은 기본적으로 이미지를 비활성화하므로 이로 인해 ID 동기화에 영향을 줄 수 있습니다.

>[!MORE_ like_ this]
>
>* [데이터 수집 구성 요소](../../../reference/system-components/components-data-collection.md)

