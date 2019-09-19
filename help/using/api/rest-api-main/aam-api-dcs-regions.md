---
description: 프로그래밍 방식으로 Audience Manager DCS 영역을 나열할 수 있는 메서드입니다.
seo-description: 프로그래밍 방식으로 Audience Manager DCS 영역을 나열할 수 있는 메서드입니다.
seo-title: DCS 영역 API 메서드
solution: Audience Manager
title: DCS 영역 API 메서드
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# DCS 영역 API 메서드 {#dcs-region-api-methods}

프로그래밍 방식으로 Audience Manager [!UICONTROL DCS] 영역을 나열할 수 있는 메서드입니다.

<!-- c_rest_api_regions.xml -->

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## 특정 DCS 영역 나열 {#list-specific-dcs-region}

특정 영역을 나열하는 `GET` 방법입니다 [!UICONTROL DCS] .

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

성공하면 `200 OK` 반환합니다.

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## 목록 DCS 지역 {#list-dcs-regions}

지역을 나열하는 `GET` 방법입니다 [!UICONTROL DCS] .

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

성공하면 `200 OK` 반환합니다.

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
