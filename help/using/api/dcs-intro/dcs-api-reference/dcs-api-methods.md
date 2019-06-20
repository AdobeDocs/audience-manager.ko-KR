---
description: GET 또는 POST 메서드를 사용하여 DCS API로 데이터를 전송합니다.
seo-description: GET 또는 POST 메서드를 사용하여 DCS API로 데이터를 전송합니다.
seo-title: DCS API 메서드
solution: Audience Manager
title: DCS API 메서드
uuid: 6 E 407458-11 D 4-4342-A 84 A -512 AFA 5 FC 183
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# DCS API Methods {#dcs-api-methods}

Send data to the [!UICONTROL DCS] [!DNL API] using `GET` or `POST` methods.

You can send data to the [!UICONTROL DCS] using either one of the `GET` or `POST` methods. Take a look at the sample calls below, using [curl](https://curl.haxx.se/). In all three sample calls, we are adding the signals `c_likes = famous popstar` and `c_loves = famous actress` to the device profile `12345678901234567890123456789012345678`.

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. Substitute a real value for the placeholder when you send data to the [!UICONTROL DCS] with this method.

## Send Data via GET {#send-data-via-get}

Note that the maximum allowed size for `GET` calls is 8K.

<pre><code>curl -i "<i>yourcompany.demdex.net/event</i>?
d_uuid=<i>12345678901234567890123456789012345678</i>&amp;d_rtbd=json&amp;<i>c_likes=famous%20popstar</i>&amp;<i>c_loves=famous%20actress</i>"
</code></pre>

## Send Data via POST {#send-data-via-post}

Note the requirements for sending data using the `POST` method:

* 최대 허용 크기는 32 K 입니다.
* Set the content type to `application/x-www-form-urlencoded`.

### 샘플 호출

<pre><code>curl -x post\ 
 https://yourcompany.demdex.net/event<i></i>\ 
 -h'content-type: application/x-www-form-urlencoded '\ 
 -d'<i>c_ likes = famous % 20 popstar</i>&amp;<i>c_ loves = famous % 20 Queen</i>&amp;<i>D_ UUID = 12345678901234567890123456789012345678</i>'</code>
</pre>

<pre><code>curl -x post\ 
 https://yourcompany.demdex.net/event<i></i>\ 
 -h'content-type: application/x-www-form-urlencoded '\ 
 -d'<i>c_ likes = famous % 20 popstar</i>&amp; <i>c_ loves = famous % 20 Queen</i>&amp;<i>D_ UUID = 12345678901234567890123456789012345678</i>'</code>
</pre>
