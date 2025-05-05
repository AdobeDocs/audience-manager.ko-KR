---
description: 데이터를 공유하는 광고 서버 또는 DSP와 같은 모든 서드파티 시스템의 장점, 유형 및 용도를 살펴보십시오. Destination Builder를 사용하여 쿠키, URL 또는 서버 간 대상을 만들고 관리할 수 있습니다.
keywords: 통합 코드, 대상, 대상 개요, 대상, 대상, 대상, 대상, 대상, 대상, 대상, 대상, 대상, 대상, 대상, 대상, 대상, 대상, 대상,
landing-page-description: 데이터를 공유하는 광고 서버 또는 DSP와 같은 모든 서드파티 시스템의 장점, 유형 및 용도를 살펴보십시오. Destination Builder를 사용하여 쿠키, URL 또는 서버 간 대상을 만들고 관리할 수 있습니다.
short-description: 데이터를 공유하는 광고 서버 또는 DSP와 같은 모든 서드파티 시스템의 장점, 유형 및 용도를 살펴보십시오. Destination Builder를 사용하여 쿠키, URL 또는 서버 간 대상을 만들고 관리할 수 있습니다.
seo-title: Destinations
solution: Audience Manager
title: 대상
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
exl-id: f880bb18-057a-494d-82bf-69fc9f34781f
source-git-commit: 5d62ecabfe66faa024f8e89149e47dd76d1bba86
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 20%

---

# [!UICONTROL Destinations] 개요 {#destinations}

Audience Manager에서 [!UICONTROL destination]은(는) 타사 시스템(광고 서버, [!DNL DSP], 광고 네트워크 등)입니다. 입니다. [!UICONTROL Destination Builder]은(는) [!UICONTROL cookie], [!DNL URL] 또는 [!UICONTROL server-to-server destinations]을(를) 만들고 관리하는 데 사용한 도구입니다.

## 목적 및 장점 {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] 및 [!UICONTROL Destination Builder]을(를) 사용하면 [!UICONTROL destinations]을(를) 만들고 세그먼트화된 사용자에 대한 정보를 데이터 파트너에게 보낼 수 있습니다. 이렇게 하면 다음과 같은 이점이 있습니다.

* **Protect 데이터 값:** [!UICONTROL Destination Builder]에서는 모든 사용자 데이터를 [!UICONTROL destination] (으)로 보내는 대신 자격 있는 사용자에 대한 특정 정보만 공유할 수 있습니다.
* **데이터에 대한 조치 취하기:** 데이터를 [!UICONTROL destination] 파트너에게 보내면 적격 대상 세그먼트를 빠르게 개발하고 타깃팅할 수 있습니다.
* **기술 오버헤드 감소:** 비즈니스 사용자는 [!UICONTROL Destination Builder] 인터페이스에서 [!UICONTROL destinations]을(를) 안전하게 설정할 수 있습니다. 이렇게 하면 배포 전 테스트에 필요한 시간을 줄일 수 있습니다. [!UICONTROL Destination Builder]을(를) 사용하면 긴 개발 주기를 거치지 않고 비즈니스 요구 사항이 변경될 때 [!UICONTROL destinations]을(를) 만들고 관리하고 삭제할 수 있습니다.

## 기술 고려 사항 {#technical-considerations}

<!-- destination-delivery-methods.xml -->

데이터 전달은 데이터 파트너가 [!UICONTROL destination] 정보를 받거나 받을 수 있는 방법에 따라 다릅니다. 기술 또는 엔지니어링 제한으로 인해 [!UICONTROL destination]이(가) [!DNL URL], [!UICONTROL cookie] 또는 [!UICONTROL server-to-server] 프로세스를 통해 데이터를 받지 못할 수 있습니다. 서드파티 파트너와 협력하여 사용할 수 있는 방법을 결정하십시오.

## 비즈니스 고려 사항 {#business-considerations}

한 전달 방법을 다른 전달 방법으로 선택하기 위한 비즈니스 의사 결정은 [!UICONTROL destination] 파트너의 기술 기능과 적격 사용자 정보로 수행할 작업에 따라 다릅니다. 예를 들어 [!UICONTROL destination]이(가) 특정 게재 방법으로 데이터를 받을 수 없는 경우 기술 제한으로 인해 옵션이 제한될 수 있습니다. 그러나 기술적인 문제가 없는 경우 해당 데이터에 대한 조치 방법을 기반으로 정보를 전송할 수 있습니다. 예:

* [!DNL URL]과(와) [!UICONTROL cookie-based destinations]은(는) 페이지의 사용자 작업과 거의 동기식으로 작동합니다.
* [!UICONTROL Server-to-server] 메서드는 시간이 지남에 따라 깊은 대상 세그먼트를 만드는 데 적합합니다.

## [!UICONTROL Destination] 형식 및 일반 사용 {#destination-types}

다음 표의 예제를 통해 특정 [!UICONTROL destination]을(를) 사용할 시점과 각 유형 간의 차이점을 파악할 수 있습니다.

| [!UICONTROL Destination] 유형 | 일반적으로 다음과 같은 경우에 사용됨 | 예 | 고려 사항 |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | 다른 Adobe Experience Cloud 솔루션으로 데이터를 전송해야 합니다. | Adobe Analytics에 데이터 보내기. |  |
| **[!UICONTROL People-Based Destinations]** | 대상 세그먼트를 Facebook과 같은 사용자 기반 환경으로 전송해야 합니다. | 구매 내역을 기반으로 기존 고객에게 개인화된 오퍼 제공 | 대상자 타깃팅은 해시된 식별자를 통해 수행됩니다. [사용자 기반 대상](people-based-destinations-overview.md)을 참조하세요. |
| **[!UICONTROL Device-Based Destinations]**(**서버 간**) | <ul><li>즉각적인 데이터 전송은 필요하지 않습니다.</li><li>자격을 갖춘 사용자의 대규모 대상 풀을 구축하기 위해 데이터를 수집합니다.</li></ul> | 나중에 실행하도록 캠페인 세트에 사용하기 위해 시간(시간 또는 일)에 따른 데이터 수집. | <ul><li>새 사이트 방문자 및 이전 사이트 방문자에 대한 데이터를 전송합니다. </li><li>방문자가 다른 세그먼트에 대한 자격을 얻기 위해 다시 볼 필요가 없습니다.</li></ul> |
| **[!UICONTROL Custom Destinations]**(**URL** 또는 **쿠키**) | 대상이 자격 있는 사용자에 대해 즉시 작업을 수행할 수 있도록 데이터를 즉시 전송해야 합니다. | 티켓 구매 사이트에서 데이터를 보내는 중입니다. [!UICONTROL URL] 또는 [!UICONTROL cookie destination]을(를) 사용하여 사용자 자격을 부여하고 즉시 대상을 다시 지정하십시오. | <ul><li>새 방문자에 대한 데이터만 전송합니다. </li><li>방문자가 세그먼트에 대한 자격이 되는 것을 다시 확인해야 합니다.</li></ul> |
