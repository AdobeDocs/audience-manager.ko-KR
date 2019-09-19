---
description: 대상 기능을 사용하여 프로그래밍 방식으로 작업할 수 있는 메서드입니다.
seo-description: 대상 기능을 사용하여 프로그래밍 방식으로 작업할 수 있는 메서드입니다.
seo-title: 대상 API 메서드
solution: Audience Manager
title: 대상 API 메서드
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 대상 API 메서드 {#destination-api-methods}

대상 기능을 사용하여 프로그래밍 방식으로 작업할 수 있는 메서드입니다.

<!-- c_destinations_api.xml -->

Audience Manager에서 대상은 다른 시스템(광고 서버, [!DNL DSP]광고 네트워크, 교환, 자사 쿠키 등)입니다. 데이터를 공유할 수 있습니다.

## 대상 유형:URL 및 쿠키 {#destination-types}

매개 변수에 사용되는 변수를 `destinationType` 나열합니다. 또는 를 사용하여 `push` 또는 `ADS` 작업할 [!UICONTROL URL] 수 [!UICONTROL cookie destination]있습니다. 사용 가능한 대상 [!UICONTROL server-to-server destinations] [!DNL API] 메서드로 만들 수 없습니다.

<!-- r_destination_types.xml -->

| API 대상 유형 | UI 대상 유형 |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORELIKE_THIS]
>
>* [대상 유형을 선택하는 방법](../../../features/destinations/destinations.md)

