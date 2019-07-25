---
description: 미디어 데이터를 Audience Manager로 보내는 한 가지 접근 방법은 광고 서버 매크로를 사용하여 캠페인 속성을 Audience Manager로 보냅니다.
seo-description: 미디어 데이터를 Audience Manager로 보내는 한 가지 접근 방법은 광고 서버 매크로를 사용하여 캠페인 속성을 Audience Manager로 보냅니다.
seo-title: 픽셀 호출을 통해 캠페인 노출 횟수 데이터 캡처
solution: Audience Manager
title: 픽셀 호출을 통해 캠페인 노출 횟수 데이터 캡처
uuid: 6 AC 44100-4 C 55-4992-8835-0 D 578 BB 4 E 5 C 2
translation-type: tm+mt
source-git-commit: c79c2311c3ea76ce2450dc1b84a7a22b60a6edb7

---


# 픽셀 호출을 통해 캠페인 노출 횟수 데이터 캡처{#capturing-campaign-impression-data-via-pixel-calls}

미디어 데이터를 Audience Manager로 보내는 한 가지 접근 방법은 광고 서버 매크로를 사용하여 캠페인 속성을 Audience Manager로 보냅니다.

이 방법은 종종 "크리에이티브" 로 불립니다. Those data points are dynamically inserted into the [!DNL Audience Manager] pixel code by the third-party ad server macros, which are used to map and report all impressions and clicks based on the key reporting attributes of the campaign. 집계된 데이터는 캠페인 성능에 대한 통합 뷰를 제공하며, 사용자 지정 전환 경로를 식별하며, 고객이 전환을 유도하는 광고 서버 이벤트의 시퀀스를 개선할 수 있도록 도와줍니다.

## 이벤트 호출 구문

>[!NOTE]
>
>텍스트 스타일(`monospaced text`, *기울임체*, 괄호 `[ ]``( )` 등)은 코드 요소 및 옵션을 나타냅니다. 자세한 내용은 [코드 및 텍스트 요소에 대한 스타일 규칙](../../reference/code-style-elements.md)을 참조하십시오.

이벤트 호출은 노출 및 전환 데이터를 수집하여 [!DNL Audience Manager] [데이터 수집 서버](/help/using/reference/system-components/components-data-collection.md) ([!UICONTROL DCS])로 보냅니다. 이 프로세스는 코드에 삽입되는 콘텐츠를 제어하는 호출을 크리에이티브에 배치하는 타사 광고 서버를 사용합니다. 타사 광고 서버(예로는 [!DNL DFA])에서는 각 광고 노출 내에 이 코드를 배치할 수 있습니다. 또한 광고 호출은 광고 태그 외부의 게시자 데이터에 액세스할 때 [!DNL JavaScript]를 사용하거나 프레임 버스팅 기술을 사용하지 않습니다.

이벤트 호출은 다음 구문을 사용하는 키-값 쌍으로 구성됩니다.

<pre>
http://clientname.demdex.net/event?d_event=imp&amp;d_src=datasource_id&amp;d_site=siteID&amp;
d_creative=<i>creative_id</i>&amp;d_adgroup=<i>adgroup_id</i>&amp;d_placement=<i>placement_id</i>
&amp;d_campaign=<i>campaign_id</i>[&amp;d_cid=(GAID|IDFA)%01 DPUUID]&amp;d_bust=cache buster value
</pre>

키-값 쌍의 값 변수는 광고 서버에 의해 삽입된 ID 또는 매크로입니다. When the ad tag loads, that `%macro%` gets replaced with the required, corresponding values. 이 호출은 응답을 반환하지 않습니다.

## Supported Key-Value Pairs {#supported-key-value-pairs}

