---
description: Audience Manager을 사용하려면 유효성을 위해 HTTP(S) 서버 간 요청을 디지털 서명해야 합니다. 이 문서에서는 개인 키로 HTTP 요청에 서명할 수 있는 방법에 대해 설명합니다.
seo-description: Audience Manager을 사용하려면 유효성을 위해 HTTP(S) 서버 간 요청을 디지털 서명해야 합니다. 이 문서에서는 개인 키로 HTTP(S) 요청에 서명할 수 있는 방법에 대해 설명합니다.
seo-title: 디지털 서명된 HTTP 요청
solution: Audience Manager
title: 디지털 서명된 HTTP 요청
uuid: 1183a70f-0c96-42cf-a4f5-37a83ffa1286
feature: 아웃바운드 데이터 전송
exl-id: 55907a25-a361-494a-86b9-c693faea4f0e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 0%

---

# 디지털 서명된 `HTTP(S)` 요청 {#digitally-signed-http-requests}

Audience Manager을 사용하려면 `HTTP(S)` 서버 간 요청을 유효성에 대해 디지털 서명해야 합니다. 이 문서에서는 개인 키로 `HTTP(S)` 요청에 서명할 수 있는 방법에 대해 설명합니다.

## 개요 {#overview}

<!-- digitally_signed_http_requests.xml -->

사용자가 제공하고 [!DNL Audience Manager]과 공유한 개인 키를 사용하면 [IRIS](../../../reference/system-components/components-data-action.md#iris) 및 HTTP(S) 서버 간에 전송되는 `HTTP(S)` 요청에 디지털 서명할 수 있습니다. 이를 통해 다음을 수행할 수 있습니다.

* **신뢰성**:개인 키([!UICONTROL IRIS])가 있는 발신자만 유효한 메시지 `HTTP(S)` 를 파트너에게 보낼 수 있습니다.
* **메시지 무결성**:이 접근 방식에서는 심지어  `HTTP`메시지가 왜곡되는 중간 공격에 있는 사람으로부터 보호받고 있습니다.

[!UICONTROL IRIS] 는 아래의 개인 키 회전 섹션에 표시된 대로 다운타임 없이  [키를 회전하도록 내장된 ](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) 지원을 제공합니다.

## {#info-to-provide} 정보를 제공해야 합니다.

`HTTP(S)` 실시간 서버 간 대상에 대해서는 [!DNL Audience Manager] 컨설턴트에게 연락하여 다음을 지정합니다.

* 요청에 서명하는 데 사용되는 키입니다.
* 생성된 서명을 보유할 `HTTP(S)` 헤더의 이름(아래 예제 헤더에서 X-Signature).
* 선택 사항:서명에 사용되는 해시 유형(md5, sha1, sha256)입니다.

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

## 작동 방법 {#how-it-works}

1. [!UICONTROL IRIS] 파트너에게  `HTTP(S)` 전송할 메시지를 만듭니다.
1. [!UICONTROL IRIS] 파트너가  `HTTP(S)` 보낸 메시지 및 개인 키를 기반으로 서명을 만듭니다.
1. [!UICONTROL IRIS] 가  `HTTP(S)` 파트너에게 요청을 보냅니다. 이 메시지에는 위의 예제와 같이 서명과 실제 메시지가 포함되어 있습니다.
1. 파트너 서버가 `HTTP(S)` 요청을 수신합니다. 메시지 본문과 [!UICONTROL IRIS]에서 받은 서명을 읽습니다.
1. 수신된 메시지 본문 및 개인 키를 기반으로 파트너 서버는 서명을 다시 계산합니다. 이 작업을 수행하는 방법에 대해서는 바로 아래의 [서명](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature)을 계산하는 방법 섹션을 참조하십시오.
1. 파트너 서버(받는 사람)에서 만든 서명과 [!UICONTROL IRIS](보낸 사람)에서 받은 서명과 비교해 보십시오.
1. 서명이 일치하면 **정품** 및 **메시지 무결성**&#x200B;이 검증되었습니다. 개인 키가 있는 발신자만 유효한 서명(정품)을 보낼 수 있습니다. 또한 중간에 있는 사람은 개인 키(메시지 무결성)가 없으므로 메시지를 수정하고 유효한 서명을 생성할 수 없습니다.

![](assets/iris-digitally-sign-http-request.png)

## 서명 {#calculate-signature}을 계산하는 방법

[!DNL HMAC] (해시 기반 메시지 인증 코드)는 메시지 서명 [!UICONTROL IRIS] 에 사용되는 방법입니다. 구현과 라이브러리는 기본적으로 모든 프로그래밍 언어로 사용할 수 있습니다. [!DNL HMAC] 에 알려진 확장 공격이 없습니다. 아래 [!DNL Java]에서 예제를 참조하십시오.

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

[!DNL HMAC] 해시 구현에 대한 RFC는 [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt)입니다. 테스트 사이트:[https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) ([16진수 인코딩을 base64로 변환해야 함을 참고하십시오.)](https://tomeko.net/online_tools/hex_to_base64.php?lang=en)

## 개인 키 회전 {#rotate-private-key}

개인 키를 회전하려면 파트너가 새 개인 키를 [!DNL Adobe Audience Manager] 컨설턴트와 통신해야 합니다. 이전 키는 [!DNL Audience Manager]에서 제거되고 [!UICONTROL IRIS]은 새 서명 헤더만 보냅니다. 키가 회전되었습니다.

## {#data-signing} 서명에 사용되는 데이터

`GET` 유형 대상의 경우 서명에 사용되는 메시지는 *REQUEST_PATH + QUERY STRING*&#x200B;입니다(예:*/from-aam-s2s?sids=1,2,3*). IRIS는 호스트 이름 또는 `HTTP(S)` 헤더를 고려하지 않습니다. 이러한 헤더는 경로를 따라 수정/잘못 구성되거나 잘못 보고될 수 있습니다.

`POST` 유형 대상의 경우 서명에 사용되는 메시지는 *REQUEST BODY*&#x200B;입니다. 다시 말해, 헤더 또는 기타 요청 매개 변수는 무시됩니다.
