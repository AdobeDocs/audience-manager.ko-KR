---
description: /event 호출에서 DCS 응답을 요청하는 방법에 대한 자세한 내용은 여기를 클릭하십시오. 이 섹션에는 응답의 공통 데이터 요소에 대한 응답 예와 정의가 포함됩니다.
seo-description: /event 호출에서 DCS 응답을 요청하는 방법에 대한 자세한 내용은 여기를 클릭하십시오. 이 섹션에는 응답의 공통 데이터 요소에 대한 응답 예와 정의가 포함됩니다.
seo-title: DCS에서 데이터 받기
solution: Audience Manager
title: DCS에서 데이터 받기
uuid: FBB 77197-8530-48 A 8-B 708-D 785 F 7214494
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# DCS에서 데이터 받기 {#receive-data-from-the-dcs}

통화에서 [!UICONTROL DCS] 응답을 요청하는 방법에 대한 자세한 내용은 여기를 `/event` 클릭하십시오. 이 섹션에는 응답의 공통 데이터 요소에 대한 응답 예와 정의가 포함됩니다.

이 콘텐트를 검토하기 전에 DCS로 데이터 [전송을 참조하십시오](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## DCS 응답 매개 변수: 리뷰 {#dcs-response-parameters}

에서 응답을 받으려면 [!UICONTROL DCS]`d_rtbd=json` 요청에 [!UICONTROL DCS]포함되어야 합니다. 이 매개 변수를 생략하면 데이터를 반환하지 [!UICONTROL DCS] 않습니다. 데이터 [!UICONTROL DCS] 요청에 대한 기본 호출은 다음 구문을 사용합니다.

<pre><code>https://domain alias.demdex.net/event<i></i>?<i>key 1</i>= <i>val 1</i>, &amp;<i>key 2</i>= <i>val 2</i>&amp; d_ dst = 1 &amp; d_ rtbd = JSON &amp; D_ CB =<i>callback</i></code>
</pre>

## 샘플 응답 {#sample-response}

The [Transmit Data to the DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) Documentation, the Scenes Company [!DNL Acme, Inc.] Made This Call:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

이 호출에는 필수 응답 매개 변수가 포함되어 있으므로, 아래에 [!UICONTROL DCS] 표시된 [!DNL JSON] 개체가 반환됩니다. 여러분의 모습은 유사하거나 복잡할 수 있습니다.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 응답 매개 변수 {#response-parameters}

아래 표는의 응답으로 볼 수 있는 더 일반적인 매개 변수를 나열하고 정의합니다 [!UICONTROL DCS]. 이것은 데이터를 반환하는 이벤트 호출 또는 기타 [!UICONTROL DCS][!DNL API] 쿼리에 적용됩니다.

| 매개 변수 | 설명 |
|--- |--- |
| `c` | URL 대상으로 설정된 [URL](../../../features/destinations/create-url-destination.md)입니다. |
| `cn` | [쿠키 대상의](../../../features/destinations/create-cookie-destination.md)쿠키 이름 필드에 설정된 이름 또는 ID |
| `cv` | " cn "으로 정의된 대상에 전송된 값: " destinaton name "매개 변수. |
| `dcs_region` | [서버 간 DCS 호출](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | 이 개체에는 UI에 구성된 모든 URL 대상에 대한 정보가 포함되어 있습니다. 이 개체의 목록은 사용자의 작업을 기반으로 합니다. |
| `dmn` | 쿠키 대상에 대한 쿠키 도메인 필드에 지정된 도메인입니다. 쿠키 [대상에 대한 선택적 설정을 참조하십시오](../../../features/destinations/cookie-destination-options.md). 서버 간 통합에 대해, 도메인과 같은 `aam-api.com`도메인을 사용하는 것이 좋습니다. |
| `e` | URL 대상에 설정된 보안 URL. |
| `stuff` | 이 개체에는 모든 쿠키 대상에 대한 정보가 포함되어 있습니다. 이 개체의 목록은 사용자의 작업을 기반으로 합니다. |
| `tid` | 거래 ID. 디버깅용으로 사용되는 고유한 12 자 ID 입니다. DCS에 대한 모든 /event 호출은 지원 센터에서 참조할 수 있는 TID를 받아 더욱 신속하고 빠른 응답을 제공합니다. |
| `ttl` | 쿠키의 TTL (time-to-live) 값. |
| `u` 및 `uuid` | Audience Manager에서 할당한 고유한 사용자 ID. 서버 간 DCS 호출을 수행하는 [](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)경우 필요합니다. |
| `y` | 대상 유형, iframe (`iframe`) 또는 image (`img`). |

>[!MORE_ like_ this]
>
>* [DCS에서 지원하는 주요 값 접두어 및 변수](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

