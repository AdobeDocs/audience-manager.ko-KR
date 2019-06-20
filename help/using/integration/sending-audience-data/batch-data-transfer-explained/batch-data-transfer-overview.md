---
description: 다른 시스템 (오프라인) 의 데이터를 Audience Manager로 가져오려는 기술 및 비기술 고객을 위한 개요입니다.
keywords: 인바운드
seo-description: 다른 시스템 (오프라인) 의 데이터를 Audience Manager로 가져오려는 기술 및 비기술 고객을 위한 개요입니다.
seo-title: Audience Manager 개요로 일괄 데이터 보내기
solution: Audience Manager
title: Audience Manager 개요로 일괄 데이터 보내기
uuid: 472583 B 1-5057-4 Add -8 E 3 C -5 E 50762 C 88 E 0
translation-type: tm+mt
source-git-commit: 94046c4ed825949451d0dbad37adbe9fba0f9191

---


# Send Batch Data to Audience Manager Overview{#send-batch-data-to-audience-manager-overview}

다른 시스템 (오프라인) 의 데이터를 Audience Manager로 가져오려는 기술 및 비기술 고객을 위한 개요입니다.

## 장점

<!-- c_offline_to_online.xml -->

Audience Manager에서 다른 시스템의 데이터를 만들 수 있습니다. Adobe 시스템을 통해 이전에 수집한 사용자 데이터를 활용하고 사용자 데이터를 활용할 수 있습니다. This includes information about purchases, customer surveys, registration data, [!DNL CRM] databases, etc. 각 통합은 고유한 과제를 제공하지만 이러한 공통적인 단계는 모두 공유합니다. 이 자료를 검토하여 오프라인 데이터를 온라인으로 가져오는 데 필요한 노력을 줄이십시오.

## 1 단계: 사용자 ID 동기화

동기화 중에 Audience Manager는 클라이언트 및 사용자에게 고유한 ID를 할당합니다. These IDs are known as the [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) and [!UICONTROL Unique User ID] ([!UICONTROL UUID]), respectively. Audience Manager uses the [!UICONTROL DPID] and [!UICONTROL UUID] to identify users and qualify them for traits, segments, audience groups, and for reporting. Additionally, our data collection code ([!UICONTROL DIL]) looks for these IDs to capture visitor data from your website. 이 단계가 완료되면 Audience Manager와 오프라인 저장소에는 각 사용자 레코드에 대한 해당 ID가 포함되어야 합니다.

이 단계에 대한 중요한 고려 사항:

* **클라이언트 ID 배치:** Audience Manager는 웹 사이트에서 클라이언트 ID가 표시되는 위치를 알아야 합니다 (예: 쿠키, Analytics 변수, 페이지 코드에 저장된 IS).
* **제외[!DNL PII]:** 사용자 ID 에는 개인 식별 정보 ([!DNL PII]) 가 포함되면 안 됩니다.
* **사례 및 컨텐츠 민감도:** 실시간 데이터 동기화 중에 Audience Manager에서 사이트에서 캡처한 사용자 ID는 오프라인 저장소에서 전달된 ID와 일치해야 합니다. For example, if offline records hold information about [!DNL User123], but your site renders that ID as [!DNL USER123], Audience Manager sees these as different visitors. 따라서 이 방문자에 대한 온라인 정보는 오프라인 데이터베이스의 해당 기록과 연결할 수 없습니다. ID는 정확하게 일치해야 합니다.

See [ID Synchronization for Inbound Data Transfers](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

<!-- 

<p> <b>Step 2: Create a Translation File</b> </p> 
<p>A translation file classifies data according to uniform and logical hierarchy. It is a taxonomy that helps you organize information from general categories (e.g., geography) to more precise classifications (e.g., <i>geography > United States > New York</i>). Also, it labels data with to easy to understand names such as "gender=male" or "color=green" instead of with your internal SKUs, abbreviations, or other names. The file lets Audience Manager display this information in a readable, logical manner. You and your data partners must create and share the translation file with Audience Manager before any real-time or server-to-server data transfers can begin. You can update this file on a schedule relevant to your business needs. </p> 
<p>Important considerations about this step: </p> 
<ul id="ul_6A05AECB0BD649B1BF1B34058E9008E2"> 
 <li id="li_39817ED898F14156A77FCAC066FE0968"> <b>Create a comprehensive list:</b> The translation file must include all the possible values that can be passed in on a particular key. For example, if you have category key called "color" and it accepts the values "red," "green," and "blue," the translation file must contain <i>all</i> those elements. </li> 
 <li id="li_19CAD7683BCF45278E2991C1EDBC9903"> <b>Case and content sensitivity:</b> The key-values in the file must match the values actually passed in to Audience Manager from your website. </li> 
</ul> 
<p>See DATA TRANSLATION FILE. </p>

 -->

## 2 단계: 데이터 파일 형식

파일 이름과 컨텐츠는 엄격한 지침을 따릅니다. You *must* name and organize data files according to these specifications in this guide. 다음을 참조하십시오.

* [인바운드 데이터 파일에 대한 Amazon S3 이름 요구 사항](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [인바운드 데이터 파일에 대한 FTP 이름 요구 사항](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)
* [인바운드 데이터 파일 컨텐츠: 구문, 변수 및 예제](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## 오프라인 마케팅 활동에 온라인 데이터 사용 가능

오프라인 데이터를 온라인에 가져올 경우에도 오프라인 캠페인에 이 정보를 사용할 수 있습니다. To do this, Audience Manager exports trait and segment information to an [!DNL FTP] or [!DNL Amazon S3] location of your choice. 추가 정보나 지원을 받으려면 파트너 솔루션 관리자에게 문의하십시오.

## 환경

Audience Manager는 파일 드롭다운을 위한 다음 환경을 제공합니다.

<table id="table_A61AA64578944B23B5A7355F2A76E882"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 환경 </th> 
   <th colname="col02" class="entry"> service </th> 
   <th colname="col2" class="entry"> 위치 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <b>프로덕션</b> </td> 
   <td colname="col02"> FTP </td> 
   <td colname="col2"> <p> <code> ftp-in.demdex.com</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col02"> S3 </td> 
   <td colname="col2"> <p> <code> demdex-s2s-clients</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> <b>베타 환경</b> </td> 
   <td colname="col02"> FTP </td> 
   <td colname="col2"> <p><code> sandbox-ftp-in.demdex.com</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col02"> S3 </td> 
   <td colname="col2"> <p> <code> demdex-s 2 s-clients-sandbox-us-east -1</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 기술 읽기

Systems engineers, developers, or technical/implementation teams should review [Batch Data Transfer Process Described](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md#batch-data-transfer-process) and the other articles in this section. 이러한 아티클은 전송 프로토콜, 파일 컨텐츠 및 파일 이름 요구 사항에 대한 세부 사항을 제공합니다.