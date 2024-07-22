---
description: Audience Manager 일반 분류법을 볼 수 있는 메서드입니다. 이 선택적 분류 체계는 트레이트를 업계 표준 카테고리로 구성합니다.
seo-description: Methods that let you view the Audience Manager common taxonomy. This optional classification scheme organizes traits into industry standard categories.
seo-title: Taxonomic API Methods
solution: Audience Manager
title: 분류 API 메서드
uuid: 4ee29ba5-e9ba-4498-a6ee-7343227dd7ba
feature: API
exl-id: 8bc6dcbb-7f5b-4a7b-998d-025eaf76c409
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 1%

---

# 분류 API 메서드 {#taxonomic-api-methods}

Audience Manager 일반 분류법을 볼 수 있는 메서드입니다. 이 선택적 분류 체계는 트레이트를 업계 표준 카테고리로 구성합니다.

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>이러한 방법으로는 새 분류법 범주를 만들거나 특성을 분류할 수 없습니다. 특성을 분류하려면 특성 만들기 또는 업데이트 메서드로 적절한 `categoryId`을(를) 지정하십시오.

## 특정 분류 체계 반환 {#return-specific-taxonomy}

지정된 분류법 범주에 대한 세부 정보를 반환하는 `GET` 메서드입니다.

<!-- r_rest_api_taxonomy.xml -->

### 요청

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### 응답

성공한 응답이 `200 OK`과(와) 지정한 ID의 범주를 반환합니다. 실패한 요청은 ID가 없는 경우 `404 No Content`을(를) 반환합니다.

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

배열에서 최상위 범주 목록을 반환하는 `GET` 메서드입니다.

<!-- r_rest_api_taxonomies.xml -->

### 요청

`GET https://api.demdex.com/v1/taxonomies/0/`

### 응답

간결성을 위해 잘립니다.

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

## 분류 체계적 하위 범주 반환 {#return-taxonomy-sub-categories}

배열에서 지정한 부모 범주에 대한 하위 범주를 반환하는 `GET` 메서드입니다.

<!-- r_rest_api_taxonomy_sub.xml -->

### 요청

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### 응답

성공한 응답이 `200 OK`과(와) 지정한 ID의 범주를 반환합니다. 실패한 요청은 ID가 없는 경우 `404 No Content`을(를) 반환합니다. 간결성을 위해 잘립니다.

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
