---
description: 대상 기능을 사용하여 프로그래밍 방식으로 작업할 수 있는 메서드입니다.
seo-description: Methods that let you work programmatically with destination features.
seo-title: Destination API Methods
solution: Audience Manager
title: 대상 API 메서드
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
feature: API
exl-id: 38dea854-2b7b-417e-9d56-919b65807628
TQID: https://experienceleague.adobe.com/8fUlWE0aqgltxB-bS0X1cjE4Dg0-VvHpRjvWQmjKe5s
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
  - id: c814092e-2730-45e8-a12d-e084529f52cb
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 89
ht-degree: 0%

---

# 대상 API 메서드 {#destination-api-methods}

대상 기능을 사용하여 프로그래밍 방식으로 작업할 수 있는 메서드입니다.

<!-- c_destinations_api.xml -->

Audience Manager에서 대상은 데이터를 공유할 다른 시스템(광고 서버, [!DNL DSP], 광고 네트워크, 교환, 고유한 자사 쿠키 등)입니다.

## 대상 유형: URL 및 쿠키 {#destination-types}

`destinationType` 매개 변수에서 사용하는 변수를 나열합니다. `push` 또는 `ADS`(으)로 작업하려면 [!UICONTROL URL] 또는 [!UICONTROL cookie destination]을(를) 지정하십시오. 사용 가능한 대상 [!UICONTROL server-to-server destinations] 메서드로 [!DNL API]을(를) 만들 수 없습니다.

<!-- r_destination_types.xml -->

| API 대상 유형 | UI 대상 유형 |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORELIKETHIS]
>
>* [대상 유형을 선택하는 방법](../../../features/destinations/destinations.md)
