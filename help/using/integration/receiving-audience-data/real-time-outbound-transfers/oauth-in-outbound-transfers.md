---
description: 실시간 서버 간 통합을 통해 파트너 대상에 세그먼트를 게시할 때 요청을 만들 때 OAuth 2.0을 사용하여 인증하도록 Audience Manager을 설정할 수 있습니다. 이렇게 하면 Audience Manager에서 엔드포인트로 인증된 요청을 발급할 수 있습니다.
seo-description: 실시간 서버 간 통합을 통해 파트너 대상에 세그먼트를 게시할 때 요청을 만들 때 OAuth 2.0을 사용하여 인증하도록 Audience Manager을 설정할 수 있습니다. 이렇게 하면 Audience Manager에서 엔드포인트로 인증된 요청을 발급할 수 있습니다.
seo-title: 실시간 아웃바운드 전송을 위한 OAuth 2.0 통합
solution: Audience Manager
title: 실시간 아웃바운드 전송을 위한 OAuth 2.0 통합
uuid: a39e370c-b3bd-4b06-a1af-60a024ee7ee4
feature: 아웃바운드 데이터 전송
exl-id: eef3a3ae-1a3f-47e9-aab6-abf878e4cb77
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 2%

---

# [!DNL OAuth 2.0] 실시간 아웃바운드 전송을 위한 통합{#oauth-integration-for-real-time-outbound-transfers}

실시간 서버 간 통합을 통해 파트너 대상에 세그먼트를 게시할 때 요청을 만들 때 [!DNL OAuth 2.0]을 사용하여 인증하도록 Audience Manager을 설정할 수 있습니다. 이렇게 하면 Audience Manager에서 엔드포인트로 인증된 요청을 발급할 수 있습니다.

## 인증 흐름 {#auth-flow}

[!DNL Adobe Audience Manager] [OAuth 2.0](https://tools.ietf.org/html/rfc6749#section-4.4) 인증 구현은 클라이언트 자격 증명 부여 흐름을 기반으로 하며, 다음 단계를 따릅니다.

1. 다음을 제공해야 합니다.
   * 인증 토큰을 생성하는 [!DNL OAuth 2.0] 끝점입니다.
   * 토큰을 생성하는 데 사용되는 자격 증명입니다.
1. [!DNL Audience Manager] 컨설턴트는 제공한 정보를 사용하여 [대상](../../../features/destinations/destinations.md)을 설정합니다.
1. 세그먼트가 이 대상에 매핑되면 실시간 데이터 전송 시스템인 [IRIS](../../../reference/system-components/components-data-action.md#iris)에서 토큰 끝점에 대한 `POST` 요청을 수행하여 bearer 토큰에 대한 자격 증명을 교환합니다.
1. 파트너 엔드포인트에 대한 각 세그먼트 게시 요청의 경우 [!UICONTROL IRIS]은 베어러 토큰을 사용하여 인증합니다.

![](assets/oauth2-iris.png)

## 요구 사항 {#auth-requirements}

[!DNL Audience Manager] 파트너로서 인증된 요청을 수신하려면 다음 종단점이 필요합니다.

### IRIS에서 베어러 토큰을 가져오는 데 사용하는 끝점 1

이 종단점은 1단계에서 제공된 자격 증명을 수락하고 후속 요청에서 사용할 베어러 토큰을 생성합니다.

* 끝점은 `HTTP POST` 요청을 수락해야 합니다.
* 엔드포인트는 [!DNL Authorization] 헤더를 수락 및 확인해야 합니다. 이 헤더의 값은 다음과 같습니다.`Basic <credentials_provided_by_partner>`
* 끝점은 [!DNL Content-type] 헤더를 확인하고 해당 값이 `application/x-www-form-urlencoded ; charset=UTF-8`인지 확인해야 합니다.
* 요청 본문은 `grant_type=client_credentials`입니다.

### bearer 토큰을 얻기 위해 Audience Manager이 파트너 엔드포인트에 대해 수행한 요청 예

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

### IRIS에서 베어러 토큰을 사용하여 세그먼트를 게시하기 위해 사용하는 끝점 2

[!DNL Audience Manager] 사용자가 세그먼트에 대한 자격이 부여되면 거의 실시간으로 이 종단점에 데이터를 보냅니다. 또한 이 메서드는 24시간마다 오프라인 데이터나 온보딩된 데이터 배치를 자주 보낼 수 있습니다.

끝점 1에서 생성된 베어러 토큰은 이 끝점에 대한 요청을 실행하는 데 사용됩니다. [!DNL Audience Manager] 실시간 데이터 전송 시스템인 [IRIS](../../../reference/system-components/components-data-action.md#iris)는 일반적인 HTTPS 요청을 구성하고 인증 헤더를 포함합니다. 이 헤더의 값은 다음과 같습니다.Bearer `<bearer token from step 1>`.

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
>이 요청에는 표준 페이로드(요청 콘텐츠)가 포함되어 있습니다.

## 중요 고려 사항 {#considerations}

### 토큰은 암호입니다

파트너가 제공하는 자격 증명과 [!DNL OAuth 2.0] 플로우를 사용하여 인증할 때 [!DNL Audience Manager]에서 획득한 토큰은 중요한 정보이므로 제3자와 공유해서는 안 됩니다.

### [!DNL SSL] 필수 여부

[!DNL SSL] 보안 인증 프로세스를 유지하려면 을 사용해야 합니다. 토큰을 가져오고 사용하는 데 사용되는 요청을 포함하여 모든 요청은 `HTTPS` 끝점을 사용해야 합니다.
