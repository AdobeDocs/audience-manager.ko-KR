---
description: 다른 시스템(오프라인)의 데이터를 Audience Manager로 가져오려는 기술 및 비기술 고객을 위한 개요입니다.
keywords: 인바운드, 배치, 배치 업로드, 배치 데이터
seo-description: 다른 시스템(오프라인)의 데이터를 Audience Manager로 가져오려는 기술 및 비기술 고객을 위한 개요입니다. 이렇게 하려면 Audience Manager에서 일괄 업로드 옵션을 사용합니다.
seo-title: Audience Manager로 배치 데이터 보내기 개요
solution: Audience Manager
title: Audience Manager로 배치 데이터 보내기 개요
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
translation-type: tm+mt
source-git-commit: 2e3adc8f0b2fe6efd9ca57f1d763ee4476d2edee

---


# Audience Manager로 배치 데이터 보내기 개요{#send-batch-data-to-audience-manager-overview}

다른 시스템(오프라인)의 데이터를 Audience Manager로 가져오려는 기술 및 비기술 고객을 위한 개요입니다.

## 장점

<!-- c_offline_to_online.xml -->

Audience Manager에서 다른 시스템의 데이터를 사용할 수 있도록 만들 수 있습니다. Adobe 시스템을 통해 가치를 확보하고 이전에 수집한 사용자 데이터를 활용할 수 있습니다. 여기에는 구매, 고객 설문 조사, 등록 데이터, 데이터베이스 등에 대한 정보가 [!DNL CRM] 포함됩니다. 각 통합은 자체적인 문제점을 제시하지만, 이러한 공통적인 단계를 모두 공유합니다. 이 자료를 검토하여 오프라인 데이터를 온라인 상태로 만드는 데 필요한 노력을 줄일 수 있습니다.

## 1단계:사용자 ID 동기화

동기화 중에 Audience Manager는 클라이언트 및 해당 사용자에게 고유 ID를 할당합니다. 이러한 ID를 [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) 및 [!UICONTROL Unique User ID] ([!UICONTROL UUID])라고 합니다. Audience Manager는 [!UICONTROL DPID] [!UICONTROL UUID] 및 를 사용하여 사용자를 식별하고 트레이트, 세그먼트, 대상 그룹 및 보고에 대한 자격을 부여합니다. 또한 데이터 수집 코드([!UICONTROL DIL])는 웹 사이트에서 방문자 데이터를 캡처하기 위해 이러한 ID를 찾습니다. 이 단계가 완료되면 Audience Manager 및 오프라인 보관소에 각 사용자 레코드에 대한 해당 ID가 포함되어야 합니다.

이 단계에 대한 중요 고려 사항:

* **** 클라이언트 ID 배치:Audience Manager는 웹 사이트에서 클라이언트 ID가 표시되는 위치를 알아야 합니다(예: 쿠키, Analytics 변수, 페이지 코드 등).
* **[!DNL PII]제외**:사용자 ID는 개인 식별 정보([!DNL PII])를 포함하지 않아야 합니다.
* **** 대/소문자 및 컨텐츠 민감도:실시간 데이터 동기화 동안 Audience Manager가 사이트에서 캡처한 사용자 ID는 오프라인 저장소에서 전달된 ID와 일치해야 합니다. 예를 들어 오프라인 레코드가 에 대한 정보를 [!DNL User123]보유하고 있지만 사이트에서 해당 ID를 렌더링하면 Audience Manager [!DNL USER123]는 이를 다른 방문자로 봅니다. 따라서 이 방문자에 대한 온라인 정보는 오프라인 데이터베이스의 해당 레코드와 연결할 수 없습니다. ID가 정확히 일치해야 합니다.

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

## 2단계:데이터 파일 형식

파일 이름과 내용은 엄격한 지침을 따릅니다. 이 안내서의 사양에 따라 데이터 파일의 이름을 지정하고 *구성해야* 합니다. 다음을 참조하십시오.

* [인바운드 데이터 파일에 대한 Amazon S3 이름 요구 사항](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [인바운드 데이터 파일 내용:구문, 변수 및 예제](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## 오프라인 마케팅 활동에 온라인 데이터 사용 가능

오프라인 데이터를 온라인으로 가져올 때 여전히 오프라인 캠페인에 이 정보를 사용할 수 있습니다. 이를 위해 Audience Manager는 트레이트 및 세그먼트 정보를 원하는 [!DNL FTP] 위치 또는 [!DNL Amazon S3] 위치로 내보냅니다. 자세한 내용 또는 지원은 파트너 솔루션 관리자에게 문의하십시오.

## 환경

Audience Manager는 파일 드롭다운에 대해 다음 환경을 제공합니다.

<table id="table_A61AA64578944B23B5A7355F2A76E882"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 환경 </th> 
   <th colname="col02" class="entry"> 서비스 </th> 
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
   <td colname="col2"> <p> <code> demdex-s2s-clients-sandbox-us-east-1</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 추가 기술 자료

시스템 엔지니어, 개발자 또는 기술/구현 팀은 [본](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) 섹션의 일괄 데이터 전송 프로세스 및 기타 문서를 검토해야 합니다. 이 문서에서는 전송 프로토콜, 파일 콘텐트 및 파일 이름 요구 사항에 대한 세부 정보를 제공합니다.