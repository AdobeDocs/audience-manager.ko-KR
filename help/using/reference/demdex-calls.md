---
description: Audience Manager 및 Experience Cloud ID 서비스는 demdex.net 도메인을 호출하고 이 도메인에서 데이터를 수신합니다. 이는 Adobe가 비정상적인 타사 도메인과 협력하고 있는 것처럼 보일 수 있지만 그렇지 않습니다. 이 섹션에서는 demdex.net 호출의 요소에 대해 설명합니다.
seo-description: Audience Manager 및 Experience Cloud ID 서비스는 demdex.net 도메인을 호출하고 이 도메인에서 데이터를 수신합니다. 이는 Adobe가 비정상적인 타사 도메인과 협력하고 있는 것처럼 보일 수 있지만 그렇지 않습니다. 이 섹션에서는 demdex.net 호출의 요소에 대해 설명합니다.
seo-title: Demdex 도메인에 대한 호출 이해
solution: Audience Manager
title: Demdex 도메인에 대한 호출 이해
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Demdex 도메인에 대한 호출 이해{#understanding-calls-to-the-demdex-domain}

Audience Manager 및 Experience Cloud ID 서비스는 demdex.net 도메인을 호출하고 이 도메인에서 데이터를 수신합니다. 이는 Adobe가 비정상적인 타사 도메인과 협력하고 있는 것처럼 보일 수 있지만 그렇지 않습니다. 이 섹션에서는 demdex.net 호출의 요소에 대해 설명합니다.

<table id="table_B846CBEDDA4C4AD19416F7C27FC325C6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 호출 요소 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> demdex.net</code> </p> </td> 
   <td colname="col2"> <p>This is a legacy domain controlled by <span class="keyword"> Adobe</span>. Audience <span class="keyword"> Manager의</span>원래 획득 전 이름(Demdex<span class="keyword"> )을 반영합니다</span>. <span class="keyword"> Adobe는</span> 2011 <span class="keyword"> 년 Demdex를</span> 인수하여 Adobe를 Audience Manager로 <span class="keyword"> 다시 브랜딩했습니다</span>. 이 도메인은 Audience Manager, ID 서비스 <span class="keyword"> 및 설치된 사용자 기반에 깊이</span><span class="wintitle"> 입력되어 있으므로</span>변경하는 것은 어렵습니다. 작업 <a href="../overview/aam-overview.md#history-and-background"> 내역 및 배경을 참조하십시오</a>. </p> <p>기존 <code> demdex.net</code> 호출에 연결된 다른 접두어(예: <code> dcs.demdex.net</code>또는 <code> fast.demdex.net</code>등)가 표시될 수 있습니다. 접두사에 상관없이, 에 대한 호출은 <code><i>something</i>.demdex.net</code> 항상 Adobe <span class="keyword"> 에 대한 호출이며</span> 알 수 없거나 의심스러운 타사 도메인에 대한 호출은 아닙니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dpm</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DPM은</span> 데이터 공급자 <span class="wintitle"> 일치의 약어입니다</span>. 내부 Adobe <span class="keyword"> 시스템에 Audience</span> Manager나 <span class="keyword"> ID 서비스에서</span> 고객 데이터를 전달하여 동기화하거나 ID를 요청하는 것을 알려줍니다 <span class="wintitle"></span> . 이는 Audience Manager 또는 ID 서비스에서 <code> demdex.net</code> 볼 수 있는 가장 일반적인 <span class="keyword"> 전화입니다</span> <span class="wintitle"></span>. </p> <p><span class="wintitle"> DPM</span> 호출 기본 사항: </p> <p> 
     <ul id="ul_44023BB060774518BE414EE10820C141"> 
      <li id="li_0F94D1988A6944BA885FD40AB26FC49F"> <b> Audience <span class="keyword"> Manager</span> </b>:Audience <span class="wintitle"> Manager</span> 의 <span class="keyword"> DPM</span> 호출은 데이터 수집 서버 <span class="wintitle"> 및</span> 프로필 캐시 서버에 <span class="wintitle"> 데이터를</span>보냅니다. 데이터 <a href="../reference/system-components/components-data-collection.md"> 수집 구성 요소를 참조하십시오</a>. </li> 
      <li id="li_5A7EA9EE16EE4D828F0A24AE2B969122"> <b> ID 서비스 <span class="wintitle"></span> </b>:ID <span class="wintitle"> 서비스의</span> DPM <span class="wintitle"></span> 호출은 방문자 ID에 대한 요청입니다. 쿠키 및 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Experience Cloud ID 서비스</a> 및 Experience Cloud ID 서비스가 ID를 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_id_request.html" format="https" scope="external"> 요청 및 설정하는 방법을 참조하십시오</a>. </li> 
     </ul> </p> <p> <p>참고: ID 서비스 <span class="wintitle"> 고객은</span> 도메인 이름에서 DPM <span class="wintitle"></span> 접두사를 변경할 수 있습니다. audienceManager <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-subdomain-config.html" format="https" scope="external"> Server 및 audienceManagerServerSecure를 참조하십시오</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Experience Cloud ID 서비스](https://marketing.adobe.com/resources/help/en_US/mcvid/)
>* [Audience Manager 쿠키](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html)

