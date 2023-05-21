---
description: 일반적인 개인 정보 및 데이터 관련 질문 또는 문제에 대한 답변
seo-description: Answers to common privacy- and data-related questions or issues.
seo-title: Privacy and Data Retention FAQ
solution: Audience Manager
title: 개인 정보 보호 및 데이터 유지 관련 FAQ
uuid: ef558fca-35ff-44f1-8527-f8bee9f2c7e9
feature: Data Governance & Privacy
exl-id: bccf49d7-1a3b-4286-86fb-59e472af4501
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 83%

---

# 개인 정보 보호 및 데이터 유지 관련 FAQ{#privacy-and-data-retention-faq}

일반적인 개인 정보 및 데이터 관련 질문 또는 문제에 대한 답변

<!-- faq_privacy.xml -->

## 개인 정보 관련 FAQ {#privacy-faq}

>[!TIP]
>
>자세히 알려면 [Adobe 개인 정보 보호 센터](https://www.adobe.com/kr/privacy.html)를 방문하십시오.

**Audience Manager는 쿠키를 어떻게 사용하며 어떤 쿠키를 설정합니까?**

[Audience Manager 쿠키](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html)를 참조하십시오.

**미국의 Audience Manager 고객이 EU 자산에서 사용자를 타겟팅할 수 있습니까?**

예. Audience Manager는 국제적인 자산 및 인벤토리가 있는 고객과 협력합니다. EU에는 엄격한 개인 정보 보호법이 있지만 Audience Manager에는 유럽에서 대상 타겟팅에 자사 데이터를 사용하는 고객이 있습니다. Audience Manager는 EU 대상에 대한 타겟팅을 지원할 수 있지만 현지 개인 정보 보호 규정을 준수하는 것은 귀사의 책임입니다.

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## 데이터 유지 FAQ {#data-retention-faq}

다음 표에는 다양한 데이터 유형 및 저장소 시스템의 유지 시간이 나와 있습니다.

<table id="table_21C0B13A57A44DE0999FB33F363C88F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 데이터 유형, 소스 또는 저장소 </th> 
   <th colname="col2" class="entry"> 데이터 유지 기간 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>백엔드 서버 </p> </td> 
   <td colname="col2"> <p>120일 </p> <p> Audience Manager는 Audience Manager 플랫폼에서 사용자를 마지막으로 본 후 120일 후에 백엔드 서버에서 사용자 데이터를 삭제합니다. If <span class="keyword"> Audience Manager</span> 사용자 활동을 이 120일 주기 내에 기록합니다. 이 데이터는 다른 120일 동안 보관됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Edge Server </p> </td> 
   <td colname="col2"> <p> 14일 </p> <p>Audience Manager는 Audience Manager 플랫폼에서 사용자를 마지막으로 본 후 14일 후에 Edge Server에서 사용자 데이터를 삭제합니다. If <span class="keyword"> Audience Manager</span> 사용자 활동을 이 14일 주기 내에 기록합니다. 이 데이터는 다른 14일 동안 보관됩니다. 14일 주기 후에 사용자가 다시 활성 상태가 되면 첫 번째 새 페이지 보기와 사용자가 조치를 취할 수 있는 시점 사이에 지연이 생깁니다. 14일 이상 활동이 없으면 전체 프로필을 Edge 센터로 되돌리는 데 6~18시간이 걸립니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>원시 로그 </p> </td> 
   <td colname="col2"> <p>60일(60일 동안 활동이 없으면 제거됨) </p> <p>원시 로그는 HTTP 호출이나 <span class="keyword">Audience Manager</span>에 전송된 온보딩된 파일을 통해 Edge Server에 의해 수신되는 데이터입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>광고 서버 로그 </p> </td> 
   <td colname="col2"> <p><b>보고</b> </p> <p>로그 파일은 보고 목적으로 최대 30일 동안 유지됩니다. 일치하지 않는 로그(예: 방문자의 광고 서버 ID와 <span class="keyword">Audience Manager</span> ID 간에 ID 동기화가 없는 로그)는 Adobe의 백엔드 저장소에서 유지되지 않으며, <span class="keyword">Amazon S3</span>에 저장된 일치하는 로그는 최대 30일 동안 유지됩니다. </p> <p><b>실행 가능 로그 파일</b> </p> <p>일치하는 로그와 일치하지 않는 로그가 모두 최대 30일 동안 유지됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM 수준 프로필(인증된 프로필) </p> </td> 
   <td colname="col2"> <p>비활성 CRM 수준 프로필(고객 ID)의 기본 TTL(Time-to-Live) 간격은 24개월입니다. 그러나 Audience Manager 사용자 인터페이스를 사용하여 비활성 CRM 수준 프로필의 TTL 간격을 1개월에서 5년 사이에서 줄이거나 연장할 수 있습니다. 교차 장치 데이터 소스를 만들거나 편집할 때 이렇게 할 수 있습니다.</p> <p>자세한 내용은 <a href="../features/profile-merge-rules/merge-rules-start.md#settings">교차 장치 데이터 소스 만들기</a>의 데이터 소스 설정을 참조하십시오.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>모바일 장치 ID </p> </td> 
   <td colname="col2"> <p>모바일 장치 ID(<a href="../reference/ids-in-aam.md">IDFA, GAID</a>)에 대한 유지 조건은 처음 두 행, 백엔드 서버 및 Edge Server에 설명된 간격을 따릅니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CDF(고객 데이터 피드) </p> </td> 
   <td colname="col2"> <p>CDF 파일에는 <span class="keyword">Audience Manager</span> 이벤트 호출(/event)이 서버에 보내는 것과 동일한 데이터가 포함되어 있습니다. 유지 기간은 8일입니다. CDF에 대한 자세한 내용은 <a href="../features/cdf-files.md">CDF 소개</a> 및 <a href="../faq/faq-cdf.md">CDF FAQ</a>를 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>동기화된 ID 간 매핑 </p> </td> 
   <td colname="col2"> <p>Audience Manager 쿠키 ID(<a href="../reference/ids-in-aam.md">Audience Manager 고유 사용자 ID 또는 AAM UUID</a>)와 타사 쿠키 ID 간의 <a href="../features/administration/usage-limits.md#id-mapping-limits">ID 매핑</a>의 수명은 120일로 제한되어 있습니다. ID 매핑의 수명은 Audience Manager 네트워크에 Audience Manager 쿠키가 보일 될 때마다 재설정됩니다. 가장 최근의 ID 매핑 동기화는 연결된 <a href="../reference/ids-in-aam.md">AAM UUID(Audience Manager Unique User ID)</a>의 수명 동안 유지됩니다.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>인바운드 데이터 </p> </td> 
   <td colname="col2"> <p>귀사가 FTP를 통해 <span class="keyword">Audience Manager</span>에 보내거나 <span class="keyword">Amazon S3</span> 디렉토리에 바로 보내는 인바운드 데이터입니다. <a href="../faq/faq-inbound-data-ingestion.md">인바운드 고객 데이터 섭취 FAQ</a>를 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>아웃 바운드 데이터 </p> </td> 
   <td colname="col2"> <p><span class="keyword">Audience Manager</span>가 타사 활성화 파트너에게 보내는 배치 데이터입니다. 유지 기간은 8일입니다. 아웃바운드 데이터에 대한 자세한 내용은 <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md">아웃바운드 배치 전송</a>을 참조하십시오. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 트레이트 자격 데이터 유지 {#trait-qual}

아래 표에는 트레이트 자격에 대한 유지 옵션이 나와 있습니다.

<table id="table_7FB42BEF138540AAB6869995C1AB8D3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 트레이트 작업 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>트레이트 삭제 </p> </td> 
   <td colname="col2"> <p>트레이트를 삭제하면 과거에 트레이트에 대해 자격이 부여된 모든 사용자 프로필에서 트레이트 자격 데이터가 제거됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>트레이트 제한에 도달 </p> </td> 
   <td colname="col2"> <p>각 사용자 프로필마다 트레이트 자격에 100,000개라는 제한을 두었습니다. 이 제한은 인증된 프로필 및 장치 프로필에 적용됩니다. 사용자 프로필이 이 제한에 도달하면 가장 오래된 트레이트 자격부터 선입선출 방식으로 삭제됩니다. </p> <p>자세한 내용은 <a href="../features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit">트레이트 자격 제한</a>을 참조하십시오. </p> </td> 
  </tr> 
 </tbody> 
</table>
