---
description: 일반적으로 함수 또는 자체 내부 보고 프로세스에 따라 사용자 정의된 유형 또는 카테고리에 트레이트를 할당할 수 있는 선택적 메서드입니다.
seo-description: 일반적으로 함수 또는 자체 내부 보고 프로세스에 따라 사용자 정의된 유형 또는 카테고리에 트레이트를 할당할 수 있는 선택적 메서드입니다.
seo-title: 특성 유형 메서드
solution: Audience Manager
title: 특성 유형 메서드
uuid: 082931 D 5-457 B -4622-817 B -86303 F 38 C 26 A
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Trait Type Methods {#trait-type-methods}

일반적으로 함수 또는 자체 내부 보고 프로세스에 따라 사용자 정의된 유형 또는 카테고리에 트레이트를 할당할 수 있는 선택적 메서드입니다.

<!-- c_rest_api_trait_types_intro.xml -->

>[!NOTE]
>
>Trait type methods do not assign traits to categories used by the [common taxonomy](../../api/rest-api-main/aam-api-taxonomy.md#taxonomic-api-methods). 이러한 레이블들은 일반적인 분류 체계와는 별개의 레이블로 생각할 수 있습니다.

For visual reference, [!UICONTROL Trait Types] is a dropdown control located in the [!DNL UI] under **[!UICONTROL Traits > Create new trait > Basic Information]**.

## Create a New Trait Type {#create-trait-type}

A `POST` method that lets you create a new trait type.

<!-- r_rest_api_create_trait_type.xml -->

### 요청

`POST https://api.demdex.com/v1/customer-trait-types`

### 샘플 요청

```
{
"name":"Custom trait type"
}
```

### 응답

```
{
    "pixelType": 34,
    "pid": 1099,
    "name": "Custom type",
    "description": null,
    "crUID": 694,
    "upUID": 694,
    "createTime": 1358297352000,
    "updateTime": 1358297352000
}
```

## Return Properties for a Trait Type {#return-props}

A `GET` method that returns details about the specified trait type.

<!-- r_rest_api_get_trait_type.xml -->

### 요청

`GET https://api.demdex.com/v1/customer-trait-types/`*`<customerTraitTypeId>`*

### 응답

```
{
    "pixelType": 4,
    "pid": 0,
    "name": "Delivery Event",
    "description": "Delivery Event",
    "crUID": 158,
    "upUID": 158,
    "createTime": 1299115496000,
    "updateTime": 1299115496000
}
```

## Return Properties for all Trait Types {#return-props-all}

A `GET` method that returns details about all your trait types in an array.

<!-- r_rest_api_get_trait_types.xml -->

### 요청

`GET https://api.demdex.com/v1/customer-trait-types/`

### 응답

```
[
    {
        "pixelType": 200,
        "pid": 1099,
        "name": "Customer Specific Trait Type",
        "description": "Test",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1349990458000,
        "updateTime": 1349990458000
    },
    {
        "pixelType": 1,
        "pid": 0,
        "name": "User Trait",
        "description": "User Trait",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1299115492000,
        "updateTime": 1299115492000
    },
    {
        "pixelType": 2,
        "pid": 0,
        "name": "Site Visitor",
        "description": "Site Visitor",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1299115493000,
        "updateTime": 1299115493000
    }
]
```
