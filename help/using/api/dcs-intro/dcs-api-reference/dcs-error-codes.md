---
description: 코드 ID별로 숫자 순서로 나열된 DCS(데이터 수집 서버)에서 생성된 오류 코드 및 메시지입니다.
seo-description: 코드 ID별로 숫자 순서로 나열된 DCS(데이터 수집 서버)에서 생성된 오류 코드 및 메시지입니다.
seo-title: DCS 오류 코드, 메시지 및 예제
solution: Audience Manager
title: DCS 오류 코드, 메시지 및 예제
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
feature: DCS
exl-id: 485e5ce2-143e-4d18-b157-c243c5a510ad
source-git-commit: 38c4c46709491656071f4a958e9f0de26d42dd74
workflow-type: tm+mt
source-wordcount: '1547'
ht-degree: 4%

---

# DCS 오류 코드, 메시지 및 예제 {#dcs-error-codes-messages-and-examples}

코드 ID별로 숫자 순서로 나열된 [!UICONTROL Data Collection Servers]([!DNL DCS])에 의해 생성된 오류 코드 및 메시지입니다.

아래 표에서 *기울임꼴*&#x200B;은 변수 자리 표시자를 나타냅니다.

## 시스템 오류 코드 {#system-error-codes}

| 오류 코드 | 오류 메시지 | 설명 |
|---|---|---|
| 0 | 지정되지 않은 오류 | 다른 오류 핸들러에서 다루지 않는 이벤트를 처리하는 catch-all 오류입니다. 이 오류를 해결하는 것은 어렵습니다. 알 수 없는 다양한 작업 또는 이벤트로 인해 발생할 수 있습니다. 이 오류가 표시되면 [!DNL DCS] 요청을 다시 시도하십시오. 문제가 계속되면 [!DNL Adobe] 담당자에게 문의하십시오. |
| 1 | 호스트 이름에 대한 구성을 찾을 수 없습니다.`hostname` | 요청에 전송된 호스트 이름이 파트너 프로비저닝 팀에서 설정되지 않았습니다. 이 오류 메시지가 표시되면 [!DNL Adobe] 담당자에게 문의하십시오. |
| 2 | 잘못된 `d_orgid` 값(이 조직 ID에 대한 구성을 찾을 수 없음):`ID` | 조직 ID가 잘못되었습니다. ID를 확인하고 요청을 다시 시도하십시오. 조직 ID를 모르거나 보유하고 있는 경우, 찾는 방법에 대한 자세한 내용은 &quot;관리 페이지&quot; 섹션 [조직 및 계정 연결](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html)을 참조하십시오. |
| 10 | 특성을 평가할 수 없습니다. | 요청의 트레이트가 부분적으로 평가되거나 전혀 평가되지 않았습니다. 문제가 계속되면 [!DNL Adobe] 담당자에게 문의하십시오. |

## 통합 오류 코드 {#integration-error-codes}

