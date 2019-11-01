---
description: /event 호출에서 DCS 응답을 요청하는 방법에 대한 자세한 내용을 보려면 여기를 계속 클릭하십시오. 이 섹션에는 응답의 일반적인 데이터 요소에 대한 응답 예와 정의가 포함됩니다.
seo-description: /event 호출에서 DCS 응답을 요청하는 방법에 대한 자세한 내용을 보려면 여기를 계속 클릭하십시오. 이 섹션에는 응답의 일반적인 데이터 요소에 대한 응답 예와 정의가 포함됩니다.
seo-title: DCS에서 데이터 받기
solution: Audience Manager
title: DCS에서 데이터 받기
uuid: fbb77197-8530-48a8-b708-d785f7214494
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# DCS에서 데이터 받기 {#receive-data-from-the-dcs}

호출에서 [!UICONTROL DCS] 응답을 요청하는 방법에 대한 자세한 내용은 여기를 `/event` 계속 참조하십시오. 이 섹션에는 응답의 일반적인 데이터 요소에 대한 응답 예와 정의가 포함됩니다.

이 컨텐츠를 검토하기 전에 DCS로 [데이터 전송을 참조하십시오](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## DCS 응답 매개 변수:검토 {#dcs-response-parameters}

요청에는 [!UICONTROL DCS] 요청에서 응답을 받으려면 `d_rtbd=json` 포함되어야 합니다 [!UICONTROL DCS]. 이 매개 변수를 생략하면 데이터가 반환되지 [!UICONTROL DCS] 않습니다. 데이터를 요청하기 [!UICONTROL DCS] 위해 에 대한 기본 호출은 다음 구문을 사용합니다.

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## 샘플 응답 {#sample-response}

Send Data to [the DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) documentation에서 가상 회사가 다음과 같은 호출을 [!DNL Acme, Inc.] 수행했습니다.

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

이 호출에는 필수 응답 매개 변수가 포함되므로, [!UICONTROL DCS] 전송한 [!DNL JSON] 개체는 아래에 표시됩니다. 비슷한 것 혹은 더 복잡할 수 있습니다.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 응답 매개 변수 {#response-parameters}

아래 표는 에서 응답으로 볼 수 있는 보다 일반적인 매개 변수를 나열하고 정의합니다 [!UICONTROL DCS]. 이는 데이터를 반환하는 이벤트 호출 또는 기타 [!UICONTROL DCS] [!DNL API] 쿼리에 적용됩니다.

| 매개 변수 | 설명 |
|--- |--- |
| `c` | URL 대상으로 설정된 [URL](../../../features/destinations/create-url-destination.md). |
| `cn` | [쿠키 대상의](../../../features/destinations/create-cookie-destination.md)쿠키 이름 필드에 설정된 이름 또는 ID. |
| `cv` | "cn":" 대상 이름" 매개 변수에 의해 정의된 대상으로 전송된 값입니다. |
| `dcs_region` | 서버 간 [DCS 호출](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | 이 개체에는 UI에 구성된 모든 URL 대상에 대한 정보가 포함되어 있습니다. 이 개체의 목록은 사용자의 작업에 따라 동적입니다. |
| `dmn` | 쿠키 대상에 대해 쿠키 도메인 필드에 지정된 도메인입니다. 쿠키 [대상에 대한 선택 설정을 참조하십시오](../../../features/destinations/cookie-destination-options.md).  서버와 서버 간의 통합에는 다음과 같은 도메인을 사용하는 것이 좋습니다 `aam-api.com`. |
| `e` | URL 대상에 설정된 보안 URL입니다. |
| `stuff` | 이 개체에는 모든 쿠키 대상에 대한 정보가 포함되어 있습니다. 이 개체의 목록은 사용자의 작업에 따라 동적입니다. |
| `tid` | 거래 ID - 디버깅 용도로 사용되는 고유한 12자 ID입니다. DCS에 대한 각 /event 호출은 지원 문의 시 참조할 수 있는 tid를 수신하여 보다 신속하고 나은 응답을 제공합니다. |
| `ttl` | 쿠키 사용 기간(일)입니다. |
| `u` 및 `uuid` | Audience Manager에서 할당한 고유 사용자 ID. 서버 간 DCS 호출을 [](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)수행하는 경우 필요합니다. |
| `y` | 대상 유형, iFrame(`iframe`) 또는 이미지(`img`). |

>[!MORELIKETHIS]
>
>* [DCS에서 지원하는 키-값 접두사 및 변수](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

