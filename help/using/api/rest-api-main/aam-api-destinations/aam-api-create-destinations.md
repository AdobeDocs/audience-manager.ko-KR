---
description: 이러한 Restful API 메서드로 대상을 만듭니다.
seo-description: 이러한 Restful API 메서드로 대상을 만듭니다.
seo-title: 대상 만들기
solution: Audience Manager
title: 대상 만들기
uuid: 12 f 04151-ad 0 e -4 cb 6-8 f 3 b-b 5 c 427 dc 2 cef
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create Destinations {#create-destinations}

Create destinations with these [!UICONTROL RESTful API] methods.

<!-- c_create_destinations.xml -->

## 지원되는 대상 유형: URL 및 쿠키만

The available `POST` methods let you create [!UICONTROL URL] and [!UICONTROL cookie destinations] only. Currently, you cannot create [!UICONTROL server-to-server destinations] with these [!DNL REST API] methods. However, the related destination `GET` methods let you retrieve information about [!UICONTROL server-to-server destinations] created in the user interface.

>[!MORE_ like_ this]
>
>* [대상](../../../features/destinations/destinations.md#destination-api-methods)
>* [대상 일련화](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [키-값 쌍을 설명했습니다.](../../../reference/key-value-pairs-explained.md)


## Create a Non-Serial URL Destination {#create-nonserial-dest}

A `POST` method that lets you create a destination that accepts segments composed of single key-value pairs (e.g., `gender=male` or `gender=female`).

<!-- r_create_nonserial_destination.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`

### 샘플 요청

이 요청은 단일 대상을 만듭니다. 별도의 언급이 없는 한 모든 요청 값이 필요합니다.

```
{ 
   "name":"Sample URL Destination (not serialized)",
   "description":"",
   "destinationType":"PUSH",
   "serializationEnabled":false
}
```

### 응답

A successful request returns `201 created` and the destination.

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

>[!MORE_ like_ this]
>
>* [대상 일련화](../../../features/destinations/key-value-pairs.md#destination-serialized)


## Create a Serialized URL Destination {#create-serial-url-dest}

A `POST` method that lets you create a destination that accepts multiple values associated with a single key (e.g., `color=blue, red, green`).

<!-- r_create_serial_url_destination.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`

### 샘플 요청

Specify the secure [!DNL URL] and delimiter for the key-value pair passed in to the destination. 별도의 언급이 없는 한 모든 요청 값이 필요합니다.

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

A successful update returns response code `201 created` and the destination.

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

>[!MORE_ like_ this]
>
>* [대상 일련화](../../../features/destinations/key-value-pairs.md#destination-serialized)


## Create a Cookie Destination: Single-Key, Non-Serialized {#create-cookie-dest-single}

A `POST` method that lets you create a [!UICONTROL cookie destination] that accepts segments composed of single key-value pairs (e.g., `gender=male` or `gender=female`).

<!-- r_cookie_destination_singlekey_noserial.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`

### 샘플 요청

별도의 언급이 없는 한 모든 요청 값이 필요합니다.

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

A successful update returns response code `201 created` and the destination.

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

>[!MORE_ like_ this]
>
>* [대상 일련화](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [키-값 쌍을 설명했습니다.](../../../reference/key-value-pairs-explained.md)


## Create a Cookie Destination: Single Key, Serialized {#create-cookie-dest-single-serial}

A `POST` method that lets you create a destination that accepts multiple values associated with a single key (e.g., `color=blue, red, green`).

<!-- r_cookie_destination_singlekey_serial.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`

### 샘플 요청

별도의 언급이 없는 한 모든 요청 값이 필요합니다.

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

A successful update returns response code `201 created` and the destination.

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

>[!MORE_ like_ this]
>
>* [대상 일련화](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [키-값 쌍을 설명했습니다.](../../../reference/key-value-pairs-explained.md)


## Create a Cookie Destination: Multi-Key, Non-Serialized {#create-cookie-dest-multi}

A `POST` method that lets you create a destination that accepts segments that contain multiple keys with different values (e.g., `gender=male; gender=female; color=blue; color=red`).

<!-- r_create_cookie_multikey_noserial.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`

### 샘플 요청

별도의 언급이 없는 한 모든 요청 값이 필요합니다.

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

A successful update returns response code `201 created` and the destination.

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

## Create a Cookie Destination: Multi-Key, Serialized {#create-cookie-dest-multi-serial}

A `POST` method that lets you create a destination that accepts segments that contain multiple keys and values (e.g., `gender=male, female; color=blue, red, green`).

<!-- r_cookie_destination_multikey_serial.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`

### 샘플 요청

별도의 언급이 없는 한 모든 요청 값이 필요합니다.

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

A successful update returns response code `201 created` and the destination.

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

>[!MORE_ like_ this]
>
>* [대상 일련화](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [키-값 쌍을 설명했습니다.](../../../reference/key-value-pairs-explained.md)

