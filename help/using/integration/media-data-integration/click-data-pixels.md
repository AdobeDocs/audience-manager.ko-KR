---
description: 'null'
seo-description: 'null'
seo-title: 픽셀 호출을 통해 캠페인 클릭 데이터 캡처
solution: Audience Manager
title: 픽셀 호출을 통해 캠페인 클릭 데이터 캡처
uuid: 7 C 3797 F 7-9674-493 D -972 B -38 BE 0584 Fede
translation-type: tm+mt
source-git-commit: c79c2311c3ea76ce2450dc1b84a7a22b60a6edb7

---


# Capturing Campaign Click Data via Pixel Calls {#capturing-campaign-click-data-via-pixel-calls}

클릭 추적을 사용하면 타사 크리에이티브 전문가를 위한 클릭 기반 활동을 기록하므로 캠페인 전체에서 방문자 참여를 측정할 수 있습니다. Similar to impressions collection, an event call is sent to the Audience Manager data collection servers ([!UICONTROL DCS]) for processing. 그러면 방문자가 의도한 웹 주소로 리디렉션됩니다.

## 요구 사항

클릭 추적 호출을 사용하려면 다음 매개 변수가 필요합니다.

* `d_event=click`: 이벤트 호출을 클릭 이벤트로 식별하는 키-값 쌍.
* `d_rd=redirect URL`: 인코딩된 리디렉션이 [!DNL URL]포함된 키-값 쌍.

또한 호출에는 트레이트 자격 조건에 사용할 수 있거나 다른 보고서에 대한 데이터와 메타데이터를 제공할 수 있는 키-값 쌍이 포함될 수 있습니다.

## 요청 샘플

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## 응답

The response redirects the browser to the [!DNL URL] specified in the `d_rd` parameter. 응답 문자열에는 아래 나열된 지원되는 매크로에 의해 생성된 값이 포함될 수 있습니다.

Based on the above example, the browser is redirected to the following [!DNL URL]:

[!DNL `https://adobe.com/callback?creative=123`]

## 지원되는 매크로

