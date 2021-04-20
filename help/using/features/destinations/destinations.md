---
description: Audience Manager에서 대상은 데이터를 공유할 수 있는 입니다. 대상 빌더는 쿠키, URL 또는 서버 간 대상을 만들고 관리하는 데 사용하는 도구입니다.
keywords: 통합 코드, 대상, 대상 개요, 대상, 대상, 대상, 대상, 대상, 대상, 대상, 대상, 대상, 대상, 대상, 대상, 대상, 대상
landing-page-description: 대상은 데이터를 공유할 광고 서버나 DSP와 같은 모든 서드 파티 시스템입니다. 대상 빌더 도구를 사용하여 쿠키, URL 또는 서버 간 대상을 만들고 관리합니다.
seo-title: 대상
solution: Audience Manager
title: 대상
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
exl-id: f880bb18-057a-494d-82bf-69fc9f34781f
translation-type: tm+mt
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 15%

---

# [!UICONTROL Destinations] 개요 {#destinations}

Audience Manager에서 [!UICONTROL destination]은 제3자 시스템(광고 서버, [!DNL DSP], 광고 네트워크 등)입니다. 입니다. [!UICONTROL Destination Builder] 은 만들기 및 관리 [!UICONTROL cookie], 또 [!DNL URL]는  [!UICONTROL server-to-server destinations]는

## 목적 및 장점 {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] 세그먼트화된 사용자 [!UICONTROL Destination Builder] 에 대한 정보를 만들어 데이터 파트너에 보낼 수  [!UICONTROL destinations] 있습니다. 다음과 같은 이점이 있습니다.

* **Protect 데이터 값:** 모든 사용자 데이터를 다른 사람에게 전송하는  [!UICONTROL destination]대신 자격이 있는 사용자에 대한 특정  [!UICONTROL Destination Builder] 정보만 공유할 수 있습니다.
* **데이터에 대한 조치 수행:** 파트너에게 데이터를 전송하면 자격을 갖춘  [!UICONTROL destination] 고객 세그먼트를 신속하게 개발하고 타겟팅할 수 있습니다.
* **기술 간접비 절감:** 비즈니스 사용자는 인터페이스 [!UICONTROL destinations] 에서 안전하게 설정할 수  [!UICONTROL Destination Builder] 있습니다. 이를 통해 배포 전 테스트에 필요한 시간을 줄일 수 있습니다. [!UICONTROL Destination Builder]을 사용하면 긴 개발 주기를 거치지 않고도 비즈니스의 변화에 따라 [!UICONTROL destinations]을(를) 만들고, 관리하고, 삭제합니다.

## 기술 고려 사항 {#technical-considerations}

<!-- destination-delivery-methods.xml -->

데이터 배달은 데이터 파트너가 [!UICONTROL destination] 정보를 어떻게 수신할지 또는 받을 수 있는지에 따라 달라집니다. 기술 또는 엔지니어링 제약 조건으로 인해 [!UICONTROL destination]이(가) [!DNL URL], [!UICONTROL cookie] 또는 [!UICONTROL server-to-server] 프로세스를 통해 데이터를 수신하지 못할 수 있습니다. 제3자 파트너와 협력하여 사용할 수 있는 방법을 결정합니다.

## 비즈니스 고려 사항 {#business-considerations}

다른 전달 방법을 선택할 때 비즈니스 의사 결정은 [!UICONTROL destination] 파트너의 기술 기능과 자격 조건을 갖춘 사용자 정보를 사용하여 수행할 작업에 따라 달라집니다. 예를 들어 [!UICONTROL destination]이(가) 특정 배달 방법으로 데이터를 받을 수 없는 경우 기술 제약 조건이 옵션을 제한할 수 있습니다. 그러나 기술적인 문제가 없는 경우 해당 데이터에 대해 조치를 취할 방법을 기반으로 정보를 보낼 수 있습니다. 예:

* [!DNL URL]페이지 [!UICONTROL cookie-based destinations] 의 사용자 동작과 거의 동기적으로 작동합니다.
* [!UICONTROL Server-to-server] 메서드를 사용하면 시간에 따른 심도 있는 고객 세그먼트를 만들 수 있습니다.

## [!UICONTROL Destination] 유형 및 일반 사용  {#destination-types}

다음 표의 예는 특정 [!UICONTROL destination]을 사용하는 시기와 각 유형 간의 차이점을 이해하는 데 도움이 됩니다.

| [!UICONTROL Destination] | 일반적으로 | 예 | 고려 사항 |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | 다른 Adobe Experience Cloud 솔루션으로 데이터를 보내야 합니다. | Adobe Analytics으로 데이터 전송 |  |
| **[!UICONTROL People-Based Destinations]** | 대상 세그먼트를 Facebook과 같은 사람 기반 환경으로 보내야 합니다. | 구매 내역을 기반으로 기존 고객에게 개인화된 제안 제공 | 대상 타깃팅은 해시된 식별자를 통해 수행됩니다. [사람 기반 대상](people-based-destinations-overview.md)을 참조하십시오. |
| **[!UICONTROL Device-Based Destinations]** (**서버 간**) | <ul><li>즉각적인 데이터 전송은 필요하지 않습니다.</li><li>자격 조건을 갖춘 사용자로 구성된 대규모 대상 풀을 작성하는 데이터를 수집합니다.</li></ul> | 시간(시간 또는 일)에 따른 데이터를 수집하여 나중에 실행되도록 캠페인 세트에 사용합니다. | <ul><li>새 사이트 방문자와 이전 사이트 방문자에 대한 데이터를 전송합니다. </li><li>방문자가 다른 세그먼트에 대해 자격이 부여될 필요가 없습니다.</li></ul> |
| **[!UICONTROL Custom Destinations]** (**** URL 또는  **쿠키**) | 대상이 자격이 있는 사용자에 대해 즉시 조치를 취할 수 있도록 데이터를 즉시 전송해야 합니다. | 티켓 구입 사이트에서 데이터 전송 [!UICONTROL URL] 또는 [!UICONTROL cookie destination]을 사용하여 사용자를 자격을 평가하고 즉시 다시 타깃팅합니다. | <ul><li>새 방문자에 대한 데이터만 전송합니다. </li><li>방문자가 세그먼트에 자격이 있는지 다시 확인해야 합니다.</li></ul> |
