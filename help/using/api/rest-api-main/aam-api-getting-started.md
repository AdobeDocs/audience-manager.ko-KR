---
description: 일반 요구 사항, 인증, 선택적 쿼리 매개 변수, 요청 URL 및 기타 참조에 대한 정보입니다.
seo-description: 일반 요구 사항, 인증, 선택적 쿼리 매개 변수, 요청 URL 및 기타 참조에 대한 정보입니다.
seo-title: REST API 시작하기
solution: Audience Manager
title: REST API 시작하기
uuid: AF 0 E 527 E -6 EEC -449 C -9709-F 90 E 57 CD 188 D
translation-type: tm+mt
source-git-commit: 27800ce003a62733eece0d5de3b94737ed61133a

---


# Getting Started with REST APIs {#getting-started-with-rest-apis}

일반 요구 사항, 인증, 선택적 쿼리 매개 변수, 요청 URL 및 기타 참조에 대한 정보입니다.

<!-- c_rest_api_overview.xml -->

## API Requirements and Recommendations {#api-requirements-recommendations}

Things you must and should do when working with the Audience Manager [!DNL API]s.

<!-- aam-api-requirements.xml -->

[Audience Manager API](https://bank.demdex.com/portal/swagger/index.html#/) 코드를 사용하여 작업할 때는 다음을 참고하십시오.

* **요청 매개 변수:** 달리 지정되지 않은 한 모든 요청 매개 변수가 필요합니다.
* **[!DNL JSON]컨텐츠 유형:** 코드를 지정합니다 `content-type: application/json`**`accept: application/json` .

* **요청 및 응답:** 요청을 적절하게 서식이 지정된 [!DNL JSON] 개체로 보냅니다. [!DNL Audience Manager] 서식이 지정된 데이터로 [!DNL JSON] 응답합니다. 서버 응답에는 요청된 데이터, 상태 코드 또는 둘 다를 포함할 수 있습니다.

* **액세스:** [!DNL Audience Manager] 컨설턴트가 [!DNL API] 요청할 수 있는 클라이언트 ID와 키를 제공합니다.

* **설명서 및 코드 샘플:** *기울임꼴로* 된 텍스트는 데이터를 만들거나 수신할 [!DNL API] 때 제공하거나 전달하는 변수를 나타냅니다. *기울임꼴로 된* 텍스트를 사용자 고유의 코드, 매개 변수 또는 기타 필요한 정보로 바꿉니다.

## Recommendations: Create a Generic API User {#requirements}

We recommend you create a separate, technical user account for working with the Audience Manager [!DNL API]s. This is a generic account that is not tied to or associated with a specific user in your organization. This type of [!DNL API] user account helps you accomplish 2 things:

* Identify what service is calling the [!DNL API] (e.g., calls from your apps that use our [!DNL API]s or from other tools that make [!DNL API] requests).
* [!DNL API]s. 특정 사용자와 연결된 계정은 퇴사한 경우 삭제될 수 있습니다. This will prevent you from working with the available [!DNL API] code. 특정 직원에게 연결되지 않은 일반 계정은 이 문제를 피하는 데 도움이 됩니다.

As an example or use case for this type of account, let's say you want to change a lot of segments at once with the [Bulk Management Tools](../../reference/bulk-management-tools/bulk-management-intro.md). Well, to do this, your user account needs [!DNL API] access. Rather than add permissions to a specific user, create a non-specific, [!DNL API] user account that has the appropriate credentials, key, and secret to make [!DNL API] calls. This is also useful if you develop your own applications that use the Audience Manager [!DNL API]s.

Work with your Audience Manager consultant to set up a generic, [!DNL API]-only user account.

## OAuth Authentication {#oauth}

The Audience Manager [!UICONTROL REST API] follows [!DNL OAuth 2.0] standards for token authentication and renewal. The sections below describe how to authenticate and start working with the [!DNL API]s.

## Password Authentication Workflow {#password-authentication-workflow}

<!-- oath-authentication.xml -->

Password authentication secure access our [!DNL REST API]. The steps below outline the workflow for password authentication from a [!DNL JSON] client in your browser.

>[!TIP]
>
>데이터베이스에 저장하면 액세스 및 새로 고침 토큰을 암호화합니다.

### 1 단계: API 액세스 권한 요청

파트너 솔루션 관리자에게 문의하십시오. They will provide you with an [!DNL API] client ID and secret. The ID and secret authenticate you to the [!DNL API].

Note: If you'd like to receive a refresh token, specify that when you request [!DNL API] access.

### 2 단계: 토큰 요청

Pass in a token request with your preferred [!DNL JSON] client. 요청을 빌드할 때:

* Use a `POST` method to call `https://api.demdex.com/oauth/token`.
* 클라이언트 ID와 암호를 base -64 인코딩 문자열로 변환합니다. 변환 프로세스 중에 ID와 암호를 콜론으로 구분합니다. For example, the credentials `testId : testSecret` convert to `dGVzdElkOnRlc3RTZWNyZXQ=`.
* [!DNL HTTP] 머리글을 `Authorization:Basic <base-64 clientID:clientSecret>` 전달합니다 `Content-Type: application/x-www-form-urlencoded` . For example, your header could look like this: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* 다음과 같이 요청 본문을 설정합니다.
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

### 3 단계: 토큰 받기

The [!DNL JSON] response contains your access token. 응답은 다음과 같아야 합니다.

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

`expires_in` 키는 액세스 토큰이 만료될 때까지 초 수를 나타냅니다. 토큰이 노출될 경우 짧은 만료 시간을 사용하여 노출을 제한하는 것이 좋습니다.

## Refresh Token {#refresh-token}

Refresh tokens renew [!DNL API] access after the original token expires. If requested, the response [!DNL JSON] in the password workflow includes a refresh token. 새로 고침 토큰을 받지 못하는 경우 암호 인증 프로세스를 통해 새로 만듭니다.

새로 고침 토큰을 사용하여 기존 액세스 토큰이 만료되기 전에 새 토큰을 생성할 수도 있습니다.

If your access token has expired, you receive a `401 Status Code` and the following header in the response:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

The following steps outline the workflow for using a refresh token to create a new access token from a [!DNL JSON] client in your browser.

### 1 단계: 새 토큰 요청

Pass in a refresh token request with your preferred [!DNL JSON] client. 요청을 빌드할 때:

* Use a `POST` method to call `https://api.demdex.com/oauth/token`.
* 클라이언트 ID와 암호를 base -64 인코딩 문자열로 변환합니다. 변환 프로세스 중에 ID와 암호를 콜론으로 구분합니다. For example, the credentials `testId : testSecret` convert to `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Pass in the HTTP headers `Authorization:Basic <base-64 clientID:clientSecret>` and `Content-Type: application/x-www-form-urlencoded`. For example, your header could look like this: <br/> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/> `Content-Type: application/x-www-form-urlencoded`
* In the request body, specify the `grant_type:refresh_token` and pass in the refresh token you received in your previous access request. The request should look like this: <br/> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

### 2 단계: 새 토큰 받기

[!DNL JSON] 응답에는 새 액세스 토큰이 포함됩니다. 응답은 다음과 같아야 합니다.

```json
{
    "access_token": "4fdfc261-2ffc-4fb7-8dbd-64221714c45f",
    "token_type": "bearer",
    "refresh_token": "295fa487-1825-4caa-a715-80b81ac17dae",
    "expires_in": 21922,
    "scope": "read write"
}
```

## Authorization Code and Implicit Authentication {#authentication-code-implicit}

The Audience Manager [!UICONTROL REST API] supports authorization code and implicit authentication. To use these access methods, your users need to log in to `https://api.demdex.com/oauth/authorize` to get access and refresh tokens.

>[!MORE_ like_ this]
>
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2 간소화](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)


