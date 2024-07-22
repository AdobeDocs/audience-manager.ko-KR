---
description: 대상 기능을 사용하여 프로그래밍 방식으로 작업할 수 있는 메서드입니다.
seo-description: Methods that let you work programmatically with destination features.
seo-title: Destination API Methods
solution: Audience Manager
title: 대상 API 메서드
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
feature: API
exl-id: 38dea854-2b7b-417e-9d56-919b65807628
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 0%

---

# 대상 API 메서드 {#destination-api-methods}

대상 기능을 사용하여 프로그래밍 방식으로 작업할 수 있는 메서드입니다.

<!-- c_destinations_api.xml -->

Audience Manager에서 대상은 다른 시스템(광고 서버, [!DNL DSP], 광고 네트워크, 교환, 고유한 자사 쿠키 등)입니다. 와(과) 데이터를 공유할 수 있습니다.

## 대상 유형: URL 및 쿠키 {#destination-types}

`destinationType` 매개 변수에서 사용하는 변수를 나열합니다. [!UICONTROL URL] 또는 [!UICONTROL cookie destination](으)로 작업하려면 `push` 또는 `ADS`을(를) 지정하십시오. 사용 가능한 대상 [!DNL API] 메서드로 [!UICONTROL server-to-server destinations]을(를) 만들 수 없습니다.

<!-- r_destination_types.xml -->

| API 대상 유형 | UI 대상 유형 |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORELIKETHIS]
>
>* [대상 유형을 선택하는 방법](../../../features/destinations/destinations.md)
