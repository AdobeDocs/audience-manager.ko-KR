---
description: 실시간 인바운드 데이터 통합 프로세스는 사용자 브라우저의 일련의 HTTP 요청을 사용하여 Audience Manager에 데이터를 전달합니다.
seo-description: 실시간 인바운드 데이터 통합 프로세스는 사용자 브라우저의 일련의 HTTP 요청을 사용하여 Audience Manager에 데이터를 전달합니다.
seo-title: 실시간 인바운드 데이터 통합
solution: Audience Manager
title: 실시간 인바운드 데이터 통합
uuid: 43 CB 0 EBC -6 C 36-4391-BBFB -6 B 203 D 63 C 69 A
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Real-Time Inbound Data Ingestion {#real-time-inbound-data-ingestion}

The real-time inbound data ingestion process uses a series of `HTTP` requests from a user's browser to pass in data to Audience Manager.

<!-- c_rt_inbound_real_time.xml -->

인바운드 데이터는 신호라고 하는 키-값 쌍으로 형식을 지정해야 합니다. Typically, each signal is mapped to a segment created or managed through the user interface or [!DNL API].

## URL String Parameters and Syntax {#url-string-syntax}

The [!DNL URL] for an inbound data transfer should contain the variables described below. Remember to [create traits](../../../features/traits/create-onboarded-rule-based-traits.md) and a [folder structure](../../../features/traits/trait-storage.md#create-trait-storage-folder) in the [!DNL Audience Manager] UI before setting up real-time data transfers.

>[!NOTE]
>
>기울임꼴 컨텐츠를 실제 매개 변수 값으로 바꿉니다.

| 매개 변수 | 설명 |
|---|---|
| `<KEY>` | 키-값 쌍의 고유 식별자 (예: 성별, 색상, 가격). |
| `<VAL>` | 키로 정의된 데이터 세트에 속하는 변수 (예: gender = male, color = green, price = 100) |

### URL 구문

During a real-time inbound data ingestion process, a properly formatted [!DNL URL] string uses the following syntax:

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
