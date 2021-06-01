---
description: Audience Manager이 타사 공급업체와 비동기 배치 데이터 교환을 수행하는 방법에 대한 일반적인 개요입니다.
seo-description: Audience Manager이 타사 공급업체와 비동기 배치 데이터 교환을 수행하는 방법에 대한 일반적인 개요입니다.
seo-title: 배치 데이터 전송 프로세스 설명
solution: Audience Manager
title: 배치 데이터 전송 프로세스 설명
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
feature: 인바운드 데이터 전송
exl-id: e02dcc9a-4010-4c01-bd6b-ad04b8029f18
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 8%

---

# 배치 데이터 전송 프로세스 설명 {#batch-data-transfer-process-described}

[!DNL Audience Manager] 이 타사 공급업체와 비동기 배치 데이터 교환을 수행하는 방법에 대한 일반적인 개요입니다.

## 배치 데이터 통합

<!-- c_async.xml -->

배치 데이터 통합 프로세스는 서버에 대한 방문자 정보를 저장하고 정기적으로 공급자가 보낸 데이터와 해당 데이터를 동기화합니다. 비동기 데이터 전송 프로세스는 다음과 같은 경우에 유용합니다.

* 즉각적인 데이터 전송이 필요하지 않습니다.
* 데이터를 수집하여 세그먼트화된 사용자의 대규모 풀을 구축합니다.
* 브라우저에서 데이터 불일치 및 `HTTP` 호출을 줄이려고 합니다.

![](assets/s2s_70.png)

## 데이터 통합 단계

1. 사용자가 고객 사이트를 방문합니다.
1. [!DNL Audience Manager] 및 타사 데이터 공급자는 방문자에게 고유 ID(일반적으로 쿠키와 함께)를 지정합니다.
1. [!DNL Audience Manager] 방문자 ID와 일치하도록 타사 데이터 공급자를 호출합니다.
1. 예약된 요청은 보통 일별 간격에 따라 [!DNL Audience Manager] 과 타사 데이터 공급자 간에 방문자 세그먼트 데이터를 교환합니다.
1. 인바운드 [!UICONTROL Server-to-Server] 파일이 처리될 때마다 Partner Solutions와 Partner Solutions로 Recept가 전송되는 경우 Recept가 전송됩니다. 자세한 내용은 인바운드 처리 후 파트너에 대한 샘플 메시지](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md)를 참조하십시오.[
