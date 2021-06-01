---
description: 사용자 정의 유형 또는 카테고리에 트레이트를 할당할 수 있는 선택 방법으로서, 일반적으로 기능이나 자체 내부 보고 프로세스에 따라 다릅니다.
seo-description: 사용자 정의 유형 또는 카테고리에 트레이트를 할당할 수 있는 선택 방법으로서, 일반적으로 기능이나 자체 내부 보고 프로세스에 따라 다릅니다.
seo-title: 트레이트 유형 메서드
solution: Audience Manager
title: 트레이트 유형 메서드
uuid: 082931d5-457b-4622-817b-86303f38c26a
feature: API
exl-id: d450f9ce-2abb-4a8b-b8db-2962b84fb341
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 10%

---

# 트레이트 유형 메서드 {#trait-type-methods}

사용자 정의 유형 또는 카테고리에 트레이트를 할당할 수 있는 선택 방법으로서, 일반적으로 기능이나 자체 내부 보고 프로세스에 따라 다릅니다.

<!-- c_rest_api_trait_types_intro.xml -->

>[!NOTE]
>
>특성 유형 메서드는 [일반적인 분류](../../api/rest-api-main/aam-api-taxonomy.md#taxonomic-api-methods)에 사용되는 카테고리에 트레이트를 할당하지 않습니다. 이러한 분류는 일반적인 분류법과는 별개인 레이블로 생각하십시오.

시각적 참조의 경우 [!UICONTROL Trait Types]은 **[!UICONTROL Traits > Create new trait > Basic Information]** 아래의 [!DNL UI]에 있는 드롭다운 컨트롤입니다.

## 새 트레이트 유형 {#create-trait-type} 만들기

새 트레이트 유형을 만들 수 있는 `POST` 메서드입니다.

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

## 트레이트 유형 {#return-props}에 대한 속성 반환

지정된 트레이트 유형에 대한 세부 정보를 반환하는 `GET` 메서드입니다.

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

## 모든 트레이트 유형에 대한 속성 반환 {#return-props-all}

배열에 있는 모든 트레이트 유형에 대한 세부 정보를 반환하는 `GET` 메서드입니다.

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
