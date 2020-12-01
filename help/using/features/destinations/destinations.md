---
description: Audience Manager에서 대상은 데이터를 공유할 수 있는 입니다. 대상 빌더는 쿠키, URL 또는 서버 간 대상을 만들고 관리하는 데 사용하는 도구입니다.
keywords: integration code, destination, destination overview, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination
seo-description: Audience Manager에서 대상은 데이터를 공유할 수 있는 입니다. 대상 빌더는 쿠키, URL 또는 서버 간 대상을 만들고 관리하는 데 사용하는 도구입니다.
seo-title: 대상
solution: Audience Manager
title: 대상
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 17%

---


# [!UICONTROL Destinations] 개요 {#destinations}

Audience Manager에서 [!UICONTROL destination]은 모든 타사 시스템(광고 서버, [!DNL DSP], 광고 네트워크 등)입니다. 입니다. [!UICONTROL Destination Builder] 은 작성 및 관리 [!UICONTROL cookie],  [!DNL URL]또는  [!UICONTROL server-to-server destinations]관리하는 데 사용한 도구입니다.

## 목적 및 장점 {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] 세그먼트화된 사용자 [!UICONTROL Destination Builder] 에 대한 정보를 만들어 데이터 파트너에게 보낼  [!UICONTROL destinations] 수 있습니다. 이를 통해 다음과 같은 이점이 있습니다.

* **Protect 데이터 값: 모든 사용자 데이터** 를  [!UICONTROL destination]한 사람에게 보내지  [!UICONTROL Destination Builder] 않고 자격 조건을 갖춘 사용자에 대한 특정 정보만 공유할 수 있습니다.
* **데이터에 대한 대응:** 데이터를  [!UICONTROL destination] 파트너에게 보내면 자격을 갖춘 고객 세그먼트를 신속하게 개발하고 타겟팅할 수 있습니다.
* **기술 간접비 절감:** 비즈니스 사용자는  [!UICONTROL destinations] 인터페이스에서  [!UICONTROL Destination Builder] 안전하게 설정할 수 있습니다. 이를 통해 배포 전 테스트에 필요한 시간을 줄일 수 있습니다. [!UICONTROL Destination Builder]을(를) 사용하면 비즈니스의 변화에 따라 [!UICONTROL destinations]을(를) 만들고, 관리하고, 삭제할 수 있습니다. 이 모든 것은 긴 개발 주기를 거치지 않습니다.

## 기술 고려 사항 {#technical-considerations}

<!-- destination-delivery-methods.xml -->

데이터 배달은 데이터 파트너가 [!UICONTROL destination] 정보를 어떻게 수신할지 또는 받을 수 있는지에 따라 다릅니다. 기술 또는 엔지니어링 제약 조건으로 인해 [!UICONTROL destination]이(가) [!DNL URL], [!UICONTROL cookie] 또는 [!UICONTROL server-to-server] 프로세스를 통해 데이터를 수신하지 못할 수 있습니다. 타사 파트너와 협력하여 사용할 수 있는 방법을 확인합니다.

## 비즈니스 고려 사항 {#business-considerations}

배달 방법 중 하나를 다른 방법보다 선택하는 비즈니스 결정은 [!UICONTROL destination] 파트너의 기술 기능과 자격 조건을 갖춘 사용자 정보를 사용하여 수행할 작업에 따라 달라집니다. 예를 들어 [!UICONTROL destination]이(가) 특정 배달 방법으로 데이터를 받을 수 없을 경우 기술 제약 조건으로 옵션을 제한할 수 있습니다. 그러나 기술적인 문제가 없는 경우 해당 데이터에 대해 조치를 취할 방법을 기반으로 정보를 보낼 수 있습니다. 예:

* [!DNL URL]s 및  [!UICONTROL cookie-based destinations] work almost synchronous with user actions on a page.
* [!UICONTROL Server-to-server] 방법은 시간이 지남에 따라 깊이 있는 고객 세그먼트를 만드는 데 유용합니다.

## [!UICONTROL Destination] 유형 및 일반 사용  {#destination-types}

다음 표의 예는 특정 [!UICONTROL destination]을 사용해야 하는 시기와 각 유형 간의 차이점을 이해하는 데 도움이 됩니다.

| [!UICONTROL Destination] | 일반적으로 | 예 | 고려 사항 |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | 다른 Adobe Experience Cloud 솔루션으로 데이터를 보내야 합니다. | Adobe Analytics으로 데이터 전송 |  |
| **[!UICONTROL People-Based Destinations]** | Facebook과 같은 사람 기반 환경으로 대상 세그먼트를 보내야 합니다. | 기존 고객에게 구매 내역을 기반으로 개인화된 제안 제공 | 대상 타깃팅은 해시된 식별자를 통해 수행됩니다. [사람 기반 대상](people-based-destinations-overview.md)을 참조하십시오. |
| **[!UICONTROL Device-Based Destinations]** (**서버 간**) | <ul><li>즉각적인 데이터 전송이 필요하지 않습니다.</li><li>데이터를 수집하여 자격 조건을 갖춘 사용자로 구성된 대규모 고객 풀을 구축할 수 있습니다.</li></ul> | 시간(시간 또는 일)에 따른 데이터를 수집하여 나중에 실행되도록 캠페인 세트에 사용합니다. | <ul><li>새 사이트 방문자와 이전 사이트 방문자에 대한 데이터를 전송합니다. </li><li>방문자가 다른 세그먼트를 이용할 수 있는 자격을 갖추기 위해 다시 볼 필요가 없습니다.</li></ul> |
| **[!UICONTROL Custom Destinations]** (**** URL 또는  **쿠키**) | 대상이 자격 조건을 갖춘 사용자를 즉시 조치를 취할 수 있도록 데이터를 즉시 전송해야 합니다. | 티켓 구매 사이트에서 데이터 전송 [!UICONTROL URL] 또는 [!UICONTROL cookie destination]을 사용하여 사용자 자격을 검증하고 즉시 재타깃팅합니다. | <ul><li>새 방문자에 대한 데이터만 전송합니다. </li><li>방문자가 세그먼트를 사용할 자격이 있는지 여부를 다시 확인해야 합니다.</li></ul> |
