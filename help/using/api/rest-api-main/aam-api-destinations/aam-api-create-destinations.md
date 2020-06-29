---
description: 이러한 RESTful API 메서드로 대상을 만듭니다.
seo-description: 이러한 RESTful API 메서드로 대상을 만듭니다.
seo-title: 대상 만들기
solution: Audience Manager
title: 대상 만들기
uuid: 12f04151-ad0e-4cb6-8f3b-b5c427dc2cef
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 9%

---


# 대상 만들기 {#create-destinations}

이러한 방법으로 대상을 [!UICONTROL RESTful API] 만듭니다.

<!-- c_create_destinations.xml -->

## 지원되는 대상 유형: URL 및 쿠키만

사용 가능한 `POST` 방법을 사용하면 [!UICONTROL URL] 및 [!UICONTROL cookie destinations] 만 만들 수 있습니다. 현재 이러한 방법 [!UICONTROL server-to-server destinations] 으로 만들 수 [!DNL REST API] 없습니다. 하지만 관련 대상 `GET` 방법을 사용하면 사용자 인터페이스에서 만든 정보를 검색할 [!UICONTROL server-to-server destinations] 수 있습니다.

## 비직렬 URL 대상 만들기 {#create-nonserial-dest}

단일 키-값 쌍(예: `POST` 또는 `gender=male` `gender=female`)으로 구성된 세그먼트를 허용하는 대상을 만들 수 있는 방법입니다.

<!-- r_create_nonserial_destination.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`

### 샘플 요청

이 요청은 단일 대상을 만듭니다. 별도의 설명이 없는 한 모든 요청 값이 필요합니다.

```
{ 
   "name":"Sample URL Destination (not serialized)",
   "description":"",
   "destinationType":"PUSH",
   "serializationEnabled":false
}
```

### 응답

요청이 성공적으로 반환되면 `201 created` 대상이 반환됩니다.

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

단일 키와 연관된 여러 값을 허용하는 대상을 만들 수 있는 `POST` `color=blue, red, green`방법입니다.

<!-- r_create_serial_url_destination.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`

### 샘플 요청

대상에 전달된 키 값 쌍에 대한 보안 [!DNL URL] 및 구분 기호를 지정합니다. 별도의 설명이 없는 한 모든 요청 값이 필요합니다.

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

업데이트가 성공하면 응답 코드 `201 created` 와 대상이 반환됩니다.

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

## 쿠키 대상 만들기: 단일 키, 일련 번호가 아님 {#create-cookie-dest-single}

단일 키-값 쌍(예: `POST` 또는 [!UICONTROL cookie destination] `gender=male` `gender=female`)으로 구성된 세그먼트를 허용하는 방법을 만드는 데 사용할 수 있습니다.

<!-- r_cookie_destination_singlekey_noserial.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`

### 샘플 요청

별도의 설명이 없는 한 모든 요청 값이 필요합니다.

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

업데이트가 성공하면 응답 코드 `201 created` 와 대상이 반환됩니다.

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

## 쿠키 대상 만들기: 단일 키, 일련 번호 {#create-cookie-dest-single-serial}

단일 키와 연관된 여러 값을 허용하는 대상을 만들 수 있는 `POST` `color=blue, red, green`방법입니다.

<!-- r_cookie_destination_singlekey_serial.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`

### 샘플 요청

별도의 설명이 없는 한 모든 요청 값이 필요합니다.

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

업데이트가 성공하면 응답 코드 `201 created` 와 대상이 반환됩니다.

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

## 쿠키 대상 만들기: 다중 키, 일련 번호가 지정되지 않음 {#create-cookie-dest-multi}

값이 다른 여러 개의 키가 포함된 세그먼트를 허용하는 대상을 만들 수 있는 `POST` `gender=male; gender=female; color=blue; color=red`방법입니다.

<!-- r_create_cookie_multikey_noserial.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`

### 샘플 요청

별도의 설명이 없는 한 모든 요청 값이 필요합니다.

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

업데이트가 성공하면 응답 코드 `201 created` 와 대상이 반환됩니다.

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

## 쿠키 대상 만들기: 다중 키, 직렬화 {#create-cookie-dest-multi-serial}

여러 개의 키와 값(예:, `POST` `gender=male, female; color=blue, red, green`)을 포함하는 세그먼트를 허용하는 대상을 만들 수 있는 방법입니다.

<!-- r_cookie_destination_multikey_serial.xml -->

### 요청

`POST https://api.demdex.com/v1/destinations/`

### 샘플 요청

별도의 설명이 없는 한 모든 요청 값이 필요합니다.

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

업데이트가 성공하면 응답 코드 `201 created` 와 대상이 반환됩니다.

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
>* [대상 정리](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [키-값 쌍 설명](../../../reference/key-value-pairs-explained.md)