노출 이벤트 호출은 키-값 쌍으로 구성된 데이터를 승인합니다. 다음 표에서는 이러한 변수를 보관하는 데 사용된 키에 대해 설명하고 설명합니다. Many of these are required if you want to capture and analyze data in the [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

<table id="table_F068C4D49F7D4775924D3CA712BF15BA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 키 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> d_ adgroup </code> </td> 
   <td colname="col2"> <p>광고 서버의 숫자 광고 그룹 ID. </p> <p>선택 사항입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ adsrc </code> </td> 
   <td colname="col2"> <p>광고주의 데이터 소스 ID 또는 통합 코드. </p> <p><span class="wintitle"> 대상 최적화 </span> 보고서에 필요합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ bu </code> </td> 
   <td colname="col2"> <p>비즈니스 단위를 위한 데이터 소스 ID 또는 통합 코드. </p> <p><span class="wintitle"> 대상 최적화 </span> 보고서에 필요합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ bust </code> </p> </td> 
   <td colname="col2"> <p>캐시 분할 값. <span class="keyword"> Audience Manager </span> 는 대부분의 브라우저와 프록시에서 지향하는 캐시 제어 헤더를 자동으로 보냅니다. 추가적인 캐시 분할을 수행하려면 이벤트 호출에 이 매개 변수를 포함시킨 다음 임의의 문자열을 추가합니다. </p> <p> 선택 사항입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ campaign </code> </td> 
   <td colname="col2"> <p>광고 서버의 숫자 캠페인 ID 입니다. </p> <p><span class="wintitle"> 대상 최적화 </span> 보고서에 필요합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_cid </code> </td> 
   <td colname="col2"> <p>In this context, <code> d_cid </code> instantiates a key-value pair that lets you associate a mobile device type to a unique user ID (DPUUID). 고정 ID는 모바일 장치 유형을 결정합니다. 사용자 ID 인 값은 다를 수 있습니다. Separate the key-value pair with <code> %01 </code>, which is a non-printing control character. 이 매개 변수는 다음 키를 수용합니다. </p> 
    <ul id="ul_4D5D696D10B34615867AF3B64A938878"> 
     <li id="li_A4BD4B0C8C9443BF99075CDFACC013F6">20914: Android (Gaid) 장치를 식별합니다. For example, <code> d_cid = 20914 %01 1234 </code> says that user 1234 is associated with an Android device. </li> 
     <li id="li_F83D7B3EC4D24D0187BFE639E2812B36">20915: iOS (IDFA) 장치를 식별합니다. For example, <code> d_cid = 20915 %01 5678 </code> says that user 5678 is associated with an iOS device. </li> 
    </ul> <p>선택 사항입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ creative </code> </td> 
   <td colname="col2"> <p>광고 서버의 숫자 크리에이티브 ID. </p> <p><span class="wintitle"> 대상 최적화 </span> 보고서에 필요합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ event = IMP </code> </td> 
   <td colname="col2"> <p>이벤트 호출을 노출 이벤트로 식별합니다. </p> <p>필수 여부. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ placement </code> </td> 
   <td colname="col2"> <p>광고 서버의 숫자 배치 ID. </p> <p> 선택 사항입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ site </code> </td> 
   <td colname="col2"> <p>광고 서버의 숫자 사이트 ID. </p> <p><span class="wintitle"> 대상 최적화 </span> 보고서에 필요합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ src </code> </td> 
   <td colname="col2"> <p>메타데이터를 제공하는 플랫폼의 데이터 소스 ID 또는 통합 코드 (예: DFA, Atlas, GBM, Media Math 등). </p> <p><span class="wintitle"> 대상 최적화 </span> 보고서에 필요합니다. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <code><i>GDPR</i></code>  </td> 
   <td colname="col2"> <p><a href="../../overview/aam-gdpr/aam-iab-plugin.md">IAB TCF용 Audience Manager 플러그인</a>과 관련이 있습니다.</p> <p><code>GDPR</code> 는 0 (GDPR는 적용되지 않음) 또는 1 (GDPR 적용) 이 될 수 있습니다.</p> <p>기본값은 0입니다.</p><p>선택 사항입니다.</p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <code>GDPR_ 동의</code> </td> 
   <td colname="col2"> <p><a href="../../overview/aam-gdpr/aam-iab-plugin.md">IAB TCF용 Audience Manager 플러그인</a>과 관련이 있습니다.</p><p> <code>gdpr=1</code>이면 <code>%gdpr_consent%</code>는 <code>gdpr_consent</code> 문자열로 대체됩니다(<a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB 사양</a> 참조).</p> <p>기본값은 0입니다.</p><p>선택 사항입니다.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>클라이언트 도메인에 대한 정확한 URL는 Adobe Audience Manager 컨설팅 또는 계정 리드 담당자에게 문의하십시오.

>[!MORE_ like_ this]
>
>* [대상 최적화 보고서를 위한 데이터 및 메타데이터 파일](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

