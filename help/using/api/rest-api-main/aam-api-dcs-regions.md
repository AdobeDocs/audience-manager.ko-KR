---
description: Audience Manager DCS 지역을 프로그래밍 방식으로 나열할 수 있는 메서드입니다.
seo-description: Audience Manager DCS 지역을 프로그래밍 방식으로 나열할 수 있는 메서드입니다.
seo-title: DCS 영역 API 메서드
solution: Audience Manager
title: DCS 영역 API 메서드
uuid: 00 b 70927-B 3 B 7-46 BB -8 BE 1-37 C 6100 ECF 80
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# DCS Region API Methods {#dcs-region-api-methods}

Methods that let you programmatically list Audience Manager [!UICONTROL DCS] regions.

<!-- c_rest_api_regions.xml -->

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## List a Specific DCS Region {#list-specific-dcs-region}

A `GET` method to list a specific [!UICONTROL DCS] region.

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

Returns `200 OK` if successful.

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## List DCS Regions {#list-dcs-regions}

A `GET` method to list [!UICONTROL DCS] regions.

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

Returns `200 OK` if successful.

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
