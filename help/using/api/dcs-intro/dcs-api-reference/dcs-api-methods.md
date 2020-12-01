---
description: GET 또는 POST 방법을 사용하여 데이터를 DCS API로 보냅니다.
seo-description: GET 또는 POST 방법을 사용하여 데이터를 DCS API로 보냅니다.
seo-title: DCS API 메서드
solution: Audience Manager
title: DCS API 메서드
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 6%

---


# [!DNL DCS] [!DNL API] 메서드 {#dcs-api-methods}

`GET` 또는 `POST` 메서드를 사용하여 데이터를 [!DNL DCS] [!DNL API]으로 보냅니다.

`GET` 또는 `POST` 메서드 중 하나를 사용하여 데이터를 [!DNL DCS]으로 보낼 수 있습니다. [curl](https://curl.haxx.se/)을 사용하여 아래 샘플 호출을 확인하십시오. 세 가지 샘플 호출 모두에서 장치 프로파일 `12345678901234567890123456789012345678`에 신호 `c_likes = famous popstar` 및 `c_loves = famous actress`를 추가합니다.

## [!DNL GET] {#send-data-via-get}을(를) 통해 데이터 전송

`GET` 호출에 대해 허용되는 최대 크기는 8K입니다.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## [!DNL POST] {#send-data-via-post}을(를) 통해 데이터 전송

`POST` 메서드를 사용하여 데이터를 전송하기 위한 요구 사항을 참조하십시오.

* 허용되는 최대 크기는 32K입니다.
* 콘텐츠 형식을 `application/x-www-form-urlencoded`으로 설정합니다.

### 샘플 호출

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
