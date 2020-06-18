---
description: Audience Manager 및 Adobe Experience Platform ID 서비스는 demdex.net 도메인에서 데이터를 호출하고 수신합니다. Adobe가 비정상적인 타사 도메인을 사용하고 있는 것처럼 보일 수 있지만 그렇지 않습니다. 이 섹션에서는 demdex.net 호출의 요소에 대해 설명합니다.
seo-description: Audience Manager 및 Adobe Experience Platform ID 서비스는 demdex.net 도메인에서 데이터를 호출하고 수신합니다. Adobe가 비정상적인 타사 도메인을 사용하고 있는 것처럼 보일 수 있지만 그렇지 않습니다. 이 섹션에서는 demdex.net 호출의 요소에 대해 설명합니다.
seo-title: Demdex 도메인에 대한 호출 이해
solution: Audience Manager
title: Demdex 도메인에 대한 호출 이해
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
translation-type: tm+mt
source-git-commit: d219f6fa1e2a8396b049f86391142c00e263b629
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 12%

---


# Demdex 도메인에 대한 호출 이해{#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] 그리고 Adobe Experience Platform ID 서비스는 demdex.net 도메인에서 데이터를 호출하고 수신합니다. Adobe가 비정상적인 타사 도메인을 사용하고 있는 것처럼 보일 수 있지만 그렇지 않습니다. 이 섹션에서는 `demdex.net` 호출의 요소에 대해 설명합니다.

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
   <td colname="col2"> <p>This is a legacy domain controlled by <span class="keyword"> Adobe</span>. 이 보고서는 <span class="keyword"> Audience Manager</span>의 원래 획득 전 이름(<span class="keyword"> Demdex</span>)을 반영합니다. <span class="keyword"> Adobe</span> 는 2011년 <span class="keyword"> Demdex를</span> 인수하여 이 회사를 <span class="keyword"> Audience Manager으로 다시 브랜딩했습니다</span>. Audience Manager <span class="keyword"> , ID 서비스</span>및 설치된 사용자 기반에 <span class="wintitle"></span>깊이 있으므로 이 도메인을 변경하는 것은 어렵습니다. 작업 내역 <a href="../overview/aam-overview.md#history-and-background"> 및 배경을 참조하십시오</a>. </p> <p>기존 <code> demdex.net</code> 호출(예:, <code> dcs.demdex.net</code>등)에 첨부된 다른 접두사가 표시될 수 <code> fast.demdex.net</code>있습니다. 접두사에 상관없이 호출은 항상 <code><i>something</i>.demdex.net</code> Adobe <span class="keyword"></span> 에 대한 호출이며 알 수 없거나 의심스러운 타사 도메인이 아닙니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dpm</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DPM은</span> 데이터 공급자 <span class="wintitle"> 일치의 약어입니다</span>. It tells internal, <span class="keyword"> Adobe</span> systems that a call from <span class="keyword"> Audience Manager</span> or the <span class="wintitle"> ID service</span> is passing in customer data for synchronization or requesting an ID. Audience Manager <code> demdex.net</code> 또는 <span class="keyword"> ID 서비스에서</span> 볼 수 있는 가장 일반적인 <span class="wintitle"> 전화입니다</span>. </p> <p><span class="wintitle"> DPM</span> 호출 기본 사항: </p> <p> 
     <ul id="ul_44023BB060774518BE414EE10820C141"> 
      <li id="li_0F94D1988A6944BA885FD40AB26FC49F"> <b> <span class="keyword"> Audience Manager</span> </b>: Audience Manager의 <span class="wintitle"> CQ</span> 호출은 <span class="keyword"> 데이터</span> 서버 <span class="wintitle"></span> 및 <span class="wintitle"> 프로필 캐시 Dpm으로 데이터를</span>전송합니다. <a href="../reference/system-components/components-data-collection.md">데이터 수집 구성 요소</a>를 참조하십시오. </li> 
      <li id="li_5A7EA9EE16EE4D828F0A24AE2B969122"> <b> <span class="wintitle"> ID 서비스</span> </b>: ID 서비스에서 <span class="wintitle"> DPM</span> 호출은 방문자 ID에 대한 <span class="wintitle"></span> 요청입니다. 쿠키 <a href="https://docs.adobe.com/content/help/ko-KR/id-service/using/intro/cookies.html" format="https" scope="external"> 및 Adobe Experience Platform ID 서비스</a> 및 Adobe Experience Platform ID 서비스가 ID를 요청 및 설정하는 <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html" format="https" scope="external"> 방법을 참조하십시오</a>. </li> 
     </ul> </p> <p> <p>참고:  <span class="wintitle"> ID 서비스</span> 고객은 도메인 이름의 <span class="wintitle"> DPM</span> 접두사를 변경할 수 있습니다. audienceManager <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html" format="https" scope="external"> Server 및 audienceManagerServerSecure를 참조하십시오</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform ID 서비스](https://docs.adobe.com/content/help/ko-KR/id-service/using/home.html)
>* [Audience Manager 쿠키](https://docs.adobe.com/content/help/ko-KR/core-services/interface/ec-cookies/cookies-am.html)

