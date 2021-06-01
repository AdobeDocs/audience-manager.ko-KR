---
description: 일반 요구 사항, 인증, 선택적 쿼리 매개 변수, 요청 URL 및 기타 참조에 대한 정보를 제공합니다.
seo-description: 일반 요구 사항, 인증, 선택적 쿼리 매개 변수, 요청 URL 및 기타 참조에 대한 정보를 제공합니다.
seo-title: REST API 시작
solution: Audience Manager
title: REST API 시작
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
exl-id: f7d5e52d-ad21-4020-a299-d440f954c51a
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1861'
ht-degree: 3%

---

# [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis} 시작하기

일반 요구 사항, 인증, 선택적 쿼리 매개 변수, 요청 [!DNL URLs] 및 기타 참조에 대한 정보입니다.

<!-- c_rest_api_overview.xml -->

## API 요구 사항 및 권장 사항 {#api-requirements-recommendations}

[!DNL Audience Manager] [!DNL API]s를 사용하여 작업할 때 수행해야 하는 작업입니다.

<!-- aam-api-requirements.xml -->

[Audience Manager API](https://bank.demdex.com/portal/swagger/index.html#/) 코드를 사용하여 작업할 때에는 다음을 참고하십시오.

* **요청 매개 변수:** 별도로 지정하지 않는 한 모든 요청 매개 변수가 필요합니다.
* **요청 헤더**:Adobe  [I/Otokens를 사용할 ](https://www.adobe.io/) 때 헤더를 제공해야  `x-api-key` 합니다. [서비스 계정 통합](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) 페이지의 지침에 따라 [!DNL API] 키를 가져올 수 있습니다.
* **[!DNL JSON]컨텐츠 유형:** 코드 `content-type: application/json`  **  `accept: application/json` 에 및 를 지정합니다.
* **요청 및 응답:** 요청을 올바른 형식의 개체로  [!DNL JSON] 보냅니다. [!DNL Audience Manager] 형식이  [!DNL JSON] 지정된 데이터에 응답합니다. 서버 응답에는 요청된 데이터, 상태 코드 또는 둘 다 포함될 수 있습니다.
* **액세스:** 컨설턴트 [!DNL Audience Manager] 가 요청을 수행할 수 있는 클라이언트 ID와 키를  [!DNL API] 제공합니다.
* **설명서 및 코드 샘플:**  ** 이탤릭체로 된 텍스트는 데이터를 만들거나 받을 때 제공하거나 전달하는 변수를  [!DNL API] 나타냅니다. *기울임꼴* 텍스트를 사용자의 코드, 매개 변수 또는 기타 필수 정보로 바꿉니다.

## 인증 {#authentication}

[!DNL Audience Manager] [!DNL REST APIs]은 두 가지 인증 방법을 지원합니다.

* [JWT(서비스 계정) ](#jwt)  [Adobe I/O](https://www.adobe.io/)를 사용한 인증. [!DNL Adobe I/O] 는 Adobe의 개발자 에코시스템과 커뮤니티입니다. 여기에는 [Adobe I/O 개발자 도구 및 API](https://www.adobe.io/apis/experienceplatform.html) 및 모든 Adobe 제품에 대한 [API가 포함됩니다](https://www.adobe.io/apis.html). 이는 [!DNL Adobe] [!DNL APIs] 을 설정하고 사용하는 데 권장되는 방법입니다.
* [OAuth 인증(더 이상 사용되지 않음)](#oauth). 이 메서드는 더 이상 사용되지 않지만, 기존 [!DNL OAuth] 통합을 사용하는 고객은 이 메서드를 계속 사용할 수 있습니다.

>[!IMPORTANT]
>
>인증 방법에 따라 요청 [!DNL URLs]을 적절하게 조정해야 합니다. 사용해야 하는 호스트 이름에 대한 자세한 내용은 [환경](#environments) 섹션을 참조하십시오.

## [!DNL JWT] ([!DNL Service Account]) Adobe I/O을 사용한 인증 {#jwt}

### Adobe I/O 개요 {#adobeio}

[!DNL Adobe I/O] 는 Adobe의 개발자 에코시스템과 커뮤니티입니다. 여기에는 [Adobe I/O 개발자 도구 및 API](https://www.adobe.io/apis/experienceplatform.html) 및 모든 Adobe 제품에 대한 [API가 포함됩니다](https://www.adobe.io/apis.html).

이는 [!DNL Adobe] [!DNL APIs] 을 설정하고 사용하는 데 권장되는 방법입니다.

### 사전 요구 사항 {#prerequisites}

[!DNL JWT] 인증을 구성하기 전에 [Adobe I/O](https://www.adobe.io/)에서 [Adobe 개발자 콘솔](https://console.adobe.io/)에 액세스할 수 있는지 확인하십시오. 액세스 요청에 대해서는 조직 관리자에게 문의하십시오.

### 인증 {#auth}

아래 절차에 따라 [!DNL Adobe I/O]을 사용하여 [!DNL JWT (Service Account)] 인증을 구성하십시오.

1. [Adobe 개발자 콘솔](https://console.adobe.io/)에 로그인합니다.
1. [서비스 계정 연결](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)의 단계를 수행합니다.
   * [단계 2:서비스 계정 인증](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)을(를) 사용하여 프로젝트에 API를 추가하고 [!DNL Audience Manager] [!DNL API] 옵션을 선택합니다.
1. [3단계](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)의 지침에 따라 첫 번째 [!DNL API] 호출을 수행하여 연결을 테스트합니다.

>[!NOTE]
>
>[!DNL Audience Manager] [!DNL REST APIs] 을 자동으로 구성하고 작업하려면 프로그래밍 방식으로 [!DNL JWT] 를 생성할 수 있습니다. 자세한 지침은 [JWT(서비스 계정) 인증](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)을 참조하십시오.

## [!DNL OAuth] 인증(더 이상 사용되지 않음) {#oauth}

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] 를 통한 토큰 인증 및 갱신 [!DNL OAuth 2.0] 은 이제 더 이상 사용되지 않습니다.
>
> [JWT(서비스 계정) 인증](#jwt-service-account-authentication-jwt)을 대신 사용하십시오.

[!DNL Audience Manager] [!UICONTROL REST API]은 토큰 인증 및 갱신에 대한 [!DNL OAuth 2.0] 표준을 따릅니다. 아래 섹션에서는 [!DNL API]s를 인증하고 작업을 시작하는 방법에 대해 설명합니다.

### 일반 [!DNL API] 사용자 만들기 {#requirements}

[!DNL Audience Manager] [!DNL API]s 작업을 위한 별도의 기술 사용자 계정을 만드는 것이 좋습니다.조직의 특정 사용자에게 연결되어 있지 않거나 관련 없는 일반 계정입니다. 이러한 유형의 [!DNL API] 사용자 계정은 다음 두 가지 작업을 수행하는 데 도움이 됩니다.

* [!DNL API] 을 호출하는 서비스(예: [!DNL API]을 사용하는 앱이나 [!DNL API] 요청을 수행하는 다른 도구에서 호출)를 식별합니다.
* [!DNL API]에 대한 끊김 없는 액세스를 제공합니다.특정 사용자에 연결된 계정은 회사를 나갈 때 삭제할 수 있습니다. 이렇게 하면 사용 가능한 [!DNL API] 코드로 작업할 수 없습니다. 특정 직원에 연결되지 않은 일반 계정은 이 문제를 방지하는 데 도움이 됩니다.

이러한 유형의 계정에 대한 예나 사용 사례로서 [벌크 관리 도구](../../reference/bulk-management-tools/bulk-management-intro.md)를 사용하여 한 번에 많은 세그먼트를 변경하려고 한다고 가정합니다. 이렇게 하려면 사용자 계정에 [!DNL API] 액세스가 필요합니다. 특정 사용자에 대한 권한을 추가하는 대신, 적절한 자격 증명, 키 및 암호가 있는 특정하지 않은 [!DNL API] 사용자 계정을 만들어 [!DNL API] 호출을 수행합니다. 이 기능은 [!DNL Audience Manager] [!DNL API]s를 사용하는 애플리케이션을 개발하는 경우에도 유용합니다.

[!DNL Audience Manager] 컨설턴트와 협력하여 일반 [!DNL API] 전용 사용자 계정을 설정합니다.

### 암호 인증 워크플로우 {#password-authentication-workflow}

암호 인증은 [!DNL REST API]에 안전하게 액세스합니다. 아래 단계는 브라우저의 [!DNL JSON] 클라이언트에서 암호 인증을 위한 워크플로우에 대해 간략하게 설명합니다.

>[!TIP]
>
>액세스 및 토큰을 데이터베이스에 저장하는 경우 토큰을 암호화하고 새로 고칩니다.

#### 1단계:[!DNL API] 액세스 요청

파트너 솔루션 관리자에게 문의하십시오. 그러면 [!DNL API] 클라이언트 ID와 암호가 제공됩니다. ID와 암호는 [!DNL API]에 인증됩니다.

참고:새로 고침 토큰을 받으려면 [!DNL API] 액세스를 요청할 때 을 지정합니다.

#### 2단계:토큰 요청

선호하는 [!DNL JSON] 클라이언트와 함께 토큰 요청을 전달합니다. 요청을 작성하는 경우:

* `POST` 메서드를 사용하여 `https://api.demdex.com/oauth/token`을 호출합니다.
* 클라이언트 ID와 암호를 기본-64 인코딩 문자열로 변환합니다. 전환 프로세스 중에 ID와 암호를 콜론으로 구분합니다. 예를 들어 자격 증명 `testId : testSecret`은 `dGVzdElkOnRlc3RTZWNyZXQ=`로 변환됩니다.
* [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` 및 `Content-Type: application/x-www-form-urlencoded`에 전달하십시오. 예를 들어 헤더는 다음과 같을 수 있습니다.<br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* 다음과 같이 요청 본문을 설정합니다.
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### 3단계:토큰 받기

[!DNL JSON] 응답에는 액세스 토큰이 포함되어 있습니다. 응답은 다음과 같습니다.

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

`expires_in` 키는 액세스 토큰이 만료될 때까지의 시간(초)을 나타냅니다. 토큰을 노출하는 경우 짧은 만료 시간을 사용하여 노출을 제한하는 것이 좋습니다.

### 토큰 새로 고침 {#refresh-token}

새로 고침 토큰은 원래 토큰이 만료된 후 [!DNL API] 액세스를 갱신합니다. 요청한 경우 암호 워크플로우의 응답 [!DNL JSON]에 새로 고침 토큰이 포함됩니다. 새로 고침 토큰을 받지 않은 경우 암호 인증 프로세스를 통해 새 토큰을 만드십시오.

기존 액세스 토큰이 만료되기 전에 새로 고침 토큰을 사용하여 새 토큰을 생성할 수도 있습니다.

액세스 토큰이 만료되면 응답에서 `401 Status Code` 및 다음 헤더를 받게 됩니다.

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

다음 단계는 새로 고침 토큰을 사용하여 브라우저의 [!DNL JSON] 클라이언트에서 새 액세스 토큰을 만드는 워크플로우에 대해 설명합니다.

#### 1단계:새 토큰 요청

선호하는 [!DNL JSON] 클라이언트와 함께 새로 고침 토큰 요청을 전달합니다. 요청을 작성하는 경우:

* `POST` 메서드를 사용하여 `https://api.demdex.com/oauth/token`을 호출합니다.
* 클라이언트 ID와 암호를 기본-64 인코딩 문자열로 변환합니다. 전환 프로세스 중에 ID와 암호를 콜론으로 구분합니다. 예를 들어 자격 증명 `testId : testSecret`은 `dGVzdElkOnRlc3RTZWNyZXQ=`로 변환됩니다.
* HTTP 헤더 `Authorization:Basic <base-64 clientID:clientSecret>` 및 `Content-Type: application/x-www-form-urlencoded`에 전달합니다. 예를 들어 헤더는 다음과 같을 수 있습니다.<br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* 요청 본문에서 `grant_type:refresh_token`을(를) 지정하고 이전 액세스 요청에서 받은 새로 고침 토큰을 전달합니다. 요청은 다음과 같아야 합니다.<br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### 2단계:새 토큰 받기

[!DNL JSON] 응답에는 새 액세스 토큰이 포함되어 있습니다. 응답은 다음과 같습니다.

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

[!DNL Audience Manager] [!UICONTROL REST API]은 인증 코드와 암시적 인증을 지원합니다. 이러한 액세스 방법을 사용하려면 사용자가 `https://api.demdex.com/oauth/authorize`에 로그인하여 액세스 및 토큰을 새로 고쳐야 합니다.

## 인증됨 [!DNL API] 요청 만들기 {#authenticated-api-requests}

인증 토큰을 받은 후 [!DNL API] 메서드를 호출하기 위한 요구 사항입니다.

사용 가능한 [!DNL API] 메서드에 대해 를 호출하려면 다음을 수행하십시오.

* `HTTP` 헤더에서 `Authorization: Bearer <token>` 을 설정합니다.
* [JWT(서비스 계정) 인증](#jwt)을 사용할 때는 `client_id`과 동일한 `x-api-key` 헤더를 제공해야 합니다. [Adobe I/O 통합](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) 페이지에서 `client_id`을 가져올 수 있습니다.
* 필요한 [!DNL API] 메서드를 호출합니다.

## 선택 사항 [!DNL API] 쿼리 매개 변수 {#optional-api-query-parameters}

개체의 모든 속성을 반환하는 메서드에 사용할 수 있는 선택적 매개 변수를 설정합니다.

객체에 대해 *모든* 속성을 반환하는 [!DNL API] 메서드와 함께 이러한 선택적 매개 변수를 사용할 수 있습니다. 해당 쿼리를 [!DNL API]에 전달할 때 요청 문자열에서 이러한 옵션을 설정합니다.

| 매개 변수 | 설명 |
|--- |--- |
| `page` | 페이지 번호별로 결과를 반환합니다. 번호 매기는 0부터 시작됩니다. |
| `pageSize` | 요청에서 반환된 응답 결과 수를 설정합니다(10은 기본값). |
| `sortBy` | 지정된 [!DNL JSON] 속성에 따라 결과를 정렬 및 반환합니다. |
| `descending` | 결과를 내림차순으로 정렬하고 반환합니다. `ascending` 기본값은 입니다. |
| `search` | 검색 매개 변수로 사용할 지정된 문자열을 기반으로 결과를 반환합니다. 예를 들어 해당 항목의 값 필드에 &quot;Test&quot;라는 단어가 있는 모든 모델에 대한 결과를 찾겠다고 가정합니다. 샘플 요청은 다음과 같을 수 있습니다.   `GET https://aam.adobe.io/v1/models/?search=Test`  &quot;[!DNL get all]&quot; 메서드에서 반환된 값을 검색할 수 있습니다. |
| `folderId` | 지정된 폴더 내의 [!UICONTROL traits]에 대한 모든 ID를 반환합니다. 일부 메서드에서는 사용할 수 없습니다. |
| `permissions` | 지정된 권한을 기반으로 세그먼트 목록을 반환합니다. `READ` 기본값은 입니다. 권한은 다음과 같습니다.<ul><li>`READ` :세그먼트에 대한 정보를 반환하고 봅니다.</li><li>`WRITE` :세그먼트  `PUT`  를 업데이트하려면 을(를) 사용하십시오.</li><li>`CREATE` :을   `POST`  사용하여 세그먼트를 만듭니다.</li><li>`DELETE` : 세그먼트 삭제. 기본 트레이트에 대한 액세스(있는 경우)가 필요합니다. 예를 들어 세그먼트를 제거하려면 세그먼트에 속하는 트레이트를 삭제할 수 있는 권한이 필요합니다.</li></ul><br>별도의 키-값 쌍으로 여러 권한을 지정합니다. 예를 들어 `READ` 및 `WRITE` 권한만 있는 세그먼트 목록을 반환하려면 `"permissions":"READ"`, `"permissions":"WRITE"` 로 전달하십시오. |
| `includePermissions` | ([!DNL Boolean]) 세그먼트에 대한 권한을 반환하려면 `true` 로 설정하십시오. 기본값은 `false`입니다. |

### 페이지 옵션에 대한 참고 사항

페이지 정보 *가 지정되지 않은 경우 요청이 일반 [!DNL JSON]를 반환하면 배열이 발생합니다.* 페이지 정보 *가*&#x200B;인 경우, 반환된 목록이 총 결과 및 현재 페이지에 대한 정보를 포함하는 [!DNL JSON] 개체에 래핑됩니다. 페이지 옵션을 사용하는 샘플 요청은 다음과 유사할 수 있습니다.

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] 요청, 스테이징 및 프로덕션 환경, 버전에 대해 설명합니다.

## 요청 [!DNL URLs] {#request-urls}

다음 표에는 [!DNL API] 요청을 메서드로 전달하는 데 사용되는 요청 [!DNL URLs]이 나열되어 있습니다.

사용하는 인증 방법에 따라 아래 표에 따라 요청 [!DNL URLs]을 조정해야 합니다.

### [!DNL JWT] 인증 {#request-urls-jwt}에 대해 [!DNL URLs] 요청

| [!DNL API] 메서드에서 사용할 수 있습니다 | 요청 [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://aam.adobe.io/v1/models/` |
| [!DNL Data Source] | `https://aam.adobe.io/v1/datasources/` |
| [!DNL Derived Signals] | `https://aam.adobe.io/v1/signals/derived/` |
| [!DNL Destinations] | `https://aam.adobe.io/v1/destinations/` |
| [!DNL Domains] | `https://aam.adobe.io/v1/partner-sites/` |
| [!DNL Folders] | 트레이트: `https://aam.adobe.io/v1/folders/traits /`<br>세그먼트: `https://aam.adobe.io/v1/folders/segments /` |
| [!DNL Schema] | `https://aam.adobe.io/v1/schemas/` |
| [!DNL Segments] | `https://aam.adobe.io/v1/segments/` |
| [!DNL Traits] | `https://aam.adobe.io/v1/traits/` |
| [!DNL Trait Types] | `https://aam.adobe.io/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://aam.adobe.io/v1/taxonomies/0/` |

### [!DNL OAuth] 인증 요청(사용 중지) {#request-urls-oauth}[!DNL URLs]

| [!DNL API] 메서드에서 사용할 수 있습니다 | 요청 [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://api.demdex.com/v1/models/` |
| [!DNL Data Source] | `https://api.demdex.com/v1/datasources/` |
| [!DNL Derived Signals] | `https://api.demdex.com/v1/signals/derived/` |
| [!DNL Destinations] | `https://api.demdex.com/v1/destinations/` |
| [!DNL Domains] | `https://api.demdex.com/v1/partner-sites/` |
| [!DNL Folders] | 트레이트: `https://api.demdex.com/v1/folders/traits /`<br>세그먼트: `https://api.demdex.com/v1/folders/segments /` |
| [!DNL Schema] | `https://api.demdex.com/v1/schemas/` |
| [!DNL Segments] | `https://api.demdex.com/v1/segments/` |
| [!DNL Traits] | `https://api.demdex.com/v1/traits/` |
| [!DNL Trait Types] | `https://api.demdex.com/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://api.demdex.com/v1/taxonomies/0/` |

## 환경 {#environments}

[!DNL Audience Manager] [!DNL API]은(는) 다른 작업 환경에 액세스할 수 있도록 합니다. 이러한 환경은 라이브 프로덕션 데이터에 영향을 주지 않고 별도의 데이터베이스에 대해 코드를 테스트하는 데 도움이 됩니다. 다음 표에는 사용 가능한 [!DNL API] 환경과 해당 리소스 호스트 이름이 나와 있습니다.

사용하는 인증 방법에 따라 아래 표에 따라 환경 [!DNL URLs]을 조정해야 합니다.

| 환경 | [!DNL JWT] 인증에 대한 호스트 이름 | [!DNL OAuth] 인증에 대한 호스트 이름 |
|---|---|---|
| **프로덕션** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>[!DNL Audience Manager] 베타 환경은 작은 규모의 독립 실행형 프로덕션 환경입니다. 테스트할 모든 데이터를 이 환경에서 입력하고 수집해야 합니다.

## 버전 {#versions}

이러한 [!DNL API]의 새 버전은 정기적으로 출시됩니다. 새 릴리스는 [!DNL API] 버전 번호를 증가시킵니다. 버전 번호는 다음 예와 같이 [!DNL URL] 요청에서 `v<version number>` 로 참조됩니다.

`https://<host>/v1/...`

## 정의된 응답 코드 {#response-codes-defined}

`HTTP` 에서 반환한 상태 코드 및 응답 텍스트입니다  [!DNL Audience Manager] [!UICONTROL REST API].

| 응답 코드 ID | 응답 텍스트 | 정의 |
|---|---|---|
| `200` | `OK` | 요청이 성공적으로 처리되었습니다. 필요한 경우 예상 콘텐츠 또는 데이터를 반환합니다. |
| `201` | `Created` | 리소스를 만들었습니다. `PUT` 및 `POST` 요청에 대해 를 반환합니다. |
| `204` | `No Content` | 리소스가 삭제되었습니다. 응답 본문은 비어 있습니다. |
| `400` | `Bad Request` | 서버가 요청을 이해하지 못했습니다. 일반적으로 잘못된 구문 때문에 발생합니다. 요청을 확인하고 다시 시도하십시오. |
| `403` | `Forbidden` | 리소스에 대한 액세스 권한이 없습니다. |
| `404` | `Not Found` | 지정한 경로에 대한 리소스를 찾을 수 없습니다. |
| `409` | `Conflict` | 리소스 상태와 충돌하여 요청을 완료할 수 없습니다. |
| `500` | `Server Error` | 서버에서 예기치 않은 오류가 발생하여 요청을 수행하지 못했습니다. |

>[!MORELIKETHIS]
>
>* [JWT(서비스 계정) 인증](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [OAuth 인증](../../api/rest-api-main/aam-api-getting-started.md#oauth)
* [OAuth 2.0](https://oauth.net/2/)
* [OAuth 2 간소화](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

