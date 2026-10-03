---
description: 실시간 인바운드 데이터 섭취 프로세스는 사용자 브라우저의 일련의 HTTP 요청을 사용하여 데이터를 Audience Manager에 전달합니다.
seo-description: The real-time inbound data ingestion process uses a series of HTTP requests from a user's browser to pass in data to Audience Manager.
seo-title: Real-Time Inbound Data Ingestion
solution: Audience Manager
title: 실시간 인바운드 데이터 섭취
uuid: 43cb0ebc-6c36-4391-bbfb-6b203d63c69a
feature: Inbound Data Transfers
exl-id: d243c74c-3a29-4dbf-a4c7-43ea526a9d7b
TQID: 'https://experienceleague.adobe.com/ps6Iks-zvDnIIEagSND0LEnW18K6odtuwIJOsBfp2v0'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
    internal-label: Implementation
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
    internal-label: Integrations
subfeature_v2:
  - id: a03b8192-8410-479f-a326-4cddf10757f6
    internal-label: Inbound data transfers
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 1%
---
# 실시간 인바운드 데이터 섭취 {#real-time-inbound-data-ingestion}

실시간 인바운드 데이터 섭취 프로세스는 사용자 브라우저의 일련의 `HTTP` 요청을 사용하여 데이터를 Audience Manager에 전달합니다.

<!-- c_rt_inbound_real_time.xml -->

인바운드 데이터는 신호라는 키-값 쌍으로 포맷되어야 합니다. 일반적으로 각 신호는 사용자 인터페이스 또는 [!DNL API]을(를) 통해 생성되거나 관리되는 세그먼트에 매핑됩니다.

## URL 문자열 매개 변수 및 구문 {#url-string-syntax}

인바운드 데이터 전송에 대한 [!DNL URL]에 아래에 설명된 변수가 포함되어야 합니다. 실시간 데이터 전송을 설정하기 전에 [!DNL Audience Manager] UI에서 [트레이트 만들기](../../../features/traits/create-onboarded-rule-based-traits.md) 및 [폴더 구조](../../../features/traits/trait-storage.md#create-trait-storage-folder)를 참조하세요.

>[!NOTE]
>
>기울임꼴 컨텐츠를 실제 매개 변수 값으로 바꿉니다.

| 매개 변수 | 설명 |
|---|---|
| `<KEY>` | 키-값 쌍의 고유 식별자(예: 성별, 색상, 가격). |
| `<VAL>` | 키로 정의된 데이터 세트에 속하는 변수(예: gender=male, color=green, price=100) |

### URL 구문

실시간 인바운드 데이터 섭취 프로세스 중에 올바른 형식의 [!DNL URL] 문자열은 다음 구문을 사용합니다.

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
