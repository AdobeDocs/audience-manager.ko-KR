---
description: 일반 요구 사항, 인증, 선택적 쿼리 매개 변수, 요청 URL 및 기타 참조에 대한 정보를 제공합니다.
seo-description: 일반 요구 사항, 인증, 선택적 쿼리 매개 변수, 요청 URL 및 기타 참조에 대한 정보를 제공합니다.
seo-title: REST API 시작
solution: Audience Manager
title: REST API 시작
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
translation-type: tm+mt
source-git-commit: ab8745a8ba24154793201893a39a039b5a098833
workflow-type: tm+mt
source-wordcount: '1860'
ht-degree: 3%

---


# Getting Started with [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

Information about general requirements, authentication, optional query parameters, request [!DNL URLs], and other references.

<!-- c_rest_api_overview.xml -->

## API 요구 사항 및 권장 사항 {#api-requirements-recommendations}

Adobe Marketing Cloud를 사용하여 작업할 때 수행해야 하는 사항 [!DNL Audience Manager] 을 살펴볼 수 [!DNL API]있습니다.

<!-- aam-api-requirements.xml -->

Audience Manager API [코드 작업 시 다음을](https://bank.demdex.com/portal/swagger/index.html#/) 참고하십시오.

* **요청 매개 변수:** 별도로 명시되지 않는 한 모든 요청 매개 변수가 필요합니다.
* **요청 헤더**:adobe [I/O](https://www.adobe.io/) 토큰을 사용하는 경우 `x-api-key` 헤더를 제공해야 합니다. 서비스 계정 통합 [!DNL API] 페이지의 지침에 따라 키를 [가져올 수 있습니다](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) .
* **[!DNL JSON]콘텐트 유형:** 코드에 `content-type: application/json` and *를* `accept: application/json` 지정합니다.
* **요청 및 응답:** 요청을 올바른 형식으로 [!DNL JSON] 보냅니다. [!DNL Audience Manager] 형식이 지정된 데이터로 [!DNL JSON] 응답합니다. 서버 응답에는 요청된 데이터, 상태 코드 또는 둘 다를 포함할 수 있습니다.
* **액세스:** 컨설턴트는 요청을 할 수 있는 클라이언트 ID와 키를 [!DNL Audience Manager] [!DNL API] 제공합니다.
* **설명서 및 코드 샘플:** 기울임꼴의 *텍스트는* 데이터를 만들거나 수신할 때 제공하거나 전달하는 변수를 [!DNL API] 나타냅니다. 기울임체 *가* 지정된 텍스트를 고유한 코드, 매개 변수 또는 기타 필수 정보로 바꿀 수 있습니다.

## 인증 {#authentication}

두 가지 인증 방법을 [!DNL Audience Manager] [!DNL REST APIs] 지원합니다.

* [JWT(서비스 계정](#jwt) ) [Adobe I/O를 사용한 인증](https://www.adobe.io/). [!DNL Adobe I/O] 는 Adobe 개발자 에코시스템 및 커뮤니티입니다. 여기에는 모든 Adobe 제품의 [Adobe I/O 개발자 도구, API](https://www.adobe.io/apis/experienceplatform.html) 및 [API가 포함됩니다](https://www.adobe.io/apis.html). 이를 통해 설정 및 사용 방법이 권장됩니다 [!DNL Adobe] [!DNL APIs].
* [OAuth 인증(더 이상 사용되지 않음)](#oauth). 이 메서드는 더 이상 사용되지 않지만 기존 통합을 사용하는 고객은 이 방법을 계속 사용할 수 [!DNL OAuth] 있습니다.

>[!IMPORTANT]
>
>인증 방법에 따라 요청을 적절하게 조정해야 [!DNL URLs] 합니다. 사용해야 하는 호스트 이름에 대한 자세한 내용은 [환경](#environments) 섹션을 참조하십시오.

## [!DNL JWT] ([!DNL Service Account]) Adobe 입출력을 사용한 인증 {#jwt}

### Adobe I/O 개요 {#adobeio}

[!DNL Adobe I/O] 는 Adobe 개발자 에코시스템 및 커뮤니티입니다. 여기에는 모든 Adobe 제품의 [Adobe I/O 개발자 도구, API](https://www.adobe.io/apis/experienceplatform.html) 및 [API가 포함됩니다](https://www.adobe.io/apis.html).

이를 통해 설정 및 사용 방법이 권장됩니다 [!DNL Adobe] [!DNL APIs].

### 사전 요구 사항 {#prerequisites}

인증을 구성하려면 먼저 [!DNL JWT] Adobe I/O에서 [Adobe 개발자 콘솔](https://console.adobe.io/) 에 액세스할 수 있어야 합니다 [](https://www.adobe.io/). 액세스 요청은 조직 관리자에게 문의하십시오.

### 인증 {#auth}

아래 절차에 따라 다음을 사용하여 [!DNL JWT (Service Account)] 인증을 구성하십시오 [!DNL Adobe I/O].

1. Adobe 개발자 [콘솔에 로그인합니다](https://console.adobe.io/).
1. 서비스 계정 [연결의 단계를 따릅니다](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
   * 2단계 [중:서비스 계정 인증을](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)사용하여 프로젝트에 API를 추가하고 [!DNL Audience Manager] 옵션을 [!DNL API] 선택합니다.
1. 3단계의 지침에 따라 처음 [!DNL API] 전화를 걸어 연결을 [시도해 보십시오](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>자동 방식으로 구성 및 작업하려면 [!DNL Audience Manager] 프로그래밍 [!DNL REST APIs] 으로 해당 컨텐츠를 생성할 수 [!DNL JWT] 있습니다. 자세한 [내용은 JWT(서비스 계정) 인증을](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) 참조하십시오.

## [!DNL OAuth] 인증(더 이상 사용되지 않음) {#oauth}

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] 토큰 인증 및 갱신 [!DNL OAuth 2.0] 은 이제 더 이상 사용되지 않습니다.
>
> JWT( [서비스 계정) 인증을](#jwt-service-account-authentication-jwt) 대신 사용하십시오.

이 [!DNL Audience Manager] 는 토큰 인증 및 갱신 [!UICONTROL REST API] [!DNL OAuth 2.0] 기준을 따릅니다. 아래 섹션에서는 를 인증하고 사용하여 작업하는 방법에 대해 [!DNL API]설명합니다.

### 일반 [!DNL API] 사용자 만들기 {#requirements}

Adobe에서는 Adobe Marketing Cloud를 사용하여 별도의 기술 사용자 계정을 만드는 것이 [!DNL Audience Manager] [!DNL API]좋습니다.조직의 특정 사용자에게 연결되어 있거나 연결되어 있지 않은 일반 계정입니다. 이 유형의 [!DNL API] 사용자 계정은 다음 두 가지 작업을 수행하는 데 도움이 됩니다.

* 어떤 서비스가 호출되는지 [!DNL API] 확인합니다(예: Adobe [!DNL API]를 사용하는 앱이나 [!DNL API] 요청을 만드는 기타 도구에서 거는 호출).
* 중단 없는 액세스를 [!DNL API]제공합니다.특정 사용자에 연결된 계정은 회사를 떠날 때 삭제될 수 있습니다. 이렇게 하면 사용 가능한 [!DNL API] 코드를 사용할 수 없습니다. 특정 직원과 연결되지 않은 일반 계정은 이 문제를 해결하는 데 도움이 됩니다.

이 유형의 계정에 대한 예제 또는 사용 사례로서 벌크 관리 도구를 사용하여 한 번에 많은 세그먼트를 변경하려고 한다고 [가정합니다](../../reference/bulk-management-tools/bulk-management-intro.md). 이렇게 하려면 사용자 계정에 [!DNL API] 액세스 권한이 필요합니다. 특정 사용자에게 권한을 추가하는 대신 적절한 자격 증명, 키 및 암호를 가진 [!DNL API] 사용자 계정을 만들어 [!DNL API] 호출합니다. 이 기능은 Flash Platform(플래시 플랫폼)을 사용하는 애플리케이션을 개발할 때도 [!DNL Audience Manager] 유용합니다 [!DNL API].

컨설턴트와 협력하여 일반 [!DNL Audience Manager] [!DNL API]전용 사용자 계정을 설정합니다.

### 암호 인증 워크플로 {#password-authentication-workflow}

암호 인증을 통해 안전하게 액세스할 수 [!DNL REST API]있습니다. 아래 단계는 브라우저의 [!DNL JSON] 클라이언트에서 암호 인증을 위한 워크플로우에 대해 간략하게 설명합니다.

>[!TIP]
>
>액세스 토큰을 데이터베이스에 저장하는 경우 암호화 및 새로 고침 토큰을 사용하십시오.

#### 1단계:액세스 [!DNL API] 요청

파트너 솔루션 관리자에게 문의하십시오. 클라이언트 ID와 암호를 [!DNL API] 제공합니다. ID와 암호는 사용자를 인증합니다 [!DNL API].

참고:새로 고침 토큰을 받으려면 액세스 권한을 요청할 때 이 토큰을 [!DNL API] 지정합니다.

#### 2단계:토큰 요청

기본 [!DNL JSON] 클라이언트와 함께 토큰 요청을 전달합니다. 요청을 빌드할 때:

* 메서드를 사용하여 `POST` 호출합니다 `https://api.demdex.com/oauth/token`.
* 클라이언트 ID와 암호를 기본 64로 인코딩된 문자열로 변환합니다. 전환 프로세스 동안 ID와 암호를 콜론으로 구분합니다. 예를 들어 자격 증명이 `testId : testSecret` 로 변환됩니다 `dGVzdElkOnRlc3RTZWNyZXQ=`.
* 그리고 [!DNL HTTP] 를 [!DNL headers] 통과하세요 `Authorization:Basic <base-64 clientID:clientSecret>` `Content-Type: application/x-www-form-urlencoded` . 예를 들어 헤더는 다음과 같을 수 있습니다. <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* 다음과 같이 요청 본문을 설정합니다.
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### 3단계:토큰 받기

응답에 액세스 토큰이 [!DNL JSON] 포함되어 있습니다. 응답은 다음과 같아야 합니다.

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

키 `expires_in` 는 액세스 토큰이 만료될 때까지 남은 시간(초)을 나타냅니다. 토큰을 노출한 경우 짧은 만료 시간을 사용하여 노출을 제한하는 것이 좋습니다.

### 토큰 새로 고침 {#refresh-token}

토큰 새로 고침은 원래 토큰이 만료된 후에 [!DNL API] 액세스를 갱신합니다. 요청 시 암호 작업 과정 [!DNL JSON] 의 응답에 새로 고침 토큰이 포함됩니다. 새로 고침 토큰을 받지 않은 경우 암호 인증 프로세스를 통해 새 토큰을 만드십시오.

기존 액세스 토큰이 만료되기 전에 새로 고침 토큰을 사용하여 새 토큰을 생성할 수도 있습니다.

액세스 토큰이 만료되면 응답에서 다음 헤더 `401 Status Code` 를 받게 됩니다.

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

다음 단계에서는 새로 고침 토큰을 사용하여 브라우저의 [!DNL JSON] 클라이언트에서 새 액세스 토큰을 만드는 워크플로우에 대해 간략하게 설명합니다.

#### 1단계:새 토큰 요청

기본 클라이언트와 함께 새로 고침 토큰 요청을 [!DNL JSON] 전달합니다. 요청을 빌드할 때:

* 메서드를 사용하여 `POST` 호출합니다 `https://api.demdex.com/oauth/token`.
* 클라이언트 ID와 암호를 기본 64로 인코딩된 문자열로 변환합니다. 전환 프로세스 동안 ID와 암호를 콜론으로 구분합니다. 예를 들어 자격 증명이 `testId : testSecret` 로 변환됩니다 `dGVzdElkOnRlc3RTZWNyZXQ=`.
* HTTP 헤더와 HTTP 헤더 `Authorization:Basic <base-64 clientID:clientSecret>` 를 전달합니다 `Content-Type: application/x-www-form-urlencoded`. 예를 들어 헤더는 다음과 같을 수 있습니다. <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* 요청 본문에 이전 액세스 요청에서 받은 새로 고침 토큰 `grant_type:refresh_token` 을 지정하고 전달합니다. 요청은 다음과 같아야 합니다. <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### 2단계:새 토큰 받기

응답에 새 액세스 토큰이 [!DNL JSON] 포함되어 있습니다. 응답은 다음과 같아야 합니다.

```json
{
    "access_token": "4fdfc261-2ffc-4fb7-8dbd-64221714c45f",
    "token_type": "bearer",
    "refresh_token": "295fa487-1825-4caa-a715-80b81ac17dae",
    "expires_in": 21922,
    "scope": "read write"
}
```

### 인증 코드 및 암시적 인증 {#authentication-code-implicit}

인증 코드 [!DNL Audience Manager] 및 암묵적 인증을 [!UICONTROL REST API] 지원합니다. 이러한 액세스 방법을 사용하려면 로그인하여 토큰을 액세스하거나 새로 `https://api.demdex.com/oauth/authorize` 고치십시오.

## 인증된 요청 [!DNL API] 만들기 {#authenticated-api-requests}

인증 토큰을 받은 후 메서드를 호출하는 [!DNL API] 데 필요한 요구 사항입니다.

사용 가능한 방법에 대해 [!DNL API] 호출하려면

* 헤더에서 `HTTP` 를 설정합니다 `Authorization: Bearer <token>`.
* JWT( [서비스 계정) 인증을](#jwt)사용하는 경우 `x-api-key` 헤더를 제공해야 합니다. 헤더는 사용자와 `client_id`동일합니다. Adobe `client_id` I/O 통합 [](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) 페이지에서 원하는 항목을 찾을 수 있습니다.
* 필요한 메서드를 [!DNL API] 호출합니다.

## 선택적 [!DNL API] 쿼리 매개 변수 {#optional-api-query-parameters}

개체에 대한 모든 속성을 반환하는 메서드에 사용할 수 있는 선택적 매개 변수를 설정합니다.

이러한 선택적 매개 변수를 개체에 대한 [!DNL API] 모든 ** 속성을 반환하는 메서드와 함께 사용할 수 있습니다. 요청 문자열에 해당 쿼리를 전달하면 이 옵션을 설정합니다 [!DNL API].

| 매개 변수 | 설명 |
|--- |--- |
| `page` | 페이지 번호별로 결과를 반환합니다. 번호 매기는 0부터 시작됩니다. |
| `pageSize` | 요청에 의해 반환되는 응답 결과 수를 설정합니다(기본값 10). |
| `sortBy` | 지정된 속성에 따라 결과를 정렬하고 [!DNL JSON] 반환합니다. |
| `descending` | 결과를 내림차순으로 정렬하고 반환합니다. `ascending` 기본값은 기본값입니다. |
| `search` | 검색 매개 변수로 사용할 지정된 문자열을 기반으로 결과를 반환합니다. 예를 들어 해당 항목에 대한 값 필드에 &quot;Test&quot;라는 단어가 있는 모든 모델의 결과를 찾으려고 합니다. 샘플 요청은 다음과 같습니다.  `GET https://aam.adobe.io/v1/models/?search=Test`.  &quot;[!DNL get all]&quot; 메서드에서 반환되는 모든 값을 검색할 수 있습니다. |
| `folderId` | 지정된 폴더 내의 모든 ID를 [!UICONTROL traits] 반환합니다. 일부 메서드에는 사용할 수 없습니다. |
| `permissions` | 지정된 권한을 기반으로 세그먼트 목록을 반환합니다. `READ` 기본값은 기본값입니다. 권한은 다음과 같습니다.<ul><li>`READ` :세그먼트에 대한 정보를 반환하고 봅니다.</li><li>`WRITE` :세그먼트 `PUT` 를 업데이트하는 데 사용합니다.</li><li>`CREATE` :세그먼트 `POST` 를 만드는 데 사용합니다.</li><li>`DELETE` : 세그먼트 삭제. 기본 트레이트에 액세스해야 합니다(있는 경우). 예를 들어 세그먼트를 제거하려면 세그먼트에 속하는 트레이트를 삭제할 수 있는 권한이 필요합니다.</li></ul><br>별도의 키-값 쌍으로 여러 권한을 지정합니다. 예를 들어, `READ` 및 `WRITE` 권한만 있는 세그먼트 목록을 반환하려면 `"permissions":"READ"`, 을 전달합니다 `"permissions":"WRITE"` . |
| `includePermissions` | ([!DNL Boolean]) `true` 세그먼트에 대한 권한을 반환하도록 설정합니다. 기본값은 `false`입니다. |

### 페이지 옵션에 대한 참고 사항

페이지 정보 *가 지정되지* 않으면 요청은 배열에 일반 [!DNL JSON] 결과를 반환합니다. 페이지 정보 *를* 지정하면 반환된 목록이 총 결과 및 현재 페이지에 대한 정보가 포함된 [!DNL JSON] 개체로 래핑됩니다. 페이지 옵션을 사용한 샘플 요청은 다음과 비슷합니다.

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] for requests, staging and production environment, and versions.

## 요청 [!DNL URLs] {#request-urls}

다음 표에는 요청을 전달하는 데 [!DNL URLs] 사용되는 [!DNL API] 요청이 방법별로 나열되어 있습니다.

사용하는 인증 방법에 따라 아래 표 [!DNL URLs] 에 따라 요청을 조정해야 합니다.

### 인증 [!DNL URLs] [!DNL JWT] 요청 {#request-urls-jwt}

| [!DNL API] 메서드에서 사용할 수 있습니다 | 요청 [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://aam.adobe.io/v1/models/` |
| [!DNL Data Source] | `https://aam.adobe.io/v1/datasources/` |
| [!DNL Derived Signals] | `https://aam.adobe.io/v1/signals/derived/` |
| [!DNL Destinations] | `https://aam.adobe.io/v1/destinations/` |
| [!DNL Domains] | `https://aam.adobe.io/v1/partner-sites/` |
| [!DNL Folders] | 트레이트: `https://aam.adobe.io/v1/folders/traits /`<br>세그먼트:  `https://aam.adobe.io/v1/folders/segments /` |
| [!DNL Schema] | `https://aam.adobe.io/v1/schemas/` |
| [!DNL Segments] | `https://aam.adobe.io/v1/segments/` |
| [!DNL Traits] | `https://aam.adobe.io/v1/traits/` |
| [!DNL Trait Types] | `https://aam.adobe.io/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://aam.adobe.io/v1/taxonomies/0/` |

### 인증 요청 [!DNL URLs] (더 이상 사용되지 [!DNL OAuth] 않음) {#request-urls-oauth}

| [!DNL API] 메서드에서 사용할 수 있습니다 | 요청 [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://api.demdex.com/v1/models/` |
| [!DNL Data Source] | `https://api.demdex.com/v1/datasources/` |
| [!DNL Derived Signals] | `https://api.demdex.com/v1/signals/derived/` |
| [!DNL Destinations] | `https://api.demdex.com/v1/destinations/` |
| [!DNL Domains] | `https://api.demdex.com/v1/partner-sites/` |
| [!DNL Folders] | 트레이트: `https://api.demdex.com/v1/folders/traits /`<br>세그먼트:  `https://api.demdex.com/v1/folders/segments /` |
| [!DNL Schema] | `https://api.demdex.com/v1/schemas/` |
| [!DNL Segments] | `https://api.demdex.com/v1/segments/` |
| [!DNL Traits] | `https://api.demdex.com/v1/traits/` |
| [!DNL Trait Types] | `https://api.demdex.com/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://api.demdex.com/v1/taxonomies/0/` |

## 환경 {#environments}

이 [!DNL Audience Manager] 는 다양한 작업 환경 [!DNL API]에 대한 액세스를 제공합니다. 이러한 환경을 사용하면 라이브 프로덕션 데이터에 영향을 주지 않고 별도의 데이터베이스에 대해 코드를 테스트할 수 있습니다. 다음 표에는 사용 가능한 [!DNL API] 환경과 해당 리소스 호스트 이름이 나와 있습니다.

사용하는 인증 방법에 따라 아래 표에 [!DNL URLs] 따라 환경을 조정해야 합니다.

| 환경 | 인증에 대한 [!DNL JWT] 호스트 이름 | 인증에 대한 [!DNL OAuth] 호스트 이름 |
|---|---|---|
| **프로덕션** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **베타** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>베타 [!DNL Audience Manager] 환경은 제작 환경의 소규모 독립 실행형 버전입니다. 테스트할 모든 데이터는 이 환경에서 입력 및 수집되어야 합니다.

## 버전 {#versions}

새로운 버전의 이러한 [!DNL API]제품은 정기적으로 출시됩니다. 새 릴리스에서는 버전 번호가 [!DNL API] 증가합니다. 버전 번호는 다음 예와 [!DNL URL] 같이 요청에서 참조됩니다 `v<version number>` .

`https://<host>/v1/...`

## 정의된 응답 코드 {#response-codes-defined}

`HTTP` 상태 코드 및 응답 텍스트가 에서 반환한 [!DNL Audience Manager] 경우입니다 [!UICONTROL REST API].

| 응답 코드 ID | 응답 텍스트 | 정의 |
|---|---|---|
| `200` | `OK` | 요청이 처리되었습니다. 필요한 경우 예상 컨텐츠 또는 데이터를 반환합니다. |
| `201` | `Created` | 리소스가 만들어졌습니다. 및 요청 `PUT` 에 대한 `POST` 반환. |
| `204` | `No Content` | 리소스가 삭제되었습니다. 응답 본문은 비어 있게 됩니다. |
| `400` | `Bad Request` | 서버가 요청을 이해하지 못했습니다. 일반적으로 잘못된 구문 때문입니다. 요청을 확인하고 다시 시도하십시오. |
| `403` | `Forbidden` | 리소스에 액세스할 수 없습니다. |
| `404` | `Not Found` | 지정된 경로에 대한 리소스를 찾을 수 없습니다. |
| `409` | `Conflict` | 리소스 상태와 충돌하여 요청을 완료할 수 없습니다. |
| `500` | `Server Error` | 서버에서 예기치 않은 오류가 발생하여 요청을 수행하지 못했습니다. |

>[!MORELIKETHIS]
>
>* [JWT(서비스 계정) 인증](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [OAuth 인증](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2 단순화](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

