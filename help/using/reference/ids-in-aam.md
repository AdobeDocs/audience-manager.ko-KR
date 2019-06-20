---
description: Adobe Audience Manager ID의 전체 목록은 이 문서를 참조하십시오.
keywords: dpid; Dpuuid; cid; UUID; UUID; UUID
seo-description: Adobe Audience Manager ID의 전체 목록은 이 문서를 참조하십시오.
seo-title: Audience Manager의 ID 색인
solution: Audience Manager
title: Audience Manager의 ID 색인
uuid: 292185 EC -7 C 6 A -414 B-AB 17-800 C 21 CB 1 F 01
translation-type: tm+mt
source-git-commit: 94046c4ed825949451d0dbad37adbe9fba0f9191

---


# Index of IDs in Audience Manager{#index-of-ids-in-audience-manager}

Adobe Audience Manager ID의 전체 목록은 이 문서를 참조하십시오.

<table frame="all" id="table_6727BA8BBF2C40E48768126B4EC9984E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID </th> 
   <th colname="col2" class="entry"> 이름 및 설명 </th> 
   <th colname="col3" class="entry"> 예 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>SID </p> </td> 
   <td colname="col2"> <p> <b>특성 ID</b> </p> <p>The Trait ID uniquely identifies traits in the <span class="keyword"> Audience Manager</span> environment. 특성 ID는 UI (사용자 인터페이스) 의 각 특성에 할당됩니다. </p> </td> 
   <td colname="col3"> <p><code> 289983</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SID </p> </td> 
   <td colname="col2"> <p> <b>세그먼트 ID </b> </p> <p>The Segment ID uniquely identifies segments in the <span class="keyword"> Audience Manager</span> environment. 세그먼트 ID가 UI의 각 세그먼트에 할당됩니다. </p> </td> 
   <td colname="col3"> <p><code> 4798574</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Csegid </p> </td> 
   <td colname="col2"> <p> <b>기존 세그먼트 ID </b> </p> <p>This ID uniquely identifies segments in the <span class="keyword"> Audience Manager</span> environment. UI의 각 세그먼트에 이전 세그먼트 ID가 할당됩니다. </p> </td> 
   <td colname="col3"> <p><code> 741232</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>destid </p> </td> 
   <td colname="col2"> <p> <b>대상 ID </b> </p> <p>The Destination ID uniquely identifies destinations in the <span class="keyword"> Audience Manager</span> environment. UI의 각 대상에 ID가 할당됩니다. </p> </td> 
   <td colname="col3"> <p><code> 2523</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>dpid </p> </td> 
   <td colname="col2"> <p> <b>데이터 소스 ID (데이터 공급자 ID 라고도 함)</b> </p> <p>데이터 소스 ID는 ID 또는 트레이트에 대한 네임스페이스입니다. UI에서 각 데이터 소스 (데이터 공급자) 에 ID가 할당됩니다. </p> </td> 
   <td colname="col3"> <p><code> 39217</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dpuuid </p> </td> 
   <td colname="col2"> <p> <b>데이터 공급자 고유한 사용자 ID </b><b>(CRM ID 라고도 함)</b> </p> <p>타사 ID. 이것은 사용자가 자신의 CRM 시스템에서 최종 사용자를 식별하는 ID 입니다. You can sync DPUUIDs with <span class="keyword"> Audience Manager</span> UUIDs and you can sync DPUUIDs from your different <span class="wintitle"> Data Sources</span> (DPIDs) in the <a href="../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md"> ID synchronization process</a>. </p> </td> 
   <td colname="col3"> <p><code> 2132-3423 VN -343 FDS -3432 R</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM ID </p> </td> 
   <td colname="col2"> <p>위의 DPUUID를 참조하십시오. </p> </td> 
   <td colname="col3"> <p><code> 2132-3423 VN -343 FDS -3432 R</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>cid, cid_ ic </p> </td>
   <td colname="col2"> <p> <b>고객 ID, 고객 ID 통합 코드</b> </p> <p> <b>cid 및 cid_ ic 키-값 쌍은 <a href="../reference/cid.md"> dpid 및 dpuuid</a>를 대체합니다.</b> DPID 및 DPUUID와 동일한 기능을 제공하지만 데이터 공급자 ID와 사용자 ID (또는 통합 코드) 가 하나의 키-값 쌍에 포함되므로 보다 효율적입니다. </p> </td> 
   <td colname="col3"> <p><code> 81841% 013 ad 2948 b 1570 a 7 e 408 a 7 cfb 7 ff 4879 e 4 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AAM UUID </p> </td> 
   <td colname="col2"> <p> <b><span class="keyword"> Audience Manager</span> 고유 사용자 ID </b> </p> <p> A numerical, 38-digit device ID that <span class="keyword"> Audience Manager</span> associates to each device it interacts with. <span class="keyword"> Audience Manager</span> 는 이 ID를 "demdex. net" 타사 도메인에 쿠키로 저장하려고 시도합니다. </p> <p>Audience Manager UUID는 이벤트 호출 시 d_ uuid 신호로 전송됩니다. </p> </td> 
   <td colname="col3"> <p><code> demdex = 07955261652886032950143702505894272138</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Imsorgid </p> </td> 
   <td colname="col2"> <p> <b>조직 ID</b> </p> <p>Experience Cloud 등록 시 회사가 제공하는 ID 입니다. To learn how you can find your company's Organization ID, read <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html"> Organizations and Account Linking</a> and scroll down to Find your Organization ID.</p> </td> 
   <td colname="col3"> <p><code> 5DC5123F5245B1D20A490D46@AdobeOrg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p> <b>파트너 ID</b> </p> <p> The PID is a company's ID in <span class="keyword"> Audience Manager</span>. <span class="keyword"> Audience Manager</span> 는 imsorgid를 PID에 연결합니다. </p> </td> 
   <td colname="col3"> <p><code> 1352</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ECID, MID </p> </td> 
   <td colname="col2"> <p> <b>Experience Cloud ID</b> </p> <p>The Experience Cloud ID (ECID, legacy abbreviations MID or MCID) is derived mathematically from your Organization ID and the <span class="keyword"> Audience Manager</span> Unique User ID. 이러한 ID가 일정하게 유지되는 한 특정 사용자에 대한 올바른 ECID를 생성하는 것은 수학 문제입니다. 동일한 조직 ID와 Audience Manager UUID를 사용하면 항상 동일한 ECID 값을 받게 됩니다. <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> 쿠키와 Experience Cloud ID</a> 문서에서 ECID에 대해 자세히 알아볼 수 있습니다. </p> </td> 
   <td colname="col3"> <p><code> mid=08382830887934830189014177072406221371 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="2"> <p>Daid </p> <p> 
     <ul id="ul_4EA61BDD0C9140C894162F50300BA9DB"> 
      <li id="li_16148BDD80194F509FF7935364B77F7A">IDFA </li> 
      <li id="li_DF7FEEF2D46A42C5B9FECD6377758B1A">Gaid </li>
      <li>RIDA</li>
      <li>MAID</li>
      <li>DUID</li>
     </ul> </p> </td> 
   <td colname="col2"> <p> <b>장치 광고 ID</b> </p> <p>각 하드웨어 장치에 고유한 ID로서, 광고 목적으로 사용됩니다. 일반적으로 장치 또는 장치 운영 체제의 제조업체가 제공합니다. </p> </td> 
   <td colname="col3"> <p>IDFA, Gaid, Roku ID, Playstation ID </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>장치 광고 ID - IDFA - iOS 장치</b> </p> <p> <b>IDFA</b> ID는 장치 제조업체에서 제공하는 모바일 장치 식별자입니다. 이러한 ID는 iOS 운영 체제를 실행하는 장치를 나타냅니다. </p> </td> 
   <td colname="col3"> <p> The format strictly consists of 32 <i>uppercase</i> hexadecimal digits, displayed in five groups and separated by hyphens, in the form 8-4-4-4-12, for a total of 36 characters. </p> <p><code> AEBE 52 E 7-03 EE -455 A-B 3 C 4-E 57283966239</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>장치 광고 ID - Gaid - Android 장치</b> </p> <p><b>Gaid</b> ID는 장치 제조업체에서 제공하는 모바일 장치 식별자입니다. 이러한 ID는 Android 운영 체제를 실행하는 장치를 나타냅니다. </p> </td> 
   <td colname="col3"> <p><i>이 형식은</i> 16 진수 16 진수 자릿수로 구성되며 5 개의 그룹에 표시되고 하이픈으로 구분됩니다 (8-4-4-4-12). </p> <p> <code> E 4 FE 9 BDE-CAA 0-47 B 6-908 D-FFBA 3 FA 184 F 2</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>Roku - RIDA - Roku Streaming Devices</b> </p> <p><b>Gaid</b> RIDA ID는 Roku 장치 제조업체가 제공하는 스트리밍 장치 식별자입니다.</p> </td>
   <td colname="col3"> <p><i>이 형식은</i> 16 진수 16 진수 자릿수로 구성되며 5 개의 그룹에 표시되고 하이픈으로 구분됩니다 (8-4-4-4-12). </p> <p> <code> fcb 2 a 29 c -315 a -5 e 6 b-bcfd-d 889 ba 19 aada</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>Microsoft Advertising ID - MAID - Windows 10 장치</b> </p> <p><b>메이드</b> ID는 디바이스별로 Windows 10에서 생성된 디바이스 식별자입니다.</p> </td>
   <td colname="col3"> <p>Maid는 영숫자 문자열로 지정됩니다.</p></td>
  </tr>
   <tr> 
   <td colname="col2"> <p> <b>Samsung Duid - Samsung 장치</b> </p> Samsung Duid는 Samsung TV에서 제공하는 장치 식별자입니다.</p> </td>
   <td colname="col3"> <p>Samsung Duid는 영숫자 문자열로 지정됩니다.</p></td>
  </tr>
 </tbody> 
</table>