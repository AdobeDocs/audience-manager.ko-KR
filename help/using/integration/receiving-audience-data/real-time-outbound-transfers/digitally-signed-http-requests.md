---
description: Audience Manager 에서는 유효성을 위해 HTTP 서버-서버 요청이 디지털 서명을 받아야 합니다. 이 문서에서는 개인 키를 사용하여 HTTP 요청에 서명할 수 있는 방법에 대해 설명합니다.
seo-description: Audience Manager 에서는 유효성을 위해 HTTP 서버-서버 요청이 디지털 서명을 받아야 합니다. 이 문서에서는 개인 키를 사용하여 HTTP 요청에 서명할 수 있는 방법에 대해 설명합니다.
seo-title: 디지털 서명된 HTTP 요청
solution: Audience Manager
title: 디지털 서명된 HTTP 요청
uuid: 1183 a 70 f -0 c 96-42 cf-a 4 f 5-37 a 83 ffa 1286
translation-type: tm+mt
source-git-commit: 9bf1f3771b6a4b9bb9a52149e812b37d1c8e27f8

---


# Digitally Signed `HTTP` Requests {#digitally-signed-http-requests}

Audience Manager requires the `HTTP` server-to-server requests to be digitally signed for validity. This document describes how you can sign `HTTP` requests with private keys.

## 개요 {#overview}

<!-- digitally_signed_http_requests.xml -->

Using a private key provided by you and shared with [!DNL Audience Manager], we can digitally sign the `HTTP` requests that are sent between [IRIS](../../../reference/system-components/components-data-action.md#iris) and your HTTP server. 이를 통해 다음을 수행할 수 있습니다.

* **신뢰성**: 개인 키 ([!UICONTROL IRIS]) 가 있는 발신자만 유효한 `HTTP(S)` 메시지를 파트너에게 보낼 수 있습니다.
* **메시지 무결성**: 이러한 `HTTP`접근 방식을 사용하면 메시지가 왜곡되는 중간 공격자로부터 보호됩니다.

[!UICONTROL IRIS] 아래의 개인 키 [회전 섹션에 표시된 것처럼, 기본 제공 지원을 통해 중단 없이 키를 회전할](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) 수 있습니다.

## Information you need to provide {#info-to-provide}

For an `HTTP` real-time server-to-server destination, contact your [!DNL Audience Manager] consultant and specify:

* 요청을 서명하는 데 사용되는 키.
* The name of the `HTTP` header that will hold the generated signature (X-Signature in the example header below).
* 옵션: 서명에 사용된 해시 유형 (MD 5, SHA 1, SHA 256).

```
* Connected to partner.website.com (127.0.0.1) port 80 (#0)
> POST /webpage HTTP/1.1
> Host: partner.host.com
> Accept: */*
> Content-Type: application/json
> Content-Length: 20
> X-Signature: +wFdR/afZNoVqtGl8/e1KJ4ykPU=
POST message content
```

## How it works {#how-it-works}

1. [!UICONTROL IRIS] 파트너에게 보낼 `HTTP` 메시지를 만듭니다.
1. [!UICONTROL IRIS] 파트너가 전달하는 개인 키 및 `HTTP` 메시지를 기반으로 서명을 만듭니다.
1. [!UICONTROL IRIS] 파트너에게 `HTTP(S)` 요청을 보냅니다. 이 메시지에는 위 예와 같이 서명과 실제 메시지가 포함되어 있습니다.
1. The partner server receives the `HTTP(S)` request. It reads the message body and the signature received from [!UICONTROL IRIS].
1. 메시지 본문을 받은 본문과 개인 키를 기반으로 파트너 서버가 서명을 다시 계산합니다. See the [How to calculate the signature](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature) section just below on how to achieve this.
1. Compare the signature created on the partner server (receiver) with the one received from [!UICONTROL IRIS] (sender).
1. If the signatures match, then the **authenticity** and **message integrity** have been validated. 개인 키가 있는 발신자만 유효한 서명 (신뢰성) 를 보낼 수 있습니다. 또한 중간에 있는 남자는 개인 키 (메시지 무결성) 가 없기 때문에 메시지를 수정하고 새 유효한 서명을 생성할 수 없습니다.

![](assets/iris-digitally-sign-http-request.png)

## How to calculate the signature {#calculate-signature}

[!DNL HMAC] (해시 기반 메시지 인증 코드) 메시지 서명용으로 사용되는 [!UICONTROL IRIS] 메서드입니다. 구현 및 라이브러리는 기본적으로 모든 프로그래밍 언어로 제공됩니다. [!DNL HMAC] 알려진 확장 공격이 없습니다. See an example in [!DNL Java] below:

```
// Message to be signed.
// For GET type HTTP destinations, the message used for signing will be the REQUEST_PATH + QUERY_STRING
// For POST type HTTP destinations, the message used for signing will be the REQUEST_BODY.
// String getData = "/from-aam-s2s?sids=1,2,3";
String postData = "POST message content";
// Algorithm used. Currently supported: HmacSHA1, HmacSHA256, HmacMD5.
String algorithm = "HmacSHA1";
// Private key shared between the partner and Adobe Audience Manager.
String key = "sample_partner_private_key";
  
// Perform signing.
SecretKeySpec signingKey = new SecretKeySpec(key.getBytes(), algorithm);
Mac mac = Mac.getInstance(algorithm);
mac.init(signingKey);
byte[] result = mac.doFinal(postData.getBytes());
  
String signature = Base64.encodeBase64String(result).trim(); 
// signature = +wFdR/afZNoVqtGl8/e1KJ4ykPU=
```

[!DNL HMAC] 해시 구현의 RFC는 [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt)입니다. A test site: [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) (note that you have to [convert](https://tomeko.net/online_tools/hex_to_base64.php?lang=en) the hex encoding to base64).

## Rotating the private key {#rotate-private-key}

보안상의 이유로 개인 키를 주기적으로 회전시키는 것이 좋습니다. 개인 키와 회전 기간을 결정하는 것은 사용자에게 달려 있습니다. In order to achieve the key rotation with zero downtime, [!UICONTROL IRIS] supports adding multiple signature headers. 한 머리글에는 이전 키로 생성된 서명이 포함되고, 다른 헤더는 새 개인 키를 사용하여 생성된 서명을 포함합니다. 단계 아래의 단계를 참조하십시오.

1. Partner communicates the new private key to [!DNL Adobe Audience Manager].
1. [!UICONTROL IRIS] 두 개의 서명 헤더 (이전 키를 사용한 다른 키, 새 키를 사용한 키) 전송을 시작합니다.
1. 두 헤더 모두 받으면 이전 키를 무시하고 새 서명만 보도록 선택할 수 있습니다.
1. The old key is removed from [!DNL Audience Manager] and [!UICONTROL IRIS] only sends the new signature header. 키가 회전되었습니다.

## Data used for signing {#data-signing}

For `GET` type destinations, the message used for signing will be the *REQUEST_PATH + QUERY STRING* (e.g. */from-aam-s2s?sids=1,2,3*). IRIS does not take into account the hostname or `HTTP` headers - these can be modified / misconfigured along the path or reported incorrectly.

For `POST` type destinations, the message used for signing is the *REQUEST BODY*. 헤더 또는 기타 요청 매개 변수는 무시됩니다.
