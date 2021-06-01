---
description: 프로그래밍 방식으로 Audience Manager DCS 영역을 나열할 수 있는 메서드입니다.
seo-description: 프로그래밍 방식으로 Audience Manager DCS 영역을 나열할 수 있는 메서드입니다.
seo-title: DCS 지역 API 메서드
solution: Audience Manager
title: DCS 지역 API 메서드
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
feature: API
exl-id: 3cd1700e-6914-46be-a0be-a870c472343e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 15%

---

# DCS 지역 API 메서드 {#dcs-region-api-methods}

프로그래밍 방식으로 Audience Manager [!DNL DCS] 영역을 나열할 수 있는 메서드입니다.

<!-- c_rest_api_regions.xml -->

지역 및 해당 정수 목록에 대해서는 [DCS 지역 ID, 위치 및 호스트 이름](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)을 참조하십시오.

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

성공하면 `200 OK` 을 반환합니다.

지역 및 해당 정수 목록에 대해서는 [DCS 지역 ID, 위치 및 호스트 이름](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)을 참조하십시오.

## 목록 DCS 지역 {#list-dcs-regions}

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

성공하면 `200 OK` 을 반환합니다.

지역 및 해당 정수 목록에 대해서는 [DCS 지역 ID, 위치 및 호스트 이름](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)을 참조하십시오.
