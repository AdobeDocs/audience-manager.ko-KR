---
description: Audience Manager이 타사 공급업체와 비동기 배치 데이터 교환을 수행하는 방법에 대한 일반적인 개요입니다.
seo-description: A general overview of how Audience Manager performs an asynchronous batch data exchange with a third-party vendor.
seo-title: Batch Data Transfer Process Described
solution: Audience Manager
title: 배치 데이터 전송 프로세스 설명
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
feature: Inbound Data Transfers
exl-id: e02dcc9a-4010-4c01-bd6b-ad04b8029f18
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 5%

---

# 배치 데이터 전송 프로세스 설명 {#batch-data-transfer-process-described}

방법에 대한 일반적인 개요 [!DNL Audience Manager] 타사 공급업체와 비동기 일괄 데이터 교환을 수행합니다.

## 일괄 데이터 통합

<!-- c_async.xml -->

배치 데이터 통합 프로세스는 서버에 방문자 정보를 저장하고, 정기적으로 공급자가 보낸 데이터와 해당 자료를 동기화합니다. 비동기 데이터 전송 프로세스는 다음과 같은 경우에 유용합니다.

* 즉각적인 데이터 전송은 필요하지 않습니다.
* 데이터를 수집하여 세그먼트화된 사용자의 대규모 풀 구축
* 데이터 불일치를 줄이고 `HTTP` 브라우저에서 를 호출합니다.

![](assets/s2s_70.png)

## 데이터 통합 단계

1. 사용자가 고객 사이트를 방문하고
1. [!DNL Audience Manager] 및 타사 데이터 공급자는 방문자에게 고유 ID(일반적으로 쿠키와 함께)를 할당합니다.
1. [!DNL Audience Manager] 은 방문자 ID와 일치하도록 타사 데이터 공급자를 호출합니다.
1. 예약된 요청(일반적으로 일별 간격)은 방문자 세그먼트 데이터를 [!DNL Audience Manager] 및 타사 데이터 공급자입니다.
1. 인바운드 때마다 [!UICONTROL Server-to-Server] 파일이 처리되고, 전자 메일을 통해 파트너 솔루션으로 영수증이 전송되며, 구성된 경우 파트너에게 전송됩니다. 자세한 내용은 [인바운드 처리 후 파트너에 대한 샘플 메시지](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).
