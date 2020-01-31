---
description: Audience Manager로 미디어 데이터를 전송하는 한 가지 방법은 광고 서버 매크로를 사용하여 캠페인 속성을 Audience Manager로 보냅니다.
seo-description: Audience Manager로 미디어 데이터를 전송하는 한 가지 방법은 광고 서버 매크로를 사용하여 캠페인 속성을 Audience Manager로 보냅니다.
seo-title: 픽셀 호출을 통해 캠페인 노출 횟수 데이터 캡처
solution: Audience Manager
title: 픽셀 호출을 통해 캠페인 노출 횟수 데이터 캡처
uuid: 6ac44100-4c55-4992-8835-0d578bb4e5c2
translation-type: tm+mt
source-git-commit: 132e36175a69a270ea608643049931fbc06efc69

---


# 픽셀 호출을 통해 캠페인 노출 횟수 데이터 캡처{#capturing-campaign-impression-data-via-pixel-calls}

Audience Manager로 미디어 데이터를 전송하는 한 가지 방법은 광고 서버 매크로를 사용하여 캠페인 속성을 Audience Manager로 보냅니다.

이 방법론은 종종 &quot;창의력을 모사화&quot;라고 합니다. 이러한 데이터 포인트는 캠페인의 주요 보고 속성을 기반으로 모든 노출 및 클릭 수를 매핑하고 보고하는 데 사용되는 타사 광고 서버 매크로가 [!DNL Audience Manager] 픽셀 코드에 동적으로 삽입됩니다. 집계된 데이터는 캠페인 성능에 대한 통합된 보기를 제공하고 사용자 지정 전환 경로를 식별하며 고객이 전환으로 이어지는 광고 서버 이벤트의 시퀀스를 개선할 수 있도록 도와줍니다.

## 이벤트 호출 구문

>[!NOTE]
>
>텍스트 스타일(`monospaced text`, *기울임체*, 괄호 `[ ]``( )` 등)은 코드 요소 및 옵션을 나타냅니다. 자세한 내용은 [코드 및 텍스트 요소에 대한 스타일 규칙](../../reference/code-style-elements.md)을 참조하십시오.

이벤트 호출은 노출 및 전환 데이터를 수집하여 [!DNL Audience Manager] [데이터 수집 서버](/help/using/reference/system-components/components-data-collection.md) ([!UICONTROL DCS])로 보냅니다. 이 프로세스는 코드에 삽입되는 콘텐츠를 제어하는 호출을 크리에이티브에 배치하는 타사 광고 서버를 사용합니다. 타사 광고 서버(예로는 [!DNL DFA])에서는 각 광고 노출 내에 이 코드를 배치할 수 있습니다. 또한 광고 호출은 광고 태그 외부의 게시자 데이터에 액세스할 때 [!DNL JavaScript]를 사용하거나 프레임 버스팅 기술을 사용하지 않습니다.

이벤트 호출은 다음 구문을 사용하는 키-값 쌍으로 구성됩니다.

```
http://clientname.demdex.net/event?d_event=imp&d_src=datasource_id&d_site=siteID&d_creative=<i>creative_id</i>&d_adgroup=<i>adgroup_id</i>&d_placement=<i>placement_id</i>&d_campaign=<i>campaign_id</i>[&d_cid=(GAID|IDFA)%01 DPUUID]&d_bust=cache buster value
```

키-값 쌍에서 값 변수는 광고 서버에서 삽입한 ID 또는 매크로입니다. 광고 태그가 로드되면 해당 값이 필수 값으로 `%macro%` 대체됩니다. 이 호출은 응답을 반환하지 않습니다.

## 지원되는 키-값 쌍 {#supported-key-value-pairs}

