---
description: 다른 시스템(오프라인)의 데이터를 Audience Manager으로 가져오려는 기술 및 비기술 고객을 위한 개요입니다.
keywords: 인바운드, 일괄 처리, 일괄 업로드, 배치 데이터
seo-description: 다른 시스템(오프라인)의 데이터를 Audience Manager으로 가져오려는 기술 및 비기술 고객을 위한 개요입니다. 이렇게 하려면 Audience Manager에서 일괄 업로드 옵션을 사용합니다.
seo-title: Audience Manager로 배치 데이터 보내기 개요
solution: Audience Manager
title: Audience Manager로 배치 데이터 보내기 개요
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: Inbound Data Transfers
exl-id: ba95537e-30c9-4546-9456-55f46dbe29ff
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 7%

---

# 배치 데이터를 [!DNL Audience Manager] 개요 {#send-batch-data-to-audience-manager-overview}로 보내기

다른 시스템(오프라인)의 데이터를 [!DNL Audience Manager]으로 가져오려는 기술 및 비기술 고객을 위한 개요입니다.

## 장점

[!DNL Audience Manager]에서 다른 시스템의 데이터를 사용할 수 있게 만들 수 있습니다. Adobe 시스템을 사용하면 가치를 이해하고 이전에 수집한 사용자 데이터를 활용할 수 있습니다. 여기에는 구매, 고객 설문 조사, 등록 데이터, [!DNL CRM] 데이터베이스 등에 대한 정보가 포함됩니다. 각 통합은 자체적인 문제를 제시하지만 이러한 공통 단계를 모두 공유합니다. 이 자료를 검토하여 오프라인 데이터를 온라인 상태로 만드는 데 필요한 노력을 줄일 수 있습니다.

## 1단계:사용자 ID 동기화

동기화 도중 [!DNL Audience Manager]은 클라이언트 및 해당 사용자에게 고유한 ID를 할당합니다. 이러한 ID는 각각 [!UICONTROL Data Provider ID]([!UICONTROL DPID]) 및 [!UICONTROL Unique User ID]([!UICONTROL UUID])로 알려져 있습니다. [!DNL Audience Manager] 를  [!UICONTROL DPID] 사용하여 사용자 [!UICONTROL UUID] 를 식별하고  [!UICONTROL traits],  [!UICONTROL segments]대상 그룹 및 보고를 위한 자격을 얻습니다. 또한 데이터 수집 코드([!UICONTROL DIL])는 웹 사이트에서 방문자 데이터를 캡처하기 위해 이러한 ID를 찾습니다. 이 단계가 완료되면 [!DNL Audience Manager] 및 오프라인 리포지토리는 각 사용자 레코드에 대한 해당 ID를 포함해야 합니다.

이 단계에 대한 중요 고려 사항:

* **클라이언트 ID 배치: 클라이언트 ID가 웹 사이트에서 표시되는 위치를 알고** [!DNL Audience Manager] 있어야 합니다(예: 쿠키, Analytics 변수, 페이지 코드 등에서 저장됨).
* **제외  [!DNL PII]:** 사용자 ID에는 개인 식별 정보([!DNL PII])가 포함되어 있지 않아야 합니다.
* **대/소문자 및 컨텐츠 민감도:** 실시간 데이터 동기화 시, 에 의해 사이트에서 캡처된 사용자 ID는 오프라인 저장소에서 전달된 ID와  [!DNL Audience Manager] 일치해야 합니다. 예를 들어 오프라인 레코드에 [!DNL User123]에 대한 정보가 있지만 사이트가 해당 ID를 [!DNL USER123](으)로 렌더링하는 경우 [!DNL Audience Manager]에서는 이를 다른 방문자로 인식합니다. 따라서 이 방문자에 대한 온라인 정보는 오프라인 데이터베이스의 해당 레코드와 연결할 수 없습니다. ID는 정확히 일치해야 합니다.

인바운드 데이터 전송](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md)에 대한 [ID 동기화를 참조하십시오.

## 2단계:데이터 파일 형식

파일 이름과 내용은 엄격한 지침을 따릅니다. 이 안내서의 이러한 사양에 따라 *의 이름을 지정하고 데이터 파일을 구성해야 합니다.* 다음을 참조하십시오.

* [인바운드 데이터 파일에 대한 Amazon S3 이름 요구 사항](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [인바운드 데이터 파일 내용:구문, 변수 및 예](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## 오프라인 마케팅 활동에 온라인 데이터 사용 가능

오프라인 데이터를 온라인으로 가져올 경우에도 오프라인 캠페인에 이 정보를 사용할 수 있습니다. 이렇게 하려면 [!DNL Audience Manager]에서 트레이트 및 세그먼트 정보를 원하는 [!DNL FTP] 또는 [!DNL Amazon S3] 위치로 내보냅니다. 추가 정보 또는 지원을 받으려면 파트너 솔루션 관리자에게 문의하십시오.

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

시스템 엔지니어, 개발자 또는 기술/구현 팀은 [Batch Data Transfer Process Described](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) 및 이 섹션의 기타 문서를 검토해야 합니다. 이 문서에서는 전송 프로토콜, 파일 콘텐트 및 파일 이름 요구 사항에 대한 세부 정보를 제공합니다.
