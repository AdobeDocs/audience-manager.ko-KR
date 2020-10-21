---
description: 타사 컨텐츠 제공업체와 실시간 데이터 전송을 수행하는 방법에 대한 일반적인 개요입니다.
seo-description: 타사 컨텐츠 제공업체와 실시간 데이터 전송을 수행하는 방법에 대한 일반적인 개요입니다.
seo-title: 실시간 데이터 전송 프로세스 설명
solution: Audience Manager
title: 실시간 데이터 전송 프로세스 설명
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---


# Real-Time Data Transfer Process Described{#real-time-data-transfer-process-described}

타사 컨텐츠 제공업체와 실시간 데이터 전송을 수행하는 방법에 대한 일반적인 개요입니다.

<!-- real-time-data-transfer-explained.xml -->

## 실시간 데이터 전송

실시간 데이터 전송은 사용자가 사이트를 방문하거나 조치를 취할 때 세그먼트 ID를 보내고 받습니다. 일반적으로, 동기 데이터 전송은 재고를 탐색하면서 사용자를 자격 조건화하거나 즉시 세그먼트화해야 할 때 유용합니다.

## 데이터 통합 단계

실시간 데이터 통합 프로세스는 다음과 같이 작동합니다.

1. 사용자가 Audience Manager 코드를 포함하는 고객의 사이트를 방문합니다.
1. Audience Manager은 iframe을 로드하고 우리 [!UICONTROL Data Collection Server] ()를 [!DNL DCS]호출합니다.
1. 타사 서버 [!DNL DCS] (실시간으로)를 호출하여 공급업체가 사용자에 대한 세그먼트 정보를 가지고 있는지 확인합니다.
1. 콘텐트 제공자는 해당 사용자에 대한 세그먼트 정보를 Audience Manager으로 반환합니다.
1. Audience Manager은 이 세그먼트 정보를 수신하고 이를 타깃팅하고 새 트레이트와 세그먼트를 만드는 데 사용할 수 있도록 합니다.

![](assets/rt_reduce70.png)