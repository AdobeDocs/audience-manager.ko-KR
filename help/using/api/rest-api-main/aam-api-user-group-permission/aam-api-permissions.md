---
description: REST API 메서드를 사용하여 개체 및 그룹에 대한 권한을 관리할 수 있습니다.
seo-description: REST API 메서드를 사용하여 개체 및 그룹에 대한 권한을 관리할 수 있습니다.
seo-title: 권한 관리 API 메서드
solution: Audience Manager
title: 권한 관리 API 메서드
uuid: 111 d 0 f 92-d 92 c -4 d 4 b-b 0 d 6-10 dd 3 fa 466 ad
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Permissions Management API Methods {#permissions-management-api-methods}

Rest [!DNL API] methods to manage permissions for objects and groups.

<!-- c_rest_api_perm_man.xml -->

## List Available Object Types {#list-object-types}

A `GET` method to list available object types on which role-based access controls can be set.

<!-- r_rest_api_perm_list.xml -->

### 요청

`GET /api/v1/permissionable-object-types/`

### 응답

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## List Available Permissions for an Object Type {#list-permissions-object-type}

A `GET` method to list available permissions for an object type.

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
>개체 유형 태그 및 파생된 신호에 사용할 수 있는 일반 권한이 없습니다. 이러한 개체 유형에 대한 컨트롤은 모두 와일드카드 권한이나 모든 와일드카드 권한으로만 변경됩니다.