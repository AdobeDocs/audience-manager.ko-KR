---
description: 레이스 조건 및 DCS 오류 처리를 방지하는 방법을 설명합니다.
seo-description: 레이스 조건 및 DCS 오류 처리를 방지하는 방법을 설명합니다.
seo-title: 레이스 조건 및 오류 처리
solution: Audience Manager
title: 레이스 조건 및 오류 처리
uuid: B 0 AAC 960-6732-4 E 96-87 A 5-40 BA 2755 E 02 D
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Race Conditions and Error Handling {#race-conditions-and-error-handling}

Describes how to prevent race conditions and [!UICONTROL DCS] error handling.

## Preventing Race Conditions {#prevent-race-conditions}

A race condition can occur if you send multiple calls simultaneously (or in rapid succession) to the [!UICONTROL DCS] before it finishes responding to the initial queries and writing data to the user’s cookie. 쿠키 데이터는 쿠키 데이터를 손상시키거나 잘못 덮어쓸 수 있으므로 바람직하지 않습니다. 이 문제를 방지하려면 다음 방법을 고려하십시오.

* Don&#39;t make simultaneous calls, or calls in rapid succession, to the [!UICONTROL DCS] from the same user.
* 후속 호출을 하기 전에 각 응답이 다시 돌아올 때까지 기다립니다.

## Error Handling {#error-handling}

오류 처리는 잘못되었거나 잘못 구성된 쿼리에 대해서만 제한됩니다. An invalid request returns an `HTTP 200 OK` response and no data. Also, the [!UICONTROL DCS] stops processing a request, discards trait data, and returns an `HTTP 200 OK` response when a user:

* Audience Manager 또는 파트너 수준에서 추적을 옵트아웃합니다.
* 은 유효하지 않거나 선택되지 않은 지리적 영역에서 옵니다.
* 브라우저 쿠키 (모두 또는 타사) 를 비활성화합니다.

[DCS 오류 코드, 메시지 및 예제를 참조하십시오](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).