---
description: 실시간 인바운드 데이터 섭취 프로세스는 사용자 브라우저의 일련의 HTTP 요청을 사용하여 데이터를 Audience Manager에 전달합니다.
seo-description: The real-time inbound data ingestion process uses a series of HTTP requests from a user's browser to pass in data to Audience Manager.
seo-title: Real-Time Inbound Data Ingestion
solution: Audience Manager
title: 실시간 인바운드 데이터 섭취
uuid: 43cb0ebc-6c36-4391-bbfb-6b203d63c69a
feature: Inbound Data Transfers
exl-id: d243c74c-3a29-4dbf-a4c7-43ea526a9d7b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 1%

---

# 실시간 인바운드 데이터 섭취 {#real-time-inbound-data-ingestion}

실시간 인바운드 데이터 섭취 프로세스는 사용자 브라우저의 일련의 `HTTP` 요청을 사용하여 데이터를 Audience Manager에 전달합니다.

<!-- c_rt_inbound_real_time.xml -->

인바운드 데이터는 신호라는 키-값 쌍으로 포맷되어야 합니다. 일반적으로 각 신호는 사용자 인터페이스 또는 [!DNL API]을(를) 통해 생성되거나 관리되는 세그먼트에 매핑됩니다.

## URL 문자열 매개 변수 및 구문 {#url-string-syntax}

인바운드 데이터 전송에 대한 [!DNL URL]에 아래에 설명된 변수가 포함되어야 합니다. 실시간 데이터 전송을 설정하기 전에 [ UI에서 ](../../../features/traits/create-onboarded-rule-based-traits.md)트레이트 만들기[ 및 ](../../../features/traits/trait-storage.md#create-trait-storage-folder)폴더 구조[!DNL Audience Manager]를 참조하세요.

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