| 오류 코드 | 오류 메시지 | 설명 |
|---|---|---|
| 100 | 요청에 대한 호스트 이름을 검색할 수 없습니다. | [!DNL API] 호출이 요청에 호스트 [!DNL HTTP] 헤더를 보내지 않았습니다. 호출에 호스트 헤더를 추가하고 다시 시도하십시오. 대부분의 브라우저 및 [!DNL API] 클라이언트는 자동으로 이 작업을 수행합니다. |
| 101 | `ID`에 잘못된 [!DNL Experience Cloud] ID가 전달되었습니다. | [!DNL DCS] 호출에 잘못된 [!DNL Experience Cloud] ID가 포함되어 있습니다. 헤더 문자열에서 `d_mid=` 키-값 쌍을 선택합니다. 올바른 [!DNL Experience Cloud] ID를 전달하고 있는지 확인하고 요청을 다시 시도하십시오. |
| 102 | 요청 `ID`에서 잘못된 [!DNL AAM ID]이 전달되었습니다. | [!DNL DCS] 호출에 잘못된 [!DNL Audience Manager] ID가 포함되어 있습니다. 헤더 문자열에서 `d_uuid=` 키-값 쌍을 선택합니다. 올바른 [!DNL Audience Manager] ID를 전달하고 있는지 확인하고 요청을 다시 시도하십시오. |
| 104 | 모든 고객 ID가 잘못되었습니다. | 호출의 모든 고객 ID가 잘못되었습니다. ID를 확인하고 다시 시도하십시오. |
| 109 | Referer `HTTP referer`은(는) 파트너 `Partner ID`에 사용할 수 없습니다. | 호출의 `HTTP referer` 헤더는 호출의 파트너 ID에 대해 허용되지 않습니다. `HTTP referer` 헤더가 올바른지 확인합니다. |
| 111 | 잘못된 `IMS` 토큰을 받았습니다. | [!DNL Audience Manager] - [!DNL Adobe Target] 통합에 대해 반환됩니다. 잘못된 [!DNL IMS] 토큰이 포함된 [!DNL DCS]을 호출하면 오류가 발생합니다. 토큰의 형식이 잘못되었거나, 만료되었거나, 사용자에게 필요한 리소스에 액세스할 수 있는 권한이 없을 수 있습니다. |

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
   <td colname="col2"> <p>ID <code><i>ID</i></code>에 대한 옵트아웃 태그가 발견되었습니다. </p> </td> 
   <td colname="col3"> <p>고객이 관심 기반 광고 수신을 선택하지 않았습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>172 </p> </td> 
   <td colname="col2"> <p>차단된 쿠키 </p> </td> 
   <td colname="col3"> <p>사용자의 브라우저가 서드파티 쿠키를 차단하면 반환됩니다.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>173 </p> </td> 
   <td colname="col2"> <p><a href="https://www.networkadvertising.org/" format="http" scope="external"> NAI</a>를 통해 트러스트 관계가 발견되었습니다. </p> </td> 
   <td colname="col3"> <p>사용자가 NAI를 통해 옵트아웃 프로세스를 시작했습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>198 </p> </td> 
   <td colname="col2"> <p>이 국가의 요청은 파트너에 의해 차단됩니다 </p> </td> 
   <td colname="col3"> <p>IP 주소를 기반으로 하여 <span class="wintitle"> DCS</span> 는 파트너가 의도적으로 트래픽을 제한한 국가의 요청을 차단합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>이 국가의 요청은 허용되지 않습니다 </p> </td> 
   <td colname="col3"> <p>IP 주소를 기준으로 <span class="wintitle"> DCS</span>은(는) 다음 국가의 요청을 차단합니다. </p> <p> 
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
   <td colname="col2"> <p> 프로필 캐시에서 ID에 대한 트레이트를 읽을 수 없습니다.<code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>내부 저장소에서 사용자 프로필을 읽을 수 없을 때 반환됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> 고객 ID에 대한 프로필 캐시에서 장치 ID를 읽을 수 없습니다.<code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>프로필 링크 병합 규칙에 대해 <a href="../../../reference/ids-in-aam.md"> 장치 ID</a>를 검색할 수 없을 때 반환됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>장치 ID에 대해 관련 고객을 읽을 수 없습니다.<code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>내부 저장소에서 장치 ID에 연결된 <a href="../../../reference/ids-in-aam.md"> 고객 ID(UUID)</a>를 검색할 수 없을 때 반환됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> ID에 대한 장치 클러스터를 읽을 수 없습니다.<code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>동일한 장치 그래프 클러스터의 연결된 장치 ID는 이 장치 ID에 대해 반환할 수 없습니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>기본 장치에 대해 프로필 읽기가 실패하여 마이그레이션을 수행할 수 없습니다. </p> </td> 
   <td colname="col3"> <p>이 오류가 표시되면 데이터 저장소(<span class="wintitle"> PCS</span>)에 확장성 문제가 발생할 수 있습니다. 문제가 계속되면 Adobe 담당자에게 문의하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p><code><i>ID</i></code>에 대해 프로필 읽기가 실패했으므로 <code><i>ID</i></code>에서 <code><i>ID</i></code>로의 마이그레이션을 수행할 수 없습니다 </p> </td>
   <td colname="col3"> <p>이 오류가 표시되면 데이터 저장소(<span class="wintitle"> PCS</span>)에 확장성 문제가 발생할 수 있습니다. 문제가 계속되면 Adobe 담당자에게 문의하십시오. </p> </td> 
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
   <td colname="col3"> <p>고객 ID가 잘못되었습니다(데이터 소스에 대한 값이 없거나 통합 코드가 없거나 데이터 소스에 대한 형식이 잘못되었습니다. 차단된 고객 ID, 빈 고객 ID, 파트너에 속하지 않는 데이터 소스에 대한 무단 액세스 시도). </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>301년 </p> </td> 
   <td colname="col2"> <p>최대 고객 ID 수를 초과했습니다. 허용되는 최대 값은 <code><i>maximum allowed</i></code>입니다. <code><i>maximum found</i></code>이(가) 있습니다.</p> </td> 
   <td colname="col3"> <p>교차 장치 데이터 소스와 연결된 고객 ID 수가 요청당 허용되는 교차 장치 ID 수를 초과합니다. 이러한 ID에는 교차 장치, 모바일 또는 쿠키 ID가 포함됩니다. 현재 이 제한은 10으로 설정되어 있습니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302년 </p> </td> 
   <td colname="col2"> <p>허가되지 않은 고객 ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>고객 ID 데이터 소스가 현재 조직 ID에 의해 소유되지 않을 때 반환됩니다. 조직 ID를 모르거나 보유하고 있는 경우, 찾는 방법에 대한 자세한 내용은 <a href="https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html" format="https" scope="external"> 조직 및 계정 연결</a>의 "조직 ID 찾기" 섹션을 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303년 </p> </td> 
   <td colname="col2"> <p>차단된 고객 ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>고객 ID가 악의적인 것으로 식별되고에 추가되면 차단 목록 반환됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304년 </p> </td> 
   <td colname="col2"> <p>차단된 데이터 소스 ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>데이터 소스 ID가 악성 ID로 식별되고에 추가되면 차단 목록 반환됩니다 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306년 </p> </td> 
   <td colname="col2"> <p>차단된 선언된 장치 ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>장치 ID가 악의적인 것으로 식별되었으며에 추가되었습니다. 이 차단 목록 문제는 짧은 시간 내에 이 장치 ID가 들어 있는 매우 많은 <span class="wintitle"> DCS</span> 요청을 받을 때 발생할 수 있습니다. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307년 </p> </td> 
   <td colname="col2"> <p><code><i>ID</i></code>에 대해 차단된 프로필 작업 </p> </td> 
   <td colname="col3"> <p>ID가 악성 ID로 식별되고 오류 코드 306에 추가되어 읽기/쓰기 작업이 차단되었습니다차단 목록. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309년 </p> </td> 
   <td colname="col2"> <p>고객 ID <code><i>ID</i></code>이(가) 요청당 선언된 고객 ID 제한을 초과했기 때문에 삭제되었습니다 </p> </td> 
   <td colname="col3"> <p>오류 301과 관련되어 있습니다. 이 오류는 제한이 초과되어 폐기된 고객 ID를 지정합니다. </p> <p>예를 들어 <span class="wintitle"> DCS</span> 호출에서 선언된 고객 ID가 12개인 경우 이 중 2개가 삭제됩니다. 폐기된 항목을 중계하려면 응답에 이 오류가 두 번 표시됩니다( 폐기된 각 고객 ID에 대해 한 번 ). </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310년 </p> </td> 
   <td colname="col2"> <p>고객 ID가 지정된 네임스페이스의 제한을 초과했기 때문에 삭제되었습니다. 네임스페이스 id는 <code><i>ID</i></code>이고 고객 ID는 <code><i>ID</i></code>입니다. </p> </td> 
   <td colname="col3"> <p>이 오류 코드는 <span class="wintitle"> DCS</span> 호출에 동일한 네임스페이스(<code> DPID</code>)에 대해 선언된 고객 ID가 3개 이상인 경우 반환됩니다. </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one </code> </p> <p>이 샘플 <span class="wintitle"> DCS</span> 요청에는 동일한 네임스페이스에 대해 선언된 4개의 ID가 있습니다(통합 코드 1 사용). ID 중 하나가 삭제되고 오류 310이 반환됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311년 </p> </td> 
   <td colname="col2"> <p>요청에 잘못된 매개 변수가 포함되어 있습니다. </p> </td> 
   <td colname="col3"> <p>하나 이상의 URL 매개 변수가 제대로 인코딩되지 않으면 <span class="wintitle"> DCS</span>에서 이 오류 코드를 반환합니다. 이 경우 <span class="wintitle"> DCS</span>은 전체 요청을 무시합니다. </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp;d_creative=%ecid!&amp;d_adgroup=%eaid!&amp;d_placement=%epid!&amp;d_campaign=%ebuy!&amp;d_adsrc=48123</code> </p> <p>위의 샘플 요청에서 <code> %</code> 시퀀스가 잘못 인코딩되었습니다. 따라서 <span class="wintitle"> DCS</span>은 이를 무시합니다. </p> <p>올바르게 인코딩된 샘플은 다음과 같습니다. </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp;d_creative=%25ecid!&amp;d_adgroup=%25eaid!&amp;d_placement=%25epid!&amp;d_campaign=%25ebuy!&amp;d_adsrc=48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312년 </p> </td> 
   <td colname="col2"> <p>요청에 잘못된 글로벌 장치 ID가 포함되어 있습니다. </p> </td> 
   <td colname="col3"> <p>요청에 잘못된 글로벌 장치 ID가 포함되어 있으면 <span class="wintitle">DCS</span>에서 이 오류 코드를 반환합니다. DCS는 잘못된 ID를 무시하고 잘못된 ID의 특정 오류와 함께 312 오류를 표시합니다. 올바른 장치 광고 ID 형식 및 해당 글로벌 데이터 소스에 대한 자세한 내용은 <a href="../../../features/global-data-sources.md" format="dita" scope="local">글로벌 데이터 소스</a> 및 <a href="../../../reference/ids-in-aam.md" format="dita" scope="local">Audience Manager의 ID 색인</a>을 참조하십시오.</p>
   <p>잘못된 호출의 예: <code>"http://partner.demdex.net/event?d_rtbd=json&amp;d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"</code></p>
   <p>설명:<span class="keyword">IDFA(DPID 20915)</span>는 대문자 ID여야 합니다. 요청에 제공된 ID는 소문자로 표시됩니다.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>313 </p> </td> 
   <td colname="col2"> <p>CMP ID가 GCL에 없습니다.</p> </td> 
   <td colname="col3"> <p>평가 시 Audience Manager의 캐시된 글로벌 CMP 목록 버전에 없는 CMP ID에 의해 <code>gdpr=1</code> 및 IAB TC 문자열이 생성되면 IAB TCF용 Audience Manager 플러그인은 IAB TC 문자열을 삭제하고 평소대로 요청을 처리합니다. IAB TCF v2.0 ${GDPR} 매크로가 0으로 설정되고 ${GDPR_CONSENT_XXX} 매크로가 비어 있습니다.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>314년 </p> </td> 
   <td colname="col2"> <p>CMP ID가 GCL에서 삭제된 것으로 표시됨</p> </td> 
   <td colname="col3"> <p>캐시된 글로벌 CMP 목록의 버전에서 삭제된 것으로 표시된 CMP에 의해 <code>gdpr=1</code> 및 IAB TC 문자열이 생성되면 IAB TCF용 Audience Manager 플러그인은 평가 시간이 글로벌 CMP 목록에서 삭제 시간이 지난 경우 TC 문자열을 삭제하고 평소대로 요청을 처리합니다. IAB TCF v2.0 ${GDPR} 매크로가 0으로 설정되고 ${GDPR_CONSENT_XXX} 매크로가 비어 있습니다.</p></td>
  </tr>
   <tr> 
   <td colname="col1"> <p>315 </p> </td> 
   <td colname="col2"> <p>동의 문자열은 동의 없음을 나타냅니다</p> </td> 
   <td colname="col3"> <p>동의 가 제공되지 않으면 IAB TCF용 Audience Manager 플러그인이 추가 데이터 수집에서 사용자를 옵트아웃하거나, 검색된 파트너 컨텍스트가 없는 경우 호출을 완전히 삭제합니다.</p>
   </td>
  </tr>

</tbody>
</table>

## 샘플 오류 코드 메시지 {#sample-error-codes}

[!DNL DCS]은 [!DNL JSON] 개체 또는 HTTP 응답 문자열의 X- 헤더에 오류 코드와 메시지를 반환합니다.

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

X- 헤더에서 캡처한 오류 코드는 다음과 같은 URL 문자열에 나타납니다. `X-Error: 101,102`

[경합 조건 및 오류 처리](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)
