---
description: 이러한 RESTful API 메서드를 사용하여 대상을 만듭니다.
seo-description: Create destinations with these RESTful API methods.
seo-title: Create Destinations
solution: Audience Manager
title: 대상 만들기
uuid: 12f04151-ad0e-4cb6-8f3b-b5c427dc2cef
feature: API
exl-id: bae0f304-0ff3-4c5f-b432-19aef61d9d10
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 9%

---

# 대상 만들기 {#create-destinations}

다음을 사용하여 대상 만들기 [!UICONTROL RESTful API] 메서드를 사용합니다.

<!-- c_create_destinations.xml -->

## 지원되는 대상 유형: URL 및 쿠키만

사용 가능한 `POST` 메서드를 사용하면 을 만들 수 있습니다. [!UICONTROL URL] 및 [!UICONTROL cookie destinations] 만 해당. 현재 다음을 만들 수 없습니다. [!UICONTROL server-to-server destinations] 다음 포함 [!DNL REST API] 메서드를 사용합니다. 그러나 관련 대상 `GET` 메서드를 사용하면 다음에 대한 정보를 검색할 수 있습니다. [!UICONTROL server-to-server destinations] 사용자 인터페이스에서 만들어집니다.

## 비-직렬 URL 대상 만들기 {#create-nonserial-dest}

A `POST` 단일 키-값 쌍으로 구성된 세그먼트를 받는 대상을 만들 수 있는 메서드(예: `gender=male` 또는 `gender=female`).

<!-- r_create_nonserial_destination.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`

### 샘플 요청

이 요청은 단일 대상을 만듭니다. 별도로 지정하지 않는 한 모든 요청 값이 필요합니다.

```
{ 
   "name":"Sample URL Destination (not serialized)",
   "description":"",
   "destinationType":"PUSH",
   "serializationEnabled":false
}
```

### 응답

성공적인 요청이 반환됩니다. `201 created` 그리고 목적지도요

```
{ 
   "destinationType":"PUSH", 
   "destinationId":4033, 
   "dataSourceId":null, 
   "pid":1099, 
   "name":"Sample URL Destination (not serialized)", 
   "description":"", 
   "startDate":null, 
   "endDate":null, 
   "status":"ACTIVE", 
   "destinationType":"PUSH", 
   "createTime":1338937116000, 
   "updateTime":1338937116000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "tagType":0, 
   "serializationEnabled":false, 
   "urlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "secureUrlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "delimiter":null,
   "mappings":null
} 
```

## 직렬화된 URL 대상 만들기 {#create-serial-url-dest}

A `POST` 단일 키와 연관된 여러 값을 받는 대상을 만들 수 있는 메서드(예: `color=blue, red, green`).

<!-- r_create_serial_url_destination.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`

### 샘플 요청

보안 지정 [!DNL URL] 대상에 전달된 키-값 쌍의 구분 기호입니다. 별도로 지정하지 않는 한 모든 요청 값이 필요합니다.

```
{ 
   "name":"Sample URL Destination (Serialized)",
   "description":"",
   "destinationType":"PUSH",
   "serializationEnabled":true,
   "urlFormatString":"https://www.adobe.com/send?data=%ALIAS%",
   "secureUrlFormatString":"https://www.adobe.com/%ALIAS%",
   "delimiter":","
}
```

### 응답

성공한 업데이트가 응답 코드를 반환합니다. `201 created` 그리고 목적지도요

```
{ 
   "destinationType":"PUSH", 
   "destinationId":4034, 
   "dataSourceId":null, 
   "pid":1099, 
   "name":"Sample URL Destination (Serialized)", 
   "description":"", 
   "startDate":null, 
   "endDate":null, 
   "status":"active", 
   "destinationType":"PUSH", 
   "createTime":1338937420000, 
   "updateTime":1338937420000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "tagType":0, 
   "serializationEnabled":true, 
   "urlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "secureUrlFormatString":"https://www.adobe.com/%ALIAS%", 
   "delimiter":"-", 
   "mappings":null 
}
```

## 쿠키 대상 만들기: 단일 키, 직렬화되지 않음 {#create-cookie-dest-single}

A `POST` 을(를) 생성할 수 있는 메서드 [!UICONTROL cookie destination] 는 단일 키-값 쌍으로 구성된 세그먼트를 허용합니다(예: `gender=male` 또는 `gender=female`).

