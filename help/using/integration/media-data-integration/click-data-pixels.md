---
description: 'null'
seo-description: 'null'
seo-title: 픽셀 호출을 통해 캠페인 클릭 데이터 캡처
solution: Audience Manager
title: 픽셀 호출을 통해 캠페인 클릭 데이터 캡처
uuid: 7c3797f7-9674-49 파섹
translation-type: tm+mt
source-git-commit: dbc96973ed2214d171fe32b7e1314d40c22c2d79

---


# Capturing Campaign Click Data via Pixel Calls {#capturing-campaign-click-data-via-pixel-calls}

클릭 추적을 사용하면 타사 크리에이티브를 위한 클릭 기반 활동을 기록하므로 캠페인 전체에서 방문자 참여를 측정할 수 있습니다. 노출 횟수 수집과 마찬가지로 이벤트 호출은 처리를 위해 Audience Manager 데이터 수집 서버([!UICONTROL DCS])로 전송됩니다. 그러면 방문자가 의도한 웹 주소로 리디렉션됩니다.

## 요구 사항

클릭 추적 호출에는 다음 매개 변수가 필요합니다.

* `d_event=click`:이벤트 호출을 클릭 이벤트로 식별하는 키-값 쌍입니다.
* `d_rd=redirect URL`:인코딩된 리디렉션을 포함하는 키-값 쌍입니다 [!DNL URL].

또한 호출에는 트레이트 자격에 사용하거나 다른 보고서에 대한 데이터 및 메타데이터를 제공하는 키-값 쌍을 포함할 수 있습니다.

## 요청 샘플

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## 응답

응답은 브라우저를 매개 변수에 [!DNL URL] 지정된 것으로 리디렉션합니다 `d_rd` . 응답 문자열에는 아래 나열된 지원되는 매크로에서 생성된 값이 포함될 수 있습니다.

위의 예를 기준으로 브라우저가 다음 내용으로 리디렉션됩니다. [!DNL URL]

[!DNL `https://adobe.com/callback?creative=123`]

## 지원되는 매크로

클릭 이벤트는 다음 표에 나열된 매크로를 지원합니다. 매크로는 캠페인 및 사용자 추적을 위해 광고 태그가 로드될 때 활성화되는 자체 포함 코드의 작은 단위입니다. 매크로는 다음 형식으로 표시된 [!DNL URL]경우 대상과 함께 전달됩니다. `%macro%`Adobe 일부 키에 매크로가 없으며 대신 하드 코딩된 ID 값을 수락합니다. 대상 최적화 보고서에서 데이터를 분석하려는 경우 하드 코딩된 값을 허용하는 [키가 필요합니다](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

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
   <td colname="col2"> <p>광고주 ID.</p> <p>광고주의 데이터 소스에 대한 통합 코드입니다. 이 데이터는 Audience Manager 데이터 소스와 관련이 없습니다.</p> <p> 대상 최적화 <span class="wintitle"> 보고서에</span> 필요합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_bu%</code> </p> </td> 
   <td colname="col2"> <p>사업부의 숫자 ID입니다. </p> <p> 대상 최적화 <span class="wintitle"> 보고서에</span> 필요합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_campaign%</code> </p> </td> 
   <td colname="col2"> <p>광고 서버의 숫자 캠페인 ID. </p> <p> 대상 최적화 <span class="wintitle"> 보고서에</span> 필요합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_creative%</code> </p> </td> 
   <td colname="col2"> <p>광고 서버의 숫자 크리에이티브 ID. </p> <p>필수 여부. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_id%</code> </p> </td> 
   <td colname="col2"> <p>데이터 공급자 ID. </p> <p>데이터 공급자 ID를 <code> 사용자 ID에</code> 연결하는 데 종종 d_dpuuid와 함께 사용됩니다. </p> <p>선택 사항입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_dpuuid%</code> </p> </td> 
   <td colname="col2"> <p>데이터 공급자가 제공한 고유한 사용자 ID입니다. </p> <p>사용자 ID를 데이터 <code> 공급자 ID에</code> 연결하는 데 종종 d_dpid와 함께 사용됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_mid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_mid%</code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> ECID(Experience Cloud ID). </span> For more information about the ECID, see <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </p> <p>선택 사항입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_placement</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_placement%</code> </p> </td> 
   <td colname="col2"> <p>광고 서버의 숫자 배치 ID. </p> <p>선택 사항입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_region</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_region%</code> </p> </td> 
   <td colname="col2"> <p>요청을 제공하는 DCS 클러스터의 숫자 영역 ID입니다. DCS에 대한 자세한 내용은 데이터 수집 구성 요소를 <a href="../../reference/system-components/components-data-collection.md"> 참조하십시오</a>. </p> <p>선택 사항입니다. </p> </td> 
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
   <td colname="col2"> <p>Audience Manager가 메타데이터를 가져오는 소스의 DPID입니다. </p> <p>필수 여부. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_uuid%</code> </p> </td> 
   <td colname="col2"> <p>Demdex 쿠키에 의존하지 않고 URL에서 직접 방문자 ID를 지정합니다. </p> <p>선택 사항입니다. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr</code> </p> </td> 
   <td colname="col02"> <p> <code>%gdpr_apples%</code> </p> </td> 
   <td colname="col2"> <p><a href="../../overview/aam-gdpr/aam-iab-plugin.md">IAB TCF용 Audience Manager 플러그인</a>과 관련이 있습니다. </p><p><code>gdpr은</code> 0(GDPR은 적용되지 않음) 또는 1(GDPR 적용)일 수 있습니다.</p> <p>기본값은 0입니다.</p><p>선택 사항입니다.</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_consgent</code> </p> </td> 
   <td colname="col02"> <p> <code>%gdpr_consent%</code> </p> </td> 
   <td colname="col2"> <p><a href="../../overview/aam-gdpr/aam-iab-plugin.md">IAB TCF용 Audience Manager 플러그인</a>과 관련이 있습니다.</p><p> <code>gdpr=1</code>이면 <code>%gdpr_consent%</code>는 <code>gdpr_consent</code> 문자열로 대체됩니다(<a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB 사양</a> 참조).</p> <p>기본값은 0입니다.</p><p>선택 사항입니다.</p></td> 
  </tr> 
 </tbody> 
</table>

## 매크로 예

이 예에서는 크리에이티브, adgroup 및 배치 매크로를 전달하는 방법을 보여줍니다. 각 매개 변수의 값이 클릭 추적 호출의 비리디렉션 부분에 전달된다고 가정합니다.

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
d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25%26campaign%3D%25d_campaign%25%26adgroup%3D%25
d_adgroup%25%26d_placement%3D%25placement%25%26src%3D%25d_src%25
```

## 응답

위의 예를 기준으로 브라우저가 다음 내용으로 리디렉션됩니다. [!DNL URL]

[!DNL `https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`]

>[!MORELIKE_THIS]
>
>* [대상 최적화 보고서를 위한 데이터 및 메타데이터 파일](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

