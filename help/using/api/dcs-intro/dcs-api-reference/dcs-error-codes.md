---
description: 코드 ID별로 숫자 순서로 나열된 데이터 수집 서버(DCS)에서 생성된 오류 코드 및 메시지입니다.
title: DCS 오류 코드, 메시지 및 예제
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
feature: DCS
exl-id: 485e5ce2-143e-4d18-b157-c243c5a510ad
source-git-commit: 5044a38c751abace922008f00b9ff463ea9c7e57
workflow-type: tm+mt
source-wordcount: '1520'
ht-degree: 4%

---

# DCS 오류 코드, 메시지 및 예제 {#dcs-error-codes-messages-and-examples}

에서 생성한 오류 코드 및 메시지 [!UICONTROL Data Collection Servers] ([!DNL DCS])가 코드 ID별 숫자 순서로 나열되어 있습니다.

아래 표에서, *기울임체* 변수 자리 표시자를 나타냅니다.

## 시스템 오류 코드 {#system-error-codes}

| 오류 코드 | 오류 메시지 | 설명 |
|---|---|---|
| 0 | 지정되지 않은 오류 | 다른 오류 처리기에서 다루지 않는 이벤트를 처리하는 다목적 캐치 오류입니다. 이 오류를 해결하는 것은 어렵습니다. 알 수 없는 다양한 작업 또는 이벤트로 인해 발생할 수 있습니다. 이 오류가 표시되면 [!DNL DCS] 다시 요청하십시오. 다음으로 연락 [!DNL Adobe] 대표: 문제가 지속되는 경우. |
| 1 | 호스트 이름에 대한 구성을 찾을 수 없음: `hostname` | 요청에서 전송된 호스트 이름이 파트너 프로비저닝 팀에 의해 설정되지 않았습니다. 다음으로 연락 [!DNL Adobe] 이 오류 메시지가 표시되면 담당자입니다. |
| 2 | 잘못됨 `d_orgid` 값(이 조직 id에 대한 구성을 찾을 수 없음): `ID` | 조직 ID가 잘못되었습니다. ID를 확인하고 요청을 다시 시도하십시오. 조직 ID를 모르거나 가지고 있는 경우 &quot;관리 페이지&quot; 섹션을 참조하십시오 [조직 및 계정 연결](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html) 를 찾는 방법에 대한 정보를 제공합니다. |
| 10 | 특성을 평가할 수 없음 | 요청에 대한 트레이트가 부분적으로 평가되었거나 전혀 평가되지 않았습니다. 다음으로 연락 [!DNL Adobe] 대표: 문제가 지속되는 경우. |

## 통합 오류 코드 {#integration-error-codes}

