---
description: 클릭 추적은 타사 크리에이티브를 위한 클릭 기반 활동을 기록하므로 캠페인 전체에서 방문자 참여를 측정할 수 있습니다.
seo-description: 클릭 추적은 타사 크리에이티브를 위한 클릭 기반 활동을 기록하므로 캠페인 전체에서 방문자 참여를 측정할 수 있습니다.
seo-title: 픽셀 호출을 통해 캠페인 클릭 데이터 캡처
solution: Audience Manager
title: 픽셀 호출을 통해 캠페인 클릭 데이터 캡처
uuid: 7c3797f7-9674-493d-972b-38be0584fede
feature: Integration with Campaign
translation-type: tm+mt
source-git-commit: 231d8e537cf5b4f29b1c4f284fe1b3ffe6d187a9
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 11%

---


# 픽셀 호출을 통해 캠페인 클릭 데이터 캡처 {#capturing-campaign-click-data-via-pixel-calls}

클릭 추적은 타사 크리에이티브를 위한 클릭 기반 활동을 기록하므로 캠페인 전체에서 방문자 참여를 측정할 수 있습니다. 노출 횟수 [수집과](/help/using/integration/media-data-integration/impression-data-pixels.md)유사하게, 처리를 위해 이벤트 호출이 [!DNL Audience Manager] 데이터 수집 서버([!DNL DCS])로 전송됩니다. 그런 다음 방문자는 의도한 웹 주소로 리디렉션됩니다.

>[!NOTE]
>
>클라이언트 도메인에 대한 정확한 정보는 [!DNL Audience Manager] 컨설팅 또는 계정 리드 [!DNL URL] 에 문의하십시오.

## 요구 사항

클릭 추적 호출에는 다음 매개 변수가 필요합니다.

* `d_event=click`:이벤트 호출을 클릭 이벤트로 식별하는 키-값 쌍입니다.
* `d_rd=redirect URL`:이중 인코딩된 리디렉션을 포함하는 키-값 쌍입니다 [!DNL URL]. 온라인 인코딩 도구를 사용하는 경우 인코더를 통해 문자열을 실행한 다음 리디렉션이 제대로 작동하도록 결과를 다시 인코딩합니다.

또한 호출에는 트레이트 자격 또는 다른 보고서에 대한 데이터 및 메타데이터를 제공하는 데 사용할 수 있는 키-값 쌍을 포함할 수 있습니다.

## 요청 샘플

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## 응답

이 응답으로 브라우저가 매개 변수에 [!DNL URL] 지정된 것으로 `d_rd` 리디렉션됩니다. 응답 문자열에는 아래 나열된 지원되는 매크로에서 생성된 값이 포함될 수 있습니다.

위의 예를 기준으로 브라우저가 다음으로 리디렉션됩니다 [!DNL URL].

`https://adobe.com/callback?creative=123`

## 지원되는 매크로

