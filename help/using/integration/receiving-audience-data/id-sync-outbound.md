---
description: Audience Manager와 타사 데이터 공급자 간 사용자 ID를 동기화하는 데 초기 HTTP 호출에 사용되는 구문과 매개 변수에 대해 설명합니다. 첫 번째 ID 동기화를 시도하기 전에 Adobe Audience Manager 컨설턴트에게 문의하십시오.
seo-description: Audience Manager와 타사 데이터 공급자 간 사용자 ID를 동기화하는 데 초기 HTTP 호출에 사용되는 구문과 매개 변수에 대해 설명합니다. 첫 번째 ID 동기화를 시도하기 전에 Adobe Audience Manager 컨설턴트에게 문의하십시오.
seo-title: 아웃바운드 데이터 전송에 대한 ID 동기화
solution: Audience Manager
title: 아웃바운드 데이터 전송에 대한 ID 동기화
uuid: f3849be8-1094-47db-9296-7482f020af18
translation-type: tm+mt
source-git-commit: b1e438a77a472c192117a2c1ddcf63f4eb25d07d

---


# 아웃바운드 데이터 전송에 대한 ID 동기화{#id-synchronization-for-outbound-data-transfers}

Audience Manager와 타사 데이터 공급자 간 사용자 ID를 동기화하는 초기 `HTTP` 호출에 사용되는 구문과 매개 변수에 대해 설명합니다. 첫 번째 ID 동기화를 시도하기 전에 Adobe Audience Manager 컨설턴트에게 문의하십시오.

<!-- c_id_sync_out.xml -->

## ID 동기화 목적

ID 동기화는 아웃바운드 비동기 데이터 전송 프로세스의 첫 번째 단계입니다. 이 단계에서, [!DNL Audience Manager] 공급업체는 해당 사이트 방문자의 ID를 비교하고 일치시킵니다. 예를 들어 [!DNL Audience Manager] 고객은 ID 123으로 사용자를 알 수 있습니다. 그러나 데이터 파트너는 ID 456으로 이 사용자를 식별할 수 있습니다. 동기화 프로세스를 통해 [!DNL Audience Manager] 및 데이터 공급업체는 이러한 서로 다른 ID를 조정하고 각각의 시스템에서 사용자를 식별할 수 있습니다. 완료되면 [!DNL Audience Manager] 서드 파티 데이터 제공업체는 네트워크에 표시되는 각 고유 사용자에 대해 해당 ID를 가져야 합니다.

## URL 구문

ID 교환에서 올바른 형식의 [!DNL URL] 문자열은 다음과 같아야 합니다.

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## URL 매개 변수

인바운드 ID 동기화 호출에 [!DNL URL] 대해서는 아래 표에 설명된 변수를 포함해야 합니다.

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
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2">데이터 공급자에 대한 고유 ID(Audience Manager에서 <span class="keyword"> 지정</span>). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> 고유 사용자 ID. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2">매크로가 포함된 URL 리디렉션을 <code> ${DD_UUID}</code> 포함합니다. <p><b></b> 참고:데이터 공급자가 호출을 시작할 때만 추가되었습니다. </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p><code>gdpr</code> 은 0(GDPR은 적용되지 않음) 또는 1(GDPR 적용)일 수 있습니다.</p><p><b>참고:</b> <ul><li>ID 동기화 URL에서 <code>gdpr</code> 및 <code>gdpr_consent</code> 매개 변수를 활성화 파트너와 점진적으로 롤아웃하고 있습니다. IAB TCF용 Audience Manager <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md#aam-activation-partners">플러그인에서 IAB TCF를 지원하는 활성화 파트너를 참조하십시오.</a></li><li>이 매개 변수는 <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"><p><code>gdpr_consent</code> 는 URL-safe base64 인코딩된 GDPR 동의 문자열입니다(IAB 사양 <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> 참조</a>).</p><p><b></b> 참고:이 매개 변수는 함께 사용할 수만 <code>gdpr</code>있습니다.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [DCS(Data Collection Server) API 메서드 및 코드](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [데이터 수집 구성 요소](../../reference/system-components/components-data-collection.md)

