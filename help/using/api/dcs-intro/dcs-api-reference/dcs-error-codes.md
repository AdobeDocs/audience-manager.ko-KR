---
description: 코드 ID별로 숫자 순서로 나열된 DCS(데이터 수집 서버)에서 생성된 오류 코드와 메시지.
seo-description: 코드 ID별로 숫자 순서로 나열된 DCS(데이터 수집 서버)에서 생성된 오류 코드와 메시지.
seo-title: DCS 오류 코드, 메시지 및 예제
solution: Audience Manager
title: DCS 오류 코드, 메시지 및 예제
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# DCS 오류 코드, 메시지 및 예제 {#dcs-error-codes-messages-and-examples}

코드 ID별로 [!UICONTROL Data Collection Servers] ([!UICONTROL DCS])가 숫자 순서로 나열한 오류 코드 및 메시지

In the tables below, *italics* represents a variable placeholder.

## 시스템 오류 코드 {#system-error-codes}

<table id="table_43F4321BEA6A4D1BBDFE2E9FB4402914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 코드 ID </th> 
   <th colname="col2" class="entry"> 오류 메시지 </th> 
   <th colname="col3" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>0 </p> </td> 
   <td colname="col2"> <p>지정되지 않은 오류 </p> </td> 
   <td colname="col3"> <p>다른 오류 처리기에서 다루지 않는 이벤트를 처리하는 catch-all 오류입니다. 이 오류를 해결하는 것은 어렵습니다. 알 수 없는 다양한 작업 또는 이벤트로 인해 발생할 수 있습니다. </p> <p>이 오류가 표시되면 DCS <span class="wintitle"> 요청을 다시</span> 시도하십시오. 문제가 지속되면 Adobe 담당자에게 문의하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>호스트 이름에 대한 구성을 찾을 수 없습니다. <code><i>hostname</i></code> </p> </td> 
   <td colname="col3"> <p>요청에서 전송된 호스트 이름이 파트너 프로비저닝 팀에서 설정하지 않았습니다. 이 오류 메시지가 표시되면 Adobe 담당자에게 문의하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>잘못된 <code> d_orgid</code> 값(이 조직 ID에 대한 구성을 찾을 수 없음):ID <code><i></i></code> </p> </td> 
   <td colname="col3"> <p>조직 ID가 잘못되었습니다. </p> <p>ID를 확인하고 요청을 다시 시도하십시오. 조직 ID를 모르거나 보유하고 있는 경우 Experience Cloud 관리의 " <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html" format="https" scope="external"> 관리</a> 페이지" 섹션을 참조하여 조직 ID를 찾는 방법에 대해 알아보십시오. </p> </td> 
  </tr>
 </tbody>
</table>

## 통합 오류 코드 {#integration-error-codes}

<table id="table_EFF06FB3D045459BA7802872AF22DF79"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 코드 ID </th> 
   <th colname="col2" class="entry"> 메시지 </th> 
   <th colname="col3" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>100 </p> </td> 
   <td colname="col2"> <p>요청에 대한 호스트 이름을 검색할 수 없습니다. </p> </td> 
   <td colname="col3"> <p>API 호출이 요청에서 호스트 HTTP 헤더를 전송하지 않았습니다. </p> <p>호스트 헤더를 호출에 추가하고 다시 시도하십시오. 참고, 대부분의 브라우저와 API 클라이언트는 이 작업을 자동으로 수행합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>101 </p> </td> 
   <td colname="col2"> <p>ID로 전달된 Experience Cloud ID가 <code><i>잘못되었습니다.</i></code> </p> </td> 
   <td colname="col3"> <p>DCS <span class="wintitle"> 호출에 잘못된</span> Experience Cloud ID가 <span class="keyword"> 포함되어</span> 있습니다. </p> <p>헤더 문자열에서 <code> d_mid=</code> key-value 쌍을 선택합니다. 올바른 Experience Cloud ID를 전달하고 <span class="keyword"> 있는지</span> 확인하고 요청을 다시 시도하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>102 </p> </td> 
   <td colname="col2"> <p>요청 ID에서 잘못된 Aam ID가 <code><i>전달되었습니다.</i></code> </p> </td> 
   <td colname="col3"> <p>DCS <span class="wintitle"> 호출에 잘못된 Audience</span> Manager ID가 <span class="keyword"> 포함되어</span> 있습니다. </p> <p>헤더 문자열에서 <code> d_uuid=</code> key-value 쌍을 확인합니다. 올바른 Audience Manager ID를 전달하고 <span class="keyword"> 있는지</span> 확인하고 요청을 다시 시도하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>104 </p> </td> 
   <td colname="col2"> <p>모든 고객 ID가 잘못되었습니다. </p> </td> 
   <td colname="col3"> <p>호출의 모든 고객 ID가 잘못되었습니다. ID를 확인하고 다시 시도하십시오. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>111 </p> </td> 
   <td colname="col2"> <p>잘못된 <span class="wintitle"> IMS.</span> 토큰을 받았습니다. </p> </td> 
   <td colname="col3"> <p>Audience Manager에 대해 반환 - Adobe Target 통합. 잘못된 IMS 토큰을 포함하는 DCS를 호출하면 오류가 발생합니다. 토큰의 형식이 잘못되었거나, 만료되었거나, 사용자에게 필요한 리소스에 대한 액세스 권한이 없을 수 있습니다. </p> </td>
  </tr>
 </tbody>
