---
description: /event 호출에서 DCS 응답을 요청하는 방법에 대한 자세한 내용은 여기 를 계속 참조하십시오. 이 섹션에는 응답의 일반 데이터 요소에 대한 응답 예와 정의가 포함되어 있습니다.
seo-description: /event 호출에서 DCS 응답을 요청하는 방법에 대한 자세한 내용은 여기 를 계속 참조하십시오. 이 섹션에는 응답의 일반 데이터 요소에 대한 응답 예와 정의가 포함되어 있습니다.
seo-title: DCS로부터 데이터 받기
solution: Audience Manager
title: DCS로부터 데이터 받기
uuid: fbb77197-8530-48a8-b708-d785f7214494
feature: DCS
exl-id: c6a87e5a-63cc-44d7-b6f0-ac8ee845fd00
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 5%

---

# DCS로부터 데이터 받기 {#receive-data-from-the-dcs}

`/event` 호출에서 [!DNL DCS] 응답을 요청하는 방법에 대한 자세한 내용은 여기 를 계속 참조하십시오. 이 섹션에는 응답의 일반 데이터 요소에 대한 응답 예와 정의가 포함되어 있습니다.

이 컨텐츠를 검토하기 전에 [DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)에 데이터 보내기 를 참조하십시오.

## DCS 응답 매개 변수:검토 {#dcs-response-parameters}

[!DNL DCS]에서 응답을 받으려면 [!DNL DCS] 요청에 `d_rtbd=json`이 포함되어야 합니다. 이 매개 변수를 생략하면 [!DNL DCS]에서 데이터를 반환하지 않습니다. 데이터를 요청하는 기본 호출은 다음 구문을 사용합니다.[!DNL DCS]

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## 샘플 응답 {#sample-response}

[데이터 전송을 DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) 설명서에서 가상 회사 [!DNL Acme, Inc.]가 다음 호출을 수행했다는 것을 기억하십시오.

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

이 호출에는 필요한 응답 매개 변수가 포함되어 있으므로 [!DNL DCS]은 아래 표시된 [!DNL JSON] 개체를 다시 전송합니다. 당신의 것은 비슷하거나 더 복잡할 수도 있다.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 응답 매개 변수 {#response-parameters}

아래 표는 [!DNL DCS] 의 응답에서 볼 수 있는 더 일반적인 매개 변수를 나열하고 정의합니다. 이는 데이터를 반환하는 이벤트 호출 또는 기타 [!DNL DCS] [!DNL API] 쿼리에 적용됩니다.

| 매개 변수 | 설명 |
|--- |--- |
| `c` | [URL 대상](../../../features/destinations/create-url-destination.md)으로 설정된 URL입니다. |
| `cn` | [쿠키 대상](../../../features/destinations/create-cookie-destination.md)의 쿠키 이름 필드에 설정된 이름 또는 ID입니다. |
| `cv` | &quot;cn&quot;:&quot; 대상 이름&quot; 매개 변수에 의해 정의된 대상으로 전송되는 값입니다. |
| `dcs_region` | [서버 간 DCS가](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)을 호출합니다. |
| `dests` | 이 개체에는 UI에 구성된 모든 URL 대상에 대한 정보가 들어 있습니다. 이 객체의 목록은 사용자의 작업에 따라 동적입니다. |
| `dmn` | 쿠키 대상에 대한 쿠키 도메인 필드에 지정된 도메인입니다. [쿠키 대상에 대한 선택적 설정](../../../features/destinations/cookie-destination-options.md)을 참조하십시오.  서버 간 통합의 경우 `aam-api.com` 과 같은 도메인을 사용하는 것이 좋습니다. |
| `e` | URL 대상에 설정된 보안 URL입니다. |
| `stuff` | 이 개체에는 모든 쿠키 대상에 대한 정보가 들어 있습니다. 이 객체의 목록은 사용자의 작업에 따라 동적입니다. |
| `tid` | 거래 ID. 디버깅 목적에 사용되는 고유한 12자 ID입니다. DCS에 대한 각 /event 호출은 지원 문의에서 참조할 수 있는 tid를 수신하여 보다 빠르고 나은 응답을 제공합니다. |
| `ttl` | 쿠키 time-to-live 값(일)입니다. |
| `u` 및 `uuid` | Audience Manager이 할당한 고유 사용자 ID입니다. [서버 간 DCS 호출](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)을 수행하는 경우에 필요합니다. |
| `y` | 대상 유형, iFrame(`iframe`) 또는 이미지(`img`). |

>[!MORELIKETHIS]
>
>* [DCS에서 지원하는 키-값 접두사 및 변수](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

