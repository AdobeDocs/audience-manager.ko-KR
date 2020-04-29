---
description: 일반 요구 사항, 인증, 선택적 쿼리 매개 변수, 요청 URL 및 기타 참조에 대한 정보입니다.
seo-description: 일반 요구 사항, 인증, 선택적 쿼리 매개 변수, 요청 URL 및 기타 참조에 대한 정보입니다.
seo-title: REST API 시작하기
solution: Audience Manager
title: REST API 시작하기
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
translation-type: tm+mt
source-git-commit: 184f9c298f776977c375e4c7a918c5a131c4bcd1

---


# REST API 시작하기 {#getting-started-with-rest-apis}

일반 요구 사항, 인증, 선택적 쿼리 매개 변수, 요청 URL 및 기타 참조에 대한 정보입니다.

<!-- c_rest_api_overview.xml -->

## API 요구 사항 및 권장 사항 {#api-requirements-recommendations}

Audience Manager를 사용하여 작업할 때 수행해야 하는 [!DNL API]사항입니다.

<!-- aam-api-requirements.xml -->

Audience Manager API 코드 작업 시 [다음 사항을](https://bank.demdex.com/portal/swagger/index.html#/) 참고하십시오.

* **요청 매개 변수:** 별도로 지정하지 않는 한 모든 요청 매개 변수가 필요합니다.
* **[!DNL JSON]콘텐트 유형:**코드에`content-type: application/json`and **`accept: application/json`를 지정합니다.

* **요청 및 응답:** 요청을 올바른 형식의 [!DNL JSON] 개체로 보냅니다. [!DNL Audience Manager] 이에 대한 [!DNL JSON] 답변은 서식이 지정된 데이터로 이루어집니다. 서버 응답에는 요청된 데이터, 상태 코드 또는 두 가지 모두를 포함할 수 있습니다.

* **액세스:** 컨설턴트가 [!DNL Audience Manager] 클라이언트 ID와 [!DNL API] 요청을 할 수 있는 키를 제공합니다.

* **설명서 및 코드 샘플:** 기울임꼴의 *텍스트는* [!DNL API] 데이터를 만들거나 수신할 때 제공하거나 전달하는 변수를 나타냅니다. 기울임꼴 ** 텍스트를 고유한 코드, 매개 변수 또는 기타 필수 정보로 바꿀 수 있습니다.

## 인증 {#authentication}

Audience Manager REST API는 두 가지 인증 방법을 지원합니다.

* [JWT(서비스 계정)](#jwt) 인증은 권장되는 인증 방법입니다.
* [OAuth 인증(더 이상 사용되지 않음)](#oauth). 기존 OAuth 통합을 사용하는 고객은 이 방법을 계속 사용할 수 있습니다.

>[!IMPORTANT]
>
>인증 방법에 따라 요청 URL을 적절하게 조정해야 합니다. 사용해야 [하는 호스트](#environments) 이름에 대한 자세한 내용은 환경 섹션을 참조하십시오.

## JWT(서비스 계정) 인증 {#jwt}

안전한 서비스 간 Adobe I/O API 세션을 설정하려면 통합 ID를 캡슐화하는 JWT(JSON Web Token)를 만든 다음 액세스 토큰과 교환해야 합니다. Adobe 서비스에 대한 모든 요청은 Adobe I/O 콘솔에서 서비스 계정 통합을 만들 때 생성된 API 키(클라이언트 ID) [와 함께](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) 인증 헤더에 액세스 토큰을 [포함해야 합니다](https://console.adobe.io/).

인증 [구성 방법에 대한 자세한 내용은 JWT](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) (서비스 계정) 인증을 참조하십시오.

## OAuth 인증(더 이상 사용되지 않음) {#oauth}

>[!WARNING]
> 이제 Audience Manager [!UICONTROL REST API] 토큰 인증 및 갱신을 [!DNL OAuth 2.0] 사용하지 않습니다.
>
> JWT( [서비스 계정) 인증을](#jwt-service-account-authentication-jwt) 대신 사용하십시오.

Audience Manager는 토큰 인증 및 갱신에 대한 [!UICONTROL REST API] 표준을 [!DNL OAuth 2.0] 따릅니다. 아래 섹션에서는 [!DNL API]s를 인증하고 작업을 시작하는 방법을 설명합니다.

### 일반 API 사용자 만들기 {#requirements}

Audience Manager를 사용하여 작업할 수 있도록 별도의 기술 사용자 계정을 만드는 것이 [!DNL API]좋습니다.이 계정은 조직의 특정 사용자에 연결되어 있지 않거나 연결되어 있지 않은 일반 계정입니다. 이 유형의 [!DNL API] 사용자 계정은 다음 두 가지 작업을 수행하는 데 도움이 됩니다.

* 어떤 서비스가 호출되는지 [!DNL API] 확인합니다(예: Adobe를 사용하는 [!DNL API]앱이나 [!DNL API] 요청을 수행하는 다른 도구에서 거는 호출).
* 중단 없이 [!DNL API]s에 액세스특정 사람에 연결된 계정은 회사를 떠날 때 삭제될 수 있습니다. 이렇게 하면 사용 가능한 [!DNL API] 코드를 사용할 수 없습니다. 특정 직원과 연결되지 않은 일반 계정은 이 문제를 해결하는 데 도움이 됩니다.

이 유형의 계정에 대한 예 또는 사용 사례로서 벌크 관리 도구를 사용하여 한 번에 많은 세그먼트를 [변경한다고 가정합니다](../../reference/bulk-management-tools/bulk-management-intro.md). 이렇게 하려면 사용자 계정에 [!DNL API] 액세스할 수 있어야 합니다. 특정 사용자에게 권한을 추가하는 대신 적절한 자격 증명, 키 및 암호를 가진 비특정 [!DNL API] 사용자 계정을 만들어 [!DNL API] 호출합니다. 이 기능은 Audience Manager를 사용하는 자체 응용 프로그램을 개발하는 경우에도 유용합니다. [!DNL API]

Audience Manager 컨설턴트와 협력하여 일반 [!DNL API]전용 사용자 계정을 설정합니다.

### 암호 인증 워크플로우 {#password-authentication-workflow}

<!-- oath-authentication.xml -->

암호 인증을 통해 안전하게 액세스할 수 [!DNL REST API]있습니다. 아래 단계에서는 브라우저의 [!DNL JSON] 클라이언트에서 암호 인증을 위한 워크플로우에 대해 간략하게 설명합니다.

>[!TIP]
>
>액세스 권한을 암호화하고 토큰을 데이터베이스에 저장하는 경우 토큰을 새로 고칩니다.

#### 1단계:API 액세스 요청

파트너 솔루션 관리자에게 문의하십시오. 클라이언트 ID와 [!DNL API] 암호를 제공합니다. ID와 비밀은 사용자를 Adobe Creative Cloud에 [!DNL API]인증합니다.

참고:새로 고침 토큰을 받으려면 액세스 [!DNL API] 권한을 요청할 때 이 토큰을 지정합니다.

#### 2단계:토큰 요청

기본 [!DNL JSON] 클라이언트와 함께 토큰 요청을 전달합니다. 요청을 빌드할 때:

* 메서드를 사용하여 `POST` 호출합니다 `https://api.demdex.com/oauth/token`.
* 클라이언트 ID와 암호를 기본-64 인코딩 문자열로 변환합니다. 변환 프로세스 중에 ID와 암호를 콜론으로 구분합니다. 예를 들어 자격 증명은 `testId : testSecret` 로 변환됩니다 `dGVzdElkOnRlc3RTZWNyZXQ=`.
* 헤더와 [!DNL HTTP] 을 `Authorization:Basic <base-64 clientID:clientSecret>` 전달합니다 `Content-Type: application/x-www-form-urlencoded` . 예를 들어 헤더는 다음과 같을 수 있습니다. <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* 다음과 같이 요청 본문을 설정합니다.
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### 3단계:토큰 받기

응답에 액세스 토큰이 포함되어 [!DNL JSON] 있습니다. 응답은 다음과 같아야 합니다.

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

이 `expires_in` 키는 액세스 토큰이 만료될 때까지 남은 시간(초)을 나타냅니다. 토큰이 노출되면 짧은 만료 시간을 사용하여 노출을 제한하는 것이 좋습니다.

### 토큰 새로 고침 {#refresh-token}

토큰 새로 고침은 원래 토큰이 만료된 후에 액세스 [!DNL API] 권한을 갱신합니다. 요청 시 암호 [!DNL JSON] 워크플로우의 응답에 새로 고침 토큰이 포함됩니다. 새로 고침 토큰을 받지 못한 경우 암호 인증 프로세스를 통해 새 토큰을 만드십시오.

기존 액세스 토큰이 만료되기 전에 새로 고침 토큰을 사용하여 새 토큰을 생성할 수도 있습니다.

액세스 토큰이 만료되면 응답에서 `401 Status Code` 다음과 같은 헤더가 수신됩니다.

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

다음 단계에서는 새로 고침 토큰을 사용하여 브라우저의 [!DNL JSON] 클라이언트에서 새 액세스 토큰을 만드는 워크플로우의 개요를 설명합니다.

#### 1단계:새 토큰 요청

기본 [!DNL JSON] 클라이언트와 함께 새로 고침 토큰 요청을 전달합니다. 요청을 빌드할 때:

* 메서드를 사용하여 `POST` 호출합니다 `https://api.demdex.com/oauth/token`.
<!-- * Request headers: when using [Adobe I/O](https://www.adobe.io/) tokens, you must provide the `x-api-key` header. You can get your API key by following the instructions in the [Service Account Integration](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) page. -->
* 클라이언트 ID와 암호를 기본-64 인코딩 문자열로 변환합니다. 변환 프로세스 중에 ID와 암호를 콜론으로 구분합니다. 예를 들어 자격 증명은 `testId : testSecret` 로 변환됩니다 `dGVzdElkOnRlc3RTZWNyZXQ=`.
* HTTP 헤더와 `Authorization:Basic <base-64 clientID:clientSecret>` HTTP 헤더에 `Content-Type: application/x-www-form-urlencoded`전달합니다. 예를 들어 헤더는 다음과 같을 수 있습니다. <br/> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/> `Content-Type: application/x-www-form-urlencoded`
* 요청 본문에서는 이전 액세스 요청에서 받은 새로 고침 토큰을 `grant_type:refresh_token` 지정하고 전달합니다. 요청은 다음과 같아야 합니다. <br/> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### 2단계:새 토큰 받기

응답에 새 액세스 토큰이 포함되어 [!DNL JSON] 있습니다. 응답은 다음과 같아야 합니다.

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

Audience Manager는 인증 코드 및 암시적 인증을 [!UICONTROL REST API] 지원합니다. 이러한 액세스 방법을 사용하려면 사용자가 로그인하여 토큰을 액세스하고 새로 `https://api.demdex.com/oauth/authorize` 고쳐야 합니다.

## 인증된 API 요청 만들기 {#authenticated-api-requests}

인증 토큰을 받은 후 메서드를 호출하는 [!DNL API] 데 필요한 요구 사항입니다.

<!-- c_oauth_call_methods.xml -->

사용 가능한 [!DNL API] 메서드에 대해 호출하려면

* 헤더에서 `HTTP` 를 설정합니다 `Authorization: Bearer <token>`.
* JWT( [서비스 계정) 인증을](#jwt)사용할 때 `x-api-key` 헤더가 있어야 합니다. 이 헤더는 사용자와 `client_id`동일합니다. Adobe I/ `client_id` O 통합 [페이지에서](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) 작업을 시작할 수 있습니다.
* 필요한 [!DNL API] 메서드를 호출합니다.

## 선택적 API 쿼리 매개 변수 {#optional-api-query-parameters}

객체의 모든 속성을 반환하는 메서드에 사용할 수 있는 선택적 매개 변수를 설정합니다.

<!-- c_rest_api_optional.xml -->

객체에 대한 [!DNL API] 모든 ** 속성을 반환하는 메서드와 함께 이러한 선택적 매개 변수를 사용할 수 있습니다. 요청 문자열에서 해당 쿼리를 [!DNL API]에 전달할 때 이 옵션을 설정합니다.

| 매개 변수 | 설명 |
|--- |--- |
| page | 페이지 번호별로 결과를 반환합니다. 번호는 0부터 시작됩니다. |
| pageSize | 요청에 의해 반환되는 응답 결과 수를 설정합니다(기본값 10). |
| sortBy | 지정된 [!DNL JSON] 속성에 따라 결과를 정렬하고 반환합니다. |
| 내림차순 | 결과를 내림차순으로 정렬하고 반환합니다. 기본값은 오름차순입니다. |
| search | 검색 매개 변수로 사용할 지정된 문자열을 기반으로 결과를 반환합니다. 예를 들어 해당 항목에 대한 값 필드에 &quot;테스트&quot;라는 단어가 있는 모든 모델의 결과를 찾으려 합니다. 샘플 요청은 다음과 같습니다.  `GET https://aam.adobe.io/v1/models/?search=Test`Adobe  &quot;모두 가져오기&quot; 메서드에서 반환되는 값을 검색할 수 있습니다. |
| folderId | 지정된 폴더 내의 트레이트에 대한 모든 ID를 반환합니다. 일부 메서드는 사용할 수 없습니다. |
| 권한 | 지정된 권한을 기반으로 세그먼트 목록을 반환합니다.  READ가 기본값입니다. 사용 권한에는 다음이 포함됩니다.<ul><li>`READ` :세그먼트에 대한 정보를 반환하고 봅니다.</li><li>`WRITE` :세그먼트를 업데이트하는 `PUT` 데 사용합니다.</li><li>`CREATE` :세그먼트를 `POST` 만드는 데 사용합니다.</li><li>`DELETE` : 세그먼트 삭제. 기본 트레이트에 대한 액세스(있는 경우)가 필요합니다. 예를 들어 세그먼트를 제거하려면 해당 세그먼트에 속하는 트레이트를 삭제할 수 있는 권한이 필요합니다.</li></ul><br>개별 키-값 쌍으로 여러 권한을 지정합니다. 예를 들어, `READ` 및 `WRITE` 권한만 있는 세그먼트 목록을 반환하려면 `"permissions":"READ"`을 전달합니다 `"permissions":"WRITE"` . |
| includePermissions | (부울) 세그먼트에 대한 권한을 반환하려면 true로 설정합니다. 기본값은 false입니다. |

### 페이지 옵션에 대한 참고 사항

페이지 정보를 *지정하지 않으면* 요청은 배열로 일반 [!DNL JSON] 결과를 반환합니다. 페이지 정보를 *지정하면* 반환된 목록이 총 결과 및 현재 페이지에 대한 정보가 포함된 [!DNL JSON] 개체로 래핑됩니다. 페이지 옵션을 사용한 샘플 요청은 다음과 비슷합니다.

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## API URL {#api-urls}

[!DNL URLs] for requests, staging and production environment, and versions.

<!-- r_rest_urls.xml -->

## URL 요청 {#request-urls}

다음 표에는 [!DNL API] 요청을 전달하는 데 사용되는 요청 URL이 메서드별로 나열되어 있습니다.

사용하는 인증 방법에 따라 아래 표에 따라 요청 URL을 조정해야 합니다.

### JWT 인증에 대한 URL 요청 {#request-urls-jwt}

| [!DNL API] 메서드에서 사용할 수 있습니다 | 요청 [!DNL URL] |
|--- |--- |
| 알고리즘 모델링 | `https://aam.adobe.io/v1/models/` |
| 데이터 소스 | `https://aam.adobe.io/v1/datasources/` |
| 파생 신호 | `https://aam.adobe.io/v1/signals/derived/` |
| 대상 | `https://aam.adobe.io/v1/destinations/` |
| 도메인 | `https://aam.adobe.io/v1/partner-sites/` |
| 폴더 | 트레이트: 세그먼트 `https://aam.adobe.io/v1/folders/traits /`<br>:  `https://aam.adobe.io/v1/folders/segments /` |
| 스키마 | `https://aam.adobe.io/v1/schemas/` |
| 세그먼트 | `https://aam.adobe.io/v1/segments/` |
| 트레이트 | `https://aam.adobe.io/v1/traits/` |
| 특성 유형 | `https://aam.adobe.io/v1/customer-trait-types` |
| 분류 | `https://aam.adobe.io/v1/taxonomies/0/` |

### OAuth 인증에 대한 URL 요청(더 이상 사용되지 않음) {#request-urls-oauth}

| [!DNL API] 메서드에서 사용할 수 있습니다 | 요청 [!DNL URL] |
|--- |--- |
| 알고리즘 모델링 | `https://api.demdex.com/v1/models/` |
| 데이터 소스 | `https://api.demdex.com/v1/datasources/` |
| 파생 신호 | `https://api.demdex.com/v1/signals/derived/` |
| 대상 | `https://api.demdex.com/v1/destinations/` |
| 도메인 | `https://api.demdex.com/v1/partner-sites/` |
| 폴더 | 트레이트: 세그먼트 `https://api.demdex.com/v1/folders/traits /`<br>:  `https://api.demdex.com/v1/folders/segments /` |
| 스키마 | `https://api.demdex.com/v1/schemas/` |
| 세그먼트 | `https://api.demdex.com/v1/segments/` |
| 트레이트 | `https://api.demdex.com/v1/traits/` |
| 특성 유형 | `https://api.demdex.com/v1/customer-trait-types` |
| 분류 | `https://api.demdex.com/v1/taxonomies/0/` |

## 환경 {#environments}

Adobe [!DNL Audience Manager] Experience Manager [!DNL API]를 사용하면 다양한 작업 환경에 액세스할 수 있습니다. 이러한 환경을 사용하면 라이브 프로덕션 데이터에 영향을 주지 않고 별도의 데이터베이스에 대해 코드를 테스트할 수 있습니다. 다음 표에는 사용 가능한 [!DNL API] 환경과 해당 리소스 호스트 이름이 나와 있습니다.

사용하는 인증 방법에 따라 아래 표에 따라 환경 URL을 조정해야 합니다.

| 환경 | OAuth 인증에 대한 호스트 이름 | JWT 인증의 호스트 이름 |
|---|---|---|
| **프로덕션** | `https://api.demdex.com/...` | `https://aam.adobe.io/...` |
| **베타** | `https://api-beta.demdex.com/...` | `https://aam-beta.adobe.io/...` |

>[!NOTE]
>
>Audience Manager 베타 환경은 더 작은 규모의 독립 실행형 제작 환경입니다. 테스트할 모든 데이터는 이 환경에서 입력 및 수집되어야 합니다.

## 버전 {#versions}

새로운 버전의 [!DNL API]제품은 정기적으로 출시됩니다. 새 릴리스에서는 버전 번호가 증가됩니다 [!DNL API] . 버전 번호는 다음 예와 `v<version number>` 같이 요청 URL에서 참조됩니다.

`https://<host>/v1/...`

## 정의된 응답 코드 {#response-codes-defined}

`HTTP` Audience Manager에서 반환되는 상태 코드 및 응답 텍스트입니다 [!UICONTROL REST API].

<!-- r_api_http_response_codes.xml -->

| 응답 코드 ID | 응답 텍스트 | 정의 |
|---|---|---|
| 200 | OK | 요청이 성공적으로 처리되었습니다. 필요한 경우 예상 콘텐츠 또는 데이터를 반환합니다. |
| 201 | 작성일 | 리소스가 만들어졌습니다. 및 `PUT` 요청에 대한 `POST` 반환. |
| 204 | 컨텐츠 없음 | 리소스가 삭제되었습니다. 응답 본문이 비어 있게 됩니다. |
| 400 | 잘못된 요청 | 서버가 요청을 이해하지 못했습니다. 일반적으로 잘못된 구문 때문입니다. 요청을 확인하고 다시 시도하십시오. |
| 403 | 금지 | 리소스에 대한 액세스 권한이 없습니다. |
| 404 | 발견되지 않음 | 지정된 경로에 대한 리소스를 찾을 수 없습니다. |
| 409 | 충돌 | 리소스 상태와 충돌하여 요청을 완료할 수 없습니다. |
| 500 | 서버 오류 | 서버에서 예기치 않은 오류가 발생하여 요청을 수행하지 못했습니다. |

>[!MORELIKETHIS]
>
>* [JWT(서비스 계정) 인증](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [OAuth 인증](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2 단순화](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

