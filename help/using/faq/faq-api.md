---
description: 일반적인 API 질문 및 문제
seo-description: 일반적인 API 질문 및 문제
seo-title: API FAQ
solution: Audience Manager
title: API FAQ
uuid: 8222ebf0-b50e-4f48-8021-dbfca2828b7c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# API FAQ{#api-faq}

일반적인 API 질문 및 문제

<!-- 

faq_api.xml

 -->

REST [API](../api/rest-api-main/rest-api-main.md) 설명서에는 특정 메서드 및 코드 샘플에 대한 세부 사항이 포함되어 있습니다.

<br> 

**이벤트[!UICONTROL DIL]호출은 왜[!UICONTROL GET]및[!UICONTROL POST]메서드로 이루어집니까?**

[!UICONTROL DIL] 이벤트 호출의 쿼리 문자열 길이를 기준으로 [!DNL Audience Manager] 또는 `GET` `POST` 메서드로 데이터를 전달합니다. 이 동작은 기본적으로 `GET` 및 `POST` 메서드에 내장되어 있습니다. 그것은 특정하지 [!DNL Audience Manager]않다.

* [!UICONTROL DIL] URL에 2048자 이하여야 `GET` 하는 이벤트 호출을 만듭니다. 이벤트 호출에는 URL의 데이터가 쿼리 문자열 매개 변수로 포함되며 키-값 쌍으로 전달됩니다. `GET`

* [!UICONTROL DIL] URL에 2048자를 초과하는 `POST` 경우 이벤트 호출을 만듭니다. 이벤트 호출에는 요청 본문에 데이터가 포함됩니다. `POST` [!UICONTROL DIL] 데이터를 키-값 쌍에 삽입하고 URL 쿼리 문자열이 아닌 양식 데이터로 정보를 전달합니다.

각 메서드가 데이터를 다른 방식으로 전달하지만 기능에는 영향을 주지 않습니다. 예를 들어, 두 방법 중 하나로 데이터를 대상에 [!DNL Audience Manager] 여전히 전송하고, ID는 정상적으로 작동하며, 데이터 신호에서 트레이트를 만들 수 있습니다.

<br> 

**어떻게[!UICONTROL REST API]하면 되죠?**

이 [!UICONTROL REST API]기능을 사용하면 사용자 인터페이스에서 사용할 수 있는 대부분의 [!DNL Audience Manager] 기능과 함수를 프로그래밍 방식으로 작업할 수 있습니다.

<br> 

**클라이언트 ID와[!UICONTROL REST API]암호를 어떻게 얻습니까?**

액세스 자격 증명을 받으려면 파트너 솔루션 담당자에게 [!DNL API] 문의하십시오. Adobe API는 [토큰 인증](https://oauth.net/2/) , 인증 및 갱신에 OAuth 2.0 표준을 사용합니다. 자세한 [내용은 OAuth](../api/rest-api-main/aam-api-getting-started.md#oauth) 인증을 참조하십시오.
