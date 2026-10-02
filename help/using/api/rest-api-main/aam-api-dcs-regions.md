---
description: Audience Manager DCS 지역을 프로그래밍 방식으로 나열할 수 있는 메서드입니다.
seo-description: Methods that let you programmatically list Audience Manager DCS regions.
seo-title: DCS Region API Methods
solution: Audience Manager
title: DCS 지역 API 메서드
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
feature: API
exl-id: 3cd1700e-6914-46be-a0be-a870c472343e
TQID: 'https://experienceleague.adobe.com/ipsOlq24Y00SHvGKgUFJHnRQ11DZIuDNY76D5LCAgso'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
    internal-label: APIs and SDKs
subfeature_v2:
  - id: d8f681b8-67cc-42dc-85c5-a0977528a942
    internal-label: Data Collection Server
  - id: 7dee9651-deb5-5d4d-acfd-fbc10040467f
    internal-label: API
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 3%
---
# DCS 지역 API 메서드 {#dcs-region-api-methods}

Audience Manager [!DNL DCS] 영역을 프로그래밍 방식으로 나열할 수 있는 메서드입니다.

<!-- c_rest_api_regions.xml -->

지역 및 해당 정수의 목록을 보려면 [DCS 지역 ID, 위치 및 호스트 이름](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)을 참조하십시오.

## 특정 DCS 영역 나열 {#list-specific-dcs-region}

특정 [!DNL DCS] 영역을 나열하는 `GET` 메서드입니다.

<!-- r_rest_api_regions_list_specific.xml -->

### 요청

`GET /v1/dcs-regions/`*`<id>`*

### 샘플 응답

```
{ 
    "regionId" : <id>, 
    "location" : "<location>",
    "host" : "<host>",
    "code" : "<code>",
    "status" : "ACTIVE" | "INACTIVE",
    "createTime" : long of milliseconds since epoch,
    "updateTime" : long of milliseconds since epoch,
    "crUID" : <userId who created>,
    "upUID" : <userId who updated>
  }
```

성공하면 `200 OK`을(를) 반환합니다.

지역 및 해당 정수의 목록을 보려면 [DCS 지역 ID, 위치 및 호스트 이름](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)을 참조하십시오.

## DCS 지역 나열 {#list-dcs-regions}

[!DNL DCS] 영역을 나열하는 `GET` 메서드입니다.

<!-- r_rest_api_regions_list.xml -->

### 요청

`GET /v1/dcs-regions/`

### 샘플 응답

```
[
  { 
    "regionId" : <id>, 
    "location" : "<location>",
    "host" : "<host>",
    "code" : "<code> # APSE, USE, etc,
    "status" : "ACTIVE" | "INACTIVE",
    "createTime" : long of milliseconds since epoch,
    "updateTime" : long of milliseconds since epoch,
    "crUID" : <userId who created>,
    "upUID" : <userId who updated>
  },
  ...
]
```

성공하면 `200 OK`을(를) 반환합니다.

지역 및 해당 정수의 목록을 보려면 [DCS 지역 ID, 위치 및 호스트 이름](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)을 참조하십시오.
