---
description: 일반적인 개인 정보 및 데이터 관련 질문 또는 문제에 대한 답변
seo-description: 일반적인 개인 정보 및 데이터 관련 질문 또는 문제에 대한 답변
seo-title: 개인 정보 및 데이터 유지 FAQ
solution: Audience Manager
title: 개인 정보 및 데이터 유지 FAQ
uuid: EF 558 FCA -35 FF -44 F 1-8527-F 8 BEE 9 F 2 C 7 E 9
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

---


# Privacy and Data Retention FAQ{#privacy-and-data-retention-faq}

일반적인 개인 정보 및 데이터 관련 질문 또는 문제에 대한 답변

<!-- faq_privacy.xml -->

## Privacy FAQ {#privacy-faq}

>[!TIP]
>
>Visit the [Adobe Privacy Center](https://www.adobe.com/privacy.html) for more information.

**Audience Manager는 쿠키를 어떻게 사용하고 쿠키는 어떤 쿠키를 설정합니까?**

[Audience Manager 쿠키를 참조하십시오](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html).

**미국의 Audience Manager 클라이언트가 EU 속성을 타깃팅할 수 있습니까?**

예. Adobe Audience Manager는 국제 자산과 인벤토리가 있는 고객과 협력하고 있습니다. EU 에는 엄격한 개인 정보 보호 법이 있지만 Audience Manager 에는 유럽의 대상 타깃팅을 위해 자사 데이터를 사용하는 클라이언트가 있습니다. Audience Manager는 EU 대상자에 대한 타깃팅을 지원할 수 있지만, 로컬 개인 정보 보호 규정을 준수하는 것은 귀하의 책임입니다.

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## 데이터 보존 FAQ {#data-retention-faq}

다음 표에는 서로 다른 데이터 유형과 저장 시스템에 대한 유지 시간이 나와 있습니다.

<table id="table_21C0B13A57A44DE0999FB33F363C88F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 데이터 유형, 소스 또는 저장소 </th> 
   <th colname="col2" class="entry"> 데이터 보존 기간 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>백엔드 서버 </p> </td> 
   <td colname="col2"> <p>120 일. </p> <p> Audience Manager는 마지막으로 Audience Manager 플랫폼에서 사용자를 본 후 120 일 후에 백엔드 서버에서 사용자 데이터를 삭제합니다. <span class="keyword"> Audience Manager</span> 가 이 120 일 주기 내에 사용자 활동을 기록하는 경우, Adobe는 이 데이터를 다른 120 일간 보관합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Edge Server </p> </td> 
   <td colname="col2"> <p> 14 일. </p> <p>Audience Manager는 마지막으로 Audience Manager 플랫폼에서 사용자를 본 후 14 일 후에 Edge Server에서 사용자 데이터를 삭제합니다. <span class="keyword"> Audience Manager</span> 가 이 14 일 주기 내에 사용자 활동을 기록하는 경우, Adobe는 이 데이터를 다른 14 일간 보관합니다. 사용자가 14 일 기간 이후에 다시 활성화되는 경우 처음 새 페이지 보기와 사용자가 실행 가능한 시기 사이에 지연이 생깁니다. 14 일 이상 활동하지 않은 경우 전체 프로필을 다시 에지 센터로 가져오는 데 6-18 시간이 걸립니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Raw 로그 </p> </td> 
   <td colname="col2"> <p>180 일 (활동이 없는 180 일 후 제거됨). </p> <p>Raw logs are data received by an edge server via HTTP calls or from onboarded files sent in to <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>광고 서버 로그 </p> </td> 
   <td colname="col2"> <p><b>보고</b> </p> <p>로그 파일은 최대 30 일 동안 보고 목적으로 보관됩니다. We do not persist unmatched logs (i.e. logs for which there is no ID sync between a visitor's ad server ID and <span class="keyword"> Audience Manager</span> ID) in our backend storage, and matched logs stored in <span class="keyword"> Amazon S3</span> are retained for up to 30 days. </p> <p><b>실행 가능 로그 파일</b> </p> <p>일치와 일치하지 않는 로그 모두 최대 30 일간 유지됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM 수준 프로필 (인증된 프로필) </p> </td> 
   <td colname="col2"> <p>비활성 CRM 수준 프로필 (고객 ID) 에 대한 기본 TTL (time-to-live) 간격은 24 개월입니다. 그러나 Audience Manager UI를 사용하여 1 달과 5 년 간의 비활성 CRM 레벨 프로필의 TTL 간격을 줄이거나 확장할 수 있습니다. 크로스 디바이스 데이터 소스를 만들거나 편집할 때 이를 완수할 수 있습니다.</p> <p>For more information, see Data Source Settings in <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Create a Cross-Device Data Source </a>.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>모바일 장치 ID </p> </td> 
   <td colname="col2"> <p>The retention conditions for mobile device IDs (<a href="../reference/ids-in-aam.md"> IDFA, GAID</a>) follow the cadence described in the first two rows, back-end servers and edge servers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>고객 데이터 피드 (CDF) </p> </td> 
   <td colname="col2"> <p>A CDF file contains the same data that an <span class="keyword"> Audience Manager</span> event call (/event) sends to our servers. 유지 기간은 8 일입니다. For more details about CDF, please refer to <a href="../features/cdf-files.md"> CDF Intro</a> and <a href="../faq/faq-cdf.md"> CDF FAQ</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>동기화된 ID 간 매핑 </p> </td> 
   <td colname="col2"> <p>Mappings between synchronized IDs may be kept for the life of the associated <a href="../reference/ids-in-aam.md"> Audience Manager Unique User ID (AAM UUID)</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>인바운드 데이터 </p> </td> 
   <td colname="col2"> <p>This is inbound data you send to <span class="keyword"> Audience Manager</span> by FTP or directly to an <span class="keyword"> Amazon S3</span> directory. <a href="../faq/faq-inbound-data-ingestion.md"> 인바운드 고객 데이터 통합 FAQ</a>를 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>아웃바운드 데이터 </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager가 타사 정품 인증 파트너에게</span> 보내는 일괄 처리 데이터입니다. 유지 기간은 8 일입니다. For more details about Outbound data, please refer to <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md"> Outbound Batch Transfers</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Trait Qualification Data Retention {#trait-qual}

아래 표에는 트레이트 자격 조건에 대한 유지 옵션이 나와 있습니다.

<table id="table_7FB42BEF138540AAB6869995C1AB8D3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 특성 작업 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>특성 삭제 </p> </td> 
   <td colname="col2"> <p>트레이트를 삭제하면 이전에 트레이트에 대한 자격을 갖춘 모든 사용자 프로필의 특성 자격 데이터가 제거됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>특성 제한에 도달했습니다. </p> </td> 
   <td colname="col2"> <p>Adobe는 각 사용자 프로필에 대해 100,000 개의 트레이트 자격 조건을 적용합니다. 이 제한은 인증된 프로필 및 장치 프로필에 적용됩니다. 사용자 프로필이 이 제한에 도달하는 경우 첫 번째 아웃 기준으로 가장 오래된 특성 자격을 삭제합니다. </p> <p>For more details, read our <a href="../features/traits/trait-qualification-reference.md#trait-qualification-limit"> Trait Qualification Limit</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

