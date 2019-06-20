---
description: 실시간 서버 간 통합을 통해 파트너 대상에 세그먼트를 게시할 때 Audience Manager를 설정하여 요청을 만들 때 OAuth 2.0를 사용하여 인증할 수 있습니다. 이를 통해 Audience Manager에서 인증 받은 요청을 종단점에 발행할 수 있습니다.
seo-description: 실시간 서버 간 통합을 통해 파트너 대상에 세그먼트를 게시할 때 Audience Manager를 설정하여 요청을 만들 때 OAuth 2.0를 사용하여 인증할 수 있습니다. 이를 통해 Audience Manager에서 인증 받은 요청을 종단점에 발행할 수 있습니다.
seo-title: 실시간 아웃바운드 전송을 위한 OAuth 2.0 통합
solution: Audience Manager
title: 실시간 아웃바운드 전송을 위한 OAuth 2.0 통합
uuid: A 39 E 370 C-B 3 BD -4 B 06-A 1 AF -60 A 024 EE 7 EE 4
translation-type: tm+mt
source-git-commit: 1cc8afd25331528fd67922183b6550288b9939bc

---


# [!DNL OAuth 2.0] 실시간 아웃바운드 전송을 위한 통합{#oauth-integration-for-real-time-outbound-transfers}

When publishing segments to the partner destination via a realtime server-to-server integration, Audience Manager can be set up to authenticate using [!DNL OAuth 2.0] when making the requests. 이를 통해 Audience Manager에서 인증 받은 요청을 종단점에 발행할 수 있습니다.

## Authentication Flow {#auth-flow}

[!DNL Adobe Audience Manager][OAuth 2.0](https://tools.ietf.org/html/rfc6749#section-4.4) 인증 구현은 클라이언트 자격 증명을 기반으로 하며 다음 단계를 따릅니다.

1. 귀하는 다음 사항을 제공해야 합니다.
   * The [!DNL OAuth 2.0] endpoint that generates the authentication token.
   * 토큰을 생성하는 데 사용되는 자격 증명입니다.
1. [!DNL Audience Manager] 컨설턴트는 사용자가 제공한 정보를 사용하여 [대상을](../../../features/destinations/destinations.md) 설정합니다.
1. Once a segment is mapped to this destination, our real-time data transfer system, [IRIS](../../../reference/system-components/components-data-action.md#iris), makes a `POST` request to the token endpoint to exchange the credentials for a bearer token.
1. For each segment publishing request to the partner endpoint, [!UICONTROL IRIS] uses the bearer token to authenticate.

![](assets/oauth2-iris.png)

## 요구 사항 {#auth-requirements}

[!DNL Audience Manager] 파트너로서 인증된 요청을 받는 데 다음 종점이 필요합니다.

### IRIS에서 베어러 토큰을 얻기 위해 사용하는 끝점 1

이 끝점은 1 단계에서 제공된 자격 증명을 수락하고 후속 요청에 사용될 베어러 토큰을 생성합니다.

* The endpoint must accept `HTTP POST` requests.
* The endpoint must accept and look at the [!DNL Authorization] header. The value for this header will be: `Basic <credentials_provided_by_partner>`.
* The endpoint must look at the [!DNL Content-type] header and validate that its value is `application/x-www-form-urlencoded ; charset=UTF-8`.
* The body of the request will be `grant_type=client_credentials`.

### 베어러 토큰을 얻기 위해 Audience Manager가 파트너 끝점을 요청한 예

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

### 파트너 끝점의 예 응답

```
HTTP/1.1 200 OK
Status: 200 OK
Content-Type: application/json; charset=utf-8
...
Content-Encoding: gzip
Content-Length: 121
  
{"token_type":"Bearer","access_token":"glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY"}
```

### 베어러 토큰을 사용하여 세그먼트를 게시하기 위해 IRIS가 사용하는 끝점 2

[!DNL Audience Manager] 사용자가 세그먼트에 대한 자격을 적용받을 때 거의 실시간으로 이 종단점에 데이터를 보냅니다. 또한 이 방법을 사용하면 오프라인 또는 온보드 데이터 배치를 24 시간마다 자주 보낼 수 있습니다.

Endpoint 1에서 생성된 Bearer 토큰이 이 종단점에 대한 요청을 발행하는 데 사용됩니다. The [!DNL Audience Manager] real-time data transfer system, [IRIS](../../../reference/system-components/components-data-action.md#iris), constructs a normal HTTPS request and includes an Authorization header. The value for this header will be: Bearer `<bearer token from step 1>`.

### 파트너 끝점의 예 응답

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
>이 요청에는 표준 페이로드 (컨텐츠 요청) 가 포함되어 있습니다.

## Important Considerations {#considerations}

### 토큰은 암호입니다.

The credentials presented by the partner and the tokens obtained by [!DNL Audience Manager] when authenticating using the [!DNL OAuth 2.0] flow, are sensitive information and must not be shared with third parties.

### [!DNL SSL] is required

[!DNL SSL] 를 사용해야 합니다. All requests, including the ones used to obtain and use the tokens must use `HTTPS` endpoints.