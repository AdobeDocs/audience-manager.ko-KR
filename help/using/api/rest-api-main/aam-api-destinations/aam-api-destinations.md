---
description: 대상 기능으로 프로그래밍 방식으로 작업할 수 있는 메서드입니다.
seo-description: 대상 기능으로 프로그래밍 방식으로 작업할 수 있는 메서드입니다.
seo-title: 대상 API 메서드
solution: Audience Manager
title: 대상 API 메서드
uuid: 048 bcdb 9-2 b 31-46 f 4-8 b 80-4 ba 25 bf 06640
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Destination API Methods {#destination-api-methods}

대상 기능으로 프로그래밍 방식으로 작업할 수 있는 메서드입니다.

<!-- c_destinations_api.xml -->

In Audience Manager, a destination is any other system (ad server, [!DNL DSP], ad network, exchange, your own first-party cookie, etc.) 로 데이터를 공유할 수 있습니다.

## Destination Types: URL and Cookie {#destination-types}

Lists the variables used by the `destinationType` parameter. Specify `push` or `ADS` to work with a [!UICONTROL URL] or [!UICONTROL cookie destination]. You cannot create [!UICONTROL server-to-server destinations] with the available destination [!DNL API] methods.

<!-- r_destination_types.xml -->

| API 대상 유형 | UI 대상 유형 |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORE_ like_ this]
>
>* [대상 유형을 선택하는 방법](../../../features/destinations/destinations.md)

