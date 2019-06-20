---
description: Audience Manager 및 Experience Cloud ID 서비스는 demdex.net 도메인을 호출하고 이 도메인에서 데이터를 수신합니다. Adobe가 비정상적인 타사 도메인을 사용하는 것처럼 보일 수 있지만 이는 사실이 아닙니다. 이 섹션에서는 demdex. net 호출의 요소에 대해 설명합니다.
seo-description: Audience Manager 및 Experience Cloud ID 서비스는 demdex.net 도메인을 호출하고 이 도메인에서 데이터를 수신합니다. Adobe가 비정상적인 타사 도메인을 사용하는 것처럼 보일 수 있지만 이는 사실이 아닙니다. 이 섹션에서는 demdex. net 호출의 요소에 대해 설명합니다.
seo-title: Demdex 도메인에 대한 호출 이해
solution: Audience Manager
title: Demdex 도메인에 대한 호출 이해
uuid: C 06 DAE 3 A-F 169-4712-80 FB-D 6 D 448 DCE 51 A
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Demdex 도메인에 대한 호출 이해{#understanding-calls-to-the-demdex-domain}

Audience Manager 및 Experience Cloud ID 서비스는 demdex.net 도메인을 호출하고 이 도메인에서 데이터를 수신합니다. Adobe가 비정상적인 타사 도메인을 사용하는 것처럼 보일 수 있지만 이는 사실이 아닙니다. 이 섹션에서는 demdex. net 호출의 요소에 대해 설명합니다.

<table id="table_B846CBEDDA4C4AD19416F7C27FC325C6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 전화 요소 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> demdex.net</code> </p> </td> 
   <td colname="col2"> <p>This is a legacy domain controlled by <span class="keyword"> Adobe</span>. <span class="keyword"> Audience Manager</span>의 기존 사전 획득 이름<span class="keyword"> (demdex</span>) 이 반영되어 있습니다. <span class="keyword"> Adobe</span> 는 2011 년 <span class="keyword"> Demdex</span> 를 인수했으며 <span class="keyword"> Adobe Audience Manager</span>로 브랜드를 다시 브랜딩했습니다. It is difficult to change this domain because it is entwined deeply with <span class="keyword"> Audience Manager</span>, the <span class="wintitle"> ID service</span>, and our installed user base. <a href="../overview/aam-overview.md#history-and-background"> 작업 내역 및 배경을 참조하십시오</a>. </p> <p>You may see other prefixes attached to legacy <code> demdex.net</code> calls (e.g., <code> dcs.demdex.net</code>, <code> fast.demdex.net</code>, etc.). Regardless of the prefix, a call to <code><i>something</i>.demdex.net</code> is always a call to <span class="keyword"> Adobe</span> and not to some unknown or suspicious third-party domain. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPM</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DPM</span> 는 <span class="wintitle"> 데이터 공급자에 대한 약자입니다</span>. <span class="keyword"> Audience</span> <span class="keyword"> Manager</span> 또는 <span class="wintitle"> ID 서비스에서</span> 고객 데이터를 전달하여 동기화를 위해 고객 데이터를 전달하거나 ID를 요청하는 것을 내부 Adobe 시스템에 알립니다. This is the most common <code> demdex.net</code> call you'll see from <span class="keyword"> Audience Manager</span> or the <span class="wintitle"> ID service</span>. </p> <p><span class="wintitle"> DPM</span> 호출 기본 사항: </p> <p> 
     <ul id="ul_44023BB060774518BE414EE10820C141"> 
      <li id="li_0F94D1988A6944BA885FD40AB26FC49F"> <b><span class="keyword"> Audience Manager</span></b>: Audience Manager의 <span class="wintitle"> DPM</span> <span class="keyword"> 호출은</span> 데이터 수집 <span class="wintitle"> 서버와</span> <span class="wintitle"> 프로필 캐시 서버로 데이터를 전송합니다</span>. <a href="../reference/system-components/components-data-collection.md"> 데이터 수집 구성 요소를 참조하십시오</a>. </li> 
      <li id="li_5A7EA9EE16EE4D828F0A24AE2B969122"> <b><span class="wintitle"> ID 서비스</span></b>: ID 서비스에서 <span class="wintitle"> DPM</span> <span class="wintitle"> 호출은</span> 방문자 ID에 대한 요청입니다. <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> 쿠키 및 Experience Cloud ID 서비스</a> , Experience Cloud ID 서비스가 ID 요청 및 설정 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_id_request.html" format="https" scope="external"> 방법을 참조하십시오</a>. </li> 
     </ul> </p> <p> <p>Note:  <span class="wintitle"> ID service</span> customers can change the <span class="wintitle"> DPM</span> prefix in the domain name. <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-subdomain-config.html" format="https" scope="external"> Audiencemanager 서버 및 audiencemanagerserversecure</a>를 참조하십시오. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ like_ this]
>
>* [Experience Cloud ID 서비스](https://marketing.adobe.com/resources/help/en_US/mcvid/)
>* [Audience Manager 쿠키](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html)

