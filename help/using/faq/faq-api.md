---
description: 일반적인 API 질문 및 문제
seo-description: 일반적인 API 질문 및 문제
seo-title: API FAQ
solution: Audience Manager
title: API FAQ
uuid: 8222ebf0-b50e-4f48-8021-dbfca2828b7c
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 100%

---


# API FAQ{#api-faq}

일반적인 API 질문 및 문제

<!-- 

faq_api.xml

 -->

[REST API](../api/rest-api-main/rest-api-main.md) 설명서에는 특정 메서드 및 코드 샘플에 대한 자세한 내용이 포함되어 있습니다.

<br> 

**왜 [!UICONTROL DIL]이 [!UICONTROL GET] 및 [!UICONTROL POST] 메서드로 이벤트를 호출합니까?**

[!UICONTROL DIL]은 이벤트 호출의 쿼리 문자열 길이를 기반으로 `GET` 또는 `POST` 메서드를 사용하여 데이터를 [!DNL Audience Manager]에 전달합니다. 이 동작은 기본적으로 `GET` 및 `POST` 메서드에 내장되어 있으며, [!DNL Audience Manager]에만 국한되지 않습니다.

* URL이 2,048자 이하인 경우 [!UICONTROL DIL]은 `GET`으로 이벤트를 호출합니다. `GET` 이벤트 호출은 키-값 쌍으로 전달되는 쿼리 문자열 매개 변수로서 URL의 데이터를 포함합니다.

* URL이 2048자보다 많은 경우 [!UICONTROL DIL]은 `POST`로 이벤트를 호출합니다. `POST` 이벤트 호출은 요청 본문의 데이터를 포함합니다. [!UICONTROL DIL]은 데이터를 키-값 쌍에 넣고 URL 쿼리 문자열이 아닌 정보를 양식 데이터로 전달합니다.

각 메서드가 데이터를 다른 방식으로 전달하지만 이것이 기능에 영향을 주지는 않습니다. 예를 들어, 두 방법 중 하나를 사용하면 [!DNL Audience Manager]는 데이터를 대상에 전송하고 ID 동기화는 정상적으로 작동하며 데이터 신호로부터 트레이트를 만들 수 있습니다.

<br> 

**[!UICONTROL REST API]로 무엇을 할 수 있습니까?**

[!UICONTROL REST API]를 사용하면 사용자 인터페이스에 있는 대부분의 [!DNL Audience Manager] 기능을 프로그래밍 방식으로 사용할 수 있습니다.

<br> 

**[!UICONTROL REST API] 클라이언트 ID와 암호를 어떻게 얻습니까?**

[!DNL API] 액세스 자격 증명을 받으려면 파트너 솔루션 담당자에게 문의하십시오. Adobe API는 토큰 인증, 허가 및 갱신에 [OAuth 2.0](https://oauth.net/2/) 표준을 사용합니다. 자세한 내용은 [OAuth 인증](../api/rest-api-main/aam-api-getting-started.md#oauth)을 참조하십시오.
