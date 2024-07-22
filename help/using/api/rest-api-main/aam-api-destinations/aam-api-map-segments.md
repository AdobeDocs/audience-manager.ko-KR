---
description: 이러한 RESTful API 메서드를 사용하여 세그먼트를 대상에 매핑합니다.
seo-description: Map segments to destinations with these RESTful API methods.
seo-title: Map Segments to a Destination
solution: Audience Manager
title: 대상에 세그먼트 매핑
uuid: 35358ace-3082-4e86-a6eb-d77281af6d7e
feature: API
exl-id: 906df6c5-f878-48e6-a804-eb5b4407f304
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 6%

---

# 대상에 세그먼트 매핑 {#map-segments-to-a-destination}

이러한 [!DNL RESTful API] 메서드를 사용하여 세그먼트를 대상에 매핑합니다.

<!-- c_api_map_seg_dest.xml -->

## 지원되는 대상 유형: URL 및 쿠키만

사용 가능한 `POST` 메서드를 사용하면 세그먼트를 [!UICONTROL URL] 및 [!UICONTROL cookie destinations]에 매핑할 수 있습니다. 현재 이러한 [!DNL REST API] 메서드로 세그먼트를 [!UICONTROL server-to-server destinations]에 매핑할 수 없습니다. 대신 사용자 인터페이스를 사용하십시오. 그러나 관련 대상 `GET` 메서드를 사용하면 사용자 인터페이스에서 만든 [!UICONTROL server-to-server destinations]에 대한 정보를 검색할 수 있습니다.

## 세그먼트를 일련화되지 않은 URL 대상에 매핑 {#map-segment-non-serial}

세그먼트를 비직렬 [!UICONTROL URL] 대상에 매핑할 수 있는 `POST` 메서드.

<!-- r_map_noserial_url.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 샘플 요청

별도로 지정하지 않는 한 모든 요청 값이 필요합니다.

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

## 일련화된 URL 대상에 세그먼트 매핑 {#map-segment-serial}

세그먼트를 직렬화된 [!UICONTROL URL] 대상에 매핑할 수 있는 `POST` 메서드입니다.

<!-- r_map_serialized_url.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`*`<dataOrderId>`*`/traits/`

### 샘플 요청

요청에서 `traitAlias`은(는) 키-값 쌍의 키에 해당합니다. 별도로 지정하지 않는 한 모든 요청 값이 필요합니다.

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

## 세그먼트를 쿠키 대상에 매핑: 단일 키, 직렬화되지 않음 {#map-segment-cookie-noserial}

세그먼트를 단일 키의 직렬화되지 않은 [!UICONTROL cookie] 대상에 매핑할 수 있는 `POST` 메서드입니다.

<!-- r_map_cookie_noserial.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 샘플 요청

요청에서 `valueAlias`은(는) 키-값 쌍의 값에 해당합니다. 별도로 지정하지 않는 한 모든 요청 값이 필요합니다.

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

## 세그먼트를 쿠키 대상에 매핑: 다중 키, 일련화되지 않음 {#map-segment-cookie-multi-noserial}

세그먼트를 다중 키, 직렬화되지 않은 [!UICONTROL cookie] 대상에 매핑할 수 있는 `POST` 메서드입니다.

<!-- r_map_cookie_multikey_noserial.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 샘플 요청

요청에서 `traitAlias` 및 `valueAlias`은(는) 키-값 쌍으로 키와 값을 각각 설정합니다. 별도로 지정하지 않는 한 모든 요청 값이 필요합니다.

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

## 세그먼트를 쿠키 대상에 매핑: 다중 키, 직렬화됨 {#map-segment-cookie-multi-serial}

세그먼트를 다중 키에 매핑할 수 있는 `POST` 메서드로, 직렬화된 [!UICONTROL cookie destination]입니다.

<!-- r_map_cookie_multikey_serialized.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 샘플 요청

요청에서 `traitAlias` 및 `valueAlias`이(가) 키-값 쌍으로 키와 값을 설정합니다. 별도로 지정하지 않는 한 모든 요청 값이 필요합니다.

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

## 세그먼트를 서버 간 대상에 매핑 {#map-segment-s2s}

기존 [!UICONTROL server-to-server] 대상에 세그먼트를 매핑할 수 있는 `POST` 메서드입니다. 그러나 현재 사용 가능한 [!DNL API] 메서드로 [!UICONTROL server-to-server] 대상을 만들 수는 없습니다.

<!-- r_map_segment_s2s.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 샘플 요청

요청에서 `traitAlias`은(는) 키-값 쌍의 키에 해당합니다. 별도로 지정하지 않는 한 모든 요청 값이 필요합니다.

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

## 대상 매핑 벌크 만들기 {#bulk-create}

[!UICONTROL cookie] 또는 [!UICONTROL URL] 대상 매핑의 배열을 전달할 수 있는 `POST` 메서드입니다.

<!-- r_bulk_create.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/bulk-create`

### 샘플 요청

별도로 지정하지 않는 한 모든 요청 값이 필요합니다.

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

성공한 응답은 생성된 매핑 배열을 반환합니다.

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

## 대상에 여러 세그먼트 추가 {#add-segments-dest}

여러 세그먼트를 대상에 매핑할 수 있는 `POST` 메서드입니다.

<!-- r_add_segments_to_destination.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`bulk-create`

### 샘플 요청

배열에 여러 대상 매핑을 만듭니다. 별도로 지정하지 않는 한 모든 요청 값이 필요합니다.

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

생성된 매핑 배열을 반환합니다.

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

## 대상 ID별 대상 업데이트 {#update-dest-data-order}

`destinationId`에 의해 기존 대상을 업데이트할 수 있는 `PUT` 메서드입니다.

<!-- r_update_destination_data_order_id.xml -->

### 요청

`PUT https://api.demdex.com/v1/destinations/`*`<destinationId>`*

### 샘플 요청

별도로 지정하지 않는 한 모든 요청 값이 필요합니다.

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

## 매핑 ID로 대상에 대한 매핑 업데이트 {#update-mapping-dest-id}

지정한 `mappingId`까지 대상에 대한 매핑을 업데이트할 수 있는 `PUT` 메서드입니다.

<!-- r_update_destination_trait_data_order_id.xml -->

### 요청

`PUT https://api.demdex.com/v1/destinations/mappings/`*`<mappingId>`*

### 샘플 요청

별도로 지정하지 않는 한 모든 요청 값이 필요합니다.

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

>[!MORELIKETHIS]
>
>* [대상](../../../features/destinations/destinations.md)
>* [대상 직렬화](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [키-값 쌍 설명](../../../reference/key-value-pairs-explained.md)
