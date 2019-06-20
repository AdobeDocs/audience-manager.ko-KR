---
description: Audience Manager와 타사 데이터 공급자 간 사용자 ID를 동기화하는 초기 HTTP 호출에 사용된 구문 및 매개 변수에 대해 설명합니다. 첫 번째 ID 동기화를 시도하기 전에 Adobe Audience Manager 컨설턴트에게 문의하십시오.
seo-description: Audience Manager와 타사 데이터 공급자 간 사용자 ID를 동기화하는 초기 HTTP 호출에 사용된 구문 및 매개 변수에 대해 설명합니다. 첫 번째 ID 동기화를 시도하기 전에 Adobe Audience Manager 컨설턴트에게 문의하십시오.
seo-title: 아웃바운드 데이터 전송을 위한 ID 동기화
solution: Audience Manager
title: 아웃바운드 데이터 전송을 위한 ID 동기화
uuid: F 3849 BE 8-1094-47 DB -9296-7482 F 020 AF 18
translation-type: tm+mt
source-git-commit: e206d3a3cba259dc215f2f4190c9b4e03264f080

---


# ID Synchronization for Outbound Data Transfers{#id-synchronization-for-outbound-data-transfers}

Describes the syntax and parameters used in the initial `HTTP` call to synchronize user IDs between Audience Manager and a third-party data provider. 첫 번째 ID 동기화를 시도하기 전에 Adobe Audience Manager 컨설턴트에게 문의하십시오.

<!-- c_id_sync_out.xml -->

## ID 동기화 목적

ID 동기화는 아웃바운드 비동기 데이터 전송 프로세스의 첫 번째 단계입니다. In this step, [!DNL Audience Manager] and the vendor compare and match IDs for their respective site visitors. For example, an [!DNL Audience Manager] customer may know a user by ID 123. 데이터 파트너는 ID 456를 사용하여 이 사용자를 식별할 수 있었습니다. The synchronization process allows [!DNL Audience Manager] and a data vendor to reconcile these different IDs and identify users in their respective systems. Once complete, [!DNL Audience Manager] and the third-party data provider should have corresponding IDs for each unique user seen on our networks.

## URL 구문

In an ID exchange, a properly formatted [!DNL URL] string should look like this:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## URL 매개 변수

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
  <tr valign="top"> 
   <td colname="col1"> <code><i>&lt; vendor_ id &gt;</i></code> </td> 
   <td colname="col2">Unique ID for the data provider (assigned by <span class="keyword"> Audience Manager</span>). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>&lt; vendor_ uuid &gt;</i></code> </td> 
   <td colname="col2"> 고유 사용자 ID. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>&lt; redirect_ url &gt;</i></code> </td> 
   <td colname="col2">An encoded URL redirect with the macro <code> ${DD_UUID}</code> embedded within it. <p><b>참고:</b> 데이터 공급자가 호출을 시작할 때에만 추가되었습니다. </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr = &lt; 0|1 &gt;</i></code> </td> 
   <td colname="col2"> <p><code>GDPR</code> 는 0 (GDPR는 적용되지 않음) 또는 1 (GDPR 적용) 이 될 수 있습니다.</p><p><b>참고:</b> <ul><li><code>gdpr</code> 및 <code>gdpr_ consent</code> 매개 변수가 ID 동기화 URL에서 활성화 파트너와 점진적으로 롤아웃됩니다. See Activation partners that support IAB TCF in <a href="../../overview/aam-gdpr/aam-iab-plugin.md#aam-activation-partners">Audience Manager Plug-in for IAB TCF.</a></li><li>This parameter can only be used together with <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_ consent = &lt; 인코딩된 문자열 &gt;</i></code> </td> 
   <td colname="col2"><p><code>gdpr_ consent</code> 는 URL-Safe Base 64 인코딩 GDPR 동의 문자열입니다 ( <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB 사양</a>참조).</p><p><b>참고:</b> 이 매개 변수는 <code>GDPR</code>와 함께 사용할 수 있습니다.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ like_ this]
>
>* [DCS (Data Collection Server) API 메서드 및 코드](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [데이터 수집 구성 요소](../../reference/system-components/components-data-collection.md)

