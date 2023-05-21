---
description: 개체 및 그룹의 권한을 관리하는 REST API 메서드입니다.
seo-description: Rest API methods to manage permissions for objects and groups.
seo-title: Permissions Management API Methods
solution: Audience Manager
title: 권한 관리 API 메서드
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
exl-id: 7aac8ea8-4120-4c6b-88a6-30e8aa727dc8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 12%

---

# 권한 관리 API 메서드 {#permissions-management-api-methods}

Rest [!DNL API] 개체 및 그룹에 대한 권한을 관리하는 방법입니다.

<!-- c_rest_api_perm_man.xml -->

## 사용 가능한 객체 유형 나열 {#list-object-types}

A `GET` 역할 기반 액세스 컨트롤을 설정할 수 있는 사용 가능한 개체 형식을 나열하는 메서드입니다.

<!-- r_rest_api_perm_list.xml -->

### 요청

`GET /api/v1/permissionable-object-types/`

### 응답

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## 개체 유형에 사용 가능한 권한 나열 {#list-permissions-object-type}

A `GET` 개체 유형에 사용 가능한 권한을 나열하는 메서드입니다.

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
