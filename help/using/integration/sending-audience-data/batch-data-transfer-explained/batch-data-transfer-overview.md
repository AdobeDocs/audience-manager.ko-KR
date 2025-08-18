---
description: 다른 시스템(오프라인)의 데이터를 Audience Manager으로 가져오려는 기술 및 비기술 고객을 위한 개요입니다.
keywords: 인바운드, 배치, 배치 업로드, 배치 데이터
seo-description: An overview for technical and non-technical customers who want to bring data from other systems (offline) into Audience Manager. To do so, use the batch upload option in Audience Manager.
seo-title: Send Batch Data to Audience Manager Overview
solution: Audience Manager
title: Audience Manager으로 배치 데이터 보내기 개요
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: Inbound Data Transfers
exl-id: ba95537e-30c9-4546-9456-55f46dbe29ff
source-git-commit: f02e6bcfb7ff3560d9624c3dce7ff065a3a75748
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 4%

---

# [!DNL Audience Manager] 개요에 일괄 처리 데이터 보내기 {#send-batch-data-to-audience-manager-overview}

다른 시스템(오프라인)의 데이터를 [!DNL Audience Manager]&#x200B;(으)로 가져오려는 기술 및 비기술 고객을 위한 개요입니다.

## 장점

[!DNL Audience Manager]에서 다른 시스템의 데이터를 사용할 수 있도록 설정할 수 있습니다. 당사의 시스템은 가치를 잠금 해제하고 이전에 수집한 사용자 데이터를 활용하는 데 도움이 됩니다. 여기에는 구매, 고객 설문 조사, 등록 데이터, [!DNL CRM] 데이터베이스 등에 대한 정보가 포함됩니다. 각 통합은 고유한 과제를 제시하지만 이러한 일반적인 단계를 모두 공유합니다. 오프라인 데이터를 온라인으로 전환하는 데 필요한 수고를 줄이려면 이 자료를 검토하십시오.

## 1단계: 사용자 ID 동기화

동기화 중에 [!DNL Audience Manager]은(는) 클라이언트와 해당 사용자에게 고유 ID를 할당합니다. 이러한 ID를 각각 [!UICONTROL Data Provider ID]&#x200B;([!UICONTROL DPID]) 및 [!UICONTROL Unique User ID]&#x200B;([!UICONTROL UUID])이라고 합니다. [!DNL Audience Manager]은(는) [!UICONTROL DPID] 및 [!UICONTROL UUID]을(를) 사용하여 사용자를 식별하고 [!UICONTROL traits], [!UICONTROL segments], 대상 그룹 및 보고를 위한 자격을 부여합니다. 또한 데이터 수집 코드([!UICONTROL DIL])는 웹 사이트에서 방문자 데이터를 캡처하기 위해 이러한 ID를 찾습니다. 이 단계를 완료하면 [!DNL Audience Manager] 및 오프라인 리포지토리에는 각 사용자 레코드에 대한 해당 ID가 포함되어야 합니다.

이 단계에 대한 중요 고려 사항:

* **클라이언트 ID 배치:** [!DNL Audience Manager]에서는 클라이언트 ID가 웹 사이트에서 표시되는 위치를 알아야 합니다(예: 쿠키, Analytics 변수, 페이지 코드 등에 저장됨).
* **제외 [!DNL PII]:** 사용자 ID에는 개인 식별 정보([!DNL PII])가 포함되어서는 안 됩니다.
* **대/소문자 및 콘텐츠 민감도:** 실시간 데이터 동기화 중에 [!DNL Audience Manager]이(가) 사이트에서 캡처한 사용자 ID는 오프라인 리포지토리에서 전달된 ID와 일치해야 합니다. 예를 들어 오프라인 레코드에 [!DNL User123]에 대한 정보가 있지만 사이트에서 해당 ID를 [!DNL USER123]&#x200B;(으)로 렌더링하는 경우 [!DNL Audience Manager]에서 이러한 ID를 다른 방문자로 봅니다. 따라서 이 방문자의 온라인 정보는 오프라인 데이터베이스의 해당 레코드와 연결할 수 없습니다. ID는 정확히 일치해야 합니다.

인바운드 데이터 전송을 위한 [ID 동기화](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md)를 참조하십시오.

## 2단계: 데이터 파일 형식

파일 이름 및 컨텐츠는 엄격한 지침을 따릅니다. 이 안내서의 사양에 따라 데이터 파일의 이름을 *반드시*&#x200B;해야 합니다. 다음을 참조하십시오.

* [인바운드 데이터 파일에 대한 Amazon S3 이름 요구 사항](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [인바운드 데이터 파일 내용: 구문, 변수 및 예](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## 오프라인 마케팅 활동에 온라인 데이터 사용 가능

오프라인 데이터를 온라인으로 가져올 때 오프라인 캠페인에 이 정보를 계속 사용할 수 있습니다. 이렇게 하려면 [!DNL Audience Manager]에서 트레이트 및 세그먼트 정보를 선택한 [!DNL FTP] 또는 [!DNL Amazon S3] 위치로 내보냅니다. 자세한 내용 또는 지원이 필요한 경우 파트너 솔루션 관리자에게 문의하십시오.

## 환경

[!DNL Audience Manager]은(는) 파일 드롭오프에 대해 다음 환경을 제공합니다.

| 환경 | 서비스 | 위치 |
|---------|----------|---------|
| 프로덕션 | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-clients</li><li>ftp-in.demdex.com</li></ul> |
| Beta 환경 | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-clients-sandbox-us-east-1</li><li>sandbox-ftp-in.demdex.com</li></ul> |

{style="table-layout:auto"}

## 추가 기술 자료

시스템 엔지니어, 개발자 또는 기술/구현 팀은 [설명된 일괄 데이터 전송 프로세스](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) 및 이 섹션의 다른 문서를 검토해야 합니다. 이 문서에서는 전송 프로토콜, 파일 컨텐츠 및 파일 이름 요구 사항에 대해 자세히 설명합니다.