</table>

## 옵트아웃 오류 코드 {#opt-out-error-codes}

<table id="table_A50C284AB84F48A79B01223D991884A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 코드 ID </th> 
   <th colname="col2" class="entry"> 메시지 </th> 
   <th colname="col3" class="entry"> 설명 </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>171 </p> </td> 
   <td colname="col2"> <p>id ID에 대한 옵트아웃 태그가 <code><i>있습니다.</i></code> </p> </td> 
   <td colname="col3"> <p>고객이 관심 기반 광고를 받지 않기로 선택한 경우 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>172 </p> </td> 
   <td colname="col2"> <p>차단된 쿠키 </p> </td> 
   <td colname="col3"> <p>사용자의 브라우저가 타사 쿠키를 차단하면 반환됩니다.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>173 </p> </td> 
   <td colname="col2"> <p>NAI를 통한 신뢰 관계 <a href="https://www.networkadvertising.org/" format="http" scope="external"> 발생</a> </p> </td> 
   <td colname="col3"> <p>사용자가 NAI를 통해 옵트아웃 프로세스를 시작했습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>198 </p> </td> 
   <td colname="col2"> <p>파트너가 이 국가의 요청을 차단합니다. </p> </td> 
   <td colname="col3"> <p>IP 주소를 기준으로 DCS <span class="wintitle"> 는</span> 파트너가 의도적으로 트래픽을 제한한 국가의 요청을 차단합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>이 국가의 요청은 허용되지 않습니다. </p> </td> 
   <td colname="col3"> <p>DCS는 IP 주소를 기반으로 <span class="wintitle"> 다음</span> 국가의 요청을 차단합니다. </p> <p> 
     <ul id="ul_4017A7D074064FE7A8B5618AFCFA4E28"> 
      <li id="li_EE65DEC3C64F4522B214C503DC754DC1">쿠바(CU) </li> 
      <li id="li_EDE8B304D35A41458DCFF11E9328802A">이란(IR) </li> 
      <li id="li_36664315A06540E0BE024EE60638D5DC">북한(KP) </li> 
      <li id="li_B508A5FF173E491AAE41334C074D9DED">수단(SD) </li> 
      <li id="li_0875540C20204158ADBD92698CEB10EA">시리아(SY) </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 프로필 검색 오류 코드 {#profile-retrieval-error-codes}

<table id="table_CFF2252A3CC54960802905454A867D7A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 코드 ID </th> 
   <th colname="col2" class="entry"> 메시지 </th> 
   <th colname="col3" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>200 </p> </td> 
   <td colname="col2"> <p> ID에 대한 프로필 캐시에서 트레이트를 읽을 수 없습니다.ID <code><i></i></code> </p> </td> 
   <td colname="col3"> <p>내부 저장소에서 사용자 프로필을 읽을 수 없을 때 반환됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> 고객 ID에 대한 프로필 캐시에서 장치 ID를 읽을 수 없습니다.ID <code><i></i></code> </p> </td> 
   <td colname="col3"> <p>프로필 링크 병합 규칙에 대해 <a href="../../../reference/ids-in-aam.md"> 장치 ID를</a> 검색할 수 없을 때 반환됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>장치 ID에 대해 관련 고객을 읽을 수 없습니다.ID <code><i></i></code> </p> </td> 
   <td colname="col3"> <p>장치 ID에 연결된 <a href="../../../reference/ids-in-aam.md"> 고객 ID(UUID)</a> 를 내부 저장소에서 마지막 인증된 병합 규칙에 대해 검색할 수 없을 때 반환됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> ID에 대한 장치 클러스터를 읽을 수 없습니다.ID <code><i></i></code> </p> </td> 
   <td colname="col3"> <p>동일한 장치 그래프 클러스터의 연결된 장치 ID는 이 장치 ID에 대해 반환할 수 없습니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>기본 장치에 대해 프로필을 읽지 못했기 때문에 마이그레이션을 수행할 수 없습니다. </p> </td> 
   <td colname="col3"> <p>이 오류가 발생하는 경우 Adobe의 데이터 저장소(PCS)에 확장성 문제가 발생할 수<span class="wintitle"> 있습니다</span>. 문제가 지속되면 Adobe 담당자에게 문의하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>ID에 대해 프로필을 <code><i>읽지</i></code> 못했기 때문에 ID에서 ID로 <code><i>마이그레이션을 수행할 수</i></code>없습니다 <code><i>.</i></code> </p> </td>
   <td colname="col3"> <p>이 오류가 발생하는 경우 Adobe의 데이터 저장소(PCS)에 확장성 문제가 발생할 수<span class="wintitle"> 있습니다</span>. 문제가 지속되면 Adobe 담당자에게 문의하십시오. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 통합 경고 코드 {#integration-warning-codes}

<table id="table_31F1593C46804DDBA2E9BEDE83F2417F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 코드 ID </th> 
   <th colname="col2" class="entry"> 메시지 </th> 
   <th colname="col3" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>300 </p> </td> 
   <td colname="col2"> <p>잘못된 고객 ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>고객 ID가 잘못되었습니다(데이터 소스에 대한 값 누락, 통합 코드 누락, 데이터 소스에 대한 잘못된 형식, 차단된 고객 ID, 빈 고객 ID, 파트너에 속하지 않는 데이터 소스에 대한 권한 없는 액세스 시도). </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>301 </p> </td> 
   <td colname="col2"> <p>최대 고객 ID 수를 초과했습니다. 최대 허용 <code><i>최대입니다</i></code>. 찾은 <code><i>최대</i></code>수입니다.</p> </td> 
   <td colname="col3"> <p>장치 간 데이터 소스와 연결된 고객 ID 수가 요청당 허용된 장치 간 ID 수를 초과합니다. 이러한 ID에는 장치 간, 모바일 또는 쿠키 ID가 포함됩니다. 제한은 현재 10으로 설정되어 있습니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p>허가되지 않은 고객 ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>고객 ID 데이터 소스가 현재 조직 ID에 의해 소유되지 않을 때 반환됩니다. 조직 ID를 모르거나 보유하고 있는 경우 조직 및 계정 연결에 있는 "조직 ID 찾기" 섹션을 <a href="https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html" format="https" scope="external"></a> 참조하여 조직 및 계정 연결을 찾는 방법에 대해 알아보십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>차단된 고객 ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>고객 ID 파섹 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>차단된 데이터 소스 ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>데이터 소스 ID가 악의적인 것으로 식별되어 블랙리스트에 추가되면 반환됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p>차단된 선언된 장치 ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>장치 ID가 악의적인 것으로 식별되었으며 블랙리스트에 추가되었습니다. 이 문제는 이 장치 ID가 들어 <span class="wintitle"> 있는</span> DCS 요청이 짧은 시간 내에 극히 많은 경우 발생할 수 있습니다. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p>ID에 대한 차단된 프로필 <code><i>작업</i></code> </p> </td> 
   <td colname="col3"> <p>ID가 악성 ID로 식별되어 차단되었으므로 읽기/쓰기 작업이 차단되었습니다. 오류 코드 306을 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p>고객 <code><i>ID</i></code> ID가 요청당 선언된 고객 ID의 제한을 초과했기 때문에 삭제되었습니다. </p> </td> 
   <td colname="col3"> <p>오류 301과 관련되어 있습니다. 이 오류는 제한이 초과되어 버린 고객 ID를 지정합니다. </p> <p>예를 들어 DCS 호출에 선언된 고객 ID가 12개인 경우 <span class="wintitle"> 이</span> 중 2개가 무시됩니다. 폐기된 고객 ID를 릴레이하려면 이 오류가 응답에 두 번 나타납니다(삭제된 고객 ID에 대해 한 번). </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>고객 ID가 지정된 네임스페이스의 제한을 초과하여 삭제되었습니다. 네임스페이스 ID는 <code><i>ID</i></code>, 고객 ID는 <code><i>ID입니다</i></code>. </p> </td> 
   <td colname="col3"> <p>DCS 호출에 동일한 네임스페이스(DPID)에 대해 선언된 고객 ID가 3개 이상인 경우 이 오류 코드가<code> 반환됩니다</code><span class="wintitle"></span> . </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one </code> </p> <p>이 샘플 <span class="wintitle"> DCS</span> 요청에는 동일한 네임스페이스에 대해 선언된 4개의 ID가 있습니다(통합 코드 1과 함께). ID 중 하나가 삭제되고 310 오류가 반환됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311 </p> </td> 
   <td colname="col2"> <p>요청에 잘못된 매개 변수가 있습니다. </p> </td> 
   <td colname="col3"> <p>DCS <span class="wintitle"></span> 는 하나 이상의 URL 매개 변수가 제대로 인코딩되지 않은 경우 이 오류 코드를 반환합니다. 이 경우 DCS는 <span class="wintitle"> 전체</span> 요청을 무시합니다. </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp;d_creative=%ecid!&amp;d_adgroup=%eaid!&amp;d_placement=%epid!&amp;d_campaign=%ebuy!&amp;d_adsrc=48123</code> </p> <p>위의 샘플 요청에서 <code> %</code> 시퀀스가 잘못 인코딩되었습니다. 따라서 DCS <span class="wintitle"> 는</span> 무시하게 됩니다. </p> <p>올바르게 인코딩된 샘플은 다음과 같아야 합니다. </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp;d_creative=%25ecid!&amp;d_adgroup=%25aid!&amp;d_placement=%25epid!&amp;d_campaign=%25ebuy!&amp;d_adsrc=48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>요청에 잘못된 전역 장치 ID가 포함되어 있습니다. </p> </td> 
   <td colname="col3"> <p>요청에 <span class="wintitle">잘못된 전역 장치</span> ID가 포함되어 있으면 DCS가 이 오류 코드를 반환합니다. DCS는 잘못된 ID를 무시하고 잘못된 ID의 특정 오류와 함께 312 오류를 발생시킵니다. 올바른 장치 <a href="../../../features/global-data-sources.md" format="dita" scope="local">광고 ID</a> 형식 및 해당 글로벌 데이터 소스에 대한 자세한 내용은 Audience Manager의 <a href="../../../reference/ids-in-aam.md" format="dita" scope="local"></a> 전역 데이터 소스 및 ID 인덱스를 참조하십시오.</p>
   <p>잘못된 호출의 예: <code>"http://partner.demdex.net/event?d_rtbd=json&amp;d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"</code></p>
   <p>설명:IDFA <span class="keyword">(DPID 20915)</span> 는 대문자 ID여야 합니다. 요청에 제공된 ID는 소문자입니다.</p>
   </td>
  </tr>

</tbody>
</table>

## 샘플 오류 코드 메시지 {#sample-error-codes}

이 [!UICONTROL DCS] 값은 [!DNL JSON] 개체 또는 HTTP 응답 문자열의 X-헤더에서 오류 코드와 메시지를 반환합니다.

### 샘플 DCS 오류 코드 및 메시지

```
{ 
   "errors":[ 
      { 
         "code":101,
         "msg":"Invalid Experience Cloud id passed in"
      },
      { 
         "code":102,
         "msg":"Invalid aam id passed in request"
      }
   ]
}
```

### X-오류

X-헤더에 의해 캡처된 오류 코드는 다음과 같은 URL 문자열에 나타납니다 `X-Error: 101,102`.

[레이스 조건 및 오류 처리](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)