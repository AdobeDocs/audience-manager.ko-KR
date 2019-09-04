---
description: GET 또는 POST 메서드를 사용하여 DCS API로 데이터를 전송합니다.
seo-description: GET 또는 POST 메서드를 사용하여 DCS API로 데이터를 전송합니다.
seo-title: DCS API 메서드
solution: Audience Manager
title: DCS API 메서드
uuid: 6 E 407458-11 D 4-4342-A 84 A -512 AFA 5 FC 183
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# DCS API 메서드 {#dcs-api-methods}

Using data to the [!UICONTROL DCS][!DNL API] using `GET` or `POST` methods.

하나 또는 메서드 [!UICONTROL DCS] 중 하나를 사용하여 데이터를 보낼 `GET``POST` 수 있습니다. Curl를 사용하여 [아래의 샘플 호출을 살펴](https://curl.haxx.se/)보십시오. 세 가지 샘플 호출 모두에서 신호 `c_likes = famous popstar` 및 `c_loves = famous actress` 장치 프로파일에 `12345678901234567890123456789012345678`추가됩니다.

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. 이 방법으로 데이터를 보낼 [!UICONTROL DCS] 때 자리 표시자에 대한 실제 값을 대체합니다.

## GET: GET Data {#send-data-via-get}

호출에 허용되는 최대 크기는 `GET` 8 K 입니다.

<pre><code>curl -i "<i>yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&amp;d_rtbd=jsonc_likes=famous%20popstar&amp;c_loves=famous%20actress</i><i></i><i></i><i></i>"</code></pre>

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
