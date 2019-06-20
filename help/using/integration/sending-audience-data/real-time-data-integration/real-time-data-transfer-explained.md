---
description: Audience Manager가 타사 컨텐츠 제공업체를 통해 실시간 데이터 전송을 수행하는 방법에 대한 일반적인 개요입니다.
seo-description: Audience Manager가 타사 컨텐츠 제공업체를 통해 실시간 데이터 전송을 수행하는 방법에 대한 일반적인 개요입니다.
seo-title: 실시간 데이터 전송 프로세스 설명
solution: Audience Manager
title: 실시간 데이터 전송 프로세스 설명
uuid: B 68781 B 3-0 B 7 A -442 D -8 E 34-2 DB 2474849 A 4
translation-type: tm+mt
source-git-commit: ea95df8531c00c183f22b09a4a78fc6b35ee279d

---


# Real-Time Data Transfer Process Described{#real-time-data-transfer-process-described}

Audience Manager가 타사 컨텐츠 제공업체를 통해 실시간 데이터 전송을 수행하는 방법에 대한 일반적인 개요입니다.

<!-- real-time-data-transfer-explained.xml -->

## 실시간 데이터 전송

실시간 데이터 전송은 사용자가 사이트에서 방문 또는 조치를 취할 때 세그먼트 ID를 전송하고 수신합니다. 일반적으로 동기 데이터 전송은 인벤토리를 탐색하면서 사용자를 바로 자격을 부여하거나 세그먼트화해야 할 때 유용합니다.

## 데이터 통합 단계

실시간 데이터 통합 프로세스는 다음과 같이 작동합니다.

1. 사용자가 Audience Manager 코드가 들어 있는 고객 사이트를 방문합니다.
1. Audience Manager loads an iframe and makes a call to our [!UICONTROL Data Collection Server] ( [!UICONTROL DCS]).
1. The [!UICONTROL DCS] calls the third-party server (in real time) to check if the vendor has any segment information about the user.
1. 컨텐츠 제공자는 해당 사용자에 대한 세그먼트 정보를 Audience Manager로 반환합니다.
1. Audience Manager는 이 세그먼트 정보를 받고 새 트레이트와 세그먼트를 타깃팅하고 작성하는 데 사용할 수 있도록 합니다.

![](assets/rt_reduce70.png)