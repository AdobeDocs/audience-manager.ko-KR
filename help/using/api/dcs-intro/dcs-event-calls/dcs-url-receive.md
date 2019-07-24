---
description: /event 호출에서 DCS 응답을 요청하는 방법에 대한 자세한 내용은 여기를 클릭하십시오. 이 섹션에는 응답의 공통 데이터 요소에 대한 응답 예와 정의가 포함됩니다.
seo-description: /event 호출에서 DCS 응답을 요청하는 방법에 대한 자세한 내용은 여기를 클릭하십시오. 이 섹션에는 응답의 공통 데이터 요소에 대한 응답 예와 정의가 포함됩니다.
seo-title: DCS에서 데이터 받기
solution: Audience Manager
title: DCS에서 데이터 받기
uuid: FBB 77197-8530-48 A 8-B 708-D 785 F 7214494
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Receive Data From the DCS {#receive-data-from-the-dcs}

Continue here for information about how to request a [!UICONTROL DCS] response in a `/event` call. 이 섹션에는 응답의 공통 데이터 요소에 대한 응답 예와 정의가 포함됩니다.

Before reviewing this content, see [Send Data to the DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## DCS Response Parameters: A Review {#dcs-response-parameters}

Your [!UICONTROL DCS] request must include `d_rtbd=json` if you want to receive a response from the [!UICONTROL DCS]. The [!UICONTROL DCS] will not return data if you omit this parameter. A basic call to the [!UICONTROL DCS] to request data uses this syntax:

<pre><code>https://domain alias.demdex.net/event<i></i>?<i>key 1</i>= <i>val 1</i>, &amp;<i>key 2</i>= <i>val 2</i>&amp; d_ dst = 1 &amp; d_ rtbd = JSON &amp; D_ CB =<i>callback</i></code>
</pre>

## 샘플 응답 {#sample-response}

Recall that from the [Send Data to the DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) documentation, the fictional company [!DNL Acme, Inc.] made this call:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

As this call includes the required response parameter, the [!UICONTROL DCS] sent back the [!DNL JSON] object shown below. 여러분의 모습은 유사하거나 복잡할 수 있습니다.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 응답 매개 변수 {#response-parameters}

The table below lists and defines the more common parameters you may see in a response from the [!UICONTROL DCS]. This applies to event calls or other [!UICONTROL DCS] [!DNL API] queries that return data.

| 매개 변수 | 설명 |
|--- |--- |
| `c` | A URL that has been set as a [URL destination](../../../features/destinations/manage-destinations.md#configure-url-destination). |
| `cn` | [쿠키 대상의](../../../features/destinations/manage-destinations.md#create-cookie-destination)쿠키 이름 필드에 설정된 이름 또는 ID |
| `cv` | " cn "으로 정의된 대상에 전송된 값: " destinaton name "매개 변수. |
| `dcs_region` | [서버 간 DCS 호출](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | 이 개체에는 UI에 구성된 모든 URL 대상에 대한 정보가 포함되어 있습니다. 이 개체의 목록은 사용자의 작업을 기반으로 합니다. |
| `dmn` | 쿠키 대상에 대한 쿠키 도메인 필드에 지정된 도메인입니다. See [Optional Settings for Cookie Destinations](../../../features/destinations/manage-destinations.md#optional-settings-cookies).  For  Server to Server integrations we recommend using a domain like `aam-api.com`. |
| `e` | URL 대상에 설정된 보안 URL. |
| `stuff` | 이 개체에는 모든 쿠키 대상에 대한 정보가 포함되어 있습니다. 이 개체의 목록은 사용자의 작업을 기반으로 합니다. |
| `tid` | 거래 ID. 디버깅용으로 사용되는 고유한 12 자 ID 입니다. DCS에 대한 모든 /event 호출은 지원 센터에서 참조할 수 있는 TID를 받아 더욱 신속하고 빠른 응답을 제공합니다. |
| `ttl` | 쿠키의 TTL (time-to-live) 값. |
| `u` 및 `uuid` | Audience Manager에서 할당한 고유한 사용자 ID. This is required if you're making [server-to-server DCS calls](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md). |
| `y` | Destination type,  iFrame (`iframe`) or image (`img`). |

>[!MORE_ like_ this]
>
>* [DCS에서 지원하는 주요 값 접두어 및 변수](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

