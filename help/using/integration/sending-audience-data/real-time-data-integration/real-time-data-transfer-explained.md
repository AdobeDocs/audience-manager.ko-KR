---
description: Audience Manager이 타사 콘텐츠 공급자와 실시간 데이터 전송을 수행하는 방법에 대한 일반적인 개요입니다.
seo-description: A general overview of how Audience Manager performs real-time data transfers with a third-party content provider.
seo-title: Real-Time Data Transfer Process Described
solution: Audience Manager
title: 실시간 데이터 전송 프로세스 설명
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: Inbound Data Transfers
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
    internal-label: Integrations
subfeature_v2:
  - id: a03b8192-8410-479f-a326-4cddf10757f6
    internal-label: Inbound data transfers
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 0%
---

# 실시간 데이터 전송 프로세스 설명{#real-time-data-transfer-process-described}

Audience Manager이 타사 콘텐츠 공급자와 실시간 데이터 전송을 수행하는 방법에 대한 일반적인 개요입니다.

<!-- real-time-data-transfer-explained.xml -->

## 실시간 데이터 전송

실시간 데이터 전송은 사용자가 사이트를 방문하거나 사이트에서 작업을 수행할 때 세그먼트 ID를 보내고 받습니다. 일반적으로 동기 데이터 전송은 사용자가 인벤토리를 탐색할 때 자격을 부여하거나 즉시 세그먼트화해야 할 때 유용합니다.

## 데이터 통합 단계

실시간 데이터 통합 프로세스는 다음과 같이 작동합니다.

1. 사용자가 Audience Manager 코드가 포함된 고객의 사이트를 방문합니다.
1. Audience Manager은 iframe을 로드하고 [!UICONTROL Data Collection Server]&#x200B;( [!DNL DCS])을 호출합니다.
1. [!DNL DCS]은(는) 서드파티 서버를 실시간으로 호출하여 공급업체에 사용자에 대한 세그먼트 정보가 있는지 확인합니다.
1. 콘텐츠 공급자는 해당 사용자에 대한 세그먼트 정보를 Audience Manager에 반환합니다.
1. Audience Manager은 이 세그먼트 정보를 수신하여 타겟팅하고 새로운 트레이트 및 세그먼트를 만드는 데 사용할 수 있도록 합니다.

![](assets/rt_reduce70.png)