## Make Authenticated API Requests {#authenticated-api-requests}

Requirements for calling [!DNL API] methods after you receive an authentication token.

<!-- c_oauth_call_methods.xml -->

To make calls against the available [!DNL API] methods:

* `HTTP` 헤더에서를 설정합니다 `Authorization: Bearer <token>`.
* Call the required [!DNL API] method.

>[!MORE_ like_ this]
>
>* [OAuth 인증](../../api/rest-api-main/aam-api-getting-started.md#oauth)


## Optional API Query Parameters {#optional-api-query-parameters}

개체에 대한 모든 속성을 반환하는 메서드에 사용할 수 있는 선택적 매개 변수를 설정합니다.

<!-- c_rest_api_optional.xml -->

You can use these optional parameters with [!DNL API] methods that return *all* properties for an object. Set these options in the request string when passing that query in to the [!DNL API].

| 매개 변수 | 설명 |
|--- |--- |
| page | 결과를 페이지 번호별로 반환합니다. 번호 매기기는 0 부터 시작합니다. |
| Pagesize | 요청에 의해 반환된 응답 결과 수를 설정합니다 (10는 기본값). |
| Sortby | Sorts and returns results according to the specified [!DNL JSON] property. |
| 내림차순 | 결과를 내림차순으로 정렬하고 반환합니다. 기본값은 기본값입니다. |
| search | 검색 매개 변수로 사용하려는 지정된 문자열을 기반으로 결과를 반환합니다. 예를 들어 해당 항목에 대한 값 필드에 "test" 단어가 있는 모든 모델에 대한 결과를 찾는다고 가정합니다. Your sample request could look like this:   `GET https://api.demdex.com/v1/models/?search=Test`.  " 모두 가져오기 "방법으로 반환되는 값을 검색할 수 있습니다. |
| Folderid | 지정된 폴더 내의 특성에 대한 모든 ID를 반환합니다. 모든 메서드에서 사용할 수 없습니다. |
| 권한 | 지정된 권한을 기반으로 한 세그먼트 목록을 반환합니다. 읽기는 기본값입니다. 사용 권한:<ul><li>`READ` : 세그먼트에 대한 정보를 반환하고 봅니다.</li><li>`WRITE` : 세그먼트를 업데이트하는 `PUT` 데 사용합니다.</li><li>`CREATE` : 세그먼트를 만드는 `POST` 데 사용합니다.</li><li>`DELETE` : 세그먼트 삭제. 기본 트레이트에 대한 액세스 권한이 있어야 합니다. 예를 들어, 세그먼트를 제거하려면 세그먼트에 속하는 트레이트를 삭제할 수 있는 권한이 필요합니다.</li></ul><br>별도의 키-값 쌍으로 여러 권한을 지정합니다. For example, to return a list of segments with  `READ`  and  `WRITE`  permissions only, pass in  `"permissions":"READ"`, `"permissions":"WRITE"` . |
| Includepermissions | (부울) 세그먼트에 대한 권한을 반환하려면 true로 설정합니다. 기본값은 false입니다. |

### 페이지 옵션에 대한 참고 사항

When page information *is not* specified, the request returns plain [!DNL JSON] results in an array. If page information *is* specified, then the returned list is wrapped in a [!DNL JSON] object that contains information about the total result and current page. 페이지 옵션을 사용한 샘플 요청은 다음과 비슷합니다.

```
GET https://api.demdex.com/v1/models/?page=1&pageSize=2&search=Test
```

## API URL {#api-urls}

[!DNL URLs] 요청, 스테이징 및 프로덕션 환경, 버전을 참조하십시오.

<!-- r_rest_urls.xml -->

## Request URLs {#request-urls}

The following table lists the request URLs used to pass in [!DNL API] requests, by method.

| [!DNL API] 메서드에서 사용할 수 있습니다 | 요청 [!DNL URL] |
|--- |--- |
| 알고리즘 모델링 | `https://api.demdex.com/v1/models/` |
| 데이터 소스 | `https://api.demdex.com/v1/datasources/` |
| 파생 신호 | `https://api.demdex.com/v1/signals/derived/` |
| 대상 | `https://api.demdex.com/v1/destinations/` |
| 도메인 | `https://api.demdex.com/v1/partner-sites/` |
| 폴더 | Traits:  `https://api.demdex.com/v1/folders/traits /`<br>Segments:  `https://api.demdex.com/v1/folders/segments /` |
| 스키마 | `https://api.demdex.com/v1/schemas/` |
| 세그먼트 | `https://api.demdex.com/v1/segments/` |
| 트레이트 | `https://api.demdex.com/v1/traits/` |
| 특성 유형 | `https://api.demdex.com/v1/customer-trait-types` |
| 분류법 | `https://api.demdex.com/v1/taxonomies/0/` |

## Environments {#environments}

[!DNL Audience Manager][!DNL API]s는 서로 다른 작업 환경에 대한 액세스를 제공합니다. 이러한 환경에서는 라이브 프로덕션 데이터에 영향을 주지 않고 별도의 데이터베이스에서 코드를 테스트할 수 있습니다. The following table lists the available [!DNL API] environments and corresponding resource hostnames.

| 환경 | 호스트 이름 |
|---|---|
| **프로덕션** | `https://api.demdex.com/...` |
| **베타** | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>Audience Manager 베타 환경은 제작 환경의 독립 실행형 독립 실행형 버전입니다. 테스트하려는 모든 데이터는 이 환경에서 입력하고 수집해야 합니다.

## 버전 {#versions}

New versions of these [!DNL API]s are released on a regular schedule. A new release increments the [!DNL API] version number. The version number is referenced in the request URL as `v<version number>` as shown in the following example:

`https://<host>/v1/...`

## Response Codes Defined {#response-codes-defined}

`HTTP` Audience Manager에서 반환된 상태 코드 및 응답 텍스트입니다 [!UICONTROL REST API].

<!-- r_api_http_response_codes.xml -->

| 응답 코드 ID | 응답 텍스트 | 정의 |
|---|---|---|
| 200 | OK | 요청이 성공적으로 처리되었습니다. 필요한 경우 예상 컨텐츠나 데이터를 반환합니다. |
| 201 | created | 리소스가 생성되었습니다. Returns for `PUT` and `POST` requests. |
| 204 | 컨텐츠 없음 | 리소스가 삭제되었습니다. 응답 본문은 비어 있습니다. |
| 400 | 잘못된 요청 | 서버에서 요청을 인식하지 못했습니다. 일반적으로 잘못된 구문 때문입니다. 요청을 확인하고 다시 시도하십시오. |
| 403 | 금지됨 | 리소스에 액세스할 수 없습니다. |
| 404 | 발견되지 않음 | 지정된 경로에 리소스를 찾을 수 없습니다. |
| 409 | conflict | 리소스 상태와 충돌로 인해 요청을 완료할 수 없었습니다. |
| 500 | 서버 오류 | 서버에서 요청을 처리할 수 없는 예기치 않은 오류가 발생했습니다. |