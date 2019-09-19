---
description: 일반적인 개인 정보 및 데이터 관련 질문 또는 문제에 대한 답변
seo-description: 일반적인 개인 정보 및 데이터 관련 질문 또는 문제에 대한 답변
seo-title: 개인 정보 및 데이터 유지 FAQ
solution: Audience Manager
title: 개인 정보 및 데이터 유지 FAQ
uuid: ef558fca-35ff-44f1-8527-f8bee9f2c7e9
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

---


# Privacy and Data Retention FAQ{#privacy-and-data-retention-faq}

일반적인 개인 정보 및 데이터 관련 질문 또는 문제에 대한 답변

<!-- faq_privacy.xml -->

## 개인 정보 FAQ {#privacy-faq}

>[!TIP]
>
>자세한 내용은 [Adobe 개인 정보](https://www.adobe.com/privacy.html) 센터를 참조하십시오.

**Audience Manager는 쿠키를 어떻게 사용하고 어떤 쿠키를 설정합니까?**

See [Audience Manager Cookies](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html).

**미국의 Audience Manager 클라이언트가 EU 속성에 대해 사용자를 타깃팅할 수 있습니까?**

예. Audience Manager는 국제 자산 및 인벤토리를 보유한 고객과 연동됩니다. EU는 엄격한 개인 정보 보호 법을 갖고 있지만 Audience Manager는 유럽에서 고객을 타깃팅하기 위해 퍼스트 파티 데이터를 사용하는 클라이언트를 보유하고 있습니다. Audience Manager는 EU 고객을 대상으로 하는 타깃팅을 지원할 수 있지만 로컬 개인 정보 보호 규정을 준수하는 것은 귀하의 책임입니다.

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## 데이터 보존 FAQ {#data-retention-faq}

다음 표에는 다양한 데이터 유형과 스토리지 시스템에 대한 보존 시간이 나와 있습니다.

<table id="table_21C0B13A57A44DE0999FB33F363C88F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 데이터 유형, 소스 또는 스토리지 </th> 
   <th colname="col2" class="entry"> 데이터 보존 기간 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>백엔드 서버 </p> </td> 
   <td colname="col2"> <p>120일 </p> <p> Audience Manager는 Audience Manager 플랫폼에서 사용자를 마지막으로 본 후 120일 후 백엔드 서버에서 사용자 데이터를 삭제합니다. Audience <span class="keyword"> Manager가</span> 이 120일 주기 내에 사용자 활동을 기록하는 경우 이 데이터는 120일 동안 계속 보관됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Edge Server </p> </td> 
   <td colname="col2"> <p> 14일 </p> <p>Audience Manager는 Audience Manager 플랫폼에서 사용자를 마지막으로 본 후 14일 후 Edge Server에서 사용자 데이터를 삭제합니다. Audience <span class="keyword"> Manager가</span> 이 14일 주기 내에 사용자 활동을 기록하는 경우, 이 데이터는 14일 동안 추가로 보관됩니다. 사용자가 14일 이후에 다시 활성화되면 첫 번째 새 페이지 뷰와 사용자가 작업을 수행할 수 있게 되는 시기 사이에 지연이 발생합니다. 14일 이상의 비활동 상태가 발생한 후 전체 프로필을 Edge Center로 다시 가져오려면 6-18시간이 소요됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Raw 로그 </p> </td> 
   <td colname="col2"> <p>180일(180일 동안 활동이 없는 후 제거됨) </p> <p>Raw 로그는 Audience Manager에 전송된 HTTP 호출을 통해 Edge Server에서 수신되는 <span class="keyword"> 데이터입니다</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>광고 서버 로그 </p> </td> 
   <td colname="col2"> <p><b>보고</b> </p> <p>로그 파일은 최대 30일 동안 보고용으로 유지됩니다. Adobe는 백 엔드 저장소에서 일치하지 않는 로그(즉, 방문자의 광고 서버 ID와 Audience Manager ID 사이에 ID가 동기화되지 않은 로그) <span class="keyword"> 를</span> 지속하지 않으며, Amazon S3에 <span class="keyword"> 저장된 일치된 로그는 최대 30일 동안</span> 유지됩니다. </p> <p><b>실행 가능 로그 파일</b> </p> <p>일치된 로그와 일치하지 않는 로그가 최대 30일 동안 유지됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM 수준 프로필(인증된 프로필) </p> </td> 
   <td colname="col2"> <p>비활성 CRM 수준 프로필(고객 ID)의 기본 TTL(Time to Live) 간격은 24개월입니다. 그러나 Audience Manager UI를 사용하여 비활성 CRM 수준 프로필의 TTL 간격을 1개월에서 5년 사이 줄이거나 확장할 수 있습니다. 크로스 장치 데이터 소스를 만들거나 편집할 때 이를 수행할 수 있습니다.</p> <p>자세한 내용은 장치 간 데이터 소스 <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> 만들기에서 데이터 소스 설정을 참조하십시오 </a>.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>모바일 장치 ID </p> </td> 
   <td colname="col2"> <p>모바일 장치 ID(IDFA,<a href="../reference/ids-in-aam.md"> GAID</a>)에 대한 보존 조건은 처음 두 행, 백엔드 서버 및 Edge Server에 설명된 cadence를 따릅니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>고객 데이터 피드(CDF) </p> </td> 
   <td colname="col2"> <p>CDF 파일에는 Audience Manager 이벤트 호출(/event)이 <span class="keyword"> Adobe</span> 서버로 전송하는 것과 동일한 데이터가 들어 있습니다. 보존 기간은 8일입니다. CDF에 대한 자세한 내용은 CDF 소개 및 <a href="../features/cdf-files.md"> CDF</a> FAQ를 <a href="../faq/faq-cdf.md"> 참조하십시오</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>동기화된 ID 간 매핑 </p> </td> 
   <td colname="col2"> <p>동기화된 ID 간 매핑은 연결된 Audience Manager 고유 사용자 ID( <a href="../reference/ids-in-aam.md"> AAM UUID)</a>동안 유지될 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>인바운드 데이터 </p> </td> 
   <td colname="col2"> <p>FTP를 통해 Audience <span class="keyword"> Manager로</span> 전송하거나 Amazon S3 <span class="keyword"> 디렉토리로 직접 전송하는 인바운드 데이터입니다</span> . 인바운드 <a href="../faq/faq-inbound-data-ingestion.md"> 고객 데이터 통합 FAQ를 참조하십시오</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>아웃바운드 데이터 </p> </td> 
   <td colname="col2"> <p>Audience Manager가 제3자 <span class="keyword"> 활성화</span> 파트너에게 보내는 배치 데이터입니다. 보존 기간은 8일입니다. 아웃바운드 데이터에 대한 자세한 내용은 아웃바운드 배치 전송을 <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md"> 참조하십시오</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 트레이트 자격 데이터 유지 {#trait-qual}

아래 표에는 트레이트 자격에 대한 유지 옵션이 나와 있습니다.

<table id="table_7FB42BEF138540AAB6869995C1AB8D3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 특성 작업 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>트레이트 삭제 </p> </td> 
   <td colname="col2"> <p>트레이트를 삭제하면 이전 트레이트에 대해 자격을 부여했던 모든 사용자 프로필에서 트레이트 자격 데이터가 제거됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>트레이트 제한에 도달했습니다. </p> </td> 
   <td colname="col2"> <p>각 사용자 프로필에 대해 10만 가지 트레이트 자격 조건을 적용합니다. 이 제한은 인증된 프로필 및 장치 프로필에 적용됩니다. 사용자 프로필이 이 제한에 도달하면 가장 오래된 트레이트 자격 조건을 선착순으로 삭제합니다. </p> <p>자세한 내용은 트레이트 자격 <a href="../features/traits/trait-qualification-reference.md#trait-qualification-limit"> 제한을 참조하십시오</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

