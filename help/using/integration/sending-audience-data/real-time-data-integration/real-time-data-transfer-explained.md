---
description: Audience Manager이 타사 컨텐츠 공급자와 실시간 데이터 전송을 수행하는 방법에 대한 일반적인 개요입니다.
seo-description: Audience Manager이 타사 컨텐츠 공급자와 실시간 데이터 전송을 수행하는 방법에 대한 일반적인 개요입니다.
seo-title: 실시간 데이터 전송 프로세스 설명
solution: Audience Manager
title: 실시간 데이터 전송 프로세스 설명
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: 인바운드 데이터 전송
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 1%

---


# 실시간 데이터 전송 프로세스 설명{#real-time-data-transfer-process-described}

Audience Manager이 타사 컨텐츠 공급자와 실시간 데이터 전송을 수행하는 방법에 대한 일반적인 개요입니다.

<!-- real-time-data-transfer-explained.xml -->

## 실시간 데이터 전송

실시간 데이터 전송은 사용자가 사이트를 방문하거나 사이트에서 작업을 수행할 때 세그먼트 ID를 전송하고 받습니다. 일반적으로 동기 데이터 전송은 인벤토리를 탐색할 때 사용자를 즉시 분류하거나 자격을 부여해야 할 때 유용합니다.

## 데이터 통합 단계

실시간 데이터 통합 프로세스는 다음과 같이 작동합니다.

1. 사용자가 Audience Manager 코드를 포함하는 고객의 사이트를 방문합니다.
1. Audience Manager은 iframe을 로드하고 [!UICONTROL Data Collection Server]( [!DNL DCS])를 호출합니다.
1. [!DNL DCS] 은 타사 서버를 호출하여(실시간으로) 공급업체가 사용자에 대한 세그먼트 정보를 가지고 있는지 확인합니다.
1. 컨텐츠 공급자는 해당 사용자에 대한 Audience Manager 정보를 반환합니다.
1. Audience Manager은 이 세그먼트 정보를 수신하여 새로운 트레이트 및 세그먼트를 타깃팅하고 작성할 수 있도록 합니다.

![](assets/rt_reduce70.png)