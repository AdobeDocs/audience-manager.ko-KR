---
description: 경합 조건 및 DCS 오류 처리를 방지하는 방법을 설명합니다.
seo-description: Describes how to prevent race conditions and DCS error handling.
seo-title: Race Conditions and Error Handling
solution: Audience Manager
title: 경합 조건 및 오류 처리
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
exl-id: bfb0b684-6b15-434d-b5ec-5f8741c0c691
source-git-commit: 25d785097228ae66d20cf2b35c8ef63fd64936c6
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 0%

---

# 경합 조건, 속도 제한 및 오류 처리 {#race-conditions-and-error-handling}

경합 조건 및 [!DNL DCS] 오류 처리를 방지하는 방법에 대해 설명합니다.

## 경합 상태 방지 {#prevent-race-conditions}

초기 쿼리에 응답하고 사용자의 쿠키에 데이터를 쓰기 전에 [!DNL DCS]에 동시에(또는 빠르게 연속하여) 여러 호출을 보내는 경우 경합 상태가 발생할 수 있습니다. 경합 조건은 쿠키 데이터를 손상시키거나 잘못 덮어쓸 수 있으므로 바람직하지 않습니다. 이 문제를 방지하는 데 도움이 되는 다음 방법을 고려하는 것이 좋습니다.

* 같은 사용자의 [!DNL DCS](으)로 동시에 호출하거나 빠르게 연속하여 호출하지 마십시오.
* 후속 호출을 수행하기 전에 각 응답이 반환될 때까지 기다립니다.

## 속도 제한 {#rate-limiting}

Adobe은 서비스 가용성에 부정적인 영향을 미칠 수 있는 과도한 DCS API 호출을 감지하는 경우 속도 제한을 도입할 수 있습니다.

속도 제한이 활성화된 경우 DCS 호출에서 `429 Too Many Requests` HTTP 응답 상태 코드를 받을 수 있습니다. 이 HTTP 응답을 받으면 나중에 API 호출을 다시 시도하십시오.

## 오류 처리 {#error-handling}

잘못되거나 형식이 잘못된 쿼리에 대해 오류 처리가 제한됩니다. 잘못된 요청이 `HTTP 200 OK` 응답을 반환하고 데이터가 없습니다. 또한 [!DNL DCS]은(는) 요청 처리를 중지하고, 트레이트 데이터를 삭제하고, 사용자가 다음 경우에 `HTTP 200 OK` 응답을 반환합니다.

* Audience Manager 또는 파트너 수준에서 추적을 옵트아웃합니다.
* 유효하지 않거나 선택되지 않은 지리적 영역에서 가져옵니다.
* 브라우저 쿠키를 비활성화합니다(모두 또는 타사).

[DCS 오류 코드, 메시지 및 예제를 참조하십시오](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).
