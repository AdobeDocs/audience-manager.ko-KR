---
description: GET 또는 POST 메서드를 사용하여 데이터를 DCS API로 보냅니다.
seo-description: GET 또는 POST 메서드를 사용하여 데이터를 DCS API로 보냅니다.
seo-title: DCS API 메서드
solution: Audience Manager
title: DCS API 메서드
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
translation-type: tm+mt
source-git-commit: bdea2609b84d7f80d67452b4c43e11cbef01a368

---


# DCS API 메서드 {#dcs-api-methods}

또는 메서드를 사용하여 데이터를 [!UICONTROL DCS] [!DNL API] 로 `GET` 보냅니다 `POST` .

또는 방법 중 하나를 사용하여 데이터를 [!UICONTROL DCS] 으로 보낼 `GET` 수 `POST` 있습니다. 아래 [curl](https://curl.haxx.se/)샘플을 살펴보십시오. 세 가지 샘플 호출 모두에서 신호를 `c_likes = famous popstar` 장치 프로파일과 `c_loves = famous actress` 함께 추가하고 `12345678901234567890123456789012345678`있습니다.


## GET을 통해 데이터 보내기 {#send-data-via-get}

최대 `GET` 호출 허용 크기는 8K입니다.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## POST 파섹 {#send-data-via-post}

다음 `POST` 방법을 사용하여 데이터를 전송하기 위한 요구 사항을 참조하십시오.

* 허용되는 최대 크기는 32K입니다.
* 컨텐츠 유형을 로 `application/x-www-form-urlencoded`설정합니다.

### 샘플 호출

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
