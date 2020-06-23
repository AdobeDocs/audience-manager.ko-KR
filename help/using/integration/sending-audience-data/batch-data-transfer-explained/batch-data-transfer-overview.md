---
description: 다른 시스템(오프라인)의 데이터를 Audience Manager으로 가져오려는 기술 및 비기술 고객을 위한 개요입니다.
keywords: inbound, batch, batch upload, batch data
seo-description: 다른 시스템(오프라인)의 데이터를 Audience Manager으로 가져오려는 기술 및 비기술 고객을 위한 개요입니다. 이렇게 하려면 Audience Manager에서 일괄 업로드 옵션을 사용합니다.
seo-title: Audience Manager로 배치 데이터 보내기 개요
solution: Audience Manager
title: Audience Manager로 배치 데이터 보내기 개요
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
translation-type: tm+mt
source-git-commit: 9a8c0650d3f00a95a8a1f05c248c21b420e727e0
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 6%

---


# 배치 데이터를 개요로 [!DNL Audience Manager] 보내기 {#send-batch-data-to-audience-manager-overview}

다른 시스템(오프라인)의 데이터를 다른 시스템으로 가져오려는 기술 및 비기술 고객을 위한 개요입니다 [!DNL Audience Manager].

## 장점

다른 시스템의 데이터를 [!DNL Audience Manager] Adobe 시스템을 통해 가치를 이해하고 이전에 수집한 사용자 데이터를 활용할 수 있습니다. 여기에는 구매, 고객 설문 조사, 등록 데이터, 데이터베이스 등에 대한 [!DNL CRM] 정보가 포함됩니다. 각 통합은 자체적인 문제를 제시하지만, 이러한 공통적인 단계를 모두 공유합니다. 이 자료를 검토하여 오프라인 데이터를 온라인 상태로 만드는 데 필요한 노력을 줄일 수 있습니다.

## 1단계: 사용자 ID 동기화

동기화 도중 클라이언트 및 해당 사용자에게 고유 ID를 [!DNL Audience Manager] 할당합니다. 이러한 ID를 각각 [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) [!UICONTROL Unique User ID] 와[!UICONTROL UUID]()라고 합니다. [!DNL Audience Manager] 및 [!UICONTROL DPID] 를 사용하여 사용자를 식별하고 사용자 그룹 [!UICONTROL UUID] , [!UICONTROL traits][!UICONTROL segments]및 보고를 위한 자격을 얻습니다. 또한 데이터 수집 코드([!UICONTROL DIL])는 웹 사이트에서 방문자 데이터를 캡처하기 위해 이러한 ID를 찾습니다. 이 단계가 완료되면 오프라인 보관소에 [!DNL Audience Manager] 각 사용자 레코드에 대한 해당 ID가 포함되어야 합니다.

이 단계에 대한 중요 고려 사항:

* **클라이언트 ID 배치:** [!DNL Audience Manager] 클라이언트 ID가 웹 사이트에서 표시되는 위치를 알고 있어야 합니다(예: 쿠키, Analytics 변수, 페이지 코드 등에 저장되었는지).
* **제외[!DNL PII]:** 사용자 ID에는 개인 식별 정보([!DNL PII])가 없어야 합니다.
* **대/소문자 및 컨텐츠 민감도:** 실시간 데이터 동기화 중, 에 의해 사이트에서 캡처된 사용자 ID는 오프라인 저장소에서 전달된 ID와 일치해야 [!DNL Audience Manager] 합니다. 예를 들어, 오프라인 레코드가 에 대한 정보를 [!DNL User123]보유하고 있지만 사이트에서 해당 ID를 렌더링하면 이 ID를 다른 방문자로 [!DNL USER123][!DNL Audience Manager] 볼 수 있습니다. 따라서 이 방문자에 대한 온라인 정보는 오프라인 데이터베이스의 해당 레코드와 연결할 수 없습니다. ID가 정확히 일치해야 합니다.

See [ID Synchronization for Inbound Data Transfers](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

## 2단계: 데이터 파일 형식

파일 이름과 내용은 엄격한 지침을 따릅니다. 이 안내서의 이러한 사양에 따라 데이터 파일의 이름을 지정하고 구성해야 *합니다* . 다음을 참조하십시오.

* [인바운드 데이터 파일에 대한 Amazon S3 이름 요구 사항](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [인바운드 데이터 파일 내용: 구문, 변수 및 예제](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## 오프라인 마케팅 활동에 온라인 데이터 사용 가능

오프라인 데이터를 온라인 상태로 전환하더라도 오프라인 캠페인에 이 정보를 사용할 수 있습니다. 이렇게 하려면 트레이트 및 세그먼트 정보를 원하는 [!DNL Audience Manager] 위치 또는 [!DNL FTP] [!DNL Amazon S3] 위치로 내보냅니다. 자세한 정보나 지원은 파트너 솔루션 관리자에게 문의하십시오.

## 환경

[!DNL Audience Manager] 파일 드롭다운에 대해 다음 환경을 제공합니다.

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

시스템 엔지니어, 개발자 또는 기술/구현 팀은 [일괄 데이터 전송 처리 설명](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) 및 이 섹션의 기타 문서를 검토해야 합니다. 이 문서에서는 전송 프로토콜, 파일 콘텐트 및 파일 이름 요구 사항에 대한 세부 정보를 제공합니다.
