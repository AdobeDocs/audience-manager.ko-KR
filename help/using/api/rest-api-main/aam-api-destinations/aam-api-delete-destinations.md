---
description: 대상 및 POST 매핑을 제거할 수 있는 DELETE 및 세그먼트 메서드.
seo-description: DELETE and POST methods that let you remove destinations and segment mappings.
seo-title: Delete Destinations
solution: Audience Manager
title: 대상 삭제
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
feature: API
exl-id: eaac3908-75ab-42d2-93bd-e8979f8b2427
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 6%

---

# 대상 삭제 {#delete-destinations}

`DELETE` 및 `POST` 대상 및 세그먼트 매핑을 제거할 수 있는 방법입니다.

<!-- r_delete_destinations_all.xml -->

## 대상 삭제

A `DELETE` 대상을 제거하는 방법입니다.

>[!NOTE]
>
>대상을 삭제하려면 먼저 모든 세그먼트 매핑을 제거해야 합니다.

* 요청: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* 응답: 코드를 반환합니다. `204 No Content` 성공하면

## 대상 일괄 삭제

이 옵션을 사용하여 여러 대상 제거 `POST` 메서드를 사용합니다. 대상 ID 전달( `destinationId`)를 추가합니다.

* 요청: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* 응답: 코드를 반환합니다. `204 No Content` 성공하면

## 세그먼트 매핑 ID별 대상 매핑 삭제

A `POST` 지정된 세그먼트 ID에 따라 대상 매핑을 제거하는 메서드입니다.

* 요청: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* 응답: 코드를 반환합니다. `204 No Content` 성공하면
