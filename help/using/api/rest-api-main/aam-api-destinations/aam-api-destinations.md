---
description: 대상 기능을 사용하여 프로그래밍 방식으로 작업할 수 있는 메서드입니다.
seo-description: 대상 기능을 사용하여 프로그래밍 방식으로 작업할 수 있는 메서드입니다.
seo-title: 대상 API 메서드
solution: Audience Manager
title: 대상 API 메서드
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 15%

---


# 대상 API 메서드 {#destination-api-methods}

대상 기능을 사용하여 프로그래밍 방식으로 작업할 수 있는 메서드입니다.

<!-- c_destinations_api.xml -->

Audience Manager에서 대상은 다른 시스템(광고 서버, [!DNL DSP], 광고 네트워크, 교환, 자사 쿠키 등)입니다. 입니다.

## 대상 유형:URL 및 쿠키 {#destination-types}

`destinationType` 매개 변수에 사용되는 변수를 나열합니다. [!UICONTROL URL] 또는 [!UICONTROL cookie destination]과 함께 사용할 `push` 또는 `ADS`을 지정합니다. 사용 가능한 대상 [!DNL API] 메서드로 [!UICONTROL server-to-server destinations]을(를) 만들 수 없습니다.

<!-- r_destination_types.xml -->

| API 대상 유형 | UI 대상 유형 |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORELIKETHIS]
>
>* [대상 유형 선택 방법](../../../features/destinations/destinations.md)

