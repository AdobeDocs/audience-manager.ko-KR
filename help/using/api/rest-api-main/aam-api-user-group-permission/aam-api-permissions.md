---
description: Rest API 메서드를 사용하여 개체 및 그룹에 대한 권한을 관리할 수 있습니다.
seo-description: Rest API 메서드를 사용하여 개체 및 그룹에 대한 권한을 관리할 수 있습니다.
seo-title: 권한 관리 API 메서드
solution: Audience Manager
title: 권한 관리 API 메서드
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# 권한 관리 API 메서드 {#permissions-management-api-methods}

나머지 [!DNL API] 방법을 사용하여 개체 및 그룹에 대한 권한을 관리합니다.

<!-- c_rest_api_perm_man.xml -->

## 사용 가능한 개체 유형 목록 {#list-object-types}

역할 기반 액세스 컨트롤을 설정할 수 있는 사용 가능한 객체 유형을 나열하는 `GET` 방법입니다.

<!-- r_rest_api_perm_list.xml -->

### 요청

`GET /api/v1/permissionable-object-types/`

### 응답

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## 객체 유형에 사용할 수 있는 권한 목록 {#list-permissions-object-type}

객체 유형에 사용 가능한 권한을 나열하는 `GET` 방법입니다.

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
>개체 유형 TAGS 및 DERIVED SIGNATURES에는 사용할 일반 권한이 없습니다. 이러한 개체 유형에 대한 컨트롤은 모두 또는 아무 것도 와일드카드 권한으로만 변경됩니다.