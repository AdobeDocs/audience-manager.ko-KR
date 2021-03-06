---
description: 다른 시스템(오프라인)의 데이터를 Audience Manager으로 가져오려는 기술 및 비기술 고객을 위한 개요입니다.
keywords: 인바운드, 배치, 배치 업로드, 배치 데이터
seo-description: An overview for technical and non-technical customers who want to bring data from other systems (offline) into Audience Manager. To do so, use the batch upload option in Audience Manager.
seo-title: Send Batch Data to Audience Manager Overview
solution: Audience Manager
title: Audience Manager로 배치 데이터 보내기 개요
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: Inbound Data Transfers
exl-id: ba95537e-30c9-4546-9456-55f46dbe29ff
source-git-commit: f02e6bcfb7ff3560d9624c3dce7ff065a3a75748
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 6%

---

# 배치 데이터를에 보내기 [!DNL Audience Manager] 개요 {#send-batch-data-to-audience-manager-overview}

다른 시스템(오프라인)에서 로 데이터를 가져오려는 기술 및 비기술 고객을 위한 개요입니다 [!DNL Audience Manager].

## 장점

다른 시스템의 데이터를 [!DNL Audience Manager]. Adobe 시스템을 통해 가치를 잠금 해제하고 이전에 수집한 사용자 데이터를 활용할 수 있습니다. 여기에는 구매, 고객 설문 조사, 등록 데이터, [!DNL CRM] 데이터베이스 등 각 통합은 자체 과제를 제시하는 반면, 이러한 공통적인 단계를 모두 공유합니다. 오프라인 데이터를 온라인으로 전환하는 데 필요한 노력을 줄이려면 이 자료를 검토하십시오.

## 1단계: 사용자 ID 동기화

동기화 중에 [!DNL Audience Manager] 클라이언트 및 해당 사용자에게 고유 ID를 할당합니다. 이러한 ID를 [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) 및 [!UICONTROL Unique User ID] ([!UICONTROL UUID]) 내의 아무 곳에나 삽입할 수 있습니다. [!DNL Audience Manager] 사용 [!UICONTROL DPID] 및 [!UICONTROL UUID] 사용자를 식별하고 [!UICONTROL traits], [!UICONTROL segments], 대상 그룹 및 를 사용하여 데이터를 분류할 수 있습니다. 또한 데이터 수집 코드([!UICONTROL DIL])은 웹 사이트에서 방문자 데이터를 캡처할 이러한 ID를 찾습니다. 이 단계가 완료되면, [!DNL Audience Manager] 오프라인 저장소에는 각 사용자 레코드에 대한 해당 ID가 포함되어야 합니다.

이 단계에 대한 중요 고려 사항:

* **클라이언트 ID 배치:** [!DNL Audience Manager] 는 웹 사이트에 클라이언트 ID가 표시되는 위치(예: 쿠키, Analytics 변수, 페이지 코드 등에 저장되었는지)를 알고 있어야 합니다.
* **제외 [!DNL PII]:** 사용자 ID에는 개인 식별 정보([!DNL PII]).
* **대/소문자 및 컨텐츠 민감도:** 실시간 데이터 동기화 중에 [!DNL Audience Manager] 는 오프라인 저장소에서 전달된 ID에 해당해야 합니다. 예를 들어 오프라인 레코드에 [!DNL User123]로 설정되지만 사이트에서 해당 ID를 [!DNL USER123], [!DNL Audience Manager] 는 이것을 다른 방문자로 봅니다. 따라서 이 방문자에 대한 온라인 정보는 오프라인 데이터베이스의 해당 레코드와 연결할 수 없습니다. ID가 정확히 일치해야 합니다.

자세한 내용은 [인바운드 데이터 전송을 위한 ID 동기화](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

## 2단계: 데이터 파일 형식

파일 이름 및 컨텐츠는 엄격한 지침을 따릅니다. 사용자 *반드시* 이 안내서의 이러한 사양에 따라 데이터 파일의 이름을 지정하고 구성합니다. 다음을 참조하십시오.

* [인바운드 데이터 파일에 대한 Amazon S3 이름 요구 사항](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [인바운드 데이터 파일 내용: 구문, 변수 및 예](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## 오프라인 마케팅 활동에 온라인 데이터를 사용할 수 있습니다

오프라인 데이터를 온라인으로 가져올 때에도 오프라인 캠페인에 이 정보를 사용할 수 있습니다. 이렇게 하려면 [!DNL Audience Manager] 트레이트 및 세그먼트 정보를 로 내보내기 [!DNL FTP] 또는 [!DNL Amazon S3] 선택한 위치입니다. 추가 정보 또는 지원이 필요하면 파트너 솔루션 관리자에게 문의하십시오.

## 환경

[!DNL Audience Manager] 에서는 파일 드롭오프에 대해 다음 환경을 제공합니다.

| 환경 | 서비스 | 위치 |
|---------|----------|---------|
| 프로덕션 | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-clients</li><li>ftp-in.demdex.com</li></ul> |
| 베타 환경 | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-clients-sandbox-us-east-1</li><li>sandbox-ftp-in.demdex.com</li></ul> |

{style=&quot;table-layout:auto&quot;}

## 추가 기술 읽기

시스템 엔지니어, 개발자 또는 기술/구현 팀이 검토해야 합니다. [배치 데이터 전송 프로세스 설명](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) 및 이 섹션의 다른 기사. 이러한 문서는 전송 프로토콜, 파일 콘텐츠 및 파일 이름 요구 사항에 대한 세부 정보를 제공합니다.
