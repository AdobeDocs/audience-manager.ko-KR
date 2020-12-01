---
description: 실시간 서버 간 통합을 통해 파트너 대상에 세그먼트를 게시할 때 요청 시 OAuth 2.0을 사용하여 인증하도록 Audience Manager을 설정할 수 있습니다. 이는 Audience Manager에서 종단점으로 인증된 요청을 발행할 수 있는 기능을 제공합니다.
seo-description: 실시간 서버 간 통합을 통해 파트너 대상에 세그먼트를 게시할 때 요청 시 OAuth 2.0을 사용하여 인증하도록 Audience Manager을 설정할 수 있습니다. 이는 Audience Manager에서 종단점으로 인증된 요청을 발행할 수 있는 기능을 제공합니다.
seo-title: 실시간 아웃바운드 전송을 위한 OAuth 2.0 통합
solution: Audience Manager
title: 실시간 아웃바운드 전송을 위한 OAuth 2.0 통합
uuid: a39e370c-b3bd-4b06-a1af-60a024ee7ee4
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 2%

---


# [!DNL OAuth 2.0] 실시간 아웃바운드 전송을 위한 통합{#oauth-integration-for-real-time-outbound-transfers}

실시간 서버 간 통합을 통해 파트너 대상에 세그먼트를 게시할 때 요청 시 [!DNL OAuth 2.0]을(를) 사용하여 인증하도록 Audience Manager을 설정할 수 있습니다. 이는 Audience Manager에서 종단점으로 인증된 요청을 발행할 수 있는 기능을 제공합니다.

## 인증 흐름 {#auth-flow}

[!DNL Adobe Audience Manager] [OAuth 2.0](https://tools.ietf.org/html/rfc6749#section-4.4) 인증 구현은 클라이언트 자격 증명 부여 흐름을 기반으로 하며 다음 단계를 따릅니다.

1. 귀하는 다음 사항을 제공해야 합니다.
   * 인증 토큰을 생성하는 [!DNL OAuth 2.0] 끝점
   * 토큰을 생성하는 데 사용되는 자격 증명.
1. [!DNL Audience Manager] 컨설턴트는 입력한 정보를 사용하여 [destination](../../../features/destinations/destinations.md)을 설정합니다.
1. 세그먼트가 이 대상에 매핑되면 실시간 데이터 전송 시스템인 [IRIS](../../../reference/system-components/components-data-action.md#iris)에서 스테이러 토큰에 대한 자격 증명을 교환하기 위해 토큰 끝점에 `POST` 요청을 합니다.
1. 파트너 끝점에 대한 각 세그먼트 게시 요청에 대해 [!UICONTROL IRIS]은 전달자 토큰을 사용하여 인증합니다.

![](assets/oauth2-iris.png)

## 요구 사항 {#auth-requirements}

[!DNL Audience Manager] 파트너인 경우 인증된 요청을 수신하려면 다음 끝점이 필요합니다.

### IRIS가 베어러 토큰을 가져오는 데 사용한 끝점 1

이 끝점은 1단계에서 제공된 자격 증명을 수락하고 이후 요청에 사용할 무기명 토큰을 생성합니다.

* 끝점은 `HTTP POST` 요청을 수락해야 합니다.
* 끝점은 수락하고 [!DNL Authorization] 헤더를 확인해야 합니다. 이 헤더의 값은 다음과 같습니다.`Basic <credentials_provided_by_partner>`.
* 끝점은 [!DNL Content-type] 헤더를 보고 해당 값이 `application/x-www-form-urlencoded ; charset=UTF-8`인지 확인해야 합니다.
* 요청의 본문은 `grant_type=client_credentials`입니다.

### Audience Manager에서 스테이러 토큰을 가져오기 위해 파트너 종단점에 요청한 예

```
POST /oauth2/token HTTP/1.1
Host: api.partner.com
User-Agent: Adobe Audience Manager Iris
Authorization: Basic zq2LOO1CcYGrODS5nXiNHpEz97eCpVHAoMF8pAgCntXAzxp5uRV7DTAE2qtPLjhMQwrEX3O6MHV4S
Content-Type: application/x-www-form-urlencoded;charset=UTF-8
Content-Length: 29
Accept-Encoding: gzip
  
grant_type=client_credentials
```

### 파트너 끝점의 응답 예

```
HTTP/1.1 200 OK
Status: 200 OK
Content-Type: application/json; charset=utf-8
...
Content-Encoding: gzip
Content-Length: 121
  
{"token_type":"Bearer","access_token":"glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY"}
```

### IRIS에서 베어러 토큰을 사용하여 세그먼트를 게시하기 위해 사용한 끝점 2

[!DNL Audience Manager] 사용자가 세그먼트를 사용할 수 있으므로 거의 실시간으로 이 끝점에 데이터를 보냅니다. 또한 이 방법은 24시간마다 오프라인 또는 온보드 데이터의 일괄 처리를 보낼 수 있습니다.

끝점 1에서 생성된 전달자 토큰은 이 끝점에 대한 요청을 게시하는 데 사용됩니다. [!DNL Audience Manager] 실시간 데이터 전송 시스템인 [IRIS](../../../reference/system-components/components-data-action.md#iris)에서 일반 HTTPS 요청을 생성하고 인증 헤더를 포함합니다. 이 헤더의 값은 다음과 같습니다.`<bearer token from step 1>`.

### 파트너 끝점의 응답 예

```
GET /segments/aam HTTP/1.1
Host: api.partner.com
User-Agent: Adobe Audience Manager Iris
Authorization: Bearer glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY
Content-Type: application/json
Accept-Encoding: gzip
   
{
"ProcessTime": "Wed Jul 27 16:17:42 UTC 2016",
"User_DPID": "12345",
"Client_ID": "74323",
"AAM_Destination_Id": "423",
"User_count": "2",
"Users": [{
   "AAM_UUID": "19393572368547369350319949416899715727",
   "DataPartner_UUID": "4250948725049857",
   "Segments": [{
            "Segment_ID": "14356",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         }
      ]
   }]
}
```

>[!NOTE]
>
>이 요청에는 표준 페이로드(콘텐츠 요청)가 포함되어 있습니다.

## 중요 고려 사항 {#considerations}

### 토큰은 암호입니다.

파트너가 제공하는 자격 증명과 [!DNL OAuth 2.0] 흐름을 사용하여 인증하는 경우 [!DNL Audience Manager]에서 얻은 토큰은 민감한 정보이므로 제3자와 공유해서는 안 됩니다.

### [!DNL SSL] is required

[!DNL SSL] 보안 인증 프로세스를 유지하기 위해 사용해야 합니다. 토큰을 가져오고 사용하는 데 사용되는 것과 같은 모든 요청은 `HTTPS` 끝점을 사용해야 합니다.