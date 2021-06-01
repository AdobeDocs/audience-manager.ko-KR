---
description: 개체 및 그룹에 대한 권한을 관리하는 REST API 메서드.
seo-description: 개체 및 그룹에 대한 권한을 관리하는 REST API 메서드.
seo-title: 권한 관리 API 메서드
solution: Audience Manager
title: 권한 관리 API 메서드
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
exl-id: 7aac8ea8-4120-4c6b-88a6-30e8aa727dc8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 15%

---

# 권한 관리 API 메서드 {#permissions-management-api-methods}

개체 및 그룹에 대한 권한을 관리하려면 [!DNL API] 메서드를 사용하십시오.

<!-- c_rest_api_perm_man.xml -->

## 사용 가능한 개체 유형 목록 {#list-object-types}

역할 기반 액세스 제어를 설정할 수 있는 사용 가능한 개체 유형을 나열하는 `GET` 메서드입니다.

<!-- r_rest_api_perm_list.xml -->

### 요청

`GET /api/v1/permissionable-object-types/`

### 응답

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## 개체 유형 {#list-permissions-object-type}에 사용 가능한 사용 권한 나열

개체 유형에 사용할 수 있는 권한을 나열하는 `GET` 메서드입니다.

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
>개체 유형 TAGS 및 파생 SIGNAL에는 사용할 일반 권한이 없습니다. 이러한 개체 유형에 대한 컨트롤은 모두 또는 없음 와일드카드 권한으로만 변경됩니다.
