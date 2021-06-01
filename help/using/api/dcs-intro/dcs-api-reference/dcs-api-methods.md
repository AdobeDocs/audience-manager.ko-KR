---
description: GET 또는 POST 방법을 사용하여 DCS API로 데이터를 보냅니다.
seo-description: GET 또는 POST 방법을 사용하여 DCS API로 데이터를 보냅니다.
seo-title: DCS API 메서드
solution: Audience Manager
title: DCS API 메서드
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
exl-id: 258994e1-6b15-4ae1-9e1f-c6e0685350c1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 6%

---

# [!DNL DCS] [!DNL API] 메서드 {#dcs-api-methods}

`GET` 또는 `POST` 메서드를 사용하여 [!DNL DCS] [!DNL API] 로 데이터를 보냅니다.

`GET` 또는 `POST` 메서드 중 하나를 사용하여 [!DNL DCS]에 데이터를 보낼 수 있습니다. [curl](https://curl.haxx.se/)을 사용하여 아래의 샘플 호출을 살펴보십시오. 세 개의 샘플 호출 모두에서 신호 `c_likes = famous popstar` 및 `c_loves = famous actress`를 장치 프로필 `12345678901234567890123456789012345678`에 추가하고 있습니다.

## [!DNL GET] {#send-data-via-get}을 통해 데이터 보내기

`GET` 호출에 대해 허용되는 최대 크기는 8K입니다.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## [!DNL POST] {#send-data-via-post}을 통해 데이터 보내기

`POST` 메서드를 사용하여 데이터를 전송하기 위한 요구 사항을 확인합니다.

* 허용되는 최대 크기는 32K입니다.
* 컨텐츠 유형을 `application/x-www-form-urlencoded`(으)로 설정합니다.

### 샘플 호출

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
