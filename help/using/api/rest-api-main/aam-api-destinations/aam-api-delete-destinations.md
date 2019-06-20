---
description: 대상을 제거하고 세그먼트 매핑을 제거할 수 있는 삭제 및 게시 방법을 참조하십시오.
seo-description: 대상을 제거하고 세그먼트 매핑을 제거할 수 있는 삭제 및 게시 방법을 참조하십시오.
seo-title: 대상 삭제
solution: Audience Manager
title: 대상 삭제
uuid: 38 FB 2228-E 564-49 A 3-9930-3139 F 8799 A 8 F
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# Delete Destinations {#delete-destinations}

`DELETE` 대상 및 세그먼트 매핑을 제거할 수 `POST` 있는 메서드입니다.

<!-- r_delete_destinations_all.xml -->

## 대상 삭제

A `DELETE` method that removes a destination.

>[!NOTE]
>
>대상을 삭제하려면 먼저 모든 세그먼트 매핑을 제거해야 합니다.

* Request: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Response: Returns code `204 No Content` if successful.

## 일괄 삭제 대상

Remove multiple destinations with this `POST` method. Pass in destination IDs ( `destinationId`) with an array in the request body.

* 요청: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Response: Returns code `204 No Content` if successful.

## 세그먼트 매핑 ID 별로 대상 매핑 삭제

A `POST` method that removes destination mappings according to the specified segment ID.

* Request: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Response: Returns code `204 No Content` if successful.