<!-- r_cookie_destination_singlekey_noserial.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`

### 샘플 요청

별도로 지정하지 않는 한 모든 요청 값이 필요합니다.

```
{ 
   "name":"Cookie Destination Single Key Not Serialized",
   "destinationType":"ADS",
   "adServerTypeID":1,
   "cookieName":"adobe",
   "cnameDomain":"adobe.com",
   "maxSize":"2048",
   "ttl":"0",
   "domainRestrictions":"inclusion",
   "siteIDs":[
      312
   ],
   "formatType":"single_key",
   "singleKey":"key",
   "keySeparator":"=",
   "valueSeparator":",",
   "serializationEnabled":false
}
```

### 응답

성공한 업데이트가 응답 코드를 반환합니다. `201 created` 그리고 목적지도요

```
{ 
   "destinationType":"ADS", 
   "destinationId":4035, 
   "pid":1099, 
   "name":"Cookie Destination Single Key Not Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338937984000, 
   "updateTime":1338937984000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"inclusion", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "singleKey":"key", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"single_key", 
   "transferMethod":0, 
   "serializationEnabled":false, 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
      312 
   ], 
   "uparamEnabled":false
} 
```

## 쿠키 대상 만들기: 단일 키, 직렬화됨 {#create-cookie-dest-single-serial}

A `POST` 단일 키와 연관된 여러 값을 받는 대상을 만들 수 있는 메서드(예: `color=blue, red, green`).

<!-- r_cookie_destination_singlekey_serial.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`

### 샘플 요청

별도로 지정하지 않는 한 모든 요청 값이 필요합니다.

```
{ 
   "name":"Cookie Destination Single Key Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains", 
   "siteIDs":[ 
 
   ], 
   "formatType":"single_key", 
   "singleKey":"k", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":true, 
   "serializationSeparator":"#" 
}
```

### 응답

성공한 업데이트가 응답 코드를 반환합니다. `201 created` 그리고 목적지도요

```
{ 
   "destinationType":"ADS", 
   "destinationId":4036, 
   "pid":1099, 
   "name":"Cookie Destination Single Key Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338938329000, 
   "updateTime":1338938329000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "singleKey":"k", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"single_key", 
   "transferMethod":0, 
   "serializationEnabled":true, 
   "serializationSeparator":"#", 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
 
   ], 
   "uparamEnabled":false
}
```

## 쿠키 대상 만들기: 다중 키, 직렬화되지 않음 {#create-cookie-dest-multi}

A `POST` 다른 값을 가진 여러 키가 포함된 세그먼트를 허용하는 대상을 만들 수 있는 메서드(예: `gender=male; gender=female; color=blue; color=red`).

<!-- r_create_cookie_multikey_noserial.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`

### 샘플 요청

별도로 지정하지 않는 한 모든 요청 값이 필요합니다.

```
{ 
   "name":"Ad Server Multi-Key Not Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains", 
   "siteIDs":[ 
  
   ], 
   "formatType":"key_value", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":false 
}
```

### 응답

성공한 업데이트가 응답 코드를 반환합니다. `201 created` 그리고 목적지도요

```
{ 
   "destinationType":"ADS", 
   "destinationId":4037, 
   "pid":1099, 
   "name":"Ad Server Multi-Key Not Serialized", 
   "status":1, 
   "destinationType":"ADS", 
   "createTime":1338938666000, 
   "updateTime":1338938666000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"key_value", 
   "transferMethod":0, 
   "serializationEnabled":false, 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
  
   ], 
   "uparamEnabled":false 
}
```

## 쿠키 대상 만들기: 다중 키, 직렬화됨 {#create-cookie-dest-multi-serial}

A `POST` 여러 키 및 값이 포함된 세그먼트를 허용하는 대상을 만들 수 있는 메서드(예: `gender=male, female; color=blue, red, green`).

<!-- r_cookie_destination_multikey_serial.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`

### 샘플 요청

별도로 지정하지 않는 한 모든 요청 값이 필요합니다.

```
{ 
   "name":"Cookie Destination Multi-Key Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains",
   "siteIDs":[ 
 
   ], 
   "formatType":"key_value", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":true, 
   "serializationSeparator":"#" 
}
```

### 응답

성공한 업데이트가 응답 코드를 반환합니다. `201 created` 그리고 목적지도요

```
{ 
   "destinationType":"ADS", 
   "destinationId":4038, 
   "pid":1099, 
   "name":"Ad Server Multi-Key Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338938872000, 
   "updateTime":1338938872000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"key_value", 
   "transferMethod":0, 
   "serializationEnabled":true, 
   "serializationSeparator":"#", 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
 
   ], 
   "uparamEnabled":false 
}
```

>[!MORELIKETHIS]
>
>* [대상](../../../features/destinations/destinations.md)
>* [대상 직렬화](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [키-값 쌍 설명](../../../reference/key-value-pairs-explained.md)

