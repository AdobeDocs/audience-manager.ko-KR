---
description: 이러한 Restful API 메서드를 사용하여 세그먼트를 대상에 매핑할 수 있습니다.
seo-description: 이러한 Restful API 메서드를 사용하여 세그먼트를 대상에 매핑할 수 있습니다.
seo-title: 세그먼트를 대상에 매핑
solution: Audience Manager
title: 세그먼트를 대상에 매핑
uuid: 35358 ACE -3082-4 E 86-A 6 EB-D 77281 AF 6 D 7 E
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Map Segments to a Destination {#map-segments-to-a-destination}

Map segments to destinations with these [!DNL RESTful API] methods.

<!-- c_api_map_seg_dest.xml -->

## 지원되는 대상 유형: URL 및 쿠키만

The available `POST` methods let you map segments to [!UICONTROL URL] and [!UICONTROL cookie destinations] only. Currently, you cannot map segments to [!UICONTROL server-to-server destinations] with these [!DNL REST API] methods. 사용자 인터페이스를 대신 사용하십시오. However, the related destination `GET` methods let you retrieve information about [!UICONTROL server-to-server destinations] created in the user interface.

>[!MORE_ like_ this]
>
>* [대상](../../../features/destinations/destinations.md#destination-api-methods)
>* [대상 일련화](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [키-값 쌍을 설명했습니다.](../../../reference/key-value-pairs-explained.md)


## Map a Segment to a Non-Serialized URL Destination {#map-segment-non-serial}

A `POST` method that lets you map a segment to a non-serial [!UICONTROL URL] destination.

<!-- r_map_noserial_url.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 샘플 요청

별도의 언급이 없는 한 모든 요청 값이 필요합니다.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-07-04"
}
```

### 응답

```
{
   "mappingId":65334,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4033,
   "elementName":"Sample games",
   "elementDescription":"Sample games pixel",
   "elementStatus":"active",
   "createTime":1338940094000,
   "updateTime":1338940094000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "url":"https://adobe.com",
   "secureUrl":null,
   "tagCode":null,
   "secureTagCode":null,
   "traitAlias":null
}
```

## Map a Segment to a Serialized URL Destination {#map-segment-serial}

A `POST` method that lets you map a segment to a serialized [!UICONTROL URL] destination.

<!-- r_map_serialized_url.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`*`<dataOrderId>`*`/traits/`

### 샘플 요청

In the request, the `traitAlias` corresponds to the key in a key-value pair. 별도의 언급이 없는 한 모든 요청 값이 필요합니다.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"123"
}
```

### 응답

```
{
   "mappingId":65335,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4034,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338940401000,
   "updateTime":1338940401000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "url":"123",
   "secureUrl":"123",
   "tagCode":null,
   "secureTagCode":null,
   "traitAlias":"123"
}
```

## Map a Segment to a Cookie Destination: Single-Key, Non-Serialized {#map-segment-cookie-noserial}

A `POST` method that lets you map a segment to single-key, non-serialized [!UICONTROL cookie] destination.

<!-- r_map_cookie_noserial.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 샘플 요청

In the request, the `valueAlias` corresponds to the value in a key-value pair. 별도의 언급이 없는 한 모든 요청 값이 필요합니다.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "valueAlias":"123"
}
```

### 응답

```
{
   "destinationMappingId":65336,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4035,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338940704000,
   "updateTime":1338940704000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":1,
   "traitAlias":null,
   "valueAlias":"123"
}
```

## Map a Segment to a Cookie Destination: Multi-Key, Non-Serialized {#map-segment-cookie-multi-noserial}

A `POST` method that lets you map a segment to multi-key, non-serialized [!UICONTROL cookie] destination.

<!-- r_map_cookie_multikey_noserial.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 샘플 요청

In the request, the `traitAlias` and `valueAlias` set the key and the value respectively in a key-value pair. 별도의 언급이 없는 한 모든 요청 값이 필요합니다.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"type",
   "valueAlias":"123"
}
```

### 응답

```
{
   "mappingId":65338,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4037,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338941092000,
   "updateTime":1338941092000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":1,
   "traitAlias":"type",
   "valueAlias":"123"
}
```

## Map a Segment to a Cookie Destination: Multi-Key, Serialized {#map-segment-cookie-multi-serial}

A `POST` method that lets you map a segment to a multi-key, serialized [!UICONTROL cookie destination].

<!-- r_map_cookie_multikey_serialized.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 샘플 요청

In the request, the `traitAlias` and `valueAlias` set the key and the value in a key-value pair. 별도의 언급이 없는 한 모든 요청 값이 필요합니다.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"type",
   "valueAlias":"123"
}
```

### 응답

```
{
   "destinationMappingId":65340,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4038,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338941273000,
   "updateTime":1338941273000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":2,
   "traitAlias":"type",
   "valueAlias":"123"
}
```

## Map a Segment to a Server-to-Server Destination {#map-segment-s2s}

A `POST` method that lets you map a segment to an existing [!UICONTROL server-to-server] destination. Note, however, that you cannot create [!UICONTROL server-to-server] destinations with these currently available [!DNL API] methods.

