---
description: Audience Manager 일반 분류법을 볼 수 있는 메서드입니다. 이 선택적 분류 구성표는 트레이트를 업계 표준 카테고리로 구성합니다.
seo-description: Audience Manager 일반 분류법을 볼 수 있는 메서드입니다. 이 선택적 분류 구성표는 트레이트를 업계 표준 카테고리로 구성합니다.
seo-title: 분류 API 메서드
solution: Audience Manager
title: 분류 API 메서드
uuid: 4ee29ba5-e9ba-4498-a6ee-7343227dd7ba
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 7%

---


# 분류 API 메서드 {#taxonomic-api-methods}

Audience Manager 일반 분류법을 볼 수 있는 메서드입니다. 이 선택적 분류 구성표는 트레이트를 업계 표준 카테고리로 구성합니다.

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>이러한 방법으로 새로운 분류 카테고리를 만들거나 특성을 분류할 수 없습니다. 트레이트를 분류하려면 특성 만들기 또는 업데이트 방법으로 적절한 `categoryId`을 지정합니다.

## 특정 분류 반환 {#return-specific-taxonomy}

지정된 분류 범주에 대한 세부 정보를 반환하는 `GET` 메서드입니다.

<!-- r_rest_api_taxonomy.xml -->

### 요청

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### 응답

성공적인 응답은 `200 OK` 및 지정된 ID의 카테고리를 반환합니다. 실패한 요청은 ID가 없는 경우 `404 No Content`을 반환합니다.

```
{
    "crUID": 158,
    "name": "Arts & Entertainment",
    "upUID": 158,
    "description": "Arts & Entertainment",
    "categoryID": 1,
    "parentCategoryID": 0
}
```

## 모든 분류 범주 반환 {#return-all-taxonomy-categories}

배열의 최상위 수준 카테고리 목록을 반환하는 `GET` 메서드입니다.

<!-- r_rest_api_taxonomies.xml -->

### 요청

`GET https://api.demdex.com/v1/taxonomies/0/`

### 응답

간결하게 잘렸습니다.

```
[
    {
        "crUID": 158,
        "name": "Arts & Entertainment",
        "upUID": 158,
        "description": "Arts & Entertainment",
        "categoryID": 1,
        "parentCategoryID": 0
    },
    {
        "crUID": 158,
        "name": "Automotive",
        "upUID": 158,
        "description": "Automotive",
        "categoryID": 2,
        "parentCategoryID": 0
    },
    {
        "crUID": 158,
        "name": "Business",
        "upUID": 158,
        "description": "Business",
        "categoryID": 3,
        "parentCategoryID": 0
    }
]
```

## 반환 분류 하위 범주 {#return-taxonomy-sub-categories}

배열에서 지정된 상위 카테고리의 하위 카테고리를 반환하는 `GET` 메서드입니다.

<!-- r_rest_api_taxonomy_sub.xml -->

### 요청

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### 응답

성공적인 응답은 `200 OK` 및 지정된 ID의 카테고리를 반환합니다. 실패한 요청은 ID가 없는 경우 `404 No Content`을 반환합니다. 간결하게 잘렸습니다.

```
[
    {
        "crUID": 158,
        "name": "Books & Literature",
        "upUID": 158,
        "description": "Books & Literature",
        "categoryID": 25,
        "parentCategoryID": 1
    },
    {
        "crUID": 158,
        "name": "Celebrity Fan/Gossip",
        "upUID": 158,
        "description": "Celebrity Fan/Gossip",
        "categoryID": 49,
        "parentCategoryID": 1
    },
    {
        "crUID": 158,
        "name": "Fine Art",
        "upUID": 158,
        "description": "Fine Art",
        "categoryID": 72,
        "parentCategoryID": 1
    }
]
```
