---
description: Audience Manager 일반 분류법을 볼 수 있는 메서드입니다. 이 선택적 분류 체계를 통해 트레이트를 업계 표준 카테고리로 분류할 수 있습니다.
seo-description: Audience Manager 일반 분류법을 볼 수 있는 메서드입니다. 이 선택적 분류 체계를 통해 트레이트를 업계 표준 카테고리로 분류할 수 있습니다.
seo-title: 분류 API 메서드
solution: Audience Manager
title: 분류 API 메서드
uuid: 4ee29ba5-e9ba-4498-a6ee-7343227dd7ba
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# 분류 API 메서드 {#taxonomic-api-methods}

Audience Manager 일반 분류법을 볼 수 있는 메서드입니다. 이 선택적 분류 체계를 통해 트레이트를 업계 표준 카테고리로 분류할 수 있습니다.

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>새로운 분류 카테고리를 만들거나 이러한 방법으로 트레이트를 분류할 수 없습니다. 트레이트를 분류하려면 트레이트 만들기 또는 업데이트 `categoryId` 방법으로 해당 트레이트를 지정합니다.

## 특정 분류 반환 {#return-specific-taxonomy}

지정된 분류 범주에 대한 세부 정보를 반환하는 `GET` 메서드입니다.

<!-- r_rest_api_taxonomy.xml -->

### 요청

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### 응답

성공적인 응답이 반환되고 지정된 ID에 대한 `200 OK` 카테고리가 반환됩니다. ID가 없는 `404 No Content` 경우 실패한 요청이 반환됩니다.

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

## 모든 분류 카테고리 반환 {#return-all-taxonomy-categories}

배열에서 최상위 수준 카테고리 목록을 반환하는 `GET` 메서드입니다.

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

## 분류 하위 카테고리 반환 {#return-taxonomy-sub-categories}

배열에서 지정된 상위 범주에 대한 하위 범주를 반환하는 `GET` 메서드입니다.

<!-- r_rest_api_taxonomy_sub.xml -->

### 요청

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### 응답

성공적인 응답이 반환되고 지정된 ID에 대한 `200 OK` 카테고리가 반환됩니다. ID가 없는 `404 No Content` 경우 실패한 요청이 반환됩니다. 간결하게 잘렸습니다.

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
