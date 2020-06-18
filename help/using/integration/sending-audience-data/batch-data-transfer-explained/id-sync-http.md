---
description: 공급업체와 Audience Manager 간에 사용자 ID를 동기화하는 초기 HTTP 호출에 사용되는 구문과 매개 변수에 대해 설명합니다. 데이터 분류법을 Audience Manager으로 보낸 후 ID 동기화를 시작할 수 있습니다.
seo-description: 공급업체와 Audience Manager 간에 사용자 ID를 동기화하는 초기 HTTP 호출에 사용되는 구문과 매개 변수에 대해 설명합니다. 데이터 분류법을 Audience Manager으로 보낸 후 ID 동기화를 시작할 수 있습니다.
seo-title: 인바운드 데이터 전송을 위한 ID 동기화
solution: Audience Manager
title: 인바운드 데이터 전송을 위한 ID 동기화
uuid: 037e74a6-acfd-4cef-b693-16b7aaa8e976
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '480'
ht-degree: 7%

---


# 인바운드 데이터 전송을 위한 ID 동기화{#id-synchronization-for-inbound-data-transfers}

공급업체와 공급업체 간의 사용자 ID를 동기화하는 초기 `HTTP` 호출에 사용되는 구문과 매개 변수에 대해 설명합니다 [!DNL Audience Manager]. 데이터 분류법을 다음으로 보낸 후에 ID 동기화를 시작할 수 있습니다 [!DNL Audience Manager].

<!-- c_id_sync_in.xml -->

ID 동기화는 인바운드, 비동기 데이터 전송 프로세스의 첫 번째 단계입니다. 이 단계에서 공급업체 [!DNL Audience Manager] 는 해당 사이트 방문자에 대해 ID를 비교하고 일치시킵니다. 예를 들어 [!DNL Audience Manager] 고객은 ID 123으로 사용자를 알 수 있습니다. 그러나 데이터 파트너는 ID 456으로 이 사용자를 식별할 수 있습니다. 동기화 프로세스를 통해 데이터 공급업체 [!DNL Audience Manager] 는 이러한 서로 다른 ID를 조정하고 각각의 시스템에서 사용자를 식별할 수 있습니다. 완료되면 [!DNL Audience Manager] , 타사 파트너에게는 네트워크에서 볼 수 있는 각 고유 사용자에 대해 해당 ID가 있어야 합니다.

다음 방법을 사용하여 데이터를 가져올 수 있습니다 [!DNL Audience Manager].

* [ID 동기화 HTTP 요청](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [선언된 ID 이벤트](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [이메일 포함 이미지에서 ID 동기화](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## ID 동기화 `HTTP` 요청 {#id-sync-http}

ID 교환 시 올바른 형식의 [!DNL URL] 문자열이 다음과 같아야 합니다.

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

인바운드 ID 동기화 호출 [!DNL URL] 에 아래 표에 설명된 변수가 포함되어야 합니다.

>[!NOTE]
>
>기울임꼴 컨텐츠를 실제 매개 변수 값으로 대체합니다.

<table id="table_EB9F4246E2A34ABB8ED06EA458EB186F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 매개 변수 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2"> <p>콘텐트 공급자에 대한 고유 ID(Audience Manager에 의해 <span class="keyword"> 할당됨</span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> <p>URL(퍼센트) 고유한 사용자 ID의 인코딩 표현. 인코딩이 예약된 ASCII 문자 외에도 ASCII가 아닌 모든 문자는 UTF-8 문자 인코딩 테이블에 따라 퍼센트 인코딩되어야 합니다. </p> <p>자세한 내용은 온라인 <a href="https://www.url-encode-decode.com" format="http" scope="external"></a> URL 인코딩/디코딩을 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2"> <p>매크로가 포함된 인코딩된 URL 리디렉션 <code> ${DD_UUID}</code> 입니다. </p> <p>참고:  컨텐트 공급자가 호출을 시작할 때만 추가되었습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p>선택 사항입니다. IAB TCF용 <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager 플러그인을 사용하는 경우 이 매개 변수를 추가합니다.</a></p> <p><code> gdpr</code> 0일 수(GDPR은 적용되지 않음) 또는 1(GDPR 적용)일 수 있습니다. </p> <p> <b>참고:</b> 이 매개 변수는 함께 사용해야 합니다 <code>gdpr_consent</code>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"> <p>선택 사항입니다. IAB TCF용 <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager 플러그인을 사용하는 경우 이 매개 변수를 추가합니다.</a></p> <p><code>gdpr_consent</code> is the URL-safe base64-encoded GDPR consent string (see <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB specification</a>). </p> <p> <b>참고:</b> 이 매개 변수는 함께 사용해야 합니다 <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

## 선언된 ID 이벤트 {#declared-id-event}

자세한 내용은 [선언된 ID를 참조하십시오](../../../features/declared-ids.md).

## 이메일 포함 이미지에서 ID 동기화 {#id-sync-email-image}

이메일 이미지를 통해 일치하는 ID에 대한 형식은 위와 동일합니다. 그러나 이메일 이미지는 활성화되어야 사용할 수 있습니다. 대부분의 메일 시스템은 기본적으로 이미지를 비활성화하므로 이 경우 이메일을 통한 ID 동기화에 영향을 줄 수 있습니다.

>[!MORELIKETHIS]
>
>* [데이터 수집 구성 요소](../../../reference/system-components/components-data-collection.md)

