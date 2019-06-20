---
description: Audience Manager 일반적인 분류법을 볼 수 있도록 해주는 메서드입니다. 이 선택적 분류 체계는 트레이트를 업계 표준 카테고리로 분류합니다.
seo-description: Audience Manager 일반적인 분류법을 볼 수 있도록 해주는 메서드입니다. 이 선택적 분류 체계는 트레이트를 업계 표준 카테고리로 분류합니다.
seo-title: 분류 체계 API 메서드
solution: Audience Manager
title: 분류 체계 API 메서드
uuid: 4 EE 29 BA 5-E 9 BA -4498-A 6 EE -7343227 DD 7 BA
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Taxonomic API Methods {#taxonomic-api-methods}

Audience Manager 일반적인 분류법을 볼 수 있도록 해주는 메서드입니다. 이 선택적 분류 체계는 트레이트를 업계 표준 카테고리로 분류합니다.

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>이러한 방법으로 새 분류 범주를 만들거나 트레이트를 분류할 수는 없습니다. To classify a trait, specify the appropriate `categoryId` with a trait create or update method.

## Return a Specific Taxonomy {#return-specific-taxonomy}

A `GET` method that returns details about the specified taxonomic category.

<!-- r_rest_api_taxonomy.xml -->

### 요청

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### 응답

A successful response returns `200 OK` and the category for the specified ID. An unsuccessful request returns `404 No Content` if the ID does not exist.

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

## Return all Taxonomic Categories {#return-all-taxonomy-categories}

A `GET` method that returns a list of the top-level categories in an array.

<!-- r_rest_api_taxonomies.xml -->

### 요청

`GET https://api.demdex.com/v1/taxonomies/0/`

### 응답

간결하게 잘립니다.

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

## Return Taxonomic Sub-Categories {#return-taxonomy-sub-categories}

A `GET` method that returns sub-categories for the specified parent category in an array.

<!-- r_rest_api_taxonomy_sub.xml -->

### 요청

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### 응답

A successful response returns `200 OK` and the category for the specified ID. An unsuccessful request returns `404 No Content` if the ID does not exist. 간결하게 잘립니다.

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