<!-- r_map_segment_s2s.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 샘플 요청

In the request, the `traitAlias` corresponds to the key in a key-value pair. 별도의 언급이 없는 한 모든 요청 값이 필요합니다.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"123"
}
```

### 응답

```
{
   "destinationMappingId":65341,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":566,
   "elementName":"Sample",
   "elementDescription":"",
   "elementStatus":"active",
   "createTime":1338942118000,
   "updateTime":1338942118000,
   "crUID":308,
   "upUID":308,
   "sid":84326,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "traitAlias":"123"
}
```

## Bulk Create Destination Mappings {#bulk-create}

A `POST` method that lets you pass in an array of [!UICONTROL cookie] or [!UICONTROL URL] destination mappings.

<!-- r_bulk_create.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/bulk-create`

### 샘플 요청

별도의 언급이 없는 한 모든 요청 값이 필요합니다.

```
[
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
},
{
   "sid": 121070,
   "traitType":"SEGMENT",
   "url":"https://my.adobeconnect.com",
   "startDate":"2012-11-21"
}
]
```

### 응답

성공적인 응답은 만들어진 매핑 배열을 반환합니다.

```
[
    {
        "mappingId": 103454,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Case of the Mondays",
        "elementDescription": "test",
        "elementStatus": "active",
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 105123,
        "startDate": "2012-11-19",
        "endDate": null,
        "priority": null,
        "url": "https://adobe.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    },
    {
        "mappingId": 103455,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "orderId": 780,
        "elementName": "Test Trait",
        "elementDescription": "This trait",
        "elementStatus": 1,
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 121070,
        "startDate": "2012-11-20",
        "endDate": null,
        "priority": null,
        "url": "https://my.adobeconnect.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    }
]
```

## Add Multiple Segments to a Destination {#add-segments-dest}

A `POST` method that lets you map multiple segments to a destination.

<!-- r_add_segments_to_destination.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`bulk-create`

### 샘플 요청

배열에서 여러 대상 매핑을 만듭니다. 별도의 언급이 없는 한 모든 요청 값이 필요합니다.

```
[
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
},
{
   "sid": 121070,
   "traitType":"SEGMENT",
   "url":"https://my.adobeconnect.com",
   "startDate":"2012-11-21"
}
]
```

### 응답

만들어진 매핑 배열을 반환합니다.

```
[
    {
        "destinationMappingId": 103454,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Case of the Mondays",
        "elementDescription": "test",
        "elementStatus": "active",
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 105123,
        "startDate": "2012-11-19",
        "endDate": null,
        "priority": null,
        "url": "https://adobe.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    },
    {
        "traitToDataOrderId": 103455,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Test Trait",
        "elementDescription": "This trait",
        "elementStatus": 1,
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 121070,
        "startDate": "2012-11-20",
        "endDate": null,
        "priority": null,
        "url": "https://my.adobeconnect.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    }
]
```

## Update a Destination by Destination ID {#update-dest-data-order}

`PUT` 기존 대상을 업데이트할 수 `destinationId`있는 메서드입니다.

<!-- r_update_destination_data_order_id.xml -->

### 요청

`PUT https://api.demdex.com/v1/destinations/`*`<destinationId>`*

### 샘플 요청

별도의 언급이 없는 한 모든 요청 값이 필요합니다.

```
{
   "name":"Updated URL Destination (not serialized)",
   "description":"new description",
   "destinationType":"PUSH",
   "serializationEnabled":false
}
```

### 응답

```
{
    "destinationType": "PUSH",
    "destinationId": 780,
    "dataSourceId": null,
    "pid": 1099,
    "name": "Updated URL Destination (not serialized)",
    "description": "new description",
    "startDate": null,
    "endDate": null,
    "status": 1,
    "createTime": 1348851790000,
    "updateTime": 1353372029000,
    "crUID": 884,
    "upUID": 1065,
    "domainRestrictions":"all_domains",
    "tagType": 0,
    "serializationEnabled": false,
    "urlFormatString": null,
    "secureUrlFormatString": null,
    "delimiter": null,
    "mappings": null
}
```

## Update a Mapping to a Destination by Mapping ID {#update-mapping-dest-id}

A `PUT` method that lets you update a mapping to a destination by the specified `mappingId`.

<!-- r_update_destination_trait_data_order_id.xml -->

### 요청

`PUT https://api.demdex.com/v1/destinations/mappings/`*`<mappingId>`*

### 샘플 요청

별도의 언급이 없는 한 모든 요청 값이 필요합니다.

```
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
}
```

### 응답

```
{
    "mappingId": 103453,
    "traitType": "SEGMENT",
    "traitValue": 0,
    "destinationId": 780,
    "elementName": "sample",
    "elementDescription": "test",
    "elementStatus": "active",
    "createTime": 1353373005000,
    "updateTime": 1353373005000,
    "crUID": 1065,
    "upUID": 1065,
    "sid": 105123,
    "startDate": "2012-11-19",
    "endDate": null,
    "priority": null,
    "url": "https://www.adobe.com/send?%ALIAS%",
    "secureUrl": null,
    "tagCode": null,
    "secureTagCode": null,
    "traitAlias": null
}
```
