---
description: 일반적인 API 질문 및 문제.
seo-description: 일반적인 API 질문 및 문제.
seo-title: API FAQ
solution: Audience Manager
title: API FAQ
uuid: 8222 EBF 0-B 50 E -4 F 48-8021-DBFCA 2828 B 7 C
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# API FAQ{#api-faq}

일반적인 API 질문 및 문제.

<!-- 

faq_api.xml

 -->

[REST API](../api/rest-api-main/rest-api-main.md) 설명서에는 특정 메서드 및 코드 샘플에 대한 세부 사항이 들어 있습니다.

<br> 

**이벤트[!UICONTROL DIL]호출을 포함하는[!UICONTROL GET]이유는[!UICONTROL POST]무엇입니까?**

[!UICONTROL DIL] 이벤트 호출의 [!DNL Audience Manager] 쿼리 문자열 길이에 따라 `GET` OR `POST` 메서드로 데이터를 전달합니다. This behavior is built in to `GET` and `POST` methods by default. [!DNL Audience Manager]특정 사항은 아닙니다.

* [!UICONTROL DIL] URL 이 2048 자 이하일 `GET` 때 이벤트 호출을 만듭니다. `GET` 이벤트 호출은 URL의 데이터를 키-값 쌍으로 전달되는 쿼리 문자열 매개 변수로 포함합니다.

* [!UICONTROL DIL] URL 이 2048 자보다 많은 `POST` 경우 이벤트 호출을 만듭니다. `POST` 이벤트 호출에는 요청 본문에 데이터가 포함됩니다. [!UICONTROL DIL] 데이터를 키-값 쌍에 삽입하고 정보를 URL 쿼리 문자열이 아닌 양식 데이터로 전달합니다.

각 메서드는 다른 방식으로 데이터를 전달하지만 기능에 영향을 주지 않습니다. For example, with either method, [!DNL Audience Manager] still sends data to destinations, ID syncs works normally, and you can create traits from data signals.

<br> 

**제가 수행할 수[!UICONTROL REST API]있는 작업은 무엇입니까?**

[!UICONTROL REST API]s를 사용하면 사용자 인터페이스에서 사용할 수 있는 대부분의 [!DNL Audience Manager] 기능을 사용하여 프로그래밍 방식으로 작업할 수 있습니다.

<br> 

**[!UICONTROL REST API]클라이언트 ID 및 암호를 얻으려면 어떻게 해야 합니까?**

Contact your Partner Solutions representative to obtain [!DNL API] access credentials. Our APIs use [OAuth 2.0](https://oauth.net/2/) standards for token authentication, authorization, and renewal. See [OAuth Authentication](../api/rest-api-main/aam-api-getting-started.md#oauth) for more information.
