---
description: GET 또는 POST 메서드를 사용하여 데이터를 DCS API로 보냅니다.
seo-description: GET 또는 POST 메서드를 사용하여 데이터를 DCS API로 보냅니다.
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

또는 방법을 사용하여 [!DNL DCS] 데이터 [!DNL API] 를 `GET` 로 `POST` 보냅니다.

또는 방법 중 하나를 사용하여 데이터 [!DNL DCS] 를 `GET` 로 보낼 수 `POST` 있습니다. 말림 [을 사용하여 아래 샘플 호출을 살펴보십시오](https://curl.haxx.se/). 세 가지 샘플 호출 모두에서 신호 `c_likes = famous popstar` 와 장치 프로파일 `c_loves = famous actress` 에 신호를 추가합니다 `12345678901234567890123456789012345678`.

## 데이터 전송 방법 [!DNL GET] {#send-data-via-get}

호출에 대해 허용되는 최대 크기는 8K `GET` 입니다.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## 데이터 전송 방법 [!DNL POST] {#send-data-via-post}

다음 방법을 사용하여 데이터를 전송하기 위한 요구 사항을 `POST` 참조하십시오.

* 허용되는 최대 크기는 32K입니다.
* 콘텐트 유형을 로 설정합니다 `application/x-www-form-urlencoded`.

### 샘플 호출

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
