---
description: 그룹 만들기, 업데이트, 나열, 삭제 등 그룹을 관리하는 REST API 메서드입니다.
seo-description: Rest API methods to manage groups, including creating, updating, listing, deleting groups.
seo-title: Group Management API Methods
solution: Audience Manager
title: 그룹 관리 API 메서드
uuid: fe042eb5-ea12-42fe-be98-d721f987a914
feature: API
exl-id: b43c8404-1853-4306-8f26-96d9191a2548
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 5%

---

# 그룹 관리 API 메서드 {#group-management-api-methods}

그룹 만들기, 업데이트, 나열, 삭제를 포함하여 그룹을 관리하는 나머지 [!DNL API] 메서드입니다.

<!-- c_rest_api_user_man_group.xml -->

## 그룹 만들기 {#create-group}

새 사용자 그룹을 만드는 `POST` 메서드입니다.

<!-- r_rest_api_group_create.xml -->

### 요청

`POST /api/v1/groups/`

### 샘플 요청 본문

```
 {
    "name" : <string>,
    "description" : <string_may_be_null>,
 }
```

### 응답

```
  {
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }
```

## 그룹 업데이트 {#update-group}

사용자 그룹을 업데이트하는 `PUT` 메서드.

<!--
r_rest_api_group_update.xml
-->

### 요청

`PUT /api/v1/groups/`*`<groupId>`*

### 샘플 요청 본문

```
 {
    "name" : <string>,
    "description" : <string_may_be_null>,
 }
```

### 응답

```
  {
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }
```

## 목록 그룹 {#list-groups}

사용자 그룹을 나열하는 `GET` 메서드.

<!--
r_rest_api_group_list.xml
-->

### 요청

`GET /api/v1/groups/`

### 응답

```
[
  { 
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }, ...
]
```

## 그룹 삭제 {#delete-groups}

사용자 그룹을 삭제하고 해당 그룹에서 모든 구성원을 제거하는 `DELETE` 메서드입니다.

<!-- r_rest_api_group_delete.xml -->

### 요청

`DELETE /api/v1/groups/`*`<groupId>`*

성공하면 `204 No Content`을(를) 반환합니다. 충돌이 발생하면 `409 Conflict`을(를) 반환합니다.

## 일괄 그룹 삭제 {#delete-groups-bulk}

여러 그룹을 일괄적으로 삭제하고 해당 그룹에서 모든 구성원을 제거하는 `DELETE` 메서드입니다.

<!-- r_rest_api_group_delete_bulk.xml -->

### 요청

`DELETE /api/v1/groups/bulk-delete`

성공하면 `204 No Content`을(를) 반환합니다. 충돌이 발생하면 `409 Conflict`을(를) 반환합니다.

## 그룹에 대한 모든 권한 나열 {#list-permissions-group}

그룹에 권한 개체를 나열하는 `GET` 메서드입니다.

<!-- r_rest_api_perm_list_group.xml -->

### 요청

`GET /api/v1/groups/{groupId}/permissions`

### 응답

```
[{
 "objectId" : 34,
 "objectType": "SEGMENT",
 "permissions": ["READ", "WRITE", "DELETE", "MAP_TO_MODELS"]
 },

{
 "objectId" : "234",
 "objectType": "TRAIT",
 "permissions": ["READ", "WRITE", "DELETE", "MAP_TO_MODELS"]
 },
 {
 "objectId" : 277,
 "objectType": "SEGMENT",
 "permissions": ["READ", "WRITE", "MAP_TO_MODELS"]
 }
]
```

그룹에 액세스할 수 없는 경우 `400 Bad Request`을(를) 반환합니다.

## 그룹에 대한 권한 설정 {#set-permissions-group}

그룹 권한을 업데이트하는 `PUT` 메서드입니다. 이 메서드는 이전 권한을 새 권한으로 덮어씁니다.

<!-- r_rest_api_perm_set.xml -->

### 요청

`PUT /api/v1/groups/{groupId}/permissions/`

### 응답

```
[ 
  { "objectType" : "SEGMENT",
    "objectId" : 563,
    "permissions" : [ "READ", "WRITE"]
  },
  { "objectType" : "SEGMENT",
    "objectId" : 2363,
    "permissions" : [ "CREATE", "WRITE"]
  },
  { "objectType" : "TRAIT",
    "objectId" : 83498,
    "permissions" : [ "READ", "MAP_TO_SEGMENTS"]
  },
  { "objectType" : "DESTINATION",
    "objectId" : 304,
    "permissions" : [ "READ", "WRITE", "CREATE"]
  }
]
```

샘플 응답은 업데이트된 권한 개체 목록을 나타냅니다.

성공하면 `200 OK`을(를) 반환합니다. 지정된 권한이 잘못된 경우 `400`을(를) 반환합니다. 로그인한 사용자가 개체에 액세스할 수 없는 경우 `403`을(를) 반환할 수도 있습니다.
