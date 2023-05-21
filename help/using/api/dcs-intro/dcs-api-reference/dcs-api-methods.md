---
description: GET 또는 POST 메서드를 사용하여 DCS API로 데이터를 보냅니다.
seo-description: Send data to the DCS API using GET or POST methods.
seo-title: DCS API Methods
solution: Audience Manager
title: DCS API 메서드
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
exl-id: 258994e1-6b15-4ae1-9e1f-c6e0685350c1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 4%

---

# [!DNL DCS] [!DNL API] 메서드 {#dcs-api-methods}

에 데이터 보내기 [!DNL DCS] [!DNL API] 사용 `GET` 또는 `POST` 메서드를 사용합니다.

로 데이터를 보낼 수 있습니다. [!DNL DCS] 다음 중 하나를 사용합니다. `GET` 또는 `POST` 메서드를 사용합니다. 를 사용하여 아래 샘플 호출을 살펴보십시오. [컬](https://curl.haxx.se/). 세 가지 샘플 호출 모두에서 신호를 추가하고 있습니다 `c_likes = famous popstar` 및 `c_loves = famous actress` 장치 프로필로 `12345678901234567890123456789012345678`.

## 다음을 통해 데이터 보내기 [!DNL GET] {#send-data-via-get}

에 대해 허용되는 최대 크기 `GET` 호출은 8K입니다.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## 다음을 통해 데이터 보내기 [!DNL POST] {#send-data-via-post}

를 사용하여 데이터를 전송하기 위한 요구 사항 을 참고하십시오. `POST` 방법:

* 최대 허용 크기는 32K입니다.
* 콘텐츠 유형을 다음으로 설정 `application/x-www-form-urlencoded`.

### 샘플 호출

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
