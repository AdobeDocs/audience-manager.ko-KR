---
description: Audience Manager을 사용하려면 유효성을 위해 HTTP(S) 서버간 요청을 디지털로 서명해야 합니다. 이 문서에서는 개인 키로 HTTP 요청에 서명할 수 있는 방법에 대해 설명합니다.
seo-description: Audience Manager을 사용하려면 유효성을 위해 HTTP(S) 서버간 요청을 디지털로 서명해야 합니다. 이 문서에서는 개인 키로 HTTP(S) 요청에 서명할 수 있는 방법에 대해 설명합니다.
seo-title: 디지털 서명된 HTTP 요청
solution: Audience Manager
title: 디지털 서명된 HTTP 요청
uuid: 1183a70f-0c96-42cf-a4f5-37a83ffa1286
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: 4877aa5391193ee2187609fdc9cb3740c91feb96
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 0%

---


# Digitally Signed `HTTP(S)` Requests {#digitally-signed-http-requests}

Audience Manager의 경우 `HTTP(S)` 서버 간 요청을 유효하게 디지털로 서명해야 합니다. 이 문서에서는 개인 키로 요청에 서명할 수 있는 방법에 대해 설명합니다. `HTTP(S)`

## 개요 {#overview}

<!-- digitally_signed_http_requests.xml -->

사용자가 제공하고 공유하는 개인 키를 사용하여 [!DNL Audience Manager]IRIS와 HTTP(S) 서버 간에 전송되는 `HTTP(S)` 요청에 디지털 [으로 서명할](../../../reference/system-components/components-data-action.md#iris) 수 있습니다. 이를 통해 다음을 수행할 수 있습니다.

* **신뢰성**: 개인 키([!UICONTROL IRIS])가 있는 발신자만 유효한 `HTTP(S)` 메시지를 파트너에게 보낼 수 있습니다.
* **메시지 무결성**: 이 접근 방식에서는, 심지어 `HTTP`는 메시지가 왜곡되는 중간 공격으로부터 보호받는다.

[!UICONTROL IRIS] 의 개인 키 회전 섹션에 나와 있는 것처럼 키를 다운타임이 0으로 회전하기 위한 기본 [지원이](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) 제공됩니다.

## 제공하는 데 필요한 정보 {#info-to-provide}

서버 간 `HTTP(S)` 실시간 대상의 경우 컨설턴트에 [!DNL Audience Manager] 연락하여 다음을 지정합니다.

* 요청에 서명하는 데 사용되는 키입니다.
* 생성된 서명을 저장할 헤더의 `HTTP(S)` 이름(아래 예제 헤더의 X-Signature).
* 선택 사항: 서명에 사용된 해시 유형(md5, sha1, sha256).

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

1. [!UICONTROL IRIS] 파트너에게 보낼 `HTTP(S)` 메시지를 만듭니다.
1. [!UICONTROL IRIS] 파트너가 전달하는 `HTTP(S)` 메시지 및 개인 키를 기반으로 서명을 만듭니다.
1. [!UICONTROL IRIS] 이 요청을 `HTTP(S)` 파트너에게 보냅니다. 이 메시지에는 위의 예에서 보듯이 서명과 실제 메시지가 포함됩니다.
1. 파트너 서버가 요청을 `HTTP(S)` 받습니다. 메시지 본문과 수신한 서명을 읽습니다 [!UICONTROL IRIS].
1. 메시지 본문과 개인 키를 기준으로 파트너 서버가 서명을 다시 계산합니다. 이를 [실현하는 방법에 대한 자세한 내용은 아래 서명](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature) 계산 섹션을 참조하십시오.
1. 파트너 서버(받는 사람)에서 만든 서명을 (보낸 사람)으로부터 받은 서명 [!UICONTROL IRIS] 과 비교합니다.
1. 서명이 일치하면 **신뢰성** 및 **메시지 무결성이** 검증됩니다. 개인 키가 있는 발신자만 유효한 서명(인증)을 보낼 수 있습니다. 또한 가운데 있는 사람은 개인 키가 없으므로 메시지를 수정하고 유효한 서명을 만들 수 없습니다(메시지 무결성).

![](assets/iris-digitally-sign-http-request.png)

## 서명을 계산하는 방법 {#calculate-signature}

[!DNL HMAC] (해시 기반 메시지 인증 코드)는 메시지 서명에 사용되는 [!UICONTROL IRIS] 방법입니다. 구현과 라이브러리는 기본적으로 모든 프로그래밍 언어로 제공됩니다. [!DNL HMAC] 에는 알려진 확장 공격이 없습니다. 아래 예를 [!DNL Java] 참조하십시오.

```
// Message to be signed.
// For GET type HTTP(S) destinations, the message used for signing will be the REQUEST_PATH + QUERY_STRING
// For POST type HTTP(S) destinations, the message used for signing will be the REQUEST_BODY.
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

해시 구현에 대한 RFC는 [!DNL HMAC] https://www.ietf.org/rfc/rfc2104.txt입니다 [](https://www.ietf.org/rfc/rfc2104.txt). 테스트 사이트: [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) (16진수 인코딩을 base64로 [변환해야](https://tomeko.net/online_tools/hex_to_base64.php?lang=en) 함).

## 개인 키 회전 {#rotate-private-key}

개인 키를 회전하려면 파트너는 새 개인 키를 컨설턴트에게 [!DNL Adobe Audience Manager] 전달해야 합니다. 이전 키는 제거되고 [!DNL Audience Manager] 새 서명 [!UICONTROL IRIS] 헤더만 보냅니다. 열쇠가 회전되었습니다.

## 서명에 사용되는 데이터 {#data-signing}

유형 `GET` 대상의 경우 서명에 사용되는 메시지는 *REQUEST_PATH + QUERY STRING* (예: */from-aam-s2s?sids=1,2,3*). IRIS는 호스트 이름 또는 `HTTP(S)` 헤더를 고려하지 않습니다. 이러한 IRIS는 경로를 따라 수정/오구성하거나 잘못 보고될 수 있습니다.

유형 `POST` 대상의 경우 서명에 사용되는 메시지는 *REQUEST BODY입니다*. 헤더 또는 기타 요청 매개 변수는 무시됩니다.
