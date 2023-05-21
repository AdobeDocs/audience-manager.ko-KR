---
description: /event 호출에서 DCS 응답을 요청하는 방법에 대한 자세한 내용은 여기를 계속 진행하십시오. 이 섹션에는 응답 예와 응답의 공통 데이터 요소에 대한 정의가 포함되어 있습니다.
seo-description: Continue here for information about how to request a DCS response in a /event call. This section includes a response example and definitions for common data elements in a response.
seo-title: Receive Data From the DCS
solution: Audience Manager
title: DCS로부터 데이터 받기
uuid: fbb77197-8530-48a8-b708-d785f7214494
feature: DCS
exl-id: c6a87e5a-63cc-44d7-b6f0-ac8ee845fd00
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 4%

---

# DCS로부터 데이터 받기 {#receive-data-from-the-dcs}

을(를) 요청하는 방법에 대한 자세한 내용은 여기를 계속 참조하십시오. [!DNL DCS] 의 응답 `/event` 호출합니다. 이 섹션에는 응답 예와 응답의 공통 데이터 요소에 대한 정의가 포함되어 있습니다.

이 콘텐츠를 검토하기 전에 [DCS에 데이터 보내기](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## DCS 응답 매개 변수: 검토 {#dcs-response-parameters}

사용자 [!DNL DCS] 요청에는 다음이 포함되어야 합니다. `d_rtbd=json` 에서 응답을 수신하려는 경우 [!DNL DCS]. 다음 [!DNL DCS] 이 매개 변수를 생략하면 데이터가 반환되지 않습니다. 에 대한 기본 호출 [!DNL DCS] 데이터를 요청하려면 다음 구문을 사용합니다.

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## 샘플 응답 {#sample-response}

다음에서 다시 생각해 보십시오. [DCS에 데이터 보내기](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) 문서, 가상의 회사 [!DNL Acme, Inc.] 이(가) 이 호출을 수행함:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

이 호출에 필요한 응답 매개 변수인 [!DNL DCS] 을(를) 다시 전송함 [!DNL JSON] 아래에 표시된 개체입니다. 비슷하거나 더 복잡할 수 있습니다.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 응답 매개 변수 {#response-parameters}

아래 표는 의 응답에서 볼 수 있는 보다 일반적인 매개 변수를 나열하고 정의합니다. [!DNL DCS]. 이는 이벤트 호출 또는 기타 항목에 적용됩니다 [!DNL DCS] [!DNL API] 데이터를 반환하는 쿼리

| 매개 변수 | 설명 |
|--- |--- |
| `c` | 로 설정된 URL [URL 대상](../../../features/destinations/create-url-destination.md). |
| `cn` | 의 쿠키 이름 필드에 설정된 이름 또는 ID [쿠키 대상](../../../features/destinations/create-cookie-destination.md). |
| `cv` | &quot;cn&quot;:&quot; 대상 이름&quot; 매개 변수에 의해 정의된 대상에 전송된 값. |
| `dcs_region` | 다음 [서버 간 DCS 호출](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | 이 개체에는 UI에 구성된 모든 URL 대상에 대한 정보가 들어 있습니다. 이 오브젝트의 목록은 사용자의 작업을 기반으로 동적입니다. |
| `dmn` | 쿠키 대상의 쿠키 도메인 필드에 지정된 도메인입니다. 다음을 참조하십시오 [쿠키 대상에 대한 옵션 설정](../../../features/destinations/cookie-destination-options.md).  서버 간 통합의 경우 와 같은 도메인을 사용하는 것이 좋습니다 `aam-api.com`. |
| `e` | URL 대상에 설정된 보안 URL입니다. |
| `stuff` | 이 개체에는 모든 쿠키 대상에 대한 정보가 포함되어 있습니다. 이 오브젝트의 목록은 사용자의 작업을 기반으로 동적입니다. |
| `tid` | 거래 ID: 디버깅 목적에 사용되는 고유한 12자 ID입니다. DCS에 대한 각 /event 호출은 지원 문의에서 참조할 수 있는 tid를 수신하여 보다 나은 방식으로 신속하게 응답합니다. |
| `ttl` | 쿠키 TTL(Time-To-Live)(일). |
| `u` 및 `uuid` | Audience Manager이 할당한 고유 사용자 ID. 다음을 수행하는 경우 필수입니다. [서버 간 DCS 호출](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md). |
| `y` | 대상 유형, iFrame(`iframe`) 또는 이미지(`img`). |

>[!MORELIKETHIS]
>
>* [DCS에서 지원하는 키-값 접두사 및 변수](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

