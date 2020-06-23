---
description: Audience Manager이 타사 공급업체와의 비동기 일괄 데이터 교환을 수행하는 방법에 대한 일반적인 개요입니다.
seo-description: Audience Manager이 타사 공급업체와의 비동기 일괄 데이터 교환을 수행하는 방법에 대한 일반적인 개요입니다.
seo-title: 배치 데이터 전송 프로세스 설명
solution: Audience Manager
title: 배치 데이터 전송 프로세스 설명
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
translation-type: tm+mt
source-git-commit: 9a8c0650d3f00a95a8a1f05c248c21b420e727e0
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 7%

---


# 배치 데이터 전송 프로세스 설명 {#batch-data-transfer-process-described}

타사 공급업체와의 비동기식 일괄 처리 데이터 교환을 수행하는 방법에 대한 일반적인 개요입니다. [!DNL Audience Manager]

## 일괄 데이터 통합

<!-- c_async.xml -->

일괄 데이터 통합 프로세스는 서버에 있는 방문자 정보를 저장하고 해당 자료를 주기적으로 공급자가 보낸 데이터와 동기화합니다. 비동기 데이터 전송 프로세스는 다음과 같은 경우에 유용합니다.

* 즉각적인 데이터 양도는 필요하지 않습니다.
* 데이터를 수집하여 세분화된 대규모 사용자 풀을 작성합니다.
* 브라우저의 데이터 불일치 및 `HTTP` 호출을 줄이고자 합니다.

![](assets/s2s_70.png)

## 데이터 통합 단계

1. 사용자가 고객 사이트를 방문합니다.
1. [!DNL Audience Manager] 그리고 타사 데이터 공급자는 방문자에게 고유한 ID를 지정합니다(일반적으로 쿠키가 있음).
1. [!DNL Audience Manager] 방문자 ID와 일치하도록 타사 데이터 공급자를 호출합니다.
1. 일반적으로 일별 간격으로 예약된 요청은 방문자 세그먼트 데이터를 [!DNL Audience Manager] 타사 데이터 공급자와 교환합니다.
1. 인바운드 [!UICONTROL Server-to-Server] 파일이 처리될 때마다 이메일은 파트너 솔루션에 전송되고, 구성된 경우 파트너에게 전송됩니다. 자세한 내용은 인바운드 [처리 후 파트너에게 메시지 샘플을 참조하십시오](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).
