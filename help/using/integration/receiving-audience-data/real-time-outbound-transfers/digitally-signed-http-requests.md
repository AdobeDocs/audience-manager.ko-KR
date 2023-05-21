---
description: Audience Manager을 사용하려면 유효성을 위해 HTTP(S) 서버 간 요청을 디지털 서명해야 합니다. 이 문서에서는 개인 키를 사용하여 HTTP 요청에 서명하는 방법에 대해 설명합니다.
seo-description: Audience Manager requires the HTTP(S) server-to-server requests to be digitally signed for validity. This document describes how you can sign HTTP(S) requests with private keys.
seo-title: Digitally Signed HTTP(S) Requests
solution: Audience Manager
title: 디지털 서명된 HTTP 요청
uuid: 1183a70f-0c96-42cf-a4f5-37a83ffa1286
feature: Outbound Data Transfers
exl-id: 55907a25-a361-494a-86b9-c693faea4f0e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 0%

---

# 디지털 서명됨 `HTTP(S)` 요청 {#digitally-signed-http-requests}

Audience Manager을 사용하려면 `HTTP(S)` 유효성을 위해 디지털 서명할 서버 간 요청입니다. 이 문서에서는 서명 방법에 대해 설명합니다. `HTTP(S)` 개인 키가 있는 요청.

## 개요 {#overview}

<!-- digitally_signed_http_requests.xml -->

사용자가 제공하고 와(과) 공유한 개인 키 사용 [!DNL Audience Manager], 다음을 디지털 서명할 수 있습니다 `HTTP(S)` 다음 사이에 전송된 요청: [홍채](../../../reference/system-components/components-data-action.md#iris) 및 HTTP(S) 서버입니다. 이렇게 하면 다음 사항이 보장됩니다.

* **신뢰성**: 개인 키()가 있는 발신자만[!UICONTROL IRIS])에서 유효한 을(를) 보낼 수 있습니다. `HTTP(S)` 파트너에게 보내는 메시지.
* **메시지 무결성**: 이 접근 방식을 사용하면 `HTTP`, 메시지가 왜곡되는 중간 공격에서 남성으로부터 보호됩니다.

[!UICONTROL IRIS] 에는 과 같이 가동 중지 시간 없이 키를 회전할 수 있는 기본 지원 기능이 포함되어 있습니다. [개인 키 회전](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) 아래 섹션.

## 제공해야 하는 정보 {#info-to-provide}

의 경우 `HTTP(S)` 실시간 서버 간 대상. 다음 연락처로 문의하십시오. [!DNL Audience Manager] 컨설턴트와 다음 사항을 지정합니다.

* 요청 서명에 사용되는 키입니다.
* 의 이름입니다. `HTTP(S)` 생성된 서명을 유지할 헤더(아래 예제 헤더의 X-Signature).
* 선택 사항: 서명에 사용되는 해시 유형(md5, sha1, sha256).

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

## 작동 방식 {#how-it-works}

1. [!UICONTROL IRIS] 에서 `HTTP(S)` 파트너에게 보낼 메시지.
1. [!UICONTROL IRIS] 를 기반으로 서명을 만듭니다. `HTTP(S)` 파트너가 전달한 메시지와 개인 키.
1. [!UICONTROL IRIS] 다음 전송 `HTTP(S)` 파트너에 요청합니다. 이 메시지에는 위의 예와 같이 서명과 실제 메시지가 포함되어 있습니다.
1. 파트너 서버가 `HTTP(S)` 요청. 메시지 본문과 받은 서명을 읽습니다. [!UICONTROL IRIS].
1. 수신한 메시지 본문 및 개인 키를 기반으로 파트너 서버는 서명을 다시 계산한다. 다음을 참조하십시오. [서명 계산 방법](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature) 이 작업을 수행하는 방법에 대한 아래의 섹션입니다.
1. 파트너 서버(수신자)에서 만든 서명을 다음 위치에서 받은 서명과 비교 [!UICONTROL IRIS] (보낸 사람).
1. 서명이 일치하는 경우 **신뢰성** 및 **메시지 무결성** 유효성이 확인되었습니다. 개인 키를 가진 발신자만 유효한 서명(진정성)을 보낼 수 있다. 또한 중간에 있는 사람은 개인 키(메시지 무결성)가 없기 때문에 메시지를 수정하고 유효한 새 서명을 생성할 수 없습니다.

![](assets/iris-digitally-sign-http-request.png)

## 서명 계산 방법 {#calculate-signature}

[!DNL HMAC] (해시 기반 메시지 인증 코드)은 [!UICONTROL IRIS] 메시지 서명용. 구현과 라이브러리는 기본적으로 모든 프로그래밍 언어로 사용할 수 있습니다. [!DNL HMAC] 에는 알려진 확장 공격이 없습니다. 에서 예제 참조 [!DNL Java] 아래:

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

다음에 대한 RFC [!DNL HMAC] 해시 구현 [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt). 테스트 사이트: [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) (다음을 수행해야 합니다.) [전환](https://tomeko.net/online_tools/hex_to_base64.php?lang=en) base64)에 대한 16진수 인코딩입니다.

## 개인 키 회전 {#rotate-private-key}

개인 키를 회전하려면 파트너는 새 개인 키를 사용자에게 전달해야 합니다 [!DNL Adobe Audience Manager] 컨설턴트. 이전 키가에서 제거되었습니다. [!DNL Audience Manager] 및 [!UICONTROL IRIS] 는 새 서명 헤더만 전송합니다. 키가 회전되었습니다.

## 서명에 사용된 데이터 {#data-signing}

대상 `GET` 대상 을 입력하면 서명에 사용되는 메시지는 다음과 같습니다. *REQUEST_PATH + 쿼리 문자열* (예: */from-aam-s2s?sids=1,2,3*). IRIS는 호스트 이름 또는 `HTTP(S)` 헤더 - 경로를 따라 수정/잘못 구성되거나 잘못 보고될 수 있습니다.

대상 `POST` 대상 을 입력합니다. 서명에 사용되는 메시지는 다음과 같습니다. *요청 본문*. 헤더 또는 기타 요청 매개 변수는 다시 무시됩니다.
