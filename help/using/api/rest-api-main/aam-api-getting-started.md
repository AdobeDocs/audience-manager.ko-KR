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
source-wordcount: '2558'
ht-degree: 1%

---

# 시작하기 [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

일반 요구 사항, 인증, 선택적 쿼리 매개 변수, 요청에 대한 정보 [!DNL URLs]및 기타 참조.

## API 요구 사항 및 Recommendations {#api-requirements-recommendations}

을 사용하여 작업할 때 다음 사항을 참고하십시오 [AUDIENCE MANAGER API](https://bank.demdex.com/portal/swagger/index.html#/) 코드:

* **요청 매개 변수:** 별도로 지정하지 않는 한 모든 요청 매개 변수가 필요합니다.
* **요청 헤더**: 사용 시 [Adobe Developer](https://www.adobe.io/) 토큰을 입력하십시오. `x-api-key` 머리글입니다. 다음을 가져올 수 있습니다. [!DNL API] 의 지침에 따라 키를 누릅니다. [서비스 계정 통합](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) 페이지를 가리키도록 업데이트하는 중입니다.
* **[!DNL JSON]컨텐츠 유형:** 지정 `content-type: application/json`  *및*  `accept: application/json` 코드를 입력합니다.
* **요청 및 응답:** 적절한 형식의 요청을 보냅니다. [!DNL JSON] 개체. [!DNL Audience Manager] 다음으로 응답: [!DNL JSON] 형식이 지정된 데이터입니다. 서버 응답에는 요청된 데이터, 상태 코드 또는 두 가지 모두 포함될 수 있습니다.
* **액세스:** 사용자 [!DNL Audience Manager] 컨설턴트는 다음을 수행할 수 있는 클라이언트 ID와 키를 제공합니다. [!DNL API] 요청.
* **설명서 및 코드 샘플:** 텍스트 입력 *기울임체* 만들거나 받을 때 제공하거나 전달하는 변수를 나타냅니다 [!DNL API] 데이터. 바꾸기 *기울임꼴* 고유한 코드, 매개 변수 또는 기타 필수 정보가 있는 텍스트입니다.

## 인증 {#authentication}

다음 [!DNL Audience Manager] [!DNL REST APIs] 세 가지 인증 방법을 지원합니다.

* [!BADGE 추천]{type=positive}[OAuth 서버 간 인증](#oauth-adobe-developer) 사용 [Adobe 개발자 콘솔](https://www.adobe.io/). [!DNL Adobe Developer] 는 Adobe의 개발자 생태계 및 커뮤니티입니다. 여기에는 다음이 포함됩니다 [모든 Adobe 제품에 대한 API](https://developer.adobe.com/apis/). 다음은 설정 및 사용에 권장되는 방법입니다 [!DNL Adobe] [!DNL APIs]. 자세한 내용 [OAuth 서버 간 인증](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/) Adobe 개발자 설명서에서 참조하십시오.
* [!BADGE 더 이상 사용되지 않음]{type=negative}[JWT(서비스 계정) 인증](#jwt) 사용 [Adobe 개발자 콘솔](https://www.adobe.io/). [!DNL Adobe Developer] 는 Adobe의 개발자 생태계 및 커뮤니티입니다. 여기에는 다음이 포함됩니다 [모든 Adobe 제품에 대한 API](https://developer.adobe.com/apis/).
* [!BADGE 더 이상 사용되지 않음]{type=negative}[이전 OAuth 인증](#oauth-deprecated). 이 메서드는 더 이상 사용되지 않지만 가 있는 고객은 [!DNL OAuth] 통합은 이 메서드를 사용하여 계속할 수 있습니다.

>[!IMPORTANT]
>
>인증 방법에 따라 요청을 조정해야 합니다 [!DNL URLs] 따라서. 다음을 참조하십시오. [환경](#environments) 섹션 을 참조하십시오.

## Adobe Developer을 사용한 OAuth 서버 간 인증 {#oauth-adobe-developer}

이 섹션에서는 아래 순서도에 설명된 대로 Audience Manager API 호출을 인증하는 데 필요한 자격 증명을 수집하는 방법을 다룹니다. 초기 1회 설정에서 필요한 자격 증명 대부분을 수집할 수 있습니다. 그러나 액세스 토큰은 24시간마다 새로 고쳐야 합니다.

![Audience Manager 인증 흐름 다이어그램입니다.](/help/using/api/rest-api-main/assets/aam-authentication-flow.png)

### Adobe Developer 개요 {#developer-overview}

[!DNL Adobe Developer] 는 Adobe의 개발자 생태계 및 커뮤니티입니다. 여기에는 다음이 포함됩니다 [모든 Adobe 제품에 대한 API](https://developer.adobe.com/apis).

다음은 설정 및 사용에 권장되는 방법입니다 [!DNL Adobe] [!DNL APIs].

### 전제 조건 {#prerequisites-server-to-server}

을(를) 구성하기 전에 [!DNL OAuth Server-to-Server] 인증, 다음에 대한 액세스 권한이 있는지 확인하십시오. [Adobe Developer 콘솔](https://developer.adobe.com/console/home) 위치: [Adobe Developer](https://developer.adobe.com/). 액세스 요청에 대해서는 조직 관리자에게 문의하십시오.

### 인증 {#oauth}

아래 단계에 따라 구성하십시오. [!DNL OAuth Server-to-Server] 을 사용한 인증 [!DNL Adobe Developer]:

1. 에 로그인합니다 [Adobe Developer 콘솔](https://developer.adobe.com/console/home).
1. 의 단계를 따릅니다. [OAuth 서버 간 자격 증명 구현 안내서](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/).
   * 다음 기간 동안 [2단계: 서비스 계정 인증을 사용하여 프로젝트에 API 추가](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), 을(를) 선택합니다. [!DNL Audience Manager] [!DNL API] 옵션을 선택합니다.
1. 첫 번째 를 만들어 연결 시도 [!DNL API] 의 지침에 따라 를 호출합니다. [3단계](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>을(를) 구성하고 사용하여 작업하려면 [!DNL Audience Manager] [!DNL REST APIs] 자동화된 방식으로 클라이언트 암호를 프로그래밍 방식으로 회전할 수 있습니다. 다음을 참조하십시오 [개발자 설명서](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#rotating-client-secrets-programmatically) 자세한 지침은 을 참조하십시오.

### 프로젝트에 Audience Manager API 추가 {#add-aam-api-to-project}

다음으로 이동 [Adobe Developer 콘솔](https://www.adobe.com/go/devs_console_ui) Adobe ID으로 로그인합니다. 다음은에 대한 자습서에 설명된 단계를 따릅니다. [빈 프로젝트 만들기](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty/) Adobe Developer 콘솔 설명서에서 확인할 수 있습니다.

새 프로젝트를 만들었으면 다음을 선택합니다. **[!UICONTROL Add API]** 다음에 있음 **[!UICONTROL Project Overview]** 화면.

>[!TIP]
>
>여러 조직에 대해 프로비저닝된 경우 인터페이스의 오른쪽 상단에 있는 조직 선택기를 사용하여 필요한 조직에 있는지 확인합니다.

![API 추가 옵션이 강조 표시된 Developer Console 화면입니다.](/help/using/api/rest-api-main/assets/add-api.png)

다음 **[!UICONTROL Add an API]** 화면이 나타납니다. Adobe Experience Cloud에 대한 제품 아이콘을 선택한 다음 을 선택합니다. **[!UICONTROL Audience Manager API]** 선택하기 전 **[!UICONTROL Next]**.

![Audience Manager API를 선택합니다.](/help/using/api/rest-api-main/assets/audience-manager-api.png)

>[!TIP]
>
>다음 항목 선택 **[!UICONTROL View docs]** 별도의 브라우저 창에서 완료로 이동하는 옵션 [Audience Manager API 참조 설명서](https://bank.demdex.com/portal/swagger/index.html#).

### OAuth 서버 간 인증 유형 선택 {#select-oauth-server-to-server}

그런 다음 인증 유형을 선택하여 액세스 토큰을 생성하고 Audience Manager API에 액세스합니다.

>[!IMPORTANT]
>
>다음 항목 선택 **[!UICONTROL OAuth Server-to-Server]** 이 메서드만이 향후 지원되는 유일한 메서드가 됩니다. 다음 **[!UICONTROL Service Account (JWT)]** 메서드가 더 이상 사용되지 않습니다. JWT 인증 방법을 사용하는 통합은 2025년 1월 1일까지 계속 작동하지만, Adobe은 해당 날짜 이전에 기존 통합을 새 OAuth 서버 간 방법으로 마이그레이션할 것을 강력히 권장합니다.

![OAuth 인증 방법을 선택합니다.](/help/using/api/rest-api-main/assets/select-oauth-authentication-method.png)

### 통합할 제품 프로필 선택 {#select-product-profiles}

다음에서 **[!UICONTROL Configure API]** 화면에서 원하는 제품 프로필을 선택합니다. 통합의 서비스 계정은 여기에서 선택한 제품 프로필을 통해 세분화된 기능에 액세스할 수 있습니다.

![통합할 제품 프로필을 선택합니다.](/help/using/api/rest-api-main/assets/select-product-profiles.png)

선택 **[!UICONTROL Save configured API]** 준비가 되면.

### 자격 증명 수집 {#gather-credentials}

API가 프로젝트에 추가되면 **[!UICONTROL Audience Manager API]** 프로젝트 페이지에는 모든 Audience Manager API 호출에 필요한 다음 자격 증명이 표시됩니다.

![Developer Console에서 API 추가 후 통합 정보.](/help/using/api/rest-api-main/assets/api-integration-information.png)

* `{API_KEY}` ([!UICONTROL Client ID])
* `{ORG_ID}` ([!UICONTROL Organization ID])

## 액세스 토큰 생성 {#generate-access-token}

다음 단계는 를 생성하는 것입니다. `{ACCESS_TOKEN}` Audience Manager API 호출에 사용할 자격 증명입니다. 의 값과 다르게 `{API_KEY}` 및 `{ORG_ID}`: Audience Manager API를 계속 사용하려면 24시간마다 새 토큰을 생성해야 합니다. 선택 **[!UICONTROL Generate access token]**&#x200B;아래에 표시된 대로 를 클릭합니다.

![액세스 토큰을 생성하는 방법 표시](/help/using/api/rest-api-main/assets/generate-acces-token.gif)

## API 호출 테스트 {#test-api-call}

인증 전달자 토큰을 받은 후, API 호출을 수행하여 Audience Manager API에 액세스할 수 있음을 테스트합니다.

1. 다음 위치로 이동 [API 참조 설명서](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_).
2. 선택 **[!UICONTROL Authorize]** 및에서 가져온 액세스 토큰을 붙여 넣습니다. [액세스 토큰 생성](#generate-access-token) 단계.

   ![API 호출 승인](/help/using/api/rest-api-main/assets/authorize-api-calls.gif)

3. 에 대한 GET 호출 수행 `/datasources` 전역적으로 사용 가능한 모든 데이터 소스의 목록을 검색하기 위한 API 엔드포인트,에 표시 [API 참조 설명서](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_). 선택 **[!UICONTROL Try it out]**, 그 다음 **[!UICONTROL Execute]**&#x200B;아래에 표시된 대로 를 클릭합니다.

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

## [!BADGE 더 이상 사용되지 않음]{type=negative}[!DNL JWT] ([!DNL Service Account]) Adobe Developer을 사용한 인증 {#jwt}

+++ 더 이상 사용되지 않는 항목에 대한 정보 보기 [!DNL JWT] ([!DNL Service Account]) 인증 토큰을 얻는 방법입니다.

### Adobe Developer 개요 {#adobeio}

[!DNL Adobe Developer] 는 Adobe의 개발자 생태계 및 커뮤니티입니다. 여기에는 다음이 포함됩니다 [모든 Adobe 제품에 대한 API](https://www.adobe.io/apis.html).

다음은 설정 및 사용에 권장되는 방법입니다 [!DNL Adobe] [!DNL APIs].

### 전제 조건 {#prerequisites}

을(를) 구성하기 전에 [!DNL JWT] 인증, 다음에 대한 액세스 권한이 있는지 확인하십시오. [Adobe Developer 콘솔](https://console.adobe.io/) 위치: [Adobe Developer](https://www.adobe.io/). 액세스 요청에 대해서는 조직 관리자에게 문의하십시오.

### 인증 {#auth}

아래 단계에 따라 구성하십시오. [!DNL JWT (Service Account)] 을 사용한 인증 [!DNL Adobe Developer]:

1. 에 로그인합니다 [Adobe Developer 콘솔](https://console.adobe.io/).
1. 의 단계를 따릅니다. [서비스 계정 연결](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
   * 다음 기간 동안 [2단계: 서비스 계정 인증을 사용하여 프로젝트에 API 추가](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), 을(를) 선택합니다. [!DNL Audience Manager] [!DNL API] 옵션을 선택합니다.
1. 첫 번째 를 만들어 연결 시도 [!DNL API] 의 지침에 따라 를 호출합니다. [3단계](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>을(를) 구성하고 사용하여 작업하려면 [!DNL Audience Manager] [!DNL REST APIs] 자동화된 방식으로 다음을 생성할 수 있습니다 [!DNL JWT] 프로그래밍 방식으로. 다음을 참조하십시오 [JWT(서비스 계정) 인증](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) 자세한 지침은 을 참조하십시오.

### 기술 계정 RBAC 권한

Audience Manager 계정에서 [역할 기반 액세스 제어](../../features/administration/administration-overview.md), Audience Manager 기술 사용자 계정을 만든 다음 API를 호출할 Audience Manager RBAC 그룹에 추가해야 합니다.

아래 단계에 따라 기술 사용자 계정을 만들고 RBAC 그룹에 추가합니다.

1. 만들기 `GET` 호출 대상 `https://aam.adobe.io/v1/users/self`. 호출은에서 볼 수 있는 기술 사용자 계정을 만듭니다. [!UICONTROL Admin Console], [!UICONTROL Users] 페이지를 가리키도록 업데이트하는 중입니다.

   ![기술 계정](assets/technical-account.png)

1. Audience Manager 계정에 로그인하고 [기술 사용자 계정 추가](../../features/administration/administration-overview.md#create-group) API를 호출할 사용자 그룹에 연결합니다.

+++

## [!BADGE 더 이상 사용되지 않음]{type=negative}[!DNL OAuth] 인증(사용하지 않음) {#oauth-deprecated}

+++ 더 이상 사용되지 않는 레거시에 대한 정보 보기 [!DNL OAuth] 인증 토큰을 가져오는 인증 방법.

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] 를 통한 토큰 인증 및 갱신 [!DNL OAuth 2.0] 이제 더 이상 사용되지 않습니다.
>
> 다음을 사용하십시오. [JWT(서비스 계정) 인증](#jwt-service-account-authentication-jwt) 대신,

다음 [!DNL Audience Manager] [!UICONTROL REST API] 팔로우 [!DNL OAuth 2.0] 토큰 인증 및 갱신에 대한 표준. 아래 섹션에서는 를 인증하고 작업을 시작하는 방법에 대해 설명합니다. [!DNL API]s.

### 일반 만들기 [!DNL API] 사용자 {#requirements}

을 사용하여 작업할 별도의 기술 사용자 계정을 만드는 것이 좋습니다. [!DNL Audience Manager] [!DNL API]s. 조직의 특정 사용자와 연결되거나 연결되지 않은 일반 계정입니다. 이 유형의 [!DNL API] 사용자 계정은 다음 두 가지 작업을 수행하는 데 도움이 됩니다.

* 어떤 서비스가 를 호출하는지 확인합니다. [!DNL API] (예: 를 사용하는 앱에서의 호출 [!DNL API]또는 다음을 만드는 다른 도구에서 [!DNL API] 요청)을 참조하십시오.
* 에 중단 없이 액세스 제공 [!DNL API]s. 특정 사용자에 연결된 계정은 회사에서 나갈 때 삭제될 수 있습니다. 이렇게 하면 사용 가능한 로 작업할 수 없습니다. [!DNL API] 코드. 특정 직원에게 연결되지 않은 일반 계정은 이 문제를 방지하는 데 도움이 됩니다.

이 유형의 계정에 대한 사용 사례로서, 을 사용하여 한 번에 많은 세그먼트를 변경한다고 가정해 보겠습니다. [벌크 관리 도구](../../reference/bulk-management-tools/bulk-management-intro.md). 이렇게 하려면 사용자 계정이 필요합니다. [!DNL API] 액세스 권한. 특정 사용자에게 권한을 추가하는 대신 비특정 [!DNL API] 적절한 자격 증명, 키 및 암호가 있는 사용자 계정 [!DNL API] 호출. 이 기능은 를 사용하는 자체 애플리케이션을 개발하는 경우에도 유용합니다 [!DNL Audience Manager] [!DNL API]s.

을(를) 사용하여 작업 [!DNL Audience Manager] 컨설턴트가 제네릭을 설정하는 경우, [!DNL API]-전용 사용자 계정.

### 암호 인증 워크플로 {#password-authentication-workflow}

암호 인증 보안 액세스 [!DNL REST API]. 아래 단계에서는 의 암호 인증 워크플로에 대해 간략하게 설명합니다. [!DNL JSON] 클라이언트 를 사용할 수 있습니다.

>[!TIP]
>
>액세스 및 새로 고침 토큰을 데이터베이스에 저장하는 경우 이를 암호화합니다.

#### 1단계: 요청 [!DNL API] 액세스

파트너 솔루션 관리자에게 문의하십시오. 방문자는 사용자에게 다음을 제공합니다. [!DNL API] 클라이언트 ID 및 암호. ID 및 비밀로 다음을 인증합니다. [!DNL API].

참고: 새로 고침 토큰을 받으려면 요청할 때 을 지정하십시오 [!DNL API] 액세스 권한.

#### 2단계: 토큰 요청

원하는 토큰 요청을 전달합니다. [!DNL JSON] 클라이언트. 요청을 빌드할 때:

* 사용 `POST` 호출할 메서드 `https://api.demdex.com/oauth/token`.
* 클라이언트 ID 및 암호를 base-64로 인코딩된 문자열로 변환합니다. 전환 프로세스 중에 콜론으로 ID와 암호를 구분합니다. 예를 들어 자격 증명은 `testId : testSecret` 변환 대상 `dGVzdElkOnRlc3RTZWNyZXQ=`.
* 전달 [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` 및 `Content-Type: application/x-www-form-urlencoded` . 예를 들어 머리글은 다음과 같습니다. <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* 요청 본문을 다음과 같이 설정합니다.
  <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### 3단계: 토큰 받기

다음 [!DNL JSON] 응답에 액세스 토큰이 포함되어 있습니다. 응답은 다음과 같아야 합니다.

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

다음 `expires_in` key는 액세스 토큰이 만료될 때까지의 시간(초)을 나타냅니다. 토큰이 노출된 경우 짧은 만료 시간을 사용하여 노출을 제한하는 것이 좋습니다.

### 토큰 새로 고침 {#refresh-token}

토큰 갱신 새로 고침 [!DNL API] 원래 토큰이 만료된 후에 액세스합니다. 요청한 경우 응답 [!DNL JSON] 암호 워크플로의 경우 새로 고침 토큰이 포함됩니다. 새로 고침 토큰을 받지 못한 경우 암호 인증 프로세스를 통해 새 토큰을 만듭니다.

기존 액세스 토큰이 만료되기 전에 새로 고침 토큰을 사용하여 새 토큰을 생성할 수도 있습니다.

액세스 토큰이 만료된 경우 다음을 받게 됩니다. `401 Status Code` 응답에 포함된 다음 헤더:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

다음 절차에서는 새로 고침 토큰을 사용하여 다음에서 새 액세스 토큰을 생성하기 위한 워크플로에 대해 설명합니다. [!DNL JSON] 클라이언트 를 사용할 수 있습니다.

#### 1단계: 새 토큰 요청

원하는 토큰 을 사용하여 새로 고침 요청을 전달합니다. [!DNL JSON] 클라이언트. 요청을 빌드할 때:

* 사용 `POST` 호출할 메서드 `https://api.demdex.com/oauth/token`.
* 클라이언트 ID 및 암호를 base-64로 인코딩된 문자열로 변환합니다. 전환 프로세스 중에 콜론으로 ID와 암호를 구분합니다. 예를 들어 자격 증명은 `testId : testSecret` 변환 대상 `dGVzdElkOnRlc3RTZWNyZXQ=`.
* HTTP 헤더 전달 `Authorization:Basic <base-64 clientID:clientSecret>` 및 `Content-Type: application/x-www-form-urlencoded`. 예를 들어 머리글은 다음과 같습니다. <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* 요청 본문에서 `grant_type:refresh_token` 이전 액세스 요청에서 받은 새로 고침 토큰을 전달합니다. 요청은 다음과 같아야 합니다. <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### 2단계: 새 토큰 받기

다음 [!DNL JSON] 응답에 새 액세스 토큰이 포함되어 있습니다. 응답은 다음과 같아야 합니다.

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

다음 [!DNL Audience Manager] [!UICONTROL REST API] 는 인증 코드 및 암시적 인증을 지원합니다. 이러한 액세스 방법을 사용하려면 사용자가에 로그인해야 합니다. `https://api.demdex.com/oauth/authorize` 액세스 및 토큰 새로 고침.

+++

## 인증됨 [!DNL API] 요청 {#authenticated-api-requests}

호출 요구 사항 [!DNL API] 인증 토큰을 받은 후의 방법.

사용 가능한 을 호출하려면 [!DNL API] 메서드:

* 다음에서 `HTTP` 헤더, 설정 `Authorization: Bearer <token>`.
* 사용 시 [JWT(서비스 계정) 인증](#jwt), 다음을 제공해야 합니다. `x-api-key` 헤더: 와 동일함 `client_id`. 다음을 가져올 수 있습니다. `client_id` 다음에서 [Adobe Developer 통합](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) 페이지를 가리키도록 업데이트하는 중입니다.
* 필수 호출 [!DNL API] 메서드를 사용합니다.

## 선택 사항 [!DNL API] 쿼리 매개 변수 {#optional-api-query-parameters}

개체의 모든 속성을 반환하는 메서드에서 사용할 수 있는 선택적 매개 변수를 설정합니다.

다음 옵션 매개 변수를 사용할 수 있습니다. [!DNL API] 를 반환하는 메서드 *모두* 개체의 속성입니다. 해당 쿼리를 로 전달할 때 요청 문자열에서 이러한 옵션을 설정합니다. [!DNL API].

| 매개 변수 | 설명 |
|--- |--- |
| `page` | 페이지 번호별로 결과를 반환합니다. 번호 매기기는 0부터 시작합니다. |
| `pageSize` | 요청에서 반환되는 응답 결과 수를 설정합니다(기본값: 10). |
| `sortBy` | 지정된 대로 결과를 정렬하고 반환합니다. [!DNL JSON] 속성. |
| `descending` | 결과를 내림차순으로 정렬하고 반환합니다. `ascending` 는 기본값입니다. |
| `search` | 검색 매개 변수로 사용할 지정된 문자열을 기반으로 결과를 반환합니다. 예를 들어 해당 항목의 값 필드 중 하나에서 &quot;Test&quot;라는 단어가 있는 모든 모델의 결과를 찾는다고 가정합니다. 샘플 요청은 다음과 같이 표시될 수 있습니다.   `GET https://aam.adobe.io/v1/models/?search=Test`.  에 의해 반환된 값을 검색할 수 있습니다.[!DNL get all]&quot; 메서드. |
| `folderId` | 에 대한 모든 ID 반환 [!UICONTROL traits] 지정한 폴더 안에 있습니다. 일부 메서드에서는 사용할 수 없습니다. |
| `permissions` | 지정된 권한에 따라 세그먼트 목록을 반환합니다. `READ` 는 기본값입니다. 사용 권한에는 다음이 포함됩니다.<ul><li>`READ` : 세그먼트에 대한 정보를 반환하고 봅니다.</li><li>`WRITE` : 사용  `PUT`  세그먼트 업데이트.</li><li>`CREATE` : 사용  `POST`  세그먼트 만들기.</li><li>`DELETE` : 세그먼트를 삭제합니다. 필요한 경우 기본 트레이트에 대한 액세스 권한이 필요합니다. 예를 들어, 세그먼트를 제거하려면 세그먼트에 속하는 트레이트를 삭제할 수 있는 권한이 필요합니다.</li></ul><br>별도의 키-값 쌍으로 여러 권한을 지정합니다. 예를 들어, 세그먼트 목록을  `READ`  및  `WRITE`  권한만, 전달  `"permissions":"READ"`, `"permissions":"WRITE"` . |
| `includePermissions` | ([!DNL Boolean]) 로 설정합니다. `true` 세그먼트에 대한 권한을 반환합니다. 기본값은 입니다 `false`. |

{style="table-layout:auto"}

### 페이지 옵션에 대한 참고 사항

페이지 정보 *은(는) 아님* 지정하면, 요청이 plain을 반환합니다. [!DNL JSON] 을 반환하면 배열이 생성됩니다. 페이지 정보인 경우 *은(는)* 을 지정하면 반환된 목록이 [!DNL JSON] 전체 결과 및 현재 페이지에 대한 정보가 포함된 개체입니다. 페이지 옵션을 사용하는 샘플 요청은 다음과 유사할 수 있습니다.

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] 요청, 스테이징 및 프로덕션 환경, 버전

## 요청 [!DNL URLs] {#request-urls}

다음 표에는 요청이 나열되어 있습니다 [!DNL URLs] 를 전달하는 데 사용됨 [!DNL API] 메서드별 요청.

사용하는 인증 방법에 따라 요청을 조정해야 합니다 [!DNL URLs] 아래 표에 따르면.

### 요청 [!DNL URLs] 대상: [!BADGE 추천]{type=positive}[!BADGE 더 이상 사용되지 않음]{type=negative}[!DNL JWT] Adobe Developer을 통한 인증 {#request-urls-jwt}

| [!DNL API] 메서드 | 요청 [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://aam.adobe.io/v1/models/` |
| [!DNL Data Source] | `https://aam.adobe.io/v1/datasources/` |
| [!DNL Derived Signals] | `https://aam.adobe.io/v1/signals/derived/` |
| [!DNL Destinations] | `https://aam.adobe.io/v1/destinations/` |
| [!DNL Domains] | `https://aam.adobe.io/v1/partner-sites/` |
| [!DNL Folders] | 트레이트:  `https://aam.adobe.io/v1/folders/traits /`<br>세그먼트:  `https://aam.adobe.io/v1/folders/segments /` |
| [!DNL Schema] | `https://aam.adobe.io/v1/schemas/` |
| [!DNL Segments] | `https://aam.adobe.io/v1/segments/` |
| [!DNL Traits] | `https://aam.adobe.io/v1/traits/` |
| [!DNL Trait Types] | `https://aam.adobe.io/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://aam.adobe.io/v1/taxonomies/0/` |

{style="table-layout:auto"}

### 요청 [!DNL URLs] 대상: [!BADGE 더 이상 사용되지 않음]{type=negative}[!DNL OAuth] 인증 {#request-urls-oauth}

| [!DNL API] 메서드 | 요청 [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://api.demdex.com/v1/models/` |
| [!DNL Data Source] | `https://api.demdex.com/v1/datasources/` |
| [!DNL Derived Signals] | `https://api.demdex.com/v1/signals/derived/` |
| [!DNL Destinations] | `https://api.demdex.com/v1/destinations/` |
| [!DNL Domains] | `https://api.demdex.com/v1/partner-sites/` |
| [!DNL Folders] | 트레이트:  `https://api.demdex.com/v1/folders/traits /`<br>세그먼트:  `https://api.demdex.com/v1/folders/segments /` |
| [!DNL Schema] | `https://api.demdex.com/v1/schemas/` |
| [!DNL Segments] | `https://api.demdex.com/v1/segments/` |
| [!DNL Traits] | `https://api.demdex.com/v1/traits/` |
| [!DNL Trait Types] | `https://api.demdex.com/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://api.demdex.com/v1/taxonomies/0/` |

{style="table-layout:auto"}

## 환경 {#environments}

다음 [!DNL Audience Manager] [!DNL API]는 다양한 작업 환경에 대한 액세스를 제공합니다. 이러한 환경은 라이브 프로덕션 데이터에 영향을 주지 않고 별도의 데이터베이스에 대해 코드를 테스트하는 데 도움이 됩니다. 다음 표에는 사용 가능한 가 나열되어 있습니다 [!DNL API] 환경 및 해당 리소스 호스트 이름.

사용하는 인증 방법에 따라 환경을 조정해야 합니다 [!DNL URLs] 아래 표에 따르면.

| 환경 | 의 호스트 이름 [!DNL JWT] 인증 | 의 호스트 이름 [!DNL OAuth] 인증 |
|---|---|---|
| **프로덕션** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **베타** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>다음 [!DNL Audience Manager] beta 환경은 프로덕션 환경의 소규모 독립형 버전입니다. 테스트할 모든 데이터는 이 환경에서 입력 및 수집해야 합니다.

## 버전 {#versions}

새 버전 [!DNL API]s는 정기적인 일정으로 출시됩니다. 새 릴리스는 [!DNL API] 버전 번호. 요청에서 버전 번호를 참조했습니다. [!DNL URL] 다음으로: `v<version number>` 다음 예와 같이:

`https://<host>/v1/...`

## 정의된 응답 코드 {#response-codes-defined}

`HTTP` 에서 반환된 상태 코드 및 응답 텍스트 [!DNL Audience Manager] [!UICONTROL REST API].

| 응답 코드 ID | 응답 텍스트 | 정의 |
|---|---|---|
| `200` | `OK` | 요청이 정상적으로 처리되었습니다. 필요한 경우 예상 컨텐츠 또는 데이터를 반환합니다. |
| `201` | `Created` | 리소스가 생성되었습니다. 다음에 대한 반환: `PUT` 및 `POST` 요청. |
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
