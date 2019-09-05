---
description: GET 또는 POST 메서드를 사용하여 DCS API로 데이터를 전송합니다.
seo-description: GET 또는 POST 메서드를 사용하여 DCS API로 데이터를 전송합니다.
seo-title: DCS API 메서드
solution: Audience Manager
title: DCS API 메서드
uuid: 6 E 407458-11 D 4-4342-A 84 A -512 AFA 5 FC 183
translation-type: tm+mt
source-git-commit: bdea2609b84d7f80d67452b4c43e11cbef01a368

---


# DCS API 메서드 {#dcs-api-methods}

Using data to the [!UICONTROL DCS][!DNL API] using `GET` or `POST` methods.

하나 또는 메서드 [!UICONTROL DCS] 중 하나를 사용하여 데이터를 보낼 `GET``POST` 수 있습니다. Curl를 사용하여 [아래의 샘플 호출을 살펴](https://curl.haxx.se/)보십시오. 세 가지 샘플 호출 모두에서 신호 `c_likes = famous popstar` 및 `c_loves = famous actress` 장치 프로파일에 `12345678901234567890123456789012345678`추가됩니다.


## GET: GET Data {#send-data-via-get}

호출에 허용되는 최대 크기는 `GET` 8 K 입니다.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## POST를 통해 데이터 보내기 {#send-data-via-post}

메서드를 사용하여 데이터를 전송하는 요구 사항을 `POST` 참조하십시오.

* 최대 허용 크기는 32 K 입니다.
* 컨텐츠 유형을 다음으로 설정합니다 `application/x-www-form-urlencoded`.

### 샘플 호출

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
