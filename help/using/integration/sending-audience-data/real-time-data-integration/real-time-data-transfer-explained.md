---
description: Audience Manager가 타사 컨텐츠 제공업체를 통해 실시간 데이터 전송을 수행하는 방법에 대한 일반적인 개요입니다.
seo-description: Audience Manager가 타사 컨텐츠 제공업체를 통해 실시간 데이터 전송을 수행하는 방법에 대한 일반적인 개요입니다.
seo-title: 실시간 데이터 전송 프로세스 설명
solution: Audience Manager
title: 실시간 데이터 전송 프로세스 설명
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
translation-type: tm+mt
source-git-commit: ea95df8531c00c183f22b09a4a78fc6b35ee279d

---


# 실시간 데이터 전송 프로세스 설명{#real-time-data-transfer-process-described}

Audience Manager가 타사 컨텐츠 제공업체를 통해 실시간 데이터 전송을 수행하는 방법에 대한 일반적인 개요입니다.

<!-- real-time-data-transfer-explained.xml -->

## 실시간 데이터 전송

실시간 데이터 전송은 사용자가 사이트를 방문하거나 조치를 취할 때 세그먼트 ID를 보내고 받습니다. 일반적으로 동기식 데이터 전송은 인벤토리를 탐색하면서 사용자를 즉시 분류하거나 자격을 부여해야 할 때 유용합니다.

## 데이터 통합 단계

실시간 데이터 통합 프로세스는 다음과 같습니다.

1. 사용자가 Audience Manager 코드가 들어 있는 고객 사이트를 방문합니다.
1. Audience Manager는 iframe을 로드하고 [!UICONTROL Data Collection Server] ( [!UICONTROL DCS])을 호출합니다.
1. 타사 서버를 [!UICONTROL DCS] (실시간으로) 호출하여 공급업체가 사용자에 대한 세그먼트 정보를 가지고 있는지 확인합니다.
1. 컨텐츠 제공자는 해당 사용자에 대한 세그먼트 정보를 Audience Manager에 반환합니다.
1. Audience Manager는 이 세그먼트 정보를 수신하여 이를 타깃팅하고 새 트레이트와 세그먼트를 만들 수 있도록 합니다.

![](assets/rt_reduce70.png)