Click Events는 다음 표에 나열된 매크로를 지원합니다. 매크로는 캠페인 및 사용자 추적을 위해 광고 태그가 로드될 때 활성화되는 작은 자체 포함 코드입니다. The macros will be passed along with the destination [!DNL URL], as long as they are marked with the following format: `%macro%`. 일부 키에 매크로가 없고 하드 코딩된 ID 값을 대신 수락합니다. Keys that accept hard coded values are required if you want to analyze data in the [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

<table id="table_6EB65C3B7D0E49C59AA6C932549E33FC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 키 </th> 
   <th colname="col02" class="entry"> macro </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ adgroup</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ adgroup %</code> </p> </td> 
   <td colname="col2"> <p>광고 서버의 숫자 광고 그룹 ID. </p> <p>선택 사항입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ adsrc</code> </p> </td> 
   <td colname="col02"> <p>매크로가 없습니다. </p> <p>하드 코딩된 ID 값을 수락합니다. </p> </td> 
   <td colname="col2"> <p> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> 광고주의 데이터 소스</a> ID 또는 통합 코드. </p> <p> <span class="wintitle"> 대상 최적화</span> 보고서에 필요합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ bu</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ bu %</code> </p> </td> 
   <td colname="col2"> <p>사업부의 숫자 ID 입니다. </p> <p> <span class="wintitle"> 대상 최적화</span> 보고서에 필요합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ campaign %</code> </p> </td> 
   <td colname="col2"> <p>광고 서버의 숫자 캠페인 ID 입니다. </p> <p> <span class="wintitle"> 대상 최적화</span> 보고서에 필요합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ creative</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ creative %</code> </p> </td> 
   <td colname="col2"> <p>광고 서버의 숫자 크리에이티브 ID. </p> <p>필수 여부. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpid</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ id %</code> </p> </td> 
   <td colname="col2"> <p>데이터 공급자 ID. </p> <p>Often used with <code> d_dpuuid</code> to link a data provider ID to a user ID. </p> <p>선택 사항입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpuuid</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ dpuuid %</code> </p> </td> 
   <td colname="col2"> <p>데이터 공급자가 제공한 고유한 사용자 ID 입니다. </p> <p><code> d_ dpid</code> 와 함께 사용되어 사용자 ID를 데이터 공급자 ID에 연결합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_mid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_mid%</code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> ECID(Experience Cloud ID). </span> For more information about the ECID, see <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </p> <p>선택 사항입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ placement</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ placement %</code> </p> </td> 
   <td colname="col2"> <p>광고 서버의 숫자 배치 ID. </p> <p>선택 사항입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> D_ region</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ region %</code> </p> </td> 
   <td colname="col2"> <p>요청을 처리하는 DCS 클러스터의 숫자 영역 ID 입니다. For more information about the DCS, see <a href="../../reference/system-components/components-data-collection.md"> Data Collection Components</a>. </p> <p>선택 사항입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> r_ rand</code> </p> </td> 
   <td colname="col02"> <p> <code> % r_ rand %</code> </p> </td> 
   <td colname="col2"> <p>캐시 제거에 사용되는 무작위 번호입니다. </p> <p>선택 사항입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ site</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ site %</code> </p> </td> 
   <td colname="col2"> <p>광고 서버의 숫자 사이트 ID. </p> <p>선택 사항입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ src</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ src %</code> </p> </td> 
   <td colname="col2"> <p>Audience Manager가 메타데이터를 가져오는 소스의 DPID 입니다. </p> <p>필수 여부. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ uuid</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ uuid %</code> </p> </td> 
   <td colname="col2"> <p>demdex 쿠키를 사용하지 않고 URL에서 직접 방문자의 ID를 지정합니다. </p> <p>선택 사항입니다. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>GDPR</code> </p> </td> 
   <td colname="col02"> <p> <code>% GDPR_ APPLY %</code> </p> </td> 
   <td colname="col2"> <p><a href="../../overview/aam-gdpr/aam-iab-plugin.md">IAB TCF용 Audience Manager 플러그인</a>과 관련이 있습니다. </p><p><code>GDPR</code> 는 0 (GDPR는 적용되지 않음) 또는 1 (GDPR 적용) 이 될 수 있습니다.</p> <p>기본값은 0입니다.</p><p>선택 사항입니다.</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>GDPR_ 동의</code> </p> </td> 
   <td colname="col02"> <p> <code>% GDPR_ CONSENT %</code> </p> </td> 
   <td colname="col2"> <p><a href="../../overview/aam-gdpr/aam-iab-plugin.md">IAB TCF용 Audience Manager 플러그인</a>과 관련이 있습니다.</p><p> <code>gdpr=1</code>이면 <code>%gdpr_consent%</code>는 <code>gdpr_consent</code> 문자열로 대체됩니다(<a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB 사양</a> 참조).</p> <p>기본값은 0입니다.</p><p>선택 사항입니다.</p></td> 
  </tr> 
 </tbody> 
</table>

## 매크로 예제

이 예에서는 Creative, adgroup 및 배치 매크로를 전달하는 방법을 보여 줍니다. 여기서는 각 매개 변수에 대한 값이 클릭 추적 호출의 비리디렉션 부분에서 전달된다고 가정합니다.

<ul class="simplelist"> 
 <li> <code> creative = 1235 </code> </li> 
 <li> <code> campaign = 4709 </code> </li> 
 <li> <code> adgroup = 3408 </code> </li> 
 <li> <code> placement = 1001 </code> </li> 
 <li> <code> src = 203 </code> </li> 
</ul>

## 요청

```
https://client.demdex.net/event?d_event=click&d_creative=1235&d_src=203&d_campaign=4709&d_adgroup=3408&d_placement=1001&
d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25%26campaign%3D%25d_campaign%25%26adgroup%3D%25
d_adgroup%25%26d_placement%3D%25placement%25%26src%3D%25d_src%25
```

## 응답

Based on the above example, the browser is redirected to the following [!DNL URL]:

[!DNL `https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`]

>[!MORE_ like_ this]
>
>* [대상 최적화 보고서를 위한 데이터 및 메타데이터 파일](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

