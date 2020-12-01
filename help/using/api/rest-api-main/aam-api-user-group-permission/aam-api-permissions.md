---
description: 나머지 API 메서드를 사용하여 개체 및 그룹의 권한을 관리합니다.
seo-description: 나머지 API 메서드를 사용하여 개체 및 그룹의 권한을 관리합니다.
seo-title: 권한 관리 API 메서드
solution: Audience Manager
title: 권한 관리 API 메서드
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 14%

---


# 권한 관리 API 메서드 {#permissions-management-api-methods}

개체 및 그룹에 대한 권한을 관리하려면 [!DNL API] 메서드를 중지합니다.

<!-- c_rest_api_perm_man.xml -->

## 사용 가능한 개체 유형 목록 {#list-object-types}

역할 기반 액세스 컨트롤을 설정할 수 있는 사용 가능한 개체 유형을 나열하는 `GET` 메서드입니다.

<!-- r_rest_api_perm_list.xml -->

### 요청

`GET /api/v1/permissionable-object-types/`

### 응답

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## 개체 유형 {#list-permissions-object-type}에 대한 사용 가능한 권한 목록

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
>개체 유형 TAGS 및 DERIVED SIGNATURES에는 사용할 일반 권한이 없습니다. 이러한 개체 유형에 대한 컨트롤은 모두 또는 [와일드카드 사용 권한 없음]으로만 변경됩니다.