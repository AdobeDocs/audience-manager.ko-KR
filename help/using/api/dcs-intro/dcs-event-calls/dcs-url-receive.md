---
description: /event 호출에서 DCS 응답을 요청하는 방법에 대한 자세한 내용을 보려면 여기를 계속 클릭하십시오. 이 섹션에는 응답의 일반적인 데이터 요소에 대한 응답 예와 정의가 포함됩니다.
seo-description: /event 호출에서 DCS 응답을 요청하는 방법에 대한 자세한 내용을 보려면 여기를 계속 클릭하십시오. 이 섹션에는 응답의 일반적인 데이터 요소에 대한 응답 예와 정의가 포함됩니다.
seo-title: DCS로부터 데이터 받기
solution: Audience Manager
title: DCS로부터 데이터 받기
uuid: fbb77197-8530-48a8-b708-d785f7214494
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 5%

---


# DCS로부터 데이터 받기 {#receive-data-from-the-dcs}

`/event` 호출에서 [!DNL DCS] 응답을 요청하는 방법에 대한 자세한 내용을 보려면 여기를 계속 클릭하십시오. 이 섹션에는 응답의 일반적인 데이터 요소에 대한 응답 예와 정의가 포함됩니다.

이 내용을 검토하기 전에 [DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)에 데이터 전송을 참조하십시오.

## DCS 응답 매개 변수:검토 {#dcs-response-parameters}

[!DNL DCS]로부터 응답을 받으려면 [!DNL DCS] 요청에 `d_rtbd=json`이(가) 포함되어야 합니다. 이 매개 변수를 생략하면 [!DNL DCS]에서 데이터를 반환하지 않습니다. 데이터를 요청하는 [!DNL DCS]에 대한 기본 호출에서는 다음 구문을 사용합니다.

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## 샘플 응답 {#sample-response}

[데이터 전송을 DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) 설명서에서 가상 회사인 [!DNL Acme, Inc.]이(가) 다음과 같은 호출을 수행했다는 것을 기억하십시오.

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

이 호출에는 필수 응답 매개 변수가 포함되므로 [!DNL DCS]이(가) 아래에 표시된 [!DNL JSON] 개체를 다시 보냈습니다. 여러분의 생각은 비슷하거나 더 복잡할 수 있습니다.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 응답 매개 변수 {#response-parameters}

아래 표는 [!DNL DCS]의 응답에서 볼 수 있는 보다 일반적인 매개 변수를 나열하고 정의합니다. 이는 데이터를 반환하는 다른 [!DNL DCS] [!DNL API] 쿼리에 적용됩니다.

| 매개 변수 | 설명 |
|--- |--- |
| `c` | [URL 대상](../../../features/destinations/create-url-destination.md)으로 설정된 URL입니다. |
| `cn` | [쿠키 대상](../../../features/destinations/create-cookie-destination.md)의 쿠키 이름 필드에 설정된 이름 또는 ID입니다. |
| `cv` | &quot;cn&quot;:&quot; destination name&quot; 매개 변수에 의해 정의된 대상으로 전송된 값. |
| `dcs_region` | [서버 간 DCS가 ](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)을(를) 호출합니다. |
| `dests` | 이 개체는 UI에 구성된 모든 URL 대상에 대한 정보를 포함합니다. 이 개체의 목록은 사용자의 작업에 따라 동적인 것입니다. |
| `dmn` | 쿠키 대상에 대해 쿠키 도메인 필드에 지정된 도메인입니다. 쿠키 대상](../../../features/destinations/cookie-destination-options.md)에 대한 [선택적 설정을 참조하십시오.  서버 간 통합의 경우 `aam-api.com` 같은 도메인을 사용하는 것이 좋습니다. |
| `e` | URL 대상에 설정된 보안 URL. |
| `stuff` | 이 개체에는 모든 쿠키 대상에 대한 정보가 포함되어 있습니다. 이 개체의 목록은 사용자의 작업에 따라 동적인 것입니다. |
| `tid` | 디버깅 용도로 사용되는 고유한 12자 ID인 거래 ID입니다. DCS에 대한 각 /event 호출은 지원 문의 시 참조할 수 있는 tid를 수신하여 보다 신속하고 나은 응답을 얻을 수 있습니다. |
| `ttl` | 쿠키 사용 기간(일)입니다. |
| `u` 및 `uuid` | Audience Manager에서 할당한 고유 사용자 ID. [서버 간 DCS 호출](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)을 하는 경우 필요합니다. |
| `y` | 대상 유형, iFrame(`iframe`) 또는 이미지(`img`). |

>[!MORELIKETHIS]
>
>* [DCS에서 지원하는 키-값 접두사 및 변수](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

