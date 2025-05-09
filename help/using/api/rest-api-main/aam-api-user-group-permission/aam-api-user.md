---
description: 사용자 개체 만들기, 업데이트, 나열, 삭제 및 반환을 포함하여 사용자를 관리하는 REST API 메서드입니다.
seo-description: Rest API methods to manage users, including creating, updating, listing, deleting, and returning user objects.
seo-title: User Management API Methods
solution: Audience Manager
title: 사용자 관리 API 메서드
uuid: 6e1f2c35-bb9d-4166-b7d4-d9c5518a61ad
feature: API
exl-id: c015c42c-63c7-4392-9fef-f48dc787a56f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 1%

---

# 사용자 관리 API 메서드 {#user-management-api-methods}

사용자 개체 만들기, 업데이트, 목록, 삭제 및 반환을 포함하여 사용자를 관리하는 나머지 [!DNL API] 메서드입니다.

<!-- c_rest_api_user_man_user.xml -->

## 사용자 만들기 {#create-user}

새 사용자를 만드는 `POST` 메서드입니다.

<!-- r_rest_api_user_create.xml -->

### 요청

`POST /api/v1/users/`

### 샘플 요청 본문

```
{ 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...], 
  "isAdmin" : true | false 
}
```

### 응답

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...], 
  "isAdmin" : <"true"|"false"> 
 
}
```

`isAdmin`이(가) true로 설정되어 있으면 사용자가 파트너 관리자로 만들어집니다. 이 속성을 사용하면 사용자가 파트너 관리자인지 여부도 알 수 있습니다.

사용자 이름을 이미 사용한 경우 `409 Conflict`을(를) 반환합니다.

## 사용자 업데이트 {#update-user}

사용자를 업데이트하는 `PUT` 방법입니다.

<!-- r_rest_api_user_update.xml -->

### 요청

`PUT /api/v1/users/`*`<userId>`*

### 샘플 요청 본문

```
{ 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...] 
}
```

### 응답

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "groups" : [<group_1_id>, ...] 
 
}
```

사용자 이름을 이미 사용한 경우 `409 Conflict`을(를) 반환합니다.

## 로그인한 사용자 업데이트 {#update-logged-in-user}

현재 로그인한 사용자를 업데이트하는 `PUT` 메서드입니다.

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>대부분의 [!DNL API] 메서드는 파트너 관리자만 호출할 수 있지만 이 메서드는 관리자가 아닌 사용자도 호출할 수 있습니다.

### 요청

`PUT /self/update`

### 샘플 요청 본문

```
{  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null> 
}
```

### 응답

```
{ 
  "userId": <integer>,,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string> 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null> 
}
```

사용자 이름을 이미 사용한 경우 `409 Conflict`을(를) 반환합니다.

## 로그인한 사용자 암호 업데이트 {#update-logged-in-user-pw}

현재 로그인한 사용자를 업데이트하는 `PUT` 메서드입니다.

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>대부분의 [!DNL API] 메서드는 파트너 관리자만 호출할 수 있지만 이 메서드는 관리자가 아닌 사용자도 호출할 수 있습니다.

### 요청

`POST /users/self/update-password`

### 샘플 요청 본문

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

성공하면 `200 OK`을(를) 반환합니다. 암호가 잘못되면 `400 Bad Request`을(를) 반환합니다.

## 로그인한 사용자 암호 재설정 {#reset-logged-in-user-pw}

현재 로그인한 사용자를 재설정하는 `PUT` 메서드입니다. [!UICONTROL Audience Management]이(가) 시스템에서 생성한 암호를 사용자에게 보냅니다.

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>대부분의 [!DNL API] 메서드는 파트너 관리자만 호출할 수 있지만 이 메서드는 관리자가 아닌 사용자도 호출할 수 있습니다.

### 요청

`POST /self/reset-password`

성공하면 `200 OK`을(를) 반환합니다.

## 사용자 ID에 대한 사용자 개체 반환 {#return-user-object-for-id}

사용자 ID에 대한 사용자 개체를 반환하는 `Get` 메서드입니다.

<!-- r_rest_api_user_get_user_obj.xml -->

### 요청

`GET /api/v1/users/`*`<userId>`*

### 응답

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<groupd_id_1>, ...] 
 
}
```

## 로그인한 사용자에 대한 사용자 개체 반환 {#return-user-object-for-logged-in-user}

현재 로그인한 사용자의 사용자 개체를 반환하는 `Get` 메서드입니다.

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>대부분의 [!DNL API] 메서드는 파트너 관리자만 호출할 수 있지만 이 메서드는 관리자가 아닌 사용자도 호출할 수 있습니다.

### 요청

`GET /api/v1/users/self`

### 응답

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<groupd_id_1>, ...] 
 
}
```

## 사용자 나열 {#list-users}

사용자를 나열하는 `GET` 메서드.

<!-- r_rest_api_user_list.xml -->

### 요청

`GET /api/v1/users/`

쿼리 매개 변수에서 여러 그룹 ID를 지정할 수 있습니다.

`GET /api/v1/users/?groupId=343&groupdId=12`

이 쿼리는 지정된 그룹의 모든 사용자 목록을 반환합니다.

### 응답

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...] 
 
}
```

## 사용자 삭제 {#delete-users}

사용자를 삭제하는 `DELETE` 메서드입니다.

<!-- r_rest_api_user_delete.xml -->

### 요청

`DELETE /api/v1/users/`*`<user_id>`*

성공하면 `204 No Content`을(를) 반환합니다. 충돌이 발생하면 `409 Conflict`을(를) 반환합니다.

## 일괄 사용자 삭제 {#delete-users-bulk}

여러 사용자를 일괄 삭제하는 `POST` 메서드입니다.

<!-- r_rest_api_user_delete_bulk.xml -->

### 요청

`POST /api/v1/users/bulk-delete`

### 샘플 요청 본문

```
{[<user_id_1>, <user_id_2>, ...]}
```
