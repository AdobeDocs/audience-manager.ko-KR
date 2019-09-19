---
description: Audience Manager가 타사 공급업체와 비동기 일괄 데이터 교환을 수행하는 방법에 대한 일반적인 개요입니다.
seo-description: Audience Manager가 타사 공급업체와 비동기 일괄 데이터 교환을 수행하는 방법에 대한 일반적인 개요입니다.
seo-title: 배치 데이터 전송 프로세스 설명
solution: Audience Manager
title: 배치 데이터 전송 프로세스 설명
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 배치 데이터 전송 프로세스 설명 {#batch-data-transfer-process-described}

Audience Manager가 타사 공급업체와 비동기 일괄 데이터 교환을 수행하는 방법에 대한 일반적인 개요입니다.

## 일괄 데이터 통합

<!-- c_async.xml -->

일괄 데이터 통합 프로세스는 서버에 방문자 정보를 저장하고 정기적으로 공급자가 전송하는 데이터와 해당 자료를 동기화합니다. 비동기 데이터 전송 프로세스는 다음과 같은 경우에 유용합니다.

* 즉각적인 데이터 전송이 필요하지 않습니다.
* 데이터를 수집하여 세그먼트화된 사용자의 대규모 풀을 작성합니다.
* 브라우저에서 데이터 불일치 및 `HTTP` 호출을 줄이고자 합니다.

![](assets/s2s_70.png)

## 데이터 통합 단계

1. 사용자가 고객 사이트를 방문합니다.
1. Audience Manager와 타사 데이터 공급자는 방문자에게 고유 ID를 할당합니다(일반적으로 쿠키와 함께).
1. Audience Manager는 방문자 ID와 일치하도록 타사 데이터 공급자를 호출합니다.
1. 예약된 요청은 일반적으로 일별 간격으로 Audience Manager와 타사 데이터 공급자 간에 방문자 세그먼트 데이터를 교환합니다.
1. 인바운드 [!UICONTROL Server-to-Server] 파일이 처리될 때마다 이메일이 파트너 솔루션에 전송되고, 구성된 경우 파트너에게 전송됩니다. 자세한 내용은 인바운드 처리 [후 파트너에게 보내는 샘플 메시지를 참조하십시오](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).