노출 이벤트 호출은 키-값 쌍으로 구성된 데이터를 허용합니다. 다음 표에서는 이러한 변수를 보유하는 데 사용되는 키를 나열하고 설명합니다. 대상 최적화 보고서에서 데이터를 캡처하고 분석하려는 경우 이 중 [다수가 필요합니다](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

<table id="table_F068C4D49F7D4775924D3CA712BF15BA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 키 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> d_adgroup </code> </td> 
   <td colname="col2"> <p>광고 서버의 숫자 광고 그룹 ID. </p> <p>선택 사항입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_adsrc </code> </td> 
   <td colname="col2"> <p>광고주의 데이터 소스 ID 또는 통합 코드. </p> <p>대상 최적화 <span class="wintitle"> 보고서에 </span> 필요합니다. </p> <p>선택 사항입니다.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_bu </code> </td> 
   <td colname="col2"> <p>사업부의 데이터 소스 ID 또는 통합 코드 </p> <p>대상 최적화 <span class="wintitle"> 보고서에 </span> 필요합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bust </code> </p> </td> 
   <td colname="col2"> <p>캐시 업데이트 값입니다. <span class="keyword"> Audience Manager는 대부분의 브라우저와 프록시에서 부여한 캐시 제어 헤더를 </span> 자동으로 전송합니다. 추가 캐시 빌드를 수행하려면 이벤트 호출에 이 매개 변수를 포함시키고 임의의 문자열을 포함하십시오. </p> <p> 선택 사항입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_campaign </code> </td> 
   <td colname="col2"> <p>광고 서버의 숫자 캠페인 ID. </p> <p>대상 최적화 <span class="wintitle"> 보고서에 </span> 필요합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_cid </code> </td> 
   <td colname="col2"> <p>이 컨텍스트에서 모바일 장치 유형을 고유 사용자 ID(DPUUID)에 연결할 수 있는 키-값 쌍을 <code> d_cid </code> 인스턴스화합니다. 고정 ID가 모바일 장치 유형을 결정합니다. 사용자 ID인 값은 달라질 수 있습니다. 키-값 쌍을 인쇄 금지 컨트롤 <code> %01 </code>문자인 로 구분합니다. 이 매개 변수는 다음 키를 사용합니다. </p> 
    <ul id="ul_4D5D696D10B34615867AF3B64A938878"> 
     <li id="li_A4BD4B0C8C9443BF99075CDFACC013F6">2014년:Android(GAID 파섹) 장치를 식별합니다. 예를 들어 사용자 1234는 Android 장치와 연결되어 있다고 <code> d_cid = 20914 %01 1234 </code> 합니다. </li> 
     <li id="li_F83D7B3EC4D24D0187BFE639E2812B36">2015년:iOS(IDFA) 장치를 식별합니다. 예를 들어 <code> d_cid = 20915 %01 5678 </code> 사용자 5678은 iOS 장치와 연결되어 있다고 말합니다. </li> 
    </ul> <p>선택 사항입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_creative </code> </td> 
   <td colname="col2"> <p>광고 서버의 숫자 크리에이티브 ID. </p> <p>대상 최적화 <span class="wintitle"> 보고서에 </span> 필요합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_event=imp </code> </td> 
   <td colname="col2"> <p>이벤트 호출을 노출 이벤트로 식별합니다. </p> <p>필수 여부. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_placement </code> </td> 
   <td colname="col2"> <p>광고 서버의 숫자 배치 ID. </p> <p> 선택 사항입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_site </code> </td> 
   <td colname="col2"> <p>광고 서버의 숫자 사이트 ID. </p> <p>대상 최적화 <span class="wintitle"> 보고서에 </span> 필요합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_src </code> </td> 
   <td colname="col2"> <p>메타데이터를 제공하는 플랫폼의 데이터 소스 ID 또는 통합 코드(예: DFA, Atlas, GBM, Media Math 등)입니다. </p> <p>대상 최적화 <span class="wintitle"> 보고서에 </span> 필요합니다. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <code><i>gdpr</i></code>  </td> 
   <td colname="col2"> <p><a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">IAB TCF용 Audience Manager 플러그인</a>과 관련이 있습니다.</p> <p><code>gdpr</code> 은 0(GDPR은 적용되지 않음) 또는 1(GDPR 적용)일 수 있습니다.</p> <p>기본값은 0입니다.</p><p>선택 사항입니다.</p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <code>gdpr_consent</code> </td> 
   <td colname="col2"> <p><a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">IAB TCF용 Audience Manager 플러그인</a>과 관련이 있습니다.</p><p> <code>gdpr=1</code>이면 <code>%gdpr_consent%</code>는 <code>gdpr_consent</code> 문자열로 대체됩니다(<a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB 사양</a> 참조).</p> <p>기본값은 0입니다.</p><p>선택 사항입니다.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>클라이언트 도메인과 관련된 정확한 URL은 Adobe Audience Manager 컨설팅 또는 계정 리드로 문의하십시오.

## 추가 기능 - 대상 최적화 보고서

픽셀 호출을 사용하여 대상 최적화 보고서를 [강화할 수 있습니다](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md). 보고서 [성능을 높이기 위해](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) 픽셀을 사용하려는 경우 메타데이터 파일에 대한 개요 및 매핑을 참조하십시오.

>[!MORELIKETHIS]
>
>* [대상 최적화 보고서를 위한 데이터 및 메타데이터 파일](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

