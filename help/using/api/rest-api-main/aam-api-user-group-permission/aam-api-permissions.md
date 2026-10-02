---
description: 개체 및 그룹의 권한을 관리하는 REST API 메서드입니다.
seo-description: Rest API methods to manage permissions for objects and groups.
seo-title: Permissions Management API Methods
solution: Audience Manager
title: 권한 관리 API 메서드
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
exl-id: 7aac8ea8-4120-4c6b-88a6-30e8aa727dc8
TQID: 'https://experienceleague.adobe.com/E9JWh1JKhHOSd7MzeOR8csVXChyh4Q0RiCj3Y5yb2vM'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
    internal-label: APIs and SDKs
  - id: c814092e-2730-45e8-a12d-e084529f52cb
    internal-label: Destinations
subfeature_v2:
  - id: d8f681b8-67cc-42dc-85c5-a0977528a942
    internal-label: Data Collection Server
  - id: 7dee9651-deb5-5d4d-acfd-fbc10040467f
    internal-label: API
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '97'
ht-degree: 2%
---
# 권한 관리 API 메서드 {#permissions-management-api-methods}

개체 및 그룹의 권한을 관리하는 나머지 [!DNL API] 메서드입니다.

<!-- c_rest_api_perm_man.xml -->

## 사용 가능한 객체 유형 나열 {#list-object-types}

역할 기반 액세스 컨트롤을 설정할 수 있는 사용 가능한 개체 형식을 나열하는 `GET` 메서드입니다.

<!-- r_rest_api_perm_list.xml -->

### 요청

`GET /api/v1/permissionable-object-types/`

### 응답

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## 개체 유형에 사용 가능한 권한 나열 {#list-permissions-object-type}

개체 유형에 사용 가능한 권한을 나열하는 `GET` 메서드입니다.

<!-- r_rest_api_perm_list_perms.xml -->

### 요청

`GET /api/v1/permissionable-object-types/SEGMENT/`

### 응답

```
{ 
 "wildcard" : [ "VIEW_ALL_SEGMENTS", "EDIT_ALL_SEGMENTS", "CREATE_ALL_SEGMENTS", "DELETE_ALL_SEGMENTS", "MAP_ALL_SEGMENTS_TO_MODELS", "MAP_ALL_TO_DESTINATIONS" ], 
 "perObject" : [ "READ", "WRITE", "CREATE", "DELETE", "MAP_TO_MODELS", "MAP_TO_DESTINATION" ]
}
```

>[!NOTE]
>
>TAGS 및 DERIVED SIGNALS 객체 유형에는 사용할 일반 권한이 없습니다. 이러한 객체 유형의 컨트롤은 모두 또는 없음 와일드카드 권한에 의해서만 변경됩니다.
