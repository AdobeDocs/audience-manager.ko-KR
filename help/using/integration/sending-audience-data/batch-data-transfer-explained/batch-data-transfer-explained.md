---
description: Audience Manager가 타사 공급업체와의 비동기 일괄 데이터 교환을 수행하는 방법에 대한 일반적인 개요입니다.
seo-description: Audience Manager가 타사 공급업체와의 비동기 일괄 데이터 교환을 수행하는 방법에 대한 일반적인 개요입니다.
seo-title: 일괄 데이터 전송 프로세스 설명
solution: Audience Manager
title: 일괄 데이터 전송 프로세스 설명
uuid: A 9 EEE 940-151 C -44 F 8-9 FE 9-8 AB 47 D 8 FA 45 C
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Batch Data Transfer Process Described {#batch-data-transfer-process-described}

Audience Manager가 타사 공급업체와의 비동기 일괄 데이터 교환을 수행하는 방법에 대한 일반적인 개요입니다.

## 일괄 데이터 통합

<!-- c_async.xml -->

일괄 데이터 통합 프로세스는 방문자의 정보를 서버에 저장하고, 정기적으로 공급자가 전송한 데이터와 해당 자료를 동기화합니다. 비동기 데이터 전송 프로세스는 다음과 같은 경우에 유용합니다.

* 즉각적인 데이터 전송은 필요하지 않습니다.
* 데이터를 수집하여 세그먼트화된 대규모 사용자 풀 만들기
* You want to reduce data discrepancies and `HTTP` calls from the browser.

![](assets/s2s_70.png)

## 데이터 통합 단계

1. 사용자가 고객 사이트를 방문합니다.
1. Audience Manager와 타사 데이터 공급자는 방문자에게 고유 ID (일반적으로 쿠키와 함께) 를 할당합니다.
1. Audience Manager는 방문자 ID와 일치하도록 타사 데이터 공급자를 호출합니다.
1. 일반적으로 일별 간격으로 예약된 요청은 Audience Manager와 타사 데이터 공급자 간에 방문자 세그먼트 데이터를 교환합니다.
1. Whenever an inbound [!UICONTROL Server-to-Server] file is processed, a receipt is sent via email to partner solutions and, if configured, to the partner. For more information, see [Sample Message to Partners after Inbound Processing](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).