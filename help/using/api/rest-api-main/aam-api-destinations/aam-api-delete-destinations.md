---
description: 대상 및 세그먼트 매핑을 제거할 수 있는 DELETE 및 POST 메서드
seo-description: 대상 및 세그먼트 매핑을 제거할 수 있는 DELETE 및 POST 메서드
seo-title: 대상 삭제
solution: Audience Manager
title: 대상 삭제
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 7%

---


# 대상 삭제 {#delete-destinations}

`DELETE` 및 대상 및 세그먼트 매핑을 제거할  `POST` 수 있는 메서드를 사용하는 것이 좋습니다.

<!-- r_delete_destinations_all.xml -->

## 대상 삭제

대상을 제거하는 `DELETE` 메서드입니다.

>[!NOTE]
>
>대상을 삭제하려면 먼저 세그먼트 매핑을 모두 제거해야 합니다.

* 요청: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* 응답:성공한 경우 `204 No Content` 코드를 반환합니다.

## 벌크 삭제 대상

이 `POST` 메서드로 여러 대상을 제거합니다. 요청 본문에 배열이 있는 대상 ID( `destinationId`)를 전달합니다.

* 요청: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* 응답:성공한 경우 `204 No Content` 코드를 반환합니다.

## 세그먼트 매핑 ID로 대상 매핑 삭제

지정된 세그먼트 ID에 따라 대상 매핑을 제거하는 `POST` 메서드입니다.

* 요청: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* 응답:성공한 경우 `204 No Content` 코드를 반환합니다.