| 오류 코드 | 오류 메시지 | 설명 |
|---|---|---|
| 100 | 요청에 대한 호스트 이름을 검색할 수 없습니다. | An [!DNL API] 호출이 호스트를 전송하지 않았습니다. [!DNL HTTP] 요청에 있는 헤더입니다. 호출에 호스트 헤더를 추가하고 다시 시도하십시오. 대부분의 브라우저 및 [!DNL API] 클라이언트는 자동으로 이를 수행합니다. |
| 101 | 잘못됨 [!DNL Experience Cloud] id 전달됨 `ID` | 다음 [!DNL DCS] 호출에 잘못된 가 포함되어 있습니다. [!DNL Experience Cloud] ID 다음 확인: `d_mid=` 헤더 문자열의 키-값 쌍입니다. 정확하게 전달했는지 확인하십시오. [!DNL Experience Cloud] ID를 확인하고 요청을 다시 시도하십시오. |
| 102 | 잘못됨 [!DNL AAM ID] 전달된 요청 `ID` | 다음 [!DNL DCS] 호출에 잘못된 가 포함되어 있습니다. [!DNL Audience Manager] ID 다음 확인: `d_uuid=` 헤더 문자열의 키-값 쌍입니다. 정확하게 전달했는지 확인하십시오. [!DNL Audience Manager] ID를 확인하고 요청을 다시 시도하십시오. |
| 104 | 모든 고객 ID가 잘못되었습니다. | 호출에 있는 모든 고객 ID가 잘못되었습니다. ID를 확인하고 다시 시도하십시오. |
| 109 | Referer `HTTP referer` 은(는) 파트너에게 허용되지 않습니다. `Partner ID` | 다음 `HTTP referer` 호출의 헤더가 호출의 파트너 ID에 허용되지 않습니다. 다음을 확인하십시오. `HTTP referer` 헤더가 올바릅니다. |
| 111 | 잘못됨 `IMS` 토큰 받음 | 다음에 대해 반환됨: [!DNL Audience Manager] - [!DNL Adobe Target] 통합. 에 대한 호출이 수행되면 오류가 발생합니다. [!DNL DCS], 잘못된 항목 포함 [!DNL IMS] 토큰. 토큰이 잘못되었거나 만료되었거나 사용자에게 필요한 리소스에 액세스할 수 있는 권한이 없을 수 있습니다. |

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
   <td colname="col2"> <p>ID에 대한 옵트아웃 태그가 발견되었습니다. <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>고객이 관심 기반 광고를 받지 않기로 결정했다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>172 </p> </td> 
   <td colname="col2"> <p>차단된 쿠키 </p> </td> 
   <td colname="col3"> <p>사용자의 브라우저가 서드파티 쿠키를 차단하면 반환됩니다.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>173 </p> </td> 
   <td colname="col2"> <p>다음을 통해 트러스트 관계 발생 <a href="https://www.networkadvertising.org/" format="http" scope="external"> 나이</a> </p> </td> 
   <td colname="col3"> <p>사용자가 NAI를 통해 옵트아웃 프로세스를 시작했습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>198 </p> </td> 
   <td colname="col2"> <p>이 국가의 요청은 파트너에 의해 차단됨 </p> </td> 
   <td colname="col3"> <p>IP 주소를 기반으로 하면 <span class="wintitle"> DCS</span> 은 파트너가 의도적으로 트래픽을 제한한 국가의 요청을 차단합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>이 국가의 요청은 허용되지 않습니다. </p> </td> 
   <td colname="col3"> <p>IP 주소를 기반으로 하면 <span class="wintitle"> DCS</span> 다음 국가의 요청을 차단합니다. </p> <p> 
     <ul id="ul_4017A7D074064FE7A8B5618AFCFA4E28"> 
      <li id="li_EE65DEC3C64F4522B214C503DC754DC1">쿠바 (CU) </li> 
      <li id="li_EDE8B304D35A41458DCFF11E9328802A">이란 (IR) </li> 
      <li id="li_36664315A06540E0BE024EE60638D5DC">북한 (KP) </li> 
      <li id="li_B508A5FF173E491AAE41334C074D9DED">수단 (SD) </li> 
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
   <td colname="col2"> <p> ID에 대한 프로필 캐시에서 트레이트를 읽을 수 없음: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>내부 저장소에서 사용자 프로필을 읽을 수 없을 때 반환됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> 고객 ID에 대한 프로필 캐시에서 장치 ID를 읽을 수 없음: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>다음과 같은 경우에 반환됨 <a href="../../../reference/ids-in-aam.md"> 장치 ID</a> 프로필 링크 병합 규칙에 대해 검색할 수 없습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>장치 ID에 대한 관련 고객을 읽을 수 없음: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>다음과 같은 경우에 반환됨 <a href="../../../reference/ids-in-aam.md"> 고객 ID (UUID)</a> 내부 저장소에서 마지막 인증 병합 규칙에 대해 장치 ID에 연결된 을(를) 검색할 수 없습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> ID에 대한 장치 클러스터를 읽을 수 없음: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>이 장치 ID에 대해 동일한 장치 그래프 클러스터의 연결된 장치 ID를 반환할 수 없습니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>기본 장치에 대한 프로필 읽기가 실패하여 마이그레이션을 수행할 수 없습니다. </p> </td> 
   <td colname="col3"> <p>이 오류가 발생하면 데이터 저장소에 확장성 문제가 발생할 수 있습니다. (<span class="wintitle"> PCS</span>). 문제가 지속되면 Adobe 담당자에게 문의하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>에서 마이그레이션을 수행할 수 없음 <code><i>ID</i></code> 끝 <code><i>ID</i></code>, 다음에 대한 프로필 읽기가 실패했기 때문 <code><i>ID</i></code> </p> </td>
   <td colname="col3"> <p>이 오류가 발생하면 데이터 저장소에 확장성 문제가 발생할 수 있습니다. (<span class="wintitle"> PCS</span>). 문제가 지속되면 Adobe 담당자에게 문의하십시오. </p> </td> 
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
   <td colname="col3"> <p>고객 ID가 잘못되었습니다(데이터 소스에 대한 값 누락, 통합 코드 누락, 데이터 소스에 대한 잘못된 형식, 차단된 고객 ID, 빈 고객 ID, 파트너에 속하지 않은 데이터 소스에 대한 무단 액세스 시도). </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>301 </p> </td> 
   <td colname="col2"> <p>최대 고객 ID 수를 초과했습니다. 허용되는 최대값은 입니다. <code><i>maximum allowed</i></code>. 찾음: <code><i>maximum found</i></code>.</p> </td> 
   <td colname="col3"> <p>교차 장치 데이터 소스와 연결된 고객 ID 수가 요청당 허용된 교차 장치 ID 수를 초과했습니다. 이러한 ID에는 교차 장치, 모바일 또는 쿠키 ID가 포함됩니다. 제한은 현재 10으로 설정되어 있습니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p>승인되지 않은 고객 ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>고객 ID 데이터 소스를 현재 조직 ID가 소유하지 않는 경우 반환됩니다. 조직 ID를 모르거나 가지고 있는 경우에서 "조직 ID 찾기" 섹션을 참조하십시오 <a href="https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html" format="https" scope="external"> 조직 및 계정 연결</a> 를 찾는 방법에 대한 정보를 제공합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>차단된 고객 ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>고객 ID가 악의적인 것으로 식별되어 차단 목록에 추가하다에 추가되면 반환됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>차단된 데이터 소스 ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>데이터 소스 ID가 악의적인 것으로 식별되고 차단 목록에 추가하다에 추가되면 반환됩니다 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p>선언된 장치 ID가 차단됨 <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>장치 ID가 악의적인 것으로 확인되었으며 차단 목록에 추가하다에 추가되었습니다. 이 문제는 극단적인 양을 받을 때 발생할 수 있습니다 <span class="wintitle"> DCS</span> 짧은 시간 내에 이 장치 ID를 포함하는 요청. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p>에 대한 프로필 작업 차단됨 <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>ID가 악의적인 것으로 식별되고 오류 코드(306)를 참조하십시오 차단 목록에 추가되었기 때문에 읽기/쓰기 동작이 차단되었습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p>고객 ID <code><i>ID</i></code> 요청당 선언된 고객 id의 한도를 초과하여 이(가) 삭제되었습니다 </p> </td> 
   <td colname="col3"> <p>오류 301과 관련되어 있습니다. 이 오류는 한도를 초과하여 삭제된 고객 ID를 지정합니다. </p> <p>예를 들어 에 12개의 고객 ID가 선언되어 있는 경우 <span class="wintitle"> DCS</span> 호출하면 두 개가 삭제됩니다. 삭제된 항목을 릴레이하기 위해 이 오류는 응답에 두 번 표시됩니다( 삭제된 각 고객 ID에 대해 한 번). </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>지정된 네임스페이스에 대한 제한을 초과하여 고객 ID가 삭제되었습니다. 네임스페이스 ID: <code><i>ID</i></code>, 고객 id는 <code><i>ID</i></code>. </p> </td> 
   <td colname="col3"> <p>동일한 네임스페이스에 대해 선언된 고객 ID가 3개 이상인 경우 이 오류 코드가 반환됩니다(<code> DPID</code>)의 <span class="wintitle"> DCS</span> 호출합니다. </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one </code> </p> <p>이 샘플에서 <span class="wintitle"> DCS</span> 요청에서, 동일한 네임스페이스에 대해 4개의 id가 선언되어 있습니다(통합 코드 1개 포함). ID 중 하나가 삭제되고 오류 310이 반환됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311 </p> </td> 
   <td colname="col2"> <p>요청에 잘못된 매개 변수가 포함되어 있습니다. </p> </td> 
   <td colname="col3"> <p>다음 <span class="wintitle"> DCS</span> 하나 이상의 URL 매개 변수가 올바르게 인코딩되지 않은 경우 이 오류 코드를 반환합니다. 이 경우 <span class="wintitle"> DCS</span> 전체 요청을 무시합니다. </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp;d_creative=%ecid!&amp;d_adgroup=%eaid!&amp;d_placement=%epid!&amp;d_campaign=%ebuy!&amp;d_adsrc=48123</code> </p> <p>위의 샘플 요청에서 <code> %</code> 시퀀스가 잘못 인코딩되었습니다. 따라서 <span class="wintitle"> DCS</span> 무시하겠죠 </p> <p>올바르게 인코딩된 샘플은 다음과 같아야 합니다. </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp;d_creative=%25ecid!&amp;d_adgroup=%25eaid!&amp;d_placement=%25epid!&amp;d_campaign=%25ebuy!&amp;d_adsrc=48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>요청에 잘못된 글로벌 장치 ID가 포함되어 있습니다. </p> </td> 
   <td colname="col3"> <p>다음 <span class="wintitle">DCS</span> 요청에 잘못된 글로벌 장치 ID가 포함되어 있으면 이 오류 코드를 반환합니다. DCS에서는 잘못된 ID를 무시하고 잘못된 ID의 특정 오류와 함께 312 오류가 발생합니다. 을(를) 참조하십시오 <a href="../../../features/global-data-sources.md" format="dita" scope="local">글로벌 데이터 소스</a> 및 <a href="../../../reference/ids-in-aam.md" format="dita" scope="local">Audience Manager 내 ID 색인</a> 올바른 장치 광고 ID 형식 및 해당 글로벌 데이터 소스에 대한 자세한 정보입니다.</p>
   <p>잘못된 호출의 예: <code>"http://partner.demdex.net/event?d_rtbd=json&amp;d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"</code></p>
   <p>설명: <span class="keyword">IDFA(DPID 20915)</span> 은(는) 대문자 ID여야 합니다. 요청에 입력한 ID는 소문자입니다.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>313 </p> </td> 
   <td colname="col2"> <p>CMP ID가 GCL에 없음</p> </td> 
   <td colname="col3"> <p>날짜 <code>gdpr=1</code> 그리고 IAB TC 문자열은 평가 시점에 Audience Manager의 캐시된 글로벌 CMP 목록 버전에 없는 CMP ID에 의해 생성되며, IAB TCF용 Audience Manager 플러그인은 IAB TC 문자열을 삭제하고 평소대로 요청을 처리합니다. IAB TCF v2.2 ${GDPR} 매크로가 0으로 설정되고 ${GDPR_CONSENT_XXX} 매크로가 비어 있습니다.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>314 </p> </td> 
   <td colname="col2"> <p>CMP ID가 GCL에서 삭제된 것으로 표시됨</p> </td> 
   <td colname="col3"> <p>날짜 <code>gdpr=1</code> 그리고 IAB TC 문자열은 글로벌 CMP 목록의 캐시된 버전에서 삭제된 것으로 표시된 CMP에 의해 생성되며, 평가 시간이 글로벌 CMP 목록에서 삭제 시간을 경과한 경우 IAB TCF용 Audience Manager 플러그인은 TC 문자열을 삭제하고 평소대로 요청을 처리합니다. IAB TCF v2.2 ${GDPR} 매크로가 0으로 설정되고 ${GDPR_CONSENT_XXX} 매크로가 비어 있습니다.</p></td>
  </tr>
   <tr> 
   <td colname="col1"> <p>315 </p> </td> 
   <td colname="col2"> <p>동의 문자열은 동의가 없음을 나타냅니다.</p> </td> 
   <td colname="col3"> <p>동의를 제공하지 않으면 IAB TCF용 Audience Manager 플러그인은 사용자를 추가 데이터 수집에서 옵트아웃하거나, 감지된 파트너 컨텍스트가 없는 경우 호출을 완전히 중단합니다.</p>
   </td>
  </tr>

</tbody>
</table>

## 샘플 오류 코드 메시지 {#sample-error-codes}

다음 [!DNL DCS] 에 오류 코드 및 메시지를 반환합니다. [!DNL JSON] 또는 HTTP 응답 문자열의 X- 헤더에 있습니다.

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

X- 헤더에서 캡처한 오류 코드는 다음과 같이 URL 문자열에 나타납니다. `X-Error: 101,102`.

[경합 조건 및 오류 처리](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)
