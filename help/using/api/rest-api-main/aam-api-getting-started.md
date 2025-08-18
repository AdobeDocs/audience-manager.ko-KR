---
description: 일반 요구 사항, 인증, 선택적 쿼리 매개변수, 요청 URL 및 기타 참조에 대한 정보를 제공합니다.
seo-description: Information about general requirements, authentication, optional query parameters, request URLs, and other references.
seo-title: Getting Started with REST APIs
solution: Audience Manager
title: REST API 시작
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
exl-id: f7d5e52d-ad21-4020-a299-d440f954c51a
source-git-commit: 622664170f2a76039bcf2333bde43ce9e60b6af2
workflow-type: tm+mt
source-wordcount: '2563'
ht-degree: 1%

---

# [!DNL REST] [!DNL APIs] 시작 {#getting-started-with-rest-apis}

일반 요구 사항, 인증, 선택적 쿼리 매개 변수, 요청 [!DNL URLs] 및 기타 참조에 대한 정보입니다.

## API 요구 사항 및 권장 사항 {#api-requirements-recommendations}

[Audience Manager API](https://bank.demdex.com/portal/swagger/index.html#/) 코드를 사용하여 작업할 때 다음 사항에 유의하십시오.

* **요청 매개 변수:** 달리 지정하지 않는 한 모든 요청 매개 변수가 필요합니다.
* **요청 헤더**: [Adobe Developer](https://www.adobe.io/) 토큰을 사용할 때는 `x-api-key` 헤더를 제공해야 합니다. [!DNL API]서비스 계정 통합[ 페이지의 지침에 따라 ](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) 키를 가져올 수 있습니다.
* **[!DNL JSON]콘텐츠 형식:** 코드에서 `content-type: application/json` *및* `accept: application/json`을(를) 지정합니다.
* **요청 및 응답:** 요청을 올바른 형식의 [!DNL JSON] 개체로 보냅니다. [!DNL Audience Manager]이(가) 형식이 지정된 [!DNL JSON] 데이터로 응답합니다. 서버 응답에는 요청된 데이터, 상태 코드 또는 두 가지 모두 포함될 수 있습니다.
* **액세스:** [!DNL Audience Manager] 컨설턴트가 [!DNL API]개의 요청을 할 수 있는 클라이언트 ID와 키를 제공합니다.
* **설명서 및 코드 샘플:** *기울임꼴*&#x200B;의 텍스트는 [!DNL API] 데이터를 만들거나 받을 때 제공하거나 전달하는 변수를 나타냅니다. *italicized* 텍스트를 코드, 매개 변수 또는 기타 필수 정보로 바꾸십시오.

## 인증 {#authentication}

[!DNL Audience Manager] [!DNL REST APIs]은(는) 세 가지 인증 방법을 지원합니다.

* [!BADGE 권장]{type=positive} [Adobe 개발자 콘솔](#oauth-adobe-developer)을 사용하여 [OAuth 서버 간 인증](https://www.adobe.io/). [!DNL Adobe Developer]은(는) Adobe의 개발자 생태계 및 커뮤니티입니다. 여기에는 모든 Adobe 제품에 대한 [API](https://developer.adobe.com/apis/)가 포함됩니다. [!DNL Adobe] [!DNL APIs]을(를) 설정하고 사용하는 데 권장되는 방법입니다. Adobe 개발자 설명서에서 [OAuth 서버 간 인증](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)에 대해 자세히 알아보십시오.
* [!BADGE Adobe 개발자 콘솔]{type=negative}을 사용하여 [더 이상 사용되지 않음](#jwt) [JWT(서비스 계정) 인증](https://www.adobe.io/). [!DNL Adobe Developer]은(는) Adobe의 개발자 생태계 및 커뮤니티입니다. 여기에는 모든 Adobe 제품에 대한 [API](https://developer.adobe.com/apis/)가 포함됩니다.
* [!BADGE 사용하지 않음]{type=negative} [레거시 OAuth 인증](#oauth-deprecated). 이 메서드는 더 이상 사용되지 않지만 기존 [!DNL OAuth] 통합을 사용하는 고객은 이 메서드를 계속 사용할 수 있습니다.

>[!IMPORTANT]
>
>인증 방법에 따라 요청 [!DNL URLs]을(를) 적절하게 조정해야 합니다. 사용해야 하는 호스트 이름에 대한 자세한 내용은 [환경](#environments) 섹션을 참조하십시오.

## Adobe Developer을 사용한 OAuth 서버 간 인증 {#oauth-adobe-developer}

이 섹션에서는 아래 순서도에 설명된 대로 Audience Manager API 호출을 인증하는 데 필요한 자격 증명을 수집하는 방법을 다룹니다. 초기 1회 설정에서 필요한 자격 증명 대부분을 수집할 수 있습니다. 그러나 액세스 토큰은 24시간마다 새로 고쳐야 합니다.

![Audience Manager 인증 흐름 다이어그램입니다.](/help/using/api/rest-api-main/assets/aam-authentication-flow.png)

### Adobe Developer 개요 {#developer-overview}

[!DNL Adobe Developer]은(는) Adobe의 개발자 생태계 및 커뮤니티입니다. 여기에는 모든 Adobe 제품에 대한 [API](https://developer.adobe.com/apis)가 포함됩니다.

[!DNL Adobe] [!DNL APIs]을(를) 설정하고 사용하는 데 권장되는 방법입니다.

### 사전 요구 사항 {#prerequisites-server-to-server}

[!DNL OAuth Server-to-Server] 인증을 구성하려면 먼저 [Adobe Developer](https://developer.adobe.com/console/home)에서 [Adobe Developer Console](https://developer.adobe.com/)에 액세스할 수 있는지 확인하십시오. 액세스 요청에 대해서는 조직 관리자에게 문의하십시오.

### 인증 {#oauth}

[!DNL OAuth Server-to-Server]을(를) 사용하여 [!DNL Adobe Developer] 인증을 구성하려면 아래 단계를 따르십시오.

1. [Adobe Developer Console](https://developer.adobe.com/console/home)에 로그인합니다.
1. [OAuth 서버 간 자격 증명 구현 안내서](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)의 단계를 따릅니다.
   * [2단계: 서비스 계정 인증을 사용하여 프로젝트에 API를 추가](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)하는 동안 [!DNL Audience Manager] [!DNL API] 옵션을 선택하십시오.
1. [!DNL API]3단계[의 지침에 따라 첫 번째 ](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) 통화를 수행하여 연결을 시도하십시오.

>[!NOTE]
>
>자동화된 방식으로 [!DNL Audience Manager] [!DNL REST APIs]을(를) 구성하고 작업하려면 클라이언트 암호를 프로그래밍 방식으로 회전해야 합니다. 자세한 지침은 [개발자 설명서](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#rotating-client-secrets-programmatically)를 참조하세요.

### 프로젝트에 Audience Manager API 추가 {#add-aam-api-to-project}

[Adobe Developer Console](https://www.adobe.com/go/devs_console_ui)&#x200B;(으)로 이동하여 Adobe ID으로 로그인합니다. 그런 다음 Adobe Developer Console 설명서에서 [빈 프로젝트 만들기](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty/)에 대한 자습서에 설명된 단계를 수행합니다.

새 프로젝트를 만든 후에는 **[!UICONTROL Add API]** 화면에서 **[!UICONTROL Project Overview]**&#x200B;을(를) 선택하십시오.

>[!TIP]
>
>여러 조직에 대해 프로비저닝된 경우 인터페이스의 오른쪽 상단에 있는 조직 선택기를 사용하여 필요한 조직에 있는지 확인합니다.

API 추가 옵션이 강조 표시된 ![Developer Console 화면.](/help/using/api/rest-api-main/assets/add-api.png)

**[!UICONTROL Add an API]** 화면이 나타납니다. Adobe Experience Cloud의 제품 아이콘을 선택한 다음 **[!UICONTROL Audience Manager API]**&#x200B;을(를) 선택하기 전에 **[!UICONTROL Next]**&#x200B;을(를) 선택하십시오.

![Audience Manager API를 선택하십시오.](/help/using/api/rest-api-main/assets/audience-manager-api.png)

>[!TIP]
>
>**[!UICONTROL View docs]** 옵션을 선택하여 별도의 브라우저 창에서 전체 [Audience Manager API 참조 설명서](https://bank.demdex.com/portal/swagger/index.html#)&#x200B;(으)로 이동합니다.

### OAuth 서버 간 인증 유형 선택 {#select-oauth-server-to-server}

그런 다음 인증 유형을 선택하여 액세스 토큰을 생성하고 Audience Manager API에 액세스합니다.

>[!IMPORTANT]
>
>**[!UICONTROL OAuth Server-to-Server]** 메서드를 선택하십시오. 이 메서드는 앞으로 지원되는 유일한 메서드입니다. **[!UICONTROL Service Account (JWT)]** 메서드가 더 이상 사용되지 않습니다. JWT 인증 방법을 사용하는 통합은 2025년 1월 1일까지 계속 작동하지만, Adobe에서는 해당 날짜 이전에 기존 통합을 새로운 OAuth 서버 간 방법으로 마이그레이션할 것을 강력히 권장합니다.

![OAuth 인증 방법을 선택하십시오.](/help/using/api/rest-api-main/assets/select-oauth-authentication-method.png)

### 통합할 제품 프로필 선택 {#select-product-profiles}

**[!UICONTROL Configure API]** 화면에서 원하는 제품 프로필을 선택합니다. 통합의 서비스 계정은 여기에서 선택한 제품 프로필을 통해 세분화된 기능에 액세스할 수 있습니다.

![통합할 제품 프로필을 선택하십시오.](/help/using/api/rest-api-main/assets/select-product-profiles.png)

준비가 되면 **[!UICONTROL Save configured API]**&#x200B;을(를) 선택하십시오.

### 자격 증명 수집 {#gather-credentials}

API가 프로젝트에 추가되면 프로젝트에 대한 **[!UICONTROL Audience Manager API]** 페이지에 Audience Manager API 호출에 필요한 다음 자격 증명이 표시됩니다.

![Developer Console에서 API를 추가한 후의 통합 정보.](/help/using/api/rest-api-main/assets/api-integration-information.png)

* `{API_KEY}`([!UICONTROL Client ID])
* `{ORG_ID}`([!UICONTROL Organization ID])

## 액세스 토큰 생성 {#generate-access-token}

다음 단계는 Audience Manager API 호출에 사용할 `{ACCESS_TOKEN}` 자격 증명을 생성하는 것입니다. `{API_KEY}` 및 `{ORG_ID}`의 값과 달리 Audience Manager API를 계속 사용하려면 24시간마다 새 토큰을 생성해야 합니다. 아래와 같이 **[!UICONTROL Generate access token]**&#x200B;을(를) 선택합니다.

![액세스 토큰을 생성하는 방법 표시](/help/using/api/rest-api-main/assets/generate-acces-token.gif)

## API 호출 테스트 {#test-api-call}

인증 전달자 토큰을 받은 후 API 호출을 수행하여 Audience Manager API에 액세스할 수 있음을 테스트합니다.

1. [API 참조 설명서](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_)&#x200B;(으)로 이동합니다.
2. **[!UICONTROL Authorize]**&#x200B;을(를) 선택하고 [액세스 토큰 생성](#generate-access-token) 단계에서 얻은 액세스 토큰을 붙여넣습니다.

   ![API 호출 승인](/help/using/api/rest-api-main/assets/authorize-api-calls.gif)

3. `/datasources`API 참조 설명서[에 표시된 대로 전역적으로 사용 가능한 모든 데이터 소스 목록을 검색하려면 ](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_) API 끝점에 대한 GET 호출을 수행하십시오. 아래와 같이 **[!UICONTROL Try it out]**, **[!UICONTROL Execute]**&#x200B;을(를) 차례로 선택합니다.

   ![API 호출 수행](/help/using/api/rest-api-main/assets/perform-api-calls.gif)


>[!BEGINSHADEBOX]

>[!BEGINTABS]

>[!TAB API 요청]

```shell
curl -X 'GET' \
  'https://api.demdex.com/v1/datasources/' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer your-access-token'
```


>[!TAB 올바른 전달자 토큰을 사용하는 경우의 API 응답]


작업 액세스 토큰을 사용할 때 API 끝점은 조직에서 액세스할 수 있는 모든 글로벌 데이터 소스를 포함하는 응답 본문과 함께 200개의 응답을 반환합니다.

```json
[
  {
    "pid": 1794,
    "name": "testdatasource1",
    "description": "Test data source",
    "status": "ACTIVE",
    "integrationCode": "test_ds1",
    "dataExportRestrictions": [],
    "updateTime": 1595340792000,
    "crUID": 0,
    "upUID": 15910,
    "linkNamespace": false,
    "type": "GENERAL",
    "subIdType": "CROSS_DEVICE_PERSON",
    "inboundS2S": true,
    "outboundS2S": true,
    "useAudienceManagerVisitorID": false,
    "allowDataSharing": true,
    "masterDataSourceIdProvider": true,
    "uniqueTraitIntegrationCodes": false,
    "uniqueSegmentIntegrationCodes": false,
    "marketingCloudVisitorIdVersion": 0,
    "idType": "CROSS_DEVICE",
    "samplingEndTime": 1596550392825,
    "allowDeviceGraphSharing": false,
    "supportsAuthenticatedProfile": true,
    "deviceGraph": false,
    "authenticatedProfileName": "testdatasource1",
    "deviceGraphName": "",
    "customNamespaceId": 29769,
    "customNamespaceCode": "silviu_ds1",
    "customerProfileDataRetention": 62208000,
    "samplingStartTime": 1595340792825,
    "dataSourceId": 29769,
    "containerIds": [],
    "samplingEnabled": false
  },
  {
    "pid": 1794,
    "name": "AAM Test Company Audiences",
    "description": "Automatically generated trait data source",
    "status": "ACTIVE",
    "integrationCode": "adobe-provided",
    "dataExportRestrictions": [
      "PII"
    ],

    [...]
```

>[!ENDTABS]

>[!ENDSHADEBOX]

## Adobe Developer을 사용한 [!BADGE 사용되지 않음]{type=negative} [!DNL JWT]&#x200B;([!DNL Service Account]) 인증 {#jwt}

+++ 인증 토큰을 얻는 더 이상 사용되지 않는 [!DNL JWT]&#x200B;([!DNL Service Account]) 메서드에 대한 정보를 봅니다.

### Adobe Developer 개요 {#adobeio}

[!DNL Adobe Developer]은(는) Adobe의 개발자 생태계 및 커뮤니티입니다. 여기에는 모든 Adobe 제품에 대한 [API](https://www.adobe.io/apis.html)가 포함됩니다.

[!DNL Adobe] [!DNL APIs]을(를) 설정하고 사용하는 데 권장되는 방법입니다.

### 사전 요구 사항 {#prerequisites}

[!DNL JWT] 인증을 구성하려면 먼저 [Adobe Developer](https://console.adobe.io/)에서 [Adobe Developer Console](https://www.adobe.io/)에 액세스할 수 있는지 확인하십시오. 액세스 요청에 대해서는 조직 관리자에게 문의하십시오.

### 인증 {#auth}

[!DNL JWT (Service Account)]을(를) 사용하여 [!DNL Adobe Developer] 인증을 구성하려면 아래 단계를 따르십시오.

1. [Adobe Developer Console](https://console.adobe.io/)에 로그인합니다.
1. [서비스 계정 연결](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)의 단계를 따릅니다.
   * [2단계: 서비스 계정 인증을 사용하여 프로젝트에 API를 추가](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)하는 동안 [!DNL Audience Manager] [!DNL API] 옵션을 선택하십시오.
1. [!DNL API]3단계[의 지침에 따라 첫 번째 ](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) 통화를 수행하여 연결을 시도하십시오.

>[!NOTE]
>
>[!DNL Audience Manager] [!DNL REST APIs]을(를) 자동 방식으로 구성하고 작업하려면 [!DNL JWT]을(를) 프로그래밍 방식으로 생성할 수 있습니다. 자세한 지침은 [JWT(서비스 계정) 인증](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)을 참조하십시오.

### 기술 계정 RBAC 권한

Audience Manager 계정이 [역할 기반 액세스 제어](../../features/administration/administration-overview.md)를 사용하는 경우 Audience Manager 기술 사용자 계정을 만들고 API를 호출할 Audience Manager RBAC 그룹에 추가해야 합니다.

아래 단계에 따라 기술 사용자 계정을 만들고 RBAC 그룹에 추가합니다.

1. `GET`에 `https://aam.adobe.io/v1/users/self` 통화를 합니다. 이 호출은 [!UICONTROL Admin Console] 페이지의 [!UICONTROL Users]에서 볼 수 있는 기술 사용자 계정을 만듭니다.

   ![기술 계정](assets/technical-account.png)

1. Audience Manager 계정에 로그인하고 [기술 사용자 계정을 API를 호출할 사용자 그룹에 추가](../../features/administration/administration-overview.md#create-group)합니다.

+++

## [!BADGE 사용되지 않음]{type=negative} [!DNL OAuth] 인증(사용되지 않음) {#oauth-deprecated}

+++ 인증 토큰을 얻기 위해 더 이상 사용되지 않는 레거시 [!DNL OAuth] 인증 방법에 대한 정보를 봅니다.

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] 토큰 인증 및 [!DNL OAuth 2.0]을(를) 통한 갱신은 이제 더 이상 사용되지 않습니다.
>
> 대신 [JWT(서비스 계정) 인증](#jwt-service-account-authentication-jwt)을 사용하십시오.

[!DNL Audience Manager] [!UICONTROL REST API]은(는) 토큰 인증 및 갱신에 대한 [!DNL OAuth 2.0] 표준을 따릅니다. 아래 섹션에서는 [!DNL API]을(를) 인증하고 작업을 시작하는 방법에 대해 설명합니다.

### 일반 [!DNL API] 사용자 만들기 {#requirements}

[!DNL Audience Manager] [!DNL API]&#x200B;(으)로 작업하려면 별도의 기술 사용자 계정을 만드는 것이 좋습니다. 조직의 특정 사용자와 연결되거나 연결되지 않은 일반 계정입니다. 이 유형의 [!DNL API] 사용자 계정은 다음 두 가지 작업을 수행하는 데 도움이 됩니다.

* [!DNL API]을(를) 호출하는 서비스(예: [!DNL API]을(를) 사용하는 앱이나 [!DNL API]개의 요청을 하는 다른 도구의 호출)를 식별합니다.
* [!DNL API]에 중단 없이 액세스하십시오. 특정 사용자에 연결된 계정은 회사에서 나갈 때 삭제될 수 있습니다. 이 경우 사용 가능한 [!DNL API] 코드를 사용할 수 없습니다. 특정 직원에게 연결되지 않은 일반 계정은 이 문제를 방지하는 데 도움이 됩니다.

이 유형의 계정에 대한 사용 사례로 [대량 관리 도구](../../reference/bulk-management-tools/bulk-management-intro.md)를 사용하여 한 번에 많은 세그먼트를 변경한다고 가정해 보겠습니다. 이렇게 하려면 사용자 계정에 [!DNL API] 액세스 권한이 필요합니다. 특정 사용자에게 권한을 추가하는 대신 [!DNL API]을(를) 호출할 수 있는 적절한 자격 증명, 키 및 암호가 있는 비특정 [!DNL API] 사용자 계정을 만듭니다. [!DNL Audience Manager] [!DNL API]을(를) 사용하는 자체 응용 프로그램을 개발하는 경우에도 유용합니다.

[!DNL Audience Manager] 컨설턴트와 함께 일반 [!DNL API] 전용 사용자 계정을 설정합니다.

### 암호 인증 워크플로 {#password-authentication-workflow}

암호 인증은 [!DNL REST API]에 안전하게 액세스합니다. 아래 단계에서는 브라우저의 [!DNL JSON] 클라이언트에서 암호 인증을 위한 워크플로에 대해 간략히 설명합니다.

>[!TIP]
>
>액세스 및 새로 고침 토큰을 데이터베이스에 저장하는 경우 이를 암호화합니다.

#### 1단계: [!DNL API] 액세스 요청

파트너 솔루션 관리자에게 문의하십시오. [!DNL API] 클라이언트 ID와 암호를 제공합니다. ID 및 암호가 [!DNL API]에 대해 사용자를 인증합니다.

참고: 새로 고침 토큰을 받으려면 [!DNL API] 액세스를 요청할 때 지정합니다.

#### 2단계: 토큰 요청

선호하는 [!DNL JSON] 클라이언트로 토큰 요청을 전달합니다. 요청을 빌드할 때:

* `POST` 메서드를 사용하여 `https://api.demdex.com/oauth/token`을(를) 호출하십시오.
* 클라이언트 ID 및 암호를 base-64로 인코딩된 문자열로 변환합니다. 전환 프로세스 중에 콜론으로 ID와 암호를 구분합니다. 예를 들어 자격 증명 `testId : testSecret`이(가) `dGVzdElkOnRlc3RTZWNyZXQ=`(으)로 변환됩니다.
* [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` 및 `Content-Type: application/x-www-form-urlencoded` 을(를) 전달합니다. 예를 들어 머리글은 다음과 같이 표시될 수 있습니다. <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* 요청 본문을 다음과 같이 설정합니다.
  <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### 3단계: 토큰 받기

[!DNL JSON] 응답에 액세스 토큰이 포함되어 있습니다. 응답은 다음과 같아야 합니다.

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

`expires_in` 키는 액세스 토큰이 만료될 때까지의 시간(초)을 나타냅니다. 토큰이 노출된 경우 짧은 만료 시간을 사용하여 노출을 제한하는 것이 좋습니다.

### 토큰 새로 고침 {#refresh-token}

토큰 새로 고침은 원본 토큰이 만료된 후 [!DNL API] 액세스를 갱신합니다. 요청한 경우 암호 워크플로의 응답 [!DNL JSON]에 새로 고침 토큰이 포함됩니다. 새로 고침 토큰을 받지 못한 경우 암호 인증 프로세스를 통해 새 토큰을 만듭니다.

기존 액세스 토큰이 만료되기 전에 새로 고침 토큰을 사용하여 새 토큰을 생성할 수도 있습니다.

액세스 토큰이 만료된 경우 `401 Status Code`과(와) 다음 헤더가 응답됩니다.

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

다음 단계에서는 새로 고침 토큰을 사용하여 브라우저의 [!DNL JSON] 클라이언트에서 새 액세스 토큰을 만들기 위한 워크플로에 대해 간략히 설명합니다.

#### 1단계: 새 토큰 요청

선호하는 [!DNL JSON] 클라이언트로 새로 고침 토큰 요청을 전달합니다. 요청을 빌드할 때:

* `POST` 메서드를 사용하여 `https://api.demdex.com/oauth/token`을(를) 호출하십시오.
* 클라이언트 ID 및 암호를 base-64로 인코딩된 문자열로 변환합니다. 전환 프로세스 중에 콜론으로 ID와 암호를 구분합니다. 예를 들어 자격 증명 `testId : testSecret`이(가) `dGVzdElkOnRlc3RTZWNyZXQ=`(으)로 변환됩니다.
* HTTP 헤더 `Authorization:Basic <base-64 clientID:clientSecret>` 및 `Content-Type: application/x-www-form-urlencoded`을(를) 전달합니다. 예를 들어 머리글은 다음과 같이 표시될 수 있습니다. <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* 요청 본문에 `grant_type:refresh_token`을(를) 지정하고 이전 액세스 요청에서 받은 새로 고침 토큰을 전달합니다. 요청은 다음과 같아야 합니다. <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### 2단계: 새 토큰 받기

[!DNL JSON] 응답에 새 액세스 토큰이 포함되어 있습니다. 응답은 다음과 같아야 합니다.

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

[!DNL Audience Manager] [!UICONTROL REST API]은(는) 인증 코드와 암시적 인증을 지원합니다. 이러한 액세스 방법을 사용하려면 사용자가 `https://api.demdex.com/oauth/authorize`에 로그인하여 액세스 권한을 얻고 토큰을 새로 고쳐야 합니다.

+++

## 인증된 [!DNL API]개 요청 만들기 {#authenticated-api-requests}

인증 토큰을 받은 후 [!DNL API] 메서드를 호출하기 위한 요구 사항입니다.

사용 가능한 [!DNL API] 메서드에 대해 호출하려면 다음을 수행합니다.

* `HTTP` 헤더에서 `Authorization: Bearer <token>`을(를) 설정합니다.
* [JWT(서비스 계정) 인증](#jwt)을(를) 사용하는 경우 `x-api-key`과(와) 동일한 `client_id` 헤더를 제공해야 합니다. `client_id`Adobe Developer 통합[ 페이지에서 ](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)을(를) 가져올 수 있습니다.
* 필요한 [!DNL API] 메서드를 호출합니다.

## 선택적 [!DNL API] 쿼리 매개 변수 {#optional-api-query-parameters}

개체의 모든 속성을 반환하는 메서드에서 사용할 수 있는 선택적 매개 변수를 설정합니다.

개체에 대한 [!DNL API]all *속성을 반환하는* 메서드와 함께 이러한 선택적 매개 변수를 사용할 수 있습니다. 해당 쿼리를 [!DNL API]에 전달할 때 요청 문자열에서 이러한 옵션을 설정하십시오.

| 매개 변수 | 설명 |
|--- |--- |
| `page` | 페이지 번호별로 결과를 반환합니다. 번호 매기기는 0부터 시작합니다. |
| `pageSize` | 요청에서 반환되는 응답 결과 수를 설정합니다(기본값: 10). |
| `sortBy` | 지정된 [!DNL JSON] 속성에 따라 결과를 정렬하고 반환합니다. |
| `descending` | 결과를 내림차순으로 정렬하고 반환합니다. `ascending`이(가) 기본값입니다. |
| `search` | 검색 매개 변수로 사용할 지정된 문자열을 기반으로 결과를 반환합니다. 예를 들어 해당 항목의 값 필드 중 하나에서 &quot;Test&quot;라는 단어가 있는 모든 모델의 결과를 찾는다고 가정합니다. 샘플 요청은 다음과 같이 표시될 수 있습니다.   `GET https://aam.adobe.io/v1/models/?search=Test`.  &quot;[!DNL get all]&quot; 메서드에서 반환된 값을 검색할 수 있습니다. |
| `folderId` | 지정된 폴더 내에서 [!UICONTROL traits]의 모든 ID를 반환합니다. 일부 메서드에서는 사용할 수 없습니다. |
| `permissions` | 지정된 권한에 따라 세그먼트 목록을 반환합니다. `READ`이(가) 기본값입니다. 사용 권한에는 다음이 포함됩니다.<ul><li>`READ` : 세그먼트에 대한 정보를 반환하고 봅니다.</li><li>`WRITE` : `PUT`을(를) 사용하여 세그먼트를 업데이트합니다.</li><li>`CREATE` : `POST`을(를) 사용하여 세그먼트를 만드십시오.</li><li>`DELETE` : 세그먼트를 삭제합니다. 필요한 경우 기본 트레이트에 대한 액세스 권한이 필요합니다. 예를 들어, 세그먼트를 제거하려면 세그먼트에 속하는 트레이트를 삭제할 수 있는 권한이 필요합니다.</li></ul><br>별도의 키-값 쌍을 사용하여 여러 권한을 지정합니다. 예를 들어 `READ` 및 `WRITE` 권한만 있는 세그먼트 목록을 반환하려면 `"permissions":"READ"`, `"permissions":"WRITE"` 을 전달합니다. |
| `includePermissions` | ([!DNL Boolean]) 세그먼트에 대한 사용 권한을 반환하려면 `true`(으)로 설정합니다. 기본값은 `false`입니다. |

{style="table-layout:auto"}

### 페이지 옵션에 대한 참고 사항

페이지 정보 *이(가) 지정되지 않은*&#x200B;경우 요청은 일반 [!DNL JSON] 결과를 반환하여 배열을 생성합니다. 페이지 정보 *is*&#x200B;을(를) 지정하면 반환된 목록이 전체 결과 및 현재 페이지에 대한 정보가 포함된 [!DNL JSON] 개체로 래핑됩니다. 페이지 옵션을 사용하는 샘플 요청은 다음과 유사할 수 있습니다.

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

요청, 스테이징 및 프로덕션 환경 및 버전에 대해 [!DNL URLs]합니다.

## [!DNL URLs] 요청 {#request-urls}

다음 표에는 메서드별로 [!DNL URLs] 요청을 전달하는 데 사용되는 [!DNL API] 요청이 나열되어 있습니다.

사용하는 인증 방법에 따라 아래 표에 따라 요청 [!DNL URLs]을(를) 조정해야 합니다.

### Adobe Developer을 통해 [!DNL URLs]권장[!BADGE &#x200B; OAuth 서버 간 및 &#x200B;]{type=positive}사용되지 않음[!BADGE &#x200B; &#x200B;]{type=negative} 인증에 대한 [!DNL JWT] 요청 {#request-urls-jwt}

| [!DNL API] 메서드 | [!DNL URL] 요청 |
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

{style="table-layout:auto"}

### [!DNL URLs]사용되지 않음[!BADGE &#x200B; 레거시 &#x200B;]{type=negative} 인증에 대한 [!DNL OAuth] 요청 {#request-urls-oauth}

| [!DNL API] 메서드 | [!DNL URL] 요청 |
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

{style="table-layout:auto"}

## 환경 {#environments}

[!DNL Audience Manager] [!DNL API]에서 다른 작업 환경에 액세스할 수 있습니다. 이러한 환경은 라이브 프로덕션 데이터에 영향을 주지 않고 별도의 데이터베이스에 대해 코드를 테스트하는 데 도움이 됩니다. 다음 표에는 사용 가능한 [!DNL API] 환경 및 해당 리소스 호스트 이름이 나열되어 있습니다.

사용하는 인증 방법에 따라 아래 표에 따라 환경 [!DNL URLs]을(를) 조정해야 합니다.

| 환경 | [!DNL JWT] 인증을 위한 호스트 이름 | [!DNL OAuth] 인증을 위한 호스트 이름 |
|---|---|---|
| **프로덕션** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>[!DNL Audience Manager] Beta 환경은 프로덕션 환경의 소규모 독립 실행형 버전입니다. 테스트할 모든 데이터는 이 환경에서 입력 및 수집해야 합니다.

## 버전 {#versions}

이 [!DNL API]의 새 버전은 정기적으로 릴리스됩니다. 새 릴리스로 인해 [!DNL API] 버전 번호가 증가합니다. 버전 번호가 [!DNL URL] 요청에서 `v<version number>`(으)로 참조되었습니다. 다음 예제와 같습니다.

`https://<host>/v1/...`

## 정의된 응답 코드 {#response-codes-defined}

`HTTP` [!DNL Audience Manager]에서 반환된 [!UICONTROL REST API] 상태 코드 및 응답 텍스트입니다.

| 응답 코드 ID | 응답 텍스트 | 정의 |
|---|---|---|
| `200` | `OK` | 요청이 정상적으로 처리되었습니다. 필요한 경우 예상 컨텐츠 또는 데이터를 반환합니다. |
| `201` | `Created` | 리소스가 생성되었습니다. `PUT` 및 `POST` 요청에 대해 를 반환합니다. |
| `204` | `No Content` | 리소스가 삭제되었습니다. 응답 본문은 비어 있습니다. |
| `400` | `Bad Request` | 서버가 요청을 이해하지 못했습니다. 일반적으로 잘못된 구문 때문입니다. 요청을 확인하고 다시 시도하십시오. |
| `403` | `Forbidden` | 리소스에 대한 액세스 권한이 없습니다. |
| `404` | `Not Found` | 지정한 경로에 대한 리소스를 찾을 수 없습니다. |
| `409` | `Conflict` | 리소스 상태와 충돌하여 요청을 완료할 수 없습니다. |
| `500` | `Server Error` | 서버에서 예기치 않은 오류가 발생하여 요청을 수행할 수 없습니다. |

>[!MORELIKETHIS]
>
>* [JWT(서비스 계정) 인증](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [OAuth 인증](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2 단순화](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)