다음 표에 나열된 매크로를 지원하는 클릭 이벤트를 클릭합니다. 매크로는 캠페인 및 사용자 추적을 위해 광고 태그가 로드될 때 활성화되는 자체 포함 코드의 작은 단위입니다. 매크로는 다음 형식으로 표시된 [!DNL URL]경우 대상과 함께 전달됩니다. `%macro%`. 일부 키에는 매크로가 없으며 대신 하드 코딩된 ID 값을 수락합니다. Audience Optimization 보고서에서 데이터를 분석하려면 하드 코딩된 값을 받아들이는 키가 [필요합니다](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

<table id="table_6EB65C3B7D0E49C59AA6C932549E33FC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 키 </th> 
   <th colname="col02" class="entry"> 매크로 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_adgroup</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_adgroup%</code> </p> </td> 
   <td colname="col2"> <p>광고 서버의 숫자 광고 그룹 ID. </p> <p>선택 사항입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col02"> <p>매크로가 없습니다. </p> <p>하드 코딩된 ID 값을 수락합니다. </p> </td> 
   <td colname="col2"> <p>광고주 ID.</p> <p>광고주의 데이터 소스에 대한 통합 코드입니다. Audience Manager 데이터 소스는 관련이 없습니다.</p> <p> Audience Optimization 보고서에 <span class="wintitle"> 필요합니다</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_bu%</code> </p> </td> 
   <td colname="col2"> <p>사업부의 숫자 ID. </p> <p> Audience Optimization 보고서에 <span class="wintitle"> 필요합니다</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_campaign%</code> </p> </td> 
   <td colname="col2"> <p>광고 서버의 숫자 캠페인 ID. </p> <p> Audience Optimization 보고서에 <span class="wintitle"> 필요합니다</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_creative%</code> </p> </td> 
   <td colname="col2"> <p>광고 서버의 숫자 크리에이티브 ID. </p> <p>필수 여부. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_id%</code> </p> </td> 
   <td colname="col2"> <p>데이터 공급자 ID. </p> <p>데이터 공급자 ID <code> d_dpuuid</code> 를 사용자 ID에 연결하는 데 사용되는 경우가 많습니다. </p> <p>선택 사항입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_dpuuid%</code> </p> </td> 
   <td colname="col2"> <p>데이터 공급자가 제공한 고유 사용자 ID. </p> <p>데이터 공급자 ID <code> d_dpid</code> 에 사용자 ID를 연결하는 데 사용되는 경우가 많습니다. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_mid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_mid%</code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"></span> ECID(Experience Cloud ID). For more information about the ECID, see <a href="https://docs.adobe.com/content/help/ko-KR/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </p> <p>선택 사항입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_placement</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_placement%</code> </p> </td> 
   <td colname="col2"> <p>광고 서버의 숫자 배치 ID. </p> <p>선택 사항입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_region</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_region%</code> </p> </td> 
   <td colname="col2"> <p>요청을 제공하는 DCS 클러스터의 숫자 영역 ID. DCS에 대한 자세한 내용은 데이터 수집 구성 <a href="../../reference/system-components/components-data-collection.md"> 요소를 참조하십시오</a>. </p> <p>선택 사항입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> r_rand</code> </p> </td> 
   <td colname="col02"> <p> <code> %r_rand%</code> </p> </td> 
   <td colname="col2"> <p>캐시 버싱에 사용되는 무작위 번호입니다. </p> <p>선택 사항입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_site</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_site%</code> </p> </td> 
   <td colname="col2"> <p>광고 서버의 숫자 사이트 ID. </p> <p>선택 사항입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_src</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_src%</code> </p> </td> 
   <td colname="col2"> <p>Audience Manager이 메타데이터를 가져오는 소스의 DPID입니다. </p> <p>필수 여부. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_uuid%</code> </p> </td> 
   <td colname="col2"> <p>Demdex 쿠키에 의존하는 대신 URL에서 직접 방문자 ID를 지정합니다. </p> <p>선택 사항입니다. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr}</code> </p> </td> 
   <td colname="col2"> <p><a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">IAB TCF용 Audience Manager 플러그인</a>과 관련이 있습니다. </p><p><code>gdpr</code> 0일 수(GDPR은 적용되지 않음) 또는 1(GDPR 적용)일 수 있습니다.</p> <p>기본값은 0입니다.</p><p>선택 사항입니다.</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_consent</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr_consent_XXXX}</code> </p> </td> 
   <td colname="col2"> <p><a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">IAB TCF용 Audience Manager 플러그인</a>과 관련이 있습니다.</p><p> 이 경우 <code>gdpr=1</code>문자열 <code>${gdpr_consent_XXXX}</code> 과 공급업체 ID로 대체됩니다(IAB 사양 <code>gdpr_consent</code> 참조 <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external"></a>).</p> <p>기본값은 0입니다.</p><p>선택 사항입니다.</p></td> 
  </tr> 
 </tbody> 
</table>

## 매크로 예

이 예에서는 크리에이티브, adgroup 및 배치 매크로를 전달하는 방법을 보여 줍니다. 이 프로세스에서는 각 매개 변수의 값이 클릭 추적 호출의 리디렉션이 아닌 부분에 전달된다고 가정합니다.

<ul class="simplelist"> 
 <li> <code> creative=1235 </code> </li> 
 <li> <code> campaign=4709 </code> </li> 
 <li> <code> adgroup=3408 </code> </li> 
 <li> <code> placement=1001 </code> </li> 
 <li> <code> src=203 </code> </li> 
</ul>

## 요청

```
https://client.demdex.net/event?d_event=click&d_creative=1235&d_src=203&d_campaign=4709&d_adgroup=3408&d_placement=1001&
d_rd%3Dhttp%253A%252F%252Fadobe.com%252Fcallback%253Fcreative%253D%2525d_creative%2525%2526campaign%253D%2525d_campaign%2525%2526adgroup%253D%2525%0Ad_adgroup%2525%2526d_placement%253D%2525placement%2525%2526src%253D%2525d_src%2525
```

## 응답

위의 예를 기준으로 브라우저가 다음으로 리디렉션됩니다 [!DNL URL].

`https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`

## 추가 기능 - [!UICONTROL Audience Optimization Reports]

픽셀 호출을 사용하여 [Audience Optimization 보고서에 전원을 공급할 수 있습니다](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md). 보고서 [에](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) 강력한 픽셀을 사용하려면 메타데이터 파일에 대한 개요 및 매핑을 참조하십시오.


>[!MORELIKETHIS]
>
>* [Audience Optimization 보고서용 데이터 및 메타데이터 